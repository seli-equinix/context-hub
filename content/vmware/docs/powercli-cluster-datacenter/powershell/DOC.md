---
name: powercli-cluster-datacenter
description: "VMware PowerCLI 13.3 — Clusters, datacenters, resource pools, folders, DRS rules, HA, inventory management"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,cluster,datacenter,resource-pool,folder,drs,ha,inventory,Get-Cluster,New-Cluster,Set-Cluster,Remove-Cluster,Move-Cluster,Get-Datacenter,New-Datacenter,Set-Datacenter,Move-Datacenter,Remove-Datacenter,Get-Folder,New-Folder,Set-Folder,Move-Folder,Remove-Folder,Get-ResourcePool,New-ResourcePool,Set-ResourcePool,Move-ResourcePool,Remove-ResourcePool,Get-DrsRule,New-DrsRule,Set-DrsRule,Remove-DrsRule,Get-DrsClusterGroup,New-DrsClusterGroup,Set-DrsClusterGroup,Remove-DrsClusterGroup,Get-DrsRecommendation,Invoke-DrsRecommendation,Get-Inventory,Move-Inventory,Remove-Inventory,New-VIInventoryDrive,Get-TrustAuthorityCluster,Set-TrustAuthorityCluster,Get-TrustedCluster,Set-TrustedCluster,Get-TrustedClusterAppliedStatus,Add-TrustedClusterAttestationServiceInfo,Remove-TrustedClusterAttestationServiceInfo,Add-TrustedClusterKeyProviderServiceInfo,Remove-TrustedClusterKeyProviderServiceInfo,Get-LcmClusterDesiredStateRecommendation,Export-LcmClusterDesiredState,Import-LcmClusterDesiredState,Test-LcmClusterCompliance,Test-LcmClusterHealth,Get-LcmHardwareCompatibility,New-CnsContainerCluster"
---

# VMware PowerCLI — Clusters & Datacenters

## Golden Rule

**Cluster configuration controls the behavior of EVERY host and VM inside it. DRS, HA, and admission control are cluster-level decisions that cascade downward. Get these wrong and you lose VMs silently during host failures.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| Find clusters | `Get-Cluster` | First step for any cluster operation | Supports wildcards: `Get-Cluster -Name "Prod-*"` |
| Create cluster | `New-Cluster` | Standing up a new compute boundary | Enable DRS + HA at creation; retrofitting is harder |
| Configure DRS/HA | `Set-Cluster` | Changing automation level, admission control | Requires `-DrsEnabled`, `-HAEnabled` flags |
| Keep VMs together | `New-DrsRule -KeepTogether` | VMs must run on same host (app + DB) | Affinity rule -- DRS will never separate them |
| Separate VMs | `New-DrsRule -KeepTogether:$false` | HA redundancy (two DCs on different hosts) | Anti-affinity -- DRS ensures they never share a host |
| VM-to-host pinning | `New-DrsClusterGroup` + `New-DrsRule` | Licensing, GPU, or compliance constraints | Requires both a VM group and a host group |
| Resource governance | `New-ResourcePool` | Isolate tenant/team resource entitlements | Shares + limits + reservations control priority |
| Organize inventory | `New-Folder` | Logical grouping for permissions and scripts | Folders are permission boundaries -- design them early |

## Scenario: Create a Production Cluster with DRS and HA

```powershell
# Create datacenter and cluster in one flow
$dc = New-Datacenter -Name "US-East" -Location (Get-Folder -NoRecursion) -Server $vcenter

$cluster = New-Cluster -Name "Prod-Compute" -Location $dc `
    -DrsEnabled -DrsAutomationLevel FullyAutomated `
    -HAEnabled -HAAdmissionControlEnabled `
    -HAFailoverLevel 1 `
    -Server $vcenter

# Add hosts to the cluster (hosts must already be in vCenter inventory)
$hosts = Get-VMHost -Name "esxi0[1-4].example.com" -Server $vcenter
$hosts | Move-VMHost -Destination $cluster -Confirm:$false

# Verify cluster state
Get-Cluster "Prod-Compute" -Server $vcenter |
    Select-Object Name, DrsEnabled, DrsAutomationLevel,
        HAEnabled, HAFailoverLevel, @{N='Hosts';E={($_ | Get-VMHost).Count}} |
    Format-Table
```

CRITICAL: `-HAFailoverLevel 1` means HA reserves capacity to survive 1 host failure. In a 4-host cluster, that means 25% of cluster resources are reserved and unavailable for workloads. Set this based on your actual redundancy requirements.

## Scenario: DRS Rules -- Affinity and Anti-Affinity

DRS rules are the primary mechanism for controlling VM placement across hosts.

```powershell
# Anti-affinity: ensure two domain controllers never share a host
$cluster = Get-Cluster "Prod-Compute" -Server $vcenter
$dc1 = Get-VM "dc01" -Server $vcenter
$dc2 = Get-VM "dc02" -Server $vcenter
New-DrsRule -Cluster $cluster -Name "Separate-DCs" `
    -KeepTogether:$false -VM $dc1, $dc2 -Enabled:$true

# Affinity: keep app server and its local cache on the same host
$app = Get-VM "app-server" -Server $vcenter
$cache = Get-VM "redis-cache" -Server $vcenter
New-DrsRule -Cluster $cluster -Name "AppWithCache" `
    -KeepTogether:$true -VM $app, $cache -Enabled:$true

# VM-to-host affinity (pin GPU VMs to GPU hosts)
$gpuVMs = Get-VM -Tag "GPU-Workload" -Server $vcenter
$gpuHosts = Get-VMHost -Tag "GPU-Enabled" -Server $vcenter

$vmGroup = New-DrsClusterGroup -Cluster $cluster -Name "GPU-VMs" -VM $gpuVMs
$hostGroup = New-DrsClusterGroup -Cluster $cluster -Name "GPU-Hosts" -VMHost $gpuHosts
New-DrsRule -Cluster $cluster -Name "Pin-GPU-VMs" `
    -VMGroup $vmGroup -VMHostGroup $hostGroup `
    -Type ShouldRunOn -Enabled:$true

# Review all DRS rules in the cluster
Get-DrsRule -Cluster $cluster | Select-Object Name, Type, Enabled,
    @{N='VMs';E={($_.VMIds | ForEach-Object { (Get-VM -Id $_).Name }) -join ", "}} |
    Format-Table -AutoSize
```

CRITICAL: `MustRunOn` rules are hard constraints -- DRS will NOT violate them even during HA failover. If no valid host is available, the VM stays off. Use `ShouldRunOn` for soft preferences that DRS can override in emergencies.

## Scenario: Resource Pools for Multi-Tenant Isolation

```powershell
$cluster = Get-Cluster "Prod-Compute" -Server $vcenter

# Create resource pools with shares and limits
New-ResourcePool -Name "TeamA-Production" -Location $cluster `
    -CpuSharesLevel High -MemSharesLevel High `
    -CpuReservationMHz 8000 -MemReservationGB 32

New-ResourcePool -Name "TeamB-Dev" -Location $cluster `
    -CpuSharesLevel Low -MemSharesLevel Low `
    -CpuLimitMHz 4000 -MemLimitGB 16

# Inventory resource pools with utilization
Get-ResourcePool -Location $cluster | ForEach-Object {
    $vms = Get-VM -Location $_ -Server $vcenter
    [PSCustomObject]@{
        Pool          = $_.Name
        CpuShares     = $_.CpuSharesLevel
        MemShares     = $_.MemSharesLevel
        CpuLimitMHz   = $_.CpuLimitMHz
        MemLimitGB    = [math]::Round($_.MemLimitMB / 1024, 1)
        VMCount       = $vms.Count
    }
} | Format-Table -AutoSize
```

## Scenario: Folder Structure for Permissions and Automation

```powershell
# Build a folder hierarchy for inventory organization
$dc = Get-Datacenter "US-East" -Server $vcenter
$vmFolder = Get-Folder -Type VM -Location $dc -NoRecursion | Select-Object -First 1

# Create environment folders
@("Production", "Staging", "Development") | ForEach-Object {
    New-Folder -Name $_ -Location $vmFolder -Server $vcenter
}

# Create sub-folders per team
$prodFolder = Get-Folder "Production" -Type VM -Server $vcenter
@("Web-Tier", "App-Tier", "DB-Tier") | ForEach-Object {
    New-Folder -Name $_ -Location $prodFolder -Server $vcenter
}

# Move VMs into the correct folder
Get-VM -Name "web-*" -Server $vcenter |
    Move-VM -InventoryLocation (Get-Folder "Web-Tier" -Server $vcenter)
```

## Common Mistakes

### Mistake 1: Enabling HA Without Understanding Admission Control

```powershell
# WRONG -- HA enabled but failover level too aggressive for a small cluster
New-Cluster -Name "Small-Cluster" -Location $dc `
    -HAEnabled -HAFailoverLevel 2 -DrsEnabled
# In a 3-host cluster, this reserves 66% of resources -- only 1/3 usable!

# CORRECT -- Match failover level to cluster size
# 3-4 hosts: failover level 1 (25-33% reserved)
# 6+ hosts: failover level 2 is reasonable
New-Cluster -Name "Small-Cluster" -Location $dc `
    -HAEnabled -HAFailoverLevel 1 -DrsEnabled `
    -HAAdmissionControlEnabled
```

### Mistake 2: Using MustRunOn DRS Rules Instead of ShouldRunOn

```powershell
# WRONG -- Hard constraint: if GPU host fails, VM stays powered off
New-DrsRule -Cluster $cluster -Name "Pin-GPU" `
    -VMGroup $vmGroup -VMHostGroup $hostGroup `
    -Type MustRunOn -Enabled:$true

# CORRECT -- Soft constraint: DRS prefers GPU hosts but can failover elsewhere
New-DrsRule -Cluster $cluster -Name "Pin-GPU" `
    -VMGroup $vmGroup -VMHostGroup $hostGroup `
    -Type ShouldRunOn -Enabled:$true
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-Cluster` | Find clusters | `-Name`, `-Server`, `-Location`, `-VM`, `-VMHost` |
| `New-Cluster` | Create cluster | `-Name`, `-Location`, `-DrsEnabled`, `-DrsAutomationLevel`, `-HAEnabled`, `-HAFailoverLevel` |
| `Set-Cluster` | Modify cluster | `-DrsEnabled`, `-DrsAutomationLevel`, `-HAEnabled`, `-HAAdmissionControlEnabled` |
| `Get-Datacenter` | Find datacenters | `-Name`, `-Server`, `-VMHost` |
| `New-Datacenter` | Create datacenter | `-Name`, `-Location` |
| `Get-Folder` | Find folders | `-Name`, `-Type` (VM/HostAndCluster/Network/Datastore), `-Location`, `-NoRecursion` |
| `New-Folder` | Create folder | `-Name`, `-Location` |
| `Move-Folder` | Relocate folder | `-Destination` |
| `Get-ResourcePool` | Find pools | `-Name`, `-Location`, `-VM` |
| `New-ResourcePool` | Create pool | `-Name`, `-Location`, `-CpuSharesLevel`, `-MemSharesLevel`, `-CpuLimitMHz`, `-MemLimitGB` |
| `Set-ResourcePool` | Modify pool | `-CpuSharesLevel`, `-CpuReservationMHz`, `-CpuLimitMHz`, `-MemSharesLevel` |
| `Get-DrsRule` | List DRS rules | `-Cluster`, `-Name`, `-VM` |
| `New-DrsRule` | Create affinity/anti-affinity | `-Cluster`, `-Name`, `-VM`, `-KeepTogether`, `-Enabled` |
| `New-DrsClusterGroup` | Create VM/host group | `-Cluster`, `-Name`, `-VM` or `-VMHost` |
| `Get-DrsRecommendation` | Pending DRS moves | `-Cluster` |
| `Invoke-DrsRecommendation` | Apply DRS moves | `-DrsRecommendation` |
| `Get-Inventory` | Generic inventory search | `-Name`, `-Location`, `-NoRecursion` |
| `Move-Inventory` | Move any inventory item | `-Item`, `-Destination` |
| `Test-LcmClusterCompliance` | Check image compliance | `-Cluster` |
| `Test-LcmClusterHealth` | Pre-remediation health | `-Cluster` |

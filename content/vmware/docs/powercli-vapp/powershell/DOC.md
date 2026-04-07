---
name: powercli-vapp
description: "VMware PowerCLI 13.3 — vApp management for multi-VM application stacks, resource control, and OVF export/import"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vapp,virtual-appliance,multi-vm,Get-VApp,New-VApp,Set-VApp,Remove-VApp,Start-VApp,Stop-VApp,Move-VApp,Export-VApp,Import-VApp"
---

# VMware PowerCLI — vApp Management

## Golden Rule

**A vApp is a container for multiple VMs that form a single application stack. It controls startup order, resource allocation, and OVF packaging. Use vApps when you need to manage a multi-tier application (web + app + db) as a single unit.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| Find vApps | `Get-VApp` | Listing application stacks | Returns vApp container, not individual VMs |
| Create vApp | `New-VApp` | Grouping VMs into an application stack | Requires a location (cluster, host, or resource pool) |
| Start all VMs | `Start-VApp` | Booting the entire application in order | Respects startup order defined in vApp properties |
| Stop all VMs | `Stop-VApp` | Shutting down the stack in reverse order | `-Force` for hard power off |
| Export stack | `Export-VApp` | Packaging entire application as OVF/OVA | Includes all VMs, disks, and vApp metadata |
| Import stack | `Import-VApp` | Deploying a packaged application | OVF/OVA source with network mapping |
| Move vApp | `Move-VApp` | Relocating to different resource pool/host | Does NOT storage-vMotion the VMs |
| Configure | `Set-VApp` | Changing resource limits, startup order | Resource settings apply to all VMs inside |
| Delete vApp | `Remove-VApp` | Decommissioning an application stack | `-DeletePermanently` also deletes all VM disk files |

## Scenario: Create a Multi-Tier Application vApp

```powershell
# Create a vApp container
$cluster = Get-Cluster "Production" -Server $vcenter
$vapp = New-VApp -Name "WebApp-Prod" -Location $cluster `
    -CpuLimitMHz 16000 -MemLimitGB 64 `
    -Description "Production web application stack" -Server $vcenter

# Move existing VMs into the vApp
Get-VM "webapp-db-01", "webapp-app-01", "webapp-web-01" -Server $vcenter |
    Move-VM -Destination $vapp -Confirm:$false

# Configure resource allocation for the vApp
Set-VApp -VApp $vapp -CpuSharesLevel High -MemSharesLevel High -Server $vcenter

# Start the entire application (VMs boot in defined order)
Start-VApp -VApp $vapp -Server $vcenter

# Stop the entire application (reverse order, graceful shutdown)
Stop-VApp -VApp $vapp -Confirm:$false -Server $vcenter
```

## Scenario: Export and Import Application Stack

```powershell
# Export the entire vApp as an OVA package
$vapp = Get-VApp "WebApp-Prod" -Server $vcenter
Export-VApp -VApp $vapp -Destination "C:\Exports\WebApp-Prod.ova" `
    -Format OVA -Force -Description "WebApp production backup $(Get-Date -Format 'yyyy-MM-dd')"

# Import at another site
$vmhost = Get-VMHost "esxi01.example.com" -Server $remoteVcenter
$ds = Get-Datastore "VMFS-Prod-01" -Server $remoteVcenter
$ovfConfig = Get-OvfConfiguration -Ovf "C:\Exports\WebApp-Prod.ova"
$ovfConfig.NetworkMapping.VM_Network.Value = "VLAN-200-App"

Import-VApp -Source "C:\Exports\WebApp-Prod.ova" -VMHost $vmhost `
    -Datastore $ds -OvfConfiguration $ovfConfig `
    -Name "WebApp-DR" -DiskStorageFormat Thin -Server $remoteVcenter

# Inventory: list all vApps with their VMs
Get-VApp -Server $vcenter | ForEach-Object {
    $vms = Get-VM -Location $_ -Server $vcenter
    [PSCustomObject]@{
        VApp   = $_.Name
        Status = $_.Status
        VMs    = ($vms.Name -join ", ")
        VMCount = $vms.Count
    }
} | Format-Table -AutoSize
```

## Common Mistakes

### Mistake 1: Using Remove-VApp Without Understanding the Scope

```powershell
# WRONG -- Removes vApp AND all VMs inside it from inventory
Remove-VApp -VApp "WebApp-Prod" -Confirm:$false
# VMs are gone from inventory (but disk files remain)

# ALSO WRONG -- Removes vApp, VMs, AND all disk files
Remove-VApp -VApp "WebApp-Prod" -DeletePermanently -Confirm:$false

# CORRECT -- Move VMs out first if you only want to dissolve the container
Get-VM -Location (Get-VApp "WebApp-Prod") |
    Move-VM -Destination (Get-Cluster "Production") -Confirm:$false
Remove-VApp -VApp "WebApp-Prod" -Confirm:$false  # Now safe -- vApp is empty
```

### Mistake 2: Forgetting OVF Network Mapping on Import

```powershell
# WRONG -- Import without network mapping, VMs connect to nonexistent networks
Import-VApp -Source "app.ova" -VMHost $vmhost -Datastore $ds

# CORRECT -- Check and set network mappings
$ovfConfig = Get-OvfConfiguration -Ovf "app.ova"
$ovfConfig.NetworkMapping.VM_Network.Value = "VLAN-200-App"
Import-VApp -Source "app.ova" -VMHost $vmhost -Datastore $ds `
    -OvfConfiguration $ovfConfig
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-VApp` | Find vApps | `-Name`, `-Location`, `-Server` |
| `New-VApp` | Create vApp | `-Name`, `-Location` (cluster/host/pool), `-CpuLimitMHz`, `-MemLimitGB` |
| `Set-VApp` | Configure vApp | `-Name`, `-CpuSharesLevel`, `-MemSharesLevel`, `-CpuLimitMHz`, `-MemLimitGB` |
| `Start-VApp` | Power on all VMs | `-VApp` -- respects startup order |
| `Stop-VApp` | Power off all VMs | `-VApp`, `-Force` (hard stop vs graceful) |
| `Move-VApp` | Relocate vApp | `-VApp`, `-Destination` (host/cluster/pool) |
| `Remove-VApp` | Delete vApp | `-VApp`, `-DeletePermanently` (also deletes VM disks) |
| `Export-VApp` | Export to OVF/OVA | `-VApp` or `-VM`, `-Destination`, `-Format` (OVF/OVA), `-Force` |
| `Import-VApp` | Import OVF/OVA | `-Source`, `-VMHost`, `-Datastore`, `-OvfConfiguration`, `-Name` |

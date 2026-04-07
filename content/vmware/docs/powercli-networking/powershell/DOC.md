---
name: powercli-networking
description: "VMware PowerCLI 13.3 — Standard and distributed virtual switches, port groups, VLANs, NIC teaming, traffic shaping, security policies, VM network adapters"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,networking,vswitch,distributed-switch,vds,port-group,vlan,nic-teaming,traffic-shaping,security-policy,network-adapter,Get-VirtualSwitch,New-VirtualSwitch,Set-VirtualSwitch,Remove-VirtualSwitch,Get-VirtualPortGroup,New-VirtualPortGroup,Set-VirtualPortGroup,Remove-VirtualPortGroup,Get-VDSwitch,New-VDSwitch,Set-VDSwitch,Remove-VDSwitch,Get-VDPortgroup,New-VDPortgroup,Set-VDPortgroup,Remove-VDPortGroup,Get-VDPort,Set-VDPort,Get-NicTeamingPolicy,Set-NicTeamingPolicy,Get-VDTrafficShapingPolicy,Set-VDTrafficShapingPolicy,Get-VDSecurityPolicy,Set-VDSecurityPolicy,Get-VDBlockedPolicy,Set-VDBlockedPolicy,Get-VDUplinkTeamingPolicy,Set-VDUplinkTeamingPolicy,Get-VDUplinkLacpPolicy,Set-VDUplinkLacpPolicy,Get-VDSwitchPrivateVlan,New-VDSwitchPrivateVlan,Remove-VDSwitchPrivateVlan,Add-VDSwitchPhysicalNetworkAdapter,Remove-VDSwitchPhysicalNetworkAdapter,Add-VDSwitchVMHost,Remove-VDSwitchVMHost,Export-VDPortGroup,Export-VDSwitch,Get-VirtualNetwork,Add-VirtualSwitchPhysicalNetworkAdapter,Remove-VirtualSwitchPhysicalNetworkAdapter,Set-VDVlanConfiguration,Get-NetworkAdapter,Set-NetworkAdapter,New-NetworkAdapter"
---

# VMware PowerCLI — Networking

## Golden Rule

**Understand the two types of virtual switches:**

| Feature | Standard vSwitch | Distributed vSwitch (VDS) |
|---------|-----------------|--------------------------|
| Scope | Per-host | Across cluster (managed by vCenter) |
| Create with | `New-VirtualSwitch` | `New-VDSwitch` |
| Port groups | `New-VirtualPortGroup` | `New-VDPortgroup` |
| Configuration | Per-host — must repeat on each ESXi | Central — changes propagate to all hosts |
| Migration | Manual | Automatic with host add/remove |
| Use when | Small environments, testing | Production — consistent network policy |
| EVA uses | Rarely | Always (enterprise standard) |

**Key decision: Standard vs Distributed**
- If you manage 2+ hosts → use VDS (distributed)
- If single host / lab → standard vSwitch is simpler
- EVA environments always use VDS with VLAN-backed port groups

## Scenario: Inventory Network Configuration

Before making changes, audit what exists:

```powershell
# List all distributed switches
Get-VDSwitch -Server $vcenter | 
    Select-Object Name, NumUplinkPorts, NumPorts, Mtu, Version | Format-Table

# List all port groups with VLAN info
Get-VDPortgroup -Server $vcenter | 
    Select-Object Name, VDSwitch, VlanConfiguration, NumPorts | Format-Table

# Find which port group a VM is connected to
$vm = Get-VM -Name "web-01" -Server $vcenter
Get-NetworkAdapter -VM $vm | 
    Select-Object Name, NetworkName, Type, MacAddress, ConnectionState | Format-Table

# List all VLANs in use across the environment
Get-VDPortgroup | ForEach-Object {
    [PSCustomObject]@{
        PortGroup = $_.Name
        Switch = $_.VDSwitch.Name
        VLAN = $_.VlanConfiguration
        Ports = $_.NumPorts
    }
} | Sort-Object VLAN | Format-Table
```

## Scenario: Create Distributed Switch and Port Groups

```powershell
# Create a new VDS with 2 uplinks
$vds = New-VDSwitch -Name "VDS-Production" -Location (Get-Datacenter "DC1") `
    -NumUplinkPorts 2 -Mtu 9000 -Server $vcenter

# Add hosts to the VDS
$hosts = Get-VMHost -Location (Get-Cluster "Production") -Server $vcenter
$hosts | ForEach-Object {
    Add-VDSwitchVMHost -VDSwitch $vds -VMHost $_
    # Map physical NICs to uplinks
    $pNics = Get-VMHostNetworkAdapter -VMHost $_ -Physical | 
        Where-Object { $_.Name -match "vmnic[2-3]" }
    Add-VDSwitchPhysicalNetworkAdapter -DistributedSwitch $vds `
        -VMHostPhysicalNic $pNics -Confirm:$false
}

# Create VLAN-backed port groups
$vlans = @{
    "VLAN-100-Web" = 100
    "VLAN-200-App" = 200
    "VLAN-300-DB" = 300
    "VLAN-400-Mgmt" = 400
}
foreach ($pg in $vlans.GetEnumerator()) {
    New-VDPortgroup -Name $pg.Key -VDSwitch $vds -VlanId $pg.Value -NumPorts 128
}

# Verify
Get-VDPortgroup -VDSwitch $vds | Select-Object Name, VlanConfiguration | Format-Table
```

## Scenario: Change VM Network (EVA Pattern)

```powershell
# Move VM from one port group to another
$vm = Get-VM -Name "web-01" -Server $vcenter
$targetPG = Get-VDPortgroup -Name "VLAN-200-App" -Server $vcenter

# Get the VM's network adapter and change it
Get-NetworkAdapter -VM $vm | 
    Set-NetworkAdapter -Portgroup $targetPG -Connected:$true -Confirm:$false

# Verify the change
Get-NetworkAdapter -VM $vm | Select-Object Name, NetworkName, MacAddress, ConnectionState

# Bulk move: change all VMs in a folder to a new port group
$folder = Get-Folder -Name "Web Servers"
Get-VM -Location $folder | ForEach-Object {
    Get-NetworkAdapter -VM $_ | 
        Set-NetworkAdapter -Portgroup $targetPG -Confirm:$false
    Write-Output "Moved $($_.Name) to $($targetPG.Name)"
}
```

## Scenario: Configure NIC Teaming and Failover

```powershell
# Get current teaming policy on a standard vSwitch
$vss = Get-VirtualSwitch -VMHost "esxi01.example.com" -Name "vSwitch0"
Get-NicTeamingPolicy -VirtualSwitch $vss

# Set active/standby NICs for failover
Set-NicTeamingPolicy -VirtualSwitch $vss `
    -MakeNicActive "vmnic0" -MakeNicStandby "vmnic1" `
    -LoadBalancingPolicy LoadBalanceSrcId `
    -NetworkFailoverDetectionPolicy LinkStatus `
    -NotifySwitches $true -FailbackEnabled $true

# For distributed switches — configure uplink teaming per port group
$pg = Get-VDPortgroup -Name "VLAN-100-Web"
$policy = Get-VDUplinkTeamingPolicy -VDPortgroup $pg
Set-VDUplinkTeamingPolicy -Policy $policy `
    -LoadBalancingPolicy LoadBalanceSrcId `
    -ActiveUplinkPort "Uplink 1" -StandbyUplinkPort "Uplink 2" `
    -EnableFailback $true
```

## Scenario: Configure Security Policies

```powershell
# Get security policy on a distributed port group
$pg = Get-VDPortgroup -Name "VLAN-100-Web"
Get-VDSecurityPolicy -VDPortgroup $pg

# Set security: disable promiscuous mode, allow MAC changes, allow forged transmits
Set-VDSecurityPolicy -VDPortgroup $pg `
    -AllowPromiscuous $false `
    -MacChanges $true `
    -ForgedTransmits $true

# For standard vSwitch port groups
$vss = Get-VirtualSwitch -Name "vSwitch0" -VMHost "esxi01"
$standardPG = Get-VirtualPortGroup -VirtualSwitch $vss -Name "VM Network"
# Security settings are at the vSwitch level for standard switches
```

CRITICAL: Promiscuous mode should be DISABLED in production. Only enable for network monitoring/IDS. MAC changes and forged transmits are needed for nested virtualization and some load balancers.

## Scenario: Traffic Shaping

```powershell
# Configure traffic shaping on a distributed port group
$pg = Get-VDPortgroup -Name "VLAN-100-Web"

# Ingress (incoming to VM) shaping
Set-VDTrafficShapingPolicy -VDPortgroup $pg -Direction In `
    -Enabled $true -AverageBandwidth 1000000 `
    -PeakBandwidth 1500000 -BurstSize 2048000

# Egress (outgoing from VM) shaping
Set-VDTrafficShapingPolicy -VDPortgroup $pg -Direction Out `
    -Enabled $true -AverageBandwidth 1000000 `
    -PeakBandwidth 1500000 -BurstSize 2048000
```

NOTE: Bandwidth values are in Kbps. 1000000 Kbps = 1 Gbps.

## Common Mistakes

### Mistake 1: Confusing Standard and Distributed Cmdlets

```powershell
# WRONG — Using standard vSwitch cmdlet when you have VDS
$switch = Get-VirtualSwitch -Name "VDS-Production"  # Returns nothing or wrong object

# CORRECT — Use VDS-specific cmdlet
$switch = Get-VDSwitch -Name "VDS-Production"

# Same for port groups:
# Standard: Get-VirtualPortGroup  /  Distributed: Get-VDPortgroup
```

### Mistake 2: Forgetting to Add Physical NICs to VDS

```powershell
# WRONG — Create VDS, add host, but no physical NICs mapped
$vds = New-VDSwitch -Name "VDS-Prod" -Location (Get-Datacenter)
Add-VDSwitchVMHost -VDSwitch $vds -VMHost $host
# VDS has no uplinks — VMs on this VDS have no external connectivity!

# CORRECT — Add host AND map physical NICs
Add-VDSwitchVMHost -VDSwitch $vds -VMHost $host
$pNic = Get-VMHostNetworkAdapter -VMHost $host -Physical -Name "vmnic2"
Add-VDSwitchPhysicalNetworkAdapter -DistributedSwitch $vds -VMHostPhysicalNic $pNic -Confirm:$false
```

### Mistake 3: Wrong VLAN ID on Port Group

```powershell
# WRONG — VLAN 0 means no VLAN tagging (trunk all)
New-VDPortgroup -Name "Web-Servers" -VDSwitch $vds -VlanId 0

# CORRECT — Specify the actual VLAN ID
New-VDPortgroup -Name "Web-Servers" -VDSwitch $vds -VlanId 100

# For trunk port (passes all VLANs):
New-VDPortgroup -Name "Trunk-Port" -VDSwitch $vds -VlanTrunkRange "100-400"
```

### Mistake 4: Changing Network on Running VM Without -Connected

```powershell
# WRONG — Changes port group but NIC stays disconnected
Get-NetworkAdapter -VM $vm | Set-NetworkAdapter -Portgroup $newPG -Confirm:$false

# CORRECT — Also ensure NIC is connected
Get-NetworkAdapter -VM $vm | 
    Set-NetworkAdapter -Portgroup $newPG -Connected:$true -StartConnected:$true -Confirm:$false
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| **Distributed Switches** | | |
| `Get-VDSwitch` | List VDS | `-Name`, `-VMHost` |
| `New-VDSwitch` | Create VDS | `-Name`, `-Location`, `-NumUplinkPorts`, `-Mtu` |
| `Set-VDSwitch` | Modify VDS | `-Name`, `-Mtu`, `-NumUplinkPorts` |
| `Add-VDSwitchVMHost` | Add host to VDS | `-VDSwitch`, `-VMHost` |
| `Add-VDSwitchPhysicalNetworkAdapter` | Map pNIC to uplink | `-DistributedSwitch`, `-VMHostPhysicalNic` |
| **Distributed Port Groups** | | |
| `Get-VDPortgroup` | List port groups | `-Name`, `-VDSwitch` |
| `New-VDPortgroup` | Create port group | `-Name`, `-VDSwitch`, `-VlanId`, `-NumPorts` |
| `Set-VDPortgroup` | Modify port group | `-Name`, `-NumPorts` |
| `Get-VDPort` | List individual ports | `-VDPortgroup`, `-ConnectedOnly` |
| **Standard Switches** | | |
| `Get-VirtualSwitch` | List standard vSwitch | `-Name`, `-VMHost`, `-Standard` |
| `New-VirtualSwitch` | Create vSwitch | `-Name`, `-VMHost`, `-Nic` (physical NIC) |
| `Get-VirtualPortGroup` | List standard PGs | `-Name`, `-VirtualSwitch` |
| `New-VirtualPortGroup` | Create standard PG | `-Name`, `-VirtualSwitch`, `-VLanId` |
| **Policies** | | |
| `Get-VDSecurityPolicy` | Security settings | `-VDPortgroup` |
| `Set-VDSecurityPolicy` | Set security | `-AllowPromiscuous`, `-MacChanges`, `-ForgedTransmits` |
| `Get-VDTrafficShapingPolicy` | Traffic limits | `-VDPortgroup`, `-Direction` |
| `Set-VDTrafficShapingPolicy` | Set traffic limits | `-AverageBandwidth`, `-PeakBandwidth`, `-BurstSize` |
| `Get-NicTeamingPolicy` | NIC failover | `-VirtualSwitch` or `-VirtualPortGroup` |
| `Set-NicTeamingPolicy` | Set failover | `-MakeNicActive`, `-MakeNicStandby`, `-LoadBalancingPolicy` |
| **VM NICs** | | |
| `Get-NetworkAdapter` | VM's NICs | `-VM`, `-Name` |
| `Set-NetworkAdapter` | Change NIC settings | `-Portgroup`, `-Connected`, `-MacAddress`, `-Type` |
| `New-NetworkAdapter` | Add NIC to VM | `-VM`, `-Portgroup`, `-Type` (e1000, Vmxnet3) |

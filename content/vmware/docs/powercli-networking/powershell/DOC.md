---
name: powercli-networking
description: "VMware PowerCLI virtual networking cmdlets -- distributed switches, port groups, standard switches, and host network adapters"
metadata:
  languages: "powershell"
  versions: "13.3,9.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vds,vdswitch,distributed-switch,port-group,vswitch,networking,vlan"
---

# VMware PowerCLI -- Virtual Networking Reference

This covers the `VMware.VimAutomation.Vds` (Distributed Switch) module and networking cmdlets from `VMware.VimAutomation.Core`.

> Ground truth: PowerCLI built-in help and Broadcom Developer Portal.

## Distributed Virtual Switches

### Get-VDSwitch

```
Get-VDSwitch [[-Name] <String[]>]
    [-Location <FolderContainer[]>]
    [-VM <VirtualMachine[]>] [-VMHost <VMHost[]>]
    [-Tag <Tag[]>] [-Server <VIServer[]>]

Get-VDSwitch -Id <String[]> [-Server <VIServer[]>]
Get-VDSwitch -RelatedObject <VDSwitchRelatedObjectBase[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | String[] | No (pos 0) | Switch names. Supports wildcards |
| `-Location` | FolderContainer[] | No | Folder/datacenter to search |
| `-VM` | VirtualMachine[] | No | Get switches connected to specific VMs |
| `-VMHost` | VMHost[] | No | Get switches connected to specific hosts |

**Returns**: `VDSwitch` objects

```powershell
# All distributed switches:
Get-VDSwitch

# By name:
Get-VDSwitch -Name "Production-VDS"

# Switches connected to a specific host:
Get-VDSwitch -VMHost (Get-VMHost "esxi01")
```

### New-VDSwitch

```
# Create new:
New-VDSwitch -Name <String> -Location <VIContainer>
    [-NumUplinkPorts <Int32>] [-MaxPorts <Int32>] [-Mtu <Int32>]
    [-ContactName <String>] [-ContactDetails <String>] [-Notes <String>]
    [-Version <String>]
    [-LinkDiscoveryProtocol <LinkDiscoveryProtocol>]
    [-LinkDiscoveryProtocolOperation <LinkDiscoveryOperation>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Import from backup:
New-VDSwitch -BackupPath <String> -Location <VIContainer>
    [-Name <String>] [-KeepIdentifiers] [-WithoutPortGroups]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Clone from reference:
New-VDSwitch -Name <String> -Location <VIContainer>
    -ReferenceVDSwitch <VDSwitch>
    [-WithoutPortGroups] [-RunAsync] [-Confirm] [-WhatIf]
```

**Returns**: `VDSwitch` object

```powershell
# Create distributed switch:
$dc = Get-Datacenter "Production"
New-VDSwitch -Name "Production-VDS" -Location $dc `
    -NumUplinkPorts 4 -Mtu 9000 -Version "7.0.0" `
    -Notes "Production traffic VDS"

# Clone from existing:
$ref = Get-VDSwitch -Name "Template-VDS"
New-VDSwitch -Name "NewSite-VDS" -Location $dc -ReferenceVDSwitch $ref
```

---

## Distributed Port Groups

### Get-VDPortgroup

```
Get-VDPortgroup [[-Name] <String[]>]
    [-VDSwitch <VDSwitch[]>]
    [-NetworkAdapter <NetworkAdapter[]>]
    [-VMHostNetworkAdapter <HostVirtualNic[]>]
    [-Tag <Tag[]>] [-Server <VIServer[]>]

Get-VDPortgroup -Id <String[]> [-Server <VIServer[]>]
Get-VDPortgroup -RelatedObject <VDPortgroupRelatedObjectBase[]>
```

**Returns**: `VDPortgroup` objects

```powershell
# All port groups on a VDS:
Get-VDPortgroup -VDSwitch (Get-VDSwitch "Production-VDS")

# By name:
Get-VDPortgroup -Name "VLAN100-Web"

# Port group for a specific NIC:
$nic = Get-VM "WebServer01" | Get-NetworkAdapter
Get-VDPortgroup -NetworkAdapter $nic
```

### New-VDPortgroup

```
# Create new:
New-VDPortgroup [-VDSwitch] <VDSwitch> -Name <String>
    [-NumPorts <Int32>] [-VlanId <Int32>] [-VlanTrunkRange <VlanRangeList>]
    [-PortBinding <DistributedPortGroupPortBinding>]
    [-Notes <String>] [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Import from backup:
New-VDPortgroup [-VDSwitch] <VDSwitch> -BackupPath <String>
    [-Name <String>] [-KeepIdentifiers] [-RunAsync] [-Confirm] [-WhatIf]

# Clone from reference:
New-VDPortgroup [-VDSwitch] <VDSwitch> -ReferencePortgroup <VDPortgroup>
    [-Name <String>] [-RunAsync] [-Confirm] [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VDSwitch` | VDSwitch | Yes (pos 0) | Parent distributed switch |
| `-Name` | String | Yes | Port group name |
| `-VlanId` | Int32 | No | VLAN ID (0-4094) |
| `-VlanTrunkRange` | VlanRangeList | No | VLAN trunk range (e.g., "100-200") |
| `-NumPorts` | Int32 | No | Number of ports |
| `-PortBinding` | DistributedPortGroupPortBinding | No | `Static`, `Dynamic`, `Ephemeral` |

**Returns**: `VDPortgroup` object

```powershell
# Create VLAN-tagged port group:
$vds = Get-VDSwitch "Production-VDS"
New-VDPortgroup -VDSwitch $vds -Name "VLAN100-Web" -VlanId 100 `
    -PortBinding Static -NumPorts 128

# Create trunk port group:
New-VDPortgroup -VDSwitch $vds -Name "Trunk-All" -VlanTrunkRange "1-4094"
```

---

## Standard Virtual Switches

### Get-VirtualSwitch

```
Get-VirtualSwitch [[-VMHost] <VMHost[]>] [[-VM] <VirtualMachine[]>]
    [-Datacenter <Datacenter[]>] [-Name <String[]>]
    [-Standard] [-Distributed]
    [-Server <VIServer[]>]

Get-VirtualSwitch -Id <String[]> [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VMHost` | VMHost[] | No (pos 0) | Filter by host |
| `-VM` | VirtualMachine[] | No (pos 1) | Filter by connected VMs |
| `-Standard` | Switch | No | Return only standard switches |
| `-Distributed` | Switch | No | Return only distributed switches |
| `-Name` | String[] | No | Switch name(s) |

**Returns**: `VirtualSwitchBase` objects (either `VirtualSwitch` or `DistributedSwitch`)

```powershell
# Standard switches on a host:
Get-VirtualSwitch -VMHost "esxi01" -Standard

# All distributed switches:
Get-VirtualSwitch -Distributed

# Switches used by a VM:
Get-VirtualSwitch -VM (Get-VM "WebServer01")
```

### Get-VirtualPortGroup

```
Get-VirtualPortGroup [[-VMHost] <VMHost[]>]
    [-VirtualSwitch <VirtualSwitchBase[]>] [-VM <VirtualMachine[]>]
    [-Datacenter <Datacenter[]>] [-Name <String[]>]
    [-Standard] [-Distributed]
    [-Tag <Tag[]>] [-Server <VIServer[]>]

Get-VirtualPortGroup -Id <String[]> [-Server <VIServer[]>]
```

**Returns**: `VirtualPortGroup` or `DistributedPortGroup` objects

```powershell
# Standard port groups on a host:
Get-VirtualPortGroup -VMHost "esxi01" -Standard

# Port groups on a specific switch:
Get-VirtualPortGroup -VirtualSwitch (Get-VirtualSwitch -Name "vSwitch0")

# All port groups with VLAN info:
Get-VirtualPortGroup | Select-Object Name, VirtualSwitch, VLanId
```

---

## Common Networking Patterns

### VM Network Audit

```powershell
# Report: which VMs are on which networks:
Get-VM | ForEach-Object {
    $vm = $_
    Get-NetworkAdapter -VM $vm | ForEach-Object {
        [PSCustomObject]@{
            VM          = $vm.Name
            Adapter     = $_.Name
            Type        = $_.Type
            Network     = $_.NetworkName
            MacAddress  = $_.MacAddress
            Connected   = $_.ConnectionState.Connected
        }
    }
} | Format-Table -AutoSize
```

### Migrate VMs Between Port Groups

```powershell
# Move all VMs from old network to new:
$oldPG = Get-VDPortgroup -Name "VLAN100-Legacy"
$newPG = Get-VDPortgroup -Name "VLAN100-New"

Get-VM | Get-NetworkAdapter | Where-Object { $_.NetworkName -eq $oldPG.Name } |
    Set-NetworkAdapter -Portgroup $newPG -Confirm:$false
```

### Create Full Network Stack

```powershell
# 1. Create VDS:
$dc = Get-Datacenter "Production"
$vds = New-VDSwitch -Name "Corp-VDS" -Location $dc -NumUplinkPorts 2 -Mtu 1500

# 2. Add hosts:
Get-VMHost | Add-VDSwitchVMHost -VDSwitch $vds

# 3. Create port groups:
New-VDPortgroup -VDSwitch $vds -Name "Web-VLAN100" -VlanId 100
New-VDPortgroup -VDSwitch $vds -Name "App-VLAN200" -VlanId 200
New-VDPortgroup -VDSwitch $vds -Name "DB-VLAN300" -VlanId 300
New-VDPortgroup -VDSwitch $vds -Name "Mgmt-VLAN10" -VlanId 10

# 4. Connect VM to port group:
$pg = Get-VDPortgroup -Name "Web-VLAN100"
Get-VM "WebServer01" | Get-NetworkAdapter |
    Set-NetworkAdapter -Portgroup $pg -Confirm:$false
```

---
name: powercli-networking
description: "VMware PowerCLI 13.3 — Virtual switches, distributed switches, port groups, VLAN, traffic shaping"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,networking,Add-VDSwitchPhysicalNetworkAdapter, Add-VirtualSwitchPhysicalNetworkAdapter, Export-VDPortGroup, Export-VDSwitch, Get-NicTeamingPolicy, Get-VDPort, Get-VDPortgroup, Get-VDPortgroupOverridePolicy, Get-VDSwitch, Get-VDSwitchPrivateVlan, Get-VirtualNetwork, Get-VirtualPortGroup, Get-VirtualSwitch, New-VDPortgroup, New-VDSwitch, New-VDSwitchPrivateVlan, New-VirtualPortGroup, New-VirtualSwitch, Remove-VDPortGroup, Remove-VDSwitch, Remove-VDSwitchPhysicalNetworkAdapter, Remove-VDSwitchPrivateVlan, Remove-VirtualPortGroup, Remove-VirtualSwitch, Remove-VirtualSwitchPhysicalNetworkAdapter, Set-NicTeamingPolicy, Set-VDPort, Set-VDPortgroup, Set-VDPortgroupOverridePolicy, Set-VDSwitch, Set-VirtualPortGroup, Set-VirtualSwitch"
---

# VMware PowerCLI — Networking

Virtual switches, distributed switches, port groups, VLAN, traffic shaping. Module: VMware.VimAutomation (32 cmdlets).

## Cmdlet Reference (32 cmdlets)

### Add

#### `Add-VDSwitchPhysicalNetworkAdapter`

This cmdlet adds host physical network adapters to a vSphere distributed switch.

**Parameters**: `VMHostPhysicalNic, DistributedSwitch, VirtualNicPortgroup, VMHostVirtualNic, Server`

#### `Add-VirtualSwitchPhysicalNetworkAdapter`

This cmdlet adds a host physical NIC to a standard virtual switch.

**Parameters**: `VMHostPhysicalNic, VirtualSwitch, VirtualNicPortgroup, VMHostVirtualNic, Server`

### Export

#### `Export-VDPortGroup`

This cmdlet exports the configuration of a specified distributed port group to a specified .zip file.

**Parameters**: `VDPortGroup, Description, Destination, Force, Server`

#### `Export-VDSwitch`

This cmdlet exports the configuration of a specified vSphere distributed switch to a .zip file.

**Parameters**: `VDSwitch, WithoutPortGroups, Description, Destination, Force, Server`

### Get

#### `Get-NicTeamingPolicy`

This cmdlet retrieves the NIC teaming policies of the specified virtual switches and virtual port groups.

**Parameters**: `VirtualSwitch, VirtualPortGroup, Server`

#### `Get-VDPort`

This cmdlet retrieves virtual distributed ports.

**Parameters**: `VDPortgroup, VDSwitch, Key, ActiveOnly, ConnectedOnly, Uplink, Server`

#### `Get-VDPortgroup`

This cmdlet retrieves distributed port groups.

**Parameters**: `Id, Name, NetworkAdapter, VDSwitch, VMHostNetworkAdapter, Server, RelatedObject, Tag`

#### `Get-VDPortgroupOverridePolicy`

This cmdlet retrieves the policy for overriding port group settings at port level.

**Parameters**: `VDPortgroup, Server`

#### `Get-VDSwitch`

This cmdlet retrieves vSphere distributed switches.

**Parameters**: `Id, Name, Location, VMHost, VM, RelatedObject, Tag, Server`

#### `Get-VDSwitchPrivateVlan`

This cmdlet retrieves the private VLAN configuration entries of a vSphere distributed switch.

**Parameters**: `VDSwitch, PrimaryVlanId, SecondaryVlanId, PrivateVlanType, Server`

#### `Get-VirtualNetwork`

The cmdlet retrieves all virtual networks on a vCenter server system.

**Parameters**: `Name, Location, NetworkType, Id, NoRecursion, Server`

#### `Get-VirtualPortGroup`

This cmdlet retrieves the available port groups of hosts, virtual machines, and virtual switches.

**Parameters**: `Id, VMHost, VM, VirtualSwitch, Name, Datacenter, Standard, Distributed, Tag, Server, RelatedObject`

#### `Get-VirtualSwitch`

This cmdlet retrieves the virtual switches associated with a virtual machine host or used by a virtual machine.

**Parameters**: `Id, VMHost, VM, Datacenter, Name, Standard, Distributed, RelatedObject, Server`

### New

#### `New-VDPortgroup`

This cmdlet creates distributed port groups.

**Parameters**: `VDSwitch, Name, Notes, NumPorts, VlanId, VlanTrunkRange, PortBinding, BackupPath, KeepIdentifiers, ReferencePortgroup, RunAsync, Server`

#### `New-VDSwitch`

This cmdlet creates vSphere distributed switches.

**Parameters**: `ContactDetails, ContactName, LinkDiscoveryProtocol, LinkDiscoveryProtocolOperation, MaxPorts, Mtu, Notes, NumUplinkPorts, Version, ReferenceVDSwitch, BackupPath, KeepIdentifiers` (+5 more)

#### `New-VDSwitchPrivateVlan`

This cmdlet creates private VLAN configuration entries on a vSphere distributed switch.

**Parameters**: `VDSwitch, PrimaryVlanId, SecondaryVlanId, PrivateVlanType, Server`

#### `New-VirtualPortGroup`

This cmdlet creates a new port group on the specified host.

**Parameters**: `Name, VirtualSwitch, VLanId, Server`

#### `New-VirtualSwitch`

This cmdlet creates a new virtual switch.

**Parameters**: `VMHost, Name, NumPorts, Nic, Mtu, Server`

### Remove

#### `Remove-VDPortGroup`

This cmdlet removes distributed port groups.

**Parameters**: `VDPortGroup, RunAsync, Server`

#### `Remove-VDSwitch`

This cmdlet removes vSphere distributed switches.

**Parameters**: `VDSwitch, RunAsync, Server`

#### `Remove-VDSwitchPhysicalNetworkAdapter`

This cmdlet removes host physical network adapters from the vSphere distributed switches they are connected to.

**Parameters**: `VMHostNetworkAdapter`

#### `Remove-VDSwitchPrivateVlan`

This cmdlet removes private VLAN configuration entries from vSphere distributed switches.

**Parameters**: `VDSwitchPrivateVlan`

#### `Remove-VirtualPortGroup`

This cmdlet removes the specified virtual port groups.

**Parameters**: `VirtualPortGroup`

#### `Remove-VirtualSwitch`

This cmdlet removes the specified virtual switches from their locations.

**Parameters**: `VirtualSwitch, Server`

#### `Remove-VirtualSwitchPhysicalNetworkAdapter`

This cmdlet removes the specified host physical NICs from the standard virtual switch.

**Parameters**: `VMHostNetworkAdapter`

### Set

#### `Set-NicTeamingPolicy`

This cmdlet modifies the specified NIC teaming policy.

**Parameters**: `VirtualSwitchPolicy, BeaconInterval, VirtualPortGroupPolicy, InheritLoadBalancingPolicy, InheritNetworkFailoverDetectionPolicy, InheritNotifySwitches, InheritFailback, InheritFailoverOrder, LoadBalancingPolicy, NetworkFailoverDetectionPolicy, NotifySwitches, FailbackEnabled` (+3 more)

#### `Set-VDPort`

This cmdlet modifies the configuration of virtual distributed ports.

**Parameters**: `VDPort, Name, Description`

#### `Set-VDPortgroup`

This cmdlet modifies the configuration of distributed port groups.

**Parameters**: `Name, Notes, NumPorts, VlanId, VlanTrunkRange, PrivateVlanId, PortBinding, DisableVlan, RollbackConfiguration, BackupPath, VDPortgroup, RunAsync` (+1 more)

#### `Set-VDPortgroupOverridePolicy`

This cmdlet modifies the policy for overriding port group settings at port level.

**Parameters**: `Policy, BlockOverrideAllowed, ResetPortConfigAtDisconnect, SecurityOverrideAllowed, TrafficShapingOverrideAllowed, UplinkTeamingOverrideAllowed, VlanOverrideAllowed`

#### `Set-VDSwitch`

This cmdlet modifies the configuration of vSphere distributed switches.

**Parameters**: `Name, ContactDetails, ContactName, LinkDiscoveryProtocol, LinkDiscoveryProtocolOperation, MaxPorts, Mtu, Notes, NumUplinkPorts, Version, BackupPath, WithoutPortGroups` (+4 more)

#### `Set-VirtualPortGroup`

This cmdlet modifies the properties of the specified virtual port group.

**Parameters**: `Name, VLanId, VirtualPortGroup`

#### `Set-VirtualSwitch`

This cmdlet modifies the properties of the specified virtual switch.

**Parameters**: `VirtualSwitch, NumPorts, Nic, Mtu, Server`

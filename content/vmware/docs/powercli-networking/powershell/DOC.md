---
name: powercli-networking
description: "VMware PowerCLI 13.3 — virtual networking: switches, port groups, adapters, VDS"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Add-VirtualSwitchPhysicalNetworkAdapter,Get-NetworkAdapter,Get-VirtualPortGroup,Get-VirtualSwitch,New-NetworkAdapter,New-VirtualPortGroup,New-VirtualSwitch,Remove-NetworkAdapter,Remove-VirtualPortGroup,Remove-VirtualSwitch,Remove-VirtualSwitchPhysicalNetworkAdapter,Set-NetworkAdapter,Set-VirtualPortGroup,Set-VirtualSwitch"
---

# VMware PowerCLI — virtual networking

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-VirtualSwitchPhysicalNetworkAdapter` | This cmdlet adds a host physical NIC to a standard virtual switch. |
| `Get-NetworkAdapter` | This cmdlet retrieves the virtual network adapters  available on a vCenter Server system. |
| `Get-VirtualPortGroup` | This cmdlet retrieves the available port groups of hosts, virtual machines, and virtual switches. |
| `Get-VirtualSwitch` | This cmdlet retrieves the virtual switches associated with a virtual machine host or used by a vi... |
| `New-NetworkAdapter` | This cmdlet creates a new virtual network adapter. |
| `New-VirtualPortGroup` | This cmdlet creates a new port group on the specified host. |
| `New-VirtualSwitch` | This cmdlet creates a new virtual switch. |
| `Remove-NetworkAdapter` | This cmdlet removes the virtual network adapters from their locations. |
| `Remove-VirtualPortGroup` | This cmdlet removes the specified virtual port groups. |
| `Remove-VirtualSwitch` | This cmdlet removes the specified virtual switches from their locations. |
| `Remove-VirtualSwitchPhysicalNetworkAdapter` | This cmdlet removes the specified host physical NICs from the standard virtual switch. |
| `Set-NetworkAdapter` | This cmdlet modifies the configuration of the virtual network adapter. |
| `Set-VirtualPortGroup` | This cmdlet modifies the properties of the specified virtual port group. |
| `Set-VirtualSwitch` | This cmdlet modifies the properties of the specified virtual switch. |

---

### Add-VirtualSwitchPhysicalNetworkAdapter

This cmdlet adds a host physical NIC to a standard virtual switch.

This cmdlet adds a host physical NIC to a standard virtual switch. If VMHost virtual network adapters are specified, the cmdlet migrates them to the virtual switch as well.

**Returns**: `None`

```
Add-VirtualSwitchPhysicalNetworkAdapter
    [-Server <VIServer[]>]
    [-VirtualNicPortgroup <VirtualPortGroup[]>]
    -VirtualSwitch <VirtualSwitch>
    -VMHostPhysicalNic <PhysicalNic[]>
    [-VMHostVirtualNic <HostVirtualNic[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualNicPortgroup` | `VirtualPortGroup[]` | No | Specifies the port groups to which to attach the host virtual network adapters. Accepts the same number of port groups as the number of virtual network adapters specified. The first adapter is atta... |
| `-VirtualSwitch` | `VirtualSwitch` | Yes | Specifies the standard virtual switch to which you want to migrate physical or virtual network adapters. |
| `-VMHostPhysicalNic` | `PhysicalNic[]` | Yes | Specifies the host physical network adapters that you want to add or migrate to the standard virtual switch. |
| `-VMHostVirtualNic` | `HostVirtualNic[]` | No | Specifies the host virtual network adapters to be migrated along with the physical adapter, so that their connectivity is preserved. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-NetworkAdapter

This cmdlet retrieves the virtual network adapters  available on a vCenter Server system.

This cmdlet retrieves the virtual network adapters  available on a vCenter Server system. The cmdlet returns a set of virtual network adapters assigned to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Returns**: `NetworkAdapter`

```
Get-NetworkAdapter
    [-Id <String[]>]
    [-Name <String[]>]
    -RelatedObject <NetworkAdapterRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Snapshot <Snapshot[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the network adapters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of th... |
| `-Name` | `String[]` | No | Specifies the names of the network adapters you want to retrieve. |
| `-RelatedObject` | `NetworkAdapterRelatedObjectBase[]` | Yes | Specify an object to retrieve one or more network adapters that are related to the object. This parameter accepts standard and distributed port groups. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snapshot` | `Snapshot[]` | No | Specifies the snapshots from which you want to retrieve virtual network adapters. |
| `-Template` | `Template[]` | No | Specifies the templates from which you want to retrieve virtual network adapters. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines from which you want to retrieve virtual network adapters. |

---

### Get-VirtualPortGroup

This cmdlet retrieves the available port groups of hosts, virtual machines, and virtual switches.

This cmdlet retrieves the available port groups of hosts, virtual machines, and virtual switches. To specify a server different from the default one, use the Server parameter.

**Returns**: `VirtualPortGroup`

```
Get-VirtualPortGroup
    [-Datacenter <Datacenter[]>]
    [-Distributed]
    -Id <String[]>
    [-Name <String[]>]
    -RelatedObject <VirtualPortGroupRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Standard]
    [-Tag <Tag[]>]
    [-VirtualSwitch <VirtualSwitchBase[]>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datacenter` | `Datacenter[]` | No | Filters the port groups of the virtual switches connected to hosts in the specified datacenters. |
| `-Distributed` | `SwitchParameter` | No | Indicates that you want to retrieve the port groups for DistributedSwitch objects. This parameter is obsolete. To retrieve distributed port groups, use the Get-VDPortgroup cmdlet instead. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the port groups you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the str... |
| `-Name` | `String[]` | No | Specifies the names of the port groups you want to retrieve. |
| `-RelatedObject` | `VirtualPortGroupRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more VirtualPortGroup objects that are related to them. This parameter accepts vCloud NetworkPool, vCloud ExternalNetwork, and vCloud OrgNetwork objects.   Note... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Standard` | `SwitchParameter` | No | Indicates that you want to retrieve the port groups for VirtualSwitch objects. |
| `-Tag` | `Tag[]` | No | Returns only the virtual port groups that are associated with any of the specified tags.   Note: This parameter is compatible only with standard virtual port groups. For distributed port groups, yo... |
| `-VirtualSwitch` | `VirtualSwitchBase[]` | No | Specifies the virtual switches for which you want to retrieve their port groups. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose port groups you want to retrieve. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts whose port groups you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on fu... |

---

### Get-VirtualSwitch

This cmdlet retrieves the virtual switches associated with a virtual machine host or used by a virtual machine.

This cmdlet retrieves the virtual switches associated with a virtual machine host or used by a virtual machine. At least one of the VMHost and VM parameters must be provided. The VM, VMHost, Name parameters do not accept string values through a pipeline because of collision. To specify a server different from the default one, use the Server parameter.

**Returns**: `VirtualSwitchBase`

```
Get-VirtualSwitch
    [-Datacenter <Datacenter[]>]
    [-Distributed]
    -Id <String[]>
    [-Name <String[]>]
    -RelatedObject <VirtualSwitchRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Standard]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datacenter` | `Datacenter[]` | No | Filters the virtual switches connected to hosts in the specified datacenters. |
| `-Distributed` | `SwitchParameter` | No | Indicates that you want to retrieve only DistributedSwitch objects. This parameter is obsolete. To retrieve distributed switches, use the Get-VDSwitch cmdlet instead. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the virtual switches you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of th... |
| `-Name` | `String[]` | No | Specifies the names of the virtual switches you want to retrieve. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. The position of this... |
| `-RelatedObject` | `VirtualSwitchRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more VirtualSwitch objects that are related to them. This parameter accepts vCloud NetworkPool objects.   Note: In vCloud Director 5.1 environments, you cannot ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Standard` | `SwitchParameter` | No | Indicates that you want to retrieve only VirtualSwitch objects. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose virtual switches you want to retrieve. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts whose virtual switches you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts ... |

---

### New-NetworkAdapter

This cmdlet creates a new virtual network adapter.

This cmdlet creates a new virtual network adapter for each of the provided virtual machines and sets the optional properties if provided.

**Returns**: `NetworkAdapter`

```
New-NetworkAdapter
    [-DeviceProtocol <VrdmaDeviceProtocol>]
    -DistributedSwitch <DistributedSwitch>
    [-MacAddress <String>]
    -NetworkName <String>
    [-PhysicalFunction <String>]
    -Portgroup <VirtualPortGroupBase>
    -PortId <String>
    [-Server <VIServer[]>]
    [-StartConnected]
    [-Type <VirtualNetworkAdapterType>]
    -VM <VirtualMachine>
    [-WakeOnLan]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeviceProtocol` | `VrdmaDeviceProtocol` | No | Specifies the device protocol for a Vmxnet3Vrdma adapter. If omitted, the server applies a default value. |
| `-DistributedSwitch` | `DistributedSwitch` | Yes | Specifies a virtual switch to which you want to connect the network adapter. |
| `-MacAddress` | `String` | No | Specifies an optional MAC address for the new virtual network adapter. |
| `-NetworkName` | `String` | Yes | Specifies the name of the network to which you want to add the new virtual network adapter. Specifying a distributed port group name is obsolete. Use the Portgroup parameter instead. |
| `-PhysicalFunction` | `String` | No | Specifies the PCI ID of the physical device, backing a SriovEthernetCard adapter. If omitted, automatic mode is used for the physical function. |
| `-Portgroup` | `VirtualPortGroupBase` | Yes | Specifies a standard or a distributed port group to which you want to connect the new network adapter. |
| `-PortId` | `String` | Yes | Specifies the port of the specified distributed switch to which you want to connect the network adapter. Use this parameter only if the DistributedSwitch parameter is specified. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StartConnected` | `SwitchParameter` | No | Indicates that the virtual network adapter starts connected when the virtual machine associated with it powers on. |
| `-Type` | `VirtualNetworkAdapterType` | No | Specifies the type of the new network adapter. The valid types are e1000, Flexible, Vmxnet, EnhancedVmxnet, Vmxnet3, SriovEthernetCard, Vmxnet3Vrdma, and Unknown. If no value is given to the parame... |
| `-VM` | `VirtualMachine` | Yes | Specifies the virtual machine to which you want to attach the new virtual network adapter. Passing multiple values to this parameter is obsolete. |
| `-WakeOnLan` | `SwitchParameter` | No | Indicates that wake-on-LAN is enabled on the newly created virtual network adapter. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VirtualPortGroup

This cmdlet creates a new port group on the specified host.

This cmdlet creates a new port group on the  host using the provided parameters.

**Returns**: `VirtualPortGroup`

```
New-VirtualPortGroup
    -Name <String>
    [-Server <VIServer[]>]
    -VirtualSwitch <VirtualSwitch>
    [-VLanId <Int32>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | Specifies a name for the new port group. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualSwitch` | `VirtualSwitch` | Yes | Specifies the virtual switch for which you want to create a new port group. |
| `-VLanId` | `Int32` | No | Specifies the VLAN ID for ports using this port group. The following values are valid:   0 - specifies that you do not want to associate the port group with a VLAN. 1 to 4094 - specifies a VLAN ID ... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VirtualSwitch

This cmdlet creates a new virtual switch.

This cmdlet creates a new virtual switch on the host that is specified by the VMHost parameter.

**Returns**: `VirtualSwitch`

```
New-VirtualSwitch
    [-Mtu <Int32>]
    -Name <String>
    [-Nic <PhysicalNic[]>]
    [-NumPorts <Int32>]
    [-Server <VIServer[]>]
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Mtu` | `Int32` | No | Specifies the maximum transmission unit (MTU) associated with the specified virtual switch (in bytes). The MTU value is always greater than 0. |
| `-Name` | `String` | Yes | Specifies a name for the new virtual switch. |
| `-Nic` | `PhysicalNic[]` | No | Specifies the physical network interface cards you want to add to the Active NICs of the new virtual switch. This parameter accepts both objects and strings. |
| `-NumPorts` | `Int32` | No | Specifies the virtual switch port number. The value is rounded to the closest exact power of two that is greater than the given number (for example, if the user specifies 67, this number is rounded... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost` | Yes | Specifies the host on which you want to create the new virtual switch. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-NetworkAdapter

This cmdlet removes the virtual network adapters from their locations.

**Returns**: `None`

```
Remove-NetworkAdapter
    -NetworkAdapter <NetworkAdapter[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-NetworkAdapter` | `NetworkAdapter[]` | Yes | Specifies the virtual network adapters you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VirtualPortGroup

This cmdlet removes the specified virtual port groups.

**Returns**: `None`

```
Remove-VirtualPortGroup
    -VirtualPortGroup <VirtualPortGroup[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VirtualPortGroup` | `VirtualPortGroup[]` | Yes | Specifies the virtual port groups you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation.. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VirtualSwitch

This cmdlet removes the specified virtual switches from their locations.

**Returns**: `None`

```
Remove-VirtualSwitch
    [-Server <VIServer[]>]
    -VirtualSwitch <VirtualSwitch[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualSwitch` | `VirtualSwitch[]` | Yes | Specifies the virtual switches you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VirtualSwitchPhysicalNetworkAdapter

This cmdlet removes the specified host physical NICs from the standard virtual switch.

**Returns**: `None`

```
Remove-VirtualSwitchPhysicalNetworkAdapter
    -VMHostNetworkAdapter <PhysicalNic[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VMHostNetworkAdapter` | `PhysicalNic[]` | Yes | Specifies the network adapters you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-NetworkAdapter

This cmdlet modifies the configuration of the virtual network adapter.

This cmdlet modifies the configuration of the virtual network adapter. You can change the MAC address and the network name, and to configure the Connected, StartConnected, and WakeOnLan properties of the adapter.

**Returns**: `NetworkAdapter`

```
Set-NetworkAdapter
    [-Connected <Boolean>]
    -DistributedSwitch <DistributedSwitch>
    [-MacAddress <String>]
    -NetworkAdapter <NetworkAdapter[]>
    [-NetworkName <String>]
    -Portgroup <VirtualPortGroupBase>
    -PortId <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-StartConnected <Boolean>]
    [-Type <VirtualNetworkAdapterType>]
    [-WakeOnLan <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Connected` | `Boolean` | No | If the value is $true, the virtual network adapter is connected after its creation. If the value is $false, it is disconnected. |
| `-DistributedSwitch` | `DistributedSwitch` | Yes | Specifies a virtual switch to which you want to connect the network adapter. |
| `-MacAddress` | `String` | No | Specifies an optional MAC address for the virtual network adapter. |
| `-NetworkAdapter` | `NetworkAdapter[]` | Yes | Specifies the virtual network adapter you want to configure. |
| `-NetworkName` | `String` | No | Specifies the name of the network to which you want to connect the virtual network adapter. Specifying a distributed port group name is obsolete. Use the Portgroup parameter instead. |
| `-Portgroup` | `VirtualPortGroupBase` | Yes | Specifies a standard or a distributed port group to which you want to connect the network adapter. |
| `-PortId` | `String` | Yes | Specifies the port of the virtual switch to which you want to connect the network adapter. Use this parameter only if the DistributedSwitch parameter is specified. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StartConnected` | `Boolean` | No | If the value is $true, the virtual network adapter starts connected when its associated virtual machine powers on. If the value is $false, it starts disconnected. |
| `-Type` | `VirtualNetworkAdapterType` | No | Specifies the type of the network adapter. The valid types are e1000, Flexible, Vmxnet, EnhancedVmxnet, and Vmxnet3, and Unknown. |
| `-WakeOnLan` | `Boolean` | No | Indicates that wake-on-LAN is enabled on the virtual network adapter. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VirtualPortGroup

This cmdlet modifies the properties of the specified virtual port group.

**Returns**: `VirtualPortGroup`

```
Set-VirtualPortGroup
    [-Name <String>]
    -VirtualPortGroup <VirtualPortGroup[]>
    [-VLanId <Int32>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | No | Specifies a new name for the virtual port group. |
| `-VirtualPortGroup` | `VirtualPortGroup[]` | Yes | Specifies the virtual port group whose properties you want to change. |
| `-VLanId` | `Int32` | No | Specifies the VLAN ID for ports using this port group. The following values are valid:   0 - specifies that you do not want to associate the port group with a VLAN.   1 to 4094 - specifies a VLAN I... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VirtualSwitch

This cmdlet modifies the properties of the specified virtual switch.

This cmdlet modifies the properties of the specified virtual switch. The server rounds the value of the NumPorts parameter up to the closest exact power of two, greater than the provided number. When updating NumPorts, the user needs to restart the ESX/ESXi host for the change to take effect.

**Returns**: `VirtualSwitch`

```
Set-VirtualSwitch
    [-Mtu <Int32>]
    [-Nic <String[]>]
    [-NumPorts <Int32>]
    [-Server <VIServer[]>]
    -VirtualSwitch <VirtualSwitch[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Mtu` | `Int32` | No | Specifies the maximum transmission unit (MTU) associated with the specified virtual switch (in bytes). The MTU value must be greater than 0. |
| `-Nic` | `String[]` | No | Specifies new network interface cards for the virtual switch. The old NICs are replaced by the specified ones. |
| `-NumPorts` | `Int32` | No | Specifies the VirtualSwitch port number. The value is rounded to the closest exact power of two, greater than the provided number (for example, if the user specifies 67, this number is rounded to 1... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualSwitch` | `VirtualSwitch[]` | Yes | Specifies the virtual switch you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

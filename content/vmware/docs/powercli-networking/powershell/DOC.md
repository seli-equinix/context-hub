---
name: powercli-networking
description: "VMware PowerCLI 13.3 — Virtual switches, distributed switches, port groups, VLAN, traffic shaping"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 2
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,networking,Add-VDSwitchPhysicalNetworkAdapter, Add-VirtualSwitchPhysicalNetworkAdapter, Export-VDPortGroup, Export-VDSwitch, Get-NicTeamingPolicy, Get-VDPort, Get-VDPortgroup, Get-VDPortgroupOverridePolicy, Get-VDSwitch, Get-VDSwitchPrivateVlan, Get-VirtualNetwork, Get-VirtualPortGroup, Get-VirtualSwitch, New-VDPortgroup, New-VDSwitch, New-VDSwitchPrivateVlan, New-VirtualPortGroup, New-VirtualSwitch, Remove-VDPortGroup, Remove-VDSwitch, Remove-VDSwitchPhysicalNetworkAdapter, Remove-VDSwitchPrivateVlan, Remove-VirtualPortGroup, Remove-VirtualSwitch, Remove-VirtualSwitchPhysicalNetworkAdapter, Set-NicTeamingPolicy, Set-VDPort, Set-VDPortgroup, Set-VDPortgroupOverridePolicy, Set-VDSwitch, Set-VirtualPortGroup, Set-VirtualSwitch"
---

# VMware PowerCLI — Networking

Virtual switches, distributed switches, port groups, VLAN, traffic shaping. Module: VMware.VimAutomation (32 cmdlets).

## Add

### `Add-VDSwitchPhysicalNetworkAdapter`

**This cmdlet adds host physical network adapters to a vSphere distributed switch.**

**Parameters:**

- -DistributedSwitch [DistributedSwitch] (Required) Specifies the vSphere distributed switch to which you want to add the host physical network adapter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualNicPortgroup [VDPortgroup[]] (Optional) Specifies the port groups to which to attach the host virtual network adapters. Accepts either one port group, or the same number of port groups as the number of virtual network adapters specified. If one port group is specified, all adapters are attached to that port group. If the same number of port groups as the number of virtual network adapters are specified, the first adapter is attached to the first port group, the second adapter - to the second port group, and so on.
- -VMHostPhysicalNic [PhysicalNic[]] (Required) Specifies the host physical network adapters that you want to add or migrate to the vSphere distributed switch.
- -VMHostVirtualNic [HostVirtualNic[]] (Optional) Specifies the host virtual network adapters to be migrated along with the physical adapter, so that their connectivity is preserved.

**Examples:**

```powershell
$vmhostNetworkAdapter = Get-VMHost "MyVMHost" | Get-VMHostNetworkAdapter -Physical -Name vmnic2
```
_Retrieves the specified physical network adapter from the specified host and adds it to the specified vSphere distributed switch._

```powershell
$myVMHost = Get-VMHost "MyVMHost"
```
_Migrates a host physical network adapter and a virtual network adapter to a vSphere distributed switch._

### `Add-VirtualSwitchPhysicalNetworkAdapter`

**This cmdlet adds a host physical NIC to a standard virtual switch.**

This cmdlet adds a host physical NIC to a standard virtual switch. If VMHost virtual network adapters are specified, the cmdlet migrates them to the virtual switch as well.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualNicPortgroup [VirtualPortGroup[]] (Optional) Specifies the port groups to which to attach the host virtual network adapters. Accepts the same number of port groups as the number of virtual network adapters specified. The first adapter is attached to the first port group, the second adapter - to the second port group, and so on.
- -VirtualSwitch [VirtualSwitch] (Required) Specifies the standard virtual switch to which you want to migrate physical or virtual network adapters.
- -VMHostPhysicalNic [PhysicalNic[]] (Required) Specifies the host physical network adapters that you want to add or migrate to the standard virtual switch.
- -VMHostVirtualNic [HostVirtualNic[]] (Optional) Specifies the host virtual network adapters to be migrated along with the physical adapter, so that their connectivity is preserved.

**Examples:**

```powershell
$myVMHostNetworkAdapter = Get-VMhost "MyVMHost" | Get-VMHostNetworkAdapter -Physical -Name vmnic2
```
_Adds a VMHost physical network adapter to the specified distributed switch._

```powershell
$myVMHost = Get-VMHost 'MyVMHost'
```
_Migrates VMHost physical and virtual network adapters from a distributed virtual switch to a standard virtual switch._

## Export

### `Export-VDPortGroup`

**This cmdlet exports the configuration of a specified distributed port group to a specified .zip file.**

This cmdlet exports the configuration of a specified distributed port group to a specified .zip file. You can export only vSphere distributed port groups.

**Parameters:**

- -Description [String] (Optional) Specifies a description for the exported distributed port group configuration.
- -Destination [String] (Optional) Specifies an absolute or a relative file path to the location where you want to export the configuration of the distributed port group.
- -Force [SwitchParameter] (Optional) Indicates that if the specified destination file already exists, the existing file will be overwritten. Any directories required to complete the specified file path will also be created.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPortGroup [VDPortgroup[]] (Required) Specifies the distributed port group whose configuration you want to export.

**Examples:**

```powershell
Get-VDPortGroup -Name 'MyVDPortGroup' | Export-VDPortGroup -Destination 'C:\MyVDSwitchesBackup\MyVDPortGroup_21122012.zip'
```
_Exports the configuration of the specified port group to the specified file._

```powershell
$myPortGroup = Get-VDPortGroup -Name 'MyVDPortGroup'
```
_Exports the configuration of the specified port group to the specified file. If the MyVDSwitchesBackup directory does not exist, it is created. If the MyVDPortGroupBackup.zip file already exists in the specified location, it is overwritten._

### `Export-VDSwitch`

**This cmdlet exports the configuration of a specified vSphere distributed switch to a .zip file.**

**Parameters:**

- -Description [String] (Optional) Specifies a description for the exported vSphere distributed switch configuration.
- -Destination [String] (Optional) Specifies an absolute or a relative file path to the location where you want to export the vSphere distributed switch configuration.
- -Force [SwitchParameter] (Optional) Indicates that if the specified destination file already exists, the existing file is overwritten. Any directories required to complete the specified file path are also created.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch[]] (Required) Specifies the vSphere distributed switch whose configuration you want to export.
- -WithoutPortGroups [SwitchParameter] (Optional) Indicates that the configuration of the vSphere distributed switch is exported without its port group configuration.

**Examples:**

```powershell
Get-VDSwitch -Name 'MyVDSwitch' | Export-VDSwitch -Description "My VDSwitch configuration" -Destination "c:\myVDSwitchConfig.zip"
```
_Exports the configuration of the specified vSphere distributed switch and its port groups to the specified file._

```powershell
Get-VDSwitch -Name 'MyVDSwitch' | Export-VDSwitch -Description "My VDSwitch configuration" -Destination "c:\myVDSwitchConfig.zip" -WithoutPortGroups -Force
```
_Exports the configuration of the specified vSphere distributed switch and its port groups to the specified file. If the myVDSwitchConfig.zip file already exists, it is overwritten._

## Get

### `Get-NicTeamingPolicy`

**This cmdlet retrieves the NIC teaming policies of the specified virtual switches and virtual port groups.**

This cmdlet retrieves the NIC teaming policies of the specified virtual switches and virtual port groups. The NIC teaming policy determines how network traffic is distributed between adapters and how traffic is reorganized in case of adapter failure.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualPortGroup [VirtualPortGroup[]] (Required) Specifies the port groups whose NIC teaming policy you want to retrieve.
- -VirtualSwitch [VirtualSwitch[]] (Required) Specifies the virtual switches whose NIC teaming policy you want to retrieve.

**Examples:**

```powershell
Get-VirtualPortGroup -VMHost (Get-VMHost *.128) -Name Virtual* | Get-NicTeamingPolicy | fl is*
```
_For the specified virtual port groups, retrieves the Nic teaming policy settings whose names start with "is"._

```powershell
Get-VirtualSwitch -VMHost (Get-VMHost *.128) -Name vswitch | Get-NicTeamingPolicy
```
_Retrieves the Nic teaming policy of the specified virtual switch._

### `Get-VDPort`

**This cmdlet retrieves virtual distributed ports.**

This cmdlet retrieves virtual distributed ports. At least one of the VDSwitch or VDPortgroup parameters must be specified.

**Parameters:**

- -ActiveOnly [SwitchParameter] (Optional) If set, only the active ports are returned.
- -ConnectedOnly [SwitchParameter] (Optional) If set, only the connected ports are returned.
- -Key [String[]] (Optional) Specifies the key of the port which you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Uplink [SwitchParameter] (Optional) If set, only uplink ports are returned. If not set, both uplink and non-uplink ports are returned. This parameter, like every SwitchParameter, can also be set to false (-Uplink:$false), in which case only non-uplink ports are returned.
- -VDPortgroup [VDPortgroup[]] (Optional) Specifies the distributed virtual port group whose ports you want to retrieve.
- -VDSwitch [VDSwitch[]] (Optional) Specifies the vSphere distributed switch whose ports you want to retrieve.

**Examples:**

```powershell
Get-VDPortGroup "MyVDPortgroup" | Get-VDPort -Key "MyPortgroupKey"
```
_Retrieves a virtual distributed port assigned with a key named "MyPortgroupKey" from a virtual distributed port group named "MyVDPortgroup"._

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDPort -Uplink
```
_Retrieves all uplink virtual distributed ports of a vSphere distributed switch named "MyVDSwitch"._

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDPort -ConnectedOnly
```
_Retrieves all connected virtual distributed ports of a vSphere distributed switch named "MyVDSwitch"._

### `Get-VDPortgroup`

**This cmdlet retrieves distributed port groups.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the distributed port groups that you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the distributed port groups that you want to retrieve.
- -NetworkAdapter [NetworkAdapter[]] (Optional) Specifies a virtual machine network adapter to retrieve the distributed port group to which the network adapter is connected.
- -RelatedObject [VDPortgroupRelatedObjectBase[]] (Required) Specifies an object to retrieve one or more distributed port groups that are related to the object. This parameter accepts ExternalNetwork, OrgNetwork, NetworkPool, and OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the distributed port groups that are associated with any of the specified tags.
- -VDSwitch [VDSwitch[]] (Optional) Specifies a vSphere distributed switch to retrieve the distributed port groups that belong to the switch.
- -VMHostNetworkAdapter [HostVirtualNic[]] (Optional) Specifies a host virtual network adapter to retrieve the distributed port groups to which the network adapter is connected.

**Examples:**

```powershell
Get-VDPortGroup -Name "MyVDPortGroup" -VDSwitch "MyVDSwitch"
```
_Retrieves the distributed port group named "MyVDPortGroup" on the specified vSphere distributed switch._

```powershell
Get-OrgNetwork -Name "MyOrgNetwork" | Get-VDPortGroup
```
_Retrieves the distributed port groups that are related to the specified organization network in the cloud._

```powershell
Get-NetworkAdapter -Name "MyVMNetworkAdapter" | Get-VDPortGroup
```
_Retrieves the distributed port group to which the specified virtual machine network adapter is connected._

### `Get-VDPortgroupOverridePolicy`

**This cmdlet retrieves the policy for overriding port group settings at port level.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies a distributed port group for which you want to retrieve the default port group overriding policy.

**Examples:**

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDPortgroupOverridePolicy
```
_Retrieves the overriding policy settings of a distributed port group named "MyVDPortgroup"._

### `Get-VDSwitch`

**This cmdlet retrieves vSphere distributed switches.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the vSphere distributed switches that you want to retrieve.
- -Location [FolderContainer[]] (Optional) Specifies vCenter Server container objects that you want to search for vSphere distributed switches. This parameter accepts Datacenter and Folder objects.
- -Name [String[]] (Optional) Specifies the names of the vSphere distributed switches that you want to retrieve.
- -RelatedObject [VDSwitchRelatedObjectBase[]] (Required) Specifies an object to retrieve one or more vSphere distributed switches that are related to the object. This parameter accepts NetworkPool and OMResource objects.
- -Server [VIServer[]] (Optional) Specify the cloud servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-CIServer.
- -Tag [Tag[]] (Optional) Returns only the vSphere distributed switches that are associated with any of the specified tags.
- -VM [VirtualMachine[]] (Optional) Specifies virtual machines to retrieve vSphere distributed switches they are connected to.
- -VMHost [VMHost[]] (Optional) Specifies hosts to retrieve vSphere distributed switches to which the hosts are added.

**Examples:**

```powershell
Get-Datacenter -Name MyDatacenter | Get-VDSwitch
```
_Retrieves all vSphere distributed switches in the specified datacenter._

```powershell
Get-VMHost -Name MyVMHost | Get-VDSwitch
```
_Retrieves all vSphere distributed switches to which the specified host is added._

```powershell
Get-VM -Name MyVM | Get-VDSwitch
```
_Retrieves all vSphere distributed switches to which the specified virtual machine is connected._

### `Get-VDSwitchPrivateVlan`

**This cmdlet retrieves the private VLAN configuration entries of a vSphere distributed switch.**

**Parameters:**

- -PrimaryVlanId [Int32[]] (Optional) Specifies the primary VLAN ID of the private VLAN configuration entries that you want to retrieve.
- -PrivateVlanType [PrivateVlanType[]] (Optional) Specifies the private VLAN type of the VLAN configuration entries that you want to retrieve.
- -SecondaryVlanId [Int32[]] (Optional) Specifies the secondary VLAN ID of the private VLAN configuration entries that you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch[]] (Required) Specifies the vSphere distributed switch whose private VLAN configuration entries to retrieve.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDSwitchPrivateVlan -PrivateVlanType Isolated
```
_Retrieves all private VLAN entries of a vSphere distributed switch named "MyVDSwitch" with specified 'isolated' VLAN port type._

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDSwitchPrivateVlan -PrimaryVlanId 1,3
```
_Retrieves the private VLAN entries of a vSphere distributed switch named "MyVDSwitch" with primary VLAN identifiers 1 and 3._

### `Get-VirtualNetwork`

**The cmdlet retrieves all virtual networks on a vCenter server system.**

This cmdlet retrieves all virtual networks that match the specified filters for each default connection to the vCenter server system or all specified connections in the -Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the virtual networks that you want to retrieve.
- -Location [VIContainer[]] (Optional) Specifies vSphere container objects that you want to search for virtual networks. This parameter accepts Folder and Datacenter objects.
- -Name [String[]] (Optional) Specifies the names of the virtual networks that you want to retrieve.
- -NetworkType [NetworkType[]] (Optional) Specifies the network types of the virtual networks that you want to retrieve. The accepted values are Network, Distributed, and Opaque.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$networks = Get-VirtualNetwork
```
_Retrieves all virtual networks on a vCenter server system._

```powershell
$networks = Get-VirtualNetwork -Name 'VM*'
```
_Retrieves all virtual networks whose names begin with 'VM'._

```powershell
$networks = Get-VirtualNetwork -NetworkType Distributed
```
_Retrieves all distributed networks on the vCenter server system._

### `Get-VirtualPortGroup`

**This cmdlet retrieves the available port groups of hosts, virtual machines, and virtual switches.**

This cmdlet retrieves the available port groups of hosts, virtual machines, and virtual switches. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Datacenter [Datacenter[]] (Optional) Filters the port groups of the virtual switches connected to hosts in the specified datacenters.
- -Distributed [SwitchParameter] (Optional) Indicates that you want to retrieve the port groups for DistributedSwitch objects. This parameter is obsolete. To retrieve distributed port groups, use the Get-VDPortgroup cmdlet instead.
- -Id [String[]] (Required) Specifies the IDs of the port groups you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the port groups you want to retrieve.
- -RelatedObject [VirtualPortGroupRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more VirtualPortGroup objects that are related to them. This parameter accepts vCloud NetworkPool, vCloud ExternalNetwork, and vCloud OrgNetwork objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Standard [SwitchParameter] (Optional) Indicates that you want to retrieve the port groups for VirtualSwitch objects.
- -Tag [Tag[]] (Optional) Returns only the virtual port groups that are associated with any of the specified tags.
- -VirtualSwitch [VirtualSwitchBase[]] (Optional) Specifies the virtual switches for which you want to retrieve their port groups.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose port groups you want to retrieve.
- -VMHost [VMHost[]] (Optional) Specifies the hosts whose port groups you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on future PowerCLI versions, specify the parameter by name.

**Examples:**

```powershell
Get-VirtualPortgroup -Name "VM Network"
```
_Retrieves all port groups named "VM Network"._

```powershell
$myVMHost = Get-VMHost -Name "MyVMHost"
```
_Retrieves the port group named "VM Network" on the specified host._

```powershell
$myVM = Get-VM -Name "MyVM"
```
_Retrieves all port groups to which the specified virtual machine is connected._

### `Get-VirtualSwitch`

**This cmdlet retrieves the virtual switches associated with a virtual machine host or used by a virtual machine.**

This cmdlet retrieves the virtual switches associated with a virtual machine host or used by a virtual machine. At least one of the VMHost and VM parameters must be provided. The VM, VMHost, Name parameters do not accept string values through a pipeline because of collision. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Datacenter [Datacenter[]] (Optional) Filters the virtual switches connected to hosts in the specified datacenters.
- -Distributed [SwitchParameter] (Optional) Indicates that you want to retrieve only DistributedSwitch objects. This parameter is obsolete. To retrieve distributed switches, use the Get-VDSwitch cmdlet instead.
- -Id [String[]] (Required) Specifies the IDs of the virtual switches you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the virtual switches you want to retrieve. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on future PowerCLI versions, specify the parameter by name.
- -RelatedObject [VirtualSwitchRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more VirtualSwitch objects that are related to them. This parameter accepts vCloud NetworkPool objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Standard [SwitchParameter] (Optional) Indicates that you want to retrieve only VirtualSwitch objects.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose virtual switches you want to retrieve.
- -VMHost [VMHost[]] (Optional) Specifies the hosts whose virtual switches you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on future PowerCLI versions, specify the parameter by name.

**Examples:**

```powershell
Get-VirtualSwitch -VM VM
```
_Retrieves the virtual switch used by the virtual machine named VM._

```powershell
Get-Datacenter -Name "MyDatacenter" | Get-VirtualSwitch
```
_Retrieves all virtual switches in the specified datacenter._

```powershell
Get-VMHost -Name "MyVMHost" | Get-VirtualSwitch
```
_Retrieves all virtual switches on the specified host._

## New

### `New-VDPortgroup`

**This cmdlet creates distributed port groups.**

This cmdlet creates distributed port groups. You can create a new distributed port group with custom properties, specify a reference port group to clone its properties, or provide a backup profile to import the port group configuration.

**Parameters:**

- -BackupPath [String] (Required) Specifies the full file path to the .zip file containing the backup configuration that you want to import. Only .zip files created with the Export-VDPortgroup cmdlet are supported.
- -KeepIdentifiers [SwitchParameter] (Optional) Indicates that the original vSphere distributed port group identifiers will be preserved.
- -Name [String] (Required) Specifies the name of the new distributed port group that you want to create.
- -Notes [String] (Optional) Specifies a description for the new distributed port group that you want to create.
- -NumPorts [Int32] (Optional) Specifies the number of ports that the distributed port group will have. If you do not set this parameter, the number of ports for the new distributed port group is set to 128 ports.
- -PortBinding [DistributedPortGroupPortBinding] (Optional) Specifies the port binding setting for the distributed port group that you want to create. This parameter accepts Static, Dynamic, and Ephemeral values. Note: Dynamic port binding is deprecated. For better performance, static port binding is recommended.
- -ReferencePortgroup [VDPortgroup] (Required) Specifies a reference distributed port group. The properties of the new distributed port group will be cloned from the reference distributed port group.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch] (Required) Specifies the vSphere distributed switch on which you want to create the new distributed port group.
- -VlanId [Int32] (Optional) Specifies the VLAN ID of the distributed port group that you want to create. Valid values are integers in the range of 1 to 4094.
- -VlanTrunkRange [VlanRangeList] (Optional) Specifies the VLAN trunk range for the distributed port group that you want to create. Valid values are strings representing ranges of IDs. For example, "1-4, 6, 8-9".

**Examples:**

```powershell
Get-VDSwitch -Name "MyVDSwitch" | New-VDPortgroup -Name "MyVDPortGroup" -NumPorts 8 -VLanId 4
```
_Creates a new distributed port group on the specified vSphere distributed switch with the specified number of ports and VLAN ID._

```powershell
$myReferncePortroup = Get-VDPortgroup -Name "MyReferencePortGroup"
```
_Creates a new distributed port group on the specified vSphere distributed switch by cloning the configuration of the distributed port group named "MyReferencePortGroup"._

```powershell
Get-VDSwitch -Name "MyVDSwitch" | New-VDPortgroup -Name "MyVDPortGroup" -RunAsync
```
_Creates asynchronously a new distributed port group on the specified vSphere distributed switch._

### `New-VDSwitch`

**This cmdlet creates vSphere distributed switches.**

This cmdlet creates vSphere distributed switches. You can create a new vSphere distributed switch with custom properties, specify a reference vSphere distributed switch to clone its configuration, or provide a backup profile to import the switch configuration.

**Parameters:**

- -BackupPath [String] (Required) Specifies the full file path to the .zip file containing the backup configuration that you want to import. Only .zip files created with the Export-VDSwitch cmdlet are supported.
- -ContactDetails [String] (Optional) Specifies the contact details of the vSphere distributed switch administrator.
- -ContactName [String] (Optional) Specifies the name of the vSphere distributed switch administrator.
- -KeepIdentifiers [SwitchParameter] (Optional) Indicates that the original vSphere distributed switch and port group identifiers will be preserved. You cannot specify this parameter, when the Name parameter is specified.
- -LinkDiscoveryProtocol [LinkDiscoveryProtocol] (Optional) Specifies the discovery protocol type of the vSphere distributed switch that you want to create. This parameter accepts CDP and LLDP values. If you do not set a value for this parameter, the default server setting is used.
- -LinkDiscoveryProtocolOperation [LinkDiscoveryOperation] (Optional) Specifies the link discovery protocol operation for the vSphere distributed switch that you want to create. This parameter accepts Advertise, Listen, Both, and Disabled values. If you do not set a value for this parameter, the default server setting is used.
- -Location [VIContainer] (Required) Specifies the location where you want to create the vSphere distributed switch. This parameter accepts Datacenter and Folder objects.
- -MaxPorts [Int32] (Optional) Specifies the maximum number of ports allowed on the vSphere distributed switch that you want to create.
- -Mtu [Int32] (Optional) Specifies the maximum MTU size for the vSphere distributed switch that you want to create. Valid values are positive integers only.
- -Name [String] (Required) Specifies a name for the new vSphere distributed switch that you want to create. You cannot specify this parameter, when the KeepIdentifiers parameter is specified.
- -Notes [String] (Optional) Specifies a description for the vSphere distributed switch that you want to create.
- -NumUplinkPorts [Int32] (Optional) Specifies the number of uplink ports on the vSphere distributed switch that you want to create.
- -ReferenceVDSwitch [VDSwitch] (Required) Specifies a reference vSphere distributed switch. The properties of the new vSphere distributed switch will be cloned from the reference vSphere distributed switch.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Version [String] (Optional) Specifies the version of the vSphere distributed switch that you want to create. This parameter accepts 4.0, 4.1.0, 5.0.0, 5.1.0, 5.5.0, 6.0.0, and 6.5.0 values. You cannot specify a version that is incompatible with the version of the vCenter Server system you are connected to.
- -WithoutPortGroups [SwitchParameter] (Optional) Indicates that the new vSphere distributed switch will be created without importing the port groups from the specified backup file or reference vSphere distributed switch.

**Examples:**

```powershell
$myDatacenter = Get-Datacenter -Name "MyDatacenter"
```
_Creates a new vSphere distributed switch with the specified name, version, maximum number of ports, and link discovery protocol settings in the specified datacenter._

```powershell
$myFolder = Get-Folder -Name "MyFolder"
```
_Creates a new vSphere distributed switch by cloning the configuration of the existing vSphere distributed switch named "MyReferenceSwitch". The new vSphere distributed switch is created without cloning the existing port groups and is stored in the specified folder._

```powershell
$myFolder = Get-Folder -Name "MyFolder"
```
_Creates a new vSphere distributed switch by importing the specified backup profile._

### `New-VDSwitchPrivateVlan`

**This cmdlet creates private VLAN configuration entries on a vSphere distributed switch.**

**Parameters:**

- -PrimaryVlanId [Int32] (Required) Specifies the primary VLAN ID. The VLAN IDs of 0 and 4095 are reserved and cannot be used.
- -PrivateVlanType [PrivateVlanType] (Required) Specifies the private VLAN port type: community, isolated, or promiscuous.
- -SecondaryVlanId [Int32] (Required) Specifies the secondary VLAN ID. The VLAN IDs of 0 and 4095 are reserved and cannot be used.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch] (Required) Specifies the vSphere distributed switch on which to create a private VLAN configuration.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | New-VDSwitchPrivateVlan -PrimaryVlanId 1 -SecondaryVlanId 1 -PrivateVlanType Promiscuous
```
_Creates a private VLAN inside a specific vSphere distributed switch with a promiscuous VLAN port type._

### `New-VirtualPortGroup`

**This cmdlet creates a new port group on the specified host.**

This cmdlet creates a new port group on the  host using the provided parameters.

**Parameters:**

- -Name [String] (Required) Specifies a name for the new port group.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualSwitch [VirtualSwitch] (Required) Specifies the virtual switch for which you want to create a new port group.
- -VLanId [Int32] (Optional) Specifies the VLAN ID for ports using this port group. The following values are valid:

**Examples:**

```powershell
$vswitch =  New-VirtualSwitch -VMHost 10.23.114.234 -Name VSwitch
```
_Creates a virtual port group named VPortGroup on the virtual switch VSwitch._

### `New-VirtualSwitch`

**This cmdlet creates a new virtual switch.**

This cmdlet creates a new virtual switch on the host that is specified by the VMHost parameter.

**Parameters:**

- -Mtu [Int32] (Optional) Specifies the maximum transmission unit (MTU) associated with the specified virtual switch (in bytes). The MTU value is always greater than 0.
- -Name [String] (Required) Specifies a name for the new virtual switch.
- -Nic [PhysicalNic[]] (Optional) Specifies the physical network interface cards you want to add to the Active NICs of the new virtual switch. This parameter accepts both objects and strings.
- -NumPorts [Int32] (Optional) Specifies the virtual switch port number. The value is rounded to the closest exact power of two that is greater than the given number (for example, if the user specifies 67, this number is rounded to 128). Note that the port number displayed in the vSphere Client might differ from the value that you specified for the NumPorts parameter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost] (Required) Specifies the host on which you want to create the new virtual switch.

**Examples:**

```powershell
$vswitch =  New-VirtualSwitch -VMHost 10.23.112.234 -Name VSwitch
```
_Creates a new virtual switch named VSwitch on the virtual machine host with IP address 10.23.112.234._

```powershell
$network = Get-VMHostNetwork -VMHost 10.23.112.234
```
_Creates a new virtual switch named VSwitch on the virtual machine host with IP address 10.23.112.234 with a physical network adapter._

```powershell
Get-VMHost *.128 | New-VirtualSwitch -Name VSwitch -Nic vmnic5,vmnic6
```
_Create a virtual switch named VSwitch with two physical network adapters - 'vmnic5' and 'vmnic6'. Note that the 'vmnic5' and 'vmnic6' adapters must not be assigned to other virtual switches._

## Remove

### `Remove-VDPortGroup`

**This cmdlet removes distributed port groups.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPortGroup [VDPortgroup[]] (Required) Specifies the distributed port group that you want to remove.

**Examples:**

```powershell
Get-VDPortGroup -Name "MyVDPortGroup" | Remove-VDPortGroup
```
_Removes the specified distributed port group from the vSphere distributed switch that it belongs to._

### `Remove-VDSwitch`

**This cmdlet removes vSphere distributed switches.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch[]] (Required) Specifies the vSphere distributed switches that you want to remove.

**Examples:**

```powershell
Get-VDSwitch -Name MyVDSwitch | Remove-VDSwitch
```
_Removes the specified vSphere distributed switch._

### `Remove-VDSwitchPhysicalNetworkAdapter`

**This cmdlet removes host physical network adapters from the vSphere distributed switches they are connected to.**

**Parameters:**

- -VMHostNetworkAdapter [PhysicalNic[]] (Required) Specifies the host physical network adapters that you want to remove from the vSphere distributed switch it is connected to.

**Examples:**

```powershell
Get-VMhost -Name "MyVMhost" | Get-VMHostNetworkAdapter -Physical -Name vmnic0 | Remove-VDSwitchPhysicalNetworkAdapter
```
_Removes the specified host physical network adapter from the vSphere distributed switch that it is connected to._

### `Remove-VDSwitchPrivateVlan`

**This cmdlet removes private VLAN configuration entries from vSphere distributed switches.**

**Parameters:**

- -VDSwitchPrivateVlan [VDSwitchPrivateVlan[]] (Required) Specifies the private VLAN configuration entry that you want to remove.

**Examples:**

```powershell
Get-VDSwitchPrivateVlan -VDSwitch "MyVDSwitch" -PrimaryVlanId 1,3,5 | Remove-VDSwitchPrivateVlan
```
_Removes the private VLAN configuration entries with specified primary identities from a vSphere distributed switch named "MyVDSwitch"._

### `Remove-VirtualPortGroup`

**This cmdlet removes the specified virtual port groups.**

**Parameters:**

- -VirtualPortGroup [VirtualPortGroup[]] (Required) Specifies the virtual port groups you want to remove.

**Examples:**

```powershell
$vswitch =  New-VirtualSwitch -VMHost 10.23.112.234 -Name VirtualSwitch
```
_Creates a new virtual switch named VirtualSwitch and a virtual ports group VPortGroup for this switch. Then removes the virtual ports group._

### `Remove-VirtualSwitch`

**This cmdlet removes the specified virtual switches from their locations.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualSwitch [VirtualSwitch[]] (Required) Specifies the virtual switches you want to remove.

**Examples:**

```powershell
$vswitch =  New-VirtualSwitch -VMHost 10.23.122.145 -Name VirtualSwitch
```
_Creates a new virtual switch named VirtualSwitch on the host with an IP address 10.23.122.145. Then removes the virtual switch._

### `Remove-VirtualSwitchPhysicalNetworkAdapter`

**This cmdlet removes the specified host physical NICs from the standard virtual switch.**

**Parameters:**

- -VMHostNetworkAdapter [PhysicalNic[]] (Required) Specifies the network adapters you want to remove.

**Examples:**

```powershell
Get-VMhost "myVMhost" | Get-VMHostNetworkAdapter -Physical -Name "vmnic1" | Remove-VirtualSwitchPhysicalNetworkAdapter
```
_Removes a VMHost NIC from the virtual switch it is attached to._

## Set

### `Set-NicTeamingPolicy`

**This cmdlet modifies the specified NIC teaming policy.**

This cmdlet modifies the specified NIC teaming policy. You can change the load balancing and failover settings. Default NIC teaming policies are set for the entire virtual switch and can be overridden at port group level.

**Parameters:**

- -BeaconInterval [Int32] (Optional) Specifies the interval at which the server sends out beacon probes on all NICs in the team. The value must be a positive integer. This parameter is used when the value of the NetworkFailoverDetectionPolicy parameter is BeaconProbing.
- -FailbackEnabled [Boolean] (Optional) Specifies how a physical adapter is returned to active duty after recovering from a failure. If the value is $true, the adapter is returned to active duty immediately on recovery, displacing the standby adapter that took over its slot, if any. If the value is $false, a failed adapter is left inactive even after recovery until another active adapter fails, requiring its replacement.
- -InheritFailback [Boolean] (Optional) Indicates that the value of the FailbackEnabled parameter is inherited from the virtual switch.
- -InheritFailoverOrder [Boolean] (Optional) Indicates that the value of the MakeNicActive, MakeNicStandBy, and MakeNicUnused parameters are inherited from the virtual switch.
- -InheritLoadBalancingPolicy [Boolean] (Optional) Indicates that the value of the LoadBalancingPolicy parameter is inherited from the virtual switch.
- -InheritNetworkFailoverDetectionPolicy [Boolean] (Optional) Indicates that the value of the NetworkFailoverDetectionPolicy parameter is inherited from the virtual switch.
- -InheritNotifySwitches [Boolean] (Optional) Indicates that the value of the NotifySwitches parameter is inherited from the virtual switch.
- -LoadBalancingPolicy [LoadBalancingPolicy] (Optional) Determines how network traffic is distributed between the network adapters assigned to a switch. The following values are valid:
- -MakeNicActive [PhysicalNic[]] (Optional) Specifies the adapters you want to continue to use when the network adapter connectivity is available and active.
- -MakeNicStandby [PhysicalNic[]] (Optional) Specifies the adapters you want to use if one of the active adapter's connectivity is unavailable.
- -MakeNicUnused [PhysicalNic[]] (Optional) Specifies the adapters you do not want to use.
- -NetworkFailoverDetectionPolicy [NetworkFailoverDetectionPolicy] (Optional) Specifies how to reroute traffic in the event of an adapter failure. The following values are valid:
- -NotifySwitches [Boolean] (Optional) Indicates that whenever a virtual NIC is connected to the virtual switch or whenever that virtual NIC's traffic is routed over a different physical NIC in the team because of a failover event, a notification is sent over the network to update the lookup tables on the physical switches.
- -VirtualPortGroupPolicy [NicTeamingVirtualPortGroupPolicy[]] (Required) Specifies the virtual port group policy to configure.
- -VirtualSwitchPolicy [NicTeamingVirtualSwitchPolicy[]] (Required) Specifies the virtual switch policy to configure.

**Examples:**

```powershell
$policy = Get-VirtualSwitch -VMHost (Get-VMHost *.128) -Name vSwitch1 | Get-NicTeamingPolicy
```
_Configures the NicTeaming policy  of the vSwitch1 virtual switch._

### `Set-VDPort`

**This cmdlet modifies the configuration of virtual distributed ports.**

**Parameters:**

- -Description [String] (Optional) Specifies a description for the virtual distributed port that you want to configure.
- -Name [String] (Optional) Specifies a new name for the virtual distributed port that you want to configure.
- -VDPort [VDPort[]] (Required) Specifies the virtual distributed port that you want to configure.

**Examples:**

```powershell
$myVDPort = Get-VDPort -Key "Port0" -VDSwtich "MyVDSwitch"
```
_Updates the name and the description of a specified virtual distributed port inside a vSphere distributed switch named "MyVDSwitch"._

### `Set-VDPortgroup`

**This cmdlet modifies the configuration of distributed port groups.**

This cmdlet modifies the configuration of distributed port groups. You can set the properties of the distributed port group manually, provide a backup profile to import the port group configuration, or rollback to the last valid configuration.

**Parameters:**

- -BackupPath [String] (Required) Specifies the full file path to the .zip file containing the backup configuration that you want to import. You can import only .zip files created with the Export-VDPortgroup cmdlet.
- -DisableVlan [SwitchParameter] (Optional) Sets the VLAN type of the distributed port group to None. This parameter is obsolete. Use the corresponding parameter from the Set-VDVlanConfiguration cmdlet instead.
- -Name [String] (Optional) Specifies a new name for the distributed port group that you want to configure.
- -Notes [String] (Optional) Specifies a new description for the distributed port group that you want to configure.
- -NumPorts [Int32] (Optional) Specifies a new number of ports on the distributed port group that you want to configure.
- -PortBinding [DistributedPortGroupPortBinding] (Optional) Specifies a new port binding setting for the distributed port group that you want to configure. This parameter accepts Static, Dynamic, and Ephemeral values.
- -PrivateVlanId [Int32] (Optional) Specifies the secondary VLAN ID of a vSphere distributed switch's private VLAN configuration entry. This parameter is obsolete. Use the corresponding parameter from the Set-VDVlanConfiguration cmdlet instead.
- -RollbackConfiguration [SwitchParameter] (Required) Indicates that you want to rollback the distributed port group to its last valid configuration.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies the distributed port group that you want to configure.
- -VlanId [Int32] (Optional) Specifies a new VLAN ID for the distributed port group that you want to configure. The VLAN IDs of 0 and 4095 are reserved and cannot be used. This parameter is obsolete. Use the corresponding parameter from the Set-VDVlanConfiguration cmdlet instead.
- -VlanTrunkRange [VlanRangeList] (Optional) Specifies a new VLAN trunk range for the distributed port group that you want to configure. Valid values are strings representing ranges of IDs. For example, "1-4, 6, 8-9". This parameter is obsolete. Use the corresponding parameter from the Set-VDVlanConfiguration cmdlet instead.

**Examples:**

```powershell
Get-VDPortgroup -Name "MyVDPortGroup" | Set-VDPortgroup -Name "MyNewVDPortGroupName" -NumPorts 5 -VlanId 4
```
_Changes the name, number of ports and the VLAN ID of all distributed port groups named "MyVDPortGroup"._

```powershell
Get-VDPortgroup -Name "MyVDPortGroup" | Set-VDPortgroup -VlanTrunkRange "1-5, 8-10"
```
_Changes the VLAN trunk range of all distributed port groups named "MyVDPortGroup"._

```powershell
$myVDPortgroup = Get-VDPortgroup -Name "MyVDPortGroup" -VDSwitch "MyVDSwitch"
```
_Sets the VLAN type of the specified distributed port group to None._

### `Set-VDPortgroupOverridePolicy`

**This cmdlet modifies the policy for overriding port group settings at port level.**

This cmdlet modifies the policy for overriding port group settings at port level. At least one of the Bool parameters must be specified.

**Parameters:**

- -BlockOverrideAllowed [Boolean] (Optional) Specifies whether overriding port blocking settings is allowed.
- -Policy [VDPortgroupOverridePolicy[]] (Required) Specifies the port group overriding policy that you want to configure.
- -ResetPortConfigAtDisconnect [Boolean] (Optional) Specifies whether the port configuration is reset when the port is disconnected.
- -SecurityOverrideAllowed [Boolean] (Optional) Specifies whether overriding security settings is allowed.
- -TrafficShapingOverrideAllowed [Boolean] (Optional) Specifies whether overriding traffic shaping settings is allowed.
- -UplinkTeamingOverrideAllowed [Boolean] (Optional) Specifies whether overriding uplink teaming settings is allowed.
- -VlanOverrideAllowed [Boolean] (Optional) Specifies whether overriding VLAN settings is allowed.

**Examples:**

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDPortgroupOverridePolicy | Set-VDPortgroupOverridePolicy -BlockOverrideAllowed $true
```
_Retrieves a distributed port group named "MyVDPortgroup" and updates its overriding policy to allow the port blocking settings to override the default settings at port group level._

```powershell
Get-VDSwitch "MyVDSwitch" |
```
_Retrieves all port groups inside a distributed switch named "MyVDSwitch" and updates their overriding policies with the options to override the traffic shaping setting at port level, and to reset the distributed port network settings back to the port group settings._

### `Set-VDSwitch`

**This cmdlet modifies the configuration of vSphere distributed switches.**

This cmdlet modifies the configuration of vSphere distributed switches. You can set the properties of the vSphere distributed switch manually, rollback the configuration to its previous state, or import it from a backup profile.

**Parameters:**

- -BackupPath [String] (Required) Specifies the full file path to the .zip file containing the backup configuration that you want to import. You can import only .zip files created with the Export-VDSwitch cmdlet.
- -ContactDetails [String] (Optional) Specifies new contact details of the vSphere distributed switch administrator.
- -ContactName [String] (Optional) Specifies a new name for the vSphere distributed switch administrator.
- -LinkDiscoveryProtocol [LinkDiscoveryProtocol] (Optional) Specifies the link discovery protocol for the vSphere distributed switch that you want to configure. This parameter accepts CDP and LLDP values.
- -LinkDiscoveryProtocolOperation [LinkDiscoveryOperation] (Optional) Specifies the link discovery protocol operation for the vSphere distributed switch that you want to configure. This parameter accepts Advertise, Listen, Both, and Disabled values.
- -MaxPorts [Int32] (Optional) Specifies the maximum number of ports allowed on the vSphere distributed switch that you want to configure.
- -Mtu [Int32] (Optional) Specifies the maximum MTU size for the vSphere distributed switch that you want to configure. Valid values are positive integers only.
- -Name [String] (Optional) Specifies a new name for the vSphere distributed switch that you want to configure.
- -Notes [String] (Optional) Specifies a new description for the vSphere distributed switch that you want to configure.
- -NumUplinkPorts [Int32] (Optional) Specifies the number of uplink ports on the vSphere distributed switch that you want to configure.
- -RollBackConfiguration [SwitchParameter] (Required) Indicates that you want to rollback the configuration of the vSphere distributed switch to an earlier state.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch[]] (Required) Specifies the vSphere distributed switch that you want to configure.
- -Version [String] (Optional) Specifies a new version for the vSphere distributed switch that you want to configure. This parameter accepts 4.0, 4.1.0, 5.0.0, 5.1.0, 5.5.0, and 6.0.0 values. You cannot specify a version that is incompatible with the version of the vCenter Server system you are connected to.
- -WithoutPortGroups [SwitchParameter] (Optional) Indicates that the specified backup configuration is imported without its port groups.

**Examples:**

```powershell
Get-VDSwitch -Name "MyVDSwitch" | Set-VDSwitch -MaxPorts 1000 -NumUplinkPorts 8 -Mtu 2000
```
_Modifies the maximum number of ports, the number of uplink ports, and the maximum MTU size of the specified vSphere distributed switch._

```powershell
$myVDSwitches = Get-VDSwitch -Name MyVDSwitch*
```
_Changes the version of all vSphere distributed switches whose names start with "MyVDSwitch"._

```powershell
$myVDSwitch = Get-VDSwitch -Name "MyVDSwitch"
```
_Enables link discovery protocol on the specified vSphere distributed switch, sets it to LLDP and changes the link discovery protocol operation to listen._

### `Set-VirtualPortGroup`

**This cmdlet modifies the properties of the specified virtual port group.**

**Parameters:**

- -Name [String] (Optional) Specifies a new name for the virtual port group.
- -VirtualPortGroup [VirtualPortGroup[]] (Required) Specifies the virtual port group whose properties you want to change.
- -VLanId [Int32] (Optional) Specifies the VLAN ID for ports using this port group. The following values are valid:

**Examples:**

```powershell
$vswitch =  New-VirtualSwitch -VMHost 10.23.112.36 -Name VSwitch
```
_Creates a new virtual switch named VSwitch on the virtual machine host with IP address 10.23.112.36. Creates a new virtual port group for the new switch named VPortGroup1. Sets the VLAN ID for the ports using the VPortGroup1 group._

### `Set-VirtualSwitch`

**This cmdlet modifies the properties of the specified virtual switch.**

This cmdlet modifies the properties of the specified virtual switch. The server rounds the value of the NumPorts parameter up to the closest exact power of two, greater than the provided number. When updating NumPorts, the user needs to restart the ESX/ESXi host for the change to take effect.

**Parameters:**

- -Mtu [Int32] (Optional) Specifies the maximum transmission unit (MTU) associated with the specified virtual switch (in bytes). The MTU value must be greater than 0.
- -Nic [String[]] (Optional) Specifies new network interface cards for the virtual switch. The old NICs are replaced by the specified ones.
- -NumPorts [Int32] (Optional) Specifies the VirtualSwitch port number. The value is rounded to the closest exact power of two, greater than the provided number (for example, if the user specifies 67, this number is rounded to 128). The ESX host to which the virtual switch belongs, must be restarted for the change to take effect. Note that the port number displayed in the vSphere Client might differ from the value that you specified for the NumPorts parameter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualSwitch [VirtualSwitch[]] (Required) Specifies the virtual switch you want to configure.

**Examples:**

```powershell
$vswitch = New-VirtualSwitch -Host 10.23.115.67 -Name VSwitch
```
_Creates a new virtual switch named VSwitch on the virtual machine host on IP address 10.23.115.67. Then sets the virtual switch MTU to 500._

```powershell
$vswitch = New-VirtualSwitch -VMHost 10.23.115.67
```
_Creates a new virtual switch named VSwitch on the virtual machine host on IP address 10.23.115.67. Then assigns to it a network adapter._

```powershell
Get-VMHost *.128 | Get-VirtualSwitch | Select-Object -First 1 | Set-VirtualSwitch -Nic vmnic5
```
_Add a physical network adapter named 'vmnic5' to the first switch of the host. Note that the 'vmnic5' adapter must not be assigned to other virtual switches._

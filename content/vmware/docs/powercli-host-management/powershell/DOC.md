---
name: powercli-host-management
description: "VMware PowerCLI 13.3 — ESXi host operations — configure, maintain, monitor hosts"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,host-management,Add-VDSwitchVMHost, Add-VMHost, Add-VMHostNtpServer, Export-LcmVMHostDesiredState, Export-VMHostImageDb, Export-VMHostProfile, Format-VMHostDiskPartition, Get-DrsVMHostRule, Get-EsxCli, Get-EsxTop, Get-HAPrimaryVMHost, Get-TrustAuthorityVMHostBaseImage, Get-VMHost, Get-VMHostAccount, Get-VMHostAdvancedConfiguration, Get-VMHostAuthentication, Get-VMHostAvailableTimeZone, Get-VMHostDiagnosticPartition, Get-VMHostDisk, Get-VMHostDiskPartition, Get-VMHostFirewallDefaultPolicy, Get-VMHostFirewallException, Get-VMHostFirmware, Get-VMHostHardware, Get-VMHostHba, Get-VMHostModule, Get-VMHostNetwork, Get-VMHostNetworkAdapter, Get-VMHostNetworkStack, Get-VMHostNtpServer, Get-VMHostPatch, Get-VMHostPciDevice, Get-VMHostProfile, Get-VMHostProfileImageCacheConfiguration, Get-VMHostProfileRequiredInput, Get-VMHostProfileStorageDeviceConfiguration, Get-VMHostProfileUserConfiguration, Get-VMHostProfileVmPortGroupConfiguration, Get-VMHostRoute, Get-VMHostService, Get-VMHostSnmp, Get-VMHostStartPolicy, Get-VMHostStorage, Get-VMHostSysLogServer, Get-VMHostTPM, Import-VMHostProfile, Install-VMHostPatch, Invoke-VMHostProfile, Move-VMHost, New-DrsVMHostRule, New-TrustAuthorityVMHostBaseImage, New-VMHostAccount, New-VMHostNetworkAdapter, New-VMHostProfile, New-VMHostProfileVmPortGroupConfiguration, New-VMHostRoute, Remove-DrsVMHostRule, Remove-TrustAuthorityVMHostBaseImage, Remove-VDSwitchVMHost, Remove-VMHost, Remove-VMHostAccount, Remove-VMHostNetworkAdapter, Remove-VMHostNtpServer, Remove-VMHostProfile, Remove-VMHostProfileVmPortGroupConfiguration, Remove-VMHostRoute, Restart-VMHost, Restart-VMHostService, Set-DrsVMHostRule, Set-VMHost, Set-VMHostAccount, Set-VMHostAdvancedConfiguration, Set-VMHostAuthentication, Set-VMHostDiagnosticPartition, Set-VMHostFirewallDefaultPolicy, Set-VMHostFirewallException, Set-VMHostFirmware, Set-VMHostHba, Set-VMHostModule, Set-VMHostNetwork, Set-VMHostNetworkAdapter, Set-VMHostNetworkStack, Set-VMHostProfile, Set-VMHostProfileImageCacheConfiguration, Set-VMHostProfileStorageDeviceConfiguration, Set-VMHostProfileUserConfiguration, Set-VMHostProfileVmPortGroupConfiguration, Set-VMHostRoute, Set-VMHostService, Set-VMHostSnmp, Set-VMHostStartPolicy, Set-VMHostStorage, Set-VMHostSysLogServer, Start-VMHost, Start-VMHostService, Stop-VMHost, Stop-VMHostService, Suspend-VMHost, Test-VMHostProfileCompliance, Test-VMHostSnmp"
---

# VMware PowerCLI — Host Management

ESXi host operations — configure, maintain, monitor hosts. Module: VMware.VimAutomation (100 cmdlets).

## Add

### `Add-VDSwitchVMHost`

**This cmdlet adds hosts to the specified vSphere distributed switch.**

This cmdlet adds hosts to the specified vSphere distributed switch. The physical network adapters of the hosts are not connected to the vSphere distributed switch.

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch] (Required) Specifies the vSphere distributed switch to which you want to add one or more hosts.
- -VMHost [VMHost[]] (Required) Specifies the hosts that you want to add to the vSphere distributed switch.

**Examples:**

```powershell
Get-VDSwitch -Name "MyDistributedSwitch" | Add-VDSwitchVMHost -VMHost "VMHost1", "VMHost2"
```
_Adds two hosts to the specified vSphere distributed switch._

### `Add-VMHost`

**This cmdlet adds a host to be managed by a vCenter Server system.**

This cmdlet adds a host to be managed by a vCenter Server system. The host is added to the datacenter or folder specified by the Location parameter. One of the User/Password and Credential parameters must be provided in order to authenticate with the host. If both are specified, the Credential parameter is used and the User and Password parameters are ignored.

**Parameters:**

- -Credential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the virtual machine host.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet runs even if the authenticity of the host SSL certificate cannot be verified.
- -Location [VIContainer] (Required) Specifies a datacenter or folder where you want to place the host.
- -Name [String] (Required) Specifies the name of the host you want to add to a vCenter Server system.
- -Password [String] (Optional) Specifies the password you want to use for authenticating with the host.
- -Port [Int32] (Optional) Specifies the port on the host you want to use for the connection.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -User [String] (Optional) Specifies the user name you want to use for authenticating with the host.

**Examples:**

```powershell
$myServer = Connect-VIServer -Server 10.23.112.235
Add-VMHost -Server $myServer -Name MyVMHost1 -Location MyDatacenter1 -User MyUsername1 -Password MyPassword1
```
_Adds a VM host to a specified vCenter Server system and provides a username and password for authentication._

```powershell
$myCredentials = Get-VICredentialStoreItem -File "C:\MyCredentials.xml"
$myServer = Connect-VIServer -Server 10.23.112.235
Add-VMHost -Server $myServer -Name MyVMHost1 -Location MyDatacenter1 -Credentials $myCredentials
```
_Adds a VM host to a vCenter Server system and specifies a PSCredential object that contains authentication credentials._

```powershell
$myCredentials = Get-VICredentialStoreItem -File "C:\MyCredentials.xml"
$myServer = Connect-VIServer -Server 10.23.112.235
Add-VMHost -Server $server -Name MyVMHost1 -Location MyDatacenter1 -Credentials $myCredentials -Port MyVMHostPortNumber1 -Confirm:$false
```
_Adds a VM host to a vCenter Server system without asking for confirmation and specifies a port on the host for connecting._

### `Add-VMHostNtpServer`

**This cmdlet adds the specified NTP servers to the NTP server list of the specified hosts.**

This cmdlet adds the specified NTP servers to the NTP server list of the specified hosts. If a server is already in the list, a non-terminating error is generated and a duplicate is not created.

**Parameters:**

- -NtpServer [String[]] (Required) Specifies the domain name or the IP address of the NTP server you want to add to the host.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies a host to which you want to add the NTP server.

**Examples:**

```powershell
Add-VmHostNtpServer -NtpServer "ntp-server-name.com" -VMHost $vmhost
```
_Adds the NTP server with a domain name "ntp-server-name.com" to the virtual machine hosts stored in the $vmhost variable._

```powershell
Add-VmHostNtpServer -NtpServer "192.168.1.5" -VMHost (Get-VMHost)
```
_Adds the NTP server with an IP address "192.168.1.5" to the virtual machine hosts pipelined through the Get-VMHost cmdlet._

## Export

### `Export-LcmVMHostDesiredState`

**This cmdlet exports the desired state of an ESXi host that is managed by vSphere Lifecycle Manager. The desired state consists of the host's base image and the installed software packages.**

This cmdlet exports the desired state of an ESXi host that is managed by vSphere Lifecycle Manager. The desired state consists of the host's base image and the installed software packages. The desired state is exported as a JSON metadata file, as an installable ISO image, or as a ZIP offline bundle. The exported files can be imported in other ESXi hosts or clusters managed by vSphere Lifecycle Manager.

**Parameters:**

- -Destination [String] (Optional) Specifies a local directory where you want to save the JSON metadata file, the installable ISO image, or the ZIP offline bundle. If no value is provided, your current directory will be used.
- -ExportIsoImage [SwitchParameter] (Optional) Specifies whether to export the ESXi base image as an installable ISO image.
- -ExportOfflineBundle [SwitchParameter] (Optional) Specifies whether to export an offline ZIP bundle containing all software packages that can be imported into the vSphere Lifecycle Manager depot.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost] (Required) Specifies the name of the ESXi host whose desired state you want to export.

**Examples:**

```powershell
Export-LcmVMHostDesiredState -VMHost 'my-esx' -Destination './desired-state'
```
_Exports metadata for the desired state of the 'my-esx' ESXi host in the 'desired-state' subdirectory._

```powershell
Get-VMHost 'my-esx' | Export-LcmVMHostDesiredState -ExportIsoImage
```
_Exports metadata for the desired state of the 'my-esx' ESXi host and the ESXi base ISO image in the current directory._

### `Export-VMHostImageDb`

**This cmdlet exports the specified host's base image database to a file that is in a .tgz format.**

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to export the base image database from the specified host.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost[]] (Required) Specifies the host from which you want to export the base image database.

**Examples:**

```powershell
Export-VMHostImageDb -VMHost myHost -FilePath c:\mypath
```
_Exports the base image database from the myHost host to the c:\mypath file._

### `Export-VMHostProfile`

**This cmdlet exports the specified host profile to a file.**

This cmdlet exports the specified host profile to a file that is in the VMware profile format (.vpf). If the value of the Force parameter is $false and the destination file exists or the target parent directory does not exist, a terminating error is generated. If the value of the Force parameter is $true, the existing destination file is overwritten and directories are created to complete the specified file path.

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file where you want to export the host profile.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -Profile [VMHostProfile] (Required) Specifies the host profile you want to export.
- -Server [VIServer] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$profile = (Get-VMHostProfile -Name Profile )[0]

Export-VMHostProfile -FilePath export.prf -Profile $profile -Force
```
_Exports the selected host profile to the export.prf file._

## Format

### `Format-VMHostDiskPartition`

**This cmdlet formats a new VMFS (Virtual Machine File System) on each of the specified host disk partitions.**

**Parameters:**

- -VMHostDiskPartition [VMHostDiskPartition[]] (Required) Specifies the disk partitions on which you want to format a new VMFS.
- -VolumeName [String] (Required) Specifies a name for the new VMFS.

**Examples:**

```powershell
Get-VMHost Host | Get-VMHostDisk | Get-VMHostDiskPartition | ? {.Type -eq "Ntfs"} | Format-VMHostDiskPartition -VolumeName "NewStorage"
```
_Formats the NTFS disk partitions of a host._

## Get

### `Get-DrsVMHostRule`

**This cmdlet retrieves VM to VMHost DRS rules that match the specified filters.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the DRS clusters from which you want to retrieve rules.
- -Name [String[]] (Optional) Specifies the names of the DRS rules you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [DrsVMHostRuleType[]] (Optional) Specifies the types of DRS rules you want to retrieve. This parameter accepts MustRunOn, ShouldRunOn, MustNotRunOn, and ShouldNotRunOn values.
- -VMGroup [DrsClusterVMGroup[]] (Optional) Filters rules by VM group.
- -VMHostGroup [DrsClusterVMHostGroup[]] (Optional) Filters rules by VMHost group.

**Examples:**

```powershell
Get-DrsVMHostRule -Type "MustRunOn"
```
_Retrieves all VM to VMHost DRS rules, which are of type "MustRunOn"._

```powershell
$cluster = Get-Cluster "MyCluster"
Get-DrsVMHostRule -VMHostGroup "MyDrsVMHostGroup" -Cluster $cluster
```
_Retrieves all available VM to VMHost DRS which include the "MyDrsVMHostGroup" DRS VMHost group in the "MyCluster" cluster._

### `Get-EsxCli`

**This cmdlet exposes the ESXCLI functionality.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -V2 [SwitchParameter] (Optional) If specified, the cmdlet returns an EsxCli object version 2 (V2), otherwise an EsxCli object version 1 (V1) is returned. Interface V2 supports specifying method arguments only by name. This is the recommended PowerCLI interface for interoperability with ESXCLI. Interface V1 supports specifying method arguments only by position. Scripts that use interface V1 are not guaranteed to be compatible across two different versions of ESXi. Interface V1 is deprecated.
- -VMHost [VMHost[]] (Required) Specifies hosts on which you want to expose the ESXCLI functionality.

**Examples:**

```powershell
$vmHost = Get-VMHost "vmHostIp"
$esxcli_v1 = Get-EsxCli -VMHost $vmHost
```
_Retrieves a version 1 interface to ESXCLI. This interface version is deprecated and will be removed in a future release. This example works on vCenter Server 5.0/ESXi 5.0 and later._

```powershell
$esxcli_v1 = Get-EsxCli
```
_Retrieves a version 1 interface to ESXCLI using the default connection when connected directly to a single ESXi server. This interface version is deprecated and will be removed in a future release. This example works on vCenter Server 5.0/ESXi 5.0 and later._

```powershell
$vmHost = Get-VMHost "vmHostIp"
$esxcli = Get-EsxCli -VMHost $vmHost -V2
```
_Retrieves a version 2 interface to ESXCLI by specifying a version switch parameter. This example works on vCenter Server 5.0/ESXi 5.0 and later._

### `Get-EsxTop`

**This cmdlet exposes the esxtop functionality.**

This cmdlet exposes the esxtop functionality. The default parameter set is CounterValues. The Counter parameter filters the specified statistics. To retrieve all available counters, use the CounterInfo parameter set. The properties of each counter are returned through the Fields property (an array) of the CounterInfo output object. You can also retrieve stats topologies using the TopogyInfo parameter set. This information contains either inventory data that does not change or a counter instance structure describing the relationship between different counter instances.

**Parameters:**

- -Counter [SwitchParameter] (Required) Indicates that you want to retrieve counters information.
- -CounterName [String[]] (Optional) Specifies the name of the counter for which you want to retrieve information.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Topology [String[]] (Optional) Specifies the topologies for which you want to retrieve information.
- -TopologyInfo [SwitchParameter] (Required) Indicates that you want to retrieve topologies of the statistics.

**Examples:**

```powershell
Get-EsxTop -TopologyInfo
```
_Retrieves the available topologies._

```powershell
Get-EsxTop -Counter
```
_Retrieves the available counters._

```powershell
$vm = Get-VM VM
$group = Get-EsxTop -CounterName SchedGroup | where {$_.VMName -eq $vm.Name}
$groupIDs = $group | select -ExpandProperty GroupID
$gr = Get-EsxTop -TopologyInfo -Topology SchedGroup | %{$_.Entries} | where {$groupIDs -contains $_.GroupId}

$cpuIds = @()
$gr | %{$_.CpuClient} | %{$cpuIds += $_.CPUClientID}

$cpuStats = Get-EsxTop -CounterName 'VCPU' | where {$cpuIds -contains $_.VCPUID}

$cpuStats | fl *
```
_Retrieves statistics for the virtual CPUs of the specified virtual machine._

### `Get-HAPrimaryVMHost`

**On vCenter Server 5.0 and later, this cmdlet retrieves the primary host of the specified HA cluster. On vCenter Server versions earlier than 5.0, this cmdlet retrieves the primary HA (High-Availability) hosts for the specified clusters.**

On vCenter Server 5.0 and later, the cmdlet retrieves the primary host of the specified HA cluster. On vCenter Server versions earlier than 5.0, the cmdlet retrieves the primary HA (High-Availability) hosts for the specified clusters.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters for which you want to retrieve the HA primary hosts.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Cluster | Get-HAPrimaryVMHost
```
_Retrieves the HA primary hosts of the available cluster._

```powershell
Get-HAPrimaryVMHost Cluster
```
_Retrieves the HA primary host of the cluster named Cluster._

### `Get-TrustAuthorityVMHostBaseImage`

**This cmdlet retrieves the Trust Authority virtual machine host base image from the specified Trust Authority clusters in the Trust Authority vCenter Server system.**

**Parameters:**

- -Health [TrustAuthoritySettingsConfigHealth[]] (Optional) Specifies the healths of the Trust Authority virtual machine host base images you want to retrieve.
- -Id [String[]] (Required) Specifies the IDs of the Trust Authority virtual machine host base image you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects have an ID that matches exactly one of the string values in that list.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters from which you want to retrieve the Trust Authority virtual machine host base images.
- -VMHostVersion [String[]] (Optional) Specifies the virtual machine host versions of the Trust Authority virtual machine host base images you want to retrieve.

**Examples:**

```powershell
Get-TrustAuthorityVMHostBaseImage -TrustAuthorityCluster mycluster
```
_Retrieves the Trust Authority virtual machine host base image from the Trust Authority cluster mycluster._

### `Get-VMHost`

**This cmdlet retrieves the hosts on a vCenter Server system.**

This cmdlet retrieves the hosts on a vCenter Server system. Returns a set of hosts that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter. When working directly on an ESX host, the Name property of the returned VMHost object  contains either the DNS name or the IP of the ESX host, depending on which of them was specified when connecting with Connect-VIServer.

**Parameters:**

- -Datastore [StorageResource[]] (Optional) Specifies the datastores or datastore clusters to which the hosts that you want to retrieve are associated. Passing values to this parameter through a pipeline is deprecated and will be removed in a future release.
- -DistributedSwitch [DistributedSwitch[]] (Optional) Filters the available hosts by the virtual switches they are connected to.
- -Id [String[]] (Required) Specifies the IDs of the hosts you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies the vSphere container objects (such as folders, datacenters, and clusters) you want to search for hosts.
- -Name [String[]] (Optional) Specifies the names of the hosts you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -RelatedObject [VMHostRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more VMHost objects that are related to them. This parameter accepts OMResource objects.
- -ResourcePool [ResourcePool[]] (Optional) Specifies resource pools associated with the hosts you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -State [VMHostState[]] (Optional) Specifies the state of the hosts you want to retrieve. The valid values are Connected, Disconnected, NotResponding, and Maintenance.
- -Tag [Tag[]] (Optional) Returns only the virtual machine hosts that are associated with any of the specified tags.
- -VM [VirtualMachine[]] (Optional) Specifies virtual machines whose hosts you want to retrieve.

**Examples:**

```powershell
Get-VMHost -Location MyDatacenter
```
_Retrieves all hosts in the specified datacenter._

```powershell
$MyVM = Get-VM -Name MyVM
Get-VMHost -VM $MyVM
```
_Retrieves the host on which the specified virtual machine runs._

```powershell
$myVDSwitch = Get-VDSwitch -Name "MyVDSwitch"
Get-VMHost -DistributedSwitch $myVDSwitch
```
_Retrieves all hosts associated with the specified vSphere distributed switch._

### `Get-VMHostAccount`

**This cmdlet retrieves the host accounts available on a vCenter Server system.**

This cmdlet retrieves the host accounts available on a vCenter Server system. If both User and Group parameters are set to $true, in the list returned by the command, group accounts come out on top. If none of the User and Group switch parameters are provided, the cmdlet retrieves only the user accounts. If the ID parameter is set, the cmdlet filters the host accounts by their IDs. To specify a server different from the default one, use the Server parameter. Note: The specified server must be an ESX/ESXi host.

**Parameters:**

- -Group [SwitchParameter] (Optional) Indicates that you want to retrieve only group host accounts. Starting with ESXi 5.1, this parameter is not supported.
- -Id [String[]] (Optional) Specifies the IDs of the host accounts you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -User [SwitchParameter] (Optional) Indicates that you want to retrieve only user host accounts.

**Examples:**

```powershell
Get-VMHostAccount -Group
```
_Retrieves the group accounts for the default ESX/ESXi host. Starting with ESXi 5.1, you cannot retrieve group accounts._

```powershell
$myServer1 = Connect-VIServer -Server 10.23.112.235
$myUserAccount1 = New-VMHostAccount -ID MyUser1 -Password MyPass1 -UserAccount
Get-VMHostAccount -Server $myServer1 -ID $myUserAccount1.Id -User
```
_Retrieves a host account specified by an ID and an ESX/ESXi host._

```powershell
$myServer1 = Connect-VIServer -Server 10.23.112.235
$myGroupAccount1 = New-VMHostAccount -ID MyGroup1 -Password MyPassword1 -GroupAccount
Get-VMHostAccount -Server $myServer1 -Id $myGroupAccount.Id -Group
```
_Retrieves a group host account specified by an ID and an ESX/ESXi host. Starting with ESXi 5.1, you cannot retrieve group host accounts._

### `Get-VMHostAdvancedConfiguration`

**This cmdlet retrieves the advanced configuration of the hosts.**

This cmdlet is deprecated. Use Get-AdvancedSetting instead.

**Parameters:**

- -Name [String[]] (Optional) Specifies the names of the host configuration settings you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts for which you want to retrieve the configuration settings.

**Examples:**

```powershell
Get-VMHostAdvancedConfiguration -VMHost 10.23.123.100 -Name net*tcp*
```
_Retrieves the virtual machine host advanced configuration settings, whose names contain "net" and "tcp"._

### `Get-VMHostAuthentication`

**This cmdlet retrieves authentication information for the specified hosts.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the host authentication information that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve authentication information.

**Examples:**

```powershell
$vmhost | Get-VMHostAuthentication
```
_Retrieve authentication information for the specified host._

### `Get-VMHostAvailableTimeZone`

**This cmdlet retrieves the time zones available on the specified host.**

**Parameters:**

- -Name [String[]] (Optional) Specifies the names of the available time zones you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the host for which you want to retrieve the available time zones.

**Examples:**

```powershell
Get-VMHostAvailableTimeZone -Name Pacific* -VMHost 10.23.112.19
```
_Retrieves the Pacific time zones available on the specified host._

### `Get-VMHostDiagnosticPartition`

**This cmdlet retrieves a list of  the diagnostic partitions on the specified hosts.**

This cmdlet retrieves a list of the diagnostic partitions on the specified hosts. The list is ordered by the partitions preference. Local diagnostic partitions are more preferable than shared diagnostic partitions because multiple servers cannot share the same partition. The most preferred diagnostic partition is first in the list.

**Parameters:**

- -All [SwitchParameter] (Optional) Indicates that you want to retrieve all diagnostic partitions on the specified hosts. By default, only the active partitions are retrieved.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts for which you want to retrieve diagnostic partitions.

**Examples:**

```powershell
Get-VMHost 192.168.1.10 | Get-VMHostDiagnosticPartition -All
```
_Retrieves all diagnostic partitions for the specified host._

### `Get-VMHostDisk`

**This cmdlet retrieves information about the specified SCSI LUN disk.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the SCSI LUN disks that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -ScsiLun [ScsiLun[]] (Optional) Specifies the SCSI LUN for which you want to retrieve information.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies hosts to retrieve the hard disks attached to them.

**Examples:**

```powershell
Get-VMHostDisk -VMHost $vmhost
```
_Retrieves the disks of the specified host._

```powershell
$vmhost | Get-VMHostHba -Type FibreChannel | Get-ScsiLun | Get-VMHostDisk
```
_Retrieves the host disks only for LUNs that are of FibreChannel type._

### `Get-VMHostDiskPartition`

**This cmdlet retrieves the partitions of a host disk (LUN).**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the host disk partitions that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHostDisk [VMHostDisk[]] (Optional) Specifies the host disk for which you want to retrieve the partitions.

**Examples:**

```powershell
Get-VMHost Host | Get-VMHostDisk | Get-VMHostDiskPartition | ? {.Type -eq "Ntfs"} | Format-VMHostDiskPartition -VolumeName "NewStorage"
```
_Formats the NTFS disk partitions of a host._

### `Get-VMHostFirewallDefaultPolicy`

**This cmdlet retrieves the firewall default policy of the specified hosts.**

This cmdlet retrieves the firewall default policy of the specified hosts. The firewall policy determines whether the outgoing and incoming connections are allowed.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts whose firewall default policy you want to retrieve.

**Examples:**

```powershell
Get-VMHostFirewallDefaultPolicy -VMHost 10.23.123.100
```
_Retrieves the default firewall policy of the virtual machine host with an IP address 10.23.123.100._

### `Get-VMHostFirewallException`

**This cmdlet retrieves the exceptions from the firewall policy on the specified hosts.**

This cmdlet retrieves the exceptions from the firewall policy on the specified hosts. The exceptions can be filtered using the VMHost, Name, Port, and Enabled parameters.

**Parameters:**

- -Enabled [Boolean] (Optional) Indicates whether you want to retrieve only the enabled hosts firewall exceptions.
- -Name [String[]] (Optional) Specifies the names of the firewall exceptions you want to retrieve.
- -Port [Int32[]] (Optional) Specifies the number of the port for which you want to retrieve the firewall exceptions.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts for which you want to retrieve firewall exceptions.

**Examples:**

```powershell
Get-VMHost -Name VMHost1 | Get-VMHostFirewallException -Enabled:$true
```
_Retrieves the enabled firewall exceptions of a host named VMHost1._

```powershell
Get-VMHostFirewallException "SSH Server", "SSH Client" -VMHost $vmhost
```
_Retrieves the firewall exceptions for the SSH server and client for the virtual machine host $vmhost._

```powershell
Get-VMHostFirewallException -VMHost Host -Port 21
```
_Retrieves the firewall exceptions of a host named Host. Only firewall exceptions which have port 21 in their incoming port or outgoing ports are returned._

### `Get-VMHostFirmware`

**This cmdlet retrieves hosts firmware information.**

This cmdlet retrieves firmware information for the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter. To run this cmdlet, you need to have the "Host.Config.Firmware" permission to the ESX.

**Parameters:**

- -BackupConfiguration [SwitchParameter] (Optional) Indicates that you want to backup the host firmware configuration and download the bundle to the specified DestinationPath.
- -DestinationPath [String] (Required) Specifies a destination path where to download the host configuration backup bundle if the BackupConfiguration parameter is set.
- -Server [VIServer[]] (Optional) This parameter is required when you specify the host by name. In this case, the host with the specified name is searched on the specified servers and firmware information is retrieved from it. If a VMHost object is passed to the VMHost parameter, the Server parameter is not used.
- -VMHost [VMHost[]] (Required) Specifies the hosts for which you want to retrieve firmware information.

**Examples:**

```powershell
Get-VMHostFirmware -VMHost $vmhost
```
_Retrieves the firmware information for the specified host._

```powershell
Get-VMHostFirmware -VMHost $vmhost -BackupConfiguration -DestinationPath C:\Downloads
```
_Backups a server configuration for the virtual machine host stored in the $vmhost variable, and downloads the configuration files into the specified folder._

### `Get-VMHostHardware`

**This cmdlet retrieves ESXi host hardware and firmware information.**

This cmdlet retrieves hardware and firmware information for the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Required) Filters the ESXi hosts by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Server [VIServer[]] (Optional) This parameter is required when you specify the host by name. In this case, the host with the specified name is searched on the specified servers and hardware information is retrieved from it. If a VMHost object is passed to the VMHost parameter, the Server parameter is not used.
- -SkipAllSslCertificateChecks [SwitchParameter] (Optional) Indicates that all checks for SSL server certificates are skipped.   Note: You should use this parameter only for trusted computers.
- -SkipCACheck [SwitchParameter] (Optional) Indicates that when connecting through HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).   Note: You should use this parameter only when the remote server can be trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated.
- -SkipCNCheck [SwitchParameter] (Optional) Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.   Note: You should use this parameter only for trusted computers.
- -SkipRevocationCheck [SwitchParameter] (Optional) Indicates that the revocation check for server certificates is skipped.   Note: You should use this parameter only for trusted computers.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve hardware information. If not specified, the cmdlet retrieves hardware information for all hosts on all default connections.
- -WaitForAllData [SwitchParameter] (Optional) If specified, forces all data for each result object to be retrieved before that object is returned. If this parameter is not specified, retrieval of some of the data in the output objects might be postponed to an arbitrary point in time between the cmdlet call and the first time the data is accessed through the corresponding property. As a result, not specifying this parameter makes the cmdlet return data faster, but different portions of the data in result objects might come from different points in time.

**Examples:**

```powershell
Get-VMHost "MyVMHost" | Get-VMHostHardware
```
_Retrieves hardware information about the "MyVMHost" host._

```powershell
Get-VMHostHardware -VMHost "MyVMHost" -SkipAllSslCertificateChecks
```
_Retrieves hardware information about the "MyVMHost" host, skipping all verifications of SSL server certificates._

### `Get-VMHostHba`

**This cmdlet retrieves information about the available HBAs (Host Bus Adapter).**

**Parameters:**

- -Device [String[]] (Optional) Specifies the devices of the HBA you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [HbaType[]] (Optional) Specifies the type of the HBAs you want to retrieve. The valid values are Block, FibreChannel, iSCSI, and ParallelSCSI.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve HBAs.

**Examples:**

```powershell
Get-VMHostHba -Device *hba0* | fl
```
_Retrieves the available HBA devices that contain "hba0" in their names._

### `Get-VMHostModule`

**This cmdlet retrieves the option strings of the specified host modules.**

This cmdlet retrieves the option strings of the specified host modules. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Name [String[]] (Optional) Specifies the names of the host modules you want to retrieve. To find a list of the valid module names for different servers, see the vSphere documentation or in the ESX console, run "esxcfg-module -l". This parameter is mandatory only if you are connected to ESX/vCenter Server with version earlier than 4.0.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies hosts to retrieve their modules.

**Examples:**

```powershell
Get-VMHostModule -Name Shaper
```
_Retrieves the option string for the specified host module._

### `Get-VMHostNetwork`

**THis cmdlet retrieves the host networks on a vCenter Server system.**

This cmdlet retrieves the host networks on a vCenter Server system. This command retrieves the networking configuration of the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts whose networking configuration you want to retrieve.

**Examples:**

```powershell
Get-VMHostNetwork -VMHost 10.23.113.212 | fl
```
_Retrieves the  networking configuration for the virtual machine host on IP address 10.23.113.212._

### `Get-VMHostNetworkAdapter`

**This cmdlet retrieves the host network adapters on a vCenter Server system.**

**Parameters:**

- -Console [SwitchParameter] (Optional) Indicates that you want to retrieve only service console virtual network adapters.
- -Id [String[]] (Optional) Specifies the IDs of the host network adapters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the host network adapters you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on future PowerCLI versions, specify the parameter by name.
- -Physical [SwitchParameter] (Optional) Indicates that you want to retrieve only physical network adapters.
- -PortGroup [VirtualPortGroupBase[]] (Optional) Specifies the port groups to which network adapters that you want to retrieve are connected.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VirtualSwitch [VirtualSwitchBase[]] (Optional) Specifies the virtual switches to which network adapters that you want to retrieve are connected. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on future PowerCLI versions, specify the parameter by name.
- -VMHost [VMHost[]] (Optional) Specifies the hosts whose network adapters you want to retrieve. The position of this parameter is deprecated and might change in a following release.
- -VMKernel [SwitchParameter] (Optional) Indicates that you want to retrieve only VMKernel virtual network adapters.

**Examples:**

```powershell
Get-VMHostNetworkAdapter -VMKernel
```
_Retrieves information about about all VMKernel network adapters on servers that you are connected to._

```powershell
$myVMHost = Get-VMHost -Name MyVMHost
Get-VMHostNetworkAdapter -VMHost $myVMHost -Physical
```
_Retrieves all physical network adapters on the specified host._

```powershell
$myVDSwitch = Get-VDSwitch -Name MyVDSwitch
Get-VMHostNetworkAdapter -VirtualSwitch $myVDSwitch -VMKernel
```
_Retrieves all VMKernel network adapters connected to the specified virtual switch._

### `Get-VMHostNetworkStack`

**This cmdlet retrieves the host network stacks on a vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the host network stacks you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the host network stacks you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost[]] (Optional) Specifies the hosts whose network stacks you want to retrieve.

**Examples:**

```powershell
Get-VMHostNetworkStack
```
_Retrieves all network stacks on servers that you are connected to._

```powershell
$myVMHost = Get-VMHost -Name MyVMHost
Get-VMHostNetworkStack -VMHost $myVMHost
```
_Retrieves all network stacks on the specified host._

### `Get-VMHostNtpServer`

**This cmdlet retrieves the NTP servers on the specified hosts.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts, whose NTP servers you want to retrieve.

**Examples:**

```powershell
Get-VMHostNtpServer -VMHost 10.23.123.100
```
_Retrieves the NTP server of the virtual machine host with an IP address 10.23.123.100.   127.127.1.0_

### `Get-VMHostPatch`

**This cmdlet retrieves information about the host patches installed on the specified hosts. This cmdlet is deprecated and will not return any results for ESX hosts version 5.0 and later. Use (Get-ESXCli).software.vib.list() as an alternative.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve the available patches.

**Examples:**

```powershell
Get-VMHostPatch Host
```
_Retrieves information of the host patches installed on the specified host._

### `Get-VMHostPciDevice`

**This cmdlet retrieves the PCI devices on the specified hosts.**

**Parameters:**

- -DeviceClass [PciDeviceClass[]] (Optional) Limits results to devices of the specified classes.
- -Name [String[]] (Optional) Filters the PCI devices by name.   Note: This parameter is not case-sensitive.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies the hosts whose PCI devices you want to retrieve. If not specified, the cmdlet retrieves PCI devices for all hosts on all default connections.

**Examples:**

```powershell
Get-VMHost "MyHost" | Get-VMHostPciDevice
```
_Retrieves the PCI devices on the "MyVMHost" host._

### `Get-VMHostProfile`

**This cmdlet retrieves the available host profiles.**

This cmdlet retrieves the available host profiles. A host profile encapsulates the host settings and helps to manage the host configuration.

**Parameters:**

- -Description [String[]] (Optional) Specifies a phrase from the description of the host profiles you want to retrieve.
- -Entity [InventoryItem[]] (Optional) Specifies inventory objects associated with the host profiles you want to retrieve.
- -Id [String[]] (Optional) Specifies the IDs of the host profiles you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the host profiles you want to retrieve.
- -ReferenceHost [VMHost[]] (Optional) Specifies the reference hosts of the profiles you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VMHostProfile -Name Profile
```
_Retrieves the virtual machine host profile named Profile._

### `Get-VMHostProfileImageCacheConfiguration`

**Retrieves an image cache configuration for the given host profile.**

Retrieves an image cache configuration for the given host profile. This configuration encapsulates the host image caching settings.

**Parameters:**

- -HostProfile [VMHostProfile[]] (Required) Specifies the virtual machine host profile.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VMHostProfileImageCacheConfiguration -HostProfile "Host Profile"
```
_Retrieves the image cache configuration for the host profile named Host Profile._

### `Get-VMHostProfileRequiredInput`

**This cmdlet performs a check whether the available information is sufficient to apply a host profile.**

This cmdlet performs a check whether the available information is sufficient to apply a host profile, and returns missing values. If the cmdlet returns no output, the information in the hashtable passed to the Variable parameter is sufficient to apply the host profile to the host by using the Apply-VMHostProfile cmdlet.

**Parameters:**

- -Inapplicable [SwitchParameter] (Optional) Indicates that you want to view also the elements that are inapplicable to the operation.
- -Profile [VMHostProfile] (Optional) Specifies a host profile to check if the provided information is sufficient for applying it to the specified host.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Variable [Hashtable] (Optional) Provides a hash table that contains the available values required for applying the specified profile to the the specified host.
- -VMHost [VMHost] (Required) Specifies a host to check if the provided information is sufficient for applying the specified host profile.

**Examples:**

```powershell
Get-VMHost | Get-VMHostProfileRequiredInput
```
_Retrieves required input for a list of hosts._

```powershell
Get-VMHostProfileRequiredInput -VMHost $vmhost -Profile $vmhostProfile
```
_Retrieves a required input by specifying a host and a profile._

```powershell
$result = Get-VMHostProfileRequiredInput -VMHost $vmhost -Variable $requiredInputHashtable;

if (-not $result) { Apply-VMHostProfile -Entity $vmhost -Variable $requiredInputHashtable}
```
_Check whether the specified hashtable that contains values for each required input is exhaustive. If the result is null, then the hashtable can be used by Apply-VMHostProfile._

### `Get-VMHostProfileStorageDeviceConfiguration`

**Retrieves the storage device configuration for the given host profile.**

**Parameters:**

- -DeviceName [String[]] (Optional) There can be multiple devices within a host profile. This parameter filters the result for a particular device. If no value is passed to this parameter, configurations are returned for all devices by default.
- -HostProfile [VMHostProfile[]] (Required) Specifies the virtual machine host profile.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VMHostProfileStorageDeviceConfiguration -HostProfile 'Host_Profile' -DeviceName 'mpx.vmhba1:C0:T5:L0'
```
_Retrieves the storage device configuration for the device name mpx.vmhba1:C0:T5:L0 within the HostProfile named Host_Profile_

### `Get-VMHostProfileUserConfiguration`

**This cmdlet retrieves the user password configuration for the given host profile.**

This cmdlet retrieves the user password configuration for the given host profile. The user password configuration encapsulates the hosts password policy type and password.

**Parameters:**

- -HostProfile [VMHostProfile[]] (Required) virtual machine host profile
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -UserName [String[]] (Optional) There can be multiple accounts within a host profile. This parameter filters the result for a particular account. If no value is passed to this parameter, configurations are returned for all accounts by default.

**Examples:**

```powershell
Get-VMHostProfileUserConfiguration -HostProfile "Host_Profile" -UserName "root"
```
_Retrieves the user password configuration for the username root within the HostProfile named Host_Profile_

### `Get-VMHostProfileVmPortGroupConfiguration`

**Retrieves the virtual machine port group configuration for the given host profile.**

**Parameters:**

- -HostProfile [VMHostProfile[]] (Required) Specifies the virtual machine host profile.
- -PortGroupName [String[]] (Optional) Specifies the port group name that is unique for the host profile. The port group name can be passed to filter results for the particular port group.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VMHostProfileVmPortGroupConfiguration -HostProfile 'Host_Profile'
```
_Retrieves all virtual machine port group configurations within the host profile named Host_Profile._

### `Get-VMHostRoute`

**This cmdlet retrieves the routes from the routing table of the specified hosts.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve routes.

**Examples:**

```powershell
Get-VMHostRoute -VMHost $vmhost
```
_Retrieves the routes for the specified host._

```powershell
Get-VMHostRoute -VMHost $vmhost1, $vmhost2 -Server $server1, $server2
```
_Retrieves the routes for the specified hosts and servers._

### `Get-VMHostService`

**This cmdlet retrieves information about a host service.**

This cmdlet retrieves information about a host service. If the Refresh parameter is set to $true, the cmdlet refreshes the host services information before retrieving it. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Refresh [SwitchParameter] (Optional) Indicates whether the cmdlet refreshes the service information before retrieving it.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies hosts for which you want to retrieve the available services.

**Examples:**

```powershell
Get-VMHostService -Refresh
```
_Refreshes and retrieves the host services on the default server._

```powershell
$vmhost = Get-VMHost -Name Host

$vmHostService = Get-VMHostService -VMHost $vmhost
```
_Gets the services of the specified host._

### `Get-VMHostSnmp`

**This cmdlet retrieves hosts SNMP configuration.**

This cmdlet retrieves hosts SNMP configuration. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VMHostSNMP
```
_Retrieves the host SNMP configuration. Operates on the default server which must be an ESX host._

### `Get-VMHostStartPolicy`

**This cmdlet retrieves the start policy of hosts.**

This cmdlet retrieves the start policy of the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts whose start policy you want to retrieve.

**Examples:**

```powershell
Get-VMHostStartPolicy -VMHost 10.23.113.212
```
_Retrieves the start policy of the virtual machine host on IP address 10.23.113.212._

### `Get-VMHostStorage`

**This cmdlet retrieves the host storages on a vCenter Server system.**

This cmdlet retrieves the host storages on a vCenter Server system. The cmdlet returns a list of the storages on the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the host storages that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Refresh [SwitchParameter] (Optional) Indicates whether the cmdlet refreshes the storage system information before retrieving the specified host storages.
- -RescanAllHba [SwitchParameter] (Optional) Indicates whether to issue a request to rescan all virtual machine hosts bus adapters for new storage devices prior to retrieving the storage information.
- -RescanVmfs [SwitchParameter] (Optional) Indicates whether to perform a re-scan for new virtual machine file systems that might have been added, prior to retrieving the storage information.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts for which you want to retrieve storage information.

**Examples:**

```powershell
Get-VmHostStorage -VMHost 10.23.112.234 -Refresh
```
_Retrieves storage information from the virtual machine host with IP address 10.23.112.234._

```powershell
Get-VMHostStorage | select -expandproperty scsilun | fl *
```
_Retrieves information about the vendor, model, and serial number of the virtual machine host storage SCSI adapter.   Note that for devices, that are not SCSI-3 compliant, the SerialNumber property is not defined. And not  all SCSI-3 compliant devices provide the serial number information._

### `Get-VMHostSysLogServer`

**This cmdlet displays the remote syslog servers of the specified hosts.**

This cmdlet displays the remote syslog servers of the specified hosts. The returned object contains the server address and the port if configured.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the host whose remote syslog server you want to display.

**Examples:**

```powershell
$sysLogServer = Get-VMHostSysLogServer  -VMHost 10.23.123.234
```
_Retrieves the SysLog server of the virtual machine host with IP address 10.23.123.234._

### `Get-VMHostTPM`

**This cmdlet retrieves the TPM 2.0 devices from the specified host.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the TPM you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost[]] (Required) Specifies the hosts on which you want to get TPM.

**Examples:**

```powershell
Connect-VIServer -Server $vCenterAddress -User myroot -Password mypassword
Get-VMHostTPM -VMHost $esxiAddress
```
_Retrieves the TPM 2.0 devices info of the specified host._

```powershell
Connect-VIServer -Server $vCenterAddress -User myroot -Password mypassword
Get-VMHostTPM -Id myTpmId
```
_Retrieves the TPM 2.0 devices info corresponding to the specified TPM Id._

## Import

### `Import-VMHostProfile`

**This cmdlet imports a host profile from a file. The file path must be accessible from the VMware PowerCLI client side.**

**Parameters:**

- -Description [String] (Optional) Specifies a description for the imported host profile.
- -FilePath [String] (Required) Specifies the path to the file, from which you want to import a host profile.
- -Name [String] (Required) Specifies a name of the imported host profile.
- -ReferenceHost [VMHost] (Optional) Specifies a reference host for the imported host profile.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Import-VMHostProfile -FilePath export.prf -Name Profile
```
_Imports a virtual machine host profile from the export.prf file and names it Profile._

## Install

### `Install-VMHostPatch`

**This cmdlet updates the specified hosts.**

This cmdlet updates the specified hosts. The cmdlet installs patches on the host. The patches that can be located locally, on a Web location, or in a host file system. When using the LocalPath or WebPath parameters, the ESX/ESXi host attempts to store the patch contents in its local temporary directory. Because ESXi hosts might not have enough free space on their  local drives, this cannot apply to large size patches. The best practice for upgrading an ESXi host is to upload the patch contents on the host's datastore and to run Install-VMHostPatch with the HostPath parameter. If you want to install patches packaged in a ZIP archive, you must extract them and use one of the HostPatch, LocalPath, or WebPath parameters. If you use the HostPath parameter, you must extract each patch to a temporary folder that is named after the patch ID (for example, c:\temp\ESX400-200906001\), and copy the folder in the root folder of a datastore. Note that the datastore path is case-sensitive. If you use the LocalPath parameter, you must extract each patch to a folder. The name of the folder must contain the patch ID (for example, "ESX400-200906001"). If you use the WebPath parameter, you must extract each patch to a folder that is published on a Web server. The patch URL address must contain the patch ID (for example, http://myInternalWebServer/esx40/ESX400-200906001/). Depending on the component to be upgraded, you might have to set the host into a maintenance mode and to restart the host or the hostd management service after applying the patch.

**Parameters:**

- -HostCredential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the host.
- -HostPassword [SecureString] (Optional) Specifies the password you want to use to authenticate with the host.
- -HostPath [String[]] (Required) Specifies a file path on the ESX/ESXi host to the patches you want to install.
- -HostUsername [String] (Optional) Specifies the username you want to use to authenticate with the host.
- -LocalPath [String[]] (Required) Specifies the local file system path to the patches you want to install. Providing credentials when installing a patch from a local path is mandatory.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to update.
- -WebPath [String[]] (Required) Specifies the Web location of the patches you want to install.

**Examples:**

```powershell
Install-VMHostPatch -VMHost $vmhost1,$vmhost2 -LocalPath c:\esx40\patches\ESX400-200906001\metadata.zip -HostUsername admin -HostPassword pass
```
_Updates ESX servers using a local file. Before running the cmdlet, you must download the patch file locally and extract to a folder. The name of the folder must contain the patch ID (for example, "ESX400-200906001"). Providing credentials when installing a patch from a local path is mandatory._

```powershell
$vmhost | Install-VMHostPatch -WebPath http://myInternalWebServer/esx40/ESX400-200906001/metadata.zip
```
_Upgrades an ESX server using a Web location. Before running the cmdlet, you must download the patch file and extract it to a folder that is published on a Web server. The patch URL address must contain the patch ID (for example, http://myInternalWebServer/esx40/ESX400-200906001/)._

```powershell
$datastore = Get-Datastore -Name Datastore

Copy-DatastoreItem c:\temp\ESX400-200906001\

$datastore.DatastoreBrowserPath -Recurse

$vmhost1,$vmhost2 | Install-VMHostPatch -HostPath
/vmfs/volumes/datastore/ESX400-200906001/metadata.zip
```
_Upgrades ESX servers using the -HostPath parameter. First, you must download the patch file and extract its contents to a temporary folder that is named after the patch ID (for example, c:\temp\ESX400-200906001\). Copy the folder in the root folder of the Datastore datastore and run Install-VMHostPatch providing the datastore path to the patch. Note that the datastore path is case-sensitive._

## Invoke

### `Invoke-VMHostProfile`

**This cmdlet applies a host profile to the specified host or cluster.**

This cmdlet applies a host profile to the specified host or cluster. The host or cluster must be in a maintenance mode. If no value is provided to the Profile parameter, the profile currently associated with the  host or cluster is applied.

**Parameters:**

- -ApplyOnly [SwitchParameter] (Optional) Indicates whether to apply the host profile to the specified virtual machine host without associating it.
- -AssociateOnly [SwitchParameter] (Optional) Indicates whether to associate the host profile to the specified host or cluster without applying it.
- -Entity [InventoryItem[]] (Required) Specifies hosts or clusters to which you want to apply the virtual machine host profile.
- -Profile [VMHostProfile] (Optional) Specifies the host profile you want to apply.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Variable [Hashtable] (Optional) Specifies a hash table object that provides values for the host profile required variables.

**Examples:**

```powershell
Invoke-VMHostProfile -AssociateOnly -Entity $cluster -Profile $profile
```
_Associates the specified profile to all hosts in the specified cluster._

```powershell
Invoke-VMHostProfile -Entity $vmhost -Profile $profile
```
_Associates and applies the specified profile to the specified host._

```powershell
Get-VMHost | Invoke-VMHostProfile -ApplyOnly -Profile $profile
```
_Applies the specified profile to all specified hosts._

## Move

### `Move-VMHost`

**This cmdlet moves hosts to another location.**

This cmdlet moves hosts to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Destination [VIContainer] (Required) Specifies the location where you want to move the hosts.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to move to another location.

**Examples:**

```powershell
Move-VMHost 192.168.112.113 -Destination Datacenter
```
_Moves the host with IP address 10.23.112.113 to a different datacenter named Datacenter._

## New

### `New-DrsVMHostRule`

**This cmdlet creates a new VM to VMHost DRS rule.**

**Parameters:**

- -Cluster [Cluster] (Optional) Specifies the clusters on which you want to create the new rule.
- -Enabled [Boolean] (Optional) Specifies whether to enable the new rule.
- -Name [String] (Required) Specifies the name for the new rule.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [DrsVMHostRuleType] (Required) Specifies the type of the rule you want to create. This parameter accepts MustRunOn, ShouldRunOn, MustNotRunOn, and ShouldNotRunOn values.
- -VMGroup [DrsClusterVMGroup] (Required) Specifies the VMGroup you want to use for the new rule.
- -VMHostGroup [DrsClusterVMHostGroup] (Required) Specifies the VMHostGroup you want to use for the new rule.

**Examples:**

```powershell
New-DrsVMHostRule -Name "MyDrsRule" -Cluster "MyCluster" -VMGroup "MyVMGroup" -VMHostGroup "MyVMHostGroup" -Type "MustRunOn"
```
_Creates a new VM to VMHost DRS rule within the "MyCluster" cluster._

### `New-TrustAuthorityVMHostBaseImage`

**This cmdlet creates a Trust Authority virtual machine host base image in the Trust Authority vCenter Server system.**

**Parameters:**

- -FilePath [String] (Required) Specifies the image file that you can use to create a Trust Authority virtual machine host base image. The file is in a .tgz format.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustAuthorityCluster [TrustAuthorityCluster] (Required) Specifies the Trust Authority cluster in which you can create a new Trust Authority virtual machine host base image.

**Examples:**

```powershell
Export-VMHostImageDb -VMHost 1.1.1.1 -FilePath c:\mypath -Server workloadSystem
New-TrustAuthorityVMHostBaseImage -TrustAuthorityCluster mycluster -FilePath c:\mypath -Server trustAuthoritySystem
```
_Creates a new Trust Authority virtual machine host base image in the Trust Authority cluster mycluster from the image file c:\mypath. You can export it from a workload host in the workload vCenter Server system._

### `New-VMHostAccount`

**This cmdlet creates a new host user or group account.**

This cmdlet creates a new host user or group account using the provided parameters.

**Parameters:**

- -AssignGroups [String[]] (Optional) If the UserAccount parameter is set to $true, use AssignGroups to specify the groups to which the newly created user belongs.
- -AssignUsers [String[]] (Optional) If the GroupAccount parameter is set to $true, use AssignUsers to specify the users that belong to the newly created group account.
- -Description [String] (Optional) Provide a description of the new host account. The maximum length of the text is 255 symbols.
- -GrantShellAccess [SwitchParameter] (Optional) Indicates that the new account is allowed to access the ESX shell.
- -GroupAccount [SwitchParameter] (Optional) Indicates that the new host account is a group account. Starting with ESXi 5.1, this parameter is not supported.
- -Id [String] (Required) Specifies an ID for the new host account.
- -Password [String] (Required) Specifies a password for the new host account.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -UserAccount [SwitchParameter] (Optional) Indicates that the new host account is a user account.

**Examples:**

```powershell
New-VMHostAccount -ID MyUser1 -Password MyPassword1 -UserAccount
```
_Creates a user account with a specified user ID and password. The user account is created on the default server._

```powershell
$myUser1 = Get-VMHostAccount -ID MyUser1 -User
New-VMHostAccount -Id MyGroup1 -GroupAccount -AssignUsers $myUser1
```
_Creates a group account with a specified ID and assigns a specified user to the group account. Starting with ESXi 5.1, you cannot create group host accounts._

### `New-VMHostNetworkAdapter`

**This cmdlet creates a new HostVirtualNIC (Service Console or VMKernel) on the specified host.**

This cmdlet creates a new HostVirtualNIC (Service Console or VMKernel) on the specified host. Creates a port group with a name specified by the PortGroup parameter on the virtual switch passed through the VirtualSwitch parameter. Adds either a Console NIC if ConsoleNIC is set, or a VMKernel NIC otherwise.

**Parameters:**

- -AutomaticIPv6 [SwitchParameter] (Optional) Indicates that the IPv6 address is obtained through a router advertisement.
- -ConsoleNic [SwitchParameter] (Optional) If the value is $true, indicates that you want to create a service console virtual network adapter. If the value is $false, indicates that you want to create a virtual host/VMkernel network adapter. Not supported on ESXi.
- -FaultToleranceLoggingEnabled [Boolean] (Optional) Indicates that the network adapter is enabled for Fault Tolerance (FT) logging. This parameter is supported only on ESX/vCenter Server 4.1 and later.
- -IP [String] (Optional) Specifies an IP address for the new network adapter. All IP addresses are specified using IPv4 dot notation. If IP is not specified, DHCP mode is enabled. For VMKernel network adapters, the DHCP mode is supported only on vCenter Server 4.1, ESX 4.1, and later.
- -IPv6 [String[]] (Optional) Specifies multiple static addresses using the following format: <IPv6>/<subnet_prefix_length> or <IPv6>. If you skip <subnet_prefix_length>, the default value of 64 is used.
- -IPv6ThroughDhcp [SwitchParameter] (Optional) Indicates that the IPv6 address is obtained through DHCP.
- -Mac [String] (Optional) Specifies a media access control (MAC) address for the new virtual network adapter.
- -ManagementTrafficEnabled [Boolean] (Optional) Indicates that you want to enable the network adapter for management traffic. This parameter is supported only on ESX/ESXi/vCenter Server 4.1 and later.
- -Mtu [Int32] (Optional) Specifies the MTU size. This parameter is supported only on ESX/vCenter Server 4.1 and later.
- -PortGroup [String] (Optional) Specifies the port group to which you want to add the new adapter. If a distributed switch is passed to the VirtualSwitch parameter, an existing port group name should be specified. For standard virtual switches, if the port group is non-existent, a new port group with the specified name will be created and the new adapter will be added to the port group.
- -PortId [String] (Optional) Specifies the port of the specified distributed switch to which you want to connect the network adapter. Use this parameter only if a distributed switch is passed to the VirtualSwitch parameter.
- -Server [VIServer[]] (Optional) The Server parameter is required when the host is specified by name. In this case, the host with the specified name is searched for on the specified Servers and a network adapter is added to it. If a VMHost object is passed to the VMHost parameter, the Server parameter is not used.
- -SubnetMask [String] (Optional) Specifies a subnet mask for the new network adapter.
- -VirtualSwitch [VirtualSwitchBase] (Required) Specifies the virtual switch to which you want to add the new network adapter.
- -VMHost [VMHost] (Optional) Specifies the host to which you want to add the new adapter. This parameter is mandatory when creating a network adapter on a distributed switch.
- -VMotionEnabled [Boolean] (Optional) Indicates that you want to use the new virtual host/VMKernel network adapter for VMotion.
- -VsanTrafficEnabled [Boolean] (Optional) Indicates that Virtual SAN traffic is enabled on this network adapter.
- -NetworkStack [HostNetworkStack] (Required) Specifies the host network stack to which you want to add the new adapter.

**Examples:**

```powershell
$vmhost = Get-VMHost -Name MyVMHost1
$myVirtualSwitch = Get-VirtualSwitch -VMHost $vmhost -Name MyVirtualSwitch1
New-VMHostNetworkAdapter -VMHost $vmhost -PortGroup MyVMKernelPortGroup1 -VirtualSwitch $myVirtualSwitch -Mtu 4000
```
_Creates a VMKernel port group at the MyVirtualSwitch1 virtual switch. The IP address is obtained via DHCP._

```powershell
$vmhost = Get-VMHost -Name MyVMHost1
$myVirtualSwitch = Get-VirtualSwitch -VMHost $vmhost -Name MyVirtualSwitch1
New-VMHostNetworkAdapter -VMHost $vmhost -PortGroup MyVMKernelPortGroup1 -VirtualSwitch $myVirtualSwitch -IP 192.168.168.110 -SubnetMask 255.255.255.0
```
_Creates a VMKernel port group at the MyVirtualSwitch1 virtual switch and assigns a static IP address._

```powershell
$vmhost = Get-VMHost -Name MyVMHost1
$myVirtualSwitch = Get-VirtualSwitch -VMHost $vmhost -Name MyVirtualSwitch1
New-VMHostNetworkAdapter -VMHost $vmhost -VirtualSwitch $myVirtualSwitch -PortGroup MyVMKernelPortGroup1 -IP 192.168.0.1 -SubnetMask 255.255.255.0 -IPv6 "0200:2342::1/32"
```
_Creates a VMKernel NIC that has an IPv4 address and an IPv6 address._

### `New-VMHostProfile`

**This cmdlet creates a new  host profile based on a reference host.**

This cmdlet creates a new host profile based on a reference host.

**Parameters:**

- -CompatibilityMode [SwitchParameter] (Optional) If you are connected to a vCenter Server/ESX 5.0 or later, use this parameter to indicate that you want the new profile to be compatible with hosts running ESX/vCenter Server versions earlier than 5.0.
- -Description [String] (Optional) Provides a description for the new host profile.
- -Name [String] (Required) Specifies a name for the new host profile.
- -ReferenceHost [VMHost] (Required) Specifies the reference host, on which the new virtual machine host profile is based.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$h = Get-VMHost 10.23.134.133

New-VMHostProfile -Name testProfile -Description "This is my first test profile." -ReferenceHost $h
```
_Creates a profile based on the virtual machine host with an IP address 10.23.134.133._

### `New-VMHostProfileVmPortGroupConfiguration`

**This cmdlet creates a new virtual machine port group configuration.**

**Parameters:**

- -HostProfile [VMHostProfile] (Required) Specifies the virtual machine host profile.
- -PortGroupName [String] (Required) Specifies the name of the new virtual machine port group configuration. This name is unique for the particual host profile.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VLanId [Int32] (Optional) Specifies the VLAN ID for the new configuration.
- -VSwitchName [String] (Required) Specifies the virtual switch name for the new configuration.

**Examples:**

```powershell
New-VMHostProfileVmPortGroupConfiguration -HostProfile 'Host Profile' -PortGroupName 'VM Network2' -VSwitchName 'vSwitch0' -VLanId 1
```
_Creates a new virtual machine port group configuration 'VM Network2' within the host profile named 'HostProfile' with a virtual switch named 'vSwitch0' and VLAN Id that is equal to one._

### `New-VMHostRoute`

**This cmdlet creates a new route in the routing table of a host.**

**Parameters:**

- -Destination [IPAddress] (Required) Specifies a destination IP address for the new route.
- -Gateway [IPAddress] (Required) Specifies a gateway IP address for the new route.
- -PrefixLength [Int32] (Required) Specifies the prefix length of the destination IP address. For IPv4, the valid values are from 0 to 32, and for IPv6 - from 0 to 128.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost] (Required) Specifies the host for which you want to create a new route. Passing multiple values to this parameter is obsolete.

**Examples:**

```powershell
New-VMHostRoute -VMHost 10.23.114.195 -Destination 192.168.103.102 -PrefixLength 32 -Gateway 10.23.84.53
```
_Creates a route for the specified host._

## Remove

### `Remove-DrsVMHostRule`

**This cmdlet removes the specified VM to VMHost DRS rule.**

**Parameters:**

- -Rule [DrsVMHostRule[]] (Required) Specifies the rules you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-DrsVMHostRule -Rule "MyDRSRule"
```
_Removes the "MyDRSRule" VM to VMHost DRS rule from the environment._

### `Remove-TrustAuthorityVMHostBaseImage`

**This cmdlet removes the Trust Authority virtual machine host base images from the Trust Authority cluster in the Trust Authority vCenter Server system.**

**Parameters:**

- -VMHostBaseImage [TrustAuthorityVMHostBaseImage[]] (Required) Specifies the virtual machine host base images that you want to remove.

**Examples:**

```powershell
$baseImages = Get-TrustAuthorityVMHostBaseImage -TrustAuthorityCluster mycluster
Remove-TrustAuthorityVMHostBaseImage -VMHostBaseImage $baseImages
```
_Removes the Trust Authority virtual machine host base images from the mycluster Trust Authority cluster._

### `Remove-VDSwitchVMHost`

**This cmdlet removes hosts from the specified vSphere distributed switches.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDSwitch [VDSwitch] (Required) Specifies the vSphere distributed switch from which you want to remove hosts.
- -VMHost [VMHost[]] (Required) Specifies the hosts that you want to remove.

**Examples:**

```powershell
Get-VDSwitch -Name "MySwitch" | Remove-VDSwitchVMHost -VMHost "VMHost1", "VMHost2"
```
_Removes two hosts from the specified vSphere distributed switch._

### `Remove-VMHost`

**This cmdlet removes the specified hosts from the inventory.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to remove.

**Examples:**

```powershell
$myServer = Connect-VIServer -Server 10.23.112.235
Get-VMHost -Server $myServer -Location MyDatacenter1 | Remove-VMHost -Confirm:$false
```
_Removes all VM hosts in the specified location from the vCenter Server system without asking for confirmation._

### `Remove-VMHostAccount`

**This cmdlet removes the specified host accounts.**

This cmdlet removes the specified host accounts . These can be  HostGroupAccount objects, HostUserAccount objects, or both.

**Parameters:**

- -HostAccount [HostAccount[]] (Required) Specifies the host accounts you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VMHostAccount -Group -ID user | Remove-VMHostAccount -Confirm
```
_Removes the group account with ID "user". Asks for confirmation before running the command._

### `Remove-VMHostNetworkAdapter`

**This cmdlet removes the specified host network adapters.**

**Parameters:**

- -Nic [HostVirtualNic[]] (Required) Specifies the network adapters you want to remove.

**Examples:**

```powershell
$network = Get-VMHostNetwork

Remove-VMHostNetworkAdapter $network.VirtualNic[0] -Confirm
```
_Removes the first virtual network adapter of the host._

### `Remove-VMHostNtpServer`

**This cmdlet removes the specified NTP servers from the NTP server list of the specified hosts.**

**Parameters:**

- -NtpServer [String[]] (Required) Specifies the NTP servers you want to remove from the NTP servers list of the specified host.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the host whose NTP servers you want to remove.

**Examples:**

```powershell
Remove-VmHostNtpServer -NtpServer 192.168.1.5 -VMHost $vmhost -Confirm
```
_Removes the NTP server with an IP address 192.168.1.5 from the virtual machine hosts stored in the $vmhost variable._

```powershell
Remove-VmHostNtpServer -NtpServer "old-ntp-server.com" -VMHost (Get-VMHost) -Confirm
```
_Removes the NTP server with a domain name "old-ntp-server.com" from the virtual machine hosts pipelined through the Get-VMHost cmdlet._

### `Remove-VMHostProfile`

**This cmdlet removes the specified host profiles.**

This cmdlet removes the specified host profiles. If the Entity parameter is provided, the cmdlet removes the profile association for the specified entity. Otherwise, the cmdlet removes the profile object.

**Parameters:**

- -Entity [InventoryItem[]] (Required) Specifies the host or cluster whose host profile association you want to remove.
- -Profile [VMHostProfile[]] (Required) Specifies the host profiles you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VMHostProfile -Name Profile | Remove-VMHostProfile -Confirm:$false
```
_Deletes the Profile host profile._

### `Remove-VMHostProfileVmPortGroupConfiguration`

**Removes the given virtual machine port group configuration from the host profile.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VmPortGroupConfiguration [VMHostProfileVmPortGroupConfiguration[]] (Required) Specifies the configuration that you want to remove.

**Examples:**

```powershell
$conf = Get-VMHostProfileVmPortGroupConfiguration -HostProfile 'Host_Profile' -PortGroup 'VM Network2'
Remove-VMHostProfileVmPortGroupConfiguration -VmPortGroupConfiguration $conf
```
_Removes the virtual machine port group configuration 'VM Network2' from the host profile._

### `Remove-VMHostRoute`

**This cmdlet removes host routes.**

**Parameters:**

- -VMHostRoute [VMHostRoute[]] (Required) Specifies the host routes you want to remove.

**Examples:**

```powershell
$destIpList = ('192.168.111.101', '192.168.111.102')

$routes = Get-VMHostRoute -VMHost ($script:vmhost1, $script:vmhost2) | where {$destIpList -contains $_.Destination.IPAddressToString}

Remove-VMHostRoute -VMHostRoute $routes -Confirm:$false
```
_Removes the host routes that have the specified destination IP addresses._

## Restart

### `Restart-VMHost`

**This cmdlet restarts the specified hosts.**

**Parameters:**

- -Evacuate [SwitchParameter] (Optional) Indicates that vCenter Server automatically reregisters the virtual machines that are compatible for reregistration. If they are not compatible, they remain on the rebooted host. If there are powered-on virtual machines that cannot be reregistered, the operation waits until they are powered off manually. The Evacuate parameter is valid only if the cmdlet is run against a vCenter Server system and the host is in a DRS-enabled cluster.
- -Force [SwitchParameter] (Optional) Indicates that you want to restart the hosts even if they are not in a maintenance mode.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to restart.
- -Reason [String] (Optional) Specifies a short message containing the reason for restarting the host. The message cannot be null or empty string.

**Examples:**

```powershell
Restart-VMHost 10.23.112.235 -RunAsync -Confirm
```
_Restarts the specified host after user confirmation. The cmdlet returns without waiting for the task to complete._

### `Restart-VMHostService`

**This cmdlet restarts the specified host services.**

**Parameters:**

- -HostService [HostService[]] (Required) Specifies the host service you want to restart.

**Examples:**

```powershell
Restart-VMHostService -Service $vmHostService -Confirm:$false
```
_Restarts a host service._

## Set

### `Set-DrsVMHostRule`

**This cmdlet modifies the specified VM to VMHost DRS rule.**

**Parameters:**

- -Enabled [Boolean] (Optional) Specifies whether to activate or deactivate the modified rule.
- -Name [String] (Optional) Specifies the new name for the modified rule.
- -Rule [DrsVMHostRule[]] (Required) Specifies the rules you want to modify.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [DrsVMHostRuleType] (Optional) Specifies the new type for the modified rule.
- -VMGroup [DrsClusterVMGroup] (Optional) Specifies the VMGroup you want to use for the modified rule.
- -VMHostGroup [DrsClusterVMHostGroup] (Optional) Specifies the VMHostGroup you want to use for the modified rule.

**Examples:**

```powershell
Get-DRSVMHostRule "MyVMHostRule" | Set-DRSVMHostRule -Name "NewRuleName" -Enabled:$false
```
_Renames and deactivates the "MyVMHostRule" VM to VMHost DRS rule._

### `Set-VMHost`

**This cmdlet modifies the configuration of the host.**

**Parameters:**

- -BaseImage [BaseImage] (Optional) Specifies the ESXi base image that the host should comply with.
- -Component [Component[]] (Optional) Specifies the ESXi component(s) that the host should comply with.
- -DepotOverride [String[]] (Optional) Specifies a depot address from where the host can fetch metadata and resources for the vSphere Lifecycle Manager operations.
- -DisableCryptoSafe [SwitchParameter] (Required) If the value is $true and the VMHost's previous CryptoState is Safe, the VMHost enters a PendingIncapable state. Otherwise, the VMHost remains in an Incapable state. For the PendingIncapable state, the vmhost is explicitly crypto deactivated and pending reboot is to be applied. When vmhost is in this state, creating encrypted virtual machines is not allowed. You need a reboot to totally clean up and enter an Incapable state.
- -Evacuate [SwitchParameter] (Optional) If the value is $true, vCenter Server system automatically reregisters the virtual machines that are compatible for reregistration. If they are not compatible, they remain on the host. If there are powered on virtual machines that cannot be reregistered, the operation waits until they are powered off manually. The Evacuate parameter is valid only when connected to a vCenter Server system and the State parameter is set to Maintenance. Also, the virtual machine host must be in a DRS-enabled cluster.
- -FirmwareAddon [Package] (Optional) Specifies a package from a hardware support manager that the host should comply with.
- -KeyProvider [KeyProvider] (Required) Specifies the key provider you want to use to make the VMHost cryptographically "Safe" or rekey the VMHost's host key.
- -LicenseKey [String] (Optional) Specifies the license key to be used by the host. You can set the host to evaluation mode by passing the 00000-00000-00000-00000-00000 evaluation key.
- -Profile [VMHostProfile] (Optional) Specifies a host profile you want to associate with the host. If the value of this parameter is $null, the current profile association is removed.
- -Reason [String] (Optional) Specifies a short message containing the reason for putting the host in maintenance mode. The message cannot be null or empty string. This parameter can only be used when passing "Maintenance" value to the "State" parameter.
- -RemovedComponent [String[]] (Optional) Specifies a list of components that you want to remove from the base image.   Calling the commandlet with a new value for this parameter overrides any previously configured value. It does not add new components to the list of removed ones. To reset the list of removed components provide an empty array to this parameter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -State [VMHostState] (Optional) Specifies the state of the host. The valid values are Connected, Disconnected, and Maintenance. If there are powered on virtual machines on the host, you can set the host into a maintenance mode, only if it is a part of a DRS-enabled cluster. Before entering maintenance mode, if the host is fully automated, the cmdlet relocates all powered on virtual machines. If the host is not automated or partially automated, you must first generate a DRS recommendation and wait until all powered on virtual machines are relocated or powered off. In this case, you must specify the RunAsync parameter. Otherwise, an error appears.
- -TimeZone [VMHostTimeZone] (Optional) Specifies the time zone for the host by using its name or by providing the corresponding time zone object. Time zone names support wildcards. If the wildcards match more than one time zone, an error appears. Time zone objects can only be applied to the hosts they originate from.
- -VendorAddOn [AddOn] (Optional) Specifies the ESXi vendor add-on that the host should comply with.
- -VMHost [VMHost[]] (Required) Specifies the host you want to configure.
- -VMSwapfileDatastore [Datastore] (Optional) Specifies a datastore that is visible to the host and can be used for storing swapfiles for the virtual machines that run on this host. Using a host-specific swap location might degrade the vMotion performance.
- -VMSwapfilePolicy [VMSwapfilePolicy] (Optional) Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore specified by the VMSwapfileDatastoreID property of the virtual machine host. If the VMSwapfileDatastoreID property is not set or indicates a datastore with insufficient free space, the swapfile is stored in the same directory as the virtual machine. This setting might degrade the vMotion performance.   WithVM - stores the swapfile in the same directory as the virtual machine.
- -VsanDataMigrationMode [VsanDataMigrationMode] (Optional) Specifies the special action to take regarding the vSAN data when moving in maintenance mode. The VsanDataMigrationMode parameter is valid only when connected to a vCenter Server system and when the State parameter is set to VMHostState.Maintenance.

**Examples:**

```powershell
Set-VMHost -VMHost Host -State "Disconnected"
```
_Resets the state of the Host virtual host to Disconnected._

```powershell
$cluster = Get-Cluster -VMHost Host

$task = Set-VMHost -VMHost Host -State "Maintenance" -RunAsync

Get-DrsRecommendation -Cluster $cluster | where {$_.Reason -eq "Host is entering maintenance mode"} | Apply-DrsRecommendation

$vmhost = Wait-Task $task
```
_Activates a maintenance mode for a not automated host that is part of a DRS-enabled cluster and has powered on virtual machines on it._

```powershell
$keyprovider = Get-KeyProvider | select -First 1
Set-VMHost -VMHost Host -KeyProvider $keyprovider
```
_Resets the cryptokey of the VMHost named 'Host'._

### `Set-VMHostAccount`

**This cmdlet configures a host account.**

This cmdlet configures a host account. When configuring a host user account, you can include or exclude the user from the specified groups. When configuring a host group account, you can include or exclude the specified users from this group.

**Parameters:**

- -AssignGroups [String[]] (Optional) If a user host account is to be configured, specifies the group to which you want to add the account. Starting with ESXi 5.1, you cannot configure group host accounts.
- -AssignUsers [String[]] (Optional) If a group host account is configured, specify the users you want to add to the account. Starting with ESXi 5.1, you cannot configure group host accounts.
- -Description [String] (Optional) Provides a description of the specified account. The maximum length of the text is 255 symbols.
- -GrantShellAccess [Boolean] (Optional) Indicates that the account is allowed to access the ESX shell.
- -GroupAccount [HostGroupAccount[]] (Required) Specifies the host group account you want to configure. Starting with ESXi 5.1, you cannot configure group host accounts.
- -Password [String] (Optional) Specifies a new password for the account.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -UnassignGroups [String[]] (Optional) If a user host account is to be configured, specifies a group from which you want to remove the account. Starting with ESXi 5.1, you cannot configure group host accounts.
- -UnassignUsers [String[]] (Optional) If a group host account is to be configured, specifies the users you want to remove from the account.
- -UserAccount [HostUserAccount[]] (Required) Specifies the host user account you want to configure.

**Examples:**

```powershell
$myUserAccount = New-VMHostAccount -ID MyUser1 -Password MyPassword1 -UserAccount
$myGroupAccount = New-VMHostAccount -ID MyGroup1 -GroupAccount -AssignUsers $myUserAccount
Set-VMHostAccount -UserAccount $myUserAccount -UnassignGroups $myGroupAccount
```
_Creates a user account with an ID MyUser1. Then creates a group account with an ID MyGroup1 and assigns the user account MyUser1 to the group account MyGroup1. Finally, excludes the MyUser1 account from the MyGroup1 account. Starting with ESXi 5.1, you cannot configure group host accounts._

### `Set-VMHostAdvancedConfiguration`

**This cmdlet modifies the advanced configuration settings of a host.**

This cmdlet is deprecated. Use New-AdvancedSetting, Set-AdvancedSetting, or Remove-AdvancedSetting instead.

**Parameters:**

- -Name [String] (Optional) Specifies the name of the host configuration setting you want to change.
- -NameValue [Hashtable] (Optional) Provides a hash table that maps values to settings.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Value [Object] (Optional) Specifies a new value of the host configuration setting that you want to modify.
- -VMHost [VMHost[]] (Required) Specifies the host whose advanced configuration settings you want to change.

**Examples:**

```powershell
Get-VMHost 10.23.123.144 | Set-VmHostAdvancedConfiguration -Name Migrate.NetTimeout -Value ( [system.int32] 10 )
```
_Change the migration timeout for the virtual machine host with an IP address 10.23.123.144._

```powershell
$migrationSettings = Get-VMHost 10.23.123.144| Get-VmHostAdvancedConfiguration -Name Migrate.*

Set-VmHostAdvancedConfiguration -VMHost 10.23.123.122  -NameValue $migrationSettings
```
_Gets the advanced settings concerning migration from the host with an IP address 10.23.123.144 and applies them to the virtual machine host with an IP address 10.23.123.122._

```powershell
Set-VMHostAdvancedConfiguration -VMHost 10.23.112.120 -Name Migrate.Enabled -Value 1
```
_Enable VMotion on a host using Set-VMHostAdvancedConfiguration._

### `Set-VMHostAuthentication`

**This cmdlet modifies the host authentication information.**

**Parameters:**

- -Credential [PSCredential] (Optional) Specifies a credential object for authentication.
- -Domain [String] (Required) Specifies a domain you want to join.
- -Force [SwitchParameter] (Optional) If the value is $true, any existing permissions on the managed objects for Active Directory users are deleted and the cmdlet completes. If the value is $false, the cmdlet cannot run if there are any existing permissions on managed objects for Active Directory users.
- -JoinDomain [SwitchParameter] (Required) Indicates whether you want to join the specified domain.
- -LeaveDomain [SwitchParameter] (Required) Indicates whether you want to leave the currently joined domain.
- -Password [SecureString] (Optional) Specifies a password for authentication.
- -Username [String] (Optional) Specifies a user name for authentication.
- -VMHostAuthentication [VMHostAuthentication[]] (Required) Specifies the VMHostAuthentication object you want to modify.

**Examples:**

```powershell
$vmhost | Get-VMHostAuthentication | Set-VMHostAuthentication -JoinDomain -Domain "DomainName.com" -User "Username1" -Password "Password1"
```
_Include an ESX host in a domain._

```powershell
$vmhost | Get-VMHostAuthentication | Set-VMHostAuthentication -LeaveDomain
```
_Exclude an ESX host  from a domain._

```powershell
$vmhost | Get-VMHostAuthentication | Set-VMHostAuthentication -LeaveDomain -Force
```
_Exclude an ESX host from a domain. If AD account permissions are defined on the host, they will be removed._

### `Set-VMHostDiagnosticPartition`

**This cmdlet activates or deactivates the diagnostic partitions of  hosts.**

This cmdlet activates or deactivates the diagnostic partitions of hosts.

**Parameters:**

- -Active [Boolean] (Required) If the value of this parameter is $true, the partition state is changed to active. If the value is $false, the partition state is set to inactive.
- -VMHostDiagnosticPartition [VMHostDiagnosticPartition[]] (Required) Specifies the host diagnostic partition you want to set.

**Examples:**

```powershell
$diagPartition = Get-VMHostDiagnosticPartition -VMHost $vmhost

$diagPartition | Set-VMHostDiagnosticPartition -Active $false -Confirm
```
_Deactivates the active diagnostic partition of the specified host._

### `Set-VMHostFirewallDefaultPolicy`

**This cmdlet sets the default policy for the specified host firewall.**

This cmdlet sets the default policy for the specified host firewall. This policy specifies whether outgoing or incoming connections are allowed. At least one of the AllowIncoming and AllowOutgoing parameters must be set. When you configure the default firewall policy of an ESX/ESXi host version 5.0, you must provide the same value for the AllowIncoming and AllowOutgoing parameters.

**Parameters:**

- -AllowIncoming [Boolean] (Optional) If the value of this parameter is $true, all incoming connections are allowed. If the value is $false, all incoming connections are disallowed.
- -AllowOutgoing [Boolean] (Optional) If the value of this parameter is $true, all outcoming connections are allowed. If the value is $false, all outcoming connections are disallowed.
- -Policy [VMHostFirewallDefaultPolicy[]] (Required) Specifies the host firewall default policy you want to apply.

**Examples:**

```powershell
$firewallpolicy = Get-VMHostFirewallDefaultPolicy -VMHost 10.23.123.100

Set-VMHostFirewallDefaultPolicy -Policy $firewallpolicy -AllowOutGoing $true | fl
```
_Changes the default firewall policy of the virtual machine host with IP address 10.23.123.100, so that the outgoing connections are allowed.   VMHostId        : HostSystem-host-8 IncomingEnabled : False OutgoingEnabled : True Client          : VMware.VimAutomation.Client20.VimClient_

### `Set-VMHostFirewallException`

**This cmdlet activates or deactivates host firewall exceptions.**

**Parameters:**

- -Enabled [Boolean] (Required) If the value is $true, the specified firewall exceptions are activated. If the value is $false, the firewall exceptions are deactivated.
- -Exception [VMHostFirewallException[]] (Required) Specifies the firewall exceptions you want to activate or deactivate.

**Examples:**

```powershell
$ftpFirewallExceptions = Get-VMHostFirewallException -VMHost $vmhost | where {$_.Name.StartsWith('FTP')}

$ftpFirewallExceptions | Set-VMHostFirewallException -Enabled $true
```
_Enables the firewall exceptions for the FTP services on the specified host._

### `Set-VMHostFirmware`

**This cmdlet configures hosts firmware settings.**

This cmdlet configures hosts firmware settings. If the BackupConfiguration parameter is set, backups the host configuration and downloads the bundle to the specified DestinationPath. In order to use the Restore and ResetToDefaults parameters, the host needs to be in maintenance mode. The Backup functionality of Set-VMHostFirmware is deprecated and scheduled for removal. For making backups, use the Get-VMHostFirmware cmdlet instead.

**Parameters:**

- -BackupConfiguration [SwitchParameter] (Optional) The Backup functionality of Set-VMHostFirmware is deprecated and scheduled for removal. For making backups, use the Get-VMHostFirmware cmdlet instead.   Indicates that you want to backup the host firmware configuration and download the bundle to the path specified by the DestinationPath parameter.
- -DestinationPath [String] (Required) Specifies a destination path where to download the host configuration backup bundle if the BackupConfiguration parameter is set.
- -Force [SwitchParameter] (Optional) Indicates that you want to apply the configuration even if the bundle is mismatched. Use this parameter in combination with the Restore parameter.
- -HostCredential [PSCredential] (Optional) Specifies the credential object you want to use for authenticating with the host when uploading a firmware configuration bundle. Do not use this parameter if the HostUser and HostPassword parameters are specified.
- -HostPassword [SecureString] (Optional) Specifies a password for the authenticating with the host when uploading a firmware configuration bundle.
- -HostUser [String] (Optional) Specifies a username for authenticating with the host when uploading a firmware configuration bundle.
- -ResetToDefaults [SwitchParameter] (Optional) Indicates that you want to reset all configuration settings, including the "admin" password, to the factory defaults. The host is rebooted immediately. The host needs to be in a maintenance in order to perform this operation.
- -Restore [SwitchParameter] (Optional) Indicates that you want to restore the configuration of the host to the one that is specified in the provided bundle. The bundle is uploaded to the URL retrieved via Get-VMHostFirmware. This method resets all configuration options, including the "admin" password, to the values in the bundle. The host is rebooted immediately. The host needs to be in maintenance mode in order to perform this operation.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SourcePath [String] (Optional) Specifies the path to the host configuration backup bundle you want to restore. The bundle is uploaded to an URL address which you can retrieve by using the Get-VMHostFirmware cmdlet.
- -VMHost [VMHost[]] (Required) Specifies the host whose firmware you want to configure (it must be an ESX visor).

**Examples:**

```powershell
Set-VMHost -VMHost Host -State 'Maintenance'

Set-VMHostFirmware -VMHost Host -Restore
```
_Restore the host firmware by using the default path for the firmware bundle. You can store the bundle to the default path through HTTP by using the upload URL specified in the firmware bundle object:   $bundle = Get-VMHostFirmware   $uploadUrl = $bundle.UploadUrl_

```powershell
Set-VMHost -VMHost Host -State 'Maintenance'

Set-VMHostFirmware -VMHost Host -Restore -SourcePath c:\bundleToRestore.tgz -HostUser user -HostPassword pass
```
_Restore the host firmware by specifying a firmware bundle as a source path._

```powershell
Set-VMHost -VMHost Host -State 'Maintenance'

Set-VMHostFirmware -VMHost Host -ResetToDefaults
```
_Reset the host configuration to the factory default settings._

### `Set-VMHostHba`

**This cmdlet configures the CHAP properties of the specified iSCSI HBAs.**

This cmdlet configures the CHAP properties of the specified iSCSI HBAs. If (Mutual)ChapType is set to a value different than "Prohibited", (Mutual)ChapPassword must be set. ChapType, MutualChapType, MutualChapName, MutualChapPassword - these are only available on 4.1 or later. Note: Run Set-VmHostHba directly against ESX. When Set-VmHostHba is run against vCenter Server, changing the iScsiName property of an iSCSI adapter modifies its AuthenticationCapabilities property.

**Parameters:**

- -ChapName [String] (Optional) Specifies the CHAP initiator name if CHAP is enabled.
- -ChapPassword [String] (Optional) Specifies the CHAP password if CHAP is enabled.
- -ChapType [ChapType] (Optional) Specifies the type of the CHAP authorization. The valid values are Prohibited, Discouraged, Preferred, and Required.
- -IScsiHba [IScsiHba[]] (Required) Specifies the iSCSI HBA device you want to configure.
- -IScsiName [String] (Optional) Specifies a new name for the host HBA device.
- -MutualChapEnabled [Boolean] (Optional) Indicates that Mutual CHAP authorization is enabled.
- -MutualChapName [String] (Optional) Specifies the Mutual CHAP initiator name if Mutual CHAP is enabled.
- -MutualChapPassword [String] (Optional) Specifies the Mutual CHAP password if Mutual CHAP is enabled.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VMHostHba -Type iScsi | Set-VMHostHba -ChapType Required -ChapName Admin -ChapPassword pass
```
_Changes the CHAP type of the available iScsi to Required._

```powershell
Set-VMHostHba -IScsiHba $iscsi -MutualChapEnabled $true -ChapType Required -ChapName Admin -ChapPassword pass -MutualChapName Administrator -MutualChapPassword Pass
```
_Enables Mutual CHAP for the iScsi devices stored in the $iscsi variable and changes the CHAP type to Required._

### `Set-VMHostModule`

**This cmdlet overrides the host module options with the given ones.**

**Parameters:**

- -HostModule [VmHostModule[]] (Required) Specifies the host module you want to configure.
- -Options [String] (Required) Specifies the new options of the host module.

**Examples:**

```powershell
$module = Get-VMHostModule -Name Shaper

Set-VMHostModule -HostModule $module -Options "New options text"
```
_Overrides the options of the Shaper host module with the provided ones._

```powershell
Get-VMHostModule Shaper | Set-VMHostModule -Options "New options text" -Confirm
```
_Overrides the options of the Shaper host module with the provided ones._

### `Set-VMHostNetwork`

**This cmdlet updates the specified virtual network.**

This cmdlet updates the specified virtual network. The service console and the VMkernel are often not connected to the same network, and therefore each needs its own gateway information. A gateway is needed for connectivity to machines not on the same IP subnet as the service console or VMkernel.

**Parameters:**

- -ConsoleGateway [String] (Optional) Specifies a new console gateway.
- -ConsoleGatewayDevice [String] (Optional) Specifies a new console gateway device.
- -ConsoleV6Gateway [String] (Optional) Specifies a console V6 gateway address. Not supported on ESXi.
- -ConsoleV6GatewayDevice [String] (Optional) Specifies a console V6 gateway device. Not supported on ESXi.
- -DnsAddress [String[]] (Optional) Specifies a new DNS address.
- -DnsDhcpDevice [Object] (Optional) This parameter is mandatory if the value of the DnsFromDhcp parameter is 'true'. Otherwise, it is disregarded. If the DnsDhcpDevice parameter is set, the Dhcp DNS of the service console or VMKernel network adapter will override the system DNS. The parameter takes a ServiceConsoleNIC object, a VMKernelNIC object in case of an ESX visor, or the NIC name as a string.
- -DnsFromDhcp [Boolean] (Optional) Indicates that you want to obtain the network settings from a Dhcp server.
- -DomainName [String] (Optional) Specifies a new domain name.
- -HostName [String] (Optional) Specifies a new host name.
- -IPv6Enabled [Boolean] (Optional) Indicates that IPv6 configuration is enabled. Setting this parameter to $false deactivates the ConsoleV6Gateway, ConsoleV6GatewayDevice, and VMKernelV6Gateway parameters. IPv6 is supported only on vCenter 4.1 and ESX 4.1 or later. To use IPv6 on ESX, you must restart the host after enabling IPv6.
- -Network [VMHostNetworkInfo[]] (Required) Specifies the host network you want to configure.
- -SearchDomain [String[]] (Optional) Specifies a new search domain.
- -VMKernelGateway [String] (Optional) Specifies a new kernel gateway.
- -VMKernelGatewayDevice [String] (Optional) Specifies a new kernel gateway device.
- -VMKernelV6Gateway [String] (Optional) Specifies a VMKernel V6 gateway address. This parameter is supported only on ESX hosts.
- -VMKernelV6GatewayDevice [String] (Optional) Specifies a VMKernel V6 gateway device. This parameter is supported only on ESX hosts.

**Examples:**

```powershell
$vmHostNetworkInfo = Get-VmHostNetwork -Host Host

Set-VmHostNetwork -Network $vmHostNetworkInfo -VMKernelGateway 10.23.11.11 -DomainName eng.vmware.com -HostName Host1 -DnsFromDhcp $false
```
_Gets the network configuration of the virtual machine host named Host. Sets the virtual machine kernel gateway, the domain name, the host name, and the Dhcp of the network._

```powershell
Get-VMHost Host | Get-VMHostNetwork | Set-VMHostNetwork -IPv6Enabled $true

Get-VMHost Host | Restart-VMHost -Force -Confirm:$false
```
_Enables IPv6 support on the Host host and restarts the host._

```powershell
Get-VMHost Host | Get-VMHostNetwork | Set-VMHostNetwork -ConsoleV6Gateway $ipv6GatewayAddress -ConsoleV6GatewayDevice "vswif0"
```
_Configures the IPv6 console default gateway on the Host host._

### `Set-VMHostNetworkAdapter`

**This cmdlet configures the specified host network adapter.**

This cmdlet configures the specified host network adapter. For a physical NIC, you can change the duplex and the bit rate settings (10, 100, 1000, 10000). For a regular virtual NIC, you can change the IP address and the subnet mask. For a console virtual NIC, you can modify the IP and the subnet mask, or choose DHCP mode.

**Parameters:**

- -AutomaticIPv6 [Boolean] (Optional) Indicates that the IPv6 address is obtained through a router advertisement.
- -AutoNegotiate [SwitchParameter] (Optional) Indicates that the host network adapter speed/duplex settings are configured automatically. Use this parameter only if the Duplex and BitRatePerSecMb parameters are not set.
- -BitRatePerSecMb [Int32] (Optional) Specifies the bit rate of the link. Only valid when configuring a physical NIC. Use this parameter only if the AutoNegotiate parameter is not set. Note that updating the speed (BitRatePerSec) of a physical NIC might take some time due to the hardware configuration being performed, and the returned object might still contain the current configuration instead of the updated one.
- -Dhcp [SwitchParameter] (Optional) Indicates whether the host network adapter uses a Dhcp server. This parameter works only on ESXi hosts. For VMKernel adapters, Dhcp is supported only on ESX 4.1 and later.
- -Duplex [String] (Optional) Indicates whether the link is capable of full-duplex. The valid values are Full and Half. You can set this parameter only when updating a PhysicalNIC. Use this parameter only if the AutoNegotiate parameter is not set.
- -FaultToleranceLoggingEnabled [Boolean] (Optional) Indicates that the network adapter is enabled for Fault Tolerance (FT) logging. This parameter is supported only on ESX/vCenter Server 4.1 and later.
- -IP [String] (Optional) Specifies an IP address for the network adapter using an IPv4 dot notation. If the NIC has no subnet mask previously defined, you must also set the SubnetMask parameter. If the IP parameter is not specified, DHCP mode is enabled. Only valid when configuring a virtual NIC.
- -IPv6 [String[]] (Optional) Specifies static addresses using the following format: <IPv6>/<subnet_prefix_length> or <IPv6>. If you skip <subnet_prefix_length>, the default value of 64 is used. Specifying a value for IPv6 parameter overrides the current configuration. To clear all configured static IP addresses, pass an empty array to the IPv6 parameter.
- -IPv6Enabled [Boolean] (Optional) Indicates that IPv6 configuration is enabled. Setting this parameter to $false deactivates all IPv6-related parameters. If the value is $true", you need to provide values for at least one of the IPv6ThroughDhcp, AutomaticIPv6, and IPv6 parameters.
- -IPv6ThroughDhcp [Boolean] (Optional) Indicates that the IPv6 address is obtained through DHCP.
- -Mac [String] (Optional) Specifies the media access control (MAC) address of the virtual network adapter. Only valid when configuring a virtual NIC.
- -ManagementTrafficEnabled [Boolean] (Optional) Indicates that you want to enable the network adapter for management traffic. This parameter is supported only on ESX/ESXi/vCenter Server 4.1 and later.
- -Mtu [Int32] (Optional) Specifies the MTU size.
- -PhysicalNic [PhysicalNic[]] (Required) Specifies the PhysicalNIC objects you want to update.
- -PortGroup [DistributedPortGroup] (Required) Specifies a distributed port group to which you want to connect the host network adapter. You can use this parameter only to migrate a virtual network adapter from a standard port group to a distributed port group.
- -SubnetMask [String] (Optional) Specifies a subnet mask for the NIC. If the NIC has a subnet mask previously defined, specifying the SubnetMask parameter when configuring the IP address is not mandatory unless you want to modify the mask. Only valid when configuring a virtual NIC.
- -VirtualNic [HostVirtualNic[]] (Required) Provide a list of the host network adapters you want to configure.
- -VMotionEnabled [Boolean] (Optional) Indicates that you want to use the virtual host/VMKernel network adapter for VMotion.
- -VsanTrafficEnabled [Boolean] (Optional) Specifies whether Virtual SAN traffic is enabled on this network adapter.
- -ProvisioningEnabled [Boolean] (Optional) Specifies whether vSphere Provisioning is enabled on this network adapter.
- -VSphereReplicationEnabled [Boolean] (Optional) Specifies whether vSphere Replication traffic is enabled on this network adapter.
- -VSphereReplicationNfcEnabled [Boolean] (Optional) Specifies whether vSphere Replication Network File Copy (NFC) traffic is enabled on this network adapter.
- -VSphereBackupNfcEnabled [Boolean] (Optional) Specifies whether backup through NFC is enabled on this network adapter. This parameter is supported in vSphere 7.0 and later.

**Examples:**

```powershell
$vswitch =  New-VirtualSwitch -VMHost 10.23.112.234  -Name VSwitch

$nic =  New-VMHostNetworkAdapter -VMHost 10.23.112.234 -PortGroup PortGroup -VirtualSwitch $vswitch -IP 10.23.123.234 -SubnetMask 255.255.254.0

Set-VMHostNetworkAdapter -VirtualNIC $nic -IP 10.23.112.245 -SubnetMask 255.255.255.0 -Mtu 4000
```
_Updates the network adapter IP address, Subnet mask, and MTU size._

```powershell
Get-VMHost Host | Get-VMHostNetworkAdapter -VMKernel | Set-VMHostNetworkAdapter -VMotionEnabled $true
```
_Enable VMotion on all VMKernel network adapters on the specified host._

```powershell
Get-VMHostNetworkAdapter | where { $_.PortGroupName -eq "Service Console 1" } | Set-VMHostNetworkAdapter -IPv6Enabled $false
```
_Deactivates the IPv6 support on a network adapter._

### `Set-VMHostNetworkStack`

**This cmdlet modifies the specified host network stack.**

This cmdlet configures the specified host network stack.

**Parameters:**

- -CongestionControlAlgoritm [HostNetworkStackCongestionControlAlgoritm] (Optional) Specifies the TCP congest control algorithm used by the network stack.
- -DnsAddress [String[]] (Optional) Specifies the IP addresses of the DNS servers, placed in order of preference.   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set.
- -DnsFromDhcp [Boolean] (Optional) Specifies whether or not DHCP (dynamic host control protocol) is used to determine DNS configuration automatically.
- -DomainName [String] (Optional) Specifies the domain name portion of the DNS name. For example, "vmware.com".   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set.
- -HostName [String] (Optional) Specifies the host name portion of DNS name. For example, "esx01".   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set.
- -MaxNumberOfConnections [Int32] (Optional) Specifies the maximum number of socket connections that can be requested on the network stack.
- -Name [String] (Optional) Specifies a new name for the network stack.
- -NetworkStack [HostNetworkStack[]] (Required) Specifies the network stack that you want to configure.
- -SearchDomain [String[]] (Optional) Specifies the domain in which to search for hosts, placed in order of preference.   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set.
- -VMKernelGateway [String] (Optional) Specifies an IP address for the default gateway using an IPv4 dot notation.
- -VMKernelV6Gateway [String] (Optional) Specifies the default IPv6 gateway using the following format: <IPv6>/<subnet_prefix_length> or <IPv6>. If you skip <subnet_prefix_length>, the default value of 64 is used.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$vmHostNetworkStack = Get-VMHostNetworkStack -VMHost Host

Set-VMHostNetworkStack -Network $vmHostNetworkStack -VMKernelGateway 10.23.11.11 -DomainName eng.vmware.com -HostName Host1 -DnsFromDhcp $false
```
_Retrieves the network stack configuration of the virtual machine host named Host. Sets the virtual machine kernel gateway, the domain name, the host name, and the Dhcp of the network._

### `Set-VMHostProfile`

**This cmdlet modifies the specified host profile.**

**Parameters:**

- -Description [String] (Optional) Specifies a new description for the host profile.
- -Name [String] (Optional) Specifies a new name for the host profile.
- -Profile [VMHostProfile[]] (Required) Specifies the host profile you want to modify.
- -ReferenceHost [VMHost] (Optional) Specifies a reference host for the host profile.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$profile = ( Get-VMHostProfile -Name Profile )[0]

Set-VMHostProfile -Profile $profile -Description "New description."
```
_Changes the description of the Profile host profile._

### `Set-VMHostProfileImageCacheConfiguration`

**This cmdlet modifies image cache configuration for given host profile.**

This cmdlet modifies the image cache configuration for the given host profile.

**Parameters:**

- -DiskArguments [String] (Optional) Specify a comma-separated list of disks that you want to use based on your order of preference. You can specify more than one disk. Default value is the local disk for this argument.
- -IgnoreSsd [Boolean] (Optional) Excludes solid-state disks from eligibility.
- -ImageCacheConfiguration [VMHostProfileImageCacheConfiguration[]] (Required) Specifies the configuration that you want to modify.
- -InstallationDevice [VMHostProfileInstallationDevice] (Optional) Specifies the installation device that can be either on a host (Disk) or on a USB disk.
- -InstallationType [VMHostProfileInstallationType] (Required) Specifies the installation type that can be either stateless caching or statefull install.
- -OverwriteVmfs [Boolean] (Optional) Allows the system to overwrite existing VMFS volumes, if the space is not enough to store the image.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$conf = Get-VMHostProfileImageCacheConfiguration -HostProfile "Host_Profile"

Set-VMHostProfileImageCacheConfiguration -ImageCacheConfiguration $conf -InstallationType StatelessCaching -InstallationDevice Disk
```
_Modifies the image cache configuration by setting the installation type to stateless and device type to Disk for the host profile named Host_Profile._

### `Set-VMHostProfileStorageDeviceConfiguration`

**This cmdlet modifies the storage device configuration for the given host profile.**

**Parameters:**

- -ConfigInfo [String] (Optional) Speicifies configuration information for the device.
- -DeviceStateOn [Boolean] (Optional) Specifies if the device state is switched On.
- -IsPerenniallyReserved [Boolean] (Optional) Specifies if the device is perennially reserved.
- -IsSharedClusterwide [Boolean] (Optional) Specifies if the device is shared clusterwide.
- -NumReqOutstanding [Int32] (Optional) Specifies the maximum number of outstanding disk requests.
- -PspName [String] (Optional) Specifies the path selection plug-in name.
- -QueueFullSampleSize [Int32] (Optional) Specifies the queue full sample size value.
- -QueueFullThreshold [Int32] (Optional) Specifies the queue full threshhold value.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StorageDeviceConfiguration [VMHostProfileStorageDeviceConfiguration[]] (Required) Specifies the configuration that you want to modify.

**Examples:**

```powershell
$conf = Get-VMHostProfileStorageDeviceConfiguration --HostProfile 'Host_Profile' --DeviceName 'mpx.vmhba1:C0:T5:L0'
Set-VMHostProfileStorageDeviceConfiguration -StorageDeviceConfiguration $config -DeviceStateOn $true -QueueFullSampleSize 0
```
_Modifies the storage device configuration by setting the DeviceStateOn to true and QueueFullSampleSize to zero for device name mpx.vmhba1:C0:T5:L0 in the host profile named Host_Profile._

### `Set-VMHostProfileUserConfiguration`

**This cmdlet modifies the user password configuration for the specified account within a host profile.**

**Parameters:**

- -Password [String] (Optional) Specifies the user account password. This parameter is required in case of fixed password policy.
- -PasswordPolicy [VMHostProfilePasswordPolicy] (Required) Specifies the desired password policy type.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -UserConfiguration [VMHostProfileUserConfiguration[]] (Required) Specifies the user configuration that you want to modify.

**Examples:**

```powershell
$config = Get-VMHostProfileUserConfiguration -HostProfile "Host_Profile" -UserName "root"

Set-VMHostProfileUserConfiguration -UserConfiguration $config -PasswordPolicy Default
```
_Changes the password policy type to default for the root user configuration within the host profile named Host_Profile._

### `Set-VMHostProfileVmPortGroupConfiguration`

**This cmdlet modifies the virtual machine port group configuration for the given host profile.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VLanId [Int32] (Optional) Specifies the VLAN ID for the port group.
- -VmPortGroupConfiguration [VMHostProfileVmPortGroupConfiguration[]] (Required) Specifies the configuration that you want to modify.
- -VSwitchName [String] (Optional) Specifies the virtual switch name for the port group.

**Examples:**

```powershell
$conf = Get-VMHostProfileVmPortGroupConfiguration -HostProfile 'Host_Profile'
Set-VMHostProfileVmPortGroupConfiguration -VmPortGroupConfiguration $conf -VLanId 0
```
_Modifies the virtual machine port group configuration by setting the VLAN ID to zero._

### `Set-VMHostRoute`

**This cmdlet modifies a route in the host routing table.**

**Parameters:**

- -Destination [IPAddress] (Optional) Changes the destination IP address of the route.
- -Gateway [IPAddress] (Optional) Changes the gateway IP address of the route.
- -PrefixLength [Int32] (Optional) Modifies the prefix length of the destination IP address. For IPv4, the valid values are from 0 to 32, and for IPv6 - from 0 to 128.
- -VMHostRoute [VMHostRoute[]] (Required) Specifies the route you want to modify.

**Examples:**

```powershell
$vmhostroute = New-VMHostRoute -VMHost 10.23.114.189 -Destination 192.168.104.101 -Gateway 10.23.84.69 -PrefixLength 32

$vmhostroute | Set-VMHostRoute -Gateway 10.23.84.70
```
_Creates a new host route and modifies its gateway._

```powershell
$vmhostroute1 = New-VMHostRoute -VMHost 10.23.114.189 -Destination 192.168.104.101 -Gateway 10.23.84.69 -PrefixLength 32

$vmhostroute2 = New-VMHostRoute -VMHost 10.23.114.190 -Destination 192.168.104.101 -Gateway 10.23.84.70 -PrefixLength 32

Set-VMHostRoute -VMHostRoute ($vmhostroute1, $vmhostroute2) -Destination 192.168.104.0 -PrefixLength 24
```
_Modifies the destination and the prefix length of two host routes._

### `Set-VMHostService`

**This cmdlet modifies a host service.**

**Parameters:**

- -HostService [HostService[]] (Required) Specifies the host service you want to update.
- -Policy [HostServicePolicy] (Required) Specifies an activation policy for the host service.

**Examples:**

```powershell
Get-VMHostService -VMHost Host | Set-VMHostService -Policy "Automatic"
```
_Sets the policy of all services the Host virtual machine host to "Automatic"._

### `Set-VMHostSnmp`

**This cmdlet modifies the host SNMP configuration.**

This cmdlet modifies the host SNMP configuration. If specified, adds or removes a trap target (removing can be specified by either TrapTargetToRemove parameter or by any of the following parameters (or combination of them): TargetCommunity, TargetHost, TargetPort). If the user passes $null, an empty array or string to the ReadOnlyCommunities parameter,  the old values of this property are erased. This results in a NULL value of this property of the output object.

**Parameters:**

- -AddTarget [SwitchParameter] (Required) Indicates that you want to add a new trap target to the host SNMP configuration. A trap target consists of three elements - Community (mandatory), HostName (mandatory), Port (optional - defaults to 162), specified by the TargetCommunity, TargetHost, and TargetPort parameters.
- -Enabled [Boolean] (Optional) Indicates that the SNMP feature is enabled on the specified host.
- -HostSnmp [VmHostSnmp[]] (Required) Specifies the host Snmp object you want to modify.
- -Port [Int32] (Optional) Specifies the port on which the host listens to SNMP messages.
- -ReadOnlyCommunity [String[]] (Optional) Provide a list of communities, identifying who is able to send SNMP requests to that host. If $null, an empty array or string are passed to this parameter, its old values are erased and the output object for the ReadOnlyCommunity property is an empty array. In PowerShell an empty array is defined by @().
- -RemoveTarget [SwitchParameter] (Required) Indicates that you want to remove a trap target from the host SNMP configuration. There are two ways to specify a trap target: * Pass the trap target to the TrapTargetToRemove parameter.   * Use a combination of the TargetCommunity, TargetHost, and TargetPort parameters to specify a criteria (for example, remove all trap targets that are using port 162).
- -TargetCommunity [String] (Required) Specifies the community identifier of the trap target.
- -TargetHost [String] (Required) Specifies the identifier of the target host - a host name or an IP address.
- -TargetPort [Int32] (Optional) Specifies the port on which the target host listens to SNMP messages.
- -TrapTargetToRemove [TrapTarget] (Required) Specifies the trap target you want to remove. The trap target can be obtained from the "TrapTargets" property of the HostSNMP object (an array of TrapTarget objects).

**Examples:**

```powershell
$vmhostSNMP = Get-VMHostSNMP

Set-VMHostSNMP $vmhostSNMP -Enabled:$true -ReadOnlyCommunity 'example-community'
```
_Enables SNMP on a virtual machine host._

```powershell
Get-VMHostSnmp | Set-VMHostSnmp -ReadonlyCommunity @()
```
_Sets the virtual machine host SNMP by erasing the old value of the ReadOnlyCommunity parameter._

### `Set-VMHostStartPolicy`

**This cmdlet modifies the host default start policy.**

This cmdlet modifies the host default start policy. Start policy defines what happens to virtual machines when the server starts up or stops.

**Parameters:**

- -Enabled [Boolean] (Optional) Indicates that the service that controls the host start policies is enabled. If it is enabled, the default start policies and the start policies of the specified hosts are applied. If deactivated, no start policy is applied.
- -StartDelay [Int32] (Optional) Specifies a default start delay of the virtual machines in seconds.
- -StopAction [VmStopAction] (Optional) Specifies the default action that is applied to the virtual machines when the server stops. The valid values are None, Suspend, PowerOff, or GuestShutDown.
- -StopDelay [Int32] (Optional) Specifies a default stop delay of the virtual machines in seconds.
- -VMHostStartPolicy [VMHostStartPolicy[]] (Required) Specifies the host start policy you want to modify.
- -WaitForHeartBeat [Boolean] (Optional) Specifies whether the virtual machines should start after receiving a heartbeat from the host, ignore heartbeats, and start after the StartDelay has elapsed ($true), or follow the system default before powering on ($false). When a virtual machine is next in the start order, the system either waits a specified period of time for a host to power on or it waits until it receives a successful heartbeat from a powered-on host.

**Examples:**

```powershell
Get-VMHost Host | Get-VMHostStartPolicy | Set-VMHostStartPolicy -Enabled:$true -StartOrder 2 -StartDelay 300 -StopAction GuestShutDown -StopDelay 300
```
_Retrieves the start policy of the Host host and modifies its configuration settings._

```powershell
Get-VMHost Host | Get-VMHostStartPolicy | Set-VMHostStartPolicy -WaitForHeartbeat
```
_Retrieves the start policy of the Host host and modifies its configuration settings, so that virtual machines on the specified host wait for the host heartbeat._

### `Set-VMHostStorage`

**This cmdlet configures a host storage.**

This cmdlet configures a host storage. The cmdlet activates or deactivates the software iSCSI support for the specified VMHostStorage objects.

**Parameters:**

- -SoftwareIScsiEnabled [Boolean] (Required) Indicates that on this storage, software iSCSI is enabled.
- -VMHostStorage [VMHostStorageInfo[]] (Required) Specifies the host storage you want to configure.

**Examples:**

```powershell
Get-VMHostStorage 10.23.112.234 | Set-VMHostStorage -SoftwareIScsiEnabled $true
```
_Enables the iSCSI on the specified storage._

### `Set-VMHostSysLogServer`

**This cmdlet configures the remote syslog server of the specified hosts.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SysLogServer [NamedIPEndPoint[]] (Optional) Specifies the sys log servers you want to configure. The parameter accepts objects of the NamedIPEndPoint, IPEndPoint, IPAddress, and String types. The accepted formats, if string is used, are DNS names and the standard IPv6/IPv4 format: FFFF:FFFF:FFFF:FFFF:FFFF:FFFF:192.168.0.1:80, where the FFFF:FFFF:FFFF:FFFF:FFFF:FFFF can be replaced by any hex value with the same structure (both upper or lower case). It is only meaningful in case of IPv6 address and is omitted for IPv4. The 192.168.0.1 part is mandatory and can be any address in the IPv4 format. The :80 part is optional. If omitted, the port must be specified through the SysLogServerPort parameter. If Syslog is set to $null, the configured syslog server, if any, is removed.
- -SysLogServerPort [Int32] (Optional) Specifies the sys log server port. Must be specified if the string that is passed to the SysLogServer parameter does not contain the port value, or the argument of the SysLogServer is an IP address.
- -VMHost [VMHost[]] (Required) Specifies the host whose syslog servers you want to configure.

**Examples:**

```powershell
Set-VMHostSysLogServer -SysLogServer '192.168.0.1:133' -VMHost Host
```
_Sets a SysLog server on the Host virtual machine host._

```powershell
Set-VMHostSysLogServer -SysLogServer $null -VMHost Host
```
_Removes the SysLog server from the Host virtual machine host._

## Start

### `Start-VMHost`

**This cmdlet starts the specified hosts.**

This cmdlet starts the specified hosts. The task completes when the host successfully exits standby state and sends a heartbeat signal. If nothing is received from the host for the time defined by the TimeoutSeconds parameter, the host is declared timed out, and the task is assumed failed.

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TimeoutSeconds [Int32] (Optional) Specifies a time period in seconds to wait for a heartbeat signal from the host. If nothing is received from the host for the specified time, the host is declared timed out, and the task is assumed failed. The default value is 300.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to start.

**Examples:**

```powershell
Start-VMHost 10.23.112.235 -RunAsync
```
_Starts the specified host. The command returns without waiting for the task to complete._

### `Start-VMHostService`

**This cmdlet starts the specified host services.**

**Parameters:**

- -HostService [HostService[]] (Required) Specifies the host services you want to start.

**Examples:**

```powershell
Start-VMHostService -HostService $vmHostService
```
_Starts a host service._

## Stop

### `Stop-VMHost`

**This cmdlet powers off the specified hosts.**

This cmdlet powers off the specified hosts. When the cmdlet runs asynchronously (with the RunAsync parameter) and you are connected directly to the host, the returned task object contains no indicator of success.

**Parameters:**

- -Force [SwitchParameter] (Optional) Indicates that you want to stop the hosts even if they are not in a maintenance mode.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to power off.
- -Reason [String] (Optional) Specifies a short message containing the reason for stopping the host. The message cannot be null or empty string.

**Examples:**

```powershell
Stop-VMHost 10.23.112.235 -Confirm
```
_Shutdowns the specified host after user confirmation._

### `Stop-VMHostService`

**This cmdlet stops the specified host services.**

This cmdlet stops the host service specified by the Service parameter.

**Parameters:**

- -HostService [HostService[]] (Required) Specifies the host services you want to stop.

**Examples:**

```powershell
Start-VMHostService -Service $vmHostService
```
_Stops a host service._

## Suspend

### `Suspend-VMHost`

**This cmdlet suspends hosts.**

This cmdlet puts the specified host machines in standby mode. You can use the suspend feature to make resources available on a short-term basis or for other situations in which you want to put a host on hold without powering it off.

**Parameters:**

- -Evacuate [SwitchParameter] (Optional) If the value is $true, vCenter Server automatically reregisters the virtual machines that are compatible for reregistration. If they are not compatible, they remain on the suspended host. If there are powered-on virtual machines that cannot be reregistered, the operation waits until they are powered off manually. The Evacuate parameter is valid only when connected to a vCenter Server system and the virtual machine host is part of a DRS-enabled cluster.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TimeoutSeconds [Int32] (Optional) Specifies a time period in seconds to wait for the host to enter standby mode. If the host is not suspended for the specified time, the host is declared timed out, and the task is assumed failed. The default value is 300.
- -VMHost [VMHost[]] (Required) Specifies the hosts you want to suspend.

**Examples:**

```powershell
Suspend-VMHost 10.23.112.54 -TimeOutSeconds 60 -Confirm
```
_Suspends the specified host after user confirmation. If the host is not suspended within 60 seconds, the task is reported failed._

## Test

### `Test-VMHostProfileCompliance`

**This cmdlet tests hosts for profile compliance.**

This cmdlet tests hosts for profile compliance. The Profile and VMHost parameters cannot be set at the same time. If the Profile parameter is set, the specified host profile is tested for compliance with the hosts, to which it is associated. If the VMHost parameter is specified, the host is tested for compliance with the profiles associated with it. If no profiles are associated with the host, then the profile associated with the cluster is applied.

**Parameters:**

- -Profile [VMHostProfile[]] (Required) Specifies a host profile against which to test the specified host for compliance with the host to which it is associated. Do not set this parameter if the VMHost parameter is set.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -UseCache [SwitchParameter] (Optional) Indicates that you want the vCenter Server to return cached information. If vCenter Server does not have cached information, a compliance scanning is performed.
- -VMHost [VMHost[]] (Required) Specifies the host you want to test for profile compliance with the profile associated with it. If no profile is associated with it, the host is tested for compliance with the profile associated with the cluster, to which the host belongs. Do not set this parameter if the Profile parameter is set.

**Examples:**

```powershell
Test-VMHostProfileCompliance -VMHost Host
```
_Tests the specified host for compliance with the profiles associated with it._

```powershell
$profile = Get-VMHostProfile -Name Profile

Apply-VMHostProfile -AssociateOnly -Profile $profile -Entity 10.0.0.126

Test-VMHostProfileCompliance -VMHost 10.0.0.126 | fl *
```
_Test the profile compliance of a non-compliant virtual machine host associated with the profile._

```powershell
Test-VMHostProfileCompliance -Profile $profile | fl *
```
_Test the profile compliance of a virtual machine host profile with the hosts it is associated with._

### `Test-VMHostSnmp`

**This cmdlet tests the host SNMP.**

This cmdlet tests the host SNMP specified by the HostSNMP parameter.

**Parameters:**

- -HostSnmp [VmHostSnmp[]] (Required) Specifies the host SNMP you want to test.

**Examples:**

```powershell
Test-VMHostSNMP -HostSNMP (Get-VMHostSNMP)
```
_Retrieves and tests the SNMP of the default server._

---
name: powercli-cluster-datacenter
description: "VMware PowerCLI 13.3 — Clusters, datacenters, resource pools, folders, DRS rules, inventory"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,cluster-datacenter,Add-TrustedClusterAttestationServiceInfo, Add-TrustedClusterKeyProviderServiceInfo, Copy-HardDisk, Export-LcmClusterDesiredState, Get-Cluster, Get-Datacenter, Get-DrsClusterGroup, Get-DrsRecommendation, Get-DrsRule, Get-Folder, Get-HardDisk, Get-Inventory, Get-LcmClusterDesiredStateRecommendation, Get-LcmHardwareCompatibility, Get-ResourcePool, Get-TrustAuthorityCluster, Get-TrustedCluster, Get-TrustedClusterAppliedStatus, Get-VDTrafficShapingPolicy, Import-LcmClusterDesiredState, Invoke-DrsRecommendation, Move-Cluster, Move-Datacenter, Move-Folder, Move-HardDisk, Move-Inventory, Move-ResourcePool, New-Cluster, New-CnsContainerCluster, New-Datacenter, New-DrsClusterGroup, New-DrsRule, New-Folder, New-HardDisk, New-ResourcePool, New-VIInventoryDrive, Remove-Cluster, Remove-Datacenter, Remove-DrsClusterGroup, Remove-DrsRule, Remove-Folder, Remove-HardDisk, Remove-Inventory, Remove-ResourcePool, Remove-TrustedClusterAttestationServiceInfo, Remove-TrustedClusterKeyProviderServiceInfo, Set-Cluster, Set-Datacenter, Set-DrsClusterGroup, Set-DrsRule, Set-Folder, Set-HardDisk, Set-ResourcePool, Set-TrustAuthorityCluster, Set-TrustedCluster, Set-VDTrafficShapingPolicy, Test-LcmClusterCompliance, Test-LcmClusterHealth"
---

# VMware PowerCLI — Clusters & Datacenters

Clusters, datacenters, resource pools, folders, DRS rules, inventory. Module: VMware.VimAutomation (58 cmdlets).

## Add

### `Add-TrustedClusterAttestationServiceInfo`

**This cmdlet adds the attestation service information configured in the workload vCenter Server system to the trusted hosts in the given trusted cluster.**

**Parameters:**

- -AttestationServiceInfo [AttestationServiceInfo[]] (Required) Specifies the attestation service information that you can configure in the workload vCenter Server system.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustedCluster [TrustedCluster] (Required) Specifies the trusted cluster where you can configure the trusted hosts with the attestation service information.

**Examples:**

```powershell
$attestService = Get-AttestationServiceInfo
Add-TrustedClusterAttestationServiceInfo -TrustedCluster myCluster -AttestationServiceInfo $attestService
```
_Adds the attestation service information configured in the workload vCenter Server system to the trusted hosts in the trusted cluster named myCluster._

### `Add-TrustedClusterKeyProviderServiceInfo`

**This cmdlet adds the key provider service information configured in the workload vCenter Server system to the trusted hosts in the given trusted cluster.**

**Parameters:**

- -KeyProviderServiceInfo [KeyProviderServiceInfo[]] (Required) Specifies the key provider service information that you can configure in the workload vCenter Server system.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustedCluster [TrustedCluster] (Required) Specifies the trusted cluster where you can configure the trusted hosts with the key provider service information.

**Examples:**

```powershell
$kmxService = Get-KeyProviderServiceInfo
Add-TrustedClusterKeyProviderServiceInfo -TrustedCluster myCluster -KeyProviderServiceInfo $kmxService
```
_Adds the key provider service information configured in the workload vCenter Server system to the trusted hosts in the trusted cluster named myCluster._

## Copy

### `Copy-HardDisk`

**Copies a virtual hard disk to another destination.**

Copies a virtual hard disk to another destination specified by the DestinationPath parameter. DestinationPath must be a datastore path to the destination folder.

**Parameters:**

- -DestinationPath [String] (Required) Specifies the datastore path to the folder where you want to copy the hard disk. The datastore name is included in the path in square braces.
- -DestinationStorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the type of the hard disk copy. The valid values are Thin, Thick, and EagerZeroedThick. This parameter is only applicable when you are connected to an ESX/ESXi host.
- -Force [SwitchParameter] (Optional) Indicates whether to overwrite all disks with the same name at the provided destination.
- -HardDisk [HardDisk[]] (Required) Specifies the virtual hard disk you want to copy.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.

**Examples:**

```powershell
Get-HardDisk -VM $vm | Copy-HardDisk "[Storage1]/"
```
_Retrieves the hard disks of a virtual machine and copies them into the storage1 root folder._

```powershell
Copy-HardDisk -HardDisk $hdd -DestinationPath "[Storage1] vms/disks" -DestinationStorageFormat Thick
```
_Copies the $hdd hard disk to the "vms/disks"location on storage1 and changes the storage format of the destination disk to Thick._

## Export

### `Export-LcmClusterDesiredState`

**This cmdlet exports the desired state of a vSphere Lifecycle Manager cluster.**

This cmdlet exports the desired state of a vSphere Lifecycle Manager cluster as a JSON metadata file, as an installable ISO image, or as a ZIP offline bundle. The exported files can be imported in other clusters managed by vSphere Lifecycle Manager.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the name of the cluster whose desired state you want to export.
- -Destination [String] (Optional) Specifies a local directory where you want to save the JSON metadata file, the installable ISO image, or the ZIP offline bundle.   Note: If no value is provided, your current directory will be used.
- -ExportIsoImage [SwitchParameter] (Optional) Specifies whether to export the ESXi base image as an installable ISO image.
- -ExportOfflineBundle [SwitchParameter] (Optional) Specifies whether to export an offline ZIP bundle containing all software packages that can be imported into the vSphere Lifecycle Manager depot.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Export-LcmClusterDesiredState -Cluster 'lcm-cluster' -Destination './desired-state'
```
_Exports metadata for the desired state of the 'lcm-cluster' cluster in the 'desired-state' subdirectory._

```powershell
Get-Cluster 'lcm-cluster' | Export-LcmClusterDesiredState -ExportIsoImage
```
_Exports metadata for the desired state of the 'lcm-cluster' and the ESXi base ISO image in the current directory._

## Get

### `Get-Cluster`

**This cmdlet retrieves the clusters available on a vCenter Server system.**

This cmdlet retrieves the clusters available on a vCenter Server system. Returns a set of clusters that correspond to the filter criteria defined by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the clusters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies vSphere container objects (such as folders, datacenters, and clusters) you want to search for clusters.
- -Name [String[]] (Optional) Specifies the names of the clusters you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -RelatedObject [ClusterRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more Cluster objects that are related to them. This parameter accepts OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the clusters that are associated with any of the specified tags.
- -VM [VirtualMachine[]] (Optional) Specifies virtual machines to filter the clusters that contain at least one of them.
- -VMHost [VMHost[]] (Optional) Specifies hosts to filter the clusters that contain at least one of them.

**Examples:**

```powershell
Get-Cluster -Location Folder
```
_Get a list of the available clusters in the Folder folder._

### `Get-Datacenter`

**This cmdlet retrieves the datacenters available on a vCenter Server system.**

This cmdlet retrieves the datacenters available on a vCenter Server system. Returns a set of datacenters that correspond to the filter criteria defined by the cmdlet parameters. By default, the cmdlet searches recursively from any provided starting point. In this case, if the location is not explicitly specified, the search includes the root folder and all other inventory items on the root folder level. If the command runs with the NoRecursion parameter set to $true, and the location is not specified, only the root folder is searched and no datacenters are returned. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies clusters to filter the datacenters that contain at least one of them.
- -Id [String[]] (Required) Specifies the IDs of the datacenters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [Folder[]] (Optional) Specifies vSphere container objects (such as folders) you want to search for datacenters.
- -Name [String[]] (Optional) Specifies the names of the datacenters you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -RelatedObject [DatacenterRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more Datacenter objects that are related to them. This parameter accepts OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the datacenters that are associated with any of the specified tags.
- -VM [VirtualMachine[]] (Optional) Specifies virtual machines to filter the datacenters that contain at least one of them.
- -VMHost [VMHost[]] (Optional) Specifies hosts to filter the datacenters that contain at least one of them.

**Examples:**

```powershell
Get-Datacenter -Name Datacenter*
```
_Retrieves a list of all datacenters on the server, whose names begin with "Datacenter"._

### `Get-DrsClusterGroup`

**This cmdlet retrieves DRS cluster groups for the specified cluster, VM, or VM host.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters for which you want to retrieve the DRS cluster groups.
- -Name [String[]] (Optional) Specifies the names of the DRS cluster groups you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [DrsClusterGroupType] (Optional) Specifies the type of DRS cluster groups you want to retrieve. This parameter accepts VMGroup, VMHostGroup, and All values.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines for which you want to retrieve DRS cluster groups.
- -VMHost [VMHost[]] (Optional) Specifies the VM hosts for which you want to retrieve DRS cluster groups.

**Examples:**

```powershell
Get-DrsClusterGroup -VM $vm1, $vm2
```
_Retrieves the corresponding DRS cluster groups associated with any of the virtual machines from the specified list._

```powershell
Get-DrsClusterGroup -Cluster $cluster -Type VMHostGroup
```
_Retrieves all VM host groups within the specified cluster._

### `Get-DrsRecommendation`

**This cmdlet retrieves the available DRS recommendations from the provided clusters.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters whose DRS recommendations you want to retrieve.
- -Priority [Int32[]] (Optional) Specifies the priority of the DRS recommendations you want to retrieve. The valid values range from 1 to 5.
- -Refresh [SwitchParameter] (Optional) Indicates that you want the cmdlet to refresh the information about the DRS recommendations before retrieving it.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Cluster Cluster | Get-DrsRecommendation -Priority 4,5
```
_Retrieves the DRS recommendations with priorities 4 and 5 from the Cluster cluster._

```powershell
Get-DrsRecommendation -Cluster Cluster -Refresh
```
_Refreshes and retrieves information about the DRS recommendations from the Cluster cluster._

### `Get-DrsRule`

**This cmdlet retrieves the list of DRS rules for the specified clusters.**

This cmdlet retrieves the list of DRS rules for the specified clusters. Each rule defines the virtual machines that can run on the same host (affinity rule) or must run on different hosts (anti-affinity).

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters for which you want to retrieve the DRS rules.
- -Name [String[]] (Optional) Specifies the name of the DRS rule you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [ResourceSchedulingRuleType[]] (Optional) Specifies the type of DRS rules you want to retrieve. This parameter accepts VMAntiAffinity, VMAffinity, and VMHostAffinity values. You cannot set this parameter, when the VMHost parameter is specified.
- -VM [VirtualMachine[]] (Optional) Specifies virtual machines to filter the DRS rules that reference them. Passing values to this parameter through a pipeline is deprecated and will be removed in a future release.
- -VMHost [VMHost[]] (Optional) Specifies VM hosts to filter the DRS rules that reference them. When this parameter is specified, the cmdlet returns only VMHostAffinity rules. You cannot set this parameter, when the Type parameter is specified.

**Examples:**

```powershell
$myCluster = Get-Cluster -Name "MyCluster1"
Get-DrsRule -Cluster $myCluster -Name "*Rule1*"
```
_Retrieves the DRS rules for the cluster stored in the $myCluster variable, whose names contain "Rule1"._

```powershell
Get-Cluster -Name 'MyCluster1' | Get-DrsRule
```
_Retrieves the virtual machine affinity and anti-affinity rules for the specified cluster by pipeline._

```powershell
$myVm1 = Get-VM -Name 'MyVm1'
$myCluster1 = Get-Cluster 'MyCluster1'
Get-DrsRule -Cluster $myCluster1 -VM $myVm1
```
_Retrieves the virtual machine affinity and anti-affinity rules for the specified virtual machine in the specified cluster._

### `Get-Folder`

**This cmdlet retrieves the folders available on a vCenter Server system.**

This cmdlet retrieves the folders available on a vCenter Server system. The cmdlet returns a set of folders that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the folders you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies vSphere container objects (folders or datacenters) you want to search for folders.
- -Name [String[]] (Optional) Specifies the names of the folders you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -RelatedObject [FolderRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more Folder objects that are related to them. This parameter accepts OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vSphere servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the folders that are associated with any of the specified tags.
- -Type [FolderType[]] (Optional) Specifies the type of the folders you want to retrieve. The valid values are VM, HostAndCluster, Datastore, Network, and Datacenter.

**Examples:**

```powershell
$server = Connect-VIServer -Server 10.23.112.235

Get-Folder -Server $server -Name Folder
```
_Retrieves the folder named Folder on the server with IP address 10.23.112.235._

```powershell
Get-Folder -NoRecursion
```
_Retrieves the root folder._

```powershell
Get-Folder -Location $folder
```
_Gets all folders in the specified location._

### `Get-HardDisk`

**This cmdlet retrieves the virtual hard disks available on a vCenter Server system.**

This cmdlet returns the virtual hard disks available on a vCenter Server system. You can retrieve a hard disk by specifying the virtual machines, templates, or snapshots to which it belongs. If the hard disk is not attached to any virtual machines, templates, or snapshots, you can search for it in datastores or retrieve it by providing a datastore path to the file where the virtual hard disk is stored. In this case, you might not be able to derive disk type info, and the value of the DiskType property of the hard disk is Unknown.

**Parameters:**

- -Datastore [Datastore[]] (Required) Specifies the datastores or datastore clusters you want to search for hard disks. This parameter is required when retrieving a hard disk that is attached to no virtual machines, templates, or snapshots.
- -DatastorePath [String[]] (Optional) Specifies datastore paths to the hard disks you want to retrieve. The paths must be in the following format: [datastore_name] <file_path>, where [datastore_name] is the name of the datastore in square brackets and <file_path> is a slash-delimited path from the root of the datastore to the virtual hard disk file. The cmdlet searches recursively the specified locations.   To learn more about the Datastore Provider, in the VMware PowerCLI service console, type:   help about_vimdatastore
- -DiskType [DiskType[]] (Optional) Specifies the type of the hard disks you want to retrieve. The valid values are rawVirtual, rawPhysical, flat, and unknown. If the hard disk is not attached to any virtual machines, templates, or snapshots, you can retrieve it by providing a datastore path to the file where the virtual hard disk is stored. In this case, you might not be able to derive disk type info, and the value of the DiskType property of the hard disk is Unknown.
- -Id [String[]] (Optional) Specifies the IDs of the hard disks you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the SCSI hard disks you want to retrieve.
- -Path [DatastoreItem[]] (Optional) Specifies the file paths to the virtual hard disks you want to retrieve. The cmdlet searches recursively the specified locations.
- -RelatedObject [HardDiskRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more HardDisk objects that are related to them.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Snapshot [Snapshot[]] (Optional) Specifies the snapshots from which you want to retrieve the hard disks.
- -Template [Template[]] (Optional) Specifies the virtual machine templates from which you want to retrieve the hard disks.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines from which you want to retrieve the hard disks.
- -VMGuestDisk [VMGuestDisk[]] (Required) Specifies the virtual machines guest disk from which you want to retrieve the hard disks.

**Examples:**

```powershell
Get-HardDisk -VM VM
```
_Retrieves the hard disks of the virtual machine named VM._

```powershell
Get-HardDisk -VM $vm -DiskType flat
```
_Retrieves the flat hard disks from the specified virtual machines._

```powershell
Get-HardDisk -Datastore "Storage1" -DatastorePath "[Storage1] myVM/"
```
_Retrieves the hard disks from the specified datastore and from the specified datastore path._

### `Get-Inventory`

**This cmdlet retrieves the inventory items available on a vCenter Server system.**

This cmdlet retrieves the inventory items available on a vCenter Server system. The cmdlet returns a set of inventory items that correspond to the filter criteria specified by the provided parameters. To specify a server different from the default one, use the -Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the inventory objects you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies vSphere container objects (such as folders, datacenters, and clusters) you want to search for inventory items.
- -Name [String[]] (Optional) Specifies the names of the inventory objects you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Inventory -Location Datacenter -Name *Pool
```
_Retrieves all inventory items in the Datacenter datacenter, whose names end with "Pool"._

### `Get-LcmClusterDesiredStateRecommendation`

**This cmdlet generates a desired state recommendation of a vSphere Lifecycle Manager cluster.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the name of the cluster that you want to get a desired state recommendation for.
- -Current [SwitchParameter] (Required) If specified, creates a desired state recommendation based on the currently installed ESXi major base image version. The system recommends installing the latest patch or update of the currently installed major base image version. For example, if you have ESXi base image version 6.5 installed and ESXi 6.7 U2 is the last release for the 6.0 major version, the system recommends installing ESXi 6.7 U2.
- -Latest [SwitchParameter] (Optional) If specified creates a desired state recommendation based on the latest ESXi base image version. For example, if you have ESXi base image version 6.5 installed and ESXi 7.0 is the latest version available, the system will recommend installing ESXi 7.0.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-LcmClusterDesiredStateRecommendation 'lcm-cluster'
```
_Creates a desired state recommendation based on the latest ESXi base image version._

```powershell
Get-LcmClusterDesiredStateRecommendation 'lcm-cluster' -Current
```
_Creates a desired state recommendation based on the currently installed ESXi major base image version. The system recommends installing the latest patch or update of the currently installed major base image version._

### `Get-LcmHardwareCompatibility`

**This cmdlet verifies that the components in the base image are compatible with all storage controllers on the hosts in the cluster in accordance with the VMware Compatibility Guide.**

This cmdlet verifies that the components in the base image are compatible with all vSAN storage controllers on the hosts in the cluster in accordance with the VMware Compatibility Guide. vSphere Lifecycle Manager scans the base image and checks whether the physical I/O device controllers are compatible with the specified ESXi version. Compatibility is checked for the vSAN storage controllers only.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the name of the cluster to check for hardware compatibility.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost[]] (Optional) Specifies the name of the host to check for hardware compatibility.

**Examples:**

```powershell
Get-LcmHardwareCompatibility 'lcm-cluster'
```
_Checks whether the storage controllers of the hosts in the 'lcm-cluster' cluster are compatible with vSAN in accordance with the VMware Compatibility Guide._

### `Get-ResourcePool`

**This cmdlet retrieves the resource pools available on a vCenter Server system.**

Retrieves the resource pools available on a vCenter Server system. The cmdlet returns a set of resource pools that correspond to the filter criteria provided by the cmdlet parameters. Virtual machine hosts have a hidden resource pool named Resources, which is a parent of all resource pools of the host. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the resource pools you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies vSphere container objects (such as folders, datacenters, and clusters) you want to search for resource pools.
- -Name [String[]] (Optional) Specifies the names of the resource pools you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -RelatedObject [ResourcePoolRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more ResourcePool objects that are related to them. This parameter accepts ProviderVdc and OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the resource pools that are associated with any of the specified tags.
- -VM [VirtualMachine[]] (Required) Specifies virtual machines to filter the resource pools that contain at least one of them.

**Examples:**

```powershell
$server = Connect-VIServer -Server 10.23.112.235

Get-ResourcePool -Server $server -VM VM
```
_Retrieves information of the resource pool to which the virtual machine MS Win belongs._

### `Get-TrustAuthorityCluster`

**This cmdlet retrieves the Trust Authority clusters from the Trust Authority vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the Trust Authority cluster you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the Trust Authority clusters you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -State [TrustAuthorityState] (Optional) Specifies the state of the Trust Authority clusters you want to retrieve.

**Examples:**

```powershell
Get-TrustAuthorityCluster
```
_Retrieves the Trust Authority clusters from the connected Trust Authority vCenter Server system._

### `Get-TrustedCluster`

**This cmdlet retrieves the trusted clusters from the connected workload vCenter Server system.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the trusted cluster you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the trusted clusters you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -State [TrustedState] (Optional) Specifies the state of the trusted clusters you want to retrieve.

**Examples:**

```powershell
Get-TrustedCluster -Name mycluster
```
_Retrieves the trusted cluster with a name mycluster from the connected workload vCenter Server system._

### `Get-TrustedClusterAppliedStatus`

**This cmdlet retrieves the applied status of the trusted service information on the trusted clusters in the workload vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustedCluster [TrustedCluster[]] (Required) Specifies the trusted cluster where you can retrieve the applied status.

**Examples:**

```powershell
Get-TrustedClusterAppliedStatus -TrustedCluster mycluster
```
_Retrieves the applied status from the mycluster trusted cluster in the connected workload vCenter Server system._

### `Get-VDTrafficShapingPolicy`

**This cmdlet retrieves the traffic shaping policy for distributed ports.**

This cmdlet retrieves the traffic shaping policy for distributed ports. For distributed port group and vSphere distributed switch parameter sets, the default port policy at the distributed port group or switch level is retrieved.

**Parameters:**

- -Direction [TrafficDirection] (Required) Specifies the direction of the traffic shaping policy.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPort [VDPort[]] (Required) Specifies the distributed ports for which you want to retrieve the traffic shaping policy.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies a distributed port group for which you want to retrieve the default traffic shaping policy.
- -VDSwitch [VDSwitch[]] (Required) Specifies a vSphere distributed switch for which you want to retrieve the default traffic shaping policy.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDTrafficShapingPolicy -Direction In
```
_Retrieves the ingress traffic shaping policy of a vSphere distributed switch named "MyVDSwitch"._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDPort | Get-VDTrafficShapingPolicy -Direction Out
```
_Retrieves the engress traffic shaping policies of all ports inside a distributed port group named "MyVDPortgroup"._

## Import

### `Import-LcmClusterDesiredState`

**This cmdlet imports a specification file to set a desired state of a vSphere Lifecycle Manager cluster.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the name of the cluster whose desired state you want to set.
- -JsonSpecContent [String] (Required) Specifies a JSON string containing a desired state metadata definition.
- -LocalSpecLocation [String] (Required) Specifies the path to a JSON metadata file located on the local file system.
- -RemoteSpecLocation [String] (Required) Specifies the path to a remotely located JSON metadata file.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Import-LcmClusterDesiredState -Cluster 'target-cluster' -LocalSpecLocation lcm-cluster-desired-state-spec.json
```
_Sets the desired state of the 'target-cluster' cluster to the one described in the 'lcm-cluster-desired-state-spec.json' file located on the local file system._

```powershell
Import-LcmClusterDesiredState -Cluster 'target-cluster' -RemoteSpecLocation 'https://dummy-address/lcm-cluster-desired-state-spec.json'
```
_Sets the desired state of the 'target-cluster' cluster to the one described in the file from the specified remote location._

## Invoke

### `Invoke-DrsRecommendation`

**This cmdlet applies the specified DRS recommendations.**

**Parameters:**

- -DrsRecommendation [DrsRecommendation[]] (Required) Specifies the DRS recommendations you want to apply.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.

**Examples:**

```powershell
Get-DrsRecommendation -Priority 1,2 | Invoke-DrsRecommendation
```
_Retrieves and applies DRS recommendations with priorities 1 and 2._

```powershell
$drs = Get-DrsRecommendation -Cluster Cluster
Invoke-DrsRecommendation -DrsRecommendation $drs -RunAsync
```
_Retrieves the DRS recommendations from the Cluster cluster and applies them. The command returns without waiting for the task to complete._

## Move

### `Move-Cluster`

**This cmdlet moves a vCenter Server cluster from one location to another.**

This cmdlet moves a vCenter Server cluster to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters you want to move to another location.
- -Destination [VIContainer] (Required) Specifies the folder or datacenter where you want to move the clusters. If a datacenter is specified for the Destination parameter, the cluster is moved to its "hostFolder" folder. The "hostFolder" is a system folder and is guaranteed to exist.   Note: You cannot move clusters from one datacenter to another. You can only move clusters between folders and to datacenter level.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Move-Cluster -Cluster Cluster -Destination Folder
```
_Moves the cluster named Cluster into the folder called Folder on the same datacenter_

### `Move-Datacenter`

**This cmdlet moves a vCenter Server datacenter from one location to another.**

This cmdlet moves a vCenter Server datacenter to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Datacenter [Datacenter[]] (Required) Specifies the datacenters you want to move to another location.
- -Destination [VIContainer] (Required) Specifies the folder where you want to move the datacenters.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Move-Datacenter Datacenter -Destination Folder
```
_Moves the Datacenter datacenter into the folder named Folder._

### `Move-Folder`

**This cmdlet moves a vCenter Server folder from one location to another.**

This cmdlet moves a vCenter Server folder to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Destination [VIContainer] (Required) Specifies the datacenter or folder where you want to move the folders. If a datacenter is specified for the Destination parameter, the folder is moved to the datacenter's hostFolder or vmFolder folder, depending on the folder's child item type. The hostFolder and vmFolder are system folders and are guaranteed to exist.
- -Folder [Folder[]] (Required) Specifies the folders you want to move to another location.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Folder -Name "vmFolder" | Move-Folder -Destination "destinationVmFolder"
```
_Moves the "vmFolder" folder into another folder of the same type named "destinationVmFolder"._

### `Move-HardDisk`

**This cmdlet moves a hard disk from one location to another.**

**Parameters:**

- -Datastore [StorageResource] (Required) Specifies a datastore or ? datastore cluster to move ? hard disk to. If a datastore cluster is specified, the system checks whether the Storage Distributed Resource Scheduler (SDRS) is enabled and acts accordingly. If SDRS is enabled, the system allocates the hard disk to the datastore cluster in automated SDRS mode. If SDRS is deactivated, the system allocates the hard disk to the datastore with the largest amount of free space in the datastore cluster.
- -HardDisk [HardDisk[]] (Required) Specifies the hard disk that you want to move to another location.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the storage format of the relocated hard disk. This parameter accepts Thin, Thick, and EagerZeroedThick values.

**Examples:**

```powershell
$myDatastore1 = Get-Datastore -Name 'MyDatastore1'
$myDisk = Get-VM -Name MyVm1 | Get-HardDisk
Move-HardDisk -HardDisk $myDisk -Datastore $myDatastore1
```
_Moves the hard disk of a specified virtual machine to another datastore._

```powershell
$myDisk = Get-VM -Name 'MyVM1' | Get-HardDisk
$myDatastore1 = Get-Datastore -Name 'MyDatastore1'
Move-HardDisk -HardDisk $myDisk -Datastore $myDatastore1 -StorageFormat 'EagerZeroedThick'
```
_Moves the hard disk of a specified virtual machine to another datastore and changes the storage format of the hard disk to EagerZeroedThick._

```powershell
$myDisk = Get-VM -Name 'MyVM1' | Get-HardDisk
$myDatastoreCluster = Get-DatastoreCluster -Name 'MyDatastoreCluster'
Move-HardDisk -HardDisk $myDisk -Datastore $myDatastoreCluster
```
_Moves the hard disk of the 'MyVM1' virtual machine to the 'MyDatastoreCluster' datastore cluster._

### `Move-Inventory`

**This cmdlet moves a vCenter Server inventory item from one location to another.**

This cmdlet moves a vCenter Server inventory object or template to the location that is specified by the Destination parameter.

**Parameters:**

- -Destination [VIContainer] (Required) Specifies the location where you want to move the inventory items.
- -Item [InventoryItem[]] (Required) Specifies the Folder, ResourcePool, Datacenter, VirtualMachine, VMHost, Template, or Cluster objects you want to move to another location.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -DestinationSslThumbprint [String] (Optional) Specifies the SSL thumbprint of the destination server when moving virtual machines between vCenter Server systems.

**Examples:**

```powershell
$vm = Get-VM -Name VM*

Move-Inventory -Item $vm -Destination Folder
```
_Moves the virtual machines whose names start with VM to the Folder folder._

```powershell
Get-Folder Folder1 | Get-Inventory -NoRecursion | Move-Inventory -Destination Folder2
```
_Moves all objects from the Folder1 folder to the Folder2 folder._

### `Move-ResourcePool`

**This cmdlet moves a resource pool from one location to another.**

This cmdlet moves a resource pool to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter. Moving a resource pool is only supported when the objects assigned to the ResourcePool and Destination parameters are passed through connections to one and the same server with the same credentials.

**Parameters:**

- -Destination [VIContainer] (Required) Specifies the location where you want to move the resource pools. If a host or a cluster is specified for the Destination parameter, the resource pool is moved into a resource pool named Resources. The Resources resource pool is a system resource pool and is guaranteed to exist.
- -ResourcePool [ResourcePool[]] (Required) Specifies the resource pools you want to move to another location.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Move-ResourcePool -ResourcePool ResourcePool -Destination Host
```
_Moves the resource pool named ResourcePool to the virtual machine host Host._

## New

### `New-Cluster`

**This cmdlet creates a new cluster.**

This cmdlet creates a new cluster with the provided inputs in the location that is specified by the Location parameter. HAEnabled is automatically set to $true if some of the HA settings, HAAdmissionControlEnabled, HAFailoverLevel, HARestartPriority, or HAIsolationResponse are specified. DrsEnabled is automatically set to $true if some of the DRS settings, DrsAutomationLevel, or DrsMode are specified.

**Parameters:**

- -DrsAutomationLevel [DrsAutomationLevel] (Optional) Specifies a DRS automation level. The valid values are FullyAutomated, Manual, and PartiallyAutomated.
- -DrsEnabled [SwitchParameter] (Optional) If specified, enables VMware DRS.
- -DrsMode [DrsMode] (Optional) This parameter is deprecated and scheduled for removal. Use the DrsAutomationLevel parameter instead.   Specifies a DRS mode. The valid values are FullyAutomated, Manual, and PartiallyAutomated.
- -EVCMode [String] (Optional) Specifies the VMware EVC mode of the newly created cluster. If not specified or set to $null, EVC is deactivated.
- -HAAdmissionControlEnabled [SwitchParameter] (Optional) Indicates that virtual machines cannot be powered on if they violate availability constraints.
- -HAEnabled [SwitchParameter] (Optional) If specified, enables VMware HA.
- -HAFailoverLevel [Int32] (Optional) Specifies a configured failover level. This is the number of physical host failures that can be tolerated without impacting the ability to meet minimum thresholds for all running virtual machines. The valid values are in the range of 1 to 4.
- -HAIsolationResponse [HAIsolationResponse] (Optional) Indicates that the virtual machine should be powered off if a host determines that it is isolated from the rest of the compute resource. The valid values are PowerOff and DoNothing. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -HARestartPriority [HARestartPriority] (Optional) Specifies the cluster HA restart priority. The valid values are Disabled, Lowest, Low, Medium, High, and Highest. VMware HA is a feature that detects failed virtual machines and automatically restarts them on alternative ESX hosts. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -Location [VIContainer] (Required) Specifies the location where you want to place the new cluster. If a data center is specified for the Location parameter, the cluster is created in its "hostFolder" folder. The "hostFolder" is a system folder and is guaranteed to exist.
- -Name [String] (Required) Specifies the name of the new cluster.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMSwapfilePolicy [VMSwapfilePolicy] (Optional) Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore that is specified by the VMSwapfileDatastoreID property of the virtual machine host. If the VMSwapfileDatastoreID property is not set or indicates a datastore with unsufficient free space, store the swapfile in the same directory as the virtual machine. This setting might degrade the vMotion performance.   WithVM - stores the swapfile in the same directory as the virtual machine.
- -VsanDiskClaimMode [VsanDiskClaimMode] (Optional) Specifies the mode by which disks are claimed by vSAN. If not specified and VsanEnabled is specified, the assumed value is Manual.
- -VsanEnabled [SwitchParameter] (Optional) Indicates that the vSAN feature is enabled on this cluster.
- -VsanEsaEnabled [SwitchParameter] (Optional) Indicates that the vSAN ESA feature is enabled on this cluster. This feature is supported from vSphere 8.0.
- -CryptoMode [CryptoMode] (Optional) Specifies the cluster encryption mode. When set to OnDemand, hosts in the cluster are not required to be in a cryptographically "Safe" state. When set to ForceEnable, all hosts in the cluster are forced to be in a cryptographically "Safe", that is, vCenter Server has installed a host key on the host.
- -VendorAddOn [AddOn] (Optional) Specifies the ESXi vendor add-on that the cluster's hosts should comply with.
- -BaseImage [BaseImage] (Optional) Specifies the ESXi base image that the cluster's hosts should comply with.

**Examples:**

```powershell
New-Cluster -Name "MyCluster" -Location "MyDatacenter"
```
_Creates a new cluster named "MyCluster" in the "MyDatacenter" data center._

```powershell
New-Cluster -Name "MyCluster" -Location "MyDatacenter" -HAEnabled -HAAdmissionControlEnabled -HAFailoverLevel 2 -VMSwapfilePolicy "InHostDatastore" -HARestartPriority "Low" -HAIsolationResponse "PowerOff"
```
_Creates a new cluster named "MyCluster" in the "MyDatacenter" data center with specified VMware Hgh Availability (HA) settings._

```powershell
New-Cluster -Name "MyCluster" -Location "MyDatacenter" -DRSEnabled -DRSAutomationLevel 'Manual'
```
_Creates a new cluster named "MyCluster" in the "MyDatacenter" data center with specified VMware Distributed Resource Scheduler (DRS) settings._

### `New-CnsContainerCluster`

**This cmdlet creates a vSAN file service IP configuration at the client side.**

**Parameters:**

- -ClusterFlavor [ClusterFlavor] (Optional) Specifies the flavor of the container orchestrator cluster.
- -ClusterType [CnsClusterType] (Required) Specifies the type of the container orchestrator cluster.
- -KubernetesClusterId [String] (Required) Specifies the Kubernetes cluster ID provided by the CNS client.
- -VSphereUser [String] (Required) Specifies the vSphere user corresponding to the container orchestrator cluster user.

**Examples:**

```powershell
New-CnsContainerCluster -ClusterFlavor Vanilla -KubernetesClusterId 'k8_cls_1' -ClusterType Kubernetes
 -VSphereUser 'administrator@vsphere.local'
```
_Creates a Cloud Native Storage (CNS) container cluster with Vanilla as a cluster flavor, 'k8_cls_1' as a cluster ID, Kubernetes as a cluster type, and 'administrator@vsphere.local' as a vSphere user._

### `New-Datacenter`

**This cmdlet creates a new datacenter.**

This cmdlet creates a new datacenter in the location that is specified by the Location parameter.

**Parameters:**

- -Location [VIContainer] (Required) Specifies the location where you want to create the new datacenter.
- -Name [String] (Required) Specifies a name for the new datacenter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$folder = Get-Folder -NoRecursion | New-Folder -Name Folder

New-Datacenter -Location $folder -Name Datacenter | fl
```
_Gets the inventory root folder and create a new folder called Folder in it. Creates a new datacenter called Datacenter in the Folder folder. The result is pipelined to the fl command to retrieve a flat view of the new datacenter properties._

### `New-DrsClusterGroup`

**This cmdlet creates either a VM or VM host DRS cluster group, depending on the used parameter set.**

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the cluster on which you want to create the new DRS cluster group.
- -Name [String] (Required) Specifies the name for the new DRS cluster group.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines which you want to add to the new VM DRS cluster group.
- -VMHost [VMHost[]] (Required) Specifies the VM hosts which you want to add to the new VMHost DRS cluster group.

**Examples:**

```powershell
New-DrsClusterGroup -Name "MyDrsClusterGroup" -VM "MyVM1", "MyVM2" -Cluster "MyCluster"
```
_Creates a VM DRS cluster group in the "MyCluster" cluster by adding a list of virtual machines inside._

### `New-DrsRule`

**This cmdlet creates a new DRS rule.**

This cmdlet creates a new DRS rule. Each rule defines the virtual machines that can run on the same host (affinity rule) or must run on different hosts (anti-affinity rule).

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the cluster for which the new DRS rule applies. Passing multiple values to this parameter is obsolete.
- -Enabled [Boolean] (Optional) If the value of this parameter is $true, the new DRS rule is enabled for the specified clusters. If the value is $false, it is deactivated.
- -KeepTogether [Boolean] (Required) If the value of this parameter is $true, the new DRS rule is an affinity rule. If the value is $false, the DRS rule is an anti-affinity rule.
- -Name [String] (Required) Specifies a name for the new DRS rule.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines that are referenced by the new DRS rule.

**Examples:**

```powershell
New-DrsRule -Cluster $cluster -Name antiAffinityRule1 -KeepTogether $false -VM $antiAffinityVMs
```
_Creates a new DRS rule for the cluster saved in the $cluster variable with the specified parameters._

### `New-Folder`

**This cmdlet creates a new folder on a vCenter Server system.**

This cmdlet creates a new folder on the specified location.

**Parameters:**

- -Location [VIContainer] (Required) Specifies a container object (folder or datacenter) where you want to place the new folder. If a datacenter is specified for the Location parameter, then the folder is created in its "hostFolder" folder and contains hosts and clusters. The "hostFolder" is a system folder and is guaranteed to exist.
- -Name [String] (Required) Specifies a name for the new folder.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-Folder -Name "Folder1" -Location (Get-Datacenter)[0]
```
_Creates a new folder in a datacenter root._

```powershell
Get-Folder | Select -First 1 | New-Folder -Name "Folder2"
```
_Creates a nested folder by using a pipeline command._

```powershell
New-Folder -Name "FirstLevelFolder1" -Location (Get-Folder vm)
```
_Creates a new folder in the root vSphere virtual machine folder._

### `New-HardDisk`

**This cmdlet creates a new hard disk on the specified location.**

This cmdlet creates a new hard disk on the specified virtual machine or datastore. When a new virtual disk with raw disk mapping (RDM) backing is created, the compatibility mode of "virtual" or "physical" must be specified using the DiskType parameter. In "virtual" compatibility mode, the disk can use the specified disk modes. In "physical" compatibility mode, the disk modes are ignored and commands are passed directly to the backing Logical Unit Number (LUN). If "flat" mode is set by the DiskType parameter, the virtual disk backing is preallocated. If the hard disk is attached to no virtual machine, the value of the DiskType parameter might be Unknown, which means that no type is specified. Use the Persistence parameter to make the disk Persistent (changes are immediately and permanently written to the disk), Nonpersistent (changes to the disk are discarded when you power off or reset the virtual machine), IndependentPersistent, IndependentNonPersistent, or Undoable.

**Parameters:**

- -AdvancedOption [AdvancedOption[]] (Optional) Specifies advanced options for creating hard disks. Accepts only SdrsVMDiskAntiAffinityRule objects. You can define an anti-affinity Storage Distributed Resource Scheduler (SDRS) rule for the disk by specifying a SdrsVMDiskAntiAffinityRule object to the AdvancedOption parameter and this will override any existing SdrsVMDiskAntiAffinityRule for the virtual machine.   The SdrsVMDiskAntiAffinityRule defines a Storage DRS intra-VM anti-affinity rule (VM disk anti-affinity rule). It is only applicable when creating a virtual machine or hard disk on a datastore cluster. An instance of the object is created by invoking its constructor. There are two constructors - "public SdrsVMDiskAntiAffinityRule(param string[] diskIdentifier)" and "public SdrsVMDiskAntiAffinityRule(param HardDisk[] disk)". For the first constructor, "diskIdentifier" can be either the disk key or the index of the disk in the disk array. The specified disks (and the disk to which the rule is applied) are placed in an anti-affinity rule on a DatastoreCluster. Only one such rule is supported per virtual machine. You can pass the instance to the AdvancedOption parameter of the New-VM or New-HardDisk cmdlets.
- -CapacityGB [Decimal] (Optional) Specifies the capacity of the new virtual disk in gigabytes (GB). You need to specify this parameter when you create hard disks of type Flat.
- -CapacityKB [Int64] (Optional) This parameter is obsolete. Use the CapacityGB parameter instead. Specifies the capacity of the new virtual disk in kilobytes (KB). You need to specify this parameter when you create hard disks of type Flat.
- -Controller [ScsiController] (Optional) Specifies a SCSI controller to which you want to attach the new hard disk.
- -Datastore [StorageResource] (Optional) Specifies the datastore where you want to place the new hard disk. If a DatastoreCluster object is passed to the Datastore parameter, the hard disk is added to the DatastoreCluster in an automated SDRS mode. You can define an anti-affinity SDRS rule for the disk by specifying an SdrsVMDiskAntiAffinityRule object to the AdvancedOption parameter and this will override any existing SdrsVMDiskAntiAffinityRule for the virtual machine.
- -DeviceName [String] (Optional) Specifies the host-specific device the Logical Unit Number (LUN) is being accessed through. If the target LUN is not available on the host, then it's empty. For example, this might happen if it is masked out accidentally. Only supported when DiskType is set to "rawVirtual" or "rawPhysical". The device name is visible in the vSphere Client through the new raw hard disk wizard or you can retrieve it by using the PowerCLI views.
- -DiskPath [String] (Required) Specifies the path to the hard disk.
- -DiskType [DiskType] (Optional) Specifies the type of file backing that you want to use. The valid values are rawVirtual, rawPhysical, flat, PMem, and unknown. If the hard disk is attached to no virtual machine, the value of the DiskType parameter might be Unknown, which means that no type is specified.
- -Persistence [String] (Optional) Specifies the disk persistence mode. The valid values are Persistent, NonPersistent, IndependentPersistent, IndependentNonPersistent, and Undoable. This parameter is supported only when the disk type is set to "rawVirtual" or "flat". The 'NonPersistent' and 'Undoable' values are deprecated and scheduled for removal. Their use is not recommended because they do not work with snapshots and are not supported on ESX 3.5 and later.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Split [SwitchParameter] (Optional) This parameter is deprecated and scheduled for removal. Use the StorageFormat parameter instead. Specifies the type of the virtual disk file - split or monolithic. If the value is $true, the virtual disk is stored in multiple files, each 2 sGB. If the value is $false, the virtual disk is stored in a single file. This parameter is supported only if the DiskType parameter is set to "flat".
- -StorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the storage format of the new hard disk. This parameter accepts Thin, Thick, and EagerZeroedThick values.
- -ThinProvisioned [SwitchParameter] (Optional) This parameter is deprecated and scheduled for removal. Use the StorageFormat parameter instead. Indicates to the underlying file system that the virtual disk backing file should be allocated lazily (using thin provisioning). This parameter is only used for file systems that support configuring the provisioning policy on a per file basis, such as VMFS3. This parameter is supported only if the DiskType parameter is set to "flat".
- -VDisk [VDisk] (Required) Specifies the VDisk object that you want to attach to the virtual machine.
- -VM [VirtualMachine] (Required) Specifies the virtual machine to which you want to add the new disk. Passing multiple values to this parameter is obsolete.
- -StoragePolicy [StoragePolicy] (Optional) Specifies the storage policy that you want to attach to the new disk. If the storage policy is a PMem policy, the new disk is created in the PMem datastore of the virtual machine host. If the storage policy is an encryption policy, the new disk is encrypted. If the storage policy is a non-encryption policy, the policy is attached to the new disk.
- -KeyProvider [KeyProvider] (Optional) Specifies the key provider that you want to use for the encryption key while creating the new hard disk. If the StoragePolicy parameter is not specified, the default encryption storage policy "VM Encryption Policy" is used.

**Examples:**

```powershell
$vm = Get-VM VM

$vm | New-HardDisk -CapacityGB 100 -Persistence persistent
```
_Adds a new hard disk to the VM virtual machine in a persistent mode with capacity of 100 GB._

```powershell
$deviceName = ($vmhost | Get-ScsiLun | Where {$_.CanonicalName -match "naa"})[0].ConsoleDeviceName

New-HardDisk -VM $vm -DiskType RawPhysical -DeviceName $deviceName
```
_Obtains a valid device name for Raw Disk Mapping. Then the command creates an RDM hard disk for the specified virtual machine with the obtained device name._

```powershell
New-HardDisk -VM $vm -CapacityGB 100 -Persistence IndependentNonPersistent
```
_Creates a non-persistent hard disk with the specified capacity._

### `New-ResourcePool`

**This cmdlet creates a new resource pool.**

This cmdlet creates a new resource pool with the provided inputs on the location that is specified by the Location parameter.

**Parameters:**

- -CpuExpandableReservation [Boolean] (Optional) Indicates that the CPU reservation can grow beyond the specified value if the parent resource pool has unreserved resources.
- -CpuLimitMhz [Int64] (Optional) Specifies a CPU usage limit in MHz. Utilization will not exceed this limit even if there are available resources.
- -CpuReservationMhz [Int64] (Optional) Specifies the CPU size in MHz that is guaranteed to be available.
- -CpuSharesLevel [SharesLevel] (Optional) Specifies the CPU allocation level for this pool. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal.
- -Location [VIContainer] (Required) Specifies a container object (ResourcePool, Cluster, or VMHost) where you want to place the new resource pool. If a host or a cluster is specified for the Location parameter, the resource pool is created in the "Resources" resource pool. The "Resources" resource pool is a system resource pool and is guaranteed to exist.
- -MemExpandableReservation [Boolean] (Optional) If the value is $true, the memory reservation can grow beyond the specified value if the parent resource pool has unreserved resources.
- -MemLimitGB [Decimal] (Optional) Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemLimitMB [Int64] (Optional) This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemReservationGB [Decimal] (Optional) Specifies the guaranteed available memory in gigabytes (GB).
- -MemReservationMB [Int64] (Optional) This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB).
- -MemSharesLevel [SharesLevel] (Optional) Specifies the memory allocation level for this pool. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal.
- -Name [String] (Required) Specifies a name for the new resource pool.
- -NumCpuShares [Int32] (Optional) Specifies the CPU allocation level for this pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless the CpuSharesLevel parameter is set to Custom.
- -NumMemShares [Int32] (Optional) Specifies the memory allocation level for this pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless the MemSharesLevel parameter is set to Custom.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$resourcepool1 = Get-ResourcePool -Location Cluster -Name ResourcePool1

New-ResourcePool -Location $resourcepool1 -Name ResourcePool2 -CpuExpandableReservation $true -CpuReservationMhz 500 -CpuSharesLevel high -MemExpandableReservation $true -MemReservationGB 5 -MemSharesLevel high
```
_Creates a new resource pool named ResourcePool2 in the cluster's root resource pool ResourcePool1._

### `New-VIInventoryDrive`

**This function creates a new drive for an inventory item.**

This function creates a new inventory drive that is mapped to a location in a datastore.

**Parameters:**

- -Name [String] (Optional) Specifies the name of the new inventory drive.
- -Location [Object] (Optional) Specifies the vSphere container objects (such as folders, data centers, and clusters) for which you want to create the drive.

## Remove

### `Remove-Cluster`

**This cmdlet deletes the specified clusters.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$cluster =  New-Cluster -Name Cluster -Location Datacenter

Remove-Cluster $cluster -Confirm:$false
```
_Creates and then removes, without asking for user confirmation, the Custer cluster on the Datacenter datacenter._

### `Remove-Datacenter`

**This cmdlet removes the specified datacenters from their locations.**

This cmdlet removes the specified datacenters and their children objects from their locations.

**Parameters:**

- -Datacenter [Datacenter[]] (Required) Specifies the datacenters you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-Datacenter Datacenter
```
_Removes the Datacenter datacenter._

```powershell
$task = Remove-Datacenter Datacenter -RunAsync
```
_Asynchronously removes Datacenter08._

### `Remove-DrsClusterGroup`

**This cmdlet removes the specified DRS cluster groups from the cluster on which it resides.**

**Parameters:**

- -DrsClusterGroup [DrsClusterGroup[]] (Required) Specifies the DRS cluster groups you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-DrsClusterGroup -DrsClusterGroup "MyClusterGroup"
```
_Removes the "MyClusterGroup" DRS cluster group from the environment._

### `Remove-DrsRule`

**This cmdlet removes the specified DRS rules.**

**Parameters:**

- -Rule [DrsRule[]] (Required) Specifies the DRS rules you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.

**Examples:**

```powershell
$rules = Get-DrsRule -Cluster $cluster -Name "*Rule1*"

Remove-DrsRule $rules -Confirm:$false
```
_Removes the DRS rules for the $cluster cluster, whose names contain "Rule1"._

### `Remove-Folder`

**This cmdlet removes the specified folders from their locations.**

This cmdlet removes the specified folders and their children objects from their locations.

**Parameters:**

- -DeletePermanently [SwitchParameter] (Optional) Indicates that you want to delete from the disk any virtual machines contained in the specified folder, and not only to remove them from the inventory. This parameter is supported only for VirtualMachine folders.
- -Folder [Folder[]] (Required) Specifies the folders you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-Folder -Folder "testFolder"
```
_Removes a folder by name._

```powershell
Get-Folder -Name "testFolder" | Remove-Folder
```
_Removes a folder by object._

```powershell
Get-Folder -Name "testFolder" | Remove-Folder -DeletePermanently
```
_Permanently removes a folder._

### `Remove-HardDisk`

**This cmdlet removes the specified virtual hard disks.**

**Parameters:**

- -DeletePermanently [SwitchParameter] (Optional) Indicates that you want to delete the hard disks not only from the inventory, but from the datastore as well.
- -HardDisk [HardDisk[]] (Required) Specifies the hard disks you want to remove.

**Examples:**

```powershell
Get-HardDisk -VM $vm | Remove-HardDisk
```
_Removes the hard disks of the virtual machine stored in the $vm variable._

```powershell
$hdd = Get-HardDisk -VM 'MyVM' -Name 'Hard disk 4'
Remove-HardDisk -HardDisk $hdd
```
_Removes the 'Hard disk 4' hard disk of the 'MyVM' virtual machine._

### `Remove-Inventory`

**This cmdlet removes the specified inventory items from their locations.**

This cmdlet removes the specified inventory items and their children from their locations.

**Parameters:**

- -Item [InventoryItem[]] (Required) Specifies the inventory items you want to remove. This parameter accepts Folder, ResourcePool, Datacenter, VirtualMachine, VMHost, Cluster, Template, and VApp objects.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Folder Folder| Get-Inventory -NoRecursion | Remove-Inventory
```
_Removes all objects from the Folder folder._

### `Remove-ResourcePool`

**This cmdlet removes the specified resource pools from their locations.**

This cmdlet removes the specified resource pools and their children objects from their locations.

**Parameters:**

- -ResourcePool [ResourcePool[]] (Required) Specifies the resource pools you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-ResourcePool -ResourcePool ResourcePool
```
_Removes the resource pool named ResourcePool._

### `Remove-TrustedClusterAttestationServiceInfo`

**This cmdlet removes the attestation services information from the specified trusted cluster in the workload vCenter Server system.**

**Parameters:**

- -AttestationServiceInfo [AttestationServiceInfo[]] (Required) Specifies the attestation services information that you want to remove from the specified trusted cluster.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustedCluster [TrustedCluster] (Required) Specifies the trusted cluster from which you want to remove the attestation service information.

**Examples:**

```powershell
$cluster = Get-TrustedCluster mycluster
Remove-TrustedClusterAttestationServiceInfo -TrustedCluster mycluster -AttestationServiceInfo $cluster.AttestationServiceInfo
```
_Removes the attestation services information configured in the trusted mycluster cluster._

### `Remove-TrustedClusterKeyProviderServiceInfo`

**This cmdlet removes the key provider services information from the specified trusted cluster in the workload vCenter Server system.**

**Parameters:**

- -KeyProviderServiceInfo [KeyProviderServiceInfo[]] (Required) Specifies the key provider services information you want to remove from the specified trusted cluster.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -TrustedCluster [TrustedCluster] (Required) Specifies the trusted cluster from which you want to remove the key provider service information.

**Examples:**

```powershell
$cluster = Get-TrustedCluster mycluster
Remove-TrustedClusterKeyProviderServiceInfo -TrustedCluster mycluster -KeyProviderServiceInfo $cluster.KeyProviderServiceInfo
```
_Removes the key provider services information configured in the trusted mycluster cluster._

## Set

### `Set-Cluster`

**This cmldlet modifies the configuration of a cluster.**

This cmdlet modifies the configuration of a cluster. HAEnabled is automatically set to $true if some of the HA settings, HAAdmissionControlEnabled, HAFailoverLevel, HARestartPriority, or HAIsolationResponse are specified. DrsEnabled is automatically set to $true if some of the DRS settings, DrsAutomationLevel, or DrsMode are specified.

**Parameters:**

- -AcceptEULA [SwitchParameter] (Optional) Indicates that the End User License Agreement (EULA) is accepted for the images that you want to install on the cluster's hosts in order to comply with the target state.
- -BaseImage [BaseImage] (Optional) Specifies the ESXi base image that the cluster's hosts should comply with.
- -Cluster [Cluster[]] (Required) Specifies the name of the cluster you want to configure.
- -Component [Component[]] (Optional) Specifies the ESXi components that the cluster's hosts should comply with.
- -CryptoMode [CryptoMode] (Optional) Specifies the cluster encryption mode you want to configure. When set to OnDemand, hosts in the cluster are not required to be in a cryptographically "Safe" state. When set to ForceEnable, all hosts in the cluster are forced to be cryptographically "Safe", that is, vCenter Server has installed a host key on the host.
- -DepotOverride [String[]] (Optional) Specifies a depot address from where the cluster can fetch metadata and resources for the vSphere Lifecycle Manager operations.
- -DrsAutomationLevel [DrsAutomationLevel] (Optional) Specifies a DRS automation level. The valid values are FullyAutomated, Manual, and PartiallyAutomated.
- -DrsEnabled [Boolean] (Optional) If specified, enables VMware DRS.
- -DrsMode [DrsMode] (Optional) This parameter is deprecated and scheduled for removal. Use the DrsAutomationLevel parameter instead.   Specifies a DRS mode. The valid values are FullyAutomated, Manual, and PartiallyAutomated.
- -EVCMode [String] (Optional) Specifies the EVC mode of the newly created cluster. If not specified or set to $null, EVC is deactivated.
- -FirmwareAddon [Package] (Optional) Specifies a package from a hardware support manager that the hosts on a cluster should comply with. This parameter has been renamed from "Package". A PowerShell alias "Package" for this parameter has been added for backward compatibility of PowerShell scripts.
- -HAAdmissionControlEnabled [Boolean] (Optional) Indicates that the virtual machines in the cluster will not start if they violate availability constraints.
- -HAEnabled [Boolean] (Optional) If specified, enables VMware High Availability.
- -HAFailoverLevel [Int32] (Optional) Specifies a failover level. This is the number of physical host failures that can be tolerated without impacting the ability to meet minimum thresholds for all running virtual machines. The valid values are in the range of 1 to 4.
- -HAIsolationResponse [HAIsolationResponse] (Optional) Specifies whether the virtual machine should be powered off if a host determines that it is isolated from the rest of the compute resource. The valid values are PowerOff and DoNothing. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -HARestartPriority [HARestartPriority] (Optional) Specifies the cluster HA restart priority. The valid values are Disabled, Lowest, Low, Medium, High, and Highest. VMware HA is a feature that detects failed virtual machines and automatically restarts them on alternative ESX/ESXi hosts. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -Name [String] (Optional) Specifies a new name for the cluster.
- -Profile [VMHostProfile] (Optional) Specifies a host profile you want to associate with the cluster. If the value of this parameter is $null, the current profile association is removed.
- -Remediate [SwitchParameter] (Required) Indicates that you want to remediate the cluster's hosts to the target state.
- -RemovedComponent [String[]] (Optional) Specifies a list of components that you want to remove from the base image.   Calling the commandlet with a new value for this parameter overrides any previously configured value. It does not add new components to the list of removed ones. To reset the list of removed components provide an empty array to this parameter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VendorAddOn [AddOn] (Optional) Specifies the ESXi vendor add-on that the cluster's hosts should comply with.
- -VMSwapfilePolicy [VMSwapfilePolicy] (Optional) Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore specified by the VMSwapfileDatastoreID property of the virtual machine host. If the VMSwapfileDatastoreID property is not set or indicates a datastore with insufficient free space, the swapfile is stored in the same directory as the virtual machine. This setting might degrade the vMotion performance.     WithVM - stores the swapfile in the same directory as the virtual machine.
- -VsanDiskClaimMode [VsanDiskClaimMode] (Optional) Specifies the mode by which disks are claimed by vSAN.
- -VsanEnabled [Boolean] (Optional) Specifies whether the vSAN feature is enabled on this cluster.
- -VsanEsaEnabled [Boolean] (Optional) Indicates that the vSAN ESA feature is enabled on this cluster. This feature is supported from vSphere 8.0.

**Examples:**

```powershell
Get-Cluster -Name "MyClusterName" | Set-Cluster -Name "NewClusterName" -HAEnabled:$true -HAAdmissionControlEnabled:$true -HAFailoverLevel 2 -VMSwapfilePolicy "InHostDatastore" -HARestartPriority "Low" -HAIsolationResponse "PowerOff"
```
_Renames the "MyClusterName" cluster to "NewClusterName" and changes its VMware High Availability (HA) settings._

```powershell
Set-Cluster -Cluster "MyClusterName" -DRSEnabled:$true -DRSAutomationLevel "Manual"
```
_Changes the VMware Distributed Resource Scheduler (DRS) settings of the "MyClusterName" cluster._

```powershell
Set-Cluster -Cluster "MyClusterName" -EVCMode "intel-nehalem"
```
_Changes the VMware Enhanced vMotion Compatibility (EVC) settings of the "MyClusterName" cluster._

### `Set-Datacenter`

**This cmdlet modifies the properties of the specified datacenter.**

**Parameters:**

- -Datacenter [Datacenter[]] (Required) Specifies the datacenter whose properties you want to modify.
- -Name [String] (Required) Specifies a new name for the datacenter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-Datacenter -Datacenter Datacenter1 -Name Datacenter2
```
_Renames the Datacenter1 to Datacenter2._

### `Set-DrsClusterGroup`

**This cmdlet adds or removes either virtual machines or VM hosts to or from the specified DRS cluster group, depending on the used parameter set.**

This cmdlet adds or removes either virtual machines or VM hosts to or from the specified DRS cluster group, depending on the used parameter set. You must either specify the Add or Remove parameter for both parameter sets. If not specified, you receive a terminating error.

**Parameters:**

- -Add [SwitchParameter] (Optional) Specifies that you want to add virtual machines or VM hosts to the DRS cluster group.
- -DrsClusterGroup [DrsClusterGroup] (Required) Specifies the DRS cluster group you want to modify.
- -Remove [SwitchParameter] (Optional) Specifies that you want to remove virtual machines or VM hosts from the DRS cluster group.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines which you want to add or remove to or from the specified DRS cluster group.
- -VMHost [VMHost[]] (Required) Specifies the VM hosts which you want to add or remove to or from the specified DRS cluster group.

**Examples:**

```powershell
$vm = Get-VM "MyVM"
Get-DrsClusterGroup "MyClusterGroup" | Set-DrsClusterGroup -VM $vm -Add
```
_Adds the "MyVM" virtual machine to the "MyClusterGroup" DRS cluster group by using a pipeline._

```powershell
$vmhost = Get-VMHost "MyVMHost"
Get-DrsClusterGroup "MyClusterGroup" | Set-DrsClusterGroup -VMHost $vmhost -Remove
```
_Removes the "MyVMHost" VM host from the "MyClusterGroup" DRS cluster group by using a pipeline._

### `Set-DrsRule`

**This cmdlet modifies an existing DRS rule.**

This cmdlet modifies an existing DRS rule. Each rule defines the virtual machines that can run on the same host (affinity rule) or must run on different hosts (anti-affinity rule).

**Parameters:**

- -Enabled [Boolean] (Optional) Indicates that the DRS rule is enabled.
- -Name [String] (Optional) Specifies a new name for the DRS rule.
- -Rule [DrsRule[]] (Required) Specifies the DRS rule you want to modify.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines that can be referenced by the new DRS rule.

**Examples:**

```powershell
$vm = Get-VM DrsRuleVM1*

Set-DrsRule -Rule $affinityRule -VM $vm -Enabled $true;
```
_Updates the list of virtual machines that might be referenced by the DRS rule stored in the $affinityRule  variable and enables the rule._

### `Set-Folder`

**This cmdlet modifies the properties of the specified folder.**

**Parameters:**

- -Folder [Folder[]] (Required) Specifies the folder whose properties you want to change.
- -Name [String] (Required) Specifies a new name for the folder.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Folder -Name "testFolder" | Set-Folder -Name "NewFolderName"
```
_Renames the "testFolder" folder to "NewFolderName"._

### `Set-HardDisk`

**This cmdlet modifies the properties of the specified virtual hard disk.**

This cmdlet modifies the properties of the specified virtual hard disk. You can encrypt the specified virtual hard disk or decrypt the specified virtual hard disk. You can also change the size and the persistence type, and inflate or expand the specified virtual hard disk. Do not use the Inflate parameter at the same time with the Persistence and CapacityGB parameters. If you use a helper virtual machine, all virtual machines associated with the disk and the helper virtual machine should be powered off before expanding the disk. When you resize more than one disk by using a helper virtual machine, the disks are resized one by one causing the helper machine to power on and off for each virtual machine. This might slow the cmdlet performance. For a list of supported operating systems, see the VMware PowerCLI User's Guide.

**Parameters:**

- -CapacityGB [Decimal] (Optional) Specifies the updated capacity of the virtual disk in gigabytes (GB). If you are connected to a vCenter Server 2.0 or ESX 3.0, the size of the disk cannot be changed and the CapacityGB parameter is discarded. If you are connected to a vCenter Server 2.5 or ESX 3.5, the size of the disk can only be increased and the CapacityGB parameter is discarded if its value is less than the current disk size.
- -CapacityKB [Int64] (Optional) This parameter is obsolete. Use CapacityGB instead. Specifies the updated capacity of the virtual disk in kilobytes (KB). If you are connected to a vCenter Server 2.0 or ESX 3.0 server, the size of the disk cannot be changed and the CapacityKB parameter is discarded. If you are connected to a vCenter Server 2.5 or ESX 3.5 server, the size of the disk can only be increased and the CapacityKB parameter is discarded if its value is less than the current disk size.
- -Controller [ScsiController] (Optional) Specifies a SCSI controller to which you want to attach the hard disk.
- -Datastore [Datastore] (Optional) Specifies the datastore to which you want to move the specified hard disk. Moving a hard disk attached to a virtual machine to a different datastore is only supported on vCenter Server.
- -GuestCredential [PSCredential] (Optional) Specifies the PSCredential object that contains the credentials you want to use for authenticating with the guest operating system.
- -GuestPassword [SecureString] (Optional) Specifies the password you want to use for authenticating with the guest operating system.
- -GuestUser [String] (Optional) Specifies the username you want to use for authenticating with the guest operating system.
- -HardDisk [HardDisk[]] (Required) Specifies the virtual hard disk you want to configure.
- -HelperVM [VirtualMachine] (Optional) Specifies a helper virtual machine you want to use when expanding a Windows virtual machine system disk. LVM (logical volume manager) for Linux is not supported and Linux guest system disks cannot be expanded. When you use a helper virtual machine, all virtual machines associated with the disk and the helper virtual machine must be powered off before expanding the disk. When you resize more than one disks using a helper virtual machine, the disks are resized one by one causing the helper machine to power on and off for each virtual machine, and this might slow down the cmdlet's performance.
- -HostCredential [PSCredential] (Optional) Specifies the PSCredential object that contains the credentials you want to use for authenticating with the host.
- -HostPassword [SecureString] (Optional) Specifies the password you want to use for authenticating with the host.
- -HostUser [String] (Optional) Specifies the user name you want to use for authenticating with the host.
- -Inflate [SwitchParameter] (Optional) Indicates that you want to inflate the hard disk.
- -Partition [String] (Optional) Specifies the partitions you want to resize. On Windows, you can specify which partition you want to resize by using the Partition parameter. If you do not specify a partition, the last partition of the disk is resized. On Linux, you can expand only the last partition.   Resizing guest partitions is supported only for Windows OS and for ext3 partitions on RHEL 5. It is achieved by scripts, provided with the VMware PowerCLI installation. You can modify these scripts or add new ones to support operating systems different than Windows and RHEL 5, and more specific disk resizing scenarios. The scripts are located in the "Scripts" folder in the PowerCLI installation directory and their names have the following format:   GuestDiskExpansion_<OS_Identifier>   <OS_Identifier> is the guest family or the guest ID (as returned by Get-VMGuest).   If no partition is specified, the last partition of the hard disk is resized.
- -Persistence [String] (Optional) Specifies the disk persistence mode. The valid values are Persistent, NonPersistent, IndependentPersistent, IndependentNonPersistent, and Undoable. This parameter is supported only when the disk type is rawVirtual or flat. The NonPersistent and Undoable values are deprecated and scheduled for removal. These values do not work with snapshots and are not supported on ESXi 3.5 and later.
- -ResizeGuestPartition [SwitchParameter] (Optional) Note: This functionality is deprecated and is not functional on the currently supported guest operating systems. Resizing guest disks works only on Windows XP Service Pack 3 and Red Hat Enterprise Linux 5.   Indicates that you want to resize the guest partition of the disk. To use this feature, VMware Tools must run on the virtual machine. On Windows, you can specify which partition you want to resize by using the Partition parameter. If you don't specify a partition, the last partition of the disk is resized. On Linux, you can expand only the last partition.   Resizing guest partitions is supported only for Windows OS and for ext3 partitions on RHEL 5. It is achieved by scripts, provided with the VMware PowerCLI installation. You can modify these scripts or add new ones to support operating systems different than Windows and RHEL 5, and more specific disk resizing scenarios. The scripts are located in the "Scripts" folder in the PowerCLI installation directory and their names have the following format:   GuestDiskExpansion_<OS_Identifier>   <OS_Identifier> is the guest family or the guest ID (as returned by Get-VMGuest).
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the storage format of the relocated hard disk. This parameter is applicable only when moving a virtual machine disk to a different datastore by using the Datastore parameter. This parameter accepts Thin, Thick, and EagerZeroedThick values.
- -ToolsWaitSecs [Int32] (Optional) Specifies the time in seconds to wait for a response from VMware Tools. If a non-positive value is provided, the system waits an infinitely long time.
- -ZeroOut [SwitchParameter] (Optional) Specifies that you want to fill the hard disk with zeros. This parameter is supported only if you are directly connected to an ESX/ESXi host.
- -DisableEncryption [SwitchParameter] (Required) Indicates that the cmdlet decrypts the specified hard disk.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -StoragePolicy [StoragePolicy] (Optional) Specifies the StoragePolicy that you want to attach to the specified hard disk. If the storage policy is an encryption policy, the hard disk is encrypted.
- -KeyProvider [KeyProvider] (Optional) Specifies the key provider that you want to use for the encryption key while encrypting the specified hard disk. If StoragePolicy is not specified, the default encryption storage policy "VM Encryption Policy" is used.

**Examples:**

```powershell
Get-HardDisk -VM $vm | Set-HardDisk -Persistence "IndependentNonPersistent"
```
_Changes the persistence of a hard disk to IndependentNonPersistent._

```powershell
Set-HardDisk -HardDisk $harddisk -CapacityGB $extendedCapacity -GuestCredential $guestCred
```
_Extends a hard disk with the specified capacity. The command also extends the disk on the guest operating system._

```powershell
Set-HardDisk -HardDisk $harddisk -Datastore $datastore
```
_Moves the hard disk to the specified datastore._

### `Set-ResourcePool`

**This cmdlet modifies the properties of the specified resource pool.**

**Parameters:**

- -CpuExpandableReservation [Boolean] (Optional) Indicates that the CPU reservation can grow beyond the specified value if the parent resource pool has unreserved resources.
- -CpuLimitMhz [Int64] (Optional) Specifies a CPU usage limit in MHz. If this parameter is set, utilization will not exceed this limit even if there are available resources.
- -CpuReservationMhz [Int64] (Optional) Specifies the guaranteed available CPU in MHz.
- -CpuSharesLevel [SharesLevel] (Optional) Specifies the CPU allocation level for this pool. This property is used in relative allocation between resource consumers. This parameter accepts Custom, High, Low, and Normal values.
- -MemExpandableReservation [Boolean] (Optional) Indicates that the memory reservation can grow beyond the specified value if the parent resource pool has unreserved resources.
- -MemLimitGB [Decimal] (Optional) Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemLimitMB [Int64] (Optional) This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemReservationGB [Decimal] (Optional) Specifies the guaranteed available memory in gigabytes (GB).
- -MemReservationMB [Int64] (Optional) This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB).
- -MemSharesLevel [SharesLevel] (Optional) Specifies the memory allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter accepts Custom, High, Low, and Normal values.
- -Name [String] (Optional) Specifies a new name for the resource pool.
- -NumCpuShares [Int32] (Optional) Specifies the CPU allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless CpuSharesLevel is set to Custom.
- -NumMemShares [Int32] (Optional) Specifies the memory allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless MemSharesLevel is set to Custom.
- -ResourcePool [ResourcePool[]] (Required) Specifies the resource pool you want to configure.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-ResourcePool -Resourcepool Resourcepool -NumCpuShares  512 -MemLimitGB 4
```
_Sets the CPU allocation level and the limit on memory usage in GB for the resource pool named Resourcepool._

### `Set-TrustAuthorityCluster`

**This cmdlet modifies the configuration of the specified Trust Authority clusters in the Trust Authority vCenter Server system.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -State [TrustAuthorityState] (Required) Specifies the state in which you want to modify the specified Trust Authority clusters.
- -TrustAuthorityCluster [TrustAuthorityCluster[]] (Required) Specifies the Trust Authority clusters that you want to modify.

**Examples:**

```powershell
Set-TrustAuthorityCluster -TrustAuthorityCluster mycluster -State Enabled
```
_Enables the Trust Authority cluster mycluster._

### `Set-TrustedCluster`

**This cmdlet modifies the configuration of the trusted clusters in the workload vCenter Server system.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -State [TrustedState] (Required) Specifies the state in which you want to update the specified trusted clusters.   If you specify Enabled, the cmdlet will push all the ServiceInfos, including the AttestationServiceInfos and the KeyProviderServiceInfos configured in the vCenter Server system, to the specified trusted clusters. However, if there are no AttestationServiceInfos configured in the vCenter Server system, the cmdlet will fail. If you specify Disabled, the cmdlet will clear all the ServiceInfos configured in the specified trusted clusters.   Note: In vCenter Server 7.0 Update 1 and later, a warning message appears if the given trusted cluster is unhealthy in the TrustedClusterAppliedStatus. This cmdlet remediates it automatically.
- -TrustedCluster [TrustedCluster[]] (Required) Specifies the trusted clusters you want to update.
- -Remediate [SwitchParameter] (Required) Indicates that you want to remediate the given trusted cluster to make the applied status healthy. Note: This parameter is only available for the vCenter Server system 7.0 Update 1 and later.

**Examples:**

```powershell
Set-TrustedCluster -TrustedCluster mycluster -State Enabled
```
_Copies the attestation service information and key provider service information from the workload vCenter Server system to the specified mycluster trusted cluster._

```powershell
Set-TrustedCluster -TrustedCluster mycluster -Remediate
```
_Remedites the mycluster trusted cluster. All trusted services on all virtual machine hosts in the mycluster trusted cluster become consistent with the desired state of the mycluster trusted cluster._

### `Set-VDTrafficShapingPolicy`

**This cmdlet modifies the traffic shaping policy for distributed ports.**

This cmdlet modifies the traffic shaping policy for distributed ports  or the default port policy at port group or switch level (depending on the input policy).

**Parameters:**

- -AverageBandwidth [Int64] (Optional) Specifies the average bandwidth of the traffic shaping policy for the corresponding distributed port, port group, or switch. The value is in bits per second.
- -AverageBandwidthInherited [Boolean] (Optional) Specifies whether the AverageBandwidth setting is inherited from a parent object, such as a distributed port group or switch.
- -BurstSize [Int64] (Optional) Specifies the burst size of the traffic shaping policy for the corresponding distributed port, port group, or switch. The value is in bits per second.
- -BurstSizeInherited [Boolean] (Optional) Specifies whether the BurstSize setting is inherited from a parent object, such as a distributed port group or switch.
- -Enabled [Boolean] (Optional) Specifies whether traffic shaping is enabled for the corresponding distributed port, port group, or switch.
- -EnabledInherited [Boolean] (Optional) Specifies whether the Enabled setting is inherited from a parent object, such as a distributed port group or switch.
- -PeakBandwidth [Int64] (Optional) Specifies the peak bandwidth of the traffic shaping policy for the corresponding distributed port, port group, or switch. The value is in bits per second.
- -PeakBandwidthInherited [Boolean] (Optional) Specifies whether the PeakBandwidth setting is inherited from a parent object, such as a distributed port group or switch.
- -Policy [TrafficShapingPolicy[]] (Required) Specifies the traffic shaping policy that you want to configure.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDPortgroup "MyVDPortgroup" | Get-VDPort -Key 4| Get-VDTrafficShapingPolicy -Direction In | Set-VDTrafficShapingPolicy -Enabled $true -AverageBandwidth 100000
```
_Enables traffic shaping for a specific port in a distributed port group named "MyVDPortgroup" and updates the average bandwidth settings in their traffic shaping policies._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDTrafficShapingPolicy | Set-VDTrafficShapingPolicy -BurstSizeInherited
```
_Retrieves a distributed port group named "MyVDPortgroup" and updates its traffic shaping policy by inheriting the burst size from its corresponding parent._

## Test

### `Test-LcmClusterCompliance`

**This cmdlet tests cluster's hosts compliance respective to its target state.**

This cmdlet tests cluster's hosts compliance respective to its target state. You can test the specified cluster's hosts for compliance with the cluster's vSphere Lifecycle Manager desired state.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies a cluster whose hosts compliance to be tested against custer's vSphere Lifecycle Manager desired state.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.`
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Test-LcmClusterCompliance -Cluster Cluster
```
_Tests the cluster's hosts compliance respective to its target state._

### `Test-LcmClusterHealth`

**This cmdlet tests cluster's hosts health respective to its target state.**

This cmdlet tests cluster's hosts health respective to its target state. The specified cluster's hosts health is tested with the cluster's vSphere Lifecycle Manager desired state.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies a cluster whose hosts health you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Test-LcmClusterHealth -Cluster Cluster
```
_Tests the cluster's hosts health respective to its target state._

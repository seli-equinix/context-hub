---
name: powercli-cluster
description: "VMware PowerCLI 13.3 — cluster management: DRS, HA, resource pools, datacenter, folder"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Apply-DrsRecommendation,Export-LcmClusterDesiredState,Get-Cluster,Get-Datacenter,Get-DrsClusterGroup,Get-DrsRecommendation,Get-DrsRule,Get-Folder,Get-Inventory,Get-LcmClusterDesiredStateRecommendation,Get-ResourcePool,Import-LcmClusterDesiredState,Invoke-DrsRecommendation,Move-Cluster,Move-Datacenter,Move-Folder,Move-Inventory,Move-ResourcePool,New-Cluster,New-Datacenter,New-DrsClusterGroup,New-DrsRule,New-Folder,New-ResourcePool,New-VIInventoryDrive,Remove-Cluster,Remove-Datacenter,Remove-DrsClusterGroup,Remove-DrsRule,Remove-Folder,Remove-Inventory,Remove-ResourcePool,Set-Cluster,Set-Datacenter,Set-DrsClusterGroup,Set-DrsRule,Set-Folder,Set-ResourcePool,Test-LcmClusterCompliance,Test-LcmClusterHealth"
---

# VMware PowerCLI — cluster management

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Apply-DrsRecommendation` | This cmdlet applies the specified DRS recommendations. |
| `Export-LcmClusterDesiredState` | This cmdlet exports the desired state of a vSphere Lifecycle Manager cluster. |
| `Get-Cluster` | This cmdlet retrieves the clusters available on a vCenter Server system. |
| `Get-Datacenter` | This cmdlet retrieves the datacenters available on a vCenter Server system. |
| `Get-DrsClusterGroup` | This cmdlet retrieves DRS cluster groups for the specified cluster, VM, or VM host. |
| `Get-DrsRecommendation` | This cmdlet retrieves the available DRS recommendations from the provided clusters. |
| `Get-DrsRule` | This cmdlet retrieves the list of DRS rules for the specified clusters. |
| `Get-Folder` | This cmdlet retrieves the folders available on a vCenter Server system. |
| `Get-Inventory` | This cmdlet retrieves the inventory items available on a vCenter Server system. |
| `Get-LcmClusterDesiredStateRecommendation` | This cmdlet generates a desired state recommendation of a vSphere Lifecycle Manager cluster. |
| `Get-ResourcePool` | This cmdlet retrieves the resource pools available on a vCenter Server system. |
| `Import-LcmClusterDesiredState` | This cmdlet imports a specification file to set a desired state of a vSphere Lifecycle Manager cl... |
| `Invoke-DrsRecommendation` | This cmdlet applies the specified DRS recommendations. |
| `Move-Cluster` | This cmdlet moves a vCenter Server cluster from one location to another. |
| `Move-Datacenter` | This cmdlet moves a vCenter Server datacenter from one location to another. |
| `Move-Folder` | This cmdlet moves a vCenter Server folder from one location to another. |
| `Move-Inventory` | This cmdlet moves a vCenter Server inventory item from one location to another. |
| `Move-ResourcePool` | This cmdlet moves a resource pool from one location to another. |
| `New-Cluster` | This cmdlet creates a new cluster. |
| `New-Datacenter` | This cmdlet creates a new datacenter. |
| `New-DrsClusterGroup` | This cmdlet creates either a VM or VM host DRS cluster group, depending on the used parameter set. |
| `New-DrsRule` | This cmdlet creates a new DRS rule. |
| `New-Folder` | This cmdlet creates a new folder on a vCenter Server system. |
| `New-ResourcePool` | This cmdlet creates a new resource pool. |
| `New-VIInventoryDrive` | This function creates a new drive for an inventory item. |
| `Remove-Cluster` | This cmdlet deletes the specified clusters. |
| `Remove-Datacenter` | This cmdlet removes the specified datacenters from their locations. |
| `Remove-DrsClusterGroup` | This cmdlet removes the specified DRS cluster groups from the cluster on which it resides. |
| `Remove-DrsRule` | This cmdlet removes the specified DRS rules. |
| `Remove-Folder` | This cmdlet removes the specified folders from their locations. |
| `Remove-Inventory` | This cmdlet removes the specified inventory items from their locations. |
| `Remove-ResourcePool` | This cmdlet removes the specified resource pools from their locations. |
| `Set-Cluster` | This cmldlet modifies the configuration of a cluster. |
| `Set-Datacenter` | This cmdlet modifies the properties of the specified datacenter. |
| `Set-DrsClusterGroup` | This cmdlet adds or removes either virtual machines or VM hosts to or from the specified DRS clus... |
| `Set-DrsRule` | This cmdlet modifies an existing DRS rule. |
| `Set-Folder` | This cmdlet modifies the properties of the specified folder. |
| `Set-ResourcePool` | This cmdlet modifies the properties of the specified resource pool. |
| `Test-LcmClusterCompliance` | This cmdlet tests cluster's hosts compliance respective to its target state. |
| `Test-LcmClusterHealth` | This cmdlet tests cluster's hosts health respective to its target state. |

---

### Apply-DrsRecommendation

This cmdlet applies the specified DRS recommendations.

**Returns**: `None`

```
Apply-DrsRecommendation
    -DrsRecommendation <DrsRecommendation[]>
    [-RunAsync]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DrsRecommendation` | `DrsRecommendation[]` | Yes | Specifies the DRS recommendations you want to apply. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Export-LcmClusterDesiredState

This cmdlet exports the desired state of a vSphere Lifecycle Manager cluster.

This cmdlet exports the desired state of a vSphere Lifecycle Manager cluster as a JSON metadata file, as an installable ISO image, or as a ZIP offline bundle. The exported files can be imported in other clusters managed by vSphere Lifecycle Manager.

**Returns**: `System.IO.FileInfo`

```
Export-LcmClusterDesiredState
    -Cluster <Cluster[]>
    [-Confirm]
    [-Destination <String>]
    [-ExportIsoImage]
    [-ExportOfflineBundle]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the name of the cluster whose desired state you want to export. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Destination` | `String` | No | Specifies a local directory where you want to save the JSON metadata file, the installable ISO image, or the ZIP offline bundle.   Note: If no value is provided, your current directory will be used. |
| `-ExportIsoImage` | `SwitchParameter` | No | Specifies whether to export the ESXi base image as an installable ISO image. |
| `-ExportOfflineBundle` | `SwitchParameter` | No | Specifies whether to export an offline ZIP bundle containing all software packages that can be imported into the vSphere Lifecycle Manager depot. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-Cluster

This cmdlet retrieves the clusters available on a vCenter Server system.

This cmdlet retrieves the clusters available on a vCenter Server system. Returns a set of clusters that correspond to the filter criteria defined by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `Cluster`

```
Get-Cluster
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    -RelatedObject <ClusterRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the clusters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string... |
| `-Location` | `VIContainer[]` | No | Specifies vSphere container objects (such as folders, datacenters, and clusters) you want to search for clusters. |
| `-Name` | `String[]` | No | Specifies the names of the clusters you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-RelatedObject` | `ClusterRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more Cluster objects that are related to them. This parameter accepts OMResource objects. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the clusters that are associated with any of the specified tags. |
| `-VM` | `VirtualMachine[]` | No | Specifies virtual machines to filter the clusters that contain at least one of them. |
| `-VMHost` | `VMHost[]` | No | Specifies hosts to filter the clusters that contain at least one of them. |

---

### Get-Datacenter

This cmdlet retrieves the datacenters available on a vCenter Server system.

This cmdlet retrieves the datacenters available on a vCenter Server system. Returns a set of datacenters that correspond to the filter criteria defined by the cmdlet parameters. By default, the cmdlet searches recursively from any provided starting point. In this case, if the location is not explicitly specified, the search includes the root folder and all other inventory items on the root folder level. If the command runs with the NoRecursion parameter set to $true, and the location is not s...

**Returns**: `Datacenter`

```
Get-Datacenter
    [-Cluster <Cluster[]>]
    -Id <String[]>
    [-Location <Folder[]>]
    [-Name <String[]>]
    [-NoRecursion]
    -RelatedObject <DatacenterRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | No | Specifies clusters to filter the datacenters that contain at least one of them. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the datacenters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the str... |
| `-Location` | `Folder[]` | No | Specifies vSphere container objects (such as folders) you want to search for datacenters. |
| `-Name` | `String[]` | No | Specifies the names of the datacenters you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-RelatedObject` | `DatacenterRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more Datacenter objects that are related to them. This parameter accepts OMResource objects. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the datacenters that are associated with any of the specified tags. |
| `-VM` | `VirtualMachine[]` | No | Specifies virtual machines to filter the datacenters that contain at least one of them. |
| `-VMHost` | `VMHost[]` | No | Specifies hosts to filter the datacenters that contain at least one of them. |

---

### Get-DrsClusterGroup

This cmdlet retrieves DRS cluster groups for the specified cluster, VM, or VM host.

**Returns**: `DrsClusterGroup`

```
Get-DrsClusterGroup
    [-Cluster <Cluster[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Type <DrsClusterGroupType>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | No | Specifies the clusters for which you want to retrieve the DRS cluster groups. |
| `-Name` | `String[]` | No | Specifies the names of the DRS cluster groups you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `DrsClusterGroupType` | No | Specifies the type of DRS cluster groups you want to retrieve. This parameter accepts VMGroup, VMHostGroup, and All values. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines for which you want to retrieve DRS cluster groups. |
| `-VMHost` | `VMHost[]` | No | Specifies the VM hosts for which you want to retrieve DRS cluster groups. |

---

### Get-DrsRecommendation

This cmdlet retrieves the available DRS recommendations from the provided clusters.

**Returns**: `DrsRecommendation`

```
Get-DrsRecommendation
    [-Cluster <Cluster[]>]
    [-Priority <Int32[]>]
    [-Refresh]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | No | Specifies the clusters whose DRS recommendations you want to retrieve. |
| `-Priority` | `Int32[]` | No | Specifies the priority of the DRS recommendations you want to retrieve. The valid values range from 1 to 5. |
| `-Refresh` | `SwitchParameter` | No | Indicates that you want the cmdlet to refresh the information about the DRS recommendations before retrieving it. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-DrsRule

This cmdlet retrieves the list of DRS rules for the specified clusters.

This cmdlet retrieves the list of DRS rules for the specified clusters. Each rule defines the virtual machines that can run on the same host (affinity rule) or must run on different hosts (anti-affinity).

**Returns**: `DrsRule`

```
Get-DrsRule
    -Cluster <Cluster[]>
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Type <ResourceSchedulingRuleType[]>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the clusters for which you want to retrieve the DRS rules. |
| `-Name` | `String[]` | No | Specifies the name of the DRS rule you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `ResourceSchedulingRuleType[]` | No | Specifies the type of DRS rules you want to retrieve. This parameter accepts VMAntiAffinity, VMAffinity, and VMHostAffinity values. You cannot set this parameter, when the VMHost parameter is speci... |
| `-VM` | `VirtualMachine[]` | No | Specifies virtual machines to filter the DRS rules that reference them. Passing values to this parameter through a pipeline is deprecated and will be removed in a future release. |
| `-VMHost` | `VMHost[]` | No | Specifies VM hosts to filter the DRS rules that reference them. When this parameter is specified, the cmdlet returns only VMHostAffinity rules. You cannot set this parameter, when the Type paramete... |

---

### Get-Folder

This cmdlet retrieves the folders available on a vCenter Server system.

This cmdlet retrieves the folders available on a vCenter Server system. The cmdlet returns a set of folders that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `Folder`

```
Get-Folder
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    -RelatedObject <FolderRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
    [-Type <FolderType[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the folders you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string ... |
| `-Location` | `VIContainer[]` | No | Specifies vSphere container objects (folders or datacenters) you want to search for folders. |
| `-Name` | `String[]` | No | Specifies the names of the folders you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-RelatedObject` | `FolderRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more Folder objects that are related to them. This parameter accepts OMResource objects. |
| `-Server` | `VIServer[]` | No | Specifies the vSphere servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information ... |
| `-Tag` | `Tag[]` | No | Returns only the folders that are associated with any of the specified tags. |
| `-Type` | `FolderType[]` | No | Specifies the type of the folders you want to retrieve. The valid values are VM, HostAndCluster, Datastore, Network, and Datacenter. |

---

### Get-Inventory

This cmdlet retrieves the inventory items available on a vCenter Server system.

This cmdlet retrieves the inventory items available on a vCenter Server system. The cmdlet returns a set of inventory items that correspond to the filter criteria specified by the provided parameters. To specify a server different from the default one, use the -Server parameter.

**Returns**: `VIObject`

```
Get-Inventory
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the inventory objects you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of t... |
| `-Location` | `VIContainer[]` | No | Specifies vSphere container objects (such as folders, datacenters, and clusters) you want to search for inventory items. |
| `-Name` | `String[]` | No | Specifies the names of the inventory objects you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-LcmClusterDesiredStateRecommendation

This cmdlet generates a desired state recommendation of a vSphere Lifecycle Manager cluster.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Lcm.LcmDesiredState`

```
Get-LcmClusterDesiredStateRecommendation
    -Cluster <Cluster[]>
    -Current
    [-Latest]
    [-RunAsync]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the name of the cluster that you want to get a desired state recommendation for. |
| `-Current` | `SwitchParameter` | Yes | If specified, creates a desired state recommendation based on the currently installed ESXi major base image version. The system recommends installing the latest patch or update of the currently ins... |
| `-Latest` | `SwitchParameter` | No | If specified creates a desired state recommendation based on the latest ESXi base image version. For example, if you have ESXi base image version 6.5 installed and ESXi 7.0 is the latest version av... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-ResourcePool

This cmdlet retrieves the resource pools available on a vCenter Server system.

Retrieves the resource pools available on a vCenter Server system. The cmdlet returns a set of resource pools that correspond to the filter criteria provided by the cmdlet parameters. Virtual machine hosts have a hidden resource pool named Resources, which is a parent of all resource pools of the host. To specify a server different from the default one, use the Server parameter.

**Returns**: `ResourcePool`

```
Get-ResourcePool
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    -RelatedObject <ResourcePoolRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
    -VM <VirtualMachine[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the resource pools you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the ... |
| `-Location` | `VIContainer[]` | No | Specifies vSphere container objects (such as folders, datacenters, and clusters) you want to search for resource pools. |
| `-Name` | `String[]` | No | Specifies the names of the resource pools you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-RelatedObject` | `ResourcePoolRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more ResourcePool objects that are related to them. This parameter accepts ProviderVdc and OMResource objects. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the resource pools that are associated with any of the specified tags. |
| `-VM` | `VirtualMachine[]` | Yes | Specifies virtual machines to filter the resource pools that contain at least one of them. |

---

### Import-LcmClusterDesiredState

This cmdlet imports a specification file to set a desired state of a vSphere Lifecycle Manager cluster.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Inventory.Cluster`

```
Import-LcmClusterDesiredState
    -Cluster <Cluster[]>
    [-Confirm]
    -JsonSpecContent <String>
    -LocalSpecLocation <String>
    -RemoteSpecLocation <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the name of the cluster whose desired state you want to set. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-JsonSpecContent` | `String` | Yes | Specifies a JSON string containing a desired state metadata definition. |
| `-LocalSpecLocation` | `String` | Yes | Specifies the path to a JSON metadata file located on the local file system. |
| `-RemoteSpecLocation` | `String` | Yes | Specifies the path to a remotely located JSON metadata file. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Invoke-DrsRecommendation

This cmdlet applies the specified DRS recommendations.

**Returns**: `None`

```
Invoke-DrsRecommendation
    -DrsRecommendation <DrsRecommendation[]>
    [-RunAsync]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DrsRecommendation` | `DrsRecommendation[]` | Yes | Specifies the DRS recommendations you want to apply. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-Cluster

This cmdlet moves a vCenter Server cluster from one location to another.

This cmdlet moves a vCenter Server cluster to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `Cluster`

```
Move-Cluster
    -Cluster <Cluster[]>
    -Destination <VIContainer>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the clusters you want to move to another location. |
| `-Destination` | `VIContainer` | Yes | Specifies the folder or datacenter where you want to move the clusters. If a datacenter is specified for the Destination parameter, the cluster is moved to its "hostFolder" folder. The "hostFolder"... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-Datacenter

This cmdlet moves a vCenter Server datacenter from one location to another.

This cmdlet moves a vCenter Server datacenter to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `Datacenter`

```
Move-Datacenter
    -Datacenter <Datacenter[]>
    -Destination <VIContainer>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datacenter` | `Datacenter[]` | Yes | Specifies the datacenters you want to move to another location. |
| `-Destination` | `VIContainer` | Yes | Specifies the folder where you want to move the datacenters. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-Folder

This cmdlet moves a vCenter Server folder from one location to another.

This cmdlet moves a vCenter Server folder to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `Folder`

```
Move-Folder
    -Destination <VIContainer>
    -Folder <Folder[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `VIContainer` | Yes | Specifies the datacenter or folder where you want to move the folders. If a datacenter is specified for the Destination parameter, the folder is moved to the datacenter's hostFolder or vmFolder fol... |
| `-Folder` | `Folder[]` | Yes | Specifies the folders you want to move to another location. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-Inventory

This cmdlet moves a vCenter Server inventory item from one location to another.

This cmdlet moves a vCenter Server inventory object or template to the location that is specified by the Destination parameter.

**Returns**: `VIObject`

```
Move-Inventory
    -Destination <VIContainer>
    -Item <InventoryItem[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
    [-DestinationSslThumbprint <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `VIContainer` | Yes | Specifies the location where you want to move the inventory items. |
| `-Item` | `InventoryItem[]` | Yes | Specifies the Folder, ResourcePool, Datacenter, VirtualMachine, VMHost, Template, or Cluster objects you want to move to another location. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-DestinationSslThumbprint` | `String` | No | Specifies the SSL thumbprint of the destination server when moving virtual machines between vCenter Server systems. |

---

### Move-ResourcePool

This cmdlet moves a resource pool from one location to another.

This cmdlet moves a resource pool to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter. Moving a resource pool is only supported when the objects assigned to the ResourcePool and Destination parameters are passed through connections to one and the same server with the same credentials.

**Returns**: `ResourcePool`

```
Move-ResourcePool
    -Destination <VIContainer>
    -ResourcePool <ResourcePool[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `VIContainer` | Yes | Specifies the location where you want to move the resource pools. If a host or a cluster is specified for the Destination parameter, the resource pool is moved into a resource pool named Resources.... |
| `-ResourcePool` | `ResourcePool[]` | Yes | Specifies the resource pools you want to move to another location. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-Cluster

This cmdlet creates a new cluster.

This cmdlet creates a new cluster with the provided inputs in the location that is specified by the Location parameter. HAEnabled is automatically set to $true if some of the HA settings, HAAdmissionControlEnabled, HAFailoverLevel, HARestartPriority, or HAIsolationResponse are specified. DrsEnabled is automatically set to $true if some of the DRS settings, DrsAutomationLevel, or DrsMode are specified.

**Returns**: `Cluster`

```
New-Cluster
    [-DrsAutomationLevel <DrsAutomationLevel>]
    [-DrsEnabled]
    [-DrsMode <DrsMode>]
    [-EVCMode <String>]
    [-HAAdmissionControlEnabled]
    [-HAEnabled]
    [-HAFailoverLevel <Int32>]
    [-HAIsolationResponse <HAIsolationResponse>]
    [-HARestartPriority <HARestartPriority>]
    -Location <VIContainer>
    -Name <String>
    [-Server <VIServer[]>]
    [-VMSwapfilePolicy <VMSwapfilePolicy>]
    [-VsanDiskClaimMode <VsanDiskClaimMode>]
    [-VsanEnabled]
    [-VsanEsaEnabled]
    [-Confirm]
    [-WhatIf]
    [-CryptoMode <CryptoMode>]
    [-VendorAddOn <AddOn>]
    [-BaseImage <BaseImage>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DrsAutomationLevel` | `DrsAutomationLevel` | No | Specifies a DRS automation level. The valid values are FullyAutomated, Manual, and PartiallyAutomated. |
| `-DrsEnabled` | `SwitchParameter` | No | If specified, enables VMware DRS. |
| `-DrsMode` | `DrsMode` | No | This parameter is deprecated and scheduled for removal. Use the DrsAutomationLevel parameter instead.   Specifies a DRS mode. The valid values are FullyAutomated, Manual, and PartiallyAutomated. |
| `-EVCMode` | `String` | No | Specifies the VMware EVC mode of the newly created cluster. If not specified or set to $null, EVC is deactivated. |
| `-HAAdmissionControlEnabled` | `SwitchParameter` | No | Indicates that virtual machines cannot be powered on if they violate availability constraints. |
| `-HAEnabled` | `SwitchParameter` | No | If specified, enables VMware HA. |
| `-HAFailoverLevel` | `Int32` | No | Specifies a configured failover level. This is the number of physical host failures that can be tolerated without impacting the ability to meet minimum thresholds for all running virtual machines. ... |
| `-HAIsolationResponse` | `HAIsolationResponse` | No | Indicates that the virtual machine should be powered off if a host determines that it is isolated from the rest of the compute resource. The valid values are PowerOff and DoNothing. Passing values ... |
| `-HARestartPriority` | `HARestartPriority` | No | Specifies the cluster HA restart priority. The valid values are Disabled, Lowest, Low, Medium, High, and Highest. VMware HA is a feature that detects failed virtual machines and automatically resta... |
| `-Location` | `VIContainer` | Yes | Specifies the location where you want to place the new cluster. If a data center is specified for the Location parameter, the cluster is created in its "hostFolder" folder. The "hostFolder" is a sy... |
| `-Name` | `String` | Yes | Specifies the name of the new cluster. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMSwapfilePolicy` | `VMSwapfilePolicy` | No | Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore that is specified by the VMSwapfileDatastoreID property of the virt... |
| `-VsanDiskClaimMode` | `VsanDiskClaimMode` | No | Specifies the mode by which disks are claimed by vSAN. If not specified and VsanEnabled is specified, the assumed value is Manual. |
| `-VsanEnabled` | `SwitchParameter` | No | Indicates that the vSAN feature is enabled on this cluster. |
| `-VsanEsaEnabled` | `SwitchParameter` | No | Indicates that the vSAN ESA feature is enabled on this cluster. This feature is supported from vSphere 8.0. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-CryptoMode` | `CryptoMode` | No | Specifies the cluster encryption mode. When set to OnDemand, hosts in the cluster are not required to be in a cryptographically "Safe" state. When set to ForceEnable, all hosts in the cluster are f... |
| `-VendorAddOn` | `AddOn` | No | Specifies the ESXi vendor add-on that the cluster's hosts should comply with. |
| `-BaseImage` | `BaseImage` | No | Specifies the ESXi base image that the cluster's hosts should comply with. |

---

### New-Datacenter

This cmdlet creates a new datacenter.

This cmdlet creates a new datacenter in the location that is specified by the Location parameter.

**Returns**: `Datacenter`

```
New-Datacenter
    -Location <VIContainer>
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Location` | `VIContainer` | Yes | Specifies the location where you want to create the new datacenter. |
| `-Name` | `String` | Yes | Specifies a name for the new datacenter. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-DrsClusterGroup

This cmdlet creates either a VM or VM host DRS cluster group, depending on the used parameter set.

**Returns**: `DrsClusterGroup`

```
New-DrsClusterGroup
    -Cluster <Cluster>
    -Name <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster` | Yes | Specifies the cluster on which you want to create the new DRS cluster group. |
| `-Name` | `String` | Yes | Specifies the name for the new DRS cluster group. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines which you want to add to the new VM DRS cluster group. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the VM hosts which you want to add to the new VMHost DRS cluster group. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-DrsRule

This cmdlet creates a new DRS rule.

This cmdlet creates a new DRS rule. Each rule defines the virtual machines that can run on the same host (affinity rule) or must run on different hosts (anti-affinity rule).

**Returns**: `DrsVMAffinityRule`

```
New-DrsRule
    -Cluster <Cluster>
    [-Enabled <Boolean>]
    -KeepTogether <Boolean>
    -Name <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster` | Yes | Specifies the cluster for which the new DRS rule applies. Passing multiple values to this parameter is obsolete. |
| `-Enabled` | `Boolean` | No | If the value of this parameter is $true, the new DRS rule is enabled for the specified clusters. If the value is $false, it is deactivated. |
| `-KeepTogether` | `Boolean` | Yes | If the value of this parameter is $true, the new DRS rule is an affinity rule. If the value is $false, the DRS rule is an anti-affinity rule. |
| `-Name` | `String` | Yes | Specifies a name for the new DRS rule. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines that are referenced by the new DRS rule. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-Folder

This cmdlet creates a new folder on a vCenter Server system.

This cmdlet creates a new folder on the specified location.

**Returns**: `Folder`

```
New-Folder
    -Location <VIContainer>
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Location` | `VIContainer` | Yes | Specifies a container object (folder or datacenter) where you want to place the new folder. If a datacenter is specified for the Location parameter, then the folder is created in its "hostFolder" f... |
| `-Name` | `String` | Yes | Specifies a name for the new folder. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-ResourcePool

This cmdlet creates a new resource pool.

This cmdlet creates a new resource pool with the provided inputs on the location that is specified by the Location parameter.

**Returns**: `ResourcePool`

```
New-ResourcePool
    [-CpuExpandableReservation <Boolean>]
    [-CpuLimitMhz <Int64>]
    [-CpuReservationMhz <Int64>]
    [-CpuSharesLevel <SharesLevel>]
    -Location <VIContainer>
    [-MemExpandableReservation <Boolean>]
    [-MemLimitGB <Decimal>]
    [-MemLimitMB <Int64>]
    [-MemReservationGB <Decimal>]
    [-MemReservationMB <Int64>]
    [-MemSharesLevel <SharesLevel>]
    -Name <String>
    [-NumCpuShares <Int32>]
    [-NumMemShares <Int32>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CpuExpandableReservation` | `Boolean` | No | Indicates that the CPU reservation can grow beyond the specified value if the parent resource pool has unreserved resources. |
| `-CpuLimitMhz` | `Int64` | No | Specifies a CPU usage limit in MHz. Utilization will not exceed this limit even if there are available resources. |
| `-CpuReservationMhz` | `Int64` | No | Specifies the CPU size in MHz that is guaranteed to be available. |
| `-CpuSharesLevel` | `SharesLevel` | No | Specifies the CPU allocation level for this pool. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal. |
| `-Location` | `VIContainer` | Yes | Specifies a container object (ResourcePool, Cluster, or VMHost) where you want to place the new resource pool. If a host or a cluster is specified for the Location parameter, the resource pool is c... |
| `-MemExpandableReservation` | `Boolean` | No | If the value is $true, the memory reservation can grow beyond the specified value if the parent resource pool has unreserved resources. |
| `-MemLimitGB` | `Decimal` | No | Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources. |
| `-MemLimitMB` | `Int64` | No | This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are ava... |
| `-MemReservationGB` | `Decimal` | No | Specifies the guaranteed available memory in gigabytes (GB). |
| `-MemReservationMB` | `Int64` | No | This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB). |
| `-MemSharesLevel` | `SharesLevel` | No | Specifies the memory allocation level for this pool. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal. |
| `-Name` | `String` | Yes | Specifies a name for the new resource pool. |
| `-NumCpuShares` | `Int32` | No | Specifies the CPU allocation level for this pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless the CpuSharesLevel parameter is set to Cu... |
| `-NumMemShares` | `Int32` | No | Specifies the memory allocation level for this pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless the MemSharesLevel parameter is set to... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VIInventoryDrive

This function creates a new drive for an inventory item.

This function creates a new inventory drive that is mapped to a location in a datastore.

**Returns**: `None documented`

```
New-VIInventoryDrive
    [-Name <String>]
    [-Location <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | No | Specifies the name of the new inventory drive. |
| `-Location` | `Object` | No | Specifies the vSphere container objects (such as folders, data centers, and clusters) for which you want to create the drive. |

---

### Remove-Cluster

This cmdlet deletes the specified clusters.

**Returns**: `None`

```
Remove-Cluster
    -Cluster <Cluster[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the clusters you want to remove. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-Datacenter

This cmdlet removes the specified datacenters from their locations.

This cmdlet removes the specified datacenters and their children objects from their locations.

**Returns**: `None`

```
Remove-Datacenter
    -Datacenter <Datacenter[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datacenter` | `Datacenter[]` | Yes | Specifies the datacenters you want to remove. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-DrsClusterGroup

This cmdlet removes the specified DRS cluster groups from the cluster on which it resides.

**Returns**: `None`

```
Remove-DrsClusterGroup
    -DrsClusterGroup <DrsClusterGroup[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DrsClusterGroup` | `DrsClusterGroup[]` | Yes | Specifies the DRS cluster groups you want to remove. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-DrsRule

This cmdlet removes the specified DRS rules.

**Returns**: `None`

```
Remove-DrsRule
    -Rule <DrsRule[]>
    [-RunAsync]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Rule` | `DrsRule[]` | Yes | Specifies the DRS rules you want to remove. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-Folder

This cmdlet removes the specified folders from their locations.

This cmdlet removes the specified folders and their children objects from their locations.

**Returns**: `None`

```
Remove-Folder
    [-DeletePermanently]
    -Folder <Folder[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeletePermanently` | `SwitchParameter` | No | Indicates that you want to delete from the disk any virtual machines contained in the specified folder, and not only to remove them from the inventory. This parameter is supported only for VirtualM... |
| `-Folder` | `Folder[]` | Yes | Specifies the folders you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-Inventory

This cmdlet removes the specified inventory items from their locations.

This cmdlet removes the specified inventory items and their children from their locations.

**Returns**: `None`

```
Remove-Inventory
    -Item <InventoryItem[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Item` | `InventoryItem[]` | Yes | Specifies the inventory items you want to remove. This parameter accepts Folder, ResourcePool, Datacenter, VirtualMachine, VMHost, Cluster, Template, and VApp objects. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-ResourcePool

This cmdlet removes the specified resource pools from their locations.

This cmdlet removes the specified resource pools and their children objects from their locations.

**Returns**: `None`

```
Remove-ResourcePool
    -ResourcePool <ResourcePool[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ResourcePool` | `ResourcePool[]` | Yes | Specifies the resource pools you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Cluster

This cmldlet modifies the configuration of a cluster.

This cmdlet modifies the configuration of a cluster. HAEnabled is automatically set to $true if some of the HA settings, HAAdmissionControlEnabled, HAFailoverLevel, HARestartPriority, or HAIsolationResponse are specified. DrsEnabled is automatically set to $true if some of the DRS settings, DrsAutomationLevel, or DrsMode are specified.

**Returns**: `Cluster`

```
Set-Cluster
    [-AcceptEULA]
    [-BaseImage <BaseImage>]
    -Cluster <Cluster[]>
    [-Component <Component[]>]
    [-CryptoMode <CryptoMode>]
    [-DepotOverride <String[]>]
    [-DrsAutomationLevel <DrsAutomationLevel>]
    [-DrsEnabled <Boolean>]
    [-DrsMode <DrsMode>]
    [-EVCMode <String>]
    [-FirmwareAddon <Package>]
    [-HAAdmissionControlEnabled <Boolean>]
    [-HAEnabled <Boolean>]
    [-HAFailoverLevel <Int32>]
    [-HAIsolationResponse <HAIsolationResponse>]
    [-HARestartPriority <HARestartPriority>]
    [-Name <String>]
    [-Profile <VMHostProfile>]
    -Remediate
    [-RemovedComponent <String[]>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-VendorAddOn <AddOn>]
    [-VMSwapfilePolicy <VMSwapfilePolicy>]
    [-VsanDiskClaimMode <VsanDiskClaimMode>]
    [-VsanEnabled <Boolean>]
    [-VsanEsaEnabled <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptEULA` | `SwitchParameter` | No | Indicates that the End User License Agreement (EULA) is accepted for the images that you want to install on the cluster's hosts in order to comply with the target state. |
| `-BaseImage` | `BaseImage` | No | Specifies the ESXi base image that the cluster's hosts should comply with. |
| `-Cluster` | `Cluster[]` | Yes | Specifies the name of the cluster you want to configure. |
| `-Component` | `Component[]` | No | Specifies the ESXi components that the cluster's hosts should comply with. |
| `-CryptoMode` | `CryptoMode` | No | Specifies the cluster encryption mode you want to configure. When set to OnDemand, hosts in the cluster are not required to be in a cryptographically "Safe" state. When set to ForceEnable, all host... |
| `-DepotOverride` | `String[]` | No | Specifies a depot address from where the cluster can fetch metadata and resources for the vSphere Lifecycle Manager operations. |
| `-DrsAutomationLevel` | `DrsAutomationLevel` | No | Specifies a DRS automation level. The valid values are FullyAutomated, Manual, and PartiallyAutomated. |
| `-DrsEnabled` | `Boolean` | No | If specified, enables VMware DRS. |
| `-DrsMode` | `DrsMode` | No | This parameter is deprecated and scheduled for removal. Use the DrsAutomationLevel parameter instead.   Specifies a DRS mode. The valid values are FullyAutomated, Manual, and PartiallyAutomated. |
| `-EVCMode` | `String` | No | Specifies the EVC mode of the newly created cluster. If not specified or set to $null, EVC is deactivated. |
| `-FirmwareAddon` | `Package` | No | Specifies a package from a hardware support manager that the hosts on a cluster should comply with. This parameter has been renamed from "Package". A PowerShell alias "Package" for this parameter h... |
| `-HAAdmissionControlEnabled` | `Boolean` | No | Indicates that the virtual machines in the cluster will not start if they violate availability constraints. |
| `-HAEnabled` | `Boolean` | No | If specified, enables VMware High Availability. |
| `-HAFailoverLevel` | `Int32` | No | Specifies a failover level. This is the number of physical host failures that can be tolerated without impacting the ability to meet minimum thresholds for all running virtual machines. The valid v... |
| `-HAIsolationResponse` | `HAIsolationResponse` | No | Specifies whether the virtual machine should be powered off if a host determines that it is isolated from the rest of the compute resource. The valid values are PowerOff and DoNothing. Passing valu... |
| `-HARestartPriority` | `HARestartPriority` | No | Specifies the cluster HA restart priority. The valid values are Disabled, Lowest, Low, Medium, High, and Highest. VMware HA is a feature that detects failed virtual machines and automatically resta... |
| `-Name` | `String` | No | Specifies a new name for the cluster. |
| `-Profile` | `VMHostProfile` | No | Specifies a host profile you want to associate with the cluster. If the value of this parameter is $null, the current profile association is removed. |
| `-Remediate` | `SwitchParameter` | Yes | Indicates that you want to remediate the cluster's hosts to the target state. |
| `-RemovedComponent` | `String[]` | No | Specifies a list of components that you want to remove from the base image.   Calling the commandlet with a new value for this parameter overrides any previously configured value. It does not add n... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VendorAddOn` | `AddOn` | No | Specifies the ESXi vendor add-on that the cluster's hosts should comply with. |
| `-VMSwapfilePolicy` | `VMSwapfilePolicy` | No | Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore specified by the VMSwapfileDatastoreID property of the virtual mach... |
| `-VsanDiskClaimMode` | `VsanDiskClaimMode` | No | Specifies the mode by which disks are claimed by vSAN. |
| `-VsanEnabled` | `Boolean` | No | Specifies whether the vSAN feature is enabled on this cluster. |
| `-VsanEsaEnabled` | `Boolean` | No | Indicates that the vSAN ESA feature is enabled on this cluster. This feature is supported from vSphere 8.0. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Datacenter

This cmdlet modifies the properties of the specified datacenter.

**Returns**: `Datacenter`

```
Set-Datacenter
    -Datacenter <Datacenter[]>
    -Name <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datacenter` | `Datacenter[]` | Yes | Specifies the datacenter whose properties you want to modify. |
| `-Name` | `String` | Yes | Specifies a new name for the datacenter. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-DrsClusterGroup

This cmdlet adds or removes either virtual machines or VM hosts to or from the specified DRS cluster group, depending on the used parameter set.

This cmdlet adds or removes either virtual machines or VM hosts to or from the specified DRS cluster group, depending on the used parameter set. You must either specify the Add or Remove parameter for both parameter sets. If not specified, you receive a terminating error.

**Returns**: `DrsClusterGroup`

```
Set-DrsClusterGroup
    [-Add]
    -DrsClusterGroup <DrsClusterGroup>
    [-Remove]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Add` | `SwitchParameter` | No | Specifies that you want to add virtual machines or VM hosts to the DRS cluster group. |
| `-DrsClusterGroup` | `DrsClusterGroup` | Yes | Specifies the DRS cluster group you want to modify. |
| `-Remove` | `SwitchParameter` | No | Specifies that you want to remove virtual machines or VM hosts from the DRS cluster group. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines which you want to add or remove to or from the specified DRS cluster group. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the VM hosts which you want to add or remove to or from the specified DRS cluster group. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-DrsRule

This cmdlet modifies an existing DRS rule.

This cmdlet modifies an existing DRS rule. Each rule defines the virtual machines that can run on the same host (affinity rule) or must run on different hosts (anti-affinity rule).

**Returns**: `DrsVMAffinityRule`

```
Set-DrsRule
    [-Enabled <Boolean>]
    [-Name <String>]
    -Rule <DrsRule[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Enabled` | `Boolean` | No | Indicates that the DRS rule is enabled. |
| `-Name` | `String` | No | Specifies a new name for the DRS rule. |
| `-Rule` | `DrsRule[]` | Yes | Specifies the DRS rule you want to modify. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines that can be referenced by the new DRS rule. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Folder

This cmdlet modifies the properties of the specified folder.

**Returns**: `Folder`

```
Set-Folder
    -Folder <Folder[]>
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Folder` | `Folder[]` | Yes | Specifies the folder whose properties you want to change. |
| `-Name` | `String` | Yes | Specifies a new name for the folder. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-ResourcePool

This cmdlet modifies the properties of the specified resource pool.

**Returns**: `ResourcePool`

```
Set-ResourcePool
    [-CpuExpandableReservation <Boolean>]
    [-CpuLimitMhz <Int64>]
    [-CpuReservationMhz <Int64>]
    [-CpuSharesLevel <SharesLevel>]
    [-MemExpandableReservation <Boolean>]
    [-MemLimitGB <Decimal>]
    [-MemLimitMB <Int64>]
    [-MemReservationGB <Decimal>]
    [-MemReservationMB <Int64>]
    [-MemSharesLevel <SharesLevel>]
    [-Name <String>]
    [-NumCpuShares <Int32>]
    [-NumMemShares <Int32>]
    -ResourcePool <ResourcePool[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CpuExpandableReservation` | `Boolean` | No | Indicates that the CPU reservation can grow beyond the specified value if the parent resource pool has unreserved resources. |
| `-CpuLimitMhz` | `Int64` | No | Specifies a CPU usage limit in MHz. If this parameter is set, utilization will not exceed this limit even if there are available resources. |
| `-CpuReservationMhz` | `Int64` | No | Specifies the guaranteed available CPU in MHz. |
| `-CpuSharesLevel` | `SharesLevel` | No | Specifies the CPU allocation level for this pool. This property is used in relative allocation between resource consumers. This parameter accepts Custom, High, Low, and Normal values. |
| `-MemExpandableReservation` | `Boolean` | No | Indicates that the memory reservation can grow beyond the specified value if the parent resource pool has unreserved resources. |
| `-MemLimitGB` | `Decimal` | No | Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources. |
| `-MemLimitMB` | `Int64` | No | This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are ava... |
| `-MemReservationGB` | `Decimal` | No | Specifies the guaranteed available memory in gigabytes (GB). |
| `-MemReservationMB` | `Int64` | No | This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB). |
| `-MemSharesLevel` | `SharesLevel` | No | Specifies the memory allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter accepts Custom, High, Low, and Normal values. |
| `-Name` | `String` | No | Specifies a new name for the resource pool. |
| `-NumCpuShares` | `Int32` | No | Specifies the CPU allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless CpuSharesLevel is set to Custom. |
| `-NumMemShares` | `Int32` | No | Specifies the memory allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless MemSharesLevel is set to Custom. |
| `-ResourcePool` | `ResourcePool[]` | Yes | Specifies the resource pool you want to configure. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Test-LcmClusterCompliance

This cmdlet tests cluster's hosts compliance respective to its target state.

This cmdlet tests cluster's hosts compliance respective to its target state. You can test the specified cluster's hosts for compliance with the cluster's vSphere Lifecycle Manager desired state.

**Returns**: `ClusterCompliance`

```
Test-LcmClusterCompliance
    -Cluster <Cluster[]>
    [-Confirm]
    [-RunAsync]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies a cluster whose hosts compliance to be tested against custer's vSphere Lifecycle Manager desired state. |
| `-Confirm` | `SwitchParameter` | No | This is a common parameter: If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Test-LcmClusterHealth

This cmdlet tests cluster's hosts health respective to its target state.

This cmdlet tests cluster's hosts health respective to its target state. The specified cluster's hosts health is tested with the cluster's vSphere Lifecycle Manager desired state.

**Returns**: `ClusterHealth`

```
Test-LcmClusterHealth
    -Cluster <Cluster[]>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies a cluster whose hosts health you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

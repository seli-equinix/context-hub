---
name: powercli-datastore
description: "VMware PowerCLI 13.3 — datastore operations: create, browse, manage VMFS volumes"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Copy-DatastoreItem,Get-Datastore,Get-DatastoreCluster,Move-Datastore,New-Datastore,New-DatastoreCluster,New-DatastoreDrive,Remove-Datastore,Remove-DatastoreCluster,Set-Datastore,Set-DatastoreCluster"
---

# VMware PowerCLI — datastore operations

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Copy-DatastoreItem` | This cmdlet copies items between datastores and between a datastore and a local file system provi... |
| `Get-Datastore` | This cmdlet retrieves the datastores available on a vCenter Server system. |
| `Get-DatastoreCluster` | This cmdlet retrieves datastore clusters. |
| `Move-Datastore` | This cmdlet moves datastores from one location to another. |
| `New-Datastore` | This cmdlet creates a new datastore. |
| `New-DatastoreCluster` | This cmdlet creates a new datastore cluster. |
| `New-DatastoreDrive` | This function creates a new datastore drive. |
| `Remove-Datastore` | This cmdlet removes the specified datastores from their locations. |
| `Remove-DatastoreCluster` | This cmdlet deletes the specified datastore clusters. |
| `Set-Datastore` | This cmdlet modifies the properties of the specified datastore. |
| `Set-DatastoreCluster` | This cmdlet modifies the configuration of the specified datastore cluster. |

---

### Copy-DatastoreItem

This cmdlet copies items between datastores and between a datastore and a local file system provider.

**Returns**: `FileInfo`

```
Copy-DatastoreItem
    [-Destination <Object>]
    [-Force]
    -Item <Object[]>
    [-PassThru]
    [-Recurse]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `Object` | No | Specifies the destination where you want to copy the datastore item. You can use a string to specify a relative path to the destination object in the current provider location. For more information... |
| `-Force` | `SwitchParameter` | No | Indicates whether to overwrite all items with the same name at the provided destination. |
| `-Item` | `Object[]` | Yes | Specifies the datastore item you want to copy. You can use a string to provide a relative path to the item in the current provider location. For more information about the PowerCLI datastore provid... |
| `-PassThru` | `SwitchParameter` | No | Indicates that the cmdlet returns the copied item. |
| `-Recurse` | `SwitchParameter` | No | Indicates that you want to copy not only the item, but its children items as well. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-Datastore

This cmdlet retrieves the datastores available on a vCenter Server system.

This cmdlet retrieves the datastores available on a vCenter Server system. Returns a set of datastores that correspond to the filter criteria defined by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `Datastore`

```
Get-Datastore
    -Id <String[]>
    [-Location <VIObject[]>]
    [-Name <String[]>]
    [-Refresh]
    [-RelatedObject <DatastoreRelatedObjectBase[]>]
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the datastores you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the stri... |
| `-Location` | `VIObject[]` | No | Specifies vSphere container objects that you want to search for datastores. This parameter accepts Datacenter, Folder, and DatastoreCluster objects. |
| `-Name` | `String[]` | No | Specifies the names of the datastores you want to retrieve. |
| `-Refresh` | `SwitchParameter` | No | Indicates that the cmdlet first refreshes the storage system information and then retrieves the specified datastores. |
| `-RelatedObject` | `DatastoreRelatedObjectBase[]` | No | Specifies objects to retrieve one or more Datastore objects that are related to them. This parameter accepts vSphere VirtualMachine, VMHost, Datacenter, DatastoreCluster, Cluster, Folder, HardDisk,... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the datastores that are associated with any of the specified tags. |

---

### Get-DatastoreCluster

This cmdlet retrieves datastore clusters.

**Returns**: `DatastoreCluster`

```
Get-DatastoreCluster
    [-Datastore <Datastore[]>]
    [-Id <String[]>]
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    -RelatedObject <DatastoreClusterRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `Datastore[]` | No | Filters the datastore clusters by the datastores located in them. |
| `-Id` | `String[]` | No | Specifies the IDs of the datastore clusters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of ... |
| `-Location` | `VIContainer[]` | No | Specifies the datacenters and folders from which you want to retrieve datastore clusters. |
| `-Name` | `String[]` | No | Specifies the names of the datastore clusters you want to retrieve. |
| `-RelatedObject` | `DatastoreClusterRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more DatastoreCluster objects that are related to them. This parameter accepts OMResource objects. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the datastore clusters that are associated with any of the specified tags. |
| `-Template` | `Template[]` | No | Filters the datastore clusters by the virtual machine templates located in them. |
| `-VM` | `VirtualMachine[]` | No | Filters the datastore clusters by the virtual machines located in them. |

---

### Move-Datastore

This cmdlet moves datastores from one location to another.

**Returns**: `Datastore`

```
Move-Datastore
    -Datastore <Datastore[]>
    -Destination <VIObject>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `Datastore[]` | Yes | Specifies the datastore that you want to move. |
| `-Destination` | `VIObject` | Yes | Specifies a datastore cluster, folder, or datacenter where you want to place the datastore. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-Datastore

This cmdlet creates a new datastore.

This cmdlet creates a new datastore based on the provided parameters. The following characters cannot be used in a datastore name: slash (/), backslash (\), and percent (%).

**Returns**: `Datastore`

```
New-Datastore
    [-BlockSizeMB <Int32>]
    [-FileSystemVersion <String>]
    [-Kerberos]
    -Name <String>
    [-Nfs]
    -NfsHost <String[]>
    -Path <String>
    [-ReadOnly]
    [-Server <VIServer[]>]
    [-Vmfs]
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
    -VvolStorageContainer <StorageContainer>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BlockSizeMB` | `Int32` | No | Specifies the maximum file size of VMFS in megabytes (MB). If no value is given, the maximum file size for the current system platform is used. |
| `-FileSystemVersion` | `String` | No | Specifies the file system you want to use on the new datastore. |
| `-Kerberos` | `SwitchParameter` | No | By default, NFS datastores are created with AUTH_SYS as the authentication protocol. This parameter indicates that the NFS datastore uses Kerberos version 5 for authentication. This parameter is av... |
| `-Name` | `String` | Yes | Specifies a name for the new datastore. |
| `-Nfs` | `SwitchParameter` | No | Indicates that you want to create an NFS datastore. |
| `-NfsHost` | `String[]` | Yes | Specifies the NFS host where you want to create the new datastore. |
| `-Path` | `String` | Yes | If you want to create an NFS datastore, specify the remote path of the NFS mount point. If you want to create a VMFS datastore, specify the canonical name of the SCSI logical unit that will contain... |
| `-ReadOnly` | `SwitchParameter` | No | Indicates that the access mode for the mount point is ReadOnly. The default access mode is ReadWrite. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Vmfs` | `SwitchParameter` | No | Indicates that you want to create a VMFS datastore. |
| `-VMHost` | `VMHost` | Yes | Specifies a host where you want to create the new datastore. Passing multiple values to this parameter is obsolete. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-VvolStorageContainer` | `StorageContainer` | Yes | Specifies the backing virtual volume (vVol) storage container to create the datastore. You can retrieve the storage container objects by using the Get-VvolStorageContainer cmdlet. |

---

### New-DatastoreCluster

This cmdlet creates a new datastore cluster.

This cmdlet creates a new datastore cluster. By default, Storage DRS is deactivated. To enable Storage DRS, run Set-DatastoreCluster.

**Returns**: `DatastoreCluster`

```
New-DatastoreCluster
    -Location <VIContainer>
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Location` | `VIContainer` | Yes | Specifies a container object (Datacenter or Folder) where you want to place the new datastore cluster. |
| `-Name` | `String` | Yes | Specifies a name for the datastore cluster that you want to create. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-DatastoreDrive

This function creates a new datastore drive.

This function creates a new drive that is mapped to a location in a datastore.

**Returns**: `None documented`

```
New-DatastoreDrive
    [-Name <String>]
    [-Datastore <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | No | Specifies a name for the new drive. |
| `-Datastore` | `Object` | No | Specifies the datastore for which you want to create a new drive. |

---

### Remove-Datastore

This cmdlet removes the specified datastores from their locations.

This cmdlet removes the specified datastores from their locations. The cmdlet permanently deletes the content of the removed datastores, unless they are shared (NFS).

**Returns**: `None`

```
Remove-Datastore
    -Datastore <Datastore[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `Datastore[]` | Yes | Specifies the datastores you want to remove. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost` | Yes | Specifies the host to which the datastore you want to remove belongs. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-DatastoreCluster

This cmdlet deletes the specified datastore clusters.

**Returns**: `None`

```
Remove-DatastoreCluster
    -DatastoreCluster <DatastoreCluster[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DatastoreCluster` | `DatastoreCluster[]` | Yes | Specifies the datastore cluster that you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Datastore

This cmdlet modifies the properties of the specified datastore.

This cmdlet modifies the properties of the specified datastore. You can use the following characters in a path, but not in a datastore name: slash (/), backslash (\), and percent (%).

**Returns**: `Datastore`

```
Set-Datastore
    [-CongestionThresholdMillisecond <Int32>]
    -Datastore <Datastore[]>
    [-EvacuateAutomatically]
    -MaintenanceMode <Boolean>
    [-Name <String>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-StorageIOControlEnabled <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CongestionThresholdMillisecond` | `Int32` | No | Specifies the latency period beyond which the storage array is considered congested. The range of this value is between 10 to 100 milliseconds. |
| `-Datastore` | `Datastore[]` | Yes | Specifies the datastore whose properties you want to change. |
| `-EvacuateAutomatically` | `SwitchParameter` | No | Specifies whether you want to automatically migrate all virtual machines to another datastore if the value of MaintenanceMode is $true. When the Storage DRS automation level is  set to Fully Automa... |
| `-MaintenanceMode` | `Boolean` | Yes | Specifies whether you want to put the datastore in maintenance mode. The operation completes when no virtual machines are present and no provisioning processes are running on the datastore. |
| `-Name` | `String` | No | Specifies a new name for the datastore. Do not use slash (/), backslash (\), and percent (%) characters in datastore names. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StorageIOControlEnabled` | `Boolean` | No | Indicates whether you want to enable the IO control. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-DatastoreCluster

This cmdlet modifies the configuration of the specified datastore cluster.

**Returns**: `DatastoreCluster`

```
Set-DatastoreCluster
    -DatastoreCluster <DatastoreCluster[]>
    [-IOLatencyThresholdMillisecond <Int32>]
    [-IOLoadBalanceEnabled <Boolean>]
    [-Name <String>]
    [-SdrsAutomationLevel <DrsAutomationLevel>]
    [-Server <VIServer[]>]
    [-SpaceUtilizationThresholdPercent <Int32>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DatastoreCluster` | `DatastoreCluster[]` | Yes | Specifies the datastore cluster that you want to configure. |
| `-IOLatencyThresholdMillisecond` | `Int32` | No | Specifies the maximum I/O latency in milliseconds allowed before Storage DRS is triggered for the datastore cluster. The parameter accepts values in the range of 5 to 100. If the value of IOLoadBal... |
| `-IOLoadBalanceEnabled` | `Boolean` | No | Specifies whether I/O load balancing is enabled for the datastore cluster. If the value is $false, I/O load balancing is deactivated and the settings for the I/O latency threshold and utilized spac... |
| `-Name` | `String` | No | Specifies a new name for the datastore cluster. |
| `-SdrsAutomationLevel` | `DrsAutomationLevel` | No | Specifies the Storage DRS automation level for the datastore cluster. This parameter accepts Disabled, Manual, and FullyAutomated values. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SpaceUtilizationThresholdPercent` | `Int32` | No | Specifies the maximum percentage of consumed space allowed before Storage DRS is triggered for the datastore cluster. The parameter accepts values in the range of 50 to 100. If the value of IOLoadB... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

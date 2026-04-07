---
name: powercli-template
description: "VMware PowerCLI 13.3 — templates and content library: OVF/OVA, content library items"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Copy-ContentLibraryItem,Export-ContentLibraryItem,Export-VApp,Get-ContentLibrary,Get-ContentLibraryItem,Get-OvfConfiguration,Get-Template,Get-VApp,Import-VApp,Move-Template,Move-VApp,New-ContentLibrary,New-ContentLibraryItem,New-Template,New-VApp,Remove-ContentLibrary,Remove-ContentLibraryItem,Remove-Template,Remove-VApp,Set-ContentLibrary,Set-ContentLibraryItem,Set-Template,Set-VApp,Start-VApp,Stop-VApp"
---

# VMware PowerCLI — templates and content library

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Copy-ContentLibraryItem` | This cmdlet copies content library items to a local content library. |
| `Export-ContentLibraryItem` | This cmdlet exports content library item's files to the local machine. |
| `Export-VApp` | This cmdlet exports a vApp or a single virtual machine to the specified destination. |
| `Get-ContentLibrary` | This cmdlet creates a new local or subscribed content library. |
| `Get-ContentLibraryItem` | This cmdlet retrieves catalog items from the content library. |
| `Get-OvfConfiguration` | This cmdlet retrieves the OVF configuration object from the specified OVF, OVA, or content librar... |
| `Get-Template` | This cmdlet retrieves the virtual machine templates available on a vCenter Server system. |
| `Get-VApp` | This cmdlet retrieves vApps. |
| `Import-VApp` | This cmdlet imports OVF (Open Virtualization Format) and OVA packages. The package can contain a ... |
| `Move-Template` | This cmdlet moves virtual machine templates to another location. |
| `Move-VApp` | This cmdlet moves the specified virtual appliances to a new location. |
| `New-ContentLibrary` | Creates a new local or subscribed content library that uses Datastore1 as a repository for its it... |
| `New-ContentLibraryItem` | This cmdlet creates a new content library item in the specified content library. |
| `New-Template` | This cmdlet creates a new virtual machine template. |
| `New-VApp` | This cmdlet creates a new vApp. |
| `Remove-ContentLibrary` | This cmdlet removes the specified content libraries. |
| `Remove-ContentLibraryItem` | This cmdlet removes the specified content library items. |
| `Remove-Template` | This cmdlet removes the specified virtual machine templates from the inventory. |
| `Remove-VApp` | This cmdlet removes vApps from the server. |
| `Set-ContentLibrary` | This cmdlet modifies content library's properties. |
| `Set-ContentLibraryItem` | This cmdlet modifies content library item's properties. |
| `Set-Template` | This cmdlet modifies the specified virtual machine template. |
| `Set-VApp` | This cmdlet modifies the specified vApp. |
| `Start-VApp` | This cmdlet starts vApps. |
| `Stop-VApp` | This cmdlet stops vApps. |

---

### Copy-ContentLibraryItem

This cmdlet copies content library items to a local content library.

**Returns**: `System.Void`

```
Copy-ContentLibraryItem
    [-Confirm]
    -ContentLibraryItem <ContentLibraryItem[]>
    -Destination <LocalContentLibrary>
    [-Name <String>]
    [-Notes <String>]
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-ContentLibraryItem` | `ContentLibraryItem[]` | Yes | Specifies the content library item that you want to copy. |
| `-Destination` | `LocalContentLibrary` | Yes | Specifies the local content library where you want to copy the item. |
| `-Name` | `String` | No | Specifies the name on the library item. Library item names cannot be undefined or an empty string. Names do not have to be unique.   Note: If not specified, the name of the source content library i... |
| `-Notes` | `String` | No | Specifies a human-readable description for the content library item that you want to copy. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Export-ContentLibraryItem

This cmdlet exports content library item's files to the local machine.

**Returns**: `DirectoryInfo`

```
Export-ContentLibraryItem
    [-Confirm]
    -ContentLibraryItem <ContentLibraryItem[]>
    [-Destination <String>]
    [-Force]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-ContentLibraryItem` | `ContentLibraryItem[]` | Yes | Specifies the content library item whose content you want to export. |
| `-Destination` | `String` | No | Specifies an existing local directory where you want to save the content library items.   Note: If the parameter is not specified, your current directory will be used. |
| `-Force` | `SwitchParameter` | No | Specifies if you want to overwrite existing files with the same name that exist in the destination directory. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Export-VApp

This cmdlet exports a vApp or a single virtual machine to the specified destination.

This cmdlet exports a vApp or a single virtual machine to the specified destination. If no destination is specified, the cmdlet creates a new folder in the current working directory and exports the vApp or the virtual machine to it. The name of the new folder is the same as the name of the vApp or the virtual machine as it appears in vCenter Server.

**Returns**: `FileInfo`

```
Export-VApp
    [-CreateSeparateFolder]
    [-Description <String>]
    [-Destination <String>]
    [-Force]
    [-Format <VAppStorageFormat>]
    [-Name <String>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-SHAAlgorithm <SHAAlgorithm>]
    -VApp <VApp[]>
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CreateSeparateFolder` | `SwitchParameter` | No | Indicates that you want to create a separate folder for each vApp or virtual machine. |
| `-Description` | `String` | No | Provides a description of the exported vApp or virtual machine. |
| `-Destination` | `String` | No | Specifies a destination path to the file system location where you want to export the vApp or the virtual machine. If the value of the Destination parameter is a folder, the vApp or the virtual mac... |
| `-Force` | `SwitchParameter` | No | Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path. |
| `-Format` | `VAppStorageFormat` | No | Specifies the file format of the specified vApp or virtual machine. The default format is OVF. The valid values are OVF and OVA. |
| `-Name` | `String` | No | Specifies a name for the exported vApp or virtual machine. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers... |
| `-SHAAlgorithm` | `SHAAlgorithm` | No | Specifies the hashing algorithm that you want to use in the manifest checksums. The default value is SHA256. The valid values are SHA256 and SHA1. |
| `-VApp` | `VApp[]` | Yes | Specifies the vApp that you want to export. |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machine that you want to export. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-ContentLibrary

This cmdlet creates a new local or subscribed content library.

This cmdlet retrieves content libraries and returns a set of content libraries that correspond to the filter criteria defined by the cmdlet parameters.

**Returns**: `LocalContentLibrary`

```
Get-ContentLibrary
    [-Confirm]
    -Id <String[]>
    [-Local]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Subscribed]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the content libraries you want to retrieve. |
| `-Local` | `SwitchParameter` | No | Specifies that you want to retrieve only the local content libraries. |
| `-Name` | `String[]` | No | Specifies the names of the content libraries you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Subscribed` | `SwitchParameter` | No | Specifies that you want to retrieve only the subscribed content libraries. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-ContentLibraryItem

This cmdlet retrieves catalog items from the content library.

This cmdlet retrieves catalog items from the content library and returns a set of catalog items that correspond to the filter criteria defined by the cmdlet parameters.

**Returns**: `ContentLibraryItem`

```
Get-ContentLibraryItem
    [-ContentLibrary <ContentLibrary[]>]
    -Id <String[]>
    [-ItemType <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ContentLibrary` | `ContentLibrary[]` | No | Filters items by ContentLibrary. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the catalog items you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects have an ID that matches exactly one of the string ... |
| `-ItemType` | `String[]` | No | Filters the catalog items by type. |
| `-Name` | `String[]` | No | Specifies the names of the catalog items you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-OvfConfiguration

This cmdlet retrieves the OVF configuration object from the specified OVF, OVA, or content library item.

This cmdlet retrieves the OVF configuration object from the specified OVF, OVA, or content library item. Only user-configurable properties are returned.

**Returns**: `OvfConfiguration`

```
Get-OvfConfiguration
    -ContentLibraryItem <ContentLibraryItem>
    -Ovf <String>
    -Target <VIContainer>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ContentLibraryItem` | `ContentLibraryItem` | Yes | Specifies the content library item to retrieve the OVF configuration from. |
| `-Ovf` | `String` | Yes | Specifies the local path to the OVF or OVA package for which the user-configurable options are returned. URL paths are not supported. |
| `-Target` | `VIContainer` | Yes | Specifies the location (target) to which you want to deploy the OVF package. The target can be a an object of type VMHost, ResourcePool, Cluster, or VApp. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-Template

This cmdlet retrieves the virtual machine templates available on a vCenter Server system.

This cmdlet retrieves the virtual machine templates available on a vCenter Server system. The cmdlet returns a set of templates that correspond to the filter criteria defined by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `Template`

```
Get-Template
    [-Datastore <StorageResource[]>]
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `StorageResource[]` | No | Filters templates by the datastores or datastore clusters that they are stored on. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the virtual machine templates you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly ... |
| `-Location` | `VIContainer[]` | No | Specifies the vSphere container objects (such as folders, datacenters, and VMHosts) you want to search for templates. |
| `-Name` | `String[]` | No | Specifies the names of the virtual machine templates you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VApp

This cmdlet retrieves vApps.

**Returns**: `VApp`

```
Get-VApp
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the vApps that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the stri... |
| `-Location` | `VIContainer[]` | No | Specifies Folder, Cluster, Datacenter, VMHost, and ResourcePool objects you want to search for vApps. |
| `-Name` | `String[]` | No | Specifies the names of the vApps that you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the vApps that are associated with any of the specified tags. |

---

### Import-VApp

This cmdlet imports OVF (Open Virtualization Format) and OVA packages. The package can contain a virtual appliance or a virtual machine.

This cmdlet imports OVF (Open Virtualization Format) and OVA packages. The package can contain a vApp or a virtual machine. The cmdlet returns a VApp object when the OVF contains a vApp and a VirtualMachine object when the OVF contains a single virtual machine.

**Returns**: `VApp`

```
Import-VApp
    [-Datastore <StorageResource>]
    [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-Force]
    [-InventoryLocation <FolderContainer>]
    [-Location <VIContainer>]
    [-Name <String>]
    [-OvfConfiguration <Hashtable>]
    [-RunAsync]
    [-Server <VIServer[]>]
    -Source <String>
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `StorageResource` | No | Specifies a datastore or a datastore cluster where you want to store the vApp or virtual machine. |
| `-DiskStorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the storage format for the disks of the imported VMs. By default, the storage format is thick. When you set this parameter, you set the storage format for all virtual machine disks in the... |
| `-Force` | `SwitchParameter` | No | Indicates that you want to import an OVF or OVA package even if the package signature cannot be verified or if the checksum validation algorithm is not supported. |
| `-InventoryLocation` | `FolderContainer` | No | Specifies a datacenter or a virtual machine folder where you want to place the new vApp. This folder serves as a logical container for inventory organization. The Location parameter serves as a com... |
| `-Location` | `VIContainer` | No | Specifies a vSphere inventory container where you want to import the vApp or virtual machine. It must be a vApp, a resource pool, or a cluster. |
| `-Name` | `String` | No | Specifies a name for the imported vApp or virtual machine. |
| `-OvfConfiguration` | `Hashtable` | No | Specifies values for a set of user-configurable OVF properties. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Source` | `String` | Yes | Specifies the path to the OVF or OVA package that you want to import. |
| `-VMHost` | `VMHost` | Yes | Specifies a host where you want to run the vApp or virtual machine. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-Template

This cmdlet moves virtual machine templates to another location.

This cmdlet moves virtual machine templates to a location that is specified by the Destination parameter.

**Returns**: `Template`

```
Move-Template
    -Destination <VIContainer>
    [-RunAsync]
    [-Server <VIServer[]>]
    -Template <Template[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `VIContainer` | Yes | Specifies a container object where you want to move the templates. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Template` | `Template[]` | Yes | Specifies the virtual machine templates you want to move to another location. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-VApp

This cmdlet moves the specified virtual appliances to a new location.

This cmdlet moves the specified vApps to a new location. If the destination is a host or a cluster, the vApps are moved to the system "Resources" resource pool.

**Returns**: `VApp`

```
Move-VApp
    -Destination <VIContainer>
    [-RunAsync]
    [-Server <VIServer[]>]
    -VApp <VApp[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `VIContainer` | Yes | Specifies where you want to move the specified vApps. Supported types are Folder, VMHost, Cluster, ResourcePool, VApp, and Datacenter. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VApp` | `VApp[]` | Yes | Specifies the vApps you want to move. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-ContentLibrary

Creates a new local or subscribed content library that uses Datastore1 as a repository for its items.

This cmdlet creates a new new local or subscribed content library depending on the provided parameters.

**Returns**: `ContentLibrary`

```
New-ContentLibrary
    [-AutomaticSync]
    [-Confirm]
    -Datastore <Datastore>
    [-Description <String>]
    [-DownloadContentOnDemand]
    -Name <String>
    [-OptimizeRemotePublishing]
    [-Password <String>]
    [-PersistJson]
    [-Published]
    [-Server <VIServer[]>]
    [-SslThumbprint <String>]
    -SubscriptionUrl <String>
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutomaticSync` | `SwitchParameter` | No | Specifies whether the library should participate in automatic library synchronization. If you want to do an automatic synchronization, the global Automatic Sync option must be enabled.   The subscr... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Datastore` | `Datastore` | Yes | Specifies the datastore that you want to use to store files for library items in this library. |
| `-Description` | `String` | No | Specifies a human-readable description for the content library that you want to create. |
| `-DownloadContentOnDemand` | `SwitchParameter` | No | Indicates whether a library item's content is synchronized only on demand.   If specified, then the library item's metadata is synchronized but the item's content (its files) is not. The Content Li... |
| `-Name` | `String` | Yes | Specifies the name of the library. Library names cannot be undefined or an empty string. Names do not have to be unique. |
| `-OptimizeRemotePublishing` | `SwitchParameter` | No | If specified, the library is optimized for remote publishing and the Published parameter is required.   This parameter specifies if remote publishing is the dominant use case for this library. The ... |
| `-Password` | `String` | No | Specifies the password you want to use for the content library.   If you want to create a local content library, the password is required from subscribers in Basic authentication mode.   If you wan... |
| `-PersistJson` | `SwitchParameter` | No | Specifies whether library and library item metadata are persisted in the storage location as JSON files. This flag only applies if the local library is published.   You can copy the local library c... |
| `-Published` | `SwitchParameter` | No | Specifies whether you need to publish the local library. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SslThumbprint` | `String` | No | Specifies an optional SHA-1 hash of the SSL certificate for the remote endpoint.   If this value is defined, the SSL certificate is verified by comparing it to the SSL thumbprint. The SSL certifica... |
| `-SubscriptionUrl` | `String` | Yes | Specifies the URL of the endpoint where the metadata for the remotely published library is served. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-ContentLibraryItem

This cmdlet creates a new content library item in the specified content library.

This cmdlet creates a new content library item in the specified content library. If the Files parameter is specified, you can add the specified files to the newly created content library item.

**Returns**: `ContentLibraryItem`

```
New-ContentLibraryItem
    [-Confirm]
    -ContentLibrary <LocalContentLibrary>
    [-Datastore <Datastore>]
    -FileName <String[]>
    [-Files <String[]>]
    [-InventoryLocation <FolderContainer>]
    [-ItemType <String>]
    -Location <VIContainer>
    -Name <String>
    [-Notes <String>]
    [-VApp <VApp>]
    -VM <VirtualMachine>
    -VMTemplate
    [-Server <VIServer[]>]
    [-DisableOvfCertificateChecks]
    [-SslThumbprint <String>]
    [-StoragePolicy <StoragePolicy>]
    [-Template <Template>]
    -Uri <String[]>
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-ContentLibrary` | `LocalContentLibrary` | Yes | Specifies a local content library that hosts the content library item. |
| `-Datastore` | `Datastore` | No | Specifies a datastore where you want to place the new virtual machine template. |
| `-FileName` | `String[]` | Yes | Specifies a list of file names that you want to use for the file pulled by the content library item from the URI specified in the Uri parameter. |
| `-Files` | `String[]` | No | Specifies the paths to local or remote files that you want to add to the newly created content library item. |
| `-InventoryLocation` | `FolderContainer` | No | Specifies a data center or a virtual machine folder where you want to place the new virtual machine template. |
| `-ItemType` | `String` | No | Specifies the type of the library item. |
| `-Location` | `VIContainer` | Yes | Specifies a VApp, ResourcePool, VMHost, or Cluster object where you want to place the new virtual machine template. |
| `-Name` | `String` | Yes | Specifies the name of the library item. The library item names cannot be undefined or an empty string. Names do not have to be unique. |
| `-Notes` | `String` | No | Specifies a human-readable description for the content library item that you want to create. |
| `-VApp` | `VApp` | No | Specifies a VApp object from which to create the OVF template in the content library. |
| `-VM` | `VirtualMachine` | Yes | Specifies a virtual machine from which to create the virtual machine or OVF template in the content library. |
| `-VMTemplate` | `SwitchParameter` | Yes | If the value is $true, a virtual machine template is created in the content library. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-DisableOvfCertificateChecks` | `SwitchParameter` | No | Specifies to skip all OVA/OVF certificate checks during the upload to the content library item. |
| `-SslThumbprint` | `String` | No | Specifies the SSL thumbprint of the server hosting the file specified by the URI in the Uri parameter. |
| `-StoragePolicy` | `StoragePolicy` | No | Specifies the storage policy for the new virtual machine template in the content library. |
| `-Template` | `Template` | No | Specifies a virtual machine template from which to create the OVF template in the content library. |
| `-Uri` | `String[]` | Yes | Specifies a list of URIs of the file that you want to pull into the content library item.   Note: http://, https://, and ds:// uris are acceptable. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-Template

This cmdlet creates a new virtual machine template.

This cmdlet creates a new template based on the specified virtual machine. You can also create a new template by cloning an existing one. You can also register an existing template to the vCenter Server inventory.

**Returns**: `Template`

```
New-Template
    [-Datastore <StorageResource>]
    [-DiskStorageFormat <VirtualDiskStorageFormat>]
    -Location <VIContainer>
    -Name <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    -Template <Template>
    -TemplateFilePath <String>
    -VM <VirtualMachine>
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `StorageResource` | No | Specifies the datastore or the datastore cluster where you want to store the new template. |
| `-DiskStorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the disk storage format of the new template. This parameter accepts Thin, Thick, and EagerZeroedThick values. |
| `-Location` | `VIContainer` | Yes | Specifies the location where you want to place the new template. |
| `-Name` | `String` | Yes | Specifies a name for the new template. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Template` | `Template` | Yes | Specifies a template you want to clone. |
| `-TemplateFilePath` | `String` | Yes | Specifies the datastore path to the file you want to use to register the new template. |
| `-VM` | `VirtualMachine` | Yes | Specifies the virtual machine from which you want to create the new template. |
| `-VMHost` | `VMHost` | Yes | Specifies the host where you want to create the new template. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VApp

This cmdlet creates a new vApp.

**Returns**: `VApp`

```
New-VApp
    -ContentLibraryItem <ContentLibraryItem>
    [-CpuExpandableReservation <Boolean>]
    [-CpuLimitMhz <Int64>]
    [-CpuReservationMhz <Int64>]
    [-CpuSharesLevel <SharesLevel>]
    [-Datastore <Datastore>]
    [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-InventoryLocation <FolderContainer>]
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
    [-RunAsync]
    [-Server <VIServer[]>]
    -VApp <VApp>
    [-VMHost <VMHost>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ContentLibraryItem` | `ContentLibraryItem` | Yes | Specifies the content library template to deploy the vApp from. |
| `-CpuExpandableReservation` | `Boolean` | No | Indicates that the CPU reservation can grow beyond the specified value if there are available resources. |
| `-CpuLimitMhz` | `Int64` | No | Specifies a CPU usage limit in MHz. Utilization will not exceed this limit even if there are available resources. |
| `-CpuReservationMhz` | `Int64` | No | Specifies the CPU size in MHz that is guaranteed to be available. |
| `-CpuSharesLevel` | `SharesLevel` | No | Specifies the CPU allocation level for this vApp. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal. |
| `-Datastore` | `Datastore` | No | Specifies the datastore where you want to store the copied vApp. If you do not specify a datastore, the cmdlet takes the first datastore of the host or cluster. |
| `-DiskStorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the storage format of the disks of the vApp. |
| `-InventoryLocation` | `FolderContainer` | No | Specifies a datacenter or a virtual machine folder where you want to place the new vApp. |
| `-Location` | `VIContainer` | Yes | Specifies a VApp, ResourcePool, VMHost, or Cluster object where you want to place the new vApp. |
| `-MemExpandableReservation` | `Boolean` | No | If the value is $true, the memory reservation can grow beyond the specified value if there are available resources. |
| `-MemLimitGB` | `Decimal` | No | Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources. |
| `-MemLimitMB` | `Int64` | No | This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are ava... |
| `-MemReservationGB` | `Decimal` | No | Specifies the guaranteed available memory in gigabytes (GB). |
| `-MemReservationMB` | `Int64` | No | This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB). |
| `-MemSharesLevel` | `SharesLevel` | No | Specifies the memory allocation level for this vApp. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal. |
| `-Name` | `String` | Yes | Specifies a name for the new vApp. |
| `-NumCpuShares` | `Int32` | No | Specifies the CPU allocation level for this vApp. This property is used in relative allocation between resource consumers. This parameter is ignored unless the CpuSharesLevel parameter is set to Cu... |
| `-NumMemShares` | `Int32` | No | Specifies the memory allocation level for this vApp. This property is used in relative allocation between resource consumers. This parameter is ignored unless the MemSharesLevel parameter is set to... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the Center Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more inform... |
| `-VApp` | `VApp` | Yes | Specifies a vApp you want to copy. |
| `-VMHost` | `VMHost` | No | Specifies the host where you want to run the copied vApp. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-ContentLibrary

This cmdlet removes the specified content libraries.

**Returns**: `None`

```
Remove-ContentLibrary
    [-Confirm]
    -ContentLibrary <ContentLibrary[]>
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-ContentLibrary` | `ContentLibrary[]` | Yes | Specifies the content libraries you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-ContentLibraryItem

This cmdlet removes the specified content library items.

**Returns**: `None`

```
Remove-ContentLibraryItem
    [-Confirm]
    -ContentLibraryItem <ContentLibraryItem[]>
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-ContentLibraryItem` | `ContentLibraryItem[]` | Yes | Specifies the content library items you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-Template

This cmdlet removes the specified virtual machine templates from the inventory.

This cmdlet removes the specified virtual machine templates from the inventory. If the value of the DeletePermanently parameter is  $true, the cmdlet removes the templates from the inventory and deletes them from the disk.

**Returns**: `None`

```
Remove-Template
    [-DeletePermanently]
    [-RunAsync]
    [-Server <VIServer[]>]
    -Template <Template[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeletePermanently` | `SwitchParameter` | No | Indicates that you want to delete the templates not only from the inventory, but from the datastore as well. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Template` | `Template[]` | Yes | Specifies the virtual machine templates you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VApp

This cmdlet removes vApps from the server.

**Returns**: `None`

```
Remove-VApp
    [-DeletePermanently]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VApp <VApp[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeletePermanently` | `SwitchParameter` | No | Indicates that you want not only to remove the vApps from the inventory, but also to delete the virtual machines they contain from the datastore. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VApp` | `VApp[]` | Yes | Specifies the vApp you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-ContentLibrary

This cmdlet modifies content library's properties.

**Returns**: `LocalContentLibrary`

```
Set-ContentLibrary
    [-AutomaticSync]
    [-Confirm]
    [-CurrentPassword <String>]
    [-Description <String>]
    [-DisableAuthentication]
    [-DownloadContentOnDemand]
    -Evict
    -LocalContentLibrary <LocalContentLibrary[]>
    [-Name <String>]
    [-Password <String>]
    [-PersistJson]
    [-Published]
    [-Server <VIServer[]>]
    [-SslThumbprint <String>]
    -SubscribedContentLibrary <SubscribedContentLibrary[]>
    [-SubscriptionUrl <String>]
    -Sync
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutomaticSync` | `SwitchParameter` | No | If specified, synchronization of content library items happens automatically. If not, synchronization happens by using the Set-ContentLibrary cmdlet with the Sync parameter. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-CurrentPassword` | `String` | No | Indicates if you want to update a password protected content library. Currently set password is supplied to complete the operation.   Note: Available on vCenter Server 6.7 and later. |
| `-Description` | `String` | No | Specifies a human-readable description for the content library that you want to create. |
| `-DisableAuthentication` | `SwitchParameter` | No | If specified, deactivates authentication of the content library. |
| `-DownloadContentOnDemand` | `SwitchParameter` | No | Indicates whether a library item's content is synchronized only on demand.   If specified, the library item's metadata is synchronized, but the item's content (its files) is not synchronized. The C... |
| `-Evict` | `SwitchParameter` | Yes | Removes cached content library's items content of a subscribed content library whose content is downloaded on demand. |
| `-LocalContentLibrary` | `LocalContentLibrary[]` | Yes | A local content library whose properties you want to alter. |
| `-Name` | `String` | No | Specifies a new name for the content library. |
| `-Password` | `String` | No | Specifies the password that you want to set or update to the target content library. |
| `-PersistJson` | `SwitchParameter` | No | Specifies whether library and library item metadata are persisted in the storage location as JSON files. This flag only applies if you want to publish the local library.   Enabling JSON persistence... |
| `-Published` | `SwitchParameter` | No | Specifies whether you want to publish the local library. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no given is passed to this parameter, the command runs on the default servers. For more information about default server... |
| `-SslThumbprint` | `String` | No | Specifies an optional SHA-1 hash of the SSL certificate for the remote endpoint.   If this value is defined, the SSL certificate is verified by comparing it to the SSL thumbprint. The SSL certifica... |
| `-SubscribedContentLibrary` | `SubscribedContentLibrary[]` | Yes | Specifies a subscribed content library which properties you want to alter. |
| `-SubscriptionUrl` | `String` | No | Specifies the URL of the endpoint where the metadata for the remotely published library is served. |
| `-Sync` | `SwitchParameter` | Yes | If specified, manually synchronizes the subscribed content library. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-ContentLibraryItem

This cmdlet modifies content library item's properties.

This cmdlet modifies the properties of a content library item.

**Returns**: `ContentLibraryItem`

```
Set-ContentLibraryItem
    [-ClearExistingFiles]
    [-Confirm]
    -ContentLibraryItem <ContentLibraryItem[]>
    -FileName <String[]>
    [-Files <String[]>]
    [-ItemType <String>]
    [-Name <String>]
    [-Notes <String>]
    [-VApp <VApp>]
    [-VM <VirtualMachine>]
    [-Server <VIServer[]>]
    [-DisableOvfCertificateChecks]
    [-SslThumbprint <String>]
    [-Template <Template>]
    -Uri <String[]>
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ClearExistingFiles` | `SwitchParameter` | No | Indicates that if there are any files in the content library item, they will be removed before uploading the new ones. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-ContentLibraryItem` | `ContentLibraryItem[]` | Yes | Specifies the content library item whose properties you want to change. |
| `-FileName` | `String[]` | Yes | Specifies a list of file names that you want to use for the file pulled by the content library item from the URI specified in the Uri parameter. |
| `-Files` | `String[]` | No | Specifies the paths to the local files that substitute the current content library item's files.   Note: If the Files parameter is not specified, the content library item's files do not get altered. |
| `-ItemType` | `String` | No | Specifies the type of the library item. |
| `-Name` | `String` | No | Specifies a new name for the content library item. |
| `-Notes` | `String` | No | Specifies a new description for the content library item. |
| `-VApp` | `VApp` | No | Specifies a VApp object to overwrite the original content of the OVF template content library item. |
| `-VM` | `VirtualMachine` | No | Specifies a virtual machine to overwrite the original content of the OVF template content library item. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-DisableOvfCertificateChecks` | `SwitchParameter` | No | Specifies to skip all OVA/OVF certificate checks during the upload to the content library item. |
| `-SslThumbprint` | `String` | No | Specifies the SSL thumbprint of the server hosting the file specified by the URI in the Uri parameter. |
| `-Template` | `Template` | No | Specifies a virtual machine template to overwrite the original content of the OVF template content library item. |
| `-Uri` | `String[]` | Yes | Specifies a list of URIs of the file that you want to pull into the content library item.   Note: http://, https://, and ds:// uris are acceptable. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Template

This cmdlet modifies the specified virtual machine template.

This cmdlet changes the name and the description of a virtual machine template according to the provided parameters. The cmdlet can convert the template to a virtual machine if the value of the ToVM parameter is $true.

**Returns**: `Template`

```
Set-Template
    [-Name <String>]
    [-RunAsync]
    [-Server <VIServer[]>]
    -Template <Template[]>
    [-ToVM]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | No | Specifies a new name for the template. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Template` | `Template[]` | Yes | Specifies the template whose properties you want to change. |
| `-ToVM` | `SwitchParameter` | No | Indicates that the template is to be converted to a virtual machine. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VApp

This cmdlet modifies the specified vApp.

**Returns**: `VApp`

```
Set-VApp
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
    [-Server <VIServer[]>]
    -VApp <VApp[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CpuExpandableReservation` | `Boolean` | No | Indicates that the CPU reservation can grow beyond the specified value if there are available resources. |
| `-CpuLimitMhz` | `Int64` | No | Specifies a CPU usage limit in MHz. If this parameter is set, utilization will not exceed this limit even if there are available resources. |
| `-CpuReservationMhz` | `Int64` | No | Specifies the guaranteed available CPU in MHz. |
| `-CpuSharesLevel` | `SharesLevel` | No | Specifies the CPU allocation level for this vApp. This property is used in relative allocation between resource consumers. This parameter accepts Custom, High, Low, and Normal values. |
| `-MemExpandableReservation` | `Boolean` | No | Indicates that the memory reservation can grow beyond the specified value if there are available resources. |
| `-MemLimitGB` | `Decimal` | No | Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources. |
| `-MemLimitMB` | `Int64` | No | This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are ava... |
| `-MemReservationGB` | `Decimal` | No | Specifies the guaranteed available memory in gigabytes (GB). |
| `-MemReservationMB` | `Int64` | No | This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB). |
| `-MemSharesLevel` | `SharesLevel` | No | Specifies the memory allocation level for the vApp. This property is used in relative allocation between resource consumers. This cmdlet accepts Custom, High, Low, and Normal values. |
| `-Name` | `String` | No | Modifies the name of the vApp. |
| `-NumCpuShares` | `Int32` | No | Specifies the CPU allocation level for the vApp. This property is used in relative allocation between resource consumers. This parameter is ignored unless the CpuSharesLevel parameter is set to Cus... |
| `-NumMemShares` | `Int32` | No | Specifies the memory allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless the MemSharesLevel parameter i... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VApp` | `VApp[]` | Yes | Specifies the vApp that you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Start-VApp

This cmdlet starts vApps.

**Returns**: `VApp`

```
Start-VApp
    [-RunAsync]
    [-Server <VIServer[]>]
    -VApp <VApp[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VApp` | `VApp[]` | Yes | Specifies the vApp that you want to start. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Stop-VApp

This cmdlet stops vApps.

**Returns**: `VApp`

```
Stop-VApp
    [-Force]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VApp <VApp[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `SwitchParameter` | No | Indicates that the virtual machines are powered off regardless of the auto-start configuration of the vApps. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VApp` | `VApp[]` | Yes | Specifies the vApp that you want to stop. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

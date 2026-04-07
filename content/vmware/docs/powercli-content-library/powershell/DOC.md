---
name: powercli-content-library
description: "VMware PowerCLI 13.3 — Content libraries, library items, OVF import/export"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,content-library,Copy-ContentLibraryItem, Export-ContentLibraryItem, Export-VApp, Get-ContentLibrary, Get-ContentLibraryItem, Get-OvfConfiguration, Import-VApp, New-ContentLibrary, New-ContentLibraryItem, Remove-ContentLibrary, Remove-ContentLibraryItem, Set-ContentLibrary, Set-ContentLibraryItem"
---

# VMware PowerCLI — Content Library

Content libraries, library items, OVF import/export. Module: VMware.VimAutomation (13 cmdlets).

## Copy

### `Copy-ContentLibraryItem`

**This cmdlet copies content library items to a local content library.**

**Parameters:**

- -ContentLibraryItem [ContentLibraryItem[]] (Required) Specifies the content library item that you want to copy.
- -Destination [LocalContentLibrary] (Required) Specifies the local content library where you want to copy the item.
- -Name [String] (Optional) Specifies the name on the library item. Library item names cannot be undefined or an empty string. Names do not have to be unique.   Note: If not specified, the name of the source content library item will be used.
- -Notes [String] (Optional) Specifies a human-readable description for the content library item that you want to copy.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$item = Get-ContentLibraryItem -Name 'vm1'
$library = Get-ContentLibrary -Name 'Local content library' -Local
Copy-ContentLibraryItem -ContentLibraryItem $item -Destination $library
```
_Copies a content library item named 'vm1' to the 'Local content library' content library._

## Export

### `Export-ContentLibraryItem`

**This cmdlet exports content library item's files to the local machine.**

**Parameters:**

- -ContentLibraryItem [ContentLibraryItem[]] (Required) Specifies the content library item whose content you want to export.
- -Destination [String] (Optional) Specifies an existing local directory where you want to save the content library items.   Note: If the parameter is not specified, your current directory will be used.
- -Force [SwitchParameter] (Optional) Specifies if you want to overwrite existing files with the same name that exist in the destination directory.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$item = Get-ContentLibraryItem -Name 'vm1'
Export-ContentLibraryItem -ContentLibraryItem $item -Destination ./vm1-files
```
_Exports 'vm1' content library item's files to the C:\vm1-files directory._

### `Export-VApp`

**This cmdlet exports a vApp or a single virtual machine to the specified destination.**

This cmdlet exports a vApp or a single virtual machine to the specified destination. If no destination is specified, the cmdlet creates a new folder in the current working directory and exports the vApp or the virtual machine to it. The name of the new folder is the same as the name of the vApp or the virtual machine as it appears in vCenter Server.

**Parameters:**

- -CreateSeparateFolder [SwitchParameter] (Optional) Indicates that you want to create a separate folder for each vApp or virtual machine.
- -Description [String] (Optional) Provides a description of the exported vApp or virtual machine.
- -Destination [String] (Optional) Specifies a destination path to the file system location where you want to export the vApp or the virtual machine. If the value of the Destination parameter is a folder, the vApp or the virtual machine is exported to a container folder (OVF). If the destination is a file, the vApp or the virtual machine is exported in OVA format.
- -Force [SwitchParameter] (Optional) Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path.
- -Format [VAppStorageFormat] (Optional) Specifies the file format of the specified vApp or virtual machine. The default format is OVF. The valid values are OVF and OVA.
- -Name [String] (Optional) Specifies a name for the exported vApp or virtual machine.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SHAAlgorithm [SHAAlgorithm] (Optional) Specifies the hashing algorithm that you want to use in the manifest checksums. The default value is SHA256. The valid values are SHA256 and SHA1.
- -VApp [VApp[]] (Required) Specifies the vApp that you want to export.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machine that you want to export.

**Examples:**

```powershell
Get-VApp -Name "MyVApp*" | Export-VApp -Destination "C:\vapps\"
```
_Retrieves all vApps whose names start with "MyVApp" and exports them to the specified path._

```powershell
$myVApp = Get-VApp -Name "MyVApp1"
Export-VApp -Destination "C:\NewFolder\" -VApp $myVApp -Name "EMail_vApp" -Force
```
_Exports the vApp in the $myVApp variable to the specified location and assigns a name to the folder._

```powershell
$myVApp = Get-VApp -Name "MyVApp1"
Export-VApp -vApp $myVApp -Destination "C:\vapps\Vapp\" -Force -CreateSeparateFolder:$false
```
_Exports the vApp in the $myVApp variable to the specified location without creating a separate folder for each virtual appliance._

## Get

### `Get-ContentLibrary`

**This cmdlet creates a new local or subscribed content library.**

This cmdlet retrieves content libraries and returns a set of content libraries that correspond to the filter criteria defined by the cmdlet parameters.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the content libraries you want to retrieve.
- -Local [SwitchParameter] (Optional) Specifies that you want to retrieve only the local content libraries.
- -Name [String[]] (Optional) Specifies the names of the content libraries you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Subscribed [SwitchParameter] (Optional) Specifies that you want to retrieve only the subscribed content libraries.

**Examples:**

```powershell
Get-ContentLibrary
```
_Retrieves all content libraries from the default connected servers._

```powershell
Get-ContentLibrary -Local
```
_Returns all local content libraries from the default connected servers._

```powershell
Get-ContentLibrary -Name 'Local*'
```
_Retrieves all content libraries whose name starts with 'Local' from the default connected servers._

### `Get-ContentLibraryItem`

**This cmdlet retrieves catalog items from the content library.**

This cmdlet retrieves catalog items from the content library and returns a set of catalog items that correspond to the filter criteria defined by the cmdlet parameters.

**Parameters:**

- -ContentLibrary [ContentLibrary[]] (Optional) Filters items by ContentLibrary.
- -Id [String[]] (Required) Specifies the IDs of the catalog items you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects have an ID that matches exactly one of the string values in that list.
- -ItemType [String[]] (Optional) Filters the catalog items by type.
- -Name [String[]] (Optional) Specifies the names of the catalog items you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-ContentLibraryItem -Type "OVF" -Name "Windows*"
```
_Retrieves content library templates of the specified type that match the specified name._

### `Get-OvfConfiguration`

**This cmdlet retrieves the OVF configuration object from the specified OVF, OVA, or content library item.**

This cmdlet retrieves the OVF configuration object from the specified OVF, OVA, or content library item. Only user-configurable properties are returned.

**Parameters:**

- -ContentLibraryItem [ContentLibraryItem] (Required) Specifies the content library item to retrieve the OVF configuration from.
- -Ovf [String] (Required) Specifies the local path to the OVF or OVA package for which the user-configurable options are returned. URL paths are not supported.
- -Target [VIContainer] (Required) Specifies the location (target) to which you want to deploy the OVF package. The target can be a an object of type VMHost, ResourcePool, Cluster, or VApp.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$datastore = Get-Datastore -Name 'MyDatastore'
$ovfPath = "myOvfTemplate.ovf"

$ovfConfig = Get-OvfConfiguration -Ovf $ovfPath
$ovfConfig.NetworkMapping.VM_Network.Value = 'VM Network'

Import-VApp -Name 'myVApp' -Source $ovfPath -OvfConfiguration $ovfConfig -VMHost $vmHost -Datastore $datastore
```
_Modifies a specific OVF property and passes it to the Import-VApp cmdlet._

```powershell
$datastore = Get-Datastore -Name 'MyDatastore'
$contentLibraryItem = Get-ContentLibraryItem -Name 'MyContentLibraryItem'
$target = Get-VMHost -Name 'MyVMHost'

$ovfConfig = Get-OvfConfiguration -ContentLibraryItem $contentLibraryItem -Target $target
$ovfConfig.EULAs.Accept.Value = $true
$ovfConfig.Common.vamitimezone.Value = 'US/Pacific'

New-VM -Name 'myVM' -ContentLibraryItem $contentLibraryItem -OvfConfiguration $ovfConfig -VMHost $target -Datastore $datastore
```
_Specifies a content library item, sets the OVF parameters, and deploys a new virtual machine from specified content library item._

## Import

### `Import-VApp`

**This cmdlet imports OVF (Open Virtualization Format) and OVA packages. The package can contain a virtual appliance or a virtual machine.**

This cmdlet imports OVF (Open Virtualization Format) and OVA packages. The package can contain a vApp or a virtual machine. The cmdlet returns a VApp object when the OVF contains a vApp and a VirtualMachine object when the OVF contains a single virtual machine.

**Parameters:**

- -Datastore [StorageResource] (Optional) Specifies a datastore or a datastore cluster where you want to store the vApp or virtual machine.
- -DiskStorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the storage format for the disks of the imported VMs. By default, the storage format is thick. When you set this parameter, you set the storage format for all virtual machine disks in the OVF package. This parameter accepts Thin, Thick, and EagerZeroedThick values.
- -Force [SwitchParameter] (Optional) Indicates that you want to import an OVF or OVA package even if the package signature cannot be verified or if the checksum validation algorithm is not supported.
- -InventoryLocation [FolderContainer] (Optional) Specifies a datacenter or a virtual machine folder where you want to place the new vApp. This folder serves as a logical container for inventory organization. The Location parameter serves as a compute resource that powers the imported vApp.
- -Location [VIContainer] (Optional) Specifies a vSphere inventory container where you want to import the vApp or virtual machine. It must be a vApp, a resource pool, or a cluster.
- -Name [String] (Optional) Specifies a name for the imported vApp or virtual machine.
- -OvfConfiguration [Hashtable] (Optional) Specifies values for a set of user-configurable OVF properties.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Source [String] (Required) Specifies the path to the OVF or OVA package that you want to import.
- -VMHost [VMHost] (Required) Specifies a host where you want to run the vApp or virtual machine.

**Examples:**

```powershell
$vmHost = Get-VMHost -Name "MyVMHost1"
Import-vApp -Source "c:\vApps\WebServer\WebServer.ovf" -VMHost $vmHost
```
_Imports an OVF package by specifying the target host and name._

```powershell
$myCluster = Get-Cluster -Name "MyCluster1"
$vmHost = Get-VMHost -Name "MyVMHost1"
Import-vApp -Source "c:\vApps\WebServer\WebServer.ovf" -VMHost $vmHost -Location $myCluster -Name "MyWebServerProduction1"
```
_Imports an OVF package within a cluster._

```powershell
$vmHost = Get-VMHost -Name "MyVMHost1"
$myDatastore = Get-Datastore -Name "MyDatastore1"
$vmHost | Import-vApp -Source "c:\vApps\WebServer\WebServer.ovf" -Datastore $myDatastore
```
_Imports an OVF package by specifying a datastore where to store the virtual machines._

## New

### `New-ContentLibrary`

**Creates a new local or subscribed content library that uses Datastore1 as a repository for its items.**

This cmdlet creates a new new local or subscribed content library depending on the provided parameters.

**Parameters:**

- -AutomaticSync [SwitchParameter] (Optional) Specifies whether the library should participate in automatic library synchronization. If you want to do an automatic synchronization, the global Automatic Sync option must be enabled.   The subscription is still active even when automatic synchronization is turned off, but synchronization is only done manually by using the -Sync parameter of the Set-ContentLibrary cmdlet.
- -Datastore [Datastore] (Required) Specifies the datastore that you want to use to store files for library items in this library.
- -Description [String] (Optional) Specifies a human-readable description for the content library that you want to create.
- -DownloadContentOnDemand [SwitchParameter] (Optional) Indicates whether a library item's content is synchronized only on demand.   If specified, then the library item's metadata is synchronized but the item's content (its files) is not. The Content Library Service synchronizes the content upon request only. This can cause the first use of the content to have a noticeable delay.   If not specified, all content is synchronized in advance.
- -Name [String] (Required) Specifies the name of the library. Library names cannot be undefined or an empty string. Names do not have to be unique.
- -OptimizeRemotePublishing [SwitchParameter] (Optional) If specified, the library is optimized for remote publishing and the Published parameter is required.   This parameter specifies if remote publishing is the dominant use case for this library. The remote publishing occurs when the publisher and subscribers are not part of the same vCenter Single Sign-On domain.   Any optimizations can be done as a result of turning on this optimization during library creation. For example, library content could be stored in different formats, but optimizations are not limited to just a storage format.   You can set the value of this toggle only during the creation of the library and you need to migrate your library in case you need to change this value (optimize the library for a different use case).
- -Password [String] (Optional) Specifies the password you want to use for the content library.   If you want to create a local content library, the password is required from subscribers in Basic authentication mode.   If you want to subscribe to a content library, the password should be in Basic authentication mode.
- -PersistJson [SwitchParameter] (Optional) Specifies whether library and library item metadata are persisted in the storage location as JSON files. This flag only applies if the local library is published.   You can copy the local library content and metadata to another storage location manually and then create a subscribed library referencing the location of the library JSON file in the SubscriptionUrl. When the subscribed library's storage location matches the subscription URL, you do not need to copy the files to the subscribed library.
- -Published [SwitchParameter] (Optional) Specifies whether you need to publish the local library.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SslThumbprint [String] (Optional) Specifies an optional SHA-1 hash of the SSL certificate for the remote endpoint.   If this value is defined, the SSL certificate is verified by comparing it to the SSL thumbprint. The SSL certificate must be verified against the thumbprint. When specified, the standard certificate chain validation behavior is not used.   The certificate chain is validated normally if this value is unset.
- -SubscriptionUrl [String] (Required) Specifies the URL of the endpoint where the metadata for the remotely published library is served.

**Examples:**

```powershell
New-ContentLibrary -Name 'Local Content Library' -Description 'Local content library description.' -Datastore $Datastore1 -Published
```
_Creates a new local content library that uses Datastore1 as a repository for its items._

```powershell
$localContentLibrary = Get-ContentLibrary -Name 'Local Content Library' -Local
New-ContentLibrary -Name 'Subscribed Content Library' -Description 'Subscribed content library description.' -Datastore $Datastore1 -SubscriptionUrl $localContentLibrary.PublishUrl
```
_Creates a new subscribed content library that is subscribed to $localContentLibrary and uses Datastore1 as a repository for its items._

### `New-ContentLibraryItem`

**This cmdlet creates a new content library item in the specified content library.**

This cmdlet creates a new content library item in the specified content library. If the Files parameter is specified, you can add the specified files to the newly created content library item.

**Parameters:**

- -ContentLibrary [LocalContentLibrary] (Required) Specifies a local content library that hosts the content library item.
- -Datastore [Datastore] (Optional) Specifies a datastore where you want to place the new virtual machine template.
- -FileName [String[]] (Required) Specifies a list of file names that you want to use for the file pulled by the content library item from the URI specified in the Uri parameter.
- -Files [String[]] (Optional) Specifies the paths to local or remote files that you want to add to the newly created content library item.
- -InventoryLocation [FolderContainer] (Optional) Specifies a data center or a virtual machine folder where you want to place the new virtual machine template.
- -ItemType [String] (Optional) Specifies the type of the library item.
- -Location [VIContainer] (Required) Specifies a VApp, ResourcePool, VMHost, or Cluster object where you want to place the new virtual machine template.
- -Name [String] (Required) Specifies the name of the library item. The library item names cannot be undefined or an empty string. Names do not have to be unique.
- -Notes [String] (Optional) Specifies a human-readable description for the content library item that you want to create.
- -VApp [VApp] (Optional) Specifies a VApp object from which to create the OVF template in the content library.
- -VM [VirtualMachine] (Required) Specifies a virtual machine from which to create the virtual machine or OVF template in the content library.
- -VMTemplate [SwitchParameter] (Required) If the value is $true, a virtual machine template is created in the content library.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -DisableOvfCertificateChecks [SwitchParameter] (Optional) Specifies to skip all OVA/OVF certificate checks during the upload to the content library item.
- -SslThumbprint [String] (Optional) Specifies the SSL thumbprint of the server hosting the file specified by the URI in the Uri parameter.
- -StoragePolicy [StoragePolicy] (Optional) Specifies the storage policy for the new virtual machine template in the content library.
- -Template [Template] (Optional) Specifies a virtual machine template from which to create the OVF template in the content library.
- -Uri [String[]] (Required) Specifies a list of URIs of the file that you want to pull into the content library item.   Note: http://, https://, and ds:// uris are acceptable.

**Examples:**

```powershell
$files = Get-ChildItem -File
$localContentLibrary = Get-ContentLibrary -name 'Local content library' -Local
New-ContentLibraryItem -ContentLibrary $localContentLibrary -name 'New item' -Files $files
```
_Creates a content library item named 'New item' in the 'Local content library' library, containing all the files from the C: directory._

```powershell
$files = Get-ChildItem -Name '*.ps1' -File
$localContentLibrary = Get-ContentLibrary -Name 'Local content library' -Local
New-ContentLibraryItem -ContentLibrary $localContentLibrary -Name 'New item' -ItemType 'script' -Files $files
```
_Creates a content library item named 'New item' in the 'Local content library' library, containing all PowerShell script files from the C: directory. The type of the content library item is 'script'._

```powershell
$datastore = Get-Datastore -Name 'Datastore'
$localContentLibrary = Get-ContentLibrary -Name 'Local content library' -Local
New-ContentLibraryItem -ContentLibrary $localContentLibrary -Name 'New item' -Uri ($datastore.ExtensionData.Info.Url + 'ISOs/Photon-minimal-3.0.iso') -FileName 'Photon-minimal-3.0.iso'
```
_Creates a content library item named 'New item' in the 'Local content library' library, containing a 'Photon-minimal-3.0.iso' file from the 'Datastore' datastore._

## Remove

### `Remove-ContentLibrary`

**This cmdlet removes the specified content libraries.**

**Parameters:**

- -ContentLibrary [ContentLibrary[]] (Required) Specifies the content libraries you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$libraries = Get-ContentLibrary -Name '*obsolete'
Remove-ContentLibrary $libraries
```
_Removes all content libraries whose names end in 'obsolete' from the default connected servers._

### `Remove-ContentLibraryItem`

**This cmdlet removes the specified content library items.**

**Parameters:**

- -ContentLibraryItem [ContentLibraryItem[]] (Required) Specifies the content library items you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Remove-ContentLibraryItem -ContentLibraryItem '*obsolete'
```
_Permanently deletes all content library items whose names end in 'obsolete' from the default connected servers._

## Set

### `Set-ContentLibrary`

**This cmdlet modifies content library's properties.**

**Parameters:**

- -AutomaticSync [SwitchParameter] (Optional) If specified, synchronization of content library items happens automatically. If not, synchronization happens by using the Set-ContentLibrary cmdlet with the Sync parameter.
- -CurrentPassword [String] (Optional) Indicates if you want to update a password protected content library. Currently set password is supplied to complete the operation.   Note: Available on vCenter Server 6.7 and later.
- -Description [String] (Optional) Specifies a human-readable description for the content library that you want to create.
- -DisableAuthentication [SwitchParameter] (Optional) If specified, deactivates authentication of the content library.
- -DownloadContentOnDemand [SwitchParameter] (Optional) Indicates whether a library item's content is synchronized only on demand.   If specified, the library item's metadata is synchronized, but the item's content (its files) is not synchronized. The Content Library Service  synchronizes the content upon request only. This can cause a noticeable delay when using the content for the first time.   If not specified, all content is synchronized in advance.
- -Evict [SwitchParameter] (Required) Removes cached content library's items content of a subscribed content library whose content is downloaded on demand.
- -LocalContentLibrary [LocalContentLibrary[]] (Required) A local content library whose properties you want to alter.
- -Name [String] (Optional) Specifies a new name for the content library.
- -Password [String] (Optional) Specifies the password that you want to set or update to the target content library.
- -PersistJson [SwitchParameter] (Optional) Specifies whether library and library item metadata are persisted in the storage location as JSON files. This flag only applies if you want to publish the local library.   Enabling JSON persistence allows you to synchronize a subscribed library manually instead of over HTTP. You can copy the local library content and metadata to another storage location manually and then create a subscribed library referencing the location of the library JSON file in the SubscriptionUrl. When the subscribed library's storage location matches the subscription URL, you do not need to copy the files to the subscribed library.
- -Published [SwitchParameter] (Optional) Specifies whether you want to publish the local library.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no given is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SslThumbprint [String] (Optional) Specifies an optional SHA-1 hash of the SSL certificate for the remote endpoint.   If this value is defined, the SSL certificate is verified by comparing it to the SSL thumbprint. The SSL certificate must be verified against the thumbprint. When specified, the standard certificate chain validation behavior is not used.   The certificate chain is validated normally if this value is unset.
- -SubscribedContentLibrary [SubscribedContentLibrary[]] (Required) Specifies a subscribed content library which properties you want to alter.
- -SubscriptionUrl [String] (Optional) Specifies the URL of the endpoint where the metadata for the remotely published library is served.
- -Sync [SwitchParameter] (Required) If specified, manually synchronizes the subscribed content library.

**Examples:**

```powershell
$contentLibrary = Get-ContentLibrary -Name 'Content Library' -Local
Set-ContentLibrary -LocalContentLibrary $contentLibrary -Name 'Local Content Library' -Description 'This is local content library.'
```
_Modifies a local content library named 'Content Library' by changing its name to 'Local Content Library' and its description to 'This is local content library.'._

```powershell
$subscribedContentLibrary = Get-ContentLibrary -Name 'Content Library' -Subscribed
Set-ContentLibrary -SubscribedContentLibrary $subscribedContentLibrary -Sync
```
_Manually synchronizes a subscribed content library named 'Content Library'._

```powershell
$subscribedContentLibrary = Get-ContentLibrary -Name 'Content Library' -Subscribed
Set-ContentLibrary -SubscribedContentLibrary $subscribedContentLibrary -Evict
```
_Removes cached content library items' content of subscribed content library that has -DownloadContentOnDemand set._

### `Set-ContentLibraryItem`

**This cmdlet modifies content library item's properties.**

This cmdlet modifies the properties of a content library item.

**Parameters:**

- -ClearExistingFiles [SwitchParameter] (Optional) Indicates that if there are any files in the content library item, they will be removed before uploading the new ones.
- -ContentLibraryItem [ContentLibraryItem[]] (Required) Specifies the content library item whose properties you want to change.
- -FileName [String[]] (Required) Specifies a list of file names that you want to use for the file pulled by the content library item from the URI specified in the Uri parameter.
- -Files [String[]] (Optional) Specifies the paths to the local files that substitute the current content library item's files.   Note: If the Files parameter is not specified, the content library item's files do not get altered.
- -ItemType [String] (Optional) Specifies the type of the library item.
- -Name [String] (Optional) Specifies a new name for the content library item.
- -Notes [String] (Optional) Specifies a new description for the content library item.
- -VApp [VApp] (Optional) Specifies a VApp object to overwrite the original content of the OVF template content library item.
- -VM [VirtualMachine] (Optional) Specifies a virtual machine to overwrite the original content of the OVF template content library item.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -DisableOvfCertificateChecks [SwitchParameter] (Optional) Specifies to skip all OVA/OVF certificate checks during the upload to the content library item.
- -SslThumbprint [String] (Optional) Specifies the SSL thumbprint of the server hosting the file specified by the URI in the Uri parameter.
- -Template [Template] (Optional) Specifies a virtual machine template to overwrite the original content of the OVF template content library item.
- -Uri [String[]] (Required) Specifies a list of URIs of the file that you want to pull into the content library item.   Note: http://, https://, and ds:// uris are acceptable.

**Examples:**

```powershell
$files = Get-ChildItem -File
$item = Get-ContentLibraryItem -Name 'vm1'
Set-ContentLibraryItem -ContentLibraryItem $item -Name 'New name' -Files $files
```
_Modifies the content library item named 'vm1' by setting its name to 'New name' and updates its files to the current content of the C: directory._

```powershell
$item = Get-ContentLibraryItem -Name 'vm1'
Set-ContentLibraryItem -ContentLibraryItem $item -ItemType 'file'
```
_Modifies the content library item named 'vm1' by setting its type to 'file'._

```powershell
$item = Get-ContentLibraryItem -Name 'vm1'
Set-ContentLibraryItem -ContentLibraryItem $item -Uri 'http://10.23.112.235:81/ISOs/Photon-minimal-3.0.iso' -FileName 'Photon-minimal-3.0.iso'
```
_Modifies the content library item named 'vm1' by adding the 'Photon-minimal-3.0.iso' file from the specified URI._

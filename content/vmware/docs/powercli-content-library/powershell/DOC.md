---
name: powercli-content-library
description: "VMware PowerCLI 13.3 — Content libraries, library items, OVF import/export"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,content-library,Copy-ContentLibraryItem, Export-ContentLibraryItem, Export-VApp, Get-ContentLibrary, Get-ContentLibraryItem, Get-OvfConfiguration, Import-VApp, New-ContentLibrary, New-ContentLibraryItem, Remove-ContentLibrary, Remove-ContentLibraryItem, Set-ContentLibrary, Set-ContentLibraryItem"
---

# VMware PowerCLI — Content Library

Content libraries, library items, OVF import/export. Module: VMware.VimAutomation (13 cmdlets).

## Cmdlet Reference (13 cmdlets)

### Copy

#### `Copy-ContentLibraryItem`

This cmdlet copies content library items to a local content library.

**Parameters**: `ContentLibraryItem, Destination, Name, Notes, Server`

### Export

#### `Export-ContentLibraryItem`

This cmdlet exports content library item's files to the local machine.

**Parameters**: `ContentLibraryItem, Destination, Force, RunAsync, Server`

#### `Export-VApp`

This cmdlet exports a vApp or a single virtual machine to the specified destination.

**Parameters**: `Destination, VApp, VM, Name, Force, Format, CreateSeparateFolder, Description, SHAAlgorithm, Server, RunAsync`

### Get

#### `Get-ContentLibrary`

This cmdlet creates a new local or subscribed content library.

**Parameters**: `Name, Id, Local, Subscribed, Server`

#### `Get-ContentLibraryItem`

This cmdlet retrieves catalog items from the content library.

**Parameters**: `Id, Name, ItemType, ContentLibrary, Server`

#### `Get-OvfConfiguration`

This cmdlet retrieves the OVF configuration object from the specified OVF, OVA, or content library item.

**Parameters**: `Ovf, ContentLibraryItem, Target, Server`

### Import

#### `Import-VApp`

This cmdlet imports OVF (Open Virtualization Format) and OVA packages. The package can contain a virtual appliance or a virtual machine.

**Parameters**: `Source, OvfConfiguration, Name, Location, InventoryLocation, VMHost, Datastore, Force, DiskStorageFormat, Server, RunAsync`

### New

#### `New-ContentLibrary`

Creates a new local or subscribed content library that uses Datastore1 as a repository for its items.

**Parameters**: `OptimizeRemotePublishing, Published, PersistJson, Description, Name, SslThumbprint, SubscriptionUrl, Password, AutomaticSync, Datastore, DownloadContentOnDemand, Server`

#### `New-ContentLibraryItem`

This cmdlet creates a new content library item in the specified content library.

**Parameters**: `ContentLibrary, Name, Notes, Files, Uri, FileName, SslThumbprint, ItemType, VM, Location, Datastore, StoragePolicy` (+6 more)

### Remove

#### `Remove-ContentLibrary`

This cmdlet removes the specified content libraries.

**Parameters**: `ContentLibrary, Server`

#### `Remove-ContentLibraryItem`

This cmdlet removes the specified content library items.

**Parameters**: `ContentLibraryItem, Server`

### Set

#### `Set-ContentLibrary`

This cmdlet modifies content library's properties.

**Parameters**: `Published, PersistJson, LocalContentLibrary, AutomaticSync, Description, Name, SslThumbprint, SubscriptionUrl, DisableAuthentication, Sync, SubscribedContentLibrary, Evict` (+4 more)

#### `Set-ContentLibraryItem`

This cmdlet modifies content library item's properties.

**Parameters**: `ContentLibraryItem, Name, Notes, Files, Uri, FileName, SslThumbprint, ClearExistingFiles, ItemType, VM, Template, VApp` (+2 more)

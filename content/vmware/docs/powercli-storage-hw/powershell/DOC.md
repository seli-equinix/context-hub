---
name: powercli-storage-hw
description: "VMware PowerCLI 13.3 — VM storage hardware: hard disks, SCSI controllers, CD/DVD drives, floppy, USB"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Add-PassthroughDevice,Copy-HardDisk,Get-CDDrive,Get-FloppyDrive,Get-HardDisk,Get-PassthroughDevice,Get-ScsiController,Get-ScsiLun,Get-ScsiLunPath,Get-UsbDevice,Move-HardDisk,New-CDDrive,New-FloppyDrive,New-HardDisk,New-ScsiController,Remove-CDDrive,Remove-FloppyDrive,Remove-HardDisk,Remove-PassthroughDevice,Remove-UsbDevice,Set-CDDrive,Set-FloppyDrive,Set-HardDisk,Set-ScsiController,Set-ScsiLun,Set-ScsiLunPath"
---

# VMware PowerCLI — VM storage hardware

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-PassthroughDevice` | This cmdlet attaches pass-through devices to the specified virtual machine. |
| `Copy-HardDisk` | Copies a virtual hard disk to another destination. |
| `Get-CDDrive` | This cmdlet retrieves virtual CD drives. |
| `Get-FloppyDrive` | This cmdlet retrieves the virtual floppy drives available on a vCenter Server system. |
| `Get-HardDisk` | This cmdlet retrieves the virtual hard disks available on a vCenter Server system. |
| `Get-PassthroughDevice` | This cmdlet retrieves the pass-through devices available on the specified hosts, virtual machines... |
| `Get-ScsiController` | This cmdlet retrieves the virtual SCSI controllers assigned to the specified HardDisk, VirtualMac... |
| `Get-ScsiLun` | This cmdlet retrieves the SCSI devices available on the vCenter Server system. |
| `Get-ScsiLunPath` | This cmdlet retrieves the list of vmhba paths to a specified SCSI device. |
| `Get-UsbDevice` | This cmdlet retrieves the USB devices available on a vCenter Server system. |
| `Move-HardDisk` | This cmdlet moves a hard disk from one location to another. |
| `New-CDDrive` | This cmdlet creates a new virtual CD drive. |
| `New-FloppyDrive` | This cmdlet creates a new virtual floppy drive. |
| `New-HardDisk` | This cmdlet creates a new hard disk on the specified location. |
| `New-ScsiController` | This cmdlet creates a new SCSI controller. |
| `Remove-CDDrive` | This cmdlet removes virtual CD drives from their locations. |
| `Remove-FloppyDrive` | This cmdlet removes the virtual floppy drives from their locations. |
| `Remove-HardDisk` | This cmdlet removes the specified virtual hard disks. |
| `Remove-PassthroughDevice` | This cmdlet removes the specified pass-through devices. |
| `Remove-UsbDevice` | This cmdlet removes the specified USB devices from a virtual machine. |
| `Set-CDDrive` | This cmdlet modifies the configuration of a virtual CD drive. |
| `Set-FloppyDrive` | This cmdlet modifies the configuration of the specified virtual floppy drive. |
| `Set-HardDisk` | This cmdlet modifies the properties of the specified virtual hard disk. |
| `Set-ScsiController` | This cmdlet modifies the specified SCSI controllers. |
| `Set-ScsiLun` | This cmdlet modifies the configuration of a SCSI device. |
| `Set-ScsiLunPath` | This cmdlet configures a vmhba path to a SCSI device. |

---

### Add-PassthroughDevice

This cmdlet attaches pass-through devices to the specified virtual machine.

This cmdlet attaches pass-through devices to the specified virtual machine. Note that the value of the ControllerKey property of the returned device might not be up to date, if a new SCSI controller creation process  is running in the background.

**Returns**: `PassthroughDevice`

```
Add-PassthroughDevice
    -PassthroughDevice <PassThroughDevice[]>
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PassthroughDevice` | `PassThroughDevice[]` | Yes | Specifies the passthrough devices you want to add to the virtual machine. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machine to which you want to attach the passthrough devices. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Copy-HardDisk

Copies a virtual hard disk to another destination.

Copies a virtual hard disk to another destination specified by the DestinationPath parameter. DestinationPath must be a datastore path to the destination folder.

**Returns**: `HardDisk`

```
Copy-HardDisk
    -DestinationPath <String>
    [-DestinationStorageFormat <VirtualDiskStorageFormat>]
    [-Force]
    -HardDisk <HardDisk[]>
    [-RunAsync]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DestinationPath` | `String` | Yes | Specifies the datastore path to the folder where you want to copy the hard disk. The datastore name is included in the path in square braces. |
| `-DestinationStorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the type of the hard disk copy. The valid values are Thin, Thick, and EagerZeroedThick. This parameter is only applicable when you are connected to an ESX/ESXi host. |
| `-Force` | `SwitchParameter` | No | Indicates whether to overwrite all disks with the same name at the provided destination. |
| `-HardDisk` | `HardDisk[]` | Yes | Specifies the virtual hard disk you want to copy. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-CDDrive

This cmdlet retrieves virtual CD drives.

This cmdlet returns a set of virtual CD drives  that belong to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Returns**: `CDDrive`

```
Get-CDDrive
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Snapshot <Snapshot[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the CD drives you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the strin... |
| `-Name` | `String[]` | No | Specifies the names of the CD drives you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snapshot` | `Snapshot[]` | No | Specifies the snapshots from which you want to retrieve virtual CD drives. |
| `-Template` | `Template[]` | No | Specifies the virtual machine templates from which you want to retrieve virtual CD drives. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines from which you want to retrieve virtual CD drives. |

---

### Get-FloppyDrive

This cmdlet retrieves the virtual floppy drives available on a vCenter Server system.

This cmdlet retrieves the virtual floppy drives available on a vCenter Server system. Returns a set of virtual floppy drives that belong to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Returns**: `FloppyDrive`

```
Get-FloppyDrive
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Snapshot <Snapshot[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the floppy drives you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the s... |
| `-Name` | `String[]` | No | Specifies the names of the floppy drives you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snapshot` | `Snapshot[]` | No | Specifies the snapshots from which you want to retrieve virtual CD drives. |
| `-Template` | `Template[]` | No | Specifies the templates from which you want to retrieve virtual CD drives. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines from which you want to retrieve virtual floppy drives. |

---

### Get-HardDisk

This cmdlet retrieves the virtual hard disks available on a vCenter Server system.

This cmdlet returns the virtual hard disks available on a vCenter Server system. You can retrieve a hard disk by specifying the virtual machines, templates, or snapshots to which it belongs. If the hard disk is not attached to any virtual machines, templates, or snapshots, you can search for it in datastores or retrieve it by providing a datastore path to the file where the virtual hard disk is stored. In this case, you might not be able to derive disk type info, and the value of the DiskType...

**Returns**: `HardDisk`

```
Get-HardDisk
    -Datastore <Datastore[]>
    [-DatastorePath <String[]>]
    [-DiskType <DiskType[]>]
    [-Id <String[]>]
    [-Name <String[]>]
    [-Path <DatastoreItem[]>]
    -RelatedObject <HardDiskRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Snapshot <Snapshot[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
    -VMGuestDisk <VMGuestDisk[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `Datastore[]` | Yes | Specifies the datastores or datastore clusters you want to search for hard disks. This parameter is required when retrieving a hard disk that is attached to no virtual machines, templates, or snaps... |
| `-DatastorePath` | `String[]` | No | Specifies datastore paths to the hard disks you want to retrieve. The paths must be in the following format: [datastore_name] <file_path>, where [datastore_name] is the name of the datastore in squ... |
| `-DiskType` | `DiskType[]` | No | Specifies the type of the hard disks you want to retrieve. The valid values are rawVirtual, rawPhysical, flat, and unknown. If the hard disk is not attached to any virtual machines, templates, or s... |
| `-Id` | `String[]` | No | Specifies the IDs of the hard disks you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the stri... |
| `-Name` | `String[]` | No | Specifies the names of the SCSI hard disks you want to retrieve. |
| `-Path` | `DatastoreItem[]` | No | Specifies the file paths to the virtual hard disks you want to retrieve. The cmdlet searches recursively the specified locations. |
| `-RelatedObject` | `HardDiskRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more HardDisk objects that are related to them. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snapshot` | `Snapshot[]` | No | Specifies the snapshots from which you want to retrieve the hard disks. |
| `-Template` | `Template[]` | No | Specifies the virtual machine templates from which you want to retrieve the hard disks. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines from which you want to retrieve the hard disks. |
| `-VMGuestDisk` | `VMGuestDisk[]` | Yes | Specifies the virtual machines guest disk from which you want to retrieve the hard disks. |

---

### Get-PassthroughDevice

This cmdlet retrieves the pass-through devices available on the specified hosts, virtual machines, and templates.

**Returns**: `PassthroughDevice`

```
Get-PassthroughDevice
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Template <Template[]>]
    [-Type <PassthroughDeviceType>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the pass-through devices you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one o... |
| `-Name` | `String[]` | No | Specifies the names of the pass-through devices you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Template` | `Template[]` | No | Specifies the virtual machine templates for which you want to retrieve the pass-through devices. |
| `-Type` | `PassthroughDeviceType` | No | Specifies the type of the pass-through devices you want to retrieve. The valid values are SCSI and PCI. PCI is supported only on vCenter Server 4.1 and ESX 4.1 and later. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines for which you want to retrieve the pass-through devices. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve the pass-through devices. |

---

### Get-ScsiController

This cmdlet retrieves the virtual SCSI controllers assigned to the specified HardDisk, VirtualMachine, Template, and Snapshot objects.

**Returns**: `ScsiController`

```
Get-ScsiController
    [-HardDisk <HardDisk[]>]
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Snapshot <Snapshot[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HardDisk` | `HardDisk[]` | No | Filters the SCSI controllers by the hard disks they belong to. |
| `-Id` | `String[]` | No | Specifies the IDs of the SCSI controllers you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of th... |
| `-Name` | `String[]` | No | Specifies the names of the SCSI controllers you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snapshot` | `Snapshot[]` | No | Filters the SCSI controllers by the snapshots they belong to. |
| `-Template` | `Template[]` | No | Filters the SCSI controllers by the virtual machine templates they belong to. |
| `-VM` | `VirtualMachine[]` | No | Filters the SCSI controllers by the virtual machines they belong to. |

---

### Get-ScsiLun

This cmdlet retrieves the SCSI devices available on the vCenter Server system.

This cmdlet retrieves the SCSI devices available on the vCenter Server system. Examples of SCSI logical unit objects include disks which may contain file system volumes or parts of volumes for the host or might serve as raw disks to a virtual machine. Other examples include SCSI passthrough devices that can be used by virtual machines. When retrieving ScsiLun objects by Datastore, the cmdlet returns a ScsiLun object for each host connected to the specified datastore. ScsiLun objects can be di...

**Returns**: `ScsiLun`

```
Get-ScsiLun
    [-CanonicalName <String[]>]
    -Datastore <Datastore[]>
    -Hba <Hba[]>
    -Id <String[]>
    [-Key <String[]>]
    [-LunType <String[]>]
    [-Server <VIServer[]>]
    -VmHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CanonicalName` | `String[]` | No | Specifies the canonical name of the SCSI devices you want to retrieve. An example of a SCSI canonical name for Windows is "vmhba0:0:0:0". |
| `-Datastore` | `Datastore[]` | Yes | Specifies the datastores for which you want to retrieve the SCSI devices. This parameter is supported only for VMFS volumes. |
| `-Hba` | `Hba[]` | Yes | Specifies the storage adapters for which you want to retrieve the SCSI devices. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the SCSI devices that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of t... |
| `-Key` | `String[]` | No | Specifies the linkable identifiers of the SCSI devices you want to retrieve. |
| `-LunType` | `String[]` | No | Specifies the type of the SCSI devices you want to retrieve. The following types are valid:   cdrom communications disk enclosure mediaChanger opticalDevice printer processor scanner storageArrayCo... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VmHost` | `VMHost[]` | Yes | Specifies the hosts from which you want to retrieve the virtual SCSI devices. |

---

### Get-ScsiLunPath

This cmdlet retrieves the list of vmhba paths to a specified SCSI device.

**Returns**: `ScsiLunPath`

```
Get-ScsiLunPath
    [-Name <String[]>]
    -ScsiLun <ScsiLun[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String[]` | No | Specifies the name of the SCSI device whose vmhba paths you want to retrieve. |
| `-ScsiLun` | `ScsiLun[]` | Yes | Specifies the SCSI device whose vmhba paths you want to retrieve. |

---

### Get-UsbDevice

This cmdlet retrieves the USB devices available on a vCenter Server system.

This cmdlet retrieves the USB devices available on a vCenter Server system. The cmdlet returns a set of virtual USB devices assigned to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Returns**: `UsbDevice`

```
Get-UsbDevice
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Snapshot <Snapshot[]>]
    [-Template <Template[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the USB devices you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the str... |
| `-Name` | `String[]` | No | Specifies the names of the USB devices you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snapshot` | `Snapshot[]` | No | Specifies the virtual machine snapshots whose virtual USB you want to retrieve. Supported only on vCenter Server 4.1 and ESX 4.1 and later. |
| `-Template` | `Template[]` | No | Specifies the virtual machine templates whose virtual USB drives you want to retrieve. |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose virtual USB drives you want to retrieve. |

---

### Move-HardDisk

This cmdlet moves a hard disk from one location to another.

**Returns**: `HardDisk`

```
Move-HardDisk
    -Datastore <StorageResource>
    -HardDisk <HardDisk[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-StorageFormat <VirtualDiskStorageFormat>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `StorageResource` | Yes | Specifies a datastore or ? datastore cluster to move ? hard disk to. If a datastore cluster is specified, the system checks whether the Storage Distributed Resource Scheduler (SDRS) is enabled and ... |
| `-HardDisk` | `HardDisk[]` | Yes | Specifies the hard disk that you want to move to another location. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the storage format of the relocated hard disk. This parameter accepts Thin, Thick, and EagerZeroedThick values. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-CDDrive

This cmdlet creates a new virtual CD drive.

This cmdlet creates a new virtual CD drive for each of the provided virtual machines. If an ISO location is provided, sets the CD to point to the ISO.

**Returns**: `CDDrive`

```
New-CDDrive
    -ContentLibraryIso <ContentLibraryItem>
    [-HostDevice <String>]
    [-IsoPath <String>]
    [-Server <VIServer[]>]
    [-StartConnected]
    -VM <VirtualMachine>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ContentLibraryIso` | `ContentLibraryItem` | Yes | Specifies the content library item of type ISO that you want to mount on the new CD drive. |
| `-HostDevice` | `String` | No | Specifies the path to the CD drive on the virtual machine host that backs the virtual CD drive. Do not set this parameter if the ISOPath parameter is set. |
| `-IsoPath` | `String` | No | Specifies the datastore path to the ISO (CD image) file that backs the virtual CD drive. Do not set this parameter if the HostDevice parameter is set. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StartConnected` | `SwitchParameter` | No | Indicates that the virtual CD drive starts connected when the virtual machine associated with it powers on. |
| `-VM` | `VirtualMachine` | Yes | Specifies the virtual machine to which the new virtual CD drive belongs. Passing multiple values to this parameter is obsolete. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-FloppyDrive

This cmdlet creates a new virtual floppy drive.

This cmdlet creates a new virtual floppy drive for each of the provided virtual machines. If a floppy image path is provided, sets the floppy drive to point to the image. If both the FloppyImagePath and HostDevice parameters are specified, an error is generated.

**Returns**: `FloppyDrive`

```
New-FloppyDrive
    [-FloppyImagePath <String>]
    [-HostDevice <String>]
    [-NewFloppyImagePath <String>]
    [-Server <VIServer[]>]
    [-StartConnected]
    -VM <VirtualMachine>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-FloppyImagePath` | `String` | No | Specifies the datastore path to the floppy image file backing the virtual floppy drive. Do not use this parameter together with the HostDevice parameter. |
| `-HostDevice` | `String` | No | Specifies the path to the floppy drive on the host which will back this virtual floppy drive. Do not use this parameter together with the FloppyImagePath parameter. |
| `-NewFloppyImagePath` | `String` | No | Specifies a new datastore path to a floppy image file backing the virtual floppy drive. Do not use this parameter together with the HostDevice parameter. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StartConnected` | `SwitchParameter` | No | Indicates that the virtual floppy drive starts connected when its associated virtual machine powers on. |
| `-VM` | `VirtualMachine` | Yes | Specifies the virtual machine to which you want to attach the new virtual floppy drive. Passing multiple values to this parameter is obsolete. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-HardDisk

This cmdlet creates a new hard disk on the specified location.

This cmdlet creates a new hard disk on the specified virtual machine or datastore. When a new virtual disk with raw disk mapping (RDM) backing is created, the compatibility mode of "virtual" or "physical" must be specified using the DiskType parameter. In "virtual" compatibility mode, the disk can use the specified disk modes. In "physical" compatibility mode, the disk modes are ignored and commands are passed directly to the backing Logical Unit Number (LUN). If "flat" mode is set by the Dis...

**Returns**: `HardDisk`

```
New-HardDisk
    [-AdvancedOption <AdvancedOption[]>]
    [-CapacityGB <Decimal>]
    [-CapacityKB <Int64>]
    [-Controller <ScsiController>]
    [-Datastore <StorageResource>]
    [-DeviceName <String>]
    -DiskPath <String>
    [-DiskType <DiskType>]
    [-Persistence <String>]
    [-Server <VIServer[]>]
    [-Split]
    [-StorageFormat <VirtualDiskStorageFormat>]
    [-ThinProvisioned]
    -VDisk <VDisk>
    -VM <VirtualMachine>
    [-StoragePolicy <StoragePolicy>]
    [-Confirm]
    [-WhatIf]
    [-KeyProvider <KeyProvider>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdvancedOption` | `AdvancedOption[]` | No | Specifies advanced options for creating hard disks. Accepts only SdrsVMDiskAntiAffinityRule objects. You can define an anti-affinity Storage Distributed Resource Scheduler (SDRS) rule for the disk ... |
| `-CapacityGB` | `Decimal` | No | Specifies the capacity of the new virtual disk in gigabytes (GB). You need to specify this parameter when you create hard disks of type Flat. |
| `-CapacityKB` | `Int64` | No | This parameter is obsolete. Use the CapacityGB parameter instead. Specifies the capacity of the new virtual disk in kilobytes (KB). You need to specify this parameter when you create hard disks of ... |
| `-Controller` | `ScsiController` | No | Specifies a SCSI controller to which you want to attach the new hard disk. |
| `-Datastore` | `StorageResource` | No | Specifies the datastore where you want to place the new hard disk. If a DatastoreCluster object is passed to the Datastore parameter, the hard disk is added to the DatastoreCluster in an automated ... |
| `-DeviceName` | `String` | No | Specifies the host-specific device the Logical Unit Number (LUN) is being accessed through. If the target LUN is not available on the host, then it's empty. For example, this might happen if it is ... |
| `-DiskPath` | `String` | Yes | Specifies the path to the hard disk. |
| `-DiskType` | `DiskType` | No | Specifies the type of file backing that you want to use. The valid values are rawVirtual, rawPhysical, flat, PMem, and unknown. If the hard disk is attached to no virtual machine, the value of the ... |
| `-Persistence` | `String` | No | Specifies the disk persistence mode. The valid values are Persistent, NonPersistent, IndependentPersistent, IndependentNonPersistent, and Undoable. This parameter is supported only when the disk ty... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Split` | `SwitchParameter` | No | This parameter is deprecated and scheduled for removal. Use the StorageFormat parameter instead. Specifies the type of the virtual disk file - split or monolithic. If the value is $true, the virtua... |
| `-StorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the storage format of the new hard disk. This parameter accepts Thin, Thick, and EagerZeroedThick values. |
| `-ThinProvisioned` | `SwitchParameter` | No | This parameter is deprecated and scheduled for removal. Use the StorageFormat parameter instead. Indicates to the underlying file system that the virtual disk backing file should be allocated lazil... |
| `-VDisk` | `VDisk` | Yes | Specifies the VDisk object that you want to attach to the virtual machine. |
| `-VM` | `VirtualMachine` | Yes | Specifies the virtual machine to which you want to add the new disk. Passing multiple values to this parameter is obsolete. |
| `-StoragePolicy` | `StoragePolicy` | No | Specifies the storage policy that you want to attach to the new disk. If the storage policy is a PMem policy, the new disk is created in the PMem datastore of the virtual machine host. If the stora... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-KeyProvider` | `KeyProvider` | No | Specifies the key provider that you want to use for the encryption key while creating the new hard disk. If the StoragePolicy parameter is not specified, the default encryption storage policy "VM E... |

---

### New-ScsiController

This cmdlet creates a new SCSI controller.

**Returns**: `ScsiController`

```
New-ScsiController
    [-BusSharingMode <ScsiBusSharingMode>]
    -HardDisk <HardDisk>
    [-Type <ScsiControllerType>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BusSharingMode` | `ScsiBusSharingMode` | No | Specifies the bus sharing mode of the SCSI controller. The valid values are NoSharing, Physical, and Virtual. |
| `-HardDisk` | `HardDisk` | Yes | Specifies the hard disk you want to attach to the new SCSI controller. Passing multiple values to this parameter is obsolete. |
| `-Type` | `ScsiControllerType` | No | Specifies the type of the SCSI controller. The valid values are ParaVirtual, VirtualBusLogic, VirtualLsiLogic, and VirtualLsiLogicSAS. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-CDDrive

This cmdlet removes virtual CD drives from their locations.

**Returns**: `None`

```
Remove-CDDrive
    -CD <CDDrive[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CD` | `CDDrive[]` | Yes | Specifies the virtual CD drives you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-FloppyDrive

This cmdlet removes the virtual floppy drives from their locations.

**Returns**: `None`

```
Remove-FloppyDrive
    -Floppy <FloppyDrive[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Floppy` | `FloppyDrive[]` | Yes | Specifies the virtual floppy drives you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-HardDisk

This cmdlet removes the specified virtual hard disks.

**Returns**: `None`

```
Remove-HardDisk
    [-DeletePermanently]
    -HardDisk <HardDisk[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeletePermanently` | `SwitchParameter` | No | Indicates that you want to delete the hard disks not only from the inventory, but from the datastore as well. |
| `-HardDisk` | `HardDisk[]` | Yes | Specifies the hard disks you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-PassthroughDevice

This cmdlet removes the specified pass-through devices.

This cmdlet removes the specified pass-through devices. You can remove only those pass-through devices that are retrieved from virtual machines.

**Returns**: `None`

```
Remove-PassthroughDevice
    -PassthroughDevice <PassThroughDevice[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PassthroughDevice` | `PassThroughDevice[]` | Yes | Specifies the pass-through devices you want to remove. You can remove only those pass-through devices that are retrieved from virtual machines. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-UsbDevice

This cmdlet removes the specified USB devices from a virtual machine.

**Returns**: `None`

```
Remove-UsbDevice
    -UsbDevice <UsbDevice[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-UsbDevice` | `UsbDevice[]` | Yes | Specifies the USB devices you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-CDDrive

This cmdlet modifies the configuration of a virtual CD drive.

This cmdlet updates a virtual CD drive. If an ISO location is provided, sets the CD to point to the ISO. Changes the StartConnected and Connected flags if StartConnected and/or Connected is set. If NoMedia parameter is set to $true, removes the CD drive's media backing and disconnects it. Note that the Connected parameter can be specified only if the corresponding virtual machine is powered on.

**Returns**: `CDDrive`

```
Set-CDDrive
    -CD <CDDrive[]>
    [-Connected <Boolean>]
    [-HostDevice <String>]
    [-IsoPath <String>]
    [-NoMedia]
    [-StartConnected <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CD` | `CDDrive[]` | Yes | Specifies the virtual CD drive you want to configure. |
| `-Connected` | `Boolean` | No | Indicates that the virtual CD drive is connected after its creation. This parameter can be specified only if the corresponding virtual machine is powered on. |
| `-HostDevice` | `String` | No | Specifies the path to the CD drive on the host which backs this virtual CD drive. Do not use this parameter when the ISOPath and NoMedia parameters are specified. |
| `-IsoPath` | `String` | No | Specifies the datastore path to the ISO (CD image) file that backs the virtual CD drive. Do not use this parameter when the HostDevice and NoMedia parameters are specified. |
| `-NoMedia` | `SwitchParameter` | No | Indicates that you want to detach from the CD drive any type of connected media - ISO from datastore or host device. Do not use this parameter when the ISOPath or HostDevice parameters are specified. |
| `-StartConnected` | `Boolean` | No | Indicates that the virtual CD drive starts connected when the virtual machine associated with it powers on. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-FloppyDrive

This cmdlet modifies the configuration of the specified virtual floppy drive.

This cmdlet modifies the configuration of the specified virtual floppy drive. If a floppy image path is provided, the cmdlet sets the floppy drive to point to the image. Also, the cmdlet updates the StartConnected and Connected properties. If the value of the NoMedia parameter is $true, the cmdlet removes the floppy drive's media backing and disconnects it. The FloppyImagePath, HostDevice, and NoMedia parameters cannot be used together. The Connected parameter can be specified only if the cor...

**Returns**: `FloppyDrive`

```
Set-FloppyDrive
    [-Connected <Boolean>]
    -Floppy <FloppyDrive[]>
    [-FloppyImagePath <String>]
    [-HostDevice <String>]
    [-NoMedia]
    [-StartConnected <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Connected` | `Boolean` | No | If the value is $true, the virtual floppy drive is connected after its creation. If the value is $false, the floppy drive is disconnected. This parameter can be specified only if the corresponding ... |
| `-Floppy` | `FloppyDrive[]` | Yes | Specifies the virtual floppy drive you want to configure. |
| `-FloppyImagePath` | `String` | No | Specifies the datastore path to the floppy image file that backs the virtual floppy drive. Do not use this parameter when the HostDevice and NoMedia parameters are specified. |
| `-HostDevice` | `String` | No | Specifies the path to the floppy drive on the host that backs this virtual floppy drive. Do not use this parameter when the FloppyImagePath and NoMedia parameters are specified. |
| `-NoMedia` | `SwitchParameter` | No | Indicates that the floppy drive is to have no media (similar to removing the floppy from a physical drive). Do not use this parameter when the FloppyImagePath and HostDevice parameters are specified. |
| `-StartConnected` | `Boolean` | No | If the value is $true, the virtual floppy drive starts connected when its associated virtual machine powers on. If the value is $false, it starts disconnected. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-HardDisk

This cmdlet modifies the properties of the specified virtual hard disk.

This cmdlet modifies the properties of the specified virtual hard disk. You can encrypt the specified virtual hard disk or decrypt the specified virtual hard disk. You can also change the size and the persistence type, and inflate or expand the specified virtual hard disk. Do not use the Inflate parameter at the same time with the Persistence and CapacityGB parameters. If you use a helper virtual machine, all virtual machines associated with the disk and the helper virtual machine should be p...

**Returns**: `HardDisk`

```
Set-HardDisk
    [-CapacityGB <Decimal>]
    [-CapacityKB <Int64>]
    [-Controller <ScsiController>]
    [-Datastore <Datastore>]
    [-GuestCredential <PSCredential>]
    [-GuestPassword <SecureString>]
    [-GuestUser <String>]
    -HardDisk <HardDisk[]>
    [-HelperVM <VirtualMachine>]
    [-HostCredential <PSCredential>]
    [-HostPassword <SecureString>]
    [-HostUser <String>]
    [-Inflate]
    [-Partition <String>]
    [-Persistence <String>]
    [-ResizeGuestPartition]
    [-Server <VIServer[]>]
    [-StorageFormat <VirtualDiskStorageFormat>]
    [-ToolsWaitSecs <Int32>]
    [-ZeroOut]
    [-Confirm]
    [-WhatIf]
    -DisableEncryption
    [-RunAsync]
    [-StoragePolicy <StoragePolicy>]
    [-KeyProvider <KeyProvider>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CapacityGB` | `Decimal` | No | Specifies the updated capacity of the virtual disk in gigabytes (GB). If you are connected to a vCenter Server 2.0 or ESX 3.0, the size of the disk cannot be changed and the CapacityGB parameter is... |
| `-CapacityKB` | `Int64` | No | This parameter is obsolete. Use CapacityGB instead. Specifies the updated capacity of the virtual disk in kilobytes (KB). If you are connected to a vCenter Server 2.0 or ESX 3.0 server, the size of... |
| `-Controller` | `ScsiController` | No | Specifies a SCSI controller to which you want to attach the hard disk. |
| `-Datastore` | `Datastore` | No | Specifies the datastore to which you want to move the specified hard disk. Moving a hard disk attached to a virtual machine to a different datastore is only supported on vCenter Server. |
| `-GuestCredential` | `PSCredential` | No | Specifies the PSCredential object that contains the credentials you want to use for authenticating with the guest operating system. |
| `-GuestPassword` | `SecureString` | No | Specifies the password you want to use for authenticating with the guest operating system. |
| `-GuestUser` | `String` | No | Specifies the username you want to use for authenticating with the guest operating system. |
| `-HardDisk` | `HardDisk[]` | Yes | Specifies the virtual hard disk you want to configure. |
| `-HelperVM` | `VirtualMachine` | No | Specifies a helper virtual machine you want to use when expanding a Windows virtual machine system disk. LVM (logical volume manager) for Linux is not supported and Linux guest system disks cannot ... |
| `-HostCredential` | `PSCredential` | No | Specifies the PSCredential object that contains the credentials you want to use for authenticating with the host. |
| `-HostPassword` | `SecureString` | No | Specifies the password you want to use for authenticating with the host. |
| `-HostUser` | `String` | No | Specifies the user name you want to use for authenticating with the host. |
| `-Inflate` | `SwitchParameter` | No | Indicates that you want to inflate the hard disk. |
| `-Partition` | `String` | No | Specifies the partitions you want to resize. On Windows, you can specify which partition you want to resize by using the Partition parameter. If you do not specify a partition, the last partition o... |
| `-Persistence` | `String` | No | Specifies the disk persistence mode. The valid values are Persistent, NonPersistent, IndependentPersistent, IndependentNonPersistent, and Undoable. This parameter is supported only when the disk ty... |
| `-ResizeGuestPartition` | `SwitchParameter` | No | Note: This functionality is deprecated and is not functional on the currently supported guest operating systems. Resizing guest disks works only on Windows XP Service Pack 3 and Red Hat Enterprise ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the storage format of the relocated hard disk. This parameter is applicable only when moving a virtual machine disk to a different datastore by using the Datastore parameter. This paramet... |
| `-ToolsWaitSecs` | `Int32` | No | Specifies the time in seconds to wait for a response from VMware Tools. If a non-positive value is provided, the system waits an infinitely long time. |
| `-ZeroOut` | `SwitchParameter` | No | Specifies that you want to fill the hard disk with zeros. This parameter is supported only if you are directly connected to an ESX/ESXi host. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-DisableEncryption` | `SwitchParameter` | Yes | Indicates that the cmdlet decrypts the specified hard disk. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-StoragePolicy` | `StoragePolicy` | No | Specifies the StoragePolicy that you want to attach to the specified hard disk. If the storage policy is an encryption policy, the hard disk is encrypted. |
| `-KeyProvider` | `KeyProvider` | No | Specifies the key provider that you want to use for the encryption key while encrypting the specified hard disk. If StoragePolicy is not specified, the default encryption storage policy "VM Encrypt... |

---

### Set-ScsiController

This cmdlet modifies the specified SCSI controllers.

This cmdlet modifies the specified SCSI controllers. Set-ScsiController cannot set both the Type and BusSharing parameters at the same time. First run the cmdlet to set the type and then run it again to configure the bus sharing mode.

**Returns**: `ScsiController`

```
Set-ScsiController
    [-BusSharingMode <ScsiBusSharingMode>]
    -ScsiController <ScsiController[]>
    [-Type <ScsiControllerType>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BusSharingMode` | `ScsiBusSharingMode` | No | Specifies the bus sharing mode of the SCSI controller. The valid values are NoSharing, Physical, and Virtual. |
| `-ScsiController` | `ScsiController[]` | Yes | Specifies the SCSI controller you want to modify. |
| `-Type` | `ScsiControllerType` | No | Specifies the type of the SCSI controller. The valid values are ParaVirtual, VirtualBusLogic, VirtualLsiLogic, and VirtualLsiLogicSAS. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-ScsiLun

This cmdlet modifies the configuration of a SCSI device.

**Returns**: `ScsiLun`

```
Set-ScsiLun
    [-BlocksToSwitchPath <Int32>]
    [-CommandsToSwitchPath <Int32>]
    [-DeletePartitions]
    [-Force]
    [-IsLocal <Boolean>]
    [-IsLocatorLedOn <Boolean>]
    [-IsSsd <Boolean>]
    [-MultipathPolicy <ScsiLunMultipathPolicy>]
    [-NoBlocksSwitch]
    [-NoCommandsSwitch]
    [-PreferredPath <ScsiLunPath>]
    -ScsiLun <ScsiLun[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BlocksToSwitchPath` | `Int32` | No | Specifies the maximum number of I/O blocks that you want to issue on a given path before the system tries to select a different path. Modifying this setting affects all SCSI LUN devices that are co... |
| `-CommandsToSwitchPath` | `Int32` | No | Specifies the maximum number of I/O requests that you want to issue on a given path before the system tries to select a different path. Modifying this setting affects all SCSI LUN devices that are ... |
| `-DeletePartitions` | `SwitchParameter` | No | Removes all partitions from the SCSI disk. A confirmation prompt appears. If Force is specified, the confirmation prompt does not appear and partitions are removed. |
| `-Force` | `SwitchParameter` | No | Indicates that you want to suppress the prompt that appears when the DeletePartitions parameter is specified. If the Force parameter is specified, you are not asked for confirmation when deleting d... |
| `-IsLocal` | `Boolean` | No | Marks the SCSI disk as local or remote. If the value is $true, the SCSI disk is local. If the value is $false, the SCSI disk is remote. |
| `-IsLocatorLedOn` | `Boolean` | No | Turns the LED locator of a SCSI disk on or off. |
| `-IsSsd` | `Boolean` | No | Marks the SCSI disk as an SSD or HDD. If the value is $true, the SCSI disk is an SSD type. If the value is $false, the SCSI disk is an HDD type. |
| `-MultipathPolicy` | `ScsiLunMultipathPolicy` | No | Specifies the policy that the logical unit must use when choosing a path. The following values are valid:   Fixed - uses the preferred path whenever possible. RoundRobin - load balance. MostRecentl... |
| `-NoBlocksSwitch` | `SwitchParameter` | No | This parameter is deprecated and scheduled for removal. Indicates that switching based on blocks is deactivated. Not supported on vCenter Server 4.x. |
| `-NoCommandsSwitch` | `SwitchParameter` | No | This parameter is deprecated and scheduled for removal. Indicates that switching based on commands is deactivated. Not supported on vCenter Server 4.x. |
| `-PreferredPath` | `ScsiLunPath` | No | Specifies the preferred path to access the SCSI logical unit. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. |
| `-ScsiLun` | `ScsiLun[]` | Yes | Specifies the SCSI device you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-ScsiLunPath

This cmdlet configures a vmhba path to a SCSI device.

**Returns**: `ScsiLunPath`

```
Set-ScsiLunPath
    [-Active <Boolean>]
    [-Preferred]
    -ScsiLunPath <ScsiLunPath[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Active` | `Boolean` | No | Indicates that the specified path is active. |
| `-Preferred` | `SwitchParameter` | No | Indicates that the specified path is preferred. Only one path can be preferred, so when a path is made preferred, the preference is removed from the previously preferred path. |
| `-ScsiLunPath` | `ScsiLunPath[]` | Yes | Specifies a path to the SCSI logical unit you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

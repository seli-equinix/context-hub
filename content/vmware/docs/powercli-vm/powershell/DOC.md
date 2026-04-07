---
name: powercli-vm
description: "VMware PowerCLI 13.3 — virtual machine lifecycle: create, configure, power, clone, move, remove"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Answer-VMQuestion,Get-VM,Get-VMQuestion,Get-VMResourceConfiguration,Get-VMStartPolicy,Move-VM,New-VM,Remove-VM,Restart-VM,Set-VM,Set-VMResourceConfiguration,Set-VMStartPolicy,Start-VM,Stop-VM,Suspend-VM"
---

# VMware PowerCLI — virtual machine lifecycle

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Answer-VMQuestion` | This cmdlet answers the specified virtual machine question. |
| `Get-VM` | This cmdlet retrieves the virtual machines on a vCenter Server system. |
| `Get-VMQuestion` | This cmdlet retrieves the pending questions for the specified virtual machines. |
| `Get-VMResourceConfiguration` | This cmdlet retrieves information about the resource allocation between the selected virtual mach... |
| `Get-VMStartPolicy` | This cmdlet retrieves the start policy of the virtual machines on a vCenter Server system. |
| `Move-VM` | This cmdlet moves virtual machines to another location. |
| `New-VM` | This cmdlet creates a new virtual machine. |
| `Remove-VM` | This cmdlet removes the specified virtual machines from the vCenter Server system. |
| `Restart-VM` | This cmdlet restarts the specified virtual machines. |
| `Set-VM` | This cmdlet modifies the configuration of the virtual machine. |
| `Set-VMResourceConfiguration` | This cmdlet configures resource allocation between the virtual machines. |
| `Set-VMStartPolicy` | This cmdlet modifies the virtual machine start policy. |
| `Start-VM` | This cmdlet powers on virtual machines. |
| `Stop-VM` | This cmdlet powers off  virtual machines. |
| `Suspend-VM` | This cmdlet suspends virtual machines. |

---

### Answer-VMQuestion

This cmdlet answers the specified virtual machine question.

This cmdlet answers the specified virtual machine question using the value of the Option parameter. If the DefaultOption parameter is set to $true, the cmdlet answers the question with a default option, if any.

**Returns**: `VMQuestion`

```
Answer-VMQuestion
    -DefaultOption
    -Option <Object>
    -VMQuestion <VMQuestion[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DefaultOption` | `SwitchParameter` | Yes | Indicates that you want to answer the virtual machine question using a default option. If no default option exists for the question, an error is generated. |
| `-Option` | `Object` | Yes | Specifies an object or string to provide an option to the virtual machine question. Wildcards are supported for string values. The string can be used to specify an option ID or label. If the string... |
| `-VMQuestion` | `VMQuestion[]` | Yes | Specifies the virtual machine question you want to answer. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-VM

This cmdlet retrieves the virtual machines on a vCenter Server system.

This cmdlet retrieves the virtual machines on a vCenter Server system. Returns a set of virtual machines that correspond to the filter criteria provided by the cmdlet parameters. For virtual machines with multiple NICs and multiple IP addresses, the IPAddress property of the VMGuest object contains all IP addresses of the virtual machine. The IP at position 0 is the primary IP address.

**Returns**: `VirtualMachine`

```
Get-VM
    [-Datastore <StorageResource[]>]
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    -RelatedObject <VmRelatedObjectBase[]>
    [-Server <VIServer[]>]
    [-Tag <Tag[]>]
    [-VirtualSwitch <VirtualSwitchBase[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `StorageResource[]` | No | Specifies datastores or datastore clusters to filter the virtual machines associated with them. Passing values to this parameter through a pipeline is deprecated and will be removed in a future rel... |
| `-Id` | `String[]` | Yes | Specifies the IDs of the virtual machines you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of th... |
| `-Location` | `VIContainer[]` | No | Specifies vSphere container objects you want to search for virtual machines. Supported container object types are: ResourcePool, VApp, VMHost, Folder, Cluster, Datacenter. |
| `-Name` | `String[]` | No | Specifies the names of the virtual machines you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-RelatedObject` | `VmRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more vSphere VirtualMachine objects that are related to them. This parameter accepts vCloud CIVM and OMResource objects. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | No | Returns only the virtual machines that are associated with any of the specified tags. |
| `-VirtualSwitch` | `VirtualSwitchBase[]` | No | When specified, the cmdlet returns only the virtual machines that have network adapters attached to the specified switches. |

---

### Get-VMQuestion

This cmdlet retrieves the pending questions for the specified virtual machines.

This cmdlet retrieves the pending questions for the specified virtual machines. A question is a task that requires a response from you. If the VM parameter is not specified or its value is $null, the cmdlet returns all questions for all virtual machines on the specified servers.

**Returns**: `VmQuestion`

```
Get-VMQuestion
    [-QuestionId <String>]
    [-QuestionText <String>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-QuestionId` | `String` | No | Specifies the IDs of the questions you want to retrieve. |
| `-QuestionText` | `String` | No | Specifies a phrase from the text that describes the questions you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose pending questions you want to retrieve. |

---

### Get-VMResourceConfiguration

This cmdlet retrieves information about the resource allocation between the selected virtual machines.

**Returns**: `VMResourceConfiguration`

```
Get-VMResourceConfiguration
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines whose resource configuration you want to retrieve. |

---

### Get-VMStartPolicy

This cmdlet retrieves the start policy of the virtual machines on a vCenter Server system.

This cmdlet retrieves the start policy of the virtual machines on a vCenter Server system. The virtual machines are specified by the VM parameter or retrieved from the host passed through the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMStartPolicy`

```
Get-VMStartPolicy
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose start policy you want to retrieve. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts of the virtual machines whose start policy you want to retrieve. |

---

### Move-VM

This cmdlet moves virtual machines to another location.

This cmdlet moves a virtual machine to the location that is specified by the Destination or the Datastore parameters. The destination must be a folder, host, cluster, or a resource pool. You can move a virtual machine to a DRS cluster. Moving a virtual machine to the top level of a non-DRS cluster is only possible if the virtual machine is in a resource pool in that cluster. If the virtual machine is outside the non-DRS cluster, you need to specify a virtual machine host in that cluster as de...

**Returns**: `VirtualMachine`

```
Move-VM
    [-AdvancedOption <AdvancedOption[]>]
    [-Datastore <StorageResource>]
    [-Destination <VIContainer>]
    [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-InventoryLocation <FolderContainer>]
    [-Network <Network[]>]
    [-NetworkAdapter <NetworkAdapter[]>]
    [-PortGroup <VirtualPortGroupBase[]>]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-VMotionPriority <VMotionPriority>]
    [-Confirm]
    [-WhatIf]
    [-StoragePolicy <StoragePolicy>]
    [-DestinationSslThumbprint <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdvancedOption` | `AdvancedOption[]` | No | This parameter is only applicable when a DatastoreCluster object is passed to the Datastore parameter. Specifies one or more rules for the placement of the virtual machines that you want to relocat... |
| `-Datastore` | `StorageResource` | No | Specifies the datastore or datastore cluster where you want to move the virtual machines. When you pass a datastore cluster to the Datastore parameter, you can also set the AdvancedOption parameter. |
| `-Destination` | `VIContainer` | No | Specifies a folder, host, cluster, or a resource pool where you want to move the virtual machines. If a data center is specified for the Destination parameter, you can move the virtual machines to ... |
| `-DiskStorageFormat` | `VirtualDiskStorageFormat` | No | Specifies a new storage format for the hard disk of the virtual machine you want to move. This parameter is applicable only when moving a virtual machine to a different datastore, using the Datasto... |
| `-InventoryLocation` | `FolderContainer` | No | Specifies a data center or a virtual machine folder where you want to move the virtual machine. |
| `-Network` | `Network[]` | No | Specifies the destination networks for the specified virtual machine network adapters. The number of networks should be one or equal to the number of the specified network adapters. If one network ... |
| `-NetworkAdapter` | `NetworkAdapter[]` | No | Specifies the virtual machine network adapters you want to migrate to a new port group. |
| `-PortGroup` | `VirtualPortGroupBase[]` | No | Specifies the destination port groups for the specified virtual machine network adapters. The number of the port groups should be one or equal to the number of the specified network adapters. If on... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines you want to move to another location. |
| `-VMotionPriority` | `VMotionPriority` | No | Determines the priority that you should use for a vMotion operation. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-StoragePolicy` | `StoragePolicy` | No | Specifies a new StoragePolicy for the virtual machine you want to move. The StoragePolicy is attached to VMHome and all hard disks. |
| `-DestinationSslThumbprint` | `String` | No | Specifies the SSL thumbprint of the destination server when moving virtual machines between vCenter Server systems. |

---

### New-VM

This cmdlet creates a new virtual machine.

This cmdlet creates a new virtual machine with the provided parameters. The network adapter and the Small Computer System Interface (SCSI) adapter of the new virtual machine are created of the recommended type for the operating system (OS) that is specified by the GuestId parameter. If  the OSCustomizationSpec parameter is used,  the virtual machine is customized according to the specification. You must specify values for at least one of the ResourcePool, VMHost, and VApp parameters.

**Returns**: `VirtualMachine`

```
New-VM
    [-AdvancedOption <AdvancedOption[]>]
    [-AlternateGuestName <String>]
    [-BootDelayMillisecond <Int64>]
    [-CD]
    -ContentLibraryItem <ContentLibraryItem>
    [-CoresPerSocket <Int32>]
    [-Datastore <StorageResource>]
    [-DiskGB <Decimal[]>]
    [-DiskMB <Int64[]>]
    [-DiskPath <String[]>]
    [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-DrsAutomationLevel <DrsAutomationLevel>]
    [-Floppy]
    [-GuestId <String>]
    [-HAIsolationResponse <HAIsolationResponse>]
    [-HardwareVersion <String>]
    [-HARestartPriority <HARestartPriority>]
    [-LinkedClone]
    [-Location <Folder>]
    [-MemoryGB <Decimal>]
    [-MemoryMB <Int64>]
    [-MigrationEncryption <VMMigrationEncryptionMode>]
    -Name <String>
    [-NetworkName <String[]>]
    [-Notes <String>]
    [-NumCpu <Int32>]
    [-OSCustomizationSpec <OSCustomizationSpec>]
    [-OvfConfiguration <Hashtable>]
    [-Portgroup <VirtualPortGroupBase[]>]
    [-ReferenceSnapshot <Snapshot>]
    [-ResourcePool <VIContainer>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-SEVEnabled <Boolean>]
    -Template <Template>
    [-VApp <VApp>]
    [-Version <VMVersion>]
    -VM <VirtualMachine[]>
    -VMFilePath <String>
    [-VMHost <VMHost>]
    [-VMSwapfilePolicy <VMSwapfilePolicy>]
    [-Confirm]
    [-WhatIf]
    [-SkipHardDisks]
    [-StoragePolicy <StoragePolicy>]
    [-ReplicationGroup <ReplicationGroup>]
    [-StoragePolicyTarget <StoragePolicyTargetType>]
    [-KeyProvider <KeyProvider>]
    [-CpuHotAddEnabled <Boolean>]
    [-CpuHotRemoveEnabled <Boolean>]
    [-MemoryHotAddEnabled <Boolean>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdvancedOption` | `AdvancedOption[]` | No | Specifies advanced options for creating virtual machines. Accepts only SdrsVMDiskAntiAffinityRule and SdrsVMAntiAffinityRule objects.   The SdrsVMDiskAntiAffinityRule defines a Storage DRS intra-VM... |
| `-AlternateGuestName` | `String` | No | Specifies the full OS name of the new virtual machine. Use this parameter if the GuestID parameter is set to otherGuest or otherGuest64. |
| `-BootDelayMillisecond` | `Int64` | No | Specifies the time interval in milliseconds between a virtual machine power on or restart and the beginning of the boot sequence. |
| `-CD` | `SwitchParameter` | No | Indicates that you want to add a CD drive to the new virtual machine. |
| `-ContentLibraryItem` | `ContentLibraryItem` | Yes | Specifies the content library template from which you want to deploy the virtual machine. |
| `-CoresPerSocket` | `Int32` | No | Specifies the number of virtual CPU cores per socket. |
| `-Datastore` | `StorageResource` | No | Specifies the datastore where you want to place the new virtual machine. If a DatastoreCluster is passed to the Datastore parameter, the virtual machine is placed in the DatastoreCluster in an auto... |
| `-DiskGB` | `Decimal[]` | No | Specifies the size in gigabytes (GB) of the disks that you want to create and add to the new virtual machine. |
| `-DiskMB` | `Int64[]` | No | This parameter is obsolete. Use DiskGB instead. Specifies the size in megabytes (MB) of the disks that you want to create and add to the new virtual machine. |
| `-DiskPath` | `String[]` | No | Specifies paths to virtual disks that you want to add to the new virtual machine. |
| `-DiskStorageFormat` | `VirtualDiskStorageFormat` | No | Specifies the storage format of the disks of the virtual machine. This parameter accepts Thin, Thick, and EagerZeroedThick values. |
| `-DrsAutomationLevel` | `DrsAutomationLevel` | No | Specifies a DRS (Distributed Resource Scheduler) automation level. The valid values are FullyAutomated, Manual, PartiallyAutomated, AsSpecifiedByCluster, and Disabled. Passing values to this parame... |
| `-Floppy` | `SwitchParameter` | No | Indicates that you want to add a floppy drive to the new virtual machine. |
| `-GuestId` | `String` | No | Specifies the guest operating system of the new virtual machine. The valid values for specific ESX versions are listed in the description of the VirtualMachineGuestOsIdentifier enumeration type in ... |
| `-HAIsolationResponse` | `HAIsolationResponse` | No | Indicates whether the virtual machine should be powered off if a host determines that it is isolated from the rest of the compute resource. The available values are AsSpecifiedByCluster, PowerOff, ... |
| `-HardwareVersion` | `String` | No | Specifies the version of the new virtual machine. By default, the new virtual machine is created with the latest available version. |
| `-HARestartPriority` | `HARestartPriority` | No | Specifies the HA restart priority of the new virtual machine. The valid values are Disabled, Lowest, Low, Medium, High, Highest, and ClusterRestartPriority. VMware High Availability (HA) is a featu... |
| `-LinkedClone` | `SwitchParameter` | No | Indicates that you want to create a linked clone. When you set the LinkedClone parameter, the ReferenceSnapshot parameter becomes mandatory. |
| `-Location` | `Folder` | No | Specifies the folder where you want to place the new virtual machine. |
| `-MemoryGB` | `Decimal` | No | Specifies the memory size in gigabytes (GB) of the new virtual machine. |
| `-MemoryMB` | `Int64` | No | This parameter is obsolete. Use MemoryGB instead. Specifies the memory size in megabytes (MB) of the new virtual machine. |
| `-MigrationEncryption` | `VMMigrationEncryptionMode` | No | Specifies the encryption behavior when migrating the virtual machine. Valid options are: - Disabled: Do not use encrypted vSphere vMotion.   - Opportunistic: Use encrypted vSphere vMotion if source... |
| `-Name` | `String` | Yes | Specifies a name for the new virtual machine. If you want to register or clone an existing virtual machine, this parameter is not mandatory. |
| `-NetworkName` | `String[]` | No | Specifies the networks to which you want to connect the new virtual machine. Specifying a distributed port group name is obsolete. Use the Portgroup parameter instead. |
| `-Notes` | `String` | No | Provides a description of the new virtual machine. The alias of this parameter is Description. |
| `-NumCpu` | `Int32` | No | Specifies the number of the virtual CPUs of the new virtual machine. |
| `-OSCustomizationSpec` | `OSCustomizationSpec` | No | Specifies a customization specification that is applied to the new virtual machine. |
| `-OvfConfiguration` | `Hashtable` | No | Specifies values for a set of user-configurable OVF properties. |
| `-Portgroup` | `VirtualPortGroupBase[]` | No | Specifies standard or distributed port groups to which you want to connect the virtual machine. For each specified port group, a new network adapter is created. |
| `-ReferenceSnapshot` | `Snapshot` | No | Specifies a source snapshot for the linked clone that you want to create. When you set the LinkedClone parameter, the ReferenceSnapshot parameter becomes mandatory. |
| `-ResourcePool` | `VIContainer` | No | Specifies where you want to place the new virtual machine. The parameter accepts VMHost, Cluster, ResourcePool, and VApp objects. If no value is specified, the virtual machine is added to the resou... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SEVEnabled` | `Boolean` | No | Specifies whether SEV (Secure Encrypted Virtualization) is enabled or not. It allows the CPU to encrypt the memory and the state of the virtual machine. It is applicable for AMD CPUs only. |
| `-Template` | `Template` | Yes | Specifies the virtual machine template that you want to use for the creation of the new virtual machine. Passing values to this parameter through a pipeline is deprecated and will be deactivated in... |
| `-VApp` | `VApp` | No | This parameter is deprecated. Use the ResourcePool parameter instead. Specifies the vApp where you want to create the new virtual machine. |
| `-Version` | `VMVersion` | No | This parameter is deprecated. Use the HardwareVersion parameter instead. Specifies the version of the new virtual machine. The valid values are v4, v7, v8, v9, v10, v11, v12, v13, and v14. By defau... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies a virtual machine that you want to clone. |
| `-VMFilePath` | `String` | Yes | Specifies a path to the virtual machine that you want to register. |
| `-VMHost` | `VMHost` | No | Specifies the host on which you want to create the new virtual machine. |
| `-VMSwapfilePolicy` | `VMSwapfilePolicy` | No | Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore specified by the VMSwapfileDatastoreID property of the virtual mach... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-SkipHardDisks` | `SwitchParameter` | No | Specifies whether to apply the StoragePolicy or Encryption to the hard disks in the new virtual machine. |
| `-StoragePolicy` | `StoragePolicy` | No | Specifies the StoragePolicy that you want to attach to the new virtual machine during creation. If the StoragePolicy is an encryption policy, the new virtual machine is encrypted. |
| `-ReplicationGroup` | `ReplicationGroup` | No | Specifies the ReplicationGroup where you want to place the new virtual machine. It is applicable with the storage policy provided in the StoragePolicy parameter. |
| `-StoragePolicyTarget` | `StoragePolicyTargetType` | No | Specifies the target of the StoragePolicy in the virtual machine or in the VM parameter. |
| `-KeyProvider` | `KeyProvider` | No | Specifies the key provider that you want to use for the encryption key while creating the new virtual machine. If StoragePolicy is not specified, the default encryption storage policy "VM Encryptio... |
| `-CpuHotAddEnabled` | `Boolean` | No | Specifies if virtual processors can be added to the virtual machine while it is running. |
| `-CpuHotRemoveEnabled` | `Boolean` | No | Specifies if virtual processors can be removed from the virtual machine while it is running. |
| `-MemoryHotAddEnabled` | `Boolean` | No | Specifies if memory can be added to the virtual machine while it is running. |

---

### Remove-VM

This cmdlet removes the specified virtual machines from the vCenter Server system.

This cmdlet removes the specified virtual machines from the vCenter Server system. If the value of the DeletePermanently parameter is $true, the cmdlet not only removes the virtual machines from the inventory, but also deletes them from the disk.

**Returns**: `None`

```
Remove-VM
    [-DeletePermanently]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeletePermanently` | `SwitchParameter` | No | Indicates that you want to delete the virtual machines not only from the inventory, but from the datastore. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Restart-VM

This cmdlet restarts the specified virtual machines.

**Returns**: `VirtualMachine`

```
Restart-VM
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines you want to restart. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VM

This cmdlet modifies the configuration of the virtual machine.

This cmdlet modifies the configuration of the virtual machine. If the OSCustomizationSpec parameter is used, the cmdlet customizes the virtual machine according to the specification. In addition, the cmdlet allows you to revert a virtual machine to a snapshot and convert a virtual machine to a template.

**Returns**: `VirtualMachine`

```
Set-VM
    [-AlternateGuestName <String>]
    [-BootDelayMillisecond <Int64>]
    [-CoresPerSocket <Int32>]
    -DisableEncryption
    [-DrsAutomationLevel <DrsAutomationLevel>]
    [-GuestId <String>]
    [-HAIsolationResponse <HAIsolationResponse>]
    [-HardwareVersion <String>]
    [-HARestartPriority <HARestartPriority>]
    [-MemoryGB <Decimal>]
    [-MemoryMB <Int64>]
    [-MigrationEncryption <VMMigrationEncryptionMode>]
    [-Name <String>]
    [-Notes <String>]
    [-NumCpu <Int32>]
    [-OSCustomizationSpec <OSCustomizationSpec>]
    [-PromoteDisks]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-SEVEnabled <Boolean>]
    [-SkipHardDisks]
    [-Snapshot <Snapshot>]
    [-StoragePolicy <StoragePolicy>]
    [-ToTemplate]
    [-Version <VMVersion>]
    -VM <VirtualMachine[]>
    [-VMSwapFilePolicy <VMSwapfilePolicy>]
    [-CpuHotAddEnabled <Boolean>]
    [-CpuHotRemoveEnabled <Boolean>]
    [-MemoryHotAddEnabled <Boolean>]
    [-Confirm]
    [-WhatIf]
    [-KeyProvider <KeyProvider>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlternateGuestName` | `String` | No | Specifies the full name of the guest OS for the virtual machine if the value of the GuestID parameter is set to otherGuest or otherGuest64. |
| `-BootDelayMillisecond` | `Int64` | No | Specifies the time interval in milliseconds between a virtual machine power on or restart and the beginning of the boot sequence. |
| `-CoresPerSocket` | `Int32` | No | Specifies the number of virtual CPU cores per socket. |
| `-DisableEncryption` | `SwitchParameter` | Yes | Indicates that you want to decrypt the specified virtual machine. |
| `-DrsAutomationLevel` | `DrsAutomationLevel` | No | Specifies a Distributed Resource Scheduler (DRS) automation level. The valid values are FullyAutomated, Manual, PartiallyAutomated, AsSpecifiedByCluster, and Disabled. Passing values to this parame... |
| `-GuestId` | `String` | No | Specifies the guest operating system of the virtual machine. The valid values for specific ESX versions are listed in the description of the VirtualMachineGuestOsIdentifier enumeration type in the ... |
| `-HAIsolationResponse` | `HAIsolationResponse` | No | Indicates whether the virtual machine should be powered off if a host determines that it's isolated from the rest of the compute resource. The valid values are AsSpecifiedByCluster, PowerOff, and D... |
| `-HardwareVersion` | `String` | No | Specifies the version to which you want to upgrade the virtual machine. You cannot downgrade to an earlier version. |
| `-HARestartPriority` | `HARestartPriority` | No | Specifies the virtual machine High Availability (HA) restart priority. The valid values are Disabled, Lowest, Low, Medium, High, Highest and ClusterRestartPriority. VMware HA is a feature that dete... |
| `-MemoryGB` | `Decimal` | No | Specifies the memory size in gigabytes (GB). |
| `-MemoryMB` | `Int64` | No | This parameter is obsolete. Use MemoryGB instead. Specifies the memory size in megabytes (MB). |
| `-MigrationEncryption` | `VMMigrationEncryptionMode` | No | Specifies the encryption behavior when migrating the virtual machine. Valid options are: - Disabled: Do not use encrypted vSphere vMotion.   - Opportunistic: Use encrypted vSphere vMotion if source... |
| `-Name` | `String` | No | Specifies a new name for the virtual machine. |
| `-Notes` | `String` | No | Provides a description for the virtual machine. The alias of this parameter is Description. |
| `-NumCpu` | `Int32` | No | Specifies the number of virtual CPUs. |
| `-OSCustomizationSpec` | `OSCustomizationSpec` | No | Specifies a customization specification you want to apply to the virtual machine. This works only in 32-bit mode. |
| `-PromoteDisks` | `SwitchParameter` | No | Promotes virtual machine disks. You can use this parameter to promote a linked clone virtual machine to a full clone. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SEVEnabled` | `Boolean` | No | Specifies whether SEV (Secure Encrypted Virtualization) is enabled or not. It allows the CPU to encrypt the memory and the state of the virtual machine. It is applicable for AMD CPUs only. |
| `-SkipHardDisks` | `SwitchParameter` | No | Indicates that the StoragePolicy or encryption (KeyProvider) is applied to vmhome only. |
| `-Snapshot` | `Snapshot` | No | Specifies a snapshot whose state you want to apply to the virtual machine. |
| `-StoragePolicy` | `StoragePolicy` | No | Specifies the StoragePolicy that you want to attach to the specified virtual machine. If the StoragePolicy is an encryption policy, the virtual machine is encrypted. Otherwise, the virtual machine ... |
| `-ToTemplate` | `SwitchParameter` | No | Indicates that you want to convert the virtual machine to a template. |
| `-Version` | `VMVersion` | No | This parameter is deprecated. Use the HardwareVersion parameter instead. Specifies the version to which you want to upgrade the virtual machine. The valid values are v4, v7, v8, v9, v10, v11, v12, ... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machine that you want to configure. |
| `-VMSwapFilePolicy` | `VMSwapfilePolicy` | No | Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore specified by the VMSwapfileDatastoreID property of the virtual mach... |
| `-CpuHotAddEnabled` | `Boolean` | No | Specifies if virtual processors can be added to the virtual machine while it is running. |
| `-CpuHotRemoveEnabled` | `Boolean` | No | Specifies if virtual processors can be removed from the virtual machine while it is running. |
| `-MemoryHotAddEnabled` | `Boolean` | No | Specifies if memory can be added to the virtual machine while it is running. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-KeyProvider` | `KeyProvider` | No | Specifies the key provider that you want to use for the encryption key while encrypting the specified virtual machine. If StoragePolicy is not specified, the default encryption storage policy "VM E... |

---

### Set-VMResourceConfiguration

This cmdlet configures resource allocation between the virtual machines.

This cmdlet configures resource allocation between the virtual machines. To retain the current value of a setting, omit the corresponding parameter. To activate a setting (only applicable to the nullable limit settings), pass $null.

**Returns**: `VMResourceConfiguration`

```
Set-VMResourceConfiguration
    -Configuration <VMResourceConfiguration[]>
    [-CpuAffinity <CpuAffinity>]
    [-CpuAffinityList <Int32[]>]
    [-CpuLimitMhz <Int64>]
    [-CpuReservationMhz <Int64>]
    [-CpuSharesLevel <SharesLevel>]
    [-Disk <HardDisk[]>]
    [-DiskLimitIOPerSecond <Int64>]
    [-DiskSharesLevel <SharesLevel>]
    [-HtCoreSharing <HTCoreSharing>]
    [-MemLimitGB <Decimal>]
    [-MemLimitMB <Int64>]
    [-MemReservationGB <Decimal>]
    [-MemReservationMB <Int64>]
    [-MemSharesLevel <SharesLevel>]
    [-NumCpuShares <Int32>]
    [-NumDiskShares <Int32>]
    [-NumMemShares <Int32>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Configuration` | `VMResourceConfiguration[]` | Yes | Specifies the configuration object you want to modify. |
| `-CpuAffinity` | `CpuAffinity` | No | The use of this parameter is deprecated. Use CpuAffinityList instead.   Specifies the distribution of virtual machine CPUs across the physical cores or hyperthreads of the host. You must pass exact... |
| `-CpuAffinityList` | `Int32[]` | No | Specifies the distribution of virtual machine CPUs across the physical cores or hyperthreads of the host. You must pass exactly as many arguments as the number of CPUs of the virtual machine. Each ... |
| `-CpuLimitMhz` | `Int64` | No | Specifies the limit on CPU usage in MHz. Utilization will not exceed this limit even if there are available resources. |
| `-CpuReservationMhz` | `Int64` | No | Specifies the number of CPU MHz that are guaranteed to be available. |
| `-CpuSharesLevel` | `SharesLevel` | No | Specifies the CPU allocation level. Used in relative allocation between virtual machines. The valid values are Custom, High, Low, and Normal. |
| `-Disk` | `HardDisk[]` | No | Specifies the virtual hard disk you want to configure. |
| `-DiskLimitIOPerSecond` | `Int64` | No | Specifies the disk limit IO per second. The valid values are in the range between 16 and 2147483647. -1 means unlimited. |
| `-DiskSharesLevel` | `SharesLevel` | No | Specifies the allocation level. The level is a simplified view of shares. Levels map to a pre-determined set of numeric values for shares. If the shares value does not map to a predefined size, the... |
| `-HtCoreSharing` | `HTCoreSharing` | No | Specifies whether a virtual machine is scheduled to share a physical processor core (assuming hyperthreading is enabled on the host at all). The following values are valid:   Any - (default) the vi... |
| `-MemLimitGB` | `Decimal` | No | Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources. |
| `-MemLimitMB` | `Int64` | No | This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are ava... |
| `-MemReservationGB` | `Decimal` | No | Specifies the guaranteed available memory in gigabytes (GB). |
| `-MemReservationMB` | `Int64` | No | This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB). |
| `-MemSharesLevel` | `SharesLevel` | No | Specifies the memory allocation level for this pool. Used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal. |
| `-NumCpuShares` | `Int32` | No | Specifies the CPU allocation level for this pool. Used in relative allocation between resource consumers. This parameter is ignored unless CpuSharesLevel is set to Custom. |
| `-NumDiskShares` | `Int32` | No | Specifies the number of shares allocated. Used to determine resource allocation in case of resource contention. |
| `-NumMemShares` | `Int32` | No | Specifies the number of memory shares allocated. Used to determine resource allocation in case of resource contention. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMStartPolicy

This cmdlet modifies the virtual machine start policy.

This cmdlet modifies the virtual machine start policy. Start policy defines what happens to virtual machines when the server starts up or stops.

**Returns**: `VMStartPolicy`

```
Set-VMStartPolicy
    [-InheritStartDelayFromHost]
    [-InheritStopActionFromHost]
    [-InheritStopDelayFromHost]
    [-InheritWaitForHeartbeatFromHost]
    [-StartAction <VmStartAction>]
    [-StartDelay <Int32>]
    [-StartOrder <Int32>]
    -StartPolicy <VMStartPolicy[]>
    [-StopAction <VmStopAction>]
    [-StopDelay <Int32>]
    [-UnspecifiedStartOrder]
    [-WaitForHeartBeat <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InheritStartDelayFromHost` | `SwitchParameter` | No | Indicates that the virtual machine uses the value of the StartDelay parameter of the host. |
| `-InheritStopActionFromHost` | `SwitchParameter` | No | Indicates that the virtual machine uses the value of the StopAction parameter of the host. |
| `-InheritStopDelayFromHost` | `SwitchParameter` | No | Indicates that the virtual machine uses the value of the StopDelay parameter of the host. |
| `-InheritWaitForHeartbeatFromHost` | `SwitchParameter` | No | Indicates that the virtual machine uses the value of the WaitforHeartbeat parameter of the host. |
| `-StartAction` | `VmStartAction` | No | Specifies a start action for virtual machines. It can be None or PowerOn. |
| `-StartDelay` | `Int32` | No | Specifies a default start delay in seconds. |
| `-StartOrder` | `Int32` | No | Specifies a number to define the virtual machines start order. |
| `-StartPolicy` | `VMStartPolicy[]` | Yes | Specifies the virtual machine start policy you want to modify. |
| `-StopAction` | `VmStopAction` | No | Specifies the default action of the virtual machine when the server stops. The valid values are None, Suspend, PowerOff, and GuestShutDown. |
| `-StopDelay` | `Int32` | No | Specifies the default stop delay in seconds. |
| `-UnspecifiedStartOrder` | `SwitchParameter` | No | Indicates that no order is defined for starting the virtual machines. |
| `-WaitForHeartBeat` | `Boolean` | No | Indicates whether the virtual machine should start after receiving a heartbeat, ignore heartbeats and start after the StartDelay has elapsed ($true), or follow the system default before powering on... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Start-VM

This cmdlet powers on virtual machines.

This cmdlet powers on the virtual machines specified by the VM parameter.

**Returns**: `VirtualMachine`

```
Start-VM
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines you want to power on. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Stop-VM

This cmdlet powers off  virtual machines.

This cmdlet stops the virtual machines specified by the VM parameter.

**Returns**: `VirtualMachine`

```
Stop-VM
    [-Kill]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Kill` | `SwitchParameter` | No | Indicates that you want to stop the specified virtual machines by terminating their processes running on the ESX. You can use this parameter to stop a virtual machine that is not responding and can... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines you want to power off. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Suspend-VM

This cmdlet suspends virtual machines.

This cmdlet suspends the virtual machines specified by the VM parameter. You can use the suspend feature to make resources available on a short-term basis or for other situations in which you want to put a virtual machine on hold without powering it down. Using wildcards is supported with virtual machine names.

**Returns**: `VirtualMachine`

```
Suspend-VM
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines you want to suspend. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

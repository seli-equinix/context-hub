---
name: powercli-vm-operations
description: "VMware PowerCLI 13.3 — Virtual machine lifecycle — create, power, configure, clone, move, remove VMs"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 2
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,vm-operations,Copy-VMGuestFile, Get-VM, Get-VMGuest, Get-VMGuestDisk, Get-VMQuestion, Get-VMResourceConfiguration, Get-VMStartPolicy, Invoke-VMScript, Move-VM, New-VM, Open-VMConsoleWindow, Remove-VM, Restart-VM, Restart-VMGuest, Set-VM, Set-VMQuestion, Set-VMResourceConfiguration, Set-VMStartPolicy, Start-VM, Stop-VM, Stop-VMGuest, Suspend-VM, Suspend-VMGuest, Test-VsanVMCreation, Unlock-VM"
---

# VMware PowerCLI — VM Operations

Virtual machine lifecycle — create, power, configure, clone, move, remove VMs. Module: VMware.VimAutomation (25 cmdlets).

## Copy

### `Copy-VMGuestFile`

**This cmdlet copies files and folders from and to the guest OS of the specified virtual machines using VMware Tools.**

This cmdlet copies files and folders from and to the guest OS of the specified virtual machines using VMware Tools. Use the GuestUser and GuestPassword, or GuestCredential parameters to authenticate when connecting to the VMware Tools. To authenticate with the host, use the HostUser and HostPassword, or HostCredential parameters. SSPI is not supported. For a list of supported operating systems, see the PowerCLI User's Guide.

**Parameters:**

- -Destination [String] (Required) Specifies the destination path where you want to copy the file. If the destination points to a virtual machine, specify the absolute file path. Relative destination paths are supported only when copying files to a local storage.
- -Force [SwitchParameter] (Optional) Indicates that the non-existing directories in the specified destination path are automatically created.
- -GuestCredential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the guest OS where the file to be copied is located.
- -GuestPassword [SecureString] (Optional) Specifies the password you want to use for authenticating with the guest OS where the file to be copied is located.
- -GuestToLocal [SwitchParameter] (Required) Indicates that you want to copy a file from the guest operating system of the virtual machine to a local directory.
- -GuestUser [String] (Optional) Specifies the user name you want to use for authenticating with the guest OS where the file to be copied is located.
- -HostCredential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the host where the file is to be copied. Do not use this parameter if the HostUser and HostPassword parameters are used. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier than 4.0, or the VIX version you have installed is earlier than 1.10.
- -HostPassword [SecureString] (Optional) Specifies the password you want to use for authenticating with the host where the file is to be copied. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier than 4.0, or the VIX version you have installed is earlier than 1.10.
- -HostUser [String] (Optional) Specifies the user name you want to use for authenticating with the host where the file is to be copied. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier than 4.0, or the VIX version you have installed is earlier than 1.10.
- -LocalToGuest [SwitchParameter] (Required) Indicates that you want to copy a file from a local directory to the guest operating system of the virtual machine.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Source [String[]] (Required) Specifies the file you want to copy. If the file is on a virtual machine, specifies the absolute file path. Relative file paths are supported only when copying files from a local storage. Wildcards are allowed only at the end of the source path. If you are copying files from the guest operating system of a virtual machine to a local directory, the Source parameter supports wildcards only on vCenter Server 5.0 and later.
- -ToolsWaitSecs [Int32] (Optional) Specifies the time in seconds to wait for a response from the VMware Tools. If a non-positive value is provided, the system waits infinitely long time.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machine where the file is located.

**Examples:**

```powershell
Copy-VMGuestFile -Source c:\text.txt -Destination c:\temp\ -VM VM -GuestToLocal -GuestUser user -GuestPassword pass2
```
_Copies the text.txt file from the guest OS system to the local Temp directory._

```powershell
$vm = Get-VM -Name VM
```
_Copies files from a local machine to a guest operating system._

## Get

### `Get-VM`

**This cmdlet retrieves the virtual machines on a vCenter Server system.**

This cmdlet retrieves the virtual machines on a vCenter Server system. Returns a set of virtual machines that correspond to the filter criteria provided by the cmdlet parameters. For virtual machines with multiple NICs and multiple IP addresses, the IPAddress property of the VMGuest object contains all IP addresses of the virtual machine. The IP at position 0 is the primary IP address.

**Parameters:**

- -Datastore [StorageResource[]] (Optional) Specifies datastores or datastore clusters to filter the virtual machines associated with them. Passing values to this parameter through a pipeline is deprecated and will be removed in a future release.
- -Id [String[]] (Required) Specifies the IDs of the virtual machines you want to retrieve.
- -Location [VIContainer[]] (Optional) Specifies vSphere container objects you want to search for virtual machines. Supported container object types are: ResourcePool, VApp, VMHost, Folder, Cluster, Datacenter.
- -Name [String[]] (Optional) Specifies the names of the virtual machines you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -RelatedObject [VmRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more vSphere VirtualMachine objects that are related to them. This parameter accepts vCloud CIVM and OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the virtual machines that are associated with any of the specified tags.
- -VirtualSwitch [VirtualSwitchBase[]] (Optional) When specified, the cmdlet returns only the virtual machines that have network adapters attached to the specified switches.

**Examples:**

```powershell
Get-VM -Name MyVM*
```
_Retrieves all virtual machines whose names starting with "MyVM"._

```powershell
$myDatastore = Get-Datastore -Name "MyDatastore"
```
_Retrieves all virtual machines that reside on the specified datastore._

```powershell
$myDatacenter = Get-Datacenter -Name "MyDatacenter"
```
_Retrieves all virtual machines in the specified datacenter._

### `Get-VMGuest`

**This cmdlet retrieves the guest operating systems of the specified virtual machines.**

This cmdlet retrieves the guest operating systems of the specified virtual machines. To specify a server different from the default one, use the Server parameter. When Get-VMGuest is run against a virtual machine that is just starting, the properties of the returned VMGuest object are not filled at one time.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines whose guest operating systems you want to retrieve.

**Examples:**

```powershell
Get-VMGuest -VM VM
```
_Retrieves the guest OS of the virtual machine named VM._

### `Get-VMGuestDisk`

**This cmdlet retrieves storage volumes as seen by the virtual machines' guest operating systems.**

This cmdlet retrieves storage volumes as seen by the virtual machines' guest operating systems. Optionally, you can filter the results by the virtual machine or the file system path where the storage volume is mounted. Alternatively, this cmdlet allows retrieving the guest storage volumes, backed by a specified virtual disk.

**Parameters:**

- -VM [VirtualMachine[]] (Optional) Limits the results to guest disks on the specified virtual machines.
- -VMGuest [VMGuest[]] (Optional) Limits the results to guest disks on the specified virtual machine guests.
- -HardDisk [HardDisk[]] (Required) Limits the results to guest disks that are backed by the specified virtual disks.
- -DiskPath [String[]] (Optional) Filters the results based on the file system mount location. For example, "C:\" or "/etc/my-mount-root". This parameter supports wildcards.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VMGuestDisk -VM $myVM
```
_Retrieves all guest disks for a specified virtual machine._

```powershell
$myVms | Get-VMGuestDisk -DiskPath "C:\"
```
_Retrieves all C: drives on a specified set of virtual machines._

### `Get-VMQuestion`

**This cmdlet retrieves the pending questions for the specified virtual machines.**

This cmdlet retrieves the pending questions for the specified virtual machines. A question is a task that requires a response from you. If the VM parameter is not specified or its value is $null, the cmdlet returns all questions for all virtual machines on the specified servers.

**Parameters:**

- -QuestionId [String] (Optional) Specifies the IDs of the questions you want to retrieve.
- -QuestionText [String] (Optional) Specifies a phrase from the text that describes the questions you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose pending questions you want to retrieve.

**Examples:**

```powershell
Get-VMQuestion -VM VM
```
_Retrieves the questions of the VM virtual machine._

```powershell
$vm = Get-VM VM
```
_Retrieves the VM virtual machine questions that contain the phrase "have been moved or copied"._

### `Get-VMResourceConfiguration`

**This cmdlet retrieves information about the resource allocation between the selected virtual machines.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines whose resource configuration you want to retrieve.

**Examples:**

```powershell
Get-VMResourceConfiguration -VM VM | Format-Custom -Property DiskResourceConfiguration
```
_Displays the disk share for the VM virtual machine._

### `Get-VMStartPolicy`

**This cmdlet retrieves the start policy of the virtual machines on a vCenter Server system.**

This cmdlet retrieves the start policy of the virtual machines on a vCenter Server system. The virtual machines are specified by the VM parameter or retrieved from the host passed through the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose start policy you want to retrieve.
- -VMHost [VMHost[]] (Optional) Specifies the hosts of the virtual machines whose start policy you want to retrieve.

**Examples:**

```powershell
Get-VMStartPolicy -VM VM
```
_Retrieves the start policy of the virtual machine named VM._

## Invoke

### `Invoke-VMScript`

**This cmdlet runs a script in the guest OS of each of the specified virtual machines.**

This cmdlet runs a script in the guest OS of each of the specified virtual machines. To run Invoke-VMScript, the user must have read access to the folder containing the virtual machine and a Virtual Machine.Interaction.Console Interaction privilege. The virtual machines must be powered on and have VMware Tools installed and running. Network connectivity to the ESX system hosting the virtual machine must be present. To authenticate with the host or the guest OS, one of the HostUser/HostPassword (GuestUser/GuestPassword) pair and HostCredential (GuestCredential) parameters must be provided. The guest account you use to authenticate with the guest operating system must have administrator's privileges. For a list of supported operating systems, check the release notes of the specific VMware Tools version. To run this cmdlet against vCenter Server/ESXi 5.0 and later, you need VirtualMachine.GuestOperations.Modify and VirtualMachine.GuestOperations.Execute privileges.

**Parameters:**

- -GuestCredential [PSCredential] (Optional) Specifies a PSCredential object containing the credentials you want to use for authenticating with the virtual machine guest OS.
- -GuestPassword [SecureString] (Optional) Specifies the password you want to use for authenticating with the virtual machine guest OS.
- -GuestUser [String] (Optional) Specifies the user name you want to use for authenticating with the virtual machine guest OS.
- -HostCredential [PSCredential] (Optional) Specifies a PSCredential object containing the credentials you want to use for authenticating with the host. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier than 4.0, or the VIX version you have installed is earlier than 1.10.
- -HostPassword [SecureString] (Optional) Specifies the password you want to use for authenticating with the host. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier than 4.0, or the VIX version you have installed is earlier than 1.10.
- -HostUser [String] (Optional) Specifies the user name you want to use for authenticating with the host. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier than 4.0, or the VIX version you have installed is earlier than 1.10.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -ScriptText [String] (Required) Provides the text of the script you want to run. You can also pass to this parameter a string variable containing the path to the script.
- -ScriptType [ScriptType] (Optional) Specifies the type of the script. The valid values are PowerShell, Bat, and Bash. If the virtual machine OS is Windows, the default value is PowerShell. If the virtual machine OS is Linux, the default value is Bash.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -ToolsWaitSecs [Int32] (Optional) Specifies how long in seconds the system waits for connecting to the VMware Tools. The default value is 20.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines on whose guest operating systems you want to run the script.

**Examples:**

```powershell
Invoke-VMScript -VM VM -ScriptText "dir" -GuestUser administrator -GuestPassword pass2
```
_Lists the directory entries on the guest OS._

```powershell
$script = '&"$env:ProgramFiles\Common Files\Microsoft Shared\MSInfo\msinfo32.exe" /report "$env:Tmp\inforeport"'
```
_Runs a PowerShell script. In PowerShell, to access environment variables, you must use the following syntax: $env:<environment variable> (for example, $env:ProgramFiles). Also, to run the program, you must specify an ampersand (&) in front of the program path. The outer quotes ($script = '...') are required because this is how you define a string variable in PowerShell. The inner double quotes are required because there are spaces in the path._

```powershell
$script = '"%programfiles%\Common Files\Microsoft Shared\MSInfo\msinfo32.exe" /report "%tmp%\inforeport"'
```
_Runs a BAT script. In BAT scripts, to access environment variables, you must use the following syntax: %<environment variable>% (for example, %programfiles%)._

## Move

### `Move-VM`

**This cmdlet moves virtual machines to another location.**

This cmdlet moves a virtual machine to the location that is specified by the Destination or the Datastore parameters. The destination must be a folder, host, cluster, or a resource pool. You can move a virtual machine to a DRS cluster. Moving a virtual machine to the top level of a non-DRS cluster is only possible if the virtual machine is in a resource pool in that cluster. If the virtual machine is outside the non-DRS cluster, you need to specify a virtual machine host in that cluster as destination. When moving virtual machines that are powered on, vMotion is used. You can move storage and compute resources simultaneously. You can move virtual machines between vCenter Server systems of vSphere version 6.0 and later. To specify a server different from the default one, use the Server parameter. When you move a virtual machine from one vCenter Server system to another, only datastores are supported as storage destinations.

**Parameters:**

- -AdvancedOption [AdvancedOption[]] (Optional) This parameter is only applicable when a DatastoreCluster object is passed to the Datastore parameter. Specifies one or more rules for the placement of the virtual machines that you want to relocate.
- -Datastore [StorageResource] (Optional) Specifies the datastore or datastore cluster where you want to move the virtual machines. When you pass a datastore cluster to the Datastore parameter, you can also set the AdvancedOption parameter.
- -Destination [VIContainer] (Optional) Specifies a folder, host, cluster, or a resource pool where you want to move the virtual machines. If a data center is specified for the Destination parameter, you can move the virtual machines to the data center's "vmFolder" folder. The "vmFolder" is a system folder and is guaranteed to exist. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -DiskStorageFormat [VirtualDiskStorageFormat] (Optional) Specifies a new storage format for the hard disk of the virtual machine you want to move. This parameter is applicable only when moving a virtual machine to a different datastore, using the Datastore parameter. This parameter accepts Thin, Thick, and EagerZeroedThick values.
- -InventoryLocation [FolderContainer] (Optional) Specifies a data center or a virtual machine folder where you want to move the virtual machine.
- -Network [Network[]] (Optional) Specifies the destination networks for the specified virtual machine network adapters. The number of networks should be one or equal to the number of the specified network adapters. If one network and more than one network adapters are specified, you can migrate all network adapters to the specified network. You cannot use this parameter with the PortGroup parameter.
- -NetworkAdapter [NetworkAdapter[]] (Optional) Specifies the virtual machine network adapters you want to migrate to a new port group.
- -PortGroup [VirtualPortGroupBase[]] (Optional) Specifies the destination port groups for the specified virtual machine network adapters. The number of the port groups should be one or equal to the number of the specified network adapters. If one port group and more than one network adapters are specified, you can migrate all network adapters to the specified port group. You cannot use this parameter with the Network parameter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines you want to move to another location.
- -VMotionPriority [VMotionPriority] (Optional) Determines the priority that you should use for a vMotion operation.
- -StoragePolicy [StoragePolicy] (Optional) Specifies a new StoragePolicy for the virtual machine you want to move. The StoragePolicy is attached to VMHome and all hard disks.
- -DestinationSslThumbprint [String] (Optional) Specifies the SSL thumbprint of the destination server when moving virtual machines between vCenter Server systems.

**Examples:**

```powershell
Get-VM -Name VM | Move-VM -Destination 10.23.112.235
```
_Moves the virtual machine named VM from its current location to the host on IP address 10.23.112.235._

```powershell
Move-VM -VM VM -Destination Folder
```
_Moves the virtual machine to a folder called Folder. Note that you can move virtual machines only to folders containing virtual machines (the 'blue' folders in the vSphere Client)._

```powershell
Move-VM -VM 'MyVM' -Destination 'MyDestination'
```
_Moves a powered on virtual machine from one existing host to another by using vMotion, passing parameters by name._

## New

### `New-VM`

**This cmdlet creates a new virtual machine.**

This cmdlet creates a new virtual machine with the provided parameters. The network adapter and the Small Computer System Interface (SCSI) adapter of the new virtual machine are created of the recommended type for the operating system (OS) that is specified by the GuestId parameter. If  the OSCustomizationSpec parameter is used,  the virtual machine is customized according to the specification. You must specify values for at least one of the ResourcePool, VMHost, and VApp parameters.

**Parameters:**

- -AdvancedOption [AdvancedOption[]] (Optional) Specifies advanced options for creating virtual machines. Accepts only SdrsVMDiskAntiAffinityRule and SdrsVMAntiAffinityRule objects.
- -AlternateGuestName [String] (Optional) Specifies the full OS name of the new virtual machine. Use this parameter if the GuestID parameter is set to otherGuest or otherGuest64.
- -BootDelayMillisecond [Int64] (Optional) Specifies the time interval in milliseconds between a virtual machine power on or restart and the beginning of the boot sequence.
- -CD [SwitchParameter] (Optional) Indicates that you want to add a CD drive to the new virtual machine.
- -ContentLibraryItem [ContentLibraryItem] (Required) Specifies the content library template from which you want to deploy the virtual machine.
- -CoresPerSocket [Int32] (Optional) Specifies the number of virtual CPU cores per socket.
- -Datastore [StorageResource] (Optional) Specifies the datastore where you want to place the new virtual machine. If a DatastoreCluster is passed to the Datastore parameter, the virtual machine is placed in the DatastoreCluster in an automated SDRS mode and with enabled intra-VM affinity rule (unless another rule is specified). You can specify a SDRS rule when creating the virtual machine in a DatastoreCluster by passing either a SdrsVMDiskAntiAffinityRule object or a SdrsVMAntiAffinityRule object to the AdvancedOption parameter. These two rules are mutually exclusive.
- -DiskGB [Decimal[]] (Optional) Specifies the size in gigabytes (GB) of the disks that you want to create and add to the new virtual machine.
- -DiskMB [Int64[]] (Optional) This parameter is obsolete. Use DiskGB instead. Specifies the size in megabytes (MB) of the disks that you want to create and add to the new virtual machine.
- -DiskPath [String[]] (Optional) Specifies paths to virtual disks that you want to add to the new virtual machine.
- -DiskStorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the storage format of the disks of the virtual machine. This parameter accepts Thin, Thick, and EagerZeroedThick values.
- -DrsAutomationLevel [DrsAutomationLevel] (Optional) Specifies a DRS (Distributed Resource Scheduler) automation level. The valid values are FullyAutomated, Manual, PartiallyAutomated, AsSpecifiedByCluster, and Disabled. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. Specifying this parameter is only supported when the virtual machine is inside a cluster. Otherwise, an error appears.
- -Floppy [SwitchParameter] (Optional) Indicates that you want to add a floppy drive to the new virtual machine.
- -GuestId [String] (Optional) Specifies the guest operating system of the new virtual machine. The valid values for specific ESX versions are listed in the description of the VirtualMachineGuestOsIdentifier enumeration type in the vSphere API Reference available at http://www.vmware.com/support/developer/vc-sdk/. Depending on the hardware configuration of the host, some of the guest operating systems might be inapplicable.
- -HAIsolationResponse [HAIsolationResponse] (Optional) Indicates whether the virtual machine should be powered off if a host determines that it is isolated from the rest of the compute resource. The available values are AsSpecifiedByCluster, PowerOff, and DoNothing. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. Specifying this parameter is only supported when the virtual machine is inside a cluster. Otherwise, an error appears.
- -HardwareVersion [String] (Optional) Specifies the version of the new virtual machine. By default, the new virtual machine is created with the latest available version.
- -HARestartPriority [HARestartPriority] (Optional) Specifies the HA restart priority of the new virtual machine. The valid values are Disabled, Lowest, Low, Medium, High, Highest, and ClusterRestartPriority. VMware High Availability (HA) is a feature that detects failed virtual machines and automatically restarts them on alternative ESX hosts. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. Specifying this parameter is only supported when the virtual machine is inside a cluster. Otherwise, an error appears.
- -LinkedClone [SwitchParameter] (Optional) Indicates that you want to create a linked clone. When you set the LinkedClone parameter, the ReferenceSnapshot parameter becomes mandatory.
- -Location [Folder] (Optional) Specifies the folder where you want to place the new virtual machine.
- -MemoryGB [Decimal] (Optional) Specifies the memory size in gigabytes (GB) of the new virtual machine.
- -MemoryMB [Int64] (Optional) This parameter is obsolete. Use MemoryGB instead. Specifies the memory size in megabytes (MB) of the new virtual machine.
- -MigrationEncryption [VMMigrationEncryptionMode] (Optional) Specifies the encryption behavior when migrating the virtual machine. Valid options are: - Disabled: Do not use encrypted vSphere vMotion.
- -Name [String] (Required) Specifies a name for the new virtual machine. If you want to register or clone an existing virtual machine, this parameter is not mandatory.
- -NetworkName [String[]] (Optional) Specifies the networks to which you want to connect the new virtual machine. Specifying a distributed port group name is obsolete. Use the Portgroup parameter instead.
- -Notes [String] (Optional) Provides a description of the new virtual machine. The alias of this parameter is Description.
- -NumCpu [Int32] (Optional) Specifies the number of the virtual CPUs of the new virtual machine.
- -OSCustomizationSpec [OSCustomizationSpec] (Optional) Specifies a customization specification that is applied to the new virtual machine.
- -OvfConfiguration [Hashtable] (Optional) Specifies values for a set of user-configurable OVF properties.
- -Portgroup [VirtualPortGroupBase[]] (Optional) Specifies standard or distributed port groups to which you want to connect the virtual machine. For each specified port group, a new network adapter is created.
- -ReferenceSnapshot [Snapshot] (Optional) Specifies a source snapshot for the linked clone that you want to create. When you set the LinkedClone parameter, the ReferenceSnapshot parameter becomes mandatory.
- -ResourcePool [VIContainer] (Optional) Specifies where you want to place the new virtual machine. The parameter accepts VMHost, Cluster, ResourcePool, and VApp objects. If no value is specified, the virtual machine is added to the resource pool of its host.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SEVEnabled [Boolean] (Optional) Specifies whether SEV (Secure Encrypted Virtualization) is enabled or not. It allows the CPU to encrypt the memory and the state of the virtual machine. It is applicable for AMD CPUs only.
- -Template [Template] (Required) Specifies the virtual machine template that you want to use for the creation of the new virtual machine. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -VApp [VApp] (Optional) This parameter is deprecated. Use the ResourcePool parameter instead. Specifies the vApp where you want to create the new virtual machine.
- -Version [VMVersion] (Optional) This parameter is deprecated. Use the HardwareVersion parameter instead. Specifies the version of the new virtual machine. The valid values are v4, v7, v8, v9, v10, v11, v12, v13, and v14. By default, the new virtual machine is created with the latest available version.
- -VM [VirtualMachine[]] (Required) Specifies a virtual machine that you want to clone.
- -VMFilePath [String] (Required) Specifies a path to the virtual machine that you want to register.
- -VMHost [VMHost] (Optional) Specifies the host on which you want to create the new virtual machine.
- -VMSwapfilePolicy [VMSwapfilePolicy] (Optional) Specifies the swapfile placement policy. The following values are valid:
- -SkipHardDisks [SwitchParameter] (Optional) Specifies whether to apply the StoragePolicy or Encryption to the hard disks in the new virtual machine.
- -StoragePolicy [StoragePolicy] (Optional) Specifies the StoragePolicy that you want to attach to the new virtual machine during creation. If the StoragePolicy is an encryption policy, the new virtual machine is encrypted.
- -ReplicationGroup [ReplicationGroup] (Optional) Specifies the ReplicationGroup where you want to place the new virtual machine. It is applicable with the storage policy provided in the StoragePolicy parameter.
- -StoragePolicyTarget [StoragePolicyTargetType] (Optional) Specifies the target of the StoragePolicy in the virtual machine or in the VM parameter.
- -KeyProvider [KeyProvider] (Optional) Specifies the key provider that you want to use for the encryption key while creating the new virtual machine. If StoragePolicy is not specified, the default encryption storage policy "VM Encryption Policy" is used.
- -CpuHotAddEnabled [Boolean] (Optional) Specifies if virtual processors can be added to the virtual machine while it is running.
- -CpuHotRemoveEnabled [Boolean] (Optional) Specifies if virtual processors can be removed from the virtual machine while it is running.
- -MemoryHotAddEnabled [Boolean] (Optional) Specifies if memory can be added to the virtual machine while it is running.

**Examples:**

```powershell
$myTargetVMHost = Get-VMHost -Name MyVMHost1
```
_Creates a virtual machine by specifying a target host, a target datastore, and a network to connect to, and configures the settings for the virtual machine._

```powershell
$myCluster = Get-Cluster -Name MyCluster1
```
_Creates a virtual machine by specifying a cluster. The ResourcePool parameter accepts ResourcePool, Cluster, VApp, and standalone VMHost objects._

```powershell
$vmhost = Get-VMHost -Name MyVMHost1
```
_Creates a virtual machine by specifying a cluster and explicitly selecting the host, instead of allowing autoselection of a target host._

## Open

### `Open-VMConsoleWindow`

**This cmdlet opens a window to the virtual machine's console.**

**Parameters:**

- -FullScreen [SwitchParameter] (Optional) If specified, opens the virtual machine's console window in full-screen mode.
- -Server [VIConnection[]] (Optional) Specifies the vCenter Server systems or cloud server instances on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -UrlOnly [SwitchParameter] (Optional) If specified, the cmdlet returns the URL for opening a console window to the virtual machine without actually opening the console window.
- -VM [RemoteConsoleVM[]] (Required) Specifies the virtual machine for which you want to open a remote console. Supports vCloud and vSphere virtual machines.

**Examples:**

```powershell
Get-CIVM myVM | Open-VMConsoleWindow -FullScreen
```
_Opens the console of the specified virtual machine in full-screen mode._

## Remove

### `Remove-VM`

**This cmdlet removes the specified virtual machines from the vCenter Server system.**

This cmdlet removes the specified virtual machines from the vCenter Server system. If the value of the DeletePermanently parameter is $true, the cmdlet not only removes the virtual machines from the inventory, but also deletes them from the disk.

**Parameters:**

- -DeletePermanently [SwitchParameter] (Optional) Indicates that you want to delete the virtual machines not only from the inventory, but from the datastore.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines you want to remove.

**Examples:**

```powershell
Remove-VM -VM 'myVM' -DeletePermanently
```
_Removes the 'myVM' virtual machine and deletes its files from the ESXi host._

## Restart

### `Restart-VM`

**This cmdlet restarts the specified virtual machines.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines you want to restart.

**Examples:**

```powershell
Restart-VM -VM VM -RunAsync -Confirm
```
_Restarts the VM virtual machine after user confirmation. The cmdlet returns without waiting for the task to complete._

### `Restart-VMGuest`

**This cmdlet restarts the virtual machine guest operating systems.**

**Parameters:**

- -Guest [VMGuest[]] (Optional) Specifies the virtual machine guest operating systems you want to restart.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose operating systems you want to restart. The specified virtual machines must have VMware Tools installed.

**Examples:**

```powershell
Get-VM VM | Restart-VMGuest
```
_Restarts the guest OS of the virtual machine named VM._

## Set

### `Set-VM`

**This cmdlet modifies the configuration of the virtual machine.**

This cmdlet modifies the configuration of the virtual machine. If the OSCustomizationSpec parameter is used, the cmdlet customizes the virtual machine according to the specification. In addition, the cmdlet allows you to revert a virtual machine to a snapshot and convert a virtual machine to a template.

**Parameters:**

- -AlternateGuestName [String] (Optional) Specifies the full name of the guest OS for the virtual machine if the value of the GuestID parameter is set to otherGuest or otherGuest64.
- -BootDelayMillisecond [Int64] (Optional) Specifies the time interval in milliseconds between a virtual machine power on or restart and the beginning of the boot sequence.
- -CoresPerSocket [Int32] (Optional) Specifies the number of virtual CPU cores per socket.
- -DisableEncryption [SwitchParameter] (Required) Indicates that you want to decrypt the specified virtual machine.
- -DrsAutomationLevel [DrsAutomationLevel] (Optional) Specifies a Distributed Resource Scheduler (DRS) automation level. The valid values are FullyAutomated, Manual, PartiallyAutomated, AsSpecifiedByCluster, and Disabled. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. Specifying this parameter is only supported when the virtual machine is inside a cluster. Otherwise, an error appears.
- -GuestId [String] (Optional) Specifies the guest operating system of the virtual machine. The valid values for specific ESX versions are listed in the description of the VirtualMachineGuestOsIdentifier enumeration type in the vSphere API Reference available at http://www.vmware.com/support/developer/vc-sdk/. Depending on the hardware configuration of the host, some of the guest operating systems might be inapplicable.
- -HAIsolationResponse [HAIsolationResponse] (Optional) Indicates whether the virtual machine should be powered off if a host determines that it's isolated from the rest of the compute resource. The valid values are AsSpecifiedByCluster, PowerOff, and DoNothing. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. Specifying this parameter is only supported when the virtual machine is inside a cluster. Otherwise, an error appears.
- -HardwareVersion [String] (Optional) Specifies the version to which you want to upgrade the virtual machine. You cannot downgrade to an earlier version.
- -HARestartPriority [HARestartPriority] (Optional) Specifies the virtual machine High Availability (HA) restart priority. The valid values are Disabled, Lowest, Low, Medium, High, Highest and ClusterRestartPriority. VMware HA is a feature that detects failed virtual machines and automatically restarts them on alternative ESX hosts. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. Specifying this parameter is only supported when the virtual machine is inside a cluster. Otherwise, an error appears.
- -MemoryGB [Decimal] (Optional) Specifies the memory size in gigabytes (GB).
- -MemoryMB [Int64] (Optional) This parameter is obsolete. Use MemoryGB instead. Specifies the memory size in megabytes (MB).
- -MigrationEncryption [VMMigrationEncryptionMode] (Optional) Specifies the encryption behavior when migrating the virtual machine. Valid options are: - Disabled: Do not use encrypted vSphere vMotion.
- -Name [String] (Optional) Specifies a new name for the virtual machine.
- -Notes [String] (Optional) Provides a description for the virtual machine. The alias of this parameter is Description.
- -NumCpu [Int32] (Optional) Specifies the number of virtual CPUs.
- -OSCustomizationSpec [OSCustomizationSpec] (Optional) Specifies a customization specification you want to apply to the virtual machine. This works only in 32-bit mode.
- -PromoteDisks [SwitchParameter] (Optional) Promotes virtual machine disks. You can use this parameter to promote a linked clone virtual machine to a full clone.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SEVEnabled [Boolean] (Optional) Specifies whether SEV (Secure Encrypted Virtualization) is enabled or not. It allows the CPU to encrypt the memory and the state of the virtual machine. It is applicable for AMD CPUs only.
- -SkipHardDisks [SwitchParameter] (Optional) Indicates that the StoragePolicy or encryption (KeyProvider) is applied to vmhome only.
- -Snapshot [Snapshot] (Optional) Specifies a snapshot whose state you want to apply to the virtual machine.
- -StoragePolicy [StoragePolicy] (Optional) Specifies the StoragePolicy that you want to attach to the specified virtual machine. If the StoragePolicy is an encryption policy, the virtual machine is encrypted. Otherwise, the virtual machine is decrypted, if it's encrypted before the cmdlet, and attached with the new StoragePolicy.
- -ToTemplate [SwitchParameter] (Optional) Indicates that you want to convert the virtual machine to a template.
- -Version [VMVersion] (Optional) This parameter is deprecated. Use the HardwareVersion parameter instead. Specifies the version to which you want to upgrade the virtual machine. The valid values are v4, v7, v8, v9, v10, v11, v12, v13, and v14. You cannot downgrade to an earlier version.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machine that you want to configure.
- -VMSwapFilePolicy [VMSwapfilePolicy] (Optional) Specifies the swapfile placement policy. The following values are valid:
- -CpuHotAddEnabled [Boolean] (Optional) Specifies if virtual processors can be added to the virtual machine while it is running.
- -CpuHotRemoveEnabled [Boolean] (Optional) Specifies if virtual processors can be removed from the virtual machine while it is running.
- -MemoryHotAddEnabled [Boolean] (Optional) Specifies if memory can be added to the virtual machine while it is running.
- -KeyProvider [KeyProvider] (Optional) Specifies the key provider that you want to use for the encryption key while encrypting the specified virtual machine. If StoragePolicy is not specified, the default encryption storage policy "VM Encryption Policy" is used.

**Examples:**

```powershell
$template = Get-VM VM | Set-VM -ToTemplate -Name VMTemplate
```
_Converts the VM virtual machine to a template and stores the template in the $template variable._

```powershell
Get-VM -Location ResourcePool01 | Set-VM -MemoryGB 2 -NumCPU 2
```
_Upgrades the memory and CPU count of the virtual machines in ResourcePool01._

```powershell
Set-VM -VM VM -HardwareVersion vmx-07
```
_Upgrades the virtual hardware version of the VM virtual machine._

### `Set-VMQuestion`

**This cmdlet answers the specified virtual machine question.**

This cmdlet answers the specified virtual machine question using the value of the Option parameter. If the DefaultOption parameter is set to $true, the cmdlet answers the question with a default option, if any.

**Parameters:**

- -DefaultOption [SwitchParameter] (Required) Indicates that you want to answer the virtual machine question using a default option. If no default option exists for the question, an error is generated.
- -Option [Object] (Required) Specifies an object or string to provide an option to the virtual machine question. Wildcards are supported for string values. The string can be used to specify an option ID or label. If the string does not match a valid option ID or label, or if there are multiple matches, an error is generated.
- -VMQuestion [VMQuestion[]] (Required) Specifies the virtual machine question you want to answer.

**Examples:**

```powershell
Set-VMQuestion -VMQuestion $question -DefaultOption
```
_Answers the question stored in the $question with a default option._

```powershell
Set-VMQuestion -VMQuestion $question -Option "Cancel"
```
_Answers the question stored in the $question variable with "cancel"._

```powershell
Get-VM VM | Get-VMQuestion | Set-VMQuestion -DefaultOption
```
_Answers the question of VM virtual machine with a default option._

### `Set-VMResourceConfiguration`

**This cmdlet configures resource allocation between the virtual machines.**

This cmdlet configures resource allocation between the virtual machines. To retain the current value of a setting, omit the corresponding parameter. To activate a setting (only applicable to the nullable limit settings), pass $null.

**Parameters:**

- -Configuration [VMResourceConfiguration[]] (Required) Specifies the configuration object you want to modify.
- -CpuAffinity [CpuAffinity] (Optional) The use of this parameter is deprecated. Use CpuAffinityList instead.
- -CpuAffinityList [Int32[]] (Optional) Specifies the distribution of virtual machine CPUs across the physical cores or hyperthreads of the host. You must pass exactly as many arguments as the number of CPUs of the virtual machine. Each argument specifies the physical core or hyperthread that the virtual machine will use. Valid arguments are positive integers. To clear formerly specified arguments, pass an empty array.
- -CpuLimitMhz [Int64] (Optional) Specifies the limit on CPU usage in MHz. Utilization will not exceed this limit even if there are available resources.
- -CpuReservationMhz [Int64] (Optional) Specifies the number of CPU MHz that are guaranteed to be available.
- -CpuSharesLevel [SharesLevel] (Optional) Specifies the CPU allocation level. Used in relative allocation between virtual machines. The valid values are Custom, High, Low, and Normal.
- -Disk [HardDisk[]] (Optional) Specifies the virtual hard disk you want to configure.
- -DiskLimitIOPerSecond [Int64] (Optional) Specifies the disk limit IO per second. The valid values are in the range between 16 and 2147483647. -1 means unlimited.
- -DiskSharesLevel [SharesLevel] (Optional) Specifies the allocation level. The level is a simplified view of shares. Levels map to a pre-determined set of numeric values for shares. If the shares value does not map to a predefined size, then the level is set as custom.
- -HtCoreSharing [HTCoreSharing] (Optional) Specifies whether a virtual machine is scheduled to share a physical processor core (assuming hyperthreading is enabled on the host at all). The following values are valid:
- -MemLimitGB [Decimal] (Optional) Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemLimitMB [Int64] (Optional) This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemReservationGB [Decimal] (Optional) Specifies the guaranteed available memory in gigabytes (GB).
- -MemReservationMB [Int64] (Optional) This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB).
- -MemSharesLevel [SharesLevel] (Optional) Specifies the memory allocation level for this pool. Used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal.
- -NumCpuShares [Int32] (Optional) Specifies the CPU allocation level for this pool. Used in relative allocation between resource consumers. This parameter is ignored unless CpuSharesLevel is set to Custom.
- -NumDiskShares [Int32] (Optional) Specifies the number of shares allocated. Used to determine resource allocation in case of resource contention.
- -NumMemShares [Int32] (Optional) Specifies the number of memory shares allocated. Used to determine resource allocation in case of resource contention.

**Examples:**

```powershell
Set-VMResourceConfiguration -Configuration $conf -CpuAffinity ([CpuAffinity]::Cpu1 -bor [CpuAffinity]::Cpu2)
```
_Specifies two affinities for the virtual machine resource configuration in the $conf variable. Bit Or is used._

### `Set-VMStartPolicy`

**This cmdlet modifies the virtual machine start policy.**

This cmdlet modifies the virtual machine start policy. Start policy defines what happens to virtual machines when the server starts up or stops.

**Parameters:**

- -InheritStartDelayFromHost [SwitchParameter] (Optional) Indicates that the virtual machine uses the value of the StartDelay parameter of the host.
- -InheritStopActionFromHost [SwitchParameter] (Optional) Indicates that the virtual machine uses the value of the StopAction parameter of the host.
- -InheritStopDelayFromHost [SwitchParameter] (Optional) Indicates that the virtual machine uses the value of the StopDelay parameter of the host.
- -InheritWaitForHeartbeatFromHost [SwitchParameter] (Optional) Indicates that the virtual machine uses the value of the WaitforHeartbeat parameter of the host.
- -StartAction [VmStartAction] (Optional) Specifies a start action for virtual machines. It can be None or PowerOn.
- -StartDelay [Int32] (Optional) Specifies a default start delay in seconds.
- -StartOrder [Int32] (Optional) Specifies a number to define the virtual machines start order.
- -StartPolicy [VMStartPolicy[]] (Required) Specifies the virtual machine start policy you want to modify.
- -StopAction [VmStopAction] (Optional) Specifies the default action of the virtual machine when the server stops. The valid values are None, Suspend, PowerOff, and GuestShutDown.
- -StopDelay [Int32] (Optional) Specifies the default stop delay in seconds.
- -UnspecifiedStartOrder [SwitchParameter] (Optional) Indicates that no order is defined for starting the virtual machines.
- -WaitForHeartBeat [Boolean] (Optional) Indicates whether the virtual machine should start after receiving a heartbeat, ignore heartbeats and start after the StartDelay has elapsed ($true), or follow the system default before powering on ($false). When a virtual machine is next in the start order, the system either waits a specified period of time for a virtual machine to power on or it waits until it receives a successful heartbeat from a powered on virtual machine.

**Examples:**

```powershell
$vmstartpolicy = Get-VMStartPolicy -VM VM
```
_Retrieves the start policy of the VM virtual machine and defines that when the server starts, the virtual machine is powered on._

```powershell
Get-VM VM | Get-VMStartPolicy | Set-VMStartpolicy -InheritStopActionFromHost -InheritStopDelayFromHost
```
_Reconfigures the start policy of the VM virtual machine to inherit the values of the StopAction and StopDelay from the host._

```powershell
Get-VM VM | Get-VMStartPolicy | Set-VMStartpolicy -StartAction PowerOn -StartOrder 2 -StartDelay 300 -StopAction GuestShutDown -StopDelay 300
```
_Retrieve the start policy of the specified virtual machine and modify its configuration settings._

## Start

### `Start-VM`

**This cmdlet powers on virtual machines.**

This cmdlet powers on the virtual machines specified by the VM parameter.

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines you want to power on.

**Examples:**

```powershell
Start-VM -VM VM -Confirm -RunAsync
```
_Asynchronously starts the virtual machine named VM. Before initializing the task, asks for confirmation._

## Stop

### `Stop-VM`

**This cmdlet powers off  virtual machines.**

This cmdlet stops the virtual machines specified by the VM parameter.

**Parameters:**

- -Kill [SwitchParameter] (Optional) Indicates that you want to stop the specified virtual machines by terminating their processes running on the ESX. You can use this parameter to stop a virtual machine that is not responding and cannot be stopped or restarted in other ways. To use the Kill parameter, you need to have a direct connection to ESX 4.1 or later.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines you want to power off.

**Examples:**

```powershell
Stop-VM -VM VM -Confirm
```
_Stops the virtual machine named VM after confirmation by the user._

```powershell
Stop-VM -VM VM -Kill -Confirm:$false
```
_Stops the virtual machine VM by terminating its process running on the ESX._

### `Stop-VMGuest`

**This cmdlet shuts down the specified virtual machine guest OS.**

This cmdlet issues a command to the guest operating system asking it to prepare for a shutdown operation. Returns immediately and does not wait for the guest operating system to complete the operation.

**Parameters:**

- -Guest [VMGuest[]] (Optional) Specifies the virtual machine guests you want to shut down.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose operating systems you want to shut down. The virtual machines must have VMware Tools installed.

**Examples:**

```powershell
Get-VM VM | Stop-VMGuest
```
_Shuts down the guest OS of the virtual machine named VM._

## Suspend

### `Suspend-VM`

**This cmdlet suspends virtual machines.**

This cmdlet suspends the virtual machines specified by the VM parameter. You can use the suspend feature to make resources available on a short-term basis or for other situations in which you want to put a virtual machine on hold without powering it down. Using wildcards is supported with virtual machine names.

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines you want to suspend.

**Examples:**

```powershell
Get-VM VM | Suspend-VM
```
_Suspends the virtual machine named VM._

### `Suspend-VMGuest`

**This cmdlet suspends the specified guest operating systems.**

This cmdlet issues a command to the specified guest operating system asking it to prepare for a suspend operation.

**Parameters:**

- -Guest [VMGuest[]] (Optional) Specifies the guest operating systems you want to suspend.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose operating systems you want to suspend. The virtual machines must have VMware Tools installed.

**Examples:**

```powershell
Get-VM VM| Suspend-VMGuest
```
_Suspends the guest OS of the virtual machine named VM._

## Test

### `Test-VsanVMCreation`

**This cmdlet runs a virtual machine creation test on the specified vSAN clusters and returns the test results.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters on which you want to run a vSAN virtual machine creation test.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TimeoutSeconds [Int32] (Optional) Specifies the timeout for the virtual machine creation test in seconds. The default value is 120 seconds.
- -UseCache [SwitchParameter] (Optional) Indicates whether to get a cached result from the server. If specified, a test is not run on the server and the last result cached on the server side is returned. If not specified, a test is run on the server side and the result is returned.

**Examples:**

```powershell
Test-VsanVMCreation -Cluster $cluster -TimeoutSeconds 150
```
_Runs the virtual machine creation test with a timeout of 150 seconds on the $cluster vSAN cluster and returns the result of the test._

```powershell
Test-VsanVMCreation -Cluster $cluster -UseCache
```
_Gets the result of the last virtual machine creation test run on the $cluster vSAN cluster._

## Unlock

### `Unlock-VM`

**This cmdlet unlocks the specified virtual machine.**

This cmdlet unlocks the specified virtual machine. The virtual machine should be encrypted, otherwise, this cmdlet would fail. If the virtual machine is in CryptoLocked state, this cmdlet will make the virtual machine become connected state.

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the connected viserver on which you want to run the cmdlet. If no value is passed to this parameter, the command runs on the default viservers. For more information about default viservers, see the description of the Connect-VIServer cmdlet.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machine that you want to unlock.

**Examples:**

```powershell
Get-VM 'MyVM' | Unlock-VM
```
_Unlocks the virtual machine named 'MyVM'._

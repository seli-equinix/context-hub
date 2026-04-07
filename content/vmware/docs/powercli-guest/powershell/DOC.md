---
name: powercli-guest
description: "VMware PowerCLI 13.3 — guest OS operations: run scripts, copy files, manage guest tools"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Copy-VMGuestFile,Dismount-Tools,Get-VMGuest,Get-VMGuestDisk,Invoke-VMScript,Mount-Tools,Restart-VMGuest,Shutdown-VMGuest,Stop-VMGuest,Suspend-VMGuest,Update-Tools,Wait-Tools"
---

# VMware PowerCLI — guest OS operations

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Copy-VMGuestFile` | This cmdlet copies files and folders from and to the guest OS of the specified virtual machines u... |
| `Dismount-Tools` | This cmdlet dismounts the VMware Tools installer CD. |
| `Get-VMGuest` | This cmdlet retrieves the guest operating systems of the specified virtual machines. |
| `Get-VMGuestDisk` | This cmdlet retrieves storage volumes as seen by the virtual machines' guest operating systems. |
| `Invoke-VMScript` | This cmdlet runs a script in the guest OS of each of the specified virtual machines. |
| `Mount-Tools` | This cmdlet mounts the VMware Tools CD installer as a CD-ROM on the guest operating system. |
| `Restart-VMGuest` | This cmdlet restarts the virtual machine guest operating systems. |
| `Shutdown-VMGuest` | This cmdlet shuts down the specified virtual machine guest OS. |
| `Stop-VMGuest` | This cmdlet shuts down the specified virtual machine guest OS. |
| `Suspend-VMGuest` | This cmdlet suspends the specified guest operating systems. |
| `Update-Tools` | This cmdlet upgrades VMware Tools on the specified virtual machine guest OS. |
| `Wait-Tools` | This cmdlet waits for VMware Tools on the specified virtual machines to load. |

---

### Copy-VMGuestFile

This cmdlet copies files and folders from and to the guest OS of the specified virtual machines using VMware Tools.

This cmdlet copies files and folders from and to the guest OS of the specified virtual machines using VMware Tools. Use the GuestUser and GuestPassword, or GuestCredential parameters to authenticate when connecting to the VMware Tools. To authenticate with the host, use the HostUser and HostPassword, or HostCredential parameters. SSPI is not supported. For a list of supported operating systems, see the PowerCLI User's Guide.

**Returns**: `None`

```
Copy-VMGuestFile
    -Destination <String>
    [-Force]
    [-GuestCredential <PSCredential>]
    [-GuestPassword <SecureString>]
    -GuestToLocal
    [-GuestUser <String>]
    [-HostCredential <PSCredential>]
    [-HostPassword <SecureString>]
    [-HostUser <String>]
    -LocalToGuest
    [-Server <VIServer[]>]
    -Source <String[]>
    [-ToolsWaitSecs <Int32>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `String` | Yes | Specifies the destination path where you want to copy the file. If the destination points to a virtual machine, specify the absolute file path. Relative destination paths are supported only when co... |
| `-Force` | `SwitchParameter` | No | Indicates that the non-existing directories in the specified destination path are automatically created. |
| `-GuestCredential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the guest OS where the file to be copied is located. |
| `-GuestPassword` | `SecureString` | No | Specifies the password you want to use for authenticating with the guest OS where the file to be copied is located. |
| `-GuestToLocal` | `SwitchParameter` | Yes | Indicates that you want to copy a file from the guest operating system of the virtual machine to a local directory. |
| `-GuestUser` | `String` | No | Specifies the user name you want to use for authenticating with the guest OS where the file to be copied is located. |
| `-HostCredential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the host where the file is to be copied. Do not use this parameter if the HostUser and HostPassword parameters are ... |
| `-HostPassword` | `SecureString` | No | Specifies the password you want to use for authenticating with the host where the file is to be copied. You need to specify host credentials only if the version of the vCenter Server or ESX you are... |
| `-HostUser` | `String` | No | Specifies the user name you want to use for authenticating with the host where the file is to be copied. You need to specify host credentials only if the version of the vCenter Server or ESX you ar... |
| `-LocalToGuest` | `SwitchParameter` | Yes | Indicates that you want to copy a file from a local directory to the guest operating system of the virtual machine. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Source` | `String[]` | Yes | Specifies the file you want to copy. If the file is on a virtual machine, specifies the absolute file path. Relative file paths are supported only when copying files from a local storage. Wildcards... |
| `-ToolsWaitSecs` | `Int32` | No | Specifies the time in seconds to wait for a response from the VMware Tools. If a non-positive value is provided, the system waits infinitely long time. |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machine where the file is located. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Dismount-Tools

This cmdlet dismounts the VMware Tools installer CD.

This cmdlet dismounts the VMware Tools installer CD from one or more virtual machines operating systems specified by the VM and Guest parameters. To specify a server different from the default one, use the Server parameter. The virtual machines must be powered on.

**Returns**: `None`

```
Dismount-Tools
    [-Guest <VMGuest[]>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the guest operating systems from which you want to remove the VMware Tools. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which the search for virtual machine names passed by the VM parameter is performed. If no value is given to this parameter, the search for the virtual machin... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines from which you want to remove the VMware Tools. |

---

### Get-VMGuest

This cmdlet retrieves the guest operating systems of the specified virtual machines.

This cmdlet retrieves the guest operating systems of the specified virtual machines. To specify a server different from the default one, use the Server parameter. When Get-VMGuest is run against a virtual machine that is just starting, the properties of the returned VMGuest object are not filled at one time.

**Returns**: `VMGuest`

```
Get-VMGuest
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines whose guest operating systems you want to retrieve. |

---

### Get-VMGuestDisk

This cmdlet retrieves storage volumes as seen by the virtual machines' guest operating systems.

This cmdlet retrieves storage volumes as seen by the virtual machines' guest operating systems. Optionally, you can filter the results by the virtual machine or the file system path where the storage volume is mounted. Alternatively, this cmdlet allows retrieving the guest storage volumes, backed by a specified virtual disk.

**Returns**: `VMGuestDisk`

```
Get-VMGuestDisk
    [-VM <VirtualMachine[]>]
    [-VMGuest <VMGuest[]>]
    -HardDisk <HardDisk[]>
    [-DiskPath <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VM` | `VirtualMachine[]` | No | Limits the results to guest disks on the specified virtual machines. |
| `-VMGuest` | `VMGuest[]` | No | Limits the results to guest disks on the specified virtual machine guests. |
| `-HardDisk` | `HardDisk[]` | Yes | Limits the results to guest disks that are backed by the specified virtual disks. |
| `-DiskPath` | `String[]` | No | Filters the results based on the file system mount location. For example, "C:\" or "/etc/my-mount-root". This parameter supports wildcards. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Invoke-VMScript

This cmdlet runs a script in the guest OS of each of the specified virtual machines.

This cmdlet runs a script in the guest OS of each of the specified virtual machines. To run Invoke-VMScript, the user must have read access to the folder containing the virtual machine and a Virtual Machine.Interaction.Console Interaction privilege. The virtual machines must be powered on and have VMware Tools installed and running. Network connectivity to the ESX system hosting the virtual machine must be present. To authenticate with the host or the guest OS, one of the HostUser/HostPasswor...

**Returns**: `VMScriptResult`

```
Invoke-VMScript
    [-GuestCredential <PSCredential>]
    [-GuestPassword <SecureString>]
    [-GuestUser <String>]
    [-HostCredential <PSCredential>]
    [-HostPassword <SecureString>]
    [-HostUser <String>]
    [-RunAsync]
    -ScriptText <String>
    [-ScriptType <ScriptType>]
    [-Server <VIServer[]>]
    [-ToolsWaitSecs <Int32>]
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-GuestCredential` | `PSCredential` | No | Specifies a PSCredential object containing the credentials you want to use for authenticating with the virtual machine guest OS. |
| `-GuestPassword` | `SecureString` | No | Specifies the password you want to use for authenticating with the virtual machine guest OS. |
| `-GuestUser` | `String` | No | Specifies the user name you want to use for authenticating with the virtual machine guest OS. |
| `-HostCredential` | `PSCredential` | No | Specifies a PSCredential object containing the credentials you want to use for authenticating with the host. You need to specify host credentials only if the version of the vCenter Server or ESX yo... |
| `-HostPassword` | `SecureString` | No | Specifies the password you want to use for authenticating with the host. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlier... |
| `-HostUser` | `String` | No | Specifies the user name you want to use for authenticating with the host. You need to specify host credentials only if the version of the vCenter Server or ESX you are authenticating with is earlie... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-ScriptText` | `String` | Yes | Provides the text of the script you want to run. You can also pass to this parameter a string variable containing the path to the script. |
| `-ScriptType` | `ScriptType` | No | Specifies the type of the script. The valid values are PowerShell, Bat, and Bash. If the virtual machine OS is Windows, the default value is PowerShell. If the virtual machine OS is Linux, the defa... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-ToolsWaitSecs` | `Int32` | No | Specifies how long in seconds the system waits for connecting to the VMware Tools. The default value is 20. |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines on whose guest operating systems you want to run the script. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Mount-Tools

This cmdlet mounts the VMware Tools CD installer as a CD-ROM on the guest operating system.

This cmdlet mounts the VMware Tools CD installer as a CD-ROM on the guest operating system that is specified by the Guest or VM parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `None`

```
Mount-Tools
    [-Guest <VMGuest[]>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the guest operating systems on which you want to mount VMware Tools. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines on which you want to mount VMware Tools. |

---

### Restart-VMGuest

This cmdlet restarts the virtual machine guest operating systems.

**Returns**: `VMGuest`

```
Restart-VMGuest
    [-Guest <VMGuest[]>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the virtual machine guest operating systems you want to restart. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose operating systems you want to restart. The specified virtual machines must have VMware Tools installed. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Shutdown-VMGuest

This cmdlet shuts down the specified virtual machine guest OS.

This cmdlet issues a command to the guest operating system asking it to prepare for a shutdown operation. Returns immediately and does not wait for the guest operating system to complete the operation.

**Returns**: `VMGuest`

```
Shutdown-VMGuest
    [-Guest <VMGuest[]>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the virtual machine guests you want to shut down. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose operating systems you want to shut down. The virtual machines must have VMware Tools installed. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Stop-VMGuest

This cmdlet shuts down the specified virtual machine guest OS.

This cmdlet issues a command to the guest operating system asking it to prepare for a shutdown operation. Returns immediately and does not wait for the guest operating system to complete the operation.

**Returns**: `VMGuest`

```
Stop-VMGuest
    [-Guest <VMGuest[]>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the virtual machine guests you want to shut down. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose operating systems you want to shut down. The virtual machines must have VMware Tools installed. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Suspend-VMGuest

This cmdlet suspends the specified guest operating systems.

This cmdlet issues a command to the specified guest operating system asking it to prepare for a suspend operation.

**Returns**: `VMGuest`

```
Suspend-VMGuest
    [-Guest <VMGuest[]>]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the guest operating systems you want to suspend. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies the virtual machines whose operating systems you want to suspend. The virtual machines must have VMware Tools installed. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Update-Tools

This cmdlet upgrades VMware Tools on the specified virtual machine guest OS.

This cmdlet upgrades the VMware Tools on the specified virtual machine guest OS. VMware Tools must be installed prior to updating it. After VMware Tools is updated, the virtual machine is restarted unless the NoReboot parameter is specified.

**Returns**: `None`

```
Update-Tools
    [-Guest <VMGuest[]>]
    [-NoReboot]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | No | Specifies the guest operating systems on which you want to update VMware Tools. |
| `-NoReboot` | `SwitchParameter` | No | Indicates that you do not want to reboot the system after updating VMware Tools. This parameter is supported only for Windows operating systems. NoReboot passes the following set of options to the ... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | No | Specifies a list of the virtual machines whose VMware Tools you want to upgrade. |

---

### Wait-Tools

This cmdlet waits for VMware Tools on the specified virtual machines to load.

This cmdlet waits for VMware Tools of the specified virtual machines to load. The cmdlet returns the virtual machines or guests on which VMware Tools have loaded successfully within the specified time limits. You can cancel the operation before completion using Ctrl+C. The successful completion of Wait-Tools means that VMware Tools  have loaded, but it does not guarantee for the start of other services. Updating the returned VMGuest objects requires additional communication with VMware Tools ...

**Returns**: `VirtualMachine`

```
Wait-Tools
    -Guest <VMGuest[]>
    [-HostCredential <PSCredential>]
    [-HostPassword <SecureString>]
    [-HostUser <String>]
    [-Server <VIServer[]>]
    [-TimeoutSeconds <Int32>]
    -VM <VirtualMachine[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Guest` | `VMGuest[]` | Yes | Specifies the guest operating systems for which you want to wait VMware Tools to load. |
| `-HostCredential` | `PSCredential` | No | Specifies credentials for authenticating with the ESX/ESXi host of the specified virtual machine. This parameter is needed only if you have authenticated with vCenter Server via SSPI. If SSPI is no... |
| `-HostPassword` | `SecureString` | No | Specifies a password for authenticating with the ESX host of the specified virtual machine. This parameter is needed only if you have authenticated with the vCenter Server via SSPI. If no SSPI is u... |
| `-HostUser` | `String` | No | Specifies a username for authenticating with the ESX/ESXi host of the specified virtual machine. This parameter is needed only if you have authenticated with vCenter Server via SSPI. If SSPI is not... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TimeoutSeconds` | `Int32` | No | Specifies the time period in seconds to wait for VMware Tools to start before cancelling the operation. |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines for which you want to wait VMware Tools to load. |

---

---
name: powercli-vm-operations
description: "VMware PowerCLI 13.3 — Virtual machine lifecycle — create, power, configure, clone, move, remove VMs"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,vm-operations,Copy-VMGuestFile, Get-VM, Get-VMGuest, Get-VMGuestDisk, Get-VMQuestion, Get-VMResourceConfiguration, Get-VMStartPolicy, Invoke-VMScript, Move-VM, New-VM, Open-VMConsoleWindow, Remove-VM, Restart-VM, Restart-VMGuest, Set-VM, Set-VMQuestion, Set-VMResourceConfiguration, Set-VMStartPolicy, Start-VM, Stop-VM, Stop-VMGuest, Suspend-VM, Suspend-VMGuest, Test-VsanVMCreation, Unlock-VM"
---

# VMware PowerCLI — VM Operations

Virtual machine lifecycle — create, power, configure, clone, move, remove VMs. Module: VMware.VimAutomation (25 cmdlets).

## Cmdlet Reference (25 cmdlets)

### Copy

#### `Copy-VMGuestFile`

This cmdlet copies files and folders from and to the guest OS of the specified virtual machines using VMware Tools.

**Parameters**: `Source, Destination, GuestToLocal, LocalToGuest, Force, VM, HostCredential, HostUser, HostPassword, GuestCredential, GuestUser, GuestPassword` (+2 more)

### Get

#### `Get-VM`

This cmdlet retrieves the virtual machines on a vCenter Server system.

**Parameters**: `Name, Server, Datastore, VirtualSwitch, Location, RelatedObject, Tag, Id, NoRecursion`

```powershell
Get-VM -Name "web-server-*" | Select-Object Name, PowerState, NumCpu, MemoryGB
```

#### `Get-VMGuest`

This cmdlet retrieves the guest operating systems of the specified virtual machines.

**Parameters**: `VM, Server`

#### `Get-VMGuestDisk`

This cmdlet retrieves storage volumes as seen by the virtual machines' guest operating systems.

**Parameters**: `VM, DiskPath, VMGuest, HardDisk, Server`

#### `Get-VMQuestion`

This cmdlet retrieves the pending questions for the specified virtual machines.

**Parameters**: `VM, QuestionText, QuestionId, Server`

#### `Get-VMResourceConfiguration`

This cmdlet retrieves information about the resource allocation between the selected virtual machines.

**Parameters**: `Server, VM`

#### `Get-VMStartPolicy`

This cmdlet retrieves the start policy of the virtual machines on a vCenter Server system.

**Parameters**: `VMHost, VM, Server`

### Invoke

#### `Invoke-VMScript`

This cmdlet runs a script in the guest OS of each of the specified virtual machines.

**Parameters**: `ScriptText, VM, HostCredential, HostUser, HostPassword, GuestCredential, GuestUser, GuestPassword, ToolsWaitSecs, ScriptType, RunAsync, Server`

```powershell
Invoke-VMScript -VM "linux-vm" -ScriptText "hostname && df -h" -GuestUser "root" -GuestPassword "pass" -ScriptType Bash
```

### Move

#### `Move-VM`

This cmdlet moves virtual machines to another location.

**Parameters**: `AdvancedOption, Destination, Datastore, DiskStorageFormat, VMotionPriority, NetworkAdapter, PortGroup, Network, InventoryLocation, StoragePolicy, DestinationSslThumbprint, RunAsync` (+2 more)

```powershell
Move-VM -VM "my-vm" -Destination (Get-VMHost "esxi02.example.com") -VMotionPriority High
```

### New

#### `New-VM`

This cmdlet creates a new virtual machine.

**Parameters**: `AdvancedOption, VMHost, Version, HardwareVersion, Name, ResourcePool, VApp, Location, Datastore, Template, DiskMB, DiskGB` (+37 more)

```powershell
New-VM -Name "new-vm" -VMHost $host -ResourcePool $pool -DiskGB 100 -MemoryGB 8 -NumCpu 4
```

### Open

#### `Open-VMConsoleWindow`

This cmdlet opens a window to the virtual machine's console.

**Parameters**: `VM, FullScreen, UrlOnly, Server`

### Remove

#### `Remove-VM`

This cmdlet removes the specified virtual machines from the vCenter Server system.

**Parameters**: `DeletePermanently, RunAsync, VM, Server`

### Restart

#### `Restart-VM`

This cmdlet restarts the specified virtual machines.

**Parameters**: `RunAsync, VM, Server`

#### `Restart-VMGuest`

This cmdlet restarts the virtual machine guest operating systems.

**Parameters**: `Guest, VM, Server`

### Set

#### `Set-VM`

This cmdlet modifies the configuration of the virtual machine.

**Parameters**: `VM, Name, Version, HardwareVersion, MemoryMB, MemoryGB, NumCpu, CoresPerSocket, GuestId, AlternateGuestName, Snapshot, OSCustomizationSpec` (+19 more)

#### `Set-VMQuestion`

This cmdlet answers the specified virtual machine question.

**Parameters**: `VMQuestion, Option, DefaultOption`

#### `Set-VMResourceConfiguration`

This cmdlet configures resource allocation between the virtual machines.

**Parameters**: `Configuration, HtCoreSharing, CpuAffinity, CpuAffinityList, CpuReservationMhz, CpuLimitMhz, CpuSharesLevel, NumCpuShares, MemReservationMB, MemReservationGB, MemLimitMB, MemLimitGB` (+6 more)

#### `Set-VMStartPolicy`

This cmdlet modifies the virtual machine start policy.

**Parameters**: `StartPolicy, StartAction, StartOrder, InheritStopActionFromHost, InheritStopDelayFromHost, InheritWaitForHeartbeatFromHost, InheritStartDelayFromHost, UnspecifiedStartOrder, StartDelay, StopAction, StopDelay, WaitForHeartBeat`

### Start

#### `Start-VM`

This cmdlet powers on virtual machines.

**Parameters**: `RunAsync, VM, Server`

### Stop

#### `Stop-VM`

This cmdlet powers off  virtual machines.

**Parameters**: `Kill, RunAsync, VM, Server`

#### `Stop-VMGuest`

This cmdlet shuts down the specified virtual machine guest OS.

**Parameters**: `Guest, VM, Server`

### Suspend

#### `Suspend-VM`

This cmdlet suspends virtual machines.

**Parameters**: `RunAsync, VM, Server`

#### `Suspend-VMGuest`

This cmdlet suspends the specified guest operating systems.

**Parameters**: `Guest, VM, Server`

### Test

#### `Test-VsanVMCreation`

This cmdlet runs a virtual machine creation test on the specified vSAN clusters and returns the test results.

**Parameters**: `Cluster, TimeoutSeconds, UseCache, Server`

### Unlock

#### `Unlock-VM`

This cmdlet unlocks the specified virtual machine.

**Parameters**: `VM, Server, RunAsync`

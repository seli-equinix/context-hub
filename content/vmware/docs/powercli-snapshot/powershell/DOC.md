---
name: powercli-snapshot
description: "VMware PowerCLI 13.3 — VM snapshot operations: create, list, revert, remove. CRITICAL: there is NO Revert-Snapshot cmdlet"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Get-Snapshot,New-Snapshot,Remove-Snapshot,Set-Snapshot"
---

# VMware PowerCLI — VM snapshot operations

## CRITICAL: There Is No Revert-Snapshot Cmdlet

**The most common LLM mistake**: There is NO `Revert-Snapshot` cmdlet.
To revert a VM to a snapshot, use `Set-VM -VM $vm -Snapshot $snapshot`.

```powershell
# WRONG — these cmdlets do not exist:
Revert-Snapshot -Snapshot $snap
Restore-VMSnapshot -Snapshot $snap

# CORRECT — use Set-VM with -Snapshot parameter:
$snap = Get-Snapshot -VM $vm -Name "BeforePatch"
Set-VM -VM $vm -Snapshot $snap -Confirm:$false
```

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Get-Snapshot` | This cmdlet retrieves the virtual machine snapshots available on a vCenter Server system. |
| `New-Snapshot` | This cmdlet creates a new snapshot of a virtual machine. |
| `Remove-Snapshot` | This cmdlet removes the specified virtual machine snapshots. |
| `Set-Snapshot` | This cmdlet modifies the specified virtual machine snapshot. |

---

### Get-Snapshot

This cmdlet retrieves the virtual machine snapshots available on a vCenter Server system.

This cmdlet returns information about the snapshots that correspond to the filter criteria provided by the Name and VM parameters. The disk size of the snapshots is retrieved only if you have the "Datastore/Browse datastore" privilege to the datastore where the shapshot is located. Otherwise, the following message is displayed: "Unable to populate snapshot size due to unsufficient permissions."

**Returns**: `Snapshot`

```
Get-Snapshot
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    -VM <VirtualMachine[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the snapshots you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the strin... |
| `-Name` | `String[]` | No | Specifies the names of the snapshots you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machines whose snapshots you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scri... |

---

### New-Snapshot

This cmdlet creates a new snapshot of a virtual machine.

This cmdlet creates a new snapshot of a virtual machine with the provided inputs.

**Returns**: `Snapshot`

```
New-Snapshot
    [-Description <String>]
    [-Memory]
    -Name <String>
    [-Quiesce]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VM <VirtualMachine>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Description` | `String` | No | Provide a description of the new snapshot. |
| `-Memory` | `SwitchParameter` | No | If the value is $true and if the virtual machine is powered on, the virtual machine's memory state is preserved with the snapshot. |
| `-Name` | `String` | Yes | Specifies a name for the new snapshot. |
| `-Quiesce` | `SwitchParameter` | No | If the value is $true and the virtual machine is powered on, VMware Tools are used to quiesce the file system of the virtual machine. This assures that a disk snapshot represents a consistent state... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VM` | `VirtualMachine` | Yes | Specifies the virtual machine you want to snapshot. Passing multiple values to this parameter is obsolete. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-Snapshot

This cmdlet removes the specified virtual machine snapshots.

This cmdlet removes the specified virtual machine snapshots. If the value of the RemoveChildren parameter is $true, the cmdlet removes the child snapshots as well.

**Returns**: `None`

```
Remove-Snapshot
    [-RemoveChildren]
    [-RunAsync]
    -Snapshot <Snapshot[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-RemoveChildren` | `SwitchParameter` | No | Indicates that you want to remove the children of the specified snapshots as well. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Snapshot` | `Snapshot[]` | Yes | Specifies the snapshots you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Snapshot

This cmdlet modifies the specified virtual machine snapshot.

This cmdlet modifies the name and the description of the specified virtual machine snapshot.

**Returns**: `Snapshot`

```
Set-Snapshot
    [-Description <String>]
    [-Name <String>]
    -Snapshot <Snapshot[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Description` | `String` | No | Provides a new description for the snapshot. |
| `-Name` | `String` | No | Specifies a new name for the snapshot. |
| `-Snapshot` | `Snapshot[]` | Yes | Specifies the snapshot whose properties you want to change. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

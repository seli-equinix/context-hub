# VMware PowerCLI Snapshot Operations -- Complete Reference

This reference covers every snapshot-related operation in VMware PowerCLI with exact parameter signatures, return types, and correct usage patterns. This is the most frequently mis-generated area of PowerCLI code.

## The Four Snapshot Cmdlets

There are exactly FOUR cmdlets that directly operate on snapshots:

| Cmdlet | Module | Action | Returns |
|--------|--------|--------|---------|
| `Get-Snapshot` | VMware.VimAutomation.Core | Retrieve snapshots | `Snapshot[]` |
| `New-Snapshot` | VMware.VimAutomation.Core | Create snapshot | `Snapshot` |
| `Remove-Snapshot` | VMware.VimAutomation.Core | Delete snapshot | None |
| `Set-Snapshot` | VMware.VimAutomation.Core | Rename/re-describe | `Snapshot[]` |

## There Is NO Revert-Snapshot Cmdlet

To revert a VM to a snapshot, use `Set-VM` with the `-Snapshot` parameter:

```powershell
Set-VM -VM <VirtualMachine> -Snapshot <Snapshot> [-Confirm:$false]
```

The following cmdlets DO NOT EXIST in any version of PowerCLI:
- `Revert-Snapshot`
- `Restore-Snapshot`
- `Restore-VMSnapshot`
- `Revert-VMSnapshot`
- `Apply-Snapshot`

## Snapshot Object Properties

The `VMware.VimAutomation.ViCore.Types.V1.VM.Snapshot` object has these properties:

| Property | Type | Description |
|----------|------|-------------|
| `Name` | String | Snapshot name |
| `Id` | String | Unique identifier |
| `Description` | String | User-provided description |
| `Created` | DateTime | Creation timestamp |
| `SizeGB` | Decimal | Disk space consumed (requires Datastore/Browse privilege) |
| `SizeMB` | Decimal | Disk space in MB |
| `PowerState` | VirtualMachinePowerState | VM power state when snapshot was taken |
| `VM` | VirtualMachine | Parent VM object |
| `VMId` | String | Parent VM ID |
| `Parent` | Snapshot | Parent snapshot (null for root) |
| `ParentSnapshotId` | String | Parent snapshot ID |
| `Children` | Snapshot[] | Child snapshots |
| `IsCurrent` | Boolean | Whether this is the active snapshot |
| `Quiesced` | Boolean | Whether filesystem was quiesced |
| `IsReplaySupported` | Boolean | Replay support |
| `ExtensionData` | Object | Raw vSphere API object |

## Get-Snapshot -- Full Signature

```
Get-Snapshot [-VM] <VirtualMachine[]> [[-Name] <String[]>]
    [-Id <String[]>] [-Server <VIServer[]>]
    [<CommonParameters>]
```

### Parameters

| Parameter | Type | Req | Pos | Pipeline | Wildcards | Description |
|-----------|------|-----|-----|----------|-----------|-------------|
| `-VM` | VirtualMachine[] | Yes | 0 | ByValue | Yes | Source VMs |
| `-Name` | String[] | No | 1 | No | Yes | Filter by name |
| `-Id` | String[] | No | Named | No | Yes | Filter by ID |
| `-Server` | VIServer[] | No | Named | No | Yes | Target server |

### Usage Patterns

```powershell
# All snapshots for one VM:
Get-Snapshot -VM "WebServer01"

# By name (exact):
Get-Snapshot -VM "WebServer01" -Name "BeforePatch"

# By name (wildcard):
Get-Snapshot -VM "WebServer01" -Name "Before*"

# Pipeline from Get-VM:
Get-VM "WebServer01" | Get-Snapshot

# All snapshots across ALL VMs (audit report):
Get-VM | Get-Snapshot | Select-Object VM, Name, Created, SizeGB, @{
    N='AgeDays'; E={ [math]::Round(((Get-Date) - $_.Created).TotalDays, 1) }
} | Sort-Object AgeDays -Descending

# Find current/active snapshot:
Get-Snapshot -VM "WebServer01" | Where-Object { $_.IsCurrent }

# Navigate snapshot tree:
$root = Get-Snapshot -VM "WebServer01" | Where-Object { $null -eq $_.Parent }
$root.Children  # child snapshots
```

## New-Snapshot -- Full Signature

```
New-Snapshot [-VM] <VirtualMachine> [-Name] <String>
    [-Description <String>] [-Memory] [-Quiesce]
    [-RunAsync] [-Server <VIServer[]>]
    [-Confirm] [-WhatIf]
    [<CommonParameters>]
```

### Parameters

| Parameter | Type | Req | Pos | Pipeline | Description |
|-----------|------|-----|-----|----------|-------------|
| `-VM` | VirtualMachine | Yes | 0 | ByValue | Single VM (passing multiple is obsolete) |
| `-Name` | String | Yes | 1 | No | Snapshot name |
| `-Description` | String | No | Named | No | Description text |
| `-Memory` | Switch | No | Named | No | Include memory state (powered-on VMs only) |
| `-Quiesce` | Switch | No | Named | No | Quiesce filesystem via VMware Tools (powered-on only) |
| `-RunAsync` | Switch | No | Named | No | Return Task immediately |

### Parameter Behavior Notes

- `-Memory`: Only meaningful when VM is PoweredOn. If VM is off, parameter is silently ignored.
- `-Quiesce`: Requires VMware Tools running in guest. If tools unavailable, parameter is silently ignored.
- `-Memory` + `-Quiesce`: Both can be specified together. Memory snapshot is taken first, then filesystem quiesce.
- `-RunAsync`: Returns a `Task` object instead of waiting. Use `Wait-Task` to wait for completion.

### Usage Patterns

```powershell
# Minimal:
New-Snapshot -VM "WebServer01" -Name "BeforePatch"

# With description:
New-Snapshot -VM "WebServer01" -Name "Pre-Maintenance" `
    -Description "Created before applying KB5001234 security patch"

# Memory snapshot (captures running state):
New-Snapshot -VM "WebServer01" -Name "MemoryState" -Memory

# Quiesced (consistent disk state):
New-Snapshot -VM "WebServer01" -Name "Consistent" -Quiesce

# Full state capture:
New-Snapshot -VM "WebServer01" -Name "FullCapture" -Memory -Quiesce

# Async with wait:
$task = New-Snapshot -VM "WebServer01" -Name "AsyncSnap" -RunAsync
$result = Wait-Task $task  # $result is the Snapshot object

# Bulk snapshot (correct pattern -- ForEach, not direct pipeline):
Get-VM -Name "Web*" | ForEach-Object {
    New-Snapshot -VM $_ -Name "BatchBackup-$(Get-Date -Format 'yyyyMMdd')" `
        -Description "Automated batch backup" -Quiesce
}
```

## Remove-Snapshot -- Full Signature

```
Remove-Snapshot [-Snapshot] <Snapshot[]>
    [-RemoveChildren]
    [-RunAsync]
    [-Confirm] [-WhatIf]
    [<CommonParameters>]
```

### Parameters

| Parameter | Type | Req | Pos | Pipeline | Description |
|-----------|------|-----|-----|----------|-------------|
| `-Snapshot` | Snapshot[] | Yes | 0 | ByValue | Snapshots to remove |
| `-RemoveChildren` | Switch | No | Named | No | Also delete child snapshots |
| `-RunAsync` | Switch | No | Named | No | Return Task immediately |

### Usage Patterns

```powershell
# Remove single snapshot:
Get-Snapshot -VM "WebServer01" -Name "OldSnap" | Remove-Snapshot -Confirm:$false

# Remove with children:
$snap = Get-Snapshot -VM "WebServer01" -Name "ParentSnap"
Remove-Snapshot -Snapshot $snap -RemoveChildren -Confirm:$false

# Remove ALL snapshots for a VM:
Get-VM "WebServer01" | Get-Snapshot | Remove-Snapshot -Confirm:$false

# Remove all snapshots older than N days:
$cutoff = (Get-Date).AddDays(-14)
Get-VM | Get-Snapshot | Where-Object { $_.Created -lt $cutoff } |
    Remove-Snapshot -Confirm:$false

# Async removal of large snapshot:
$task = Get-Snapshot -VM "WebServer01" -Name "LargeSnap" |
    Remove-Snapshot -RunAsync
Wait-Task $task
```

### Important Behavior Notes

- Removing a snapshot consolidates the delta disk into the parent. This is I/O intensive.
- If the VM is powered on during removal, there may be a brief performance impact.
- Without `-RemoveChildren`, child snapshots are reparented to the deleted snapshot's parent.
- Removing the last snapshot in a chain still requires disk consolidation.

## Set-Snapshot -- Full Signature

```
Set-Snapshot [-Snapshot] <Snapshot[]>
    [-Name <String>] [-Description <String>]
    [-Confirm] [-WhatIf]
    [<CommonParameters>]
```

### Parameters

| Parameter | Type | Req | Pos | Pipeline | Description |
|-----------|------|-----|-----|----------|-------------|
| `-Snapshot` | Snapshot[] | Yes | 0 | ByValue | Snapshot(s) to modify |
| `-Name` | String | No | Named | No | New name |
| `-Description` | String | No | Named | No | New description |

Set-Snapshot ONLY changes name and description. It does NOT revert, remove, or modify snapshot contents.

```powershell
# Rename:
Get-Snapshot -VM "WebServer01" -Name "OldName" |
    Set-Snapshot -Name "NewName" -Description "Updated after review"

# Bulk update descriptions:
Get-VM | Get-Snapshot -Name "InitialState" |
    Set-Snapshot -Description "OS installation baseline snapshot"
```

## Revert to Snapshot (via Set-VM) -- Full Reference

```
Set-VM [-VM] <VirtualMachine[]> -Snapshot <Snapshot>
    [-Name <String>] [-OSCustomizationSpec <OSCustomizationSpec>]
    [-RunAsync] [-Server <VIServer[]>]
    [-Confirm] [-WhatIf]
    [<CommonParameters>]
```

The `-Snapshot` parameter on Set-VM triggers the revert parameter set. The VM's disk, memory (if captured), and configuration are restored to the snapshot state.

### Usage Patterns

```powershell
# Basic revert:
$snap = Get-Snapshot -VM "WebServer01" -Name "KnownGood"
Set-VM -VM "WebServer01" -Snapshot $snap -Confirm:$false

# Revert with pipeline:
Get-Snapshot -VM "WebServer01" -Name "KnownGood" |
    ForEach-Object { Set-VM -VM $_.VM -Snapshot $_ -Confirm:$false }

# Revert and power on:
$snap = Get-Snapshot -VM "WebServer01" -Name "KnownGood"
Set-VM -VM "WebServer01" -Snapshot $snap -Confirm:$false
Start-VM -VM "WebServer01"

# Revert multiple VMs to their "Baseline" snapshots:
Get-VM -Name "Web*" | ForEach-Object {
    $snap = Get-Snapshot -VM $_ -Name "Baseline"
    if ($snap) {
        Set-VM -VM $_ -Snapshot $snap -Confirm:$false
        Write-Host "Reverted $($_.Name) to Baseline"
    } else {
        Write-Warning "$($_.Name) has no 'Baseline' snapshot"
    }
}
```

### Behavior Notes

- If the snapshot includes memory, the VM resumes to that memory state (powered on).
- If the snapshot does not include memory, the VM remains in its current power state.
- You cannot revert to a snapshot while a snapshot operation is already in progress.
- Reverting discards all changes made after the snapshot was taken.

## Complete Lifecycle Example

```powershell
# === SNAPSHOT LIFECYCLE FOR MAINTENANCE WINDOW ===

# 1. Connect to vCenter
Connect-VIServer -Server "vcenter.corp.local" -User "admin@vsphere.local" -Password 'Pass!'

# 2. Get target VMs
$vms = Get-VM -Name "WebServer*" | Where-Object { $_.PowerState -eq 'PoweredOn' }

# 3. Create pre-maintenance snapshots
$snapshots = @{}
foreach ($vm in $vms) {
    $snap = New-Snapshot -VM $vm -Name "Pre-Maint-$(Get-Date -Format 'yyyyMMdd-HHmm')" `
        -Description "Before monthly patching" -Memory -Quiesce
    $snapshots[$vm.Name] = $snap
    Write-Host "Created snapshot for $($vm.Name): $($snap.Name)"
}

# 4. Apply maintenance (example: run Windows Update)
foreach ($vm in $vms) {
    $secPass = ConvertTo-SecureString "GuestP@ss" -AsPlainText -Force
    Invoke-VMScript -VM $vm -ScriptText "Install-WindowsUpdate -AcceptAll" `
        -GuestUser "Administrator" -GuestPassword $secPass -ScriptType PowerShell
}

# 5. Validate -- if any VM has issues, revert it:
$failedVM = Get-VM "WebServer03"
if ($failedVM.Guest.State -ne 'Running') {
    Write-Warning "WebServer03 failed -- reverting to snapshot"
    Set-VM -VM $failedVM -Snapshot $snapshots["WebServer03"] -Confirm:$false
    Start-VM -VM $failedVM
}

# 6. Clean up successful snapshots (keep failed ones for investigation):
foreach ($vm in $vms) {
    if ($vm.Name -ne "WebServer03") {  # skip the failed one
        Remove-Snapshot -Snapshot $snapshots[$vm.Name] -Confirm:$false
        Write-Host "Cleaned up snapshot for $($vm.Name)"
    }
}

# 7. Disconnect
Disconnect-VIServer -Confirm:$false
```

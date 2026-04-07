---
name: powercli-core
description: "VMware PowerCLI (VCF PowerCLI) vSphere management cmdlets -- VM lifecycle, snapshots, hosts, datastores, clusters, templates, networking, and guest operations"
metadata:
  languages: "powershell"
  versions: "13.3,9.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vcf,vsphere,vcenter,esxi,vm,snapshot,datastore,cluster,template,network-adapter,hard-disk,guest,invoke-vmscript,virtual-machine"
---

# VMware PowerCLI -- VMware.VimAutomation.Core Cmdlet Reference

You are a **VMware PowerCLI expert**. This is the authoritative cmdlet reference for the `VMware.VimAutomation.Core` module (vSphere management). Every parameter name, type, and behavior documented here comes from the official PowerCLI 13.3 / VCF PowerCLI 9.0 help system.

> Ground truth: VMware PowerCLI built-in help (`Get-Help <cmdlet> -Full`) and Broadcom Developer Portal.

## CRITICAL: There Is No Revert-Snapshot Cmdlet

**The single most common LLM mistake with PowerCLI snapshots**: There is NO `Revert-Snapshot` cmdlet. To revert a VM to a snapshot, use `Set-VM -VM $vm -Snapshot $snapshot`. This is confirmed by official VMware documentation.

```powershell
# WRONG - this cmdlet does not exist:
Revert-Snapshot -Snapshot $snap
Restore-VMSnapshot -Snapshot $snap

# CORRECT - use Set-VM with -Snapshot parameter:
$snap = Get-Snapshot -VM $vm -Name "BeforePatch"
Set-VM -VM $vm -Snapshot $snap -Confirm:$false
```

## Installation and Setup

### Install PowerCLI

```powershell
# Legacy module name (deprecated but still works):
Install-Module -Name VMware.PowerCLI -Scope CurrentUser -AllowClobber

# New module name (VCF PowerCLI 9.0+, 2025+):
Install-Module -Name VCF.PowerCLI -Scope CurrentUser -AllowClobber -SkipPublisherCheck

# If upgrading from VMware.PowerCLI to VCF.PowerCLI:
Install-Module -Name VCF.PowerCLI -AllowClobber -SkipPublisherCheck
```

**Version history**: VMware PowerCLI 13.3 was the last release under the VMware.PowerCLI name. VCF PowerCLI 9.0 (June 2025) is the successor after the Broadcom acquisition. All cmdlets, modules, and scripts are backward-compatible.

### Certificate and CEIP Configuration

```powershell
# Suppress certificate warnings for lab/internal environments:
Set-PowerCLIConfiguration -InvalidCertificateAction Ignore -Confirm:$false

# Disable telemetry:
Set-PowerCLIConfiguration -Scope User -ParticipateInCEIP $false -Confirm:$false

# Set multiple default server mode (for linked vCenters):
Set-PowerCLIConfiguration -DefaultVIServerMode Multiple -Confirm:$false
```

---

## Connection Management

### Connect-VIServer

Establishes a connection to a vCenter Server or ESXi host. Returns a `VIServer` object stored in `$global:DefaultVIServer` (single mode) or `$global:DefaultVIServers` (multiple mode).

```
Connect-VIServer [-Server] <String[]>
    [-User <String>] [-Password <String>]
    [-Credential <PSCredential>]
    [-Port <Int32>] [-Protocol {http | https}]
    [-Session <String>]
    [-SaveCredentials] [-Force] [-NotDefault] [-AllLinked]
    [-SamlSecurityContext <SamlSecurityContext>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | String[] | Yes (pos 0) | IP or DNS of vCenter/ESXi. IPv6: `[fe80::250:56ff:feb0:74bd%4]` |
| `-User` | String | No | Username. Alias: `-Username` |
| `-Password` | String | No | Password. Enclose in single quotes if special chars |
| `-Credential` | PSCredential | No | Credential object (overrides -User/-Password) |
| `-Port` | Int32 | No | Port (default: 443) |
| `-Protocol` | String | No | `http` or `https` |
| `-Session` | String | No | Re-establish existing session by ID |
| `-SaveCredentials` | Switch | No | Save to local credential store (not supported on PS Core) |
| `-Force` | Switch | No | Suppress UI prompts (cert warnings, multi-server) |
| `-NotDefault` | Switch | No | Do not add to `$DefaultVIServers` |
| `-AllLinked` | Switch | No | Connect to all linked vCenters in federation |

**Returns**: `VIServer` object

```powershell
# Basic connection:
Connect-VIServer -Server vcenter.corp.local -User admin@vsphere.local -Password 'P@ssw0rd!'

# With credential object:
$cred = Get-Credential
Connect-VIServer -Server 10.0.0.100 -Credential $cred

# Linked mode (all federated vCenters):
Connect-VIServer -Server vcenter1.corp.local -AllLinked

# Re-establish session:
Connect-VIServer -Server vcenter.corp.local -Session $savedSessionId
```

**Common mistakes**:
- Forgetting `-Force` in scripts, causing interactive prompts to hang
- Using `-User` and `-Credential` together (`-Credential` wins, `-User` is ignored)
- Not handling `InvalidCertificateAction` before connecting (causes cert popup)

### Disconnect-VIServer

```
Disconnect-VIServer [[-Server] <VIServer[]>] [-Force] [-Confirm] [-WhatIf]
```

**Returns**: None

```powershell
# Disconnect specific server:
Disconnect-VIServer -Server $viServer -Confirm:$false

# Disconnect ALL connections:
Disconnect-VIServer -Server * -Force -Confirm:$false

# Disconnect all default servers:
Disconnect-VIServer -Server $global:DefaultVIServers -Force -Confirm:$false
```

**Critical note**: Closing the PowerShell process does NOT release server-side resources. Always call `Disconnect-VIServer` explicitly.

---

## Virtual Machine Lifecycle

### Get-VM

Retrieves virtual machines. Returns `VirtualMachine` objects.

```
Get-VM [[-Name] <String[]>]
    [-Location <VIContainer[]>] [-Datastore <StorageResource[]>]
    [-Tag <Tag[]>] [-VirtualSwitch <VirtualSwitchBase[]>]
    [-NoRecursion] [-Server <VIServer[]>]

Get-VM -Id <String[]> [-Server <VIServer[]>]

Get-VM -RelatedObject <VmRelatedObjectBase[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | String[] | No (pos 0) | VM names. Supports wildcards (`*`) |
| `-Id` | String[] | Yes (in Id set) | VM IDs (exact match from list) |
| `-Location` | VIContainer[] | No | Search in: ResourcePool, VApp, VMHost, Folder, Cluster, Datacenter |
| `-Datastore` | StorageResource[] | No | Filter by datastore or datastore cluster |
| `-Tag` | Tag[] | No | Filter by vSphere tags |
| `-VirtualSwitch` | VirtualSwitchBase[] | No | Filter by connected switch. Alias: `-DistributedSwitch` |
| `-NoRecursion` | Switch | No | Do not recurse into child containers |
| `-Server` | VIServer[] | No | Target server(s). Default: `$DefaultVIServers` |

**Returns**: Zero or more `VirtualMachine` objects

**Key properties of VirtualMachine object**:
- `Name`, `Id`, `PowerState` (PoweredOn/PoweredOff/Suspended)
- `NumCpu`, `CoresPerSocket`, `MemoryGB`, `MemoryMB`
- `VMHost`, `Folder`, `FolderId`, `ResourcePool`, `ResourcePoolId`
- `GuestId`, `Guest` (VMGuest object with IP, hostname, OS info)
- `HardwareVersion`, `Version`, `Notes`
- `ProvisionedSpaceGB`, `UsedSpaceGB`

```powershell
# Get all VMs:
Get-VM

# Wildcard name:
Get-VM -Name "Web*"

# In specific datacenter:
Get-VM -Location (Get-Datacenter -Name "Production")

# On specific datastore:
Get-VM -Datastore (Get-Datastore -Name "SAN_LUN01")

# On specific host:
Get-VM -Location (Get-VMHost -Name "esxi01.corp.local")
```

**Common mistakes**:
- Using `-Name` with exact match expectation (it supports wildcards by default)
- Forgetting that `FolderId` is `$null` when VM is in a vApp
- Treating `Guest.IPAddress` as a single string (it is a string array for multi-NIC VMs)

### New-VM

Creates a new virtual machine. Multiple parameter sets for different creation methods.

```
# From scratch:
New-VM -Name <String> [[-VMHost] <VMHost>]
    [-NumCpu <Int32>] [-CoresPerSocket <Int32>]
    [-MemoryGB <Decimal>] [-MemoryMB <Int64>]
    [-DiskGB <Decimal[]>] [-DiskMB <Int64[]>] [-DiskPath <String[]>]
    [-DiskStorageFormat {Thin | Thick | EagerZeroedThick}]
    [-GuestId <String>] [-AlternateGuestName <String>]
    [-NetworkName <String[]>] [-Portgroup <VirtualPortGroupBase[]>]
    [-CD] [-Floppy]
    [-Datastore <StorageResource>] [-ResourcePool <VIContainer>]
    [-Location <Folder>] [-VApp <VApp>]
    [-HardwareVersion <String>] [-Version <VMVersion>]
    [-Notes <String>] [-RunAsync]
    [-StoragePolicy <StoragePolicy>] [-KeyProvider <KeyProvider>]
    [-CpuHotAddEnabled <Boolean>] [-CpuHotRemoveEnabled <Boolean>]
    [-MemoryHotAddEnabled <Boolean>]

# Clone from existing VM:
New-VM -VM <VirtualMachine[]> [[-VMHost] <VMHost>]
    [-Name <String>] [-LinkedClone] [-ReferenceSnapshot <Snapshot>]
    [-Datastore <StorageResource>] [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-OSCustomizationSpec <OSCustomizationSpec>]
    [-Location <Folder>] [-ResourcePool <VIContainer>] [-RunAsync]

# From template:
New-VM -Template <Template> [[-VMHost] <VMHost>]
    -Name <String>
    [-Datastore <StorageResource>] [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-OSCustomizationSpec <OSCustomizationSpec>]
    [-NetworkName <String[]>] [-Portgroup <VirtualPortGroupBase[]>]
    [-Location <Folder>] [-ResourcePool <VIContainer>] [-RunAsync]

# From VMX file:
New-VM -VMFilePath <String> [[-VMHost] <VMHost>]
    [-Name <String>] [-Location <Folder>] [-ResourcePool <VIContainer>] [-RunAsync]

# From Content Library:
New-VM -ContentLibraryItem <ContentLibraryItem> [[-VMHost] <VMHost>]
    [-Name <String>] [-NumCpu <Int32>] [-MemoryGB <Decimal>] [-DiskGB <Decimal[]>]
    [-Datastore <StorageResource>] [-OSCustomizationSpec <OSCustomizationSpec>]
    [-OvfConfiguration <Hashtable>]
    [-Location <Folder>] [-ResourcePool <VIContainer>] [-RunAsync]
```

**Returns**: `VirtualMachine` object (or `Task` with `-RunAsync`)

**You must specify at least one of**: `-ResourcePool`, `-VMHost`, or `-VApp`.

```powershell
# Create from scratch:
New-VM -Name "WebServer01" -VMHost $vmhost `
    -NumCpu 4 -MemoryGB 8 -DiskGB 100 `
    -GuestId "windows2019srv_64Guest" `
    -NetworkName "VM Network" `
    -Datastore "SAN_LUN01" `
    -DiskStorageFormat Thin

# Clone VM:
New-VM -Name "WebServer02" -VM (Get-VM "WebServer01") `
    -VMHost $vmhost -Datastore "SAN_LUN02" `
    -DiskStorageFormat Thin

# Linked clone (requires a snapshot):
$snap = Get-Snapshot -VM "WebServer01" -Name "Base"
New-VM -Name "WebServer02-LC" -VM (Get-VM "WebServer01") `
    -LinkedClone -ReferenceSnapshot $snap `
    -VMHost $vmhost -Datastore "SAN_LUN02"

# From template with customization:
$spec = Get-OSCustomizationSpec -Name "WindowsSpec"
$template = Get-Template -Name "Win2019-Base"
New-VM -Name "WebServer03" -Template $template `
    -VMHost $vmhost -Datastore "SAN_LUN01" `
    -OSCustomizationSpec $spec
```

**Common mistakes**:
- Not specifying `-VMHost`, `-ResourcePool`, or `-VApp` (at least one required)
- Using `-DiskMB` (obsolete, use `-DiskGB`)
- Forgetting `-ReferenceSnapshot` for linked clones (mandatory)
- Using `-GuestId` values that do not match the ESXi version

### Set-VM

Modifies VM configuration. Also used for **snapshot revert** and **VM-to-template conversion**.

```
# Modify configuration:
Set-VM [-VM] <VirtualMachine[]>
    [-Name <String>] [-Notes <String>]
    [-NumCpu <Int32>] [-CoresPerSocket <Int32>]
    [-MemoryGB <Decimal>] [-MemoryMB <Int64>]
    [-GuestId <String>] [-AlternateGuestName <String>]
    [-HardwareVersion <String>] [-Version <VMVersion>]
    [-BootDelayMillisecond <Int64>]
    [-OSCustomizationSpec <OSCustomizationSpec>]
    [-CpuHotAddEnabled <Boolean>] [-CpuHotRemoveEnabled <Boolean>]
    [-MemoryHotAddEnabled <Boolean>]
    [-SEVEnabled <Boolean>] [-MigrationEncryption {Opportunistic|Disabled|Required}]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# REVERT TO SNAPSHOT (critical parameter set):
Set-VM [-VM] <VirtualMachine[]> -Snapshot <Snapshot>
    [-Name <String>] [-OSCustomizationSpec <OSCustomizationSpec>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Convert to template:
Set-VM [-VM] <VirtualMachine[]> -ToTemplate [-Name <String>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Promote linked clone disks:
Set-VM [-VM] <VirtualMachine[]> -PromoteDisks
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Encryption:
Set-VM [-VM] <VirtualMachine[]> -DisableEncryption
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]

# Storage policy:
Set-VM [-VM] <VirtualMachine[]>
    [-StoragePolicy <StoragePolicy>] [-SkipHardDisks]
    [-KeyProvider <KeyProvider>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VM` | VirtualMachine[] | Yes (pos 0) | Target VM(s). Accepts pipeline |
| `-Snapshot` | Snapshot | No | **Revert VM to this snapshot state** |
| `-ToTemplate` | Switch | No | Convert VM to template |
| `-PromoteDisks` | Switch | No | Promote linked clone to full clone |
| `-Name` | String | No | New name for VM |
| `-Notes` | String | No | Description. Alias: `-Description` |
| `-NumCpu` | Int32 | No | Number of virtual CPUs |
| `-MemoryGB` | Decimal | No | Memory in GB |
| `-GuestId` | String | No | Guest OS identifier |
| `-HardwareVersion` | String | No | e.g., `vmx-21`. Cannot downgrade |
| `-BootDelayMillisecond` | Int64 | No | Boot delay in ms |
| `-DisableEncryption` | Switch | No | Decrypt VM |
| `-StoragePolicy` | StoragePolicy | No | Attach storage policy |
| `-SkipHardDisks` | Switch | No | Apply policy to vmhome only |
| `-RunAsync` | Switch | No | Return Task immediately |

**Returns**: Modified `VirtualMachine` object(s) or `Template` object (with `-ToTemplate`)

```powershell
# REVERT TO SNAPSHOT (the correct way):
$snap = Get-Snapshot -VM "WebServer01" -Name "BeforePatch"
Set-VM -VM "WebServer01" -Snapshot $snap -Confirm:$false

# Modify CPU/memory:
Set-VM -VM "WebServer01" -NumCpu 4 -MemoryGB 16 -Confirm:$false

# Rename VM:
Set-VM -VM "OldName" -Name "NewName" -Confirm:$false

# Convert VM to template:
Set-VM -VM "GoldImage" -ToTemplate -Name "GoldImage-Template" -Confirm:$false

# Upgrade hardware version:
Set-VM -VM "WebServer01" -HardwareVersion "vmx-21" -Confirm:$false
```

### Remove-VM

```
Remove-VM [-VM] <VirtualMachine[]> [-DeletePermanently] [-RunAsync]
    [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VM` | VirtualMachine[] | Yes (pos 0) | VMs to remove |
| `-DeletePermanently` | Switch | No | Delete from disk too (not just inventory). Alias: `-DeleteFromDisk` |

**Returns**: None

```powershell
# Remove from inventory only:
Remove-VM -VM "TestVM" -Confirm:$false

# Delete from disk permanently:
Remove-VM -VM "TestVM" -DeletePermanently -Confirm:$false
```

**Common mistake**: Forgetting `-DeletePermanently` and thinking the VM files are gone (they remain on the datastore).

### Start-VM / Stop-VM / Restart-VM / Suspend-VM

All four share a similar signature:

```
Start-VM [-VM] <VirtualMachine[]> [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
Stop-VM [-VM] <VirtualMachine[]> [-Kill] [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
Restart-VM [-VM] <VirtualMachine[]> [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
Suspend-VM [-VM] <VirtualMachine[]> [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**Returns**: `VirtualMachine` objects in their new power state

| Cmdlet | Action | Special Parameters |
|--------|--------|-------------------|
| `Start-VM` | Power on | None |
| `Stop-VM` | Power off (hard) | `-Kill` forces process termination on ESXi (requires direct ESXi 4.1+ connection) |
| `Restart-VM` | Guest OS restart (requires VMware Tools) | None |
| `Suspend-VM` | Suspend (freeze state to disk) | None |

```powershell
# Start VM:
Start-VM -VM "WebServer01" -Confirm:$false

# Graceful shutdown (Stop-VM sends ACPI shutdown):
Stop-VM -VM "WebServer01" -Confirm:$false

# Force kill unresponsive VM:
Stop-VM -VM "WebServer01" -Kill -Confirm:$false

# Restart:
Restart-VM -VM "WebServer01" -Confirm:$false

# Bulk start:
Get-VM -Location "DevPool" | Where-Object { $_.PowerState -eq 'PoweredOff' } | Start-VM
```

**Common mistakes**:
- `Stop-VM` is a hard power-off, NOT a graceful shutdown. For graceful: use `Shutdown-VMGuest`
- `Restart-VM` requires VMware Tools running in the guest. If tools are not installed, it fails

### Shutdown-VMGuest / Restart-VMGuest (Guest OS Operations)

These are NOT the same as `Stop-VM`/`Restart-VM`:

```powershell
# Graceful OS shutdown (requires VMware Tools):
Shutdown-VMGuest -VM "WebServer01" -Confirm:$false

# Graceful OS restart (requires VMware Tools):
Restart-VMGuest -VM "WebServer01" -Confirm:$false
```

---

## Snapshot Management (CRITICAL for EVA)

### Get-Snapshot

```
Get-Snapshot [-VM] <VirtualMachine[]> [[-Name] <String[]>]
    [-Id <String[]>] [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VM` | VirtualMachine[] | Yes (pos 0) | Source VM(s). Accepts pipeline |
| `-Name` | String[] | No (pos 1) | Snapshot name(s). Supports wildcards |
| `-Id` | String[] | No | Snapshot ID(s) |

**Returns**: Zero or more `Snapshot` objects

**Key properties of Snapshot object**:
- `Name`, `Id`, `Description`
- `Created` (DateTime), `SizeGB`, `SizeMB`
- `PowerState` (state when snapshot was taken)
- `VM` (parent VirtualMachine)
- `Parent` (parent Snapshot, for tree navigation)
- `Children` (child Snapshots)
- `IsCurrent` (boolean)
- `Quiesced` (boolean)

```powershell
# Get all snapshots for a VM:
Get-VM "WebServer01" | Get-Snapshot

# Get specific named snapshot:
Get-Snapshot -VM "WebServer01" -Name "BeforePatch"

# Get all snapshots across all VMs (audit):
Get-VM | Get-Snapshot | Select-Object VM, Name, Created, SizeGB

# Find old snapshots (older than 7 days):
Get-VM | Get-Snapshot | Where-Object { $_.Created -lt (Get-Date).AddDays(-7) }
```

### New-Snapshot

```
New-Snapshot [-VM] <VirtualMachine> [-Name] <String>
    [-Description <String>] [-Memory] [-Quiesce]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VM` | VirtualMachine | Yes (pos 0) | Single VM to snapshot |
| `-Name` | String | Yes (pos 1) | Snapshot name |
| `-Description` | String | No | Snapshot description |
| `-Memory` | Switch | No | Include VM memory state (only if VM is powered on) |
| `-Quiesce` | Switch | No | Quiesce guest filesystem via VMware Tools (powered on only) |
| `-RunAsync` | Switch | No | Return Task object immediately |

**Returns**: `Snapshot` object (or `Task` with `-RunAsync`)

```powershell
# Basic snapshot:
New-Snapshot -VM "WebServer01" -Name "BeforePatch" -Description "Pre-patch baseline"

# With memory (for powered-on VMs):
New-Snapshot -VM "WebServer01" -Name "MemorySnapshot" -Memory

# Quiesced (consistent filesystem state):
New-Snapshot -VM "WebServer01" -Name "ConsistentSnap" -Quiesce

# Both memory and quiesce:
New-Snapshot -VM "WebServer01" -Name "FullState" -Memory -Quiesce

# Async (returns immediately):
$task = New-Snapshot -VM "WebServer01" -Name "Async" -RunAsync
Wait-Task $task
```

**Common mistakes**:
- `-Memory` and `-Quiesce` are IGNORED if the VM is powered off (no error thrown)
- `-Quiesce` requires VMware Tools running inside the guest
- Passing multiple VMs is obsolete; use pipeline instead: `Get-VM "Web*" | ForEach-Object { New-Snapshot -VM $_ -Name "Batch" }`

### Remove-Snapshot

```
Remove-Snapshot [-Snapshot] <Snapshot[]> [-RemoveChildren]
    [-RunAsync] [-Confirm] [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Snapshot` | Snapshot[] | Yes (pos 0) | Snapshot(s) to remove. Accepts pipeline |
| `-RemoveChildren` | Switch | No | Also remove all child snapshots |
| `-RunAsync` | Switch | No | Return Task immediately |

**Returns**: None

```powershell
# Remove specific snapshot:
Get-Snapshot -VM "WebServer01" -Name "OldSnap" | Remove-Snapshot -Confirm:$false

# Remove snapshot and all children:
$snap = Get-Snapshot -VM "WebServer01" -Name "Parent"
Remove-Snapshot -Snapshot $snap -RemoveChildren -Confirm:$false

# Remove ALL snapshots for a VM:
Get-VM "WebServer01" | Get-Snapshot | Remove-Snapshot -Confirm:$false

# Bulk cleanup old snapshots:
Get-VM | Get-Snapshot | Where-Object { $_.Created -lt (Get-Date).AddDays(-30) } |
    Remove-Snapshot -Confirm:$false
```

**Common mistakes**:
- Not using `-RemoveChildren` when the snapshot tree has children (leaves orphans)
- Running Remove-Snapshot on a snapshot chain while a VM is running can take very long (disk consolidation)

### Set-Snapshot

Renames/re-describes an existing snapshot. Does NOT revert.

```
Set-Snapshot [-Snapshot] <Snapshot[]> [-Name <String>] [-Description <String>]
    [-Confirm] [-WhatIf]
```

**Returns**: Modified `Snapshot` object(s)

```powershell
# Rename a snapshot:
Get-Snapshot -VM "WebServer01" -Name "OldName" |
    Set-Snapshot -Name "NewName" -Description "Updated description"
```

### Snapshot Revert (via Set-VM)

As stated at the top: **there is no Revert-Snapshot cmdlet**. Use `Set-VM -Snapshot`:

```powershell
# Full revert workflow:
$vm = Get-VM -Name "WebServer01"
$snapshot = Get-Snapshot -VM $vm -Name "KnownGoodState"
Set-VM -VM $vm -Snapshot $snapshot -Confirm:$false

# Pipeline pattern:
Get-Snapshot -VM "WebServer01" -Name "KnownGoodState" |
    ForEach-Object { Set-VM -VM $_.VM -Snapshot $_ -Confirm:$false }
```

### Complete Snapshot Lifecycle Pattern

```powershell
# 1. Create snapshot before change
$vm = Get-VM -Name "WebServer01"
$snap = New-Snapshot -VM $vm -Name "Pre-Maintenance" `
    -Description "Before patch KB5001234" -Quiesce

# 2. Apply changes...
Invoke-VMScript -VM $vm -ScriptText "choco upgrade all -y" `
    -GuestUser "Administrator" -GuestPassword (ConvertTo-SecureString "P@ss" -AsPlainText -Force)

# 3. If changes fail, revert:
Set-VM -VM $vm -Snapshot $snap -Confirm:$false

# 4. If changes succeed, remove snapshot:
Remove-Snapshot -Snapshot $snap -Confirm:$false
```

---

## Host Management

### Get-VMHost

```
Get-VMHost [[-Name] <String[]>]
    [-Location <VIContainer[]>] [-Datastore <StorageResource[]>]
    [-VM <VirtualMachine[]>] [-ResourcePool <ResourcePool[]>]
    [-DistributedSwitch <DistributedSwitch[]>]
    [-State <VMHostState[]>] [-Tag <Tag[]>]
    [-NoRecursion] [-Server <VIServer[]>]

Get-VMHost -Id <String[]> [-Server <VIServer[]>]
Get-VMHost -RelatedObject <VMHostRelatedObjectBase[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | String[] | No (pos 0) | Host names. Supports wildcards |
| `-Location` | VIContainer[] | No | Folders, datacenters, clusters |
| `-State` | VMHostState[] | No | `Connected`, `Disconnected`, `NotResponding`, `Maintenance` |
| `-VM` | VirtualMachine[] | No | Find host running specific VM(s) |

**Returns**: `VMHost` objects

```powershell
# All hosts:
Get-VMHost

# Hosts in a cluster:
Get-VMHost -Location (Get-Cluster "Production")

# Connected hosts only:
Get-VMHost -State Connected

# Host running a specific VM:
Get-VMHost -VM (Get-VM "WebServer01")
```

### Set-VMHost

```
Set-VMHost [-VMHost] <VMHost[]> [[-State] <VMHostState>]
    [-LicenseKey <String>] [-TimeZone <VMHostTimeZone>]
    [-Profile <VMHostProfile>]
    [-VMSwapfileDatastore <Datastore>] [-VMSwapfilePolicy <VMSwapfilePolicy>]
    [-Evacuate] [-VsanDataMigrationMode <VsanDataMigrationMode>]
    [-Reason <String>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

State transitions: `Connected` (exit maintenance), `Disconnected`, `Maintenance` (enter maintenance).

**Returns**: Modified `VMHost` object(s)

```powershell
# Enter maintenance mode:
Set-VMHost -VMHost "esxi01" -State Maintenance -Evacuate -RunAsync

# Exit maintenance mode:
Set-VMHost -VMHost "esxi01" -State Connected

# Set license:
Set-VMHost -VMHost "esxi01" -LicenseKey "XXXXX-XXXXX-XXXXX-XXXXX-XXXXX"
```

### Get-VMHostNetworkAdapter

```
Get-VMHostNetworkAdapter [[-VirtualSwitch] <VirtualSwitchBase[]>] [[-Name] <String[]>]
    [-VMHost <VMHost[]>] [-Physical] [-VMKernel] [-Console]
    [-PortGroup <VirtualPortGroupBase[]>]
    [-Id <String[]>] [-Server <VIServer[]>]
```

**Returns**: `HostVirtualNic` objects

```powershell
# Get all physical NICs on a host:
Get-VMHostNetworkAdapter -VMHost "esxi01" -Physical

# Get VMkernel adapters:
Get-VMHostNetworkAdapter -VMHost "esxi01" -VMKernel

# Get adapters on a specific vSwitch:
Get-VMHostNetworkAdapter -VirtualSwitch (Get-VirtualSwitch -Name "vSwitch0")
```

---

## Datastore Management

### Get-Datastore

```
Get-Datastore [[-Name] <String[]>]
    [-Location <VIObject[]>] [-Tag <Tag[]>]
    [-RelatedObject <DatastoreRelatedObjectBase[]>] [-Refresh]
    [-Server <VIServer[]>]

Get-Datastore -Id <String[]> [-Server <VIServer[]>]
```

`-RelatedObject` aliases: `-VM`, `-VMHost`, `-Host`, `-Entity`

**Returns**: `Datastore` objects

**Key properties**: `Name`, `Id`, `Type` (VMFS/NFS/vVol), `FreeSpaceGB`, `CapacityGB`, `State`

```powershell
# All datastores:
Get-Datastore

# Specific datastore:
Get-Datastore -Name "SAN_LUN01"

# Datastores for a VM:
Get-Datastore -RelatedObject (Get-VM "WebServer01")

# Refresh storage info first:
Get-Datastore -Name "SAN_LUN01" -Refresh

# Find datastores with low space:
Get-Datastore | Where-Object { $_.FreeSpaceGB -lt 100 } |
    Select-Object Name, FreeSpaceGB, CapacityGB
```

### New-Datastore

```
# VMFS:
New-Datastore [-VMHost] <VMHost> [-Name] <String> -Path <String>
    [-Vmfs] [-BlockSizeMB <Int32>] [-FileSystemVersion <String>]

# NFS:
New-Datastore [-VMHost] <VMHost> [-Name] <String> -Path <String>
    -NfsHost <String[]> [-Nfs] [-ReadOnly] [-Kerberos] [-FileSystemVersion <String>]

# vVol:
New-Datastore [-VMHost] <VMHost> [-Name] <String>
    -VvolStorageContainer <StorageContainer>
```

**Returns**: `Datastore` object

```powershell
# Create VMFS datastore:
$lun = Get-ScsiLun -VMHost "esxi01" | Where-Object { $_.CapacityGB -gt 500 } | Select-Object -First 1
New-Datastore -VMHost "esxi01" -Name "NewVMFS" -Path $lun.CanonicalName -Vmfs

# Create NFS datastore:
New-Datastore -VMHost "esxi01" -Name "NFSShare" -Nfs `
    -NfsHost "10.0.0.50" -Path "/exports/vmware"
```

### Remove-Datastore

```
Remove-Datastore [-Datastore] <Datastore[]> [-VMHost] <VMHost>
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**Returns**: None. Warning: permanently deletes content of non-shared (VMFS) datastores.

---

## Cluster Management

### Get-Cluster

```
Get-Cluster [[-Name] <String[]>]
    [-Location <VIContainer[]>] [-VM <VirtualMachine[]>] [-VMHost <VMHost[]>]
    [-Tag <Tag[]>] [-NoRecursion] [-Server <VIServer[]>]

Get-Cluster -Id <String[]> [-Server <VIServer[]>]
```

**Returns**: `Cluster` objects

### New-Cluster

```
New-Cluster [-Name] <String> -Location <VIContainer>
    [-DrsEnabled] [-DrsAutomationLevel <DrsAutomationLevel>]
    [-HAEnabled] [-HAAdmissionControlEnabled] [-HAFailoverLevel <Int32>]
    [-HAIsolationResponse <HAIsolationResponse>] [-HARestartPriority <HARestartPriority>]
    [-VsanEnabled] [-VsanDiskClaimMode <VsanDiskClaimMode>]
    [-EVCMode <String>] [-VMSwapfilePolicy <VMSwapfilePolicy>]
    [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**Returns**: `Cluster` object

```powershell
# Create HA+DRS cluster:
New-Cluster -Name "Production" -Location (Get-Datacenter "DC1") `
    -DrsEnabled -DrsAutomationLevel FullyAutomated `
    -HAEnabled -HAAdmissionControlEnabled -HAFailoverLevel 1
```

### Set-Cluster

```
Set-Cluster [-Cluster] <Cluster[]> [[-Name] <String>]
    [-DrsEnabled <Boolean>] [-DrsAutomationLevel <DrsAutomationLevel>]
    [-HAEnabled <Boolean>] [-HAAdmissionControlEnabled <Boolean>]
    [-HAFailoverLevel <Int32>]
    [-VsanEnabled <Boolean>]
    [-EVCMode <String>] [-Profile <VMHostProfile>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**Returns**: Modified `Cluster` object(s)

---

## Template Management

### Get-Template

```
Get-Template [[-Name] <String[]>]
    [-Datastore <StorageResource[]>] [-Location <VIContainer[]>]
    [-NoRecursion] [-Server <VIServer[]>]

Get-Template -Id <String[]> [-Server <VIServer[]>]
```

**Returns**: `Template` objects

### New-Template

```
# Convert VM to template:
New-Template [-Name] <String> [-VM] <VirtualMachine> [-Location] <VIContainer>
    [-Datastore <StorageResource>] [-RunAsync]

# Clone template:
New-Template [[-Name] <String>] -Template <Template>
    [[-Location] <VIContainer>] [-Datastore <StorageResource>]
    [-DiskStorageFormat <VirtualDiskStorageFormat>] [-VMHost <VMHost>] [-RunAsync]

# Register from VMX:
New-Template [[-Name] <String>] [-TemplateFilePath] <String>
    [[-Location] <VIContainer>] -VMHost <VMHost> [-RunAsync]
```

**Returns**: `Template` object

### Set-Template

```
Set-Template [-Template] <Template[]> [-Name <String>] [-ToVM]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**Returns**: `Template` or `VirtualMachine` (with `-ToVM`)

```powershell
# Convert template back to VM:
Set-Template -Template "GoldImage-Template" -ToVM -Name "GoldImage"
```

---

## Resource Pools

### Get-ResourcePool

```
Get-ResourcePool [[-Name] <String[]>]
    [-Location <VIContainer[]>] [-VM <VirtualMachine[]>]
    [-Tag <Tag[]>] [-NoRecursion] [-Server <VIServer[]>]
```

**Returns**: `ResourcePool` objects

### New-ResourcePool

```
New-ResourcePool -Name <String> -Location <VIContainer>
    [-CpuReservationMhz <Int64>] [-CpuLimitMhz <Int64>]
    [-CpuSharesLevel <SharesLevel>] [-NumCpuShares <Int32>]
    [-CpuExpandableReservation <Boolean>]
    [-MemReservationGB <Decimal>] [-MemLimitGB <Decimal>]
    [-MemSharesLevel <SharesLevel>] [-NumMemShares <Int32>]
    [-MemExpandableReservation <Boolean>]
    [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**Returns**: `ResourcePool` object

```powershell
New-ResourcePool -Name "DevPool" -Location (Get-Cluster "Production") `
    -CpuSharesLevel Low -MemSharesLevel Low `
    -CpuLimitMhz 8000 -MemLimitGB 32
```

---

## Virtual Hardware

### Get-NetworkAdapter / New-NetworkAdapter / Set-NetworkAdapter

```
Get-NetworkAdapter [[-VM] <VirtualMachine[]>] [[-Template] <Template[]>]
    [[-Snapshot] <Snapshot[]>] [-Name <String[]>] [-Id <String[]>]

New-NetworkAdapter [-VM] <VirtualMachine>
    {-NetworkName <String> | -Portgroup <VirtualPortGroupBase> |
     -DistributedSwitch <DistributedSwitch> -PortId <String>}
    [-Type <VirtualNetworkAdapterType>] [-MacAddress <String>]
    [-StartConnected] [-WakeOnLan]

Set-NetworkAdapter [-NetworkAdapter] <NetworkAdapter[]>
    [-NetworkName <String>] [-Connected <Boolean>] [-StartConnected <Boolean>]
    [-Type <VirtualNetworkAdapterType>] [-MacAddress <String>] [-WakeOnLan <Boolean>]
    [-RunAsync] [-Confirm] [-WhatIf]
```

**VirtualNetworkAdapterType values**: `e1000`, `e1000e`, `Vmxnet`, `Vmxnet3`, `EnhancedVmxnet`, `Sriov`, `Pvrdma`

```powershell
# Get NICs:
Get-VM "WebServer01" | Get-NetworkAdapter

# Add NIC:
New-NetworkAdapter -VM "WebServer01" -NetworkName "VLAN100" `
    -Type Vmxnet3 -StartConnected

# Change network:
Get-VM "WebServer01" | Get-NetworkAdapter | Set-NetworkAdapter -NetworkName "VLAN200" -Confirm:$false

# Connect NIC:
Get-VM "WebServer01" | Get-NetworkAdapter -Name "Network adapter 1" |
    Set-NetworkAdapter -Connected $true -Confirm:$false
```

### Get-HardDisk / New-HardDisk / Set-HardDisk

```
Get-HardDisk [[-VM] <VirtualMachine[]>] [[-Template] <Template[]>]
    [[-Snapshot] <Snapshot[]>] [-Name <String[]>] [-DiskType <DiskType[]>]

New-HardDisk [-VM] <VirtualMachine>
    [-CapacityGB <Decimal>] [-CapacityKB <Int64>]
    [-Datastore <StorageResource>] [-Controller <ScsiController>]
    [-StorageFormat <VirtualDiskStorageFormat>] [-ThinProvisioned]
    [-DiskType <DiskType>] [-Persistence <String>]
    [-StoragePolicy <StoragePolicy>] [-DiskPath <String>]

Set-HardDisk [-HardDisk] <HardDisk[]>
    [-CapacityGB <Decimal>] [-CapacityKB <Int64>]
    [-Persistence <String>] [-Datastore <Datastore>]
    [-StorageFormat <VirtualDiskStorageFormat>]
    [-Controller <ScsiController>] [-Inflate] [-ZeroOut]
```

**Persistence values**: `Persistent` (default), `IndependentPersistent`, `IndependentNonPersistent`

```powershell
# Add 100GB thin disk:
New-HardDisk -VM "WebServer01" -CapacityGB 100 -StorageFormat Thin `
    -Datastore "SAN_LUN01"

# Expand existing disk:
Get-VM "WebServer01" | Get-HardDisk -Name "Hard disk 1" |
    Set-HardDisk -CapacityGB 200 -Confirm:$false

# Get disk info:
Get-VM "WebServer01" | Get-HardDisk |
    Select-Object Name, CapacityGB, StorageFormat, Filename
```

### Get-CDDrive / Set-CDDrive

```
Get-CDDrive [[-VM] <VirtualMachine[]>] [[-Template] <Template[]>]
    [[-Snapshot] <Snapshot[]>] [-Name <String[]>]

Set-CDDrive [-CD] <CDDrive[]>
    [-IsoPath <String>] [-HostDevice <String>] [-NoMedia]
    [-Connected <Boolean>] [-StartConnected <Boolean>]
    [-Confirm] [-WhatIf]
```

```powershell
# Mount ISO:
Get-VM "WebServer01" | Get-CDDrive | Set-CDDrive `
    -IsoPath "[SAN_LUN01] ISOs/Win2019.iso" -Connected $true -Confirm:$false

# Disconnect CD:
Get-VM "WebServer01" | Get-CDDrive | Set-CDDrive -NoMedia -Confirm:$false
```

---

## Guest Operations

### Get-VMGuest

```
Get-VMGuest [-VM] <VirtualMachine[]> [-Server <VIServer[]>]
```

**Returns**: `VMGuest` objects

**Key properties**: `VmName`, `OSFullName`, `IPAddress` (String[]), `HostName`, `State` (Running/NotRunning/ShuttingDown), `ToolsVersion`, `Nics`

```powershell
Get-VM "WebServer01" | Get-VMGuest | Select-Object VmName, OSFullName, IPAddress, State
```

### Invoke-VMScript

Runs a script inside the guest OS via VMware Tools.

```
Invoke-VMScript [-ScriptText] <String> [-VM] <VirtualMachine[]>
    [-GuestUser <String>] [-GuestPassword <SecureString>]
    [-GuestCredential <PSCredential>]
    [-HostUser <String>] [-HostPassword <SecureString>]
    [-HostCredential <PSCredential>]
    [-ScriptType <ScriptType>] [-ToolsWaitSecs <Int32>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ScriptText` | String | Yes (pos 0) | Script to execute |
| `-VM` | VirtualMachine[] | Yes (pos 1) | Target VM(s) |
| `-GuestUser` | String | No | Guest OS username |
| `-GuestPassword` | SecureString | No | Guest OS password |
| `-GuestCredential` | PSCredential | No | Guest OS credential object |
| `-ScriptType` | ScriptType | No | `PowerShell`, `Bat`, `Bash` |
| `-ToolsWaitSecs` | Int32 | No | Wait for tools availability (seconds) |

**Returns**: `VMScriptResult` objects (ScriptOutput, ExitCode)

```powershell
# Run PowerShell in Windows guest:
$secPass = ConvertTo-SecureString "GuestP@ss" -AsPlainText -Force
Invoke-VMScript -VM "WinServer01" -ScriptText "Get-Service | Where Status -eq Running" `
    -GuestUser "Administrator" -GuestPassword $secPass -ScriptType PowerShell

# Run bash in Linux guest:
Invoke-VMScript -VM "LinuxServer01" -ScriptText "df -h && free -m" `
    -GuestUser "root" -GuestPassword $secPass -ScriptType Bash

# With credential object:
$guestCred = Get-Credential
Invoke-VMScript -VM "WinServer01" -ScriptText "hostname" -GuestCredential $guestCred
```

**Common mistakes**:
- Using plain String for `-GuestPassword` (requires `SecureString`)
- Forgetting `-ScriptType` for Linux (defaults to PowerShell, which may not exist on Linux guest)
- Not waiting for VMware Tools: use `-ToolsWaitSecs 120` after VM power-on

---

## VM Migration

### Move-VM

```
Move-VM [-VM] <VirtualMachine[]> [[-Destination] <VIContainer>]
    [-Datastore <StorageResource>] [-DiskStorageFormat <VirtualDiskStorageFormat>]
    [-InventoryLocation <FolderContainer>]
    [-Network <Network[]>] [-NetworkAdapter <NetworkAdapter[]>]
    [-PortGroup <VirtualPortGroupBase[]>]
    [-VMotionPriority <VMotionPriority>]
    [-StoragePolicy <StoragePolicy>]
    [-RunAsync] [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**VMotionPriority**: `Standard`, `High`

**Returns**: `VirtualMachine` objects

```powershell
# vMotion to different host:
Move-VM -VM "WebServer01" -Destination (Get-VMHost "esxi02") -VMotionPriority High

# Storage vMotion:
Move-VM -VM "WebServer01" -Datastore (Get-Datastore "SAN_LUN02") `
    -DiskStorageFormat Thin

# Cross-host + cross-storage:
Move-VM -VM "WebServer01" `
    -Destination (Get-VMHost "esxi02") `
    -Datastore (Get-Datastore "SAN_LUN02")

# Move to different folder (inventory only):
Move-VM -VM "WebServer01" -InventoryLocation (Get-Folder "Production")
```

---

## Folders

### Get-Folder / New-Folder

```
Get-Folder [[-Name] <String[]>]
    [-Location <VIContainer[]>] [-Type <FolderType[]>]
    [-Tag <Tag[]>] [-NoRecursion] [-Server <VIServer[]>]

New-Folder [-Name] <String> [-Location] <VIContainer>
    [-Server <VIServer[]>] [-Confirm] [-WhatIf]
```

**FolderType**: `VM`, `HostAndCluster`, `Datastore`, `Network`, `Datacenter`

```powershell
# Get VM folders:
Get-Folder -Type VM

# Create folder:
New-Folder -Name "WebServers" -Location (Get-Folder "vm" -Type VM)
```

---

## Events and Tasks

### Get-VIEvent

```
Get-VIEvent [[-Entity] <VIObject[]>]
    [-Start <DateTime>] [-Finish <DateTime>]
    [-Types <EventCategory[]>] [-Username <String>]
    [-MaxSamples <Int32>] [-Server <VIServer[]>]
```

**EventCategory**: `Info`, `Warning`, `Error`

**Returns**: `VimApi.Event` objects

```powershell
# Recent errors:
Get-VIEvent -Types Error -MaxSamples 100

# Events for specific VM:
Get-VIEvent -Entity (Get-VM "WebServer01") -Start (Get-Date).AddDays(-1)

# Events by user:
Get-VIEvent -Username "admin@vsphere.local" -MaxSamples 50
```

### Get-Task

```
Get-Task [[-Status] <TaskState>] [-Server <VIConnection[]>]
Get-Task -Id <String[]> [-Server <VIConnection[]>]
```

**TaskState**: `Queued`, `Running`, `Success`, `Error`

```powershell
# Running tasks:
Get-Task -Status Running

# Recent errors:
Get-Task -Status Error
```

---

## Statistics

### Get-Stat / Get-StatType

```
Get-Stat [-Entity] <VIObject[]>
    [-Stat <String[]>] [-Start <DateTime>] [-Finish <DateTime>]
    [-MaxSamples <Int32>] [-IntervalMins <Int32[]>] [-IntervalSecs <Int32[]>]
    [-Realtime] [-Instance <String[]>]
    [-Common] [-Cpu] [-Disk] [-Memory] [-Network]

Get-StatType [-Entity] <VIObject[]>
    [[-Name] <String[]>] [-Realtime]
    [-Start <DateTime>] [-Finish <DateTime>]
    [-Interval <StatInterval[]>]
```

```powershell
# CPU usage (last 24h):
Get-Stat -Entity (Get-VM "WebServer01") -Stat "cpu.usage.average" `
    -Start (Get-Date).AddDays(-1) -IntervalMins 30

# All common stats:
Get-Stat -Entity (Get-VMHost "esxi01") -Common -Realtime -MaxSamples 10

# Available stat types:
Get-StatType -Entity (Get-VM "WebServer01")
```

---

## VM Start Policy

### Get-VMStartPolicy

```
Get-VMStartPolicy [[-VM] <VirtualMachine[]>]
    [-VMHost <VMHost[]>] [-Server <VIServer[]>]
```

**Returns**: `VMStartPolicy` objects (StartAction, StopAction, StartDelay, StartOrder)

---

## Common Patterns and Best Practices

### Credential Handling

```powershell
# Interactive (prompts for credentials):
$cred = Get-Credential
Connect-VIServer -Server vcenter -Credential $cred

# Non-interactive (scripts):
$secPass = ConvertTo-SecureString "P@ssw0rd!" -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential("admin@vsphere.local", $secPass)
Connect-VIServer -Server vcenter -Credential $cred

# Or using -User/-Password directly:
Connect-VIServer -Server vcenter -User "admin@vsphere.local" -Password 'P@ssw0rd!'
```

### Pipeline Patterns

```powershell
# Get snapshots for all VMs in a cluster:
Get-Cluster "Production" | Get-VM | Get-Snapshot

# Power on all VMs in a resource pool:
Get-ResourcePool "DevPool" | Get-VM | Where-Object { $_.PowerState -eq 'PoweredOff' } | Start-VM

# Get VMs with more than 8 CPUs:
Get-VM | Where-Object { $_.NumCpu -gt 8 } | Select-Object Name, NumCpu, MemoryGB

# Snapshot cleanup pipeline:
Get-VM | Get-Snapshot | Where-Object { $_.Created -lt (Get-Date).AddDays(-14) } |
    ForEach-Object { Write-Host "Removing: $($_.VM)/$($_.Name)"; $_ } |
    Remove-Snapshot -Confirm:$false
```

### Async Operations

```powershell
# Start multiple VMs asynchronously:
$tasks = Get-VM "Web*" | Start-VM -RunAsync

# Wait for all tasks:
$tasks | Wait-Task

# Check task status:
$tasks | Select-Object Description, State, PercentComplete
```

### Error Handling

```powershell
try {
    $vm = Get-VM -Name "NonExistent" -ErrorAction Stop
} catch [VMware.VimAutomation.ViCore.Types.V1.ErrorHandling.VimException.VimException] {
    Write-Warning "VM not found: $_"
} catch {
    Write-Error "Unexpected error: $_"
}

# Bulk operations with error handling:
Get-VM "Web*" | ForEach-Object {
    try {
        New-Snapshot -VM $_ -Name "Backup" -ErrorAction Stop
        Write-Host "Snapshot created for $($_.Name)"
    } catch {
        Write-Warning "Failed to snapshot $($_.Name): $_"
    }
}
```

### Filtering Patterns

```powershell
# By name wildcard:
Get-VM -Name "Web*", "DB*"

# By location:
Get-VM -Location (Get-Folder "Production")

# By tag:
Get-VM -Tag (Get-Tag "Environment:Production")

# Where-Object for complex filters:
Get-VM | Where-Object {
    $_.PowerState -eq 'PoweredOn' -and
    $_.NumCpu -ge 4 -and
    $_.MemoryGB -ge 8
}

# Combining pipeline filters:
Get-Cluster "Prod" | Get-VMHost -State Connected | Get-VM |
    Where-Object { $_.Guest.OSFullName -like "*Windows Server 2019*" }
```

---

## Common LLM Mistakes Reference

| Mistake | What LLMs Write | Correct Code |
|---------|-----------------|--------------|
| Non-existent Revert-Snapshot | `Revert-Snapshot $snap` | `Set-VM -VM $vm -Snapshot $snap` |
| Non-existent Restore-VMSnapshot | `Restore-VMSnapshot $snap` | `Set-VM -VM $vm -Snapshot $snap` |
| Wrong password type | `-GuestPassword "plain"` | `-GuestPassword (ConvertTo-SecureString "plain" -AsPlainText -Force)` |
| Wrong script type for Linux | `Invoke-VMScript ... -ScriptType PowerShell` (on Linux) | `Invoke-VMScript ... -ScriptType Bash` |
| Confusing Stop-VM with graceful | `Stop-VM` (thinking it is graceful) | `Shutdown-VMGuest` for graceful, `Stop-VM` for hard |
| Missing required params | `New-VM -Name "VM1"` (no host/pool) | `New-VM -Name "VM1" -VMHost $host` |
| Using -MemoryMB | `-MemoryMB 8192` | `-MemoryGB 8` (MemoryMB is obsolete) |
| Using -DiskMB | `-DiskMB 102400` | `-DiskGB 100` (DiskMB is obsolete) |
| Delete vs Remove | `Remove-VM` (thinking files deleted) | `Remove-VM -DeletePermanently` to also delete files |
| Wrong hardware version format | `-HardwareVersion "21"` | `-HardwareVersion "vmx-21"` |
| Inventing -Quiesce on Get-Snapshot | `Get-Snapshot -Quiesce` | `-Quiesce` is only on `New-Snapshot` |
| Pipeline to New-Snapshot | `Get-VM | New-Snapshot` (multiple) | `Get-VM | ForEach-Object { New-Snapshot -VM $_ -Name "X" }` |

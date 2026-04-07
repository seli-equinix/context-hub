---
name: powercli-appliance
description: "VMware PowerCLI 13.3 — vCenter appliance backup and management"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,appliance,Get-ApplianceBackupJob, Get-ApplianceBackupPart, New-ApplianceBackupJob, Stop-ApplianceBackupJob, Wait-ApplianceBackupJob"
---

# VMware PowerCLI — Appliance Management

vCenter appliance backup and management. Module: VMware.VimAutomation (5 cmdlets).

## Cmdlet Reference (5 cmdlets)

### Get

#### `Get-ApplianceBackupJob`

This cmdlet retrieves a list of backup jobs for a vCenter Server system.

**Parameters**: `Id, StartDate, EndDate, Server`

#### `Get-ApplianceBackupPart`

This cmdlet retrieves backup parts that can be included in a backup for a vCenter Server system.

**Parameters**: `Name, Id, OptionalOnly, Server`

### New

#### `New-ApplianceBackupJob`

This cmdlet starts a backup job for a vCenter Server system.

**Parameters**: `BackupServer, BackupServerPassword, BackupServerPort, BackupServerType, BackupServerUsername, Description, FolderPath, OptionalBackupParts, Password, Server`

### Stop

#### `Stop-ApplianceBackupJob`

This cmdlet stops running backup jobs on a vCenter Server system.

**Parameters**: `BackupJob, Id, Server`

### Wait

#### `Wait-ApplianceBackupJob`

This cmdlet monitors the progress of a backup job and returns the ApplianceBackupJob object when the backup job is complete.

**Parameters**: `BackupJob, Id, Server`

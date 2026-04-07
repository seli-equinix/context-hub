---
name: powercli-appliance
description: "VMware PowerCLI 13.3 — vCenter appliance backup and management"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,appliance,Get-ApplianceBackupJob, Get-ApplianceBackupPart, New-ApplianceBackupJob, Stop-ApplianceBackupJob, Wait-ApplianceBackupJob"
---

# VMware PowerCLI — Appliance Management

vCenter appliance backup and management. Module: VMware.VimAutomation (5 cmdlets).

## Get

### `Get-ApplianceBackupJob`

**This cmdlet retrieves a list of backup jobs for a vCenter Server system.**

This cmdlet retrieves a list of finished or currently running backup jobs.

**Parameters:**

- -EndDate [DateTime] (Optional) Retrieves backup jobs with end time later than the provided time.
- -Id [String[]] (Optional) Retrieves backup jobs whose IDs match the specified IDs.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StartDate [DateTime] (Optional) Retrieves backup jobs with start time later than the provided time.

**Examples:**

```powershell
Get-ApplianceBackupJob
```
_List all backup jobs._

```powershell
Get-ApplianceBackupJob -StartDate (Get-Date).AddDays(-1)
```
_List all backup jobs that have started since yesterday or will start in the future._

```powershell
Get-ApplianceBackupJob -EndDate (Get-Date).AddDays(-1)
```
_List all backup jobs that have finished since yesterday or will finish in the future._

### `Get-ApplianceBackupPart`

**This cmdlet retrieves backup parts that can be included in a backup for a vCenter Server system.**

Retrieves a list of parts that can be included in a backup job, and their estimated backup size. Non-optional backup parts are always included in the backup.

**Parameters:**

- -Id [String[]] (Required) Retrieves only those backup parts whose IDs match the provided IDs.
- -Name [String[]] (Optional) Retrieves only those backup parts whose names match the provided names.
- -OptionalOnly [SwitchParameter] (Optional) Returns optional backup parts only.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-ApplianceBackupPart
```
_Lists all available backup parts._

```powershell
Get-ApplianceBackupPart -OptionalOnly
```
_Retrieves all optional backup parts. You can pass them by pipeline to the New-ApplianceBackupJob cmdlet._

```powershell
Get-ApplianceBackupPart | Measure-Object -Sum -Property SizeMB | Select-Object -ExpandProperty Sum
```
_Compute the estimated size of a full backup in MBs._

## New

### `New-ApplianceBackupJob`

**This cmdlet starts a backup job for a vCenter Server system.**

This cmdlet starts a file-based backup job for a vCenter Server system to a backup server.

**Parameters:**

- -BackupServer [String] (Required) The IP or FQDN of the backup server to be used for the backup.
- -BackupServerPassword [SecureString] (Optional) Password for the given backup server. If unset, authentication will not be used for the specified backup server.
- -BackupServerPort [Int32] (Optional) The backup server port to be used for the backup.
- -BackupServerType [String] (Required) The type of the backup server. Currently supported types are FTP, HTTP, FTPS, HTTPS, SCP, SFTP, NFS, SMB
- -BackupServerUsername [String] (Optional) Username for the given backup server. If unset, authentication will not be used for the specified backup server.
- -Description [String] (Optional) Provides a custom comment to the backup job. If unset, the comment will be empty.
- -FolderPath [String] (Required) A folder path on the backup server where the backup will be created. It must be an empty or non-existing folder. In case the folder doesn't exist it will be created.
- -OptionalBackupParts [ApplianceBackupPart[]] (Optional) A list of optional backup parts that will be included in the backup job. You can use Get-ApplianceBackupPart -OptinalOnly to retrieve a list of the available parts.
- -Password [SecureString] (Optional) You can set a password for encryption of a backup. The password must adhere to the following requirements. The length must be at least 8 characters but not more than 20 characters. It must include at least one uppercase letter, lowercase letter, numeric digit, and special character (i.e. any character different from [0-9,a-z,A-Z]). Only visible ASCII characters are permitted (no spaces). If no password is specified, the backup will not be encrypted.
- -Server [VIServer] (Optional) Specifies the vCenter Server system on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default server. Note: This cmdlet can only run on a single vCenter Server at a time since a specific folder on the backup server can only hold a single server backup.

**Examples:**

```powershell
PS C:\> New-ApplianceBackupJob `
   -BackupServerType FTP `
   -BackupServer <backup server ip> `
   -BackupServerPort 21 `
   -BackupServerUsername <backup server username> `
   -BackupServerPassword <backup server password> `
   -FolderPath /backups/manual_backup_1 `
   -Description "This is a custom comment"
```
_Starts a backup job for a vCenter Server system that is going to be stored at an FTP server in the /backups/manual_backup_1 folder and encrypted with a password. Only mandatory backup parts are included since no optional backup parts have been specified._

```powershell
PS C:\> Get-ApplianceBackupPart -OptionalOnly | New-ApplianceBackupJob `
   -BackupServerType FTP `
   -BackupServer <backup server ip> `
   -BackupServerPort 21 `
   -BackupServerUsername <backup server username> `
   -BackupServerPassword <backup server password> `
   -FolderPath /backups/manual_backup_1 `
   -Description "This is a custom comment"
```
_Starts a backup job for a vCenter Server system that is going to be stored at an FTP server in the /backups/manual_backup_1 folder and encrypted with a password. All mandatory and optional backup parts are included._

## Stop

### `Stop-ApplianceBackupJob`

**This cmdlet stops running backup jobs on a vCenter Server system.**

This cmdlet stops a list of running backup jobs matching the specified parameters.

**Parameters:**

- -BackupJob [ApplianceBackupJob[]] (Optional) A list of ApplianceBackupJob objects representing the backup jobs to be stopped.
- -Id [String[]] (Required) Stops backup jobs whose IDs match the specified IDs.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> Get-ApplianceBackupJob -Server 'vCenter Server' | Stop-ApplianceBackupJob
```
_Stops all backup jobs on the specified vCenter Server._

```powershell
PS C:\> Stop-ApplianceBackupJob -Id '<backup job id>'
```
_Stops a backup job with the specified ID._

## Wait

### `Wait-ApplianceBackupJob`

**This cmdlet monitors the progress of a backup job and returns the ApplianceBackupJob object when the backup job is complete.**

**Parameters:**

- -BackupJob [ApplianceBackupJob[]] (Optional) Specifies one or more ApplianceBackupJob object(s) representing the backup jobs you want to monitor and receive when finished.
- -Id [String[]] (Required) Specifies the IDs of the backup jobs you want to monitor and receive when finished.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
PS C:\> Get-ApplianceBackupJob -Server 'vCenter server' | Wait-ApplianceBackupJob
```
_Monitors the progress of all backup jobs on the 'vCenter Server' server and returns the backup job objects when finished._

```powershell
PS C:\> Wait-ApplianceBackupJob -Id '<backup job id>'
```
_Monitors the progress of a backup job with the specified ID and returns the backup job object when finished_

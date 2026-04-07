---
name: powercli-appliance
description: "VMware PowerCLI 13.3 — vCenter Server Appliance (VCSA) backup management, backup jobs, and backup parts"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,appliance,vcsa,backup,disaster-recovery,Get-ApplianceBackupJob,Get-ApplianceBackupPart,New-ApplianceBackupJob,Stop-ApplianceBackupJob,Wait-ApplianceBackupJob"
---

# VMware PowerCLI — Appliance Management

## Golden Rule

**These cmdlets manage file-based backups of the vCenter Server Appliance (VCSA) itself -- not VM backups. VCSA backup captures the vCenter database, configuration, and certificates. Without a current VCSA backup, losing your vCenter means rebuilding your entire management plane from scratch.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| List backup jobs | `Get-ApplianceBackupJob` | Verifying backups ran successfully | Filter by `-StartDate`/`-EndDate` for time range |
| List backup parts | `Get-ApplianceBackupPart` | Checking what can be backed up and size estimates | Non-optional parts are always included |
| Start backup | `New-ApplianceBackupJob` | Scheduled or ad-hoc VCSA backup | Requires a reachable backup server (FTP/SCP/SFTP/NFS/SMB) |
| Monitor backup | `Wait-ApplianceBackupJob` | Waiting for backup to complete in a script | Blocks until job finishes |
| Cancel backup | `Stop-ApplianceBackupJob` | Aborting a running backup | Use when backup is stuck or no longer needed |

## Scenario: Automated VCSA Backup to SFTP Server

```powershell
# Estimate backup size before starting
$parts = Get-ApplianceBackupPart -Server $vcenter
$totalMB = ($parts | Measure-Object -Property SizeMB -Sum).Sum
Write-Output "Estimated full backup size: $([math]::Round($totalMB / 1024, 2)) GB"

# List optional parts (stats, events, tasks DB)
$optionalParts = Get-ApplianceBackupPart -OptionalOnly -Server $vcenter
$optionalParts | Select-Object Id, Name, SizeMB, Optional | Format-Table

# Start a full backup (mandatory + all optional parts) to SFTP
$backupDate = Get-Date -Format "yyyyMMdd-HHmm"
$job = $optionalParts | New-ApplianceBackupJob `
    -BackupServerType SFTP `
    -BackupServer "backup.example.com" `
    -BackupServerPort 22 `
    -BackupServerUsername "vcbackup" `
    -BackupServerPassword (ConvertTo-SecureString "BackupPass!" -AsPlainText -Force) `
    -FolderPath "/backups/vcenter/$backupDate" `
    -Password (ConvertTo-SecureString "EncryptB@ckup1" -AsPlainText -Force) `
    -Description "Automated backup $backupDate" `
    -Server $vcenter

# Wait for completion and check result
$result = Wait-ApplianceBackupJob -BackupJob $job -Server $vcenter
Write-Output "Backup $($result.Id): $($result.State) - Duration: $($result.Duration)"
```

## Scenario: Backup Verification and Monitoring

```powershell
# Check if any backup has run in the last 24 hours
$recentJobs = Get-ApplianceBackupJob -StartDate (Get-Date).AddDays(-1) -Server $vcenter
if ($recentJobs.Count -eq 0) {
    Write-Warning "NO VCSA BACKUP in the last 24 hours!"
} else {
    $recentJobs | Select-Object Id, State, StartTime, EndTime,
        @{N='Duration';E={if($_.EndTime){($_.EndTime - $_.StartTime).ToString("hh\:mm\:ss")}else{"Running"}}} |
        Format-Table
}

# Find failed backup jobs in the last week
Get-ApplianceBackupJob -StartDate (Get-Date).AddDays(-7) -Server $vcenter |
    Where-Object { $_.State -eq "FAILED" } |
    Select-Object Id, StartTime, State, Messages | Format-Table -Wrap

# Stop a stuck backup job
$runningJobs = Get-ApplianceBackupJob -Server $vcenter |
    Where-Object { $_.State -eq "INPROGRESS" }
if ($runningJobs) {
    $runningJobs | Stop-ApplianceBackupJob -Confirm:$false -Server $vcenter
    Write-Output "Stopped $($runningJobs.Count) running backup jobs"
}
```

## Common Mistakes

### Mistake 1: No Encryption Password on Backup

```powershell
# WRONG -- Backup is unencrypted, contains vCenter DB with credentials
New-ApplianceBackupJob -BackupServerType SFTP -BackupServer "backup.example.com" `
    -BackupServerUsername "vcbackup" -BackupServerPassword $pass `
    -FolderPath "/backups/vcenter/latest"
# Anyone with access to the backup server can read vCenter secrets

# CORRECT -- Always encrypt VCSA backups
New-ApplianceBackupJob -BackupServerType SFTP -BackupServer "backup.example.com" `
    -BackupServerUsername "vcbackup" -BackupServerPassword $pass `
    -FolderPath "/backups/vcenter/latest" `
    -Password (ConvertTo-SecureString "Str0ngEncrypt!" -AsPlainText -Force)
```

### Mistake 2: Not Including Optional Parts in the Backup

```powershell
# WRONG -- Only mandatory parts backed up (config + DB core)
# Stats, events, and tasks history are lost on restore
New-ApplianceBackupJob -BackupServerType SFTP -BackupServer "backup.example.com" `
    -BackupServerUsername "vcbackup" -BackupServerPassword $pass `
    -FolderPath "/backups/vcenter/latest"

# CORRECT -- Include optional parts for a complete backup
Get-ApplianceBackupPart -OptionalOnly | New-ApplianceBackupJob `
    -BackupServerType SFTP -BackupServer "backup.example.com" `
    -BackupServerUsername "vcbackup" -BackupServerPassword $pass `
    -FolderPath "/backups/vcenter/latest" `
    -Password $encryptionPass
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-ApplianceBackupJob` | List backup jobs | `-Id`, `-StartDate`, `-EndDate`, `-Server` |
| `Get-ApplianceBackupPart` | List backup parts + sizes | `-Name`, `-OptionalOnly`, `-Server` |
| `New-ApplianceBackupJob` | Start backup | `-BackupServerType` (FTP/FTPS/HTTP/HTTPS/SCP/SFTP/NFS/SMB), `-BackupServer`, `-BackupServerPort`, `-BackupServerUsername`, `-BackupServerPassword`, `-FolderPath`, `-Password` (encryption), `-OptionalBackupParts`, `-Description` |
| `Stop-ApplianceBackupJob` | Cancel running backup | `-BackupJob` or `-Id` |
| `Wait-ApplianceBackupJob` | Block until complete | `-BackupJob` or `-Id` |

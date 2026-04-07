---
name: powercli-storage-protocols
description: "VMware PowerCLI 13.3 — iSCSI HBA target management and NFS user accounts for ESXi storage connectivity"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,storage-protocols,iscsi,nfs,hba,chap,kerberos,Get-IScsiHbaTarget,New-IScsiHbaTarget,Set-IScsiHbaTarget,Remove-IScsiHbaTarget,Get-NfsUser,New-NfsUser,Set-NfsUser,Remove-NfsUser"
---

# VMware PowerCLI — Storage Protocols

## Golden Rule

**These cmdlets manage the TRANSPORT layer between ESXi hosts and storage arrays -- iSCSI targets and NFS authentication. They do NOT create datastores (use `New-Datastore` for that). You configure iSCSI targets first, then rescan, then create the datastore.**

| Protocol | Cmdlets | Use When | Prerequisites |
|----------|---------|----------|---------------|
| **iSCSI** | `*-IScsiHbaTarget` | Connecting ESXi to SAN storage via iSCSI | Software iSCSI adapter enabled on host |
| **NFS v4.1** | `*-NfsUser` | Kerberos authentication for NFS datastores | Host must be joined to Active Directory |

**iSCSI target workflow:**
1. Enable software iSCSI adapter: `Get-VMHostHba -Type iScsi`
2. Add target: `New-IScsiHbaTarget`
3. Rescan: `Get-VMHostStorage -RescanAllHba`
4. Create datastore: `New-Datastore -Vmfs`

## Scenario: Configure iSCSI Storage with CHAP Authentication

```powershell
# Find the iSCSI HBA on each host in the cluster
$cluster = Get-Cluster "Production" -Server $vcenter
$hosts = Get-VMHost -Location $cluster -Server $vcenter

foreach ($vmhost in $hosts) {
    $hba = Get-VMHostHba -VMHost $vmhost -Type iScsi | Where-Object { $_.Model -eq "iSCSI Software Adapter" }

    if (-not $hba) {
        Write-Warning "$($vmhost.Name) has no software iSCSI adapter enabled"
        continue
    }

    # Add send target (dynamic discovery) with CHAP authentication
    New-IScsiHbaTarget -IScsiHba $hba -Address "10.0.50.10" -Port 3260 `
        -Type Send -ChapType Required `
        -ChapName "esxi-initiator" -ChapPassword "ChapSecret123!" `
        -Server $vcenter

    # Add a second target for multipathing
    New-IScsiHbaTarget -IScsiHba $hba -Address "10.0.50.11" -Port 3260 `
        -Type Send -ChapType Required `
        -ChapName "esxi-initiator" -ChapPassword "ChapSecret123!" `
        -Server $vcenter

    # Rescan to discover LUNs
    Get-VMHostStorage -VMHost $vmhost -RescanAllHba -RescanVmfs
    Write-Output "Configured iSCSI targets on $($vmhost.Name)"
}

# Verify targets across all hosts
$hosts | ForEach-Object {
    Get-VMHostHba -VMHost $_ -Type iScsi | Get-IScsiHbaTarget |
        Select-Object @{N='Host';E={$_.VMHost.Name}}, Address, Port, Type, AuthenticationProperties
} | Format-Table
```

## Scenario: NFS v4.1 Kerberos User Management

```powershell
# Create NFS user accounts for Kerberos-authenticated NFS v4.1
$vmhost = Get-VMHost "esxi01.example.com" -Server $vcenter
$cred = Get-Credential -UserName "nfs-svc@EXAMPLE.COM"
New-NfsUser -VMHost $vmhost -Credential $cred -Server $vcenter

# List NFS users across all hosts
Get-VMHost -Location (Get-Cluster "Production") -Server $vcenter | ForEach-Object {
    Get-NfsUser -VMHost $_ -Server $vcenter |
        Select-Object @{N='Host';E={$_.VMHost.Name}}, Username
} | Format-Table

# Update NFS user password (e.g., after AD password rotation)
$nfsUser = Get-NfsUser -VMHost $vmhost -Name "nfs-svc" -Server $vcenter
Set-NfsUser -NfsUser $nfsUser -Password (ConvertTo-SecureString "NewPassword!" -AsPlainText -Force)
```

## Common Mistakes

### Mistake 1: Adding iSCSI Target Without CHAP on a Secured Array

```powershell
# WRONG -- No CHAP authentication, array rejects the connection
New-IScsiHbaTarget -IScsiHba $hba -Address "10.0.50.10"
# Target is added but no LUNs are discovered because array requires CHAP

# CORRECT -- Match the CHAP credentials configured on the storage array
New-IScsiHbaTarget -IScsiHba $hba -Address "10.0.50.10" `
    -ChapType Required -ChapName "esxi-init" -ChapPassword "ArraySecret!" `
    -MutualChapEnabled $true -MutualChapName "array-tgt" -MutualChapPassword "MutualSecret!"
```

### Mistake 2: Forgetting to Rescan After Adding Targets

```powershell
# WRONG -- Target added but ESXi does not see any new LUNs
New-IScsiHbaTarget -IScsiHba $hba -Address "10.0.50.10" -Type Send
# No LUNs visible, no new datastores

# CORRECT -- Always rescan after adding/modifying targets
New-IScsiHbaTarget -IScsiHba $hba -Address "10.0.50.10" -Type Send
Get-VMHostStorage -VMHost $vmhost -RescanAllHba -RescanVmfs
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-IScsiHbaTarget` | List iSCSI targets | `-IScsiHba`, `-IPEndPoint`, `-Type` (Send/Static) |
| `New-IScsiHbaTarget` | Add iSCSI target | `-IScsiHba`, `-Address`, `-Port`, `-Type`, `-ChapType`, `-ChapName`, `-ChapPassword`, `-IScsiName` (static only) |
| `Set-IScsiHbaTarget` | Modify target CHAP | `-Target`, `-ChapType`, `-ChapPassword`, `-MutualChapEnabled`, `-MutualChapPassword` |
| `Remove-IScsiHbaTarget` | Remove target | `-Target` |
| `Get-NfsUser` | List NFS users | `-VMHost`, `-Name` |
| `New-NfsUser` | Create NFS user | `-VMHost`, `-Name`, `-Password` or `-Credential`, `-Force` (overwrite) |
| `Set-NfsUser` | Change NFS password | `-NfsUser`, `-Password` |
| `Remove-NfsUser` | Delete NFS user | `-NfsUser` |

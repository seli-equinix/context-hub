---
name: powercli-storage-protocols
description: "VMware PowerCLI 13.3 — NFS and iSCSI storage protocol management"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,storage-protocols,Get-IScsiHbaTarget, Get-NfsUser, New-IScsiHbaTarget, New-NfsUser, Remove-IScsiHbaTarget, Remove-NfsUser, Set-IScsiHbaTarget, Set-NfsUser"
---

# VMware PowerCLI — Storage Protocols

NFS and iSCSI storage protocol management. Module: VMware.VimAutomation (8 cmdlets).

## Cmdlet Reference (8 cmdlets)

### Get

#### `Get-IScsiHbaTarget`

This cmdlet retrieves the available iSCSI HBA targets.

**Parameters**: `IScsiHba, Type, IPEndPoint, Server`

#### `Get-NfsUser`

This cmdlet retrieves NFS user accounts.

**Parameters**: `Name, VMHost, Server`

### New

#### `New-IScsiHbaTarget`

This cmdlet creates a new iSCSI HBA target.

**Parameters**: `IScsiHba, Address, Port, Type, IScsiName, ChapType, ChapName, ChapPassword, MutualChapEnabled, MutualChapName, MutualChapPassword, InheritChap` (+2 more)

#### `New-NfsUser`

This cmdlet creates an NFS user account on the specified virtual machine host.

**Parameters**: `Name, Password, VMHost, Force, Credential, Server`

### Remove

#### `Remove-IScsiHbaTarget`

This cmdlet removes targets from their iSCSI HBAs.

**Parameters**: `Target, Server`

#### `Remove-NfsUser`

This cmdlet deletes the specified NFS user accounts.

**Parameters**: `NfsUser`

### Set

#### `Set-IScsiHbaTarget`

This cmdlet modifies the configuration of an iSCSI HBA target.

**Parameters**: `Target, ChapType, ChapName, ChapPassword, MutualChapEnabled, MutualChapName, MutualChapPassword, InheritChap, InheritMutualChap, Server`

#### `Set-NfsUser`

This cmdlet configures existing NFS user accounts by changing the password associated with the account.

**Parameters**: `NfsUser, Password, Server`

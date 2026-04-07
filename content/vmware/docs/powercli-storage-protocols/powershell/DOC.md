---
name: powercli-storage-protocols
description: "VMware PowerCLI 13.3 — NFS and iSCSI storage protocol management"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,storage-protocols,Get-IScsiHbaTarget, Get-NfsUser, New-IScsiHbaTarget, New-NfsUser, Remove-IScsiHbaTarget, Remove-NfsUser, Set-IScsiHbaTarget, Set-NfsUser"
---

# VMware PowerCLI — Storage Protocols

NFS and iSCSI storage protocol management. Module: VMware.VimAutomation (8 cmdlets).

## Get

### `Get-IScsiHbaTarget`

**This cmdlet retrieves the available iSCSI HBA targets.**

This cmdlet retrieves the available iSCSI HBA targets. The cmdlet retrieves the configured targets (send and static) on the specified iSCSI storage adapters. If IPEndPoint is specified, filters the result by <Address>:<Port>. If no IScsiHba is provided - retrieves all targets from the entire inventory.

**Parameters:**

- -IPEndPoint [String[]] (Optional) Specifies <Address>:<Port> to filter the available iSCSI HBA targets.
- -IScsiHba [IScsiHba[]] (Optional) Specifies the iSCSI HBA whose targets you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [IScsiHbaTargetType[]] (Optional) Specifies the type of the iSCSI HBA targets you want to retrieve. The valid values are Send and Static.

**Examples:**

```powershell
Get-IScsiHbaTarget -Address "10.23.84.73" -Type Send
```
_Retrieves the targets of type Send on the specified address._

### `Get-NfsUser`

**This cmdlet retrieves NFS user accounts.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Name [String[]] (Optional) Filters the retrieved NFS user accounts by user name.
- -VMHost [VMHost[]] (Optional) Specifies the virtual machine hosts for which you want to retrieve NFS user accounts.

**Examples:**

```powershell
Get-NfsUser -VMHost $vmhost
```
_Retrieves the NFS user accounts from the specified host._

```powershell
Get-NfsUser -Username MyUser*
```
_Retrieves all NFS user accounts that have a user name which starts with MyUser._

## New

### `New-IScsiHbaTarget`

**This cmdlet creates a new iSCSI HBA target.**

This cmdlet creates a new iSCSI HBA target. The cmdlet also enables and configures the CHAP (Challenge Handshake Authentication Protocol) authentication settings of the new target.

**Parameters:**

- -Address [String] (Required) Specifies the address of the new iSCSI HBA target. Passing multiple values to this parameter is obsolete.
- -ChapName [String] (Optional) Specifies a CHAP authentication name for the new target.
- -ChapPassword [String] (Optional) Specifies a CHAP authentication password for the new target.
- -ChapType [ChapType] (Optional) Specifies the type of the CHAP (Challenge Handshake Authentication Protocol) you want the new target to use. The valid values are Prohibited, Discouraged, Preferred, and Required.
- -InheritChap [Boolean] (Optional) Indicates that the CHAP setting is inherited from the iSCSI HBA.
- -InheritMutualChap [Boolean] (Optional) Indicates that the Mutual CHAP setting is inherited from the iSCSI HBA.
- -IScsiHba [IScsiHba] (Required) Specifies the iSCSI HBA for which you want to create the new target. Passing multiple values to this parameter is obsolete.
- -IScsiName [String] (Optional) Specifies the iSCSI name of the target. It can be specified only for Static targets.
- -MutualChapEnabled [Boolean] (Optional) Indicates that Mutual CHAP is enabled.
- -MutualChapName [String] (Optional) Specifies a Mutual CHAP authentication name for the new target.
- -MutualChapPassword [String] (Optional) Specifies a Mutual CHAP authentication password for the new target.
- -Port [Int32] (Optional) Specifies the TCP port of the target.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [IScsiHbaTargetType] (Optional) Specifies the type of the target. The valid values are Static and Send.

**Examples:**

```powershell
$hba = Get-VMHost | Get-VMHostHba -Type iScsi

New-IScsiHbaTarget -IScsiHba $hba -Address 10.23.84.73
```
_Creates a new target with IP address 10.23.84.73 on the specified iSCSI HBA device._

```powershell
Get-VMHost | Get-VMHostHba -Type iScsi | New-IScsiHbaTarget -Address "10.23.84.73" -ChapType Preferred -ChapName user -ChapPassword pass
```
_Creates a new target on the provided iSCSI HBA device and configures the CHAP settings of the target._

### `New-NfsUser`

**This cmdlet creates an NFS user account on the specified virtual machine host.**

This cmdlet creates an NFS user account on the specified virtual machine host. The credentials of the newly created NFS user account are used by the NFS v4.1 for Kerberos authentication. If an NFS user account already exists on the virtual machine host, this cmdlet overwrites that NFS user account. The virtual machine host must be part of an Active Directory domain for the cmdlet to run successfully.

**Parameters:**

- -Credential [PSCredential] (Optional) Specifies a PSCredential object for the Kerberos authentication.
- -Force [SwitchParameter] (Optional) By default, the cmdlet fails to create an NFS user account if an NFS user account with the same user name already exists on the virtual machine host. If the Force parameter is specified, the cmdlet overwrites the existing NFS user account.
- -Name [String] (Optional) Specifies the NFS user name that you want to use for the Kerberos authentication.
- -Password [SecureString] (Optional) Specifies password for authentication. This parameter accepts both secure and plain strings.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VMHost [VMHost] (Required) Specifies the virtual machine host to which you want to add the NFS user account.

**Examples:**

```powershell
New-NfsUser -VMHost $vmhost -Username "user1" -Password "password1"
```
_Creates the "user1" NFS user account on the $vmhost virtual machine host and sets the password to "password1"._

```powershell
New-NfsUser -VMHost $vmhost -Credential $myCredentialsObject
```
_Creates an NFS user account by using a credential object._

## Remove

### `Remove-IScsiHbaTarget`

**This cmdlet removes targets from their iSCSI HBAs.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Target [IScsiHbaTarget[]] (Required) Specifies the iSCSI HBA targets you want to remove.

**Examples:**

```powershell
Get-IScsiHbaTarget -Address 10.23.84.73 -Type Send | Remove-IScsiHbaTarget
```
_Retrieves and removes the targets of type Send on the specified address._

```powershell
Remove-IScsiHbaTarget -Target (Get-IScsiHbaTarget -Address 10.23.84.73)
```
_Removes the specified iSCSI HBA targets._

### `Remove-NfsUser`

**This cmdlet deletes the specified NFS user accounts.**

**Parameters:**

- -NfsUser [NfsUser[]] (Required) Specifies the NFS user account you want to delete.

**Examples:**

```powershell
Remove-NfsUser -NfsUser $n1
```
_Deletes the specified NFS user account._

## Set

### `Set-IScsiHbaTarget`

**This cmdlet modifies the configuration of an iSCSI HBA target.**

This cmdlet modifies the configuration of an iSCSI HBA target. The cmdlet modifies the CHAP and Digest properties of an iSCSI HBA target. You must specify at least one of the CHAP-related (or Mutual CHAP) parameters. Otherwise, an error message is displayed.

**Parameters:**

- -ChapName [String] (Optional) Specifies the CHAP initiator name if CHAP is enabled.
- -ChapPassword [String] (Optional) Specifies the CHAP password if CHAP is enabled.
- -ChapType [ChapType] (Optional) Specifies the type of the CHAP authorization. The valid values are Prohibited, Discouraged, Preferred, and Required. If you set ChapType to Discouraged, Preferred, or Required, then you must specify the ChapPassword parameter as well.
- -InheritChap [Boolean] (Optional) Indicates that the CHAP setting is inherited from the iSCSI HBA device.
- -InheritMutualChap [Boolean] (Optional) Indicates that the Mutual CHAP setting is inherited from the iSCSI HBA device.
- -MutualChapEnabled [Boolean] (Optional) Indicates that mutual CHAP is enabled. In this case, you must specify the MutualChapPassword parameter as well.
- -MutualChapName [String] (Optional) Specifies the Mutual CHAP initiator name if CHAP is enabled.
- -MutualChapPassword [String] (Optional) Specifies the Mutual CHAP password if CHAP is enabled.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Target [IScsiHbaTarget[]] (Required) Specifies the iSCSI HBA target you want to configure. To identify the target, you can provide an IScsiTarget object or use an <Address>:<Port> string.

**Examples:**

```powershell
Get-IScsiHbaTarget -Address "10.23.84.73" -Type Static | Set-IScsiHbaTarget -ChapType Prohibited
```
_Retrieves the targets of type Static on the specified address and sets their CHAP type to Prohibited._

```powershell
$target = Get-IScsiHbaTarget -Address "10.23.84.73" -Type Send

Set-IScsiHbaTarget -Target $target -ChapType Required -ChapPassword pass1 -MutualChapEnabled -MutualChapPassword pass2
```
_Modifies the CHAP and Mutual CHAP settings of the targets of type Send on the specified address._

### `Set-NfsUser`

**This cmdlet configures existing NFS user accounts by changing the password associated with the account.**

This cmdlet configures existing NFS user accounts by changing the password associated with the account. The virtual machine host must be part of an Active Directory domain for the cmdlet to run successfully.

**Parameters:**

- -NfsUser [NfsUser[]] (Required) Specifies the NFS user account you want to configure.
- -Password [SecureString] (Required) Specifies the new password for authentication. This parameter accepts both secure and plain strings.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-NfsUser -NfsUser $n1 -Password "password2"
```
_Sets "password2" as the new password for the $n1 NFS user account._

---
name: powercli-lifecycle
description: "VMware PowerCLI 13.3 — Image management, firmware, host patching, LCM"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 2
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,lifecycle,Get-LcmImage, New-LcmOfflineDepot, Update-Tools"
---

# VMware PowerCLI — Lifecycle Management

Image management, firmware, host patching, LCM. Module: VMware.VimAutomation (3 cmdlets).

## Get

### `Get-LcmImage`

**This cmdlet retrieves the vSphere Lifecycle Manager images available on a vCenter Server system.**

This cmdlet retrieves the vSphere Lifecycle Manager images available on a vCenter Server system. The cmdlet returns a set of vSphere Lifecycle Manager images that correspond to the filter criteria specified by the provided parameters. To specify a server different from the default one, use the -Server parameter.

**Parameters:**

- -Category [LcmImageCategory[]] (Optional) Specifies the categories of the vSphere Lifecycle Manager images you want to retrieve.
- -Id [String[]] (Required) Specifies the IDs of the vSphere Lifecycle Manager images you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the vSphere Lifecycle Manager images you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Type [LcmImageType] (Optional) Specifies the type of the vSphere Lifecycle Manager images you want to retrieve.
- -Version [String[]] (Optional) Specifies the versions of the vSphere Lifecycle Manager images you want to retrieve.

**Examples:**

```powershell
Get-LcmImage -Type BaseImage -Version '7.0 GA - 15843807'
```
_Retrieves an ESXi base image with version 7.0 and build number 15843807 from the default connected servers._

```powershell
Get-LcmImage -Type VendorAddOn -Category @('Bugfix', 'Enhancement')
```
_Retrieves vendor add-ons that are either bug fixes or enhancements from the default connected servers._

## New

### `New-LcmOfflineDepot`

**This cmdlet creates a new vSphere Lifecycle Manager offline depot.**

This cmdlet creates a new vSphere Lifecycle Manager offline depot from a provided online location.

**Parameters:**

- -Description [String] (Optional) Provides a description of the depot that you want to create.
- -Location [Uri] (Optional) The URL of the depot update file from which to create the offline depot.
- -OwnerData [String] (Optional) Any string that you want to associate and store with the depot.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.

**Examples:**

```powershell
PS C:\> New-LcmOfflineDepot -Location 'http://link/to/offline/depot' -Description 'Company offline depot' -OwnerData '{depot:security_updates}'
```
_Creates a new offline depot from the depot update file located at http://link/to/offline/depot. OwnerData can be any string that you want to associate with the new depot._

```powershell
PS C:\> New-LcmOfflineDepot -Location 'file:///link/to/offline/depot' -Description 'Company offline depot' -OwnerData 'Building 1 servers' -RunAsync
```
_Creates a new offline depot from the depot update file located at http://link/to/offline/depot. The command will return a task that continues to run in the background_

## Update

### `Update-Tools`

**This cmdlet upgrades VMware Tools on the specified virtual machine guest OS.**

This cmdlet upgrades the VMware Tools on the specified virtual machine guest OS. VMware Tools must be installed prior to updating it. After VMware Tools is updated, the virtual machine is restarted unless the NoReboot parameter is specified.

**Parameters:**

- -Guest [VMGuest[]] (Optional) Specifies the guest operating systems on which you want to update VMware Tools.
- -NoReboot [SwitchParameter] (Optional) Indicates that you do not want to reboot the system after updating VMware Tools. This parameter is supported only for Windows operating systems. NoReboot passes the following set of options to the VMware Tools installer on the guest OS:
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies a list of the virtual machines whose VMware Tools you want to upgrade.

**Examples:**

```powershell
Update-Tools VM
```
_Updates the VMware Tools on the specified virtual machine. The virtual machine must be powered on._

```powershell
Get-VMGuest VM | Update-Tools
```
_Updates the VMware Tools on the virtual machine specified by its guest operating system. The virtual machine must be powered on._

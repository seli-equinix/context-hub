---
name: powercli-lifecycle
description: "VMware PowerCLI 13.3 — Image management, firmware, host patching, LCM"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,lifecycle,Get-LcmImage, New-LcmOfflineDepot, Update-Tools"
---

# VMware PowerCLI — Lifecycle Management

Image management, firmware, host patching, LCM. Module: VMware.VimAutomation (3 cmdlets).

## Cmdlet Reference (3 cmdlets)

### Get

#### `Get-LcmImage`

This cmdlet retrieves the vSphere Lifecycle Manager images available on a vCenter Server system.

**Parameters**: `Name, Id, Category, Type, Version, Server`

### New

#### `New-LcmOfflineDepot`

This cmdlet creates a new vSphere Lifecycle Manager offline depot.

**Parameters**: `Location, Description, OwnerData, RunAsync`

### Update

#### `Update-Tools`

This cmdlet upgrades VMware Tools on the specified virtual machine guest OS.

**Parameters**: `NoReboot, RunAsync, Guest, VM, Server`

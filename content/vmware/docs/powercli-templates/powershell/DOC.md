---
name: powercli-templates
description: "VMware PowerCLI 13.3 — VM template management — create templates, deploy from templates"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,templates,Get-Template, Move-Template, New-Template, Remove-Template, Set-Template"
---

# VMware PowerCLI — Templates

VM template management — create templates, deploy from templates. Module: VMware.VimAutomation (5 cmdlets).

## Cmdlet Reference (5 cmdlets)

### Get

#### `Get-Template`

This cmdlet retrieves the virtual machine templates available on a vCenter Server system.

**Parameters**: `Location, Datastore, Name, Id, NoRecursion, Server`

### Move

#### `Move-Template`

This cmdlet moves virtual machine templates to another location.

**Parameters**: `Template, Destination, RunAsync, Server`

### New

#### `New-Template`

This cmdlet creates a new virtual machine template.

**Parameters**: `VM, Name, Location, VMHost, Datastore, DiskStorageFormat, Template, TemplateFilePath, Server, RunAsync`

### Remove

#### `Remove-Template`

This cmdlet removes the specified virtual machine templates from the inventory.

**Parameters**: `Template, DeletePermanently, RunAsync, Server`

### Set

#### `Set-Template`

This cmdlet modifies the specified virtual machine template.

**Parameters**: `Template, Name, ToVM, Server, RunAsync`

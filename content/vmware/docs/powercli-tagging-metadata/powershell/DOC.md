---
name: powercli-tagging-metadata
description: "VMware PowerCLI 13.3 — Tags, tag categories, custom attributes, annotations"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,tagging-metadata,Get-Annotation, Get-CustomAttribute, Get-Tag, Get-TagAssignment, Get-TagCategory, New-CustomAttribute, New-Tag, New-TagAssignment, New-TagCategory, Remove-CustomAttribute, Remove-Tag, Remove-TagAssignment, Remove-TagCategory, Set-Annotation, Set-CustomAttribute, Set-Tag, Set-TagCategory"
---

# VMware PowerCLI — Tagging & Metadata

Tags, tag categories, custom attributes, annotations. Module: VMware.VimAutomation (17 cmdlets).

## Cmdlet Reference (17 cmdlets)

### Get

#### `Get-Annotation`

This cmdlet retrieves annotations.

**Parameters**: `CustomAttribute, Entity, Name, Server`

#### `Get-CustomAttribute`

This cmdlet retrieves custom attributes.

**Parameters**: `Id, Name, TargetType, Global, Server`

#### `Get-Tag`

This cmdlet retrieves the tags available on a vCenter Server system.

**Parameters**: `Name, Category, Id, Server`

#### `Get-TagAssignment`

This cmdlet retrieves the tag assignments of objects.

**Parameters**: `Entity, Tag, Category, Server`

#### `Get-TagCategory`

This cmdlet retrieves the tag categories available on a vCenter Server system and filters them using the specified cmdlet parameters.

**Parameters**: `Name, Id, Server`

### New

#### `New-CustomAttribute`

This cmdlet creates a new custom attribute.

**Parameters**: `Name, TargetType, Server`

#### `New-Tag`

This cmdlet creates a new tag in the specified tag category with the specified parameters.

**Parameters**: `Name, Category, Description, Server`

#### `New-TagAssignment`

This cmdlet assigns the specified tag(s) to the specified entity(s).

**Parameters**: `Tag, Entity, Server`

#### `New-TagCategory`

This cmdlet creates a new tag category on the specified vCenter Server systems with the specified parameters.

**Parameters**: `Name, Description, Cardinality, EntityType, Server`

### Remove

#### `Remove-CustomAttribute`

This cmdlet removes custom attributes.

**Parameters**: `CustomAttribute, Server`

#### `Remove-Tag`

This cmdlet removes the specified tags from the server.

**Parameters**: `Tag, Server`

#### `Remove-TagAssignment`

This cmdlet removes the specified tag assignment.

**Parameters**: `TagAssignment`

#### `Remove-TagCategory`

This cmdlet removes the specified tag categories from the server.

**Parameters**: `Category, Server`

### Set

#### `Set-Annotation`

This cmdlet modifies the value of a custom attribute.

**Parameters**: `Entity, CustomAttribute, Value, Server`

#### `Set-CustomAttribute`

This cmdlet renames a custom attribute.

**Parameters**: `CustomAttribute, Name, Server`

#### `Set-Tag`

This cmdlet modifies the specified tags.

**Parameters**: `Tag, Name, Description, Server`

#### `Set-TagCategory`

This cmdlet modifies the specified tag categories.

**Parameters**: `Category, Name, Description, Cardinality, AddEntityType, Server`

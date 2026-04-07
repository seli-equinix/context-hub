---
name: powercli-tags
description: "VMware PowerCLI 13.3 — tags, categories, annotations, custom attributes"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Get-Annotation,Get-CustomAttribute,Get-Tag,Get-TagAssignment,Get-TagCategory,New-CustomAttribute,New-Tag,New-TagAssignment,New-TagCategory,Remove-CustomAttribute,Remove-Tag,Remove-TagAssignment,Remove-TagCategory,Set-Annotation,Set-CustomAttribute,Set-Tag,Set-TagCategory"
---

# VMware PowerCLI — tags, categories, annotations, custom attributes

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Get-Annotation` | This cmdlet retrieves annotations. |
| `Get-CustomAttribute` | This cmdlet retrieves custom attributes. |
| `Get-Tag` | This cmdlet retrieves the tags available on a vCenter Server system. |
| `Get-TagAssignment` | This cmdlet retrieves the tag assignments of objects. |
| `Get-TagCategory` | This cmdlet retrieves the tag categories available on a vCenter Server system and filters them us... |
| `New-CustomAttribute` | This cmdlet creates a new custom attribute. |
| `New-Tag` | This cmdlet creates a new tag in the specified tag category with the specified parameters. |
| `New-TagAssignment` | This cmdlet assigns the specified tag(s) to the specified entity(s). |
| `New-TagCategory` | This cmdlet creates a new tag category on the specified vCenter Server systems with the specified... |
| `Remove-CustomAttribute` | This cmdlet removes custom attributes. |
| `Remove-Tag` | This cmdlet removes the specified tags from the server. |
| `Remove-TagAssignment` | This cmdlet removes the specified tag assignment. |
| `Remove-TagCategory` | This cmdlet removes the specified tag categories from the server. |
| `Set-Annotation` | This cmdlet modifies the value of a custom attribute. |
| `Set-CustomAttribute` | This cmdlet renames a custom attribute. |
| `Set-Tag` | This cmdlet modifies the specified tags. |
| `Set-TagCategory` | This cmdlet modifies the specified tag categories. |

---

### Get-Annotation

This cmdlet retrieves annotations.

This cmdlet retrieves annotations. An annotation is a user-defined description field of one or more vSphere objects.

**Returns**: `Annotation`

```
Get-Annotation
    [-CustomAttribute <CustomAttribute[]>]
    -Entity <InventoryItem>
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CustomAttribute` | `CustomAttribute[]` | No | Specifies the custom attributes whose annotations you want to retrieve. |
| `-Entity` | `InventoryItem` | Yes | Specifies the entities whose annotations you want to retrieve. |
| `-Name` | `String[]` | No | Specifies the names of the annotations you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-CustomAttribute

This cmdlet retrieves custom attributes.

This cmdlet retrieves custom attributes. A custom attribute is a user-defined description field of one or more vSphere objects.

**Returns**: `CustomAttribute`

```
Get-CustomAttribute
    [-Global]
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-TargetType <CustomAttributeTargetType[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Global` | `SwitchParameter` | No | Indicates that only global custom attributes are retrieved. A global custom attribute can be applied both to hosts and virtual machines. |
| `-Id` | `String[]` | No | Specifies the IDs of the custom attributes you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of t... |
| `-Name` | `String[]` | No | Specifies the names of the custom attributes you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TargetType` | `CustomAttributeTargetType[]` | No | Specifies a target type to filter the custom attributes by the type of objects to which they can be applied. The valid values are VirtualMachine, ResourcePool, Folder, VMHost, Cluster, Datacenter, ... |

---

### Get-Tag

This cmdlet retrieves the tags available on a vCenter Server system.

This cmdlet retrieves the tags available on a vCenter Server system. This cmdlet filters tags by name and category to which tags belong.

**Returns**: `Tag`

```
Get-Tag
    [-Category <TagCategory[]>]
    -Id <String[]>
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `TagCategory[]` | No | Filters the tags by category. |
| `-Id` | `String[]` | Yes | Filters the tags by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list. |
| `-Name` | `String[]` | No | Filters the tags by name. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-TagAssignment

This cmdlet retrieves the tag assignments of objects.

This cmdlet retrieves the tag assignments of objects. If the Entity parameter is specified, the cmdlet returns only the tag assignments for the corresponding items. If the Category parameter is specified, the cmdlet returns only the tag assignments of tags that belong to the specified category.

**Returns**: `TagAssignment`

```
Get-TagAssignment
    [-Tag <Tag[]>]
    [-Category <TagCategory[]>]
    [-Entity <VIObjectCore[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Tag` | `Tag[]` | No | Returns the tag assignments that belong to the specified tags. |
| `-Category` | `TagCategory[]` | No | Returns the tags that belong to the specified categories. |
| `-Entity` | `VIObjectCore[]` | No | Retrieves the tags associated with the specified items. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-TagCategory

This cmdlet retrieves the tag categories available on a vCenter Server system and filters them using the specified cmdlet parameters.

**Returns**: `TagCategory`

```
Get-TagCategory
    -Id <String[]>
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Filters the tag categories by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list. |
| `-Name` | `String[]` | No | Filters the tag categories by name. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### New-CustomAttribute

This cmdlet creates a new custom attribute.

This cmdlet creates a new custom attribute. A custom attribute is a user-defined description field of one or more vCenter Server objects.

**Returns**: `CustomAttribute`

```
New-CustomAttribute
    -Name <String>
    [-Server <VIServer[]>]
    [-TargetType <CustomAttributeTargetType[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | Specifies a name for the new custom attribute. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TargetType` | `CustomAttributeTargetType[]` | No | Specifies the type of the objects to which the new custom attribute applies. The valid values are VirtualMachine, ResourcePool, Folder, VMHost, Cluster, Datacenter, and $null. If the value is $null... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-Tag

This cmdlet creates a new tag in the specified tag category with the specified parameters.

**Returns**: `Tag`

```
New-Tag
    -Category <TagCategory>
    [-Description <String>]
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `TagCategory` | Yes | Specifies the tag category in which the new tag will be created. |
| `-Description` | `String` | No | Specifies the description of the new tag. |
| `-Name` | `String` | Yes | Specifies the name of the new tag. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-TagAssignment

This cmdlet assigns the specified tag(s) to the specified entity(s).

This cmdlet assigns the specified tag to the specified entity.

**Returns**: `TagAssignment`

```
New-TagAssignment
    -Entity <VIObjectCore[]>
    [-Server <VIServer[]>]
    -Tag <Tag[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObjectCore[]` | Yes | Specifies the object on which to assign the specified tag. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | Yes | Specifies the tag to be assigned to the entity. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-TagCategory

This cmdlet creates a new tag category on the specified vCenter Server systems with the specified parameters.

**Returns**: `TagCategory`

```
New-TagCategory
    [-Cardinality <Cardinality>]
    [-Description <String>]
    [-EntityType <String[]>]
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cardinality` | `Cardinality` | No | Specifies the cardinality of the tag category. If not specified, the default value is "Single".   "Single" means that only a single tag from this category can be assigned to a specific object at a ... |
| `-Description` | `String` | No | Specifies the description of the new tag category. |
| `-EntityType` | `String[]` | No | Defines the type of objects to which the tags in this category will be applicable. If you do not specify this parameter or specify "All" as a value, the tags in this category will be applicable to ... |
| `-Name` | `String` | Yes | Specifies the name of the new tag category. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-CustomAttribute

This cmdlet removes custom attributes.

**Returns**: `None`

```
Remove-CustomAttribute
    -CustomAttribute <CustomAttribute[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CustomAttribute` | `CustomAttribute[]` | Yes | Specifies the custom attributes you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-Tag

This cmdlet removes the specified tags from the server.

**Returns**: `None`

```
Remove-Tag
    [-Server <VIServer[]>]
    -Tag <Tag[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | Yes | Specifies the tags you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-TagAssignment

This cmdlet removes the specified tag assignment.

This cmdlet removes the specified tag assignment. The cmdlet removes the assignment of the tag in TagAssignment.Tag from the entity in TagAssignment.Entity.

**Returns**: `None`

```
Remove-TagAssignment
    -TagAssignment <TagAssignment[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-TagAssignment` | `TagAssignment[]` | Yes | Specifies the assigned tags to be removed. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-TagCategory

This cmdlet removes the specified tag categories from the server.

**Returns**: `None`

```
Remove-TagCategory
    -Category <TagCategory[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `TagCategory[]` | Yes | Specifies the categories you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Annotation

This cmdlet modifies the value of a custom attribute.

This cmdlet modifies the value of a custom attribute that applies to one or more inventory items.

**Returns**: `Annotation`

```
Set-Annotation
    -CustomAttribute <CustomAttribute>
    -Entity <InventoryItem[]>
    [-Server <VIServer[]>]
    -Value <String>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CustomAttribute` | `CustomAttribute` | Yes | Specifies the custom attribute whose annotation you want to change. |
| `-Entity` | `InventoryItem[]` | Yes | Specifies the entities to which the new annotation value applies. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Value` | `String` | Yes | Specifies a new value for the annotation. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-CustomAttribute

This cmdlet renames a custom attribute.

**Returns**: `CustomAttribute`

```
Set-CustomAttribute
    -CustomAttribute <CustomAttribute[]>
    -Name <String>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CustomAttribute` | `CustomAttribute[]` | Yes | Specifies the custom attribute you want to rename. |
| `-Name` | `String` | Yes | Specifies a new name for the custom attribute. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-Tag

This cmdlet modifies the specified tags.

**Returns**: `Tag`

```
Set-Tag
    [-Description <String>]
    [-Name <String>]
    [-Server <VIServer[]>]
    -Tag <Tag[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Description` | `String` | No | Specifies the new description to set to the specified tags. |
| `-Name` | `String` | No | Specifies the name to which the specified tags will be renamed. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Tag` | `Tag[]` | Yes | Specifies the tags that you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-TagCategory

This cmdlet modifies the specified tag categories.

This cmdlet modifies the specified tag categories. The cardinality of a tag category can only be changed from "Single" to "Multiple".

**Returns**: `TagCategory`

```
Set-TagCategory
    [-AddEntityType <String[]>]
    [-Cardinality <Cardinality>]
    -Category <TagCategory[]>
    [-Description <String>]
    [-Name <String>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AddEntityType` | `String[]` | No | Adds the specified entity types to the list of types that tags in this category are applicable to. If you specify "All" as a value, the tags will be applicable to all entity types.   This parameter... |
| `-Cardinality` | `Cardinality` | No | Specifies the cardinality of the tag category. If not specified, the default value is "Single".   "Single" means that only a single tag from this category can be assigned to a specific object at a ... |
| `-Category` | `TagCategory[]` | Yes | Specifies the tag categories that you want to configure. |
| `-Description` | `String` | No | Specifies the new description to set to the tag categories. |
| `-Name` | `String` | No | Specifies the name to which the specified tag categories will be renamed. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

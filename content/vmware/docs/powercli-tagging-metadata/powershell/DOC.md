---
name: powercli-tagging-metadata
description: "VMware PowerCLI 13.3 — Tags, tag categories, custom attributes, annotations"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,tagging-metadata,Get-Annotation, Get-CustomAttribute, Get-Tag, Get-TagAssignment, Get-TagCategory, New-CustomAttribute, New-Tag, New-TagAssignment, New-TagCategory, Remove-CustomAttribute, Remove-Tag, Remove-TagAssignment, Remove-TagCategory, Set-Annotation, Set-CustomAttribute, Set-Tag, Set-TagCategory"
---

# VMware PowerCLI — Tagging & Metadata

Tags, tag categories, custom attributes, annotations. Module: VMware.VimAutomation (17 cmdlets).

## Get

### `Get-Annotation`

**This cmdlet retrieves annotations.**

This cmdlet retrieves annotations. An annotation is a user-defined description field of one or more vSphere objects.

**Parameters:**

- -CustomAttribute [CustomAttribute[]] (Optional) Specifies the custom attributes whose annotations you want to retrieve.
- -Entity [InventoryItem] (Required) Specifies the entities whose annotations you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the annotations you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Cluster Cluster | Get-Annotation -CustomAttribute PhysicalLocation
```
_Retrieves the annotation of the PhysicalLocation custom attribute for Cluster._

```powershell
$vm = Get-VM -Name $vmname
Get-Annotation -Entity $vm -CustomAttribute Description
```
_Retrieves the annotation of the Description custom attribute for the $vm virtual machine._

### `Get-CustomAttribute`

**This cmdlet retrieves custom attributes.**

This cmdlet retrieves custom attributes. A custom attribute is a user-defined description field of one or more vSphere objects.

**Parameters:**

- -Global [SwitchParameter] (Optional) Indicates that only global custom attributes are retrieved. A global custom attribute can be applied both to hosts and virtual machines.
- -Id [String[]] (Optional) Specifies the IDs of the custom attributes you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the custom attributes you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TargetType [CustomAttributeTargetType[]] (Optional) Specifies a target type to filter the custom attributes by the type of objects to which they can be applied. The valid values are VirtualMachine, ResourcePool, Folder, VMHost, Cluster, Datacenter, and $null. If the value is $null, the custom attribute is global and applies to all target types.

**Examples:**

```powershell
Get-CustomAttribute -Global
```
_Retrieves all global custom attributes._

```powershell
Get-CustomAttribute -TargetType "VirtualMachine", "VMHost"
```
_Retrieves all custom attributes of type VirtualMachine and VMHost._

```powershell
Get-CustomAttribute -Name "Creation*" -Global
```
_Retrieves only global custom attributes that match the specified name pattern._

### `Get-Tag`

**This cmdlet retrieves the tags available on a vCenter Server system.**

This cmdlet retrieves the tags available on a vCenter Server system. This cmdlet filters tags by name and category to which tags belong.

**Parameters:**

- -Category [TagCategory[]] (Optional) Filters the tags by category.
- -Id [String[]] (Required) Filters the tags by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Filters the tags by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Tag -Name "MyTag"
```
_Returns all tags named "MyTag"._

```powershell
Get-Tag -Category "MyCategory1", "MyCategory2" -Name "MyTag"
```
_Returns all tags from the "MyCategory1" and "MyCategory2" categories, named "MyTag"._

### `Get-TagAssignment`

**This cmdlet retrieves the tag assignments of objects.**

This cmdlet retrieves the tag assignments of objects. If the Entity parameter is specified, the cmdlet returns only the tag assignments for the corresponding items. If the Category parameter is specified, the cmdlet returns only the tag assignments of tags that belong to the specified category.

**Parameters:**

- -Tag [Tag[]] (Optional) Returns the tag assignments that belong to the specified tags.
- -Category [TagCategory[]] (Optional) Returns the tags that belong to the specified categories.
- -Entity [VIObjectCore[]] (Optional) Retrieves the tags associated with the specified items.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-TagAssignment
```
_Retrieves all tag assignments for the current vCenter Server instances._

```powershell
$datastore = Get-DataStore MyDatastore
Get-TagAssignment -Entity $datastore -Category MyCategory
```
_Retrieves all tag assignments for the $datastore entity that have tags from the "MyCategory" category._

```powershell
Get-TagAssignment -Tag MyTag
```
_Retrieves all assignments of the specified tag._

### `Get-TagCategory`

**This cmdlet retrieves the tag categories available on a vCenter Server system and filters them using the specified cmdlet parameters.**

**Parameters:**

- -Id [String[]] (Required) Filters the tag categories by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Filters the tag categories by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-TagCategory -Name "MyTagCategory" -Server "MyServer"
```
_Retrieves a tag category named "MyTagCategory" from a vCenter Server system._

## New

### `New-CustomAttribute`

**This cmdlet creates a new custom attribute.**

This cmdlet creates a new custom attribute. A custom attribute is a user-defined description field of one or more vCenter Server objects.

**Parameters:**

- -Name [String] (Required) Specifies a name for the new custom attribute.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TargetType [CustomAttributeTargetType[]] (Optional) Specifies the type of the objects to which the new custom attribute applies. The valid values are VirtualMachine, ResourcePool, Folder, VMHost, Cluster, Datacenter, and $null. If the value is $null the custom attribute is global and applies to all target types.

**Examples:**

```powershell
New-CustomAttribute -Name "CompanyName" -TargetType VMHost, VirtualMachine
```
_Creates a new custom attribute named CompanyName for the virtual machines and hosts on the server._

### `New-Tag`

**This cmdlet creates a new tag in the specified tag category with the specified parameters.**

**Parameters:**

- -Category [TagCategory] (Required) Specifies the tag category in which the new tag will be created.
- -Description [String] (Optional) Specifies the description of the new tag.
- -Name [String] (Required) Specifies the name of the new tag.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-TagCategory -Name "MyTagCategory" | New-Tag -Name "MyTag" -Description "Create MyTag tag in MyTagCategory category."
```
_Retrieves a specific tag category, named "MyTagCategory", creates a tag named "MyTag" inside it, and sets the tag description._

### `New-TagAssignment`

**This cmdlet assigns the specified tag(s) to the specified entity(s).**

This cmdlet assigns the specified tag to the specified entity.

**Parameters:**

- -Entity [VIObjectCore[]] (Required) Specifies the object on which to assign the specified tag.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Required) Specifies the tag to be assigned to the entity.

**Examples:**

```powershell
$myTag = Get-Tag "MyTag"
Get-VM "*MyVM*" | New-TagAssignment -Tag $myTag
```
_Assigns the "MyTag" tag to all virtual machines whose name contains the " MyVM " wildcard pattern._

### `New-TagCategory`

**This cmdlet creates a new tag category on the specified vCenter Server systems with the specified parameters.**

**Parameters:**

- -Cardinality [Cardinality] (Optional) Specifies the cardinality of the tag category. If not specified, the default value is "Single".   "Single" means that only a single tag from this category can be assigned to a specific object at a time. "Multiple" means that more than one tag from this category can be assigned to a specific object at a time.
- -Description [String] (Optional) Specifies the description of the new tag category.
- -EntityType [String[]] (Optional) Defines the type of objects to which the tags in this category will be applicable. If you do not specify this parameter or specify "All" as a value, the tags in this category will be applicable to all valid entity types.   This parameter accepts both PowerCLI type names and vSphere API type names. The valid PowerCLI type names are: Cluster, Datacenter, Datastore, DatastoreCluster, DistributedPortGroup, DistributedSwitch, Folder, ResourcePool, VApp, VirtualMachine, VM, VMHost, ContentLibrary, ContentLibraryItem, Network, HostNetwork, OpaqueNetwork.   For non-PowerCLI types, a namespace prefix is required. Example: 'urn:vim25:VirtualMachine'
- -Name [String] (Required) Specifies the name of the new tag category.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-TagCategory -Name "MyTagCategory" -Cardinality "Single" -EntityType "VirtualMachine"
```
_Creates a new tag category, named "MyTagCategory", defining the "VirtualMachine" type as applicable to the tags inside that category and specifying that only a single tag from that category can be assigned to a specific VirtualMachine object at a time._

```powershell
New-TagCategory -Name "MyTagCategory" -Cardinality "Multiple" -Description "MyTagCategory description"
```
_Creates a new tag category, named "MyTagCategory", that has "MyTagCategory description" set as a description and specifies that multiple tags from that category can be assigned to an object. Tags from this category are applicable to all valid entity types._

## Remove

### `Remove-CustomAttribute`

**This cmdlet removes custom attributes.**

**Parameters:**

- -CustomAttribute [CustomAttribute[]] (Required) Specifies the custom attributes you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-CustomAttribute -CustomAttribute "CompanyID", "Owner" -Server $agent007
```
_Removes the CompanyID and Owner custom attributes from the server stored in the $agent007 variable._

### `Remove-Tag`

**This cmdlet removes the specified tags from the server.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Required) Specifies the tags you want to remove.

**Examples:**

```powershell
$tagCategory = Get-TagCategory "MyTagCategory"
Get-Tag -Name "MyTag1", "MyTag2" -Category $tagCategory | Remove-Tag
```
_Retrieves the tags named "MyTag1" and "MyTag2" from the specified tag category named "MyTagCategory" and then removes the tags from the vCenter Server system._

### `Remove-TagAssignment`

**This cmdlet removes the specified tag assignment.**

This cmdlet removes the specified tag assignment. The cmdlet removes the assignment of the tag in TagAssignment.Tag from the entity in TagAssignment.Entity.

**Parameters:**

- -TagAssignment [TagAssignment[]] (Required) Specifies the assigned tags to be removed.

**Examples:**

```powershell
$myVM = Get-VM myvm
$myTagAssignment = Get-TagAssignment $myVM
Remove-TagAssignment $myTagAssignment
```
_Removes all connections to tags from the specified virtual machine entity._

### `Remove-TagCategory`

**This cmdlet removes the specified tag categories from the server.**

**Parameters:**

- -Category [TagCategory[]] (Required) Specifies the categories you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-TagCategory "MyTagCategory" | Remove-TagCategory
```
_Retrieves a tag category named "MyTagCategory" and then removes it from the vCenter Server system._

## Set

### `Set-Annotation`

**This cmdlet modifies the value of a custom attribute.**

This cmdlet modifies the value of a custom attribute that applies to one or more inventory items.

**Parameters:**

- -CustomAttribute [CustomAttribute] (Required) Specifies the custom attribute whose annotation you want to change.
- -Entity [InventoryItem[]] (Required) Specifies the entities to which the new annotation value applies.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Value [String] (Required) Specifies a new value for the annotation.

**Examples:**

```powershell
Set-Annotation -Entity $vmhost -CustomAttribute "PhysicalLocation" -Value Office
```
_Modifies the annotation of the PhysicalLocation custom attribute for the host stored in the $vmhost variable._

```powershell
Get-Cluster Cluster | Set-Annotation -CustomAttribute "PhysicalLocation" -Value California
```
_Modifies the annotation of the PhysicalLocation custom attribute for the Cluster cluster._

### `Set-CustomAttribute`

**This cmdlet renames a custom attribute.**

**Parameters:**

- -CustomAttribute [CustomAttribute[]] (Required) Specifies the custom attribute you want to rename.
- -Name [String] (Required) Specifies a new name for the custom attribute.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-CustomAttribute -Name CreationDetails -CustomAttribute CreationDate
```
_Renames a custom attribute from CreationDate to CreationDetails._

```powershell
Get-CustomAttribute -Name CreationDate -Server server1, server2 | Set-CustomAttribute -Name CreationDetails
```
_Renames the custom attributes retrieved from the specified vSphere servers from CreationDate to CreationDetails._

### `Set-Tag`

**This cmdlet modifies the specified tags.**

**Parameters:**

- -Description [String] (Optional) Specifies the new description to set to the specified tags.
- -Name [String] (Optional) Specifies the name to which the specified tags will be renamed.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Required) Specifies the tags that you want to configure.

**Examples:**

```powershell
Get-Tag -Name "MyTag" | Set-Tag -Name "MyNewTag" -Description "MyNewDescription"
```
_Retrieves a tag named "MyTag" and updates its name and description._

### `Set-TagCategory`

**This cmdlet modifies the specified tag categories.**

This cmdlet modifies the specified tag categories. The cardinality of a tag category can only be changed from "Single" to "Multiple".

**Parameters:**

- -AddEntityType [String[]] (Optional) Adds the specified entity types to the list of types that tags in this category are applicable to. If you specify "All" as a value, the tags will be applicable to all entity types.   This parameter accepts both PowerCLI type names and vSphere API type names. The valid PowerCLI type names are: Cluster, Datacenter, Datastore, DatastoreCluster, DistributedPortGroup, DistributedSwitch, Folder, ResourcePool, VApp, VirtualPortGroup, VirtualMachine, VM, VMHost.   For non-PowerCLI types, a namespace prefix is required. Example: 'urn:vim25:VirtualMachine'
- -Cardinality [Cardinality] (Optional) Specifies the cardinality of the tag category. If not specified, the default value is "Single".   "Single" means that only a single tag from this category can be assigned to a specific object at a time. "Multiple" means that more than one tag from this category can be assigned to a specific object at a time.   The only value that is accepted for this parameter is "Multiple".
- -Category [TagCategory[]] (Required) Specifies the tag categories that you want to configure.
- -Description [String] (Optional) Specifies the new description to set to the tag categories.
- -Name [String] (Optional) Specifies the name to which the specified tag categories will be renamed.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-TagCategory "MyTagCategory" | Set-TagCategory -Name "MyNewCategoryName" -Description "Update MyTagCategory description"
```
_Retrieves a tag category named "MyTagCategory" and updates its name and description._

```powershell
$myTagCategory = Get-TagCategory "MyTagCategory"
Set-TagCategory -Category $myTagCategory -Cardinality Multiple -AddEntityType "VirtualMachine"
```
_Retrieves a tag category named "MyTagCategory" and updates it by allowing more than one of its tags to be assigned to a specific object at a time, as well as adding "VirtualMachine" to the set of applicable entity types._

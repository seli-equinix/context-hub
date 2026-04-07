---
name: powercli-templates
description: "VMware PowerCLI 13.3 — VM template management — create templates, deploy from templates"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,templates,Get-Template, Move-Template, New-Template, Remove-Template, Set-Template"
---

# VMware PowerCLI — Templates

VM template management — create templates, deploy from templates. Module: VMware.VimAutomation (5 cmdlets).

## Get

### `Get-Template`

**This cmdlet retrieves the virtual machine templates available on a vCenter Server system.**

This cmdlet retrieves the virtual machine templates available on a vCenter Server system. The cmdlet returns a set of templates that correspond to the filter criteria defined by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Datastore [StorageResource[]] (Optional) Filters templates by the datastores or datastore clusters that they are stored on.
- -Id [String[]] (Required) Specifies the IDs of the virtual machine templates you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies the vSphere container objects (such as folders, datacenters, and VMHosts) you want to search for templates.
- -Name [String[]] (Optional) Specifies the names of the virtual machine templates you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-Template -Name Web* -Location Datacenter
```
_Retrieves all virtual machine templates in the Datacenter datacenter, whose names start with "Web"._

## Move

### `Move-Template`

**This cmdlet moves virtual machine templates to another location.**

This cmdlet moves virtual machine templates to a location that is specified by the Destination parameter.

**Parameters:**

- -Destination [VIContainer] (Required) Specifies a container object where you want to move the templates.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Template [Template[]] (Required) Specifies the virtual machine templates you want to move to another location.

**Examples:**

```powershell
Move-Template -Template $template -Destination $dest
```
_Moves the $template object into the $dest container object._

## New

### `New-Template`

**This cmdlet creates a new virtual machine template.**

This cmdlet creates a new template based on the specified virtual machine. You can also create a new template by cloning an existing one. You can also register an existing template to the vCenter Server inventory.

**Parameters:**

- -Datastore [StorageResource] (Optional) Specifies the datastore or the datastore cluster where you want to store the new template.
- -DiskStorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the disk storage format of the new template. This parameter accepts Thin, Thick, and EagerZeroedThick values.
- -Location [VIContainer] (Required) Specifies the location where you want to place the new template.
- -Name [String] (Required) Specifies a name for the new template.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Template [Template] (Required) Specifies a template you want to clone.
- -TemplateFilePath [String] (Required) Specifies the datastore path to the file you want to use to register the new template.
- -VM [VirtualMachine] (Required) Specifies the virtual machine from which you want to create the new template.
- -VMHost [VMHost] (Required) Specifies the host where you want to create the new template.

**Examples:**

```powershell
$myVM = Get-VM -Name "MyVM1"
$drsCluster=Get-DatastoreCluster "MyDatastoreCluster"
New-Template -VM $myVM -Name "MyTemplate" -Datastore $drsCluster -Location Datacenter2
```
_Creates a template named MyTemplate from the MyVM1 virtual machine and stores it in the MyDatastoreCluster datastore cluster in the Datacenter2 datacenter._

```powershell
$myFolder = Get-Folder -Name "MyFolder1"
New-Template -Name "MyTemplate1" -TemplateFilePath "[Storage1] templatefolder/template.vmtx" -Location $myFolder -VMHost (Get-VMHost)
```
_Registers the existing MyTemplate1 template to a vCenter Server inventory folder by using the specified template file._

```powershell
$myTemplate = Get-Template -Name "MyTemplate1"
$myDs = Get-Datastore -Name "MyDatastore1"
New-Template -Template $myTemplate -Name "MyTemplate2" -Datastore $myDs -Location "Datacenter2"
```
_Creates the MyTemplate2 template by cloning an existing template and stores the new template in the specified datastore in the Datacenter2 datacenter._

## Remove

### `Remove-Template`

**This cmdlet removes the specified virtual machine templates from the inventory.**

This cmdlet removes the specified virtual machine templates from the inventory. If the value of the DeletePermanently parameter is  $true, the cmdlet removes the templates from the inventory and deletes them from the disk.

**Parameters:**

- -DeletePermanently [SwitchParameter] (Optional) Indicates that you want to delete the templates not only from the inventory, but from the datastore as well.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Template [Template[]] (Required) Specifies the virtual machine templates you want to remove.

**Examples:**

```powershell
Remove-Template -Template $template
```
_Removes the virtual machine template saved in the $template variable._

## Set

### `Set-Template`

**This cmdlet modifies the specified virtual machine template.**

This cmdlet changes the name and the description of a virtual machine template according to the provided parameters. The cmdlet can convert the template to a virtual machine if the value of the ToVM parameter is $true.

**Parameters:**

- -Name [String] (Optional) Specifies a new name for the template.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Template [Template[]] (Required) Specifies the template whose properties you want to change.
- -ToVM [SwitchParameter] (Optional) Indicates that the template is to be converted to a virtual machine.

**Examples:**

```powershell
Set-Template -Template $template -Name Template2
```
_Renames the template saved in the $template variable to Template2._

```powershell
$vm = Set-Template -Template $template -ToVM
```
_Converts a template to a virtual machine._

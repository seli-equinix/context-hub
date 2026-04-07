---
name: powercli-templates
description: "VMware PowerCLI 13.3 — VM template creation, cloning, conversion, and management for standardized deployments"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,templates,golden-image,clone,Get-Template,New-Template,Set-Template,Move-Template,Remove-Template"
---

# VMware PowerCLI — Templates

## Golden Rule

**Templates are read-only golden images. Convert a VM to a template when it is fully patched and configured. Deploy new VMs from templates with `New-VM -Template`. Never run templates as VMs -- convert back temporarily with `Set-Template -ToVM` only for updates.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| Find templates | `Get-Template` | Listing available golden images | Supports wildcards and location filtering |
| VM -> Template | `New-Template -VM` | Freezing a configured VM as a golden image | VM is powered off and converted; it disappears from VM inventory |
| Clone template | `New-Template -Template` | Copying a template to another datastore/DC | Creates an independent copy |
| Register template | `New-Template -TemplateFilePath` | Importing a .vmtx file already on a datastore | For disaster recovery or migration |
| Template -> VM | `Set-Template -ToVM` | Updating the template (patching, agent install) | Convert back to template after changes |
| Deploy from template | `New-VM -Template` | Creating new VMs from the golden image | Use with `-OSCustomizationSpec` for unique identity |
| Organize templates | `Move-Template` | Moving to appropriate folder | Templates use VM folders for organization |
| Delete template | `Remove-Template` | Decommissioning old images | `-DeletePermanently` also removes disk files |

## Scenario: Template Lifecycle -- Create, Update, Deploy

```powershell
# Step 1: Build a VM, patch it, configure it, then convert to template
$vm = Get-VM "ubuntu-22.04-build" -Server $vcenter
Stop-VMGuest -VM $vm -Confirm:$false
do { Start-Sleep 5 } while ((Get-VM $vm.Name).PowerState -ne "PoweredOff")

New-Template -VM $vm -Name "ubuntu-22.04-$(Get-Date -Format 'yyyyMM')" `
    -Location (Get-Datacenter "US-East") `
    -Datastore (Get-Datastore "VMFS-Templates") -Server $vcenter

# Step 2: Deploy VMs from the template
$template = Get-Template "ubuntu-22.04-*" -Server $vcenter | Sort-Object Name -Descending | Select-Object -First 1
$spec = Get-OSCustomizationSpec "linux-prod" -Server $vcenter
$cluster = Get-Cluster "Production" -Server $vcenter
$ds = Get-Datastore "VMFS-Prod-01" -Server $vcenter

New-VM -Name "web-prod-10" -Template $template `
    -OSCustomizationSpec $spec -ResourcePool $cluster `
    -Datastore $ds -Location (Get-Folder "Web Servers") -Server $vcenter

Start-VM "web-prod-10" -Server $vcenter
Wait-Tools -VM (Get-VM "web-prod-10") -TimeoutSeconds 300

# Step 3: Monthly update -- convert template back to VM, patch, re-seal
$template = Get-Template "ubuntu-22.04-202604" -Server $vcenter
$updateVM = Set-Template -Template $template -ToVM  # Returns a VM object

Start-VM -VM $updateVM
Wait-Tools -VM $updateVM -TimeoutSeconds 300

# Apply patches inside the guest
Invoke-VMScript -VM $updateVM -ScriptType Bash `
    -ScriptText "apt-get update && apt-get upgrade -y && apt-get clean" `
    -GuestCredential $cred -Confirm:$false

Stop-VMGuest -VM $updateVM -Confirm:$false
do { Start-Sleep 5 } while ((Get-VM $updateVM.Name).PowerState -ne "PoweredOff")

# Convert back to template
Set-VM -VM $updateVM -ToTemplate -Name "ubuntu-22.04-$(Get-Date -Format 'yyyyMM')" -Confirm:$false
```

## Scenario: Clone Template to Another Datacenter

```powershell
# Clone an existing template to a different datacenter/datastore
$srcTemplate = Get-Template "rhel9-base" -Server $vcenter
$targetDS = Get-Datastore "VMFS-DR-01" -Server $vcenter
$targetDC = Get-Datacenter "US-West" -Server $vcenter
$targetHost = Get-VMHost "esxi-dr01.example.com" -Server $vcenter

New-Template -Template $srcTemplate -Name "rhel9-base" `
    -Datastore $targetDS -Location $targetDC -VMHost $targetHost `
    -DiskStorageFormat Thin -Server $vcenter
```

## Common Mistakes

### Mistake 1: Forgetting to Convert Back to Template After Updates

```powershell
# WRONG -- Convert template to VM for patching, forget to convert back
$vm = Set-Template -Template $template -ToVM
# ... apply patches ...
# Oops, forgot to convert back. Now VMs deploy from a RUNNING VM, not a template.
# Other admins may accidentally modify or power on the "template" VM.

# CORRECT -- Always convert back after updates
Stop-VMGuest -VM $vm -Confirm:$false
do { Start-Sleep 5 } while ((Get-VM $vm.Name).PowerState -ne "PoweredOff")
Set-VM -VM $vm -ToTemplate -Confirm:$false
```

### Mistake 2: Deleting Template Without -DeletePermanently

```powershell
# WRONG -- Removes from inventory but VMDK files remain on datastore (orphaned)
Remove-Template -Template $template -Confirm:$false

# CORRECT -- Remove from inventory AND delete disk files
Remove-Template -Template $template -DeletePermanently -Confirm:$false
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-Template` | Find templates | `-Name`, `-Location`, `-Datastore`, `-Server`, `-NoRecursion` |
| `New-Template` | Create from VM | `-VM`, `-Name`, `-Location`, `-Datastore`, `-DiskStorageFormat` |
| `New-Template` | Clone template | `-Template` (source), `-Name`, `-Datastore`, `-Location`, `-VMHost` |
| `New-Template` | Register .vmtx | `-TemplateFilePath`, `-Name`, `-Location`, `-VMHost` |
| `Set-Template` | Rename template | `-Template`, `-Name` |
| `Set-Template` | Convert to VM | `-Template`, `-ToVM` -- returns a VirtualMachine object |
| `Move-Template` | Move to folder | `-Template`, `-Destination` |
| `Remove-Template` | Delete template | `-Template`, `-DeletePermanently` (also removes VMDK files) |

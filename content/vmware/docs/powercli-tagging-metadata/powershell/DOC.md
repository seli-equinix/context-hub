---
name: powercli-tagging-metadata
description: "VMware PowerCLI 13.3 — Tags, tag categories, custom attributes, annotations for inventory classification and automation"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,tagging,metadata,tags,categories,custom-attributes,annotations,Get-Tag,New-Tag,Set-Tag,Remove-Tag,Get-TagAssignment,New-TagAssignment,Remove-TagAssignment,Get-TagCategory,New-TagCategory,Set-TagCategory,Remove-TagCategory,Get-CustomAttribute,New-CustomAttribute,Set-CustomAttribute,Remove-CustomAttribute,Get-Annotation,Set-Annotation"
---

# VMware PowerCLI — Tagging & Metadata

## Golden Rule

**Tags are for automation and policy. Custom attributes are for human-readable notes. Use tags when you need to filter, scope alarms, apply storage policies, or drive scripts. Use custom attributes when you need free-form text per object.**

| Feature | Tags | Custom Attributes |
|---------|------|-------------------|
| Scope | Category-controlled (VM, Host, Datastore, etc.) | Target type (VM, Host, Cluster, etc.) or Global |
| Cardinality | Single or Multiple per category | One value per attribute per object |
| Used by | Storage policies, DRS, alarms, `Get-VM -Tag` | `Get-Annotation` -- reporting, notes |
| Structure | Category + Tag (hierarchical) | Flat key-value |
| Best for | Automation: "Environment=Production" | Documentation: "Owner=jsmith", "Notes=migrated 2024-03" |

**Key decisions:**
1. Design tag categories BEFORE creating tags -- changing cardinality from Single to Multiple is one-way
2. Use `-EntityType` to restrict which object types a category applies to
3. Tags propagate through `Get-VM -Tag` filtering -- custom attributes do not

## Scenario: Build a Tagging Taxonomy for Automation

```powershell
# Create categories with enforced cardinality
New-TagCategory -Name "Environment" -Cardinality Single `
    -EntityType "VirtualMachine", "VMHost" -Description "Deployment environment" -Server $vcenter

New-TagCategory -Name "Application" -Cardinality Multiple `
    -EntityType "VirtualMachine" -Description "Application stack membership" -Server $vcenter

New-TagCategory -Name "BackupPolicy" -Cardinality Single `
    -EntityType "VirtualMachine", "Datastore" -Description "Backup SLA tier" -Server $vcenter

# Create tags within each category
$envCat = Get-TagCategory "Environment" -Server $vcenter
@("Production", "Staging", "Development", "DR") | ForEach-Object {
    New-Tag -Name $_ -Category $envCat -Server $vcenter
}

$backupCat = Get-TagCategory "BackupPolicy" -Server $vcenter
@("Gold-4hr", "Silver-24hr", "Bronze-Weekly", "None") | ForEach-Object {
    New-Tag -Name $_ -Category $backupCat -Server $vcenter
}

# Assign tags to VMs
$prodTag = Get-Tag -Name "Production" -Category "Environment" -Server $vcenter
$goldBackup = Get-Tag -Name "Gold-4hr" -Category "BackupPolicy" -Server $vcenter

Get-VM -Name "prod-*" -Server $vcenter | ForEach-Object {
    New-TagAssignment -Entity $_ -Tag $prodTag -Server $vcenter
    New-TagAssignment -Entity $_ -Tag $goldBackup -Server $vcenter
}

# Query VMs by tag -- the primary automation use case
Get-VM -Tag "Production" -Server $vcenter | Select-Object Name, PowerState, NumCpu, MemoryGB
```

## Scenario: Custom Attributes for Operational Metadata

```powershell
# Create custom attributes for operational tracking
New-CustomAttribute -Name "Owner" -TargetType VirtualMachine -Server $vcenter
New-CustomAttribute -Name "CostCenter" -TargetType VirtualMachine -Server $vcenter
New-CustomAttribute -Name "DecommissionDate" -TargetType VirtualMachine -Server $vcenter

# Set annotations (values) on VMs
$vm = Get-VM -Name "web-01" -Server $vcenter
Set-Annotation -Entity $vm -CustomAttribute "Owner" -Value "jsmith@company.com"
Set-Annotation -Entity $vm -CustomAttribute "CostCenter" -Value "IT-4200"
Set-Annotation -Entity $vm -CustomAttribute "DecommissionDate" -Value "2025-12-31"

# Bulk report: find VMs with no owner annotation
Get-VM -Server $vcenter | ForEach-Object {
    $owner = (Get-Annotation -Entity $_ -CustomAttribute "Owner" -Server $vcenter).Value
    if ([string]::IsNullOrWhiteSpace($owner)) {
        [PSCustomObject]@{
            VM        = $_.Name
            PowerState = $_.PowerState
            Created   = $_.ExtensionData.Config.CreateDate
        }
    }
} | Format-Table -AutoSize
```

## Scenario: Audit and Clean Up Stale Tags

```powershell
# List all tag assignments across the environment
Get-TagAssignment -Server $vcenter |
    Select-Object @{N='Object';E={$_.Entity.Name}},
        @{N='ObjectType';E={$_.Entity.GetType().Name}},
        @{N='Tag';E={$_.Tag.Name}},
        @{N='Category';E={$_.Tag.Category.Name}} |
    Sort-Object Category, Tag | Format-Table

# Find tags that are assigned to nothing (candidates for removal)
Get-Tag -Server $vcenter | ForEach-Object {
    $assignments = Get-TagAssignment -Tag $_ -Server $vcenter
    if ($assignments.Count -eq 0) {
        [PSCustomObject]@{ Tag = $_.Name; Category = $_.Category.Name; Assignments = 0 }
    }
} | Format-Table
```

## Common Mistakes

### Mistake 1: Creating a Single-Cardinality Category When You Need Multiple

```powershell
# WRONG -- Single cardinality: VM can only have ONE application tag
New-TagCategory -Name "Application" -Cardinality Single -EntityType "VirtualMachine"
# A VM running both "WebServer" and "Database" can only be tagged with one!

# CORRECT -- Multiple cardinality for multi-membership categories
New-TagCategory -Name "Application" -Cardinality Multiple -EntityType "VirtualMachine"
# Now the VM can have both "WebServer" and "Database" tags
```

NOTE: You can change cardinality from Single to Multiple, but NEVER from Multiple back to Single.

### Mistake 2: Using Tags for Free-Form Data

```powershell
# WRONG -- Creating a unique tag per VM for tracking
New-Tag -Name "Owner-jsmith" -Category "Ownership"
New-Tag -Name "Owner-bjones" -Category "Ownership"
# Hundreds of tags, impossible to manage

# CORRECT -- Use custom attributes for per-object values
New-CustomAttribute -Name "Owner" -TargetType VirtualMachine
Set-Annotation -Entity $vm -CustomAttribute "Owner" -Value "jsmith@company.com"
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-TagCategory` | List categories | `-Name`, `-Server` |
| `New-TagCategory` | Create category | `-Name`, `-Cardinality` (Single/Multiple), `-EntityType`, `-Description` |
| `Set-TagCategory` | Modify category | `-Cardinality` (only Single->Multiple), `-AddEntityType`, `-Name` |
| `Remove-TagCategory` | Delete category | `-Category` -- also removes all tags in the category |
| `Get-Tag` | List tags | `-Name`, `-Category`, `-Server` |
| `New-Tag` | Create tag | `-Name`, `-Category` (required), `-Description` |
| `Set-Tag` | Rename/describe tag | `-Name`, `-Description` |
| `Remove-Tag` | Delete tag | `-Tag` -- also removes all assignments of this tag |
| `Get-TagAssignment` | List assignments | `-Entity`, `-Tag`, `-Category` |
| `New-TagAssignment` | Assign tag | `-Entity`, `-Tag` |
| `Remove-TagAssignment` | Unassign tag | `-TagAssignment` |
| `Get-CustomAttribute` | List attributes | `-Name`, `-TargetType`, `-Global` |
| `New-CustomAttribute` | Create attribute | `-Name`, `-TargetType` (VirtualMachine/VMHost/Cluster/etc.) |
| `Set-CustomAttribute` | Rename attribute | `-CustomAttribute`, `-Name` |
| `Remove-CustomAttribute` | Delete attribute | `-CustomAttribute` |
| `Get-Annotation` | Read attribute value | `-Entity`, `-CustomAttribute`, `-Name` |
| `Set-Annotation` | Set attribute value | `-Entity`, `-CustomAttribute`, `-Value` |

---
name: powercli-content-library
description: "VMware PowerCLI 13.3 — Content libraries, library items, OVF/OVA import and export, template distribution"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,content-library,ovf,ova,template,Get-ContentLibrary,New-ContentLibrary,Set-ContentLibrary,Remove-ContentLibrary,Get-ContentLibraryItem,New-ContentLibraryItem,Set-ContentLibraryItem,Remove-ContentLibraryItem,Copy-ContentLibraryItem,Export-ContentLibraryItem,Get-OvfConfiguration,Import-VApp,Export-VApp"
---

# VMware PowerCLI — Content Library

## Golden Rule

**Content Libraries are the standard way to distribute templates, ISOs, and OVF packages across vCenters. Use LOCAL libraries for authoring, SUBSCRIBED libraries for consumption. Never deploy from raw OVF files when a content library exists.**

| Library Type | Purpose | Use When |
|-------------|---------|----------|
| **Local** | Author and store templates, ISOs, scripts | You are the source of truth for golden images |
| **Subscribed** | Consume from a published local library | Remote sites need the same templates |
| **Published** | Local library that exposes a subscription URL | Multi-site template distribution |

| Task | Cmdlet | Use When |
|------|--------|----------|
| Deploy VM from library OVF | `New-VM -ContentLibraryItem` | Standard deployment from a curated template |
| Import external OVF/OVA | `Import-VApp` | One-time import of vendor appliance |
| Export VM to OVF | `Export-VApp` | Backup or transfer a VM/vApp as a portable package |
| Capture VM to library | `New-ContentLibraryItem -VM` | Save a configured VM as a reusable library template |

## Scenario: Create a Library and Publish Templates Across Sites

```powershell
# Create a local content library on the primary vCenter
$ds = Get-Datastore "VMFS-Templates" -Server $vcenter
New-ContentLibrary -Name "Golden-Images" -Datastore $ds `
    -Published -Description "Enterprise approved OS templates" -Server $vcenter

# Capture a running VM as an OVF template in the library
$vm = Get-VM -Name "ubuntu-22.04-golden" -Server $vcenter
$lib = Get-ContentLibrary -Name "Golden-Images" -Local -Server $vcenter
New-ContentLibraryItem -ContentLibrary $lib -Name "Ubuntu-22.04-Base" `
    -VM $vm -Notes "Base Ubuntu 22.04 - patched $(Get-Date -Format 'yyyy-MM')"

# At a remote site: subscribe to the published library
$remoteDS = Get-Datastore "VMFS-Templates" -Server $remoteVcenter
$pubUrl = (Get-ContentLibrary "Golden-Images" -Local -Server $vcenter).PublishUrl
New-ContentLibrary -Name "Golden-Images" -Datastore $remoteDS `
    -SubscriptionUrl $pubUrl -AutomaticSync -Server $remoteVcenter

# Force a manual sync of the subscribed library
$subLib = Get-ContentLibrary "Golden-Images" -Subscribed -Server $remoteVcenter
Set-ContentLibrary -SubscribedContentLibrary $subLib -Sync
```

## Scenario: Deploy VM from Content Library Item

```powershell
# Find the template in the library
$item = Get-ContentLibraryItem -Name "Ubuntu-22.04-Base" -Server $vcenter

# Check if OVF configuration is needed (network mapping, EULA, etc.)
$target = Get-Cluster "Production" -Server $vcenter
$ovfConfig = Get-OvfConfiguration -ContentLibraryItem $item -Target $target
# If $ovfConfig has properties, set them:
# $ovfConfig.NetworkMapping.VM_Network.Value = "VLAN-100-Web"

# Deploy
$ds = Get-Datastore "VMFS-Prod-01" -Server $vcenter
$vmhost = Get-VMHost "esxi01.example.com" -Server $vcenter
New-VM -Name "web-prod-06" -ContentLibraryItem $item `
    -VMHost $vmhost -Datastore $ds `
    -Location (Get-Folder "Web Servers") -Server $vcenter

# For vendor appliances with OVF properties (vCSA, NSX, etc.)
$item = Get-ContentLibraryItem -Name "NSX-Manager-4.1" -Server $vcenter
$ovfConfig = Get-OvfConfiguration -ContentLibraryItem $item -Target $target
$ovfConfig.Common.nsx_hostname.Value = "nsx-mgr.example.com"
$ovfConfig.Common.nsx_ip_0.Value = "10.0.0.20"
$ovfConfig.NetworkMapping.Network_1.Value = "VLAN-400-Mgmt"
New-VM -Name "nsx-mgr" -ContentLibraryItem $item `
    -OvfConfiguration $ovfConfig -VMHost $vmhost -Datastore $ds -Server $vcenter
```

## Scenario: Import OVA and Export VM for Portability

```powershell
# Import a vendor OVA appliance
$vmhost = Get-VMHost "esxi01.example.com" -Server $vcenter
$ds = Get-Datastore "VMFS-Prod-01" -Server $vcenter
$ovfConfig = Get-OvfConfiguration -Ovf "C:\Appliances\vendor-app.ova"
$ovfConfig.NetworkMapping.VM_Network.Value = "VLAN-200-App"
Import-VApp -Source "C:\Appliances\vendor-app.ova" `
    -OvfConfiguration $ovfConfig -VMHost $vmhost -Datastore $ds `
    -Name "vendor-app-prod" -DiskStorageFormat Thin -Server $vcenter

# Export a VM as OVA for backup or migration
$vm = Get-VM "web-prod-01" -Server $vcenter
Export-VApp -VM $vm -Destination "C:\Exports\" -Format OVA `
    -Name "web-prod-01-backup" -Force

# Export a vApp (multi-VM application)
$vapp = Get-VApp "MyWebApp" -Server $vcenter
Export-VApp -VApp $vapp -Destination "C:\Exports\" -Format OVF `
    -CreateSeparateFolder -Force
```

## Common Mistakes

### Mistake 1: Deploying from OVF Without Checking OvfConfiguration

```powershell
# WRONG -- Import OVA without setting network mapping
Import-VApp -Source "appliance.ova" -VMHost $vmhost -Datastore $ds
# VM deploys but NICs are connected to default "VM Network" which may not exist

# CORRECT -- Always check and set OVF properties
$ovfConfig = Get-OvfConfiguration -Ovf "appliance.ova"
$ovfConfig.NetworkMapping.VM_Network.Value = "VLAN-200-App"
Import-VApp -Source "appliance.ova" -VMHost $vmhost -Datastore $ds `
    -OvfConfiguration $ovfConfig -Name "appliance-prod"
```

### Mistake 2: Not Using -Local or -Subscribed Filters

```powershell
# WRONG -- Ambiguous: returns both local and subscribed libraries with the same name
$lib = Get-ContentLibrary -Name "Golden-Images"
# If both exist, you might publish to the subscribed copy (which fails)

# CORRECT -- Always specify the type
$localLib = Get-ContentLibrary -Name "Golden-Images" -Local -Server $vcenter
$subLib = Get-ContentLibrary -Name "Golden-Images" -Subscribed -Server $remoteVcenter
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-ContentLibrary` | List libraries | `-Name`, `-Local`, `-Subscribed`, `-Server` |
| `New-ContentLibrary` | Create library | `-Name`, `-Datastore`, `-Published`, `-SubscriptionUrl`, `-AutomaticSync` |
| `Set-ContentLibrary` | Modify/sync library | `-Sync` (trigger sync), `-Name`, `-Description`, `-Evict` |
| `Remove-ContentLibrary` | Delete library | `-ContentLibrary` |
| `Get-ContentLibraryItem` | List items | `-Name`, `-ContentLibrary`, `-ItemType` |
| `New-ContentLibraryItem` | Create item | `-ContentLibrary`, `-Name`, `-VM` (capture), `-Files`, `-Uri` |
| `Set-ContentLibraryItem` | Update item | `-ContentLibraryItem`, `-Name`, `-Files`, `-VM` (overwrite) |
| `Remove-ContentLibraryItem` | Delete item | `-ContentLibraryItem` |
| `Copy-ContentLibraryItem` | Copy to another library | `-ContentLibraryItem`, `-Destination` (local library) |
| `Export-ContentLibraryItem` | Download files locally | `-ContentLibraryItem`, `-Destination`, `-Force` |
| `Get-OvfConfiguration` | Get OVF properties | `-Ovf` (file path) or `-ContentLibraryItem`, `-Target` |
| `Import-VApp` | Import OVF/OVA | `-Source`, `-VMHost`, `-Datastore`, `-OvfConfiguration`, `-Name`, `-DiskStorageFormat` |
| `Export-VApp` | Export VM/vApp | `-VM` or `-VApp`, `-Destination`, `-Format` (OVF/OVA), `-Force` |

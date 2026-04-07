---
name: powercli-lifecycle
description: "VMware PowerCLI 13.3 — vSphere Lifecycle Manager (LCM) images, offline depots, and VMware Tools updates for host and VM patching"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,lifecycle,lcm,patching,vmware-tools,update,firmware,Get-LcmImage,New-LcmOfflineDepot,Update-Tools"
---

# VMware PowerCLI — Lifecycle Management

## Golden Rule

**vSphere Lifecycle Manager (LCM) manages ESXi host images and firmware. `Get-LcmImage` and `New-LcmOfflineDepot` handle the IMAGE side (what version of ESXi hosts should run). `Update-Tools` handles the GUEST side (VMware Tools inside VMs). They are different workflows.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| Find available ESXi images | `Get-LcmImage` | Checking what base images and vendor add-ons exist | Filter by `-Type` (BaseImage, VendorAddOn, Component, etc.) |
| Import offline depot | `New-LcmOfflineDepot` | Air-gapped environments without internet access | Accepts file:// or http:// URIs |
| Update VMware Tools in VMs | `Update-Tools` | Keeping Tools current for guest integration | VM must be powered on; may reboot the guest |

**LCM image-based patching flow:**
1. `Get-LcmImage` -- discover available base images and vendor add-ons
2. Configure cluster desired state in vCenter (GUI or API)
3. `Test-LcmClusterCompliance` -- check if hosts match desired state
4. `Test-LcmClusterHealth` -- pre-check before remediation
5. Remediate via vCenter (puts hosts in maintenance mode one by one)

## Scenario: Discover Available Images and Check Compliance

```powershell
# List all available ESXi base images
Get-LcmImage -Type BaseImage -Server $vcenter |
    Select-Object Name, Version, ReleaseDate |
    Sort-Object Version -Descending | Format-Table

# Find vendor add-ons (Dell, HPE, etc.) that are bug fixes or enhancements
Get-LcmImage -Type VendorAddOn -Category @('Bugfix', 'Enhancement') -Server $vcenter |
    Select-Object Name, Version, Vendor, Category | Format-Table

# Check cluster compliance against the desired image
$cluster = Get-Cluster "Production" -Server $vcenter
Test-LcmClusterCompliance -Cluster $cluster -Server $vcenter

# Pre-remediation health check
Test-LcmClusterHealth -Cluster $cluster -Server $vcenter
```

## Scenario: VMware Tools Update Across a Cluster

```powershell
# Find VMs with outdated VMware Tools
$cluster = Get-Cluster "Production" -Server $vcenter
Get-VM -Location $cluster -Server $vcenter | Where-Object {
    $_.PowerState -eq "PoweredOn" -and
    $_.ExtensionData.Guest.ToolsVersionStatus -ne "guestToolsCurrent"
} | Select-Object Name, @{N='ToolsStatus';E={$_.ExtensionData.Guest.ToolsVersionStatus}},
    @{N='ToolsVersion';E={$_.ExtensionData.Guest.ToolsVersion}} |
    Format-Table

# Update Tools on specific VMs (with reboot suppression for Windows)
$vmsToUpdate = Get-VM -Name "web-*" -Server $vcenter | Where-Object {
    $_.PowerState -eq "PoweredOn"
}
$vmsToUpdate | Update-Tools -NoReboot -RunAsync -Server $vcenter

# Monitor update tasks
Get-Task -Server $vcenter |
    Where-Object { $_.Name -eq "UpgradeTools_Task" -and $_.State -eq "Running" } |
    Select-Object @{N='VM';E={$_.ObjectId}}, PercentComplete | Format-Table
```

## Common Mistakes

### Mistake 1: Running Update-Tools on Powered-Off VMs

```powershell
# WRONG -- Tools update requires the VM to be running
Update-Tools -VM (Get-VM "offline-server")
# Error: VM must be powered on

# CORRECT -- Filter to powered-on VMs only
Get-VM -Name "prod-*" -Server $vcenter |
    Where-Object { $_.PowerState -eq "PoweredOn" } |
    Update-Tools -NoReboot -RunAsync
```

### Mistake 2: Not Using -NoReboot on Windows Production VMs

```powershell
# WRONG -- Tools update reboots the Windows VM during business hours
Update-Tools -VM $windowsVM
# Guest OS reboots immediately after Tools upgrade

# CORRECT -- Suppress reboot, schedule restart during maintenance window
Update-Tools -VM $windowsVM -NoReboot
# Note: -NoReboot only works for Windows; Linux VMs may still reboot
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-LcmImage` | List LCM images | `-Type` (BaseImage/VendorAddOn/Component), `-Name`, `-Version`, `-Category` |
| `New-LcmOfflineDepot` | Import offline depot | `-Location` (URI), `-Description`, `-OwnerData`, `-RunAsync` |
| `Update-Tools` | Upgrade VMware Tools | `-VM`, `-Guest`, `-NoReboot` (Windows only), `-RunAsync` |

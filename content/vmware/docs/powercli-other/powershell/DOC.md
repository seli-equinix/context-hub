---
name: powercli-other
description: "VMware PowerCLI 13.3 — Advanced settings, virtual hardware (CD/floppy/SCSI/USB/passthrough), VMware Tools, VAIO filters, VASA providers, and CIS API access"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,advanced-settings,virtual-hardware,vmware-tools,vaio,vasa,cis,Get-AdvancedSetting,New-AdvancedSetting,Set-AdvancedSetting,Remove-AdvancedSetting,Get-CDDrive,New-CDDrive,Set-CDDrive,Remove-CDDrive,Get-FloppyDrive,New-FloppyDrive,Set-FloppyDrive,Remove-FloppyDrive,Get-ScsiController,New-ScsiController,Set-ScsiController,Get-ScsiLun,Set-ScsiLun,Get-ScsiLunPath,Set-ScsiLunPath,Get-PassthroughDevice,Add-PassthroughDevice,Remove-PassthroughDevice,Get-UsbDevice,Remove-UsbDevice,Get-Snapshot,New-Snapshot,Set-Snapshot,Remove-Snapshot,Get-NetworkAdapter,New-NetworkAdapter,Set-NetworkAdapter,Remove-NetworkAdapter,Mount-Tools,Dismount-Tools,Wait-Tools,Get-VAIOFilter,New-VAIOFilter,Set-VAIOFilter,Remove-VAIOFilter,Get-VasaProvider,New-VasaProvider,Remove-VasaProvider,Get-VApp,New-VApp,Set-VApp,Remove-VApp,Start-VApp,Stop-VApp,Move-VApp,Get-CisService,Get-CisCommand,Get-VDBlockedPolicy,Set-VDBlockedPolicy,Get-VDUplinkTeamingPolicy,Set-VDUplinkTeamingPolicy,Get-VDUplinkLacpPolicy,Set-VDUplinkLacpPolicy,Set-VDVlanConfiguration,New-CnsKubernetesEntityMetadata,New-CnsKubernetesEntityReference"
---

# VMware PowerCLI — Other Cmdlets

This package contains miscellaneous cmdlets that span multiple domains: advanced settings, virtual hardware devices, VMware Tools management, VAIO filters, VASA providers, and the CIS REST API wrapper. These are supporting cmdlets used alongside the primary packages.

## Golden Rule

**Advanced settings are the escape hatch for configurations not exposed through standard cmdlets. Virtual hardware cmdlets manage the devices attached to VMs. The CIS service cmdlets provide raw REST API access to vCenter when PowerCLI cmdlets do not exist for a feature.**

| Category | Key Cmdlets | Use When |
|----------|-------------|----------|
| **Advanced Settings** | `Get/Set/New/Remove-AdvancedSetting` | Tuning ESXi, vCenter, or VM behavior beyond standard parameters |
| **CD/DVD Drives** | `Get/Set/New/Remove-CDDrive` | Mounting ISOs for OS install or patching |
| **SCSI Controllers** | `Get/Set/New-ScsiController`, `Get/Set-ScsiLun` | Adding storage controllers, multipathing |
| **Passthrough Devices** | `Get/Add/Remove-PassthroughDevice` | GPU passthrough, USB passthrough |
| **VMware Tools** | `Mount-Tools`, `Dismount-Tools`, `Wait-Tools` | Installing or updating Tools in guest |
| **VAIO Filters** | `Get/Set/New/Remove-VAIOFilter` | I/O filter management (encryption, caching, replication) |
| **VASA Providers** | `Get/New/Remove-VasaProvider` | Registering storage array providers for SPBM |
| **CIS API** | `Get-CisService`, `Get-CisCommand` | Direct REST API calls to vCenter services |

## Scenario: Advanced Settings for Security Hardening

```powershell
# Check all advanced settings on a host matching a pattern
$vmhost = Get-VMHost "esxi01.example.com" -Server $vcenter
Get-AdvancedSetting -Entity $vmhost -Name "UserVars.ESXiShell*" |
    Select-Object Name, Value | Format-Table

# Disable ESXi Shell timeout (security hardening)
Get-AdvancedSetting -Entity $vmhost -Name "UserVars.ESXiShellTimeOut" |
    Set-AdvancedSetting -Value 900 -Confirm:$false  # 15 minutes

# Set SMTP configuration on vCenter
$viServer = $global:DefaultVIServer
Get-AdvancedSetting -Entity $viServer -Name "*smtp*" | Format-Table Name, Value
Set-AdvancedSetting -Entity $viServer -Name "mail.smtp.server" -Value "smtp.example.com" -Confirm:$false

# VM-level advanced settings (e.g., disable copy-paste for security)
$vm = Get-VM "secure-vm" -Server $vcenter
New-AdvancedSetting -Entity $vm -Name "isolation.tools.copy.disable" -Value "TRUE" -Confirm:$false
New-AdvancedSetting -Entity $vm -Name "isolation.tools.paste.disable" -Value "TRUE" -Confirm:$false

# Bulk audit: find VMs with non-default advanced settings
Get-VM -Server $vcenter | ForEach-Object {
    $settings = Get-AdvancedSetting -Entity $_ | Where-Object { $_.Name -match "isolation" }
    if ($settings) {
        [PSCustomObject]@{
            VM = $_.Name
            Settings = ($settings | ForEach-Object { "$($_.Name)=$($_.Value)" }) -join "; "
        }
    }
} | Format-Table -Wrap
```

## Scenario: Mount ISO and Manage Virtual Hardware

```powershell
# Mount an ISO from a datastore to a VM's CD drive
$vm = Get-VM "new-server" -Server $vcenter
$cdDrive = Get-CDDrive -VM $vm
Set-CDDrive -CD $cdDrive -IsoPath "[VMFS-ISO-01] ISOs/rhel9-dvd.iso" `
    -Connected:$true -StartConnected:$true -Confirm:$false

# After OS install, disconnect the CD drive
Set-CDDrive -CD $cdDrive -NoMedia -Confirm:$false

# Mount VMware Tools installer ISO
Mount-Tools -VM $vm
# After Tools install completes:
Dismount-Tools -VM $vm

# Wait for VMware Tools to become available after VM boot
Start-VM -VM $vm
Wait-Tools -VM $vm -TimeoutSeconds 300

# Add a new SCSI controller (for additional disk buses)
New-ScsiController -HardDisk (Get-HardDisk -VM $vm | Select-Object -First 1) `
    -Type ParaVirtual -Confirm:$false

# Configure SCSI LUN multipathing
$lun = Get-ScsiLun -VMHost $vmhost -LunType Disk | Where-Object { $_.CanonicalName -match "naa.600" }
Set-ScsiLun -ScsiLun $lun -MultipathPolicy RoundRobin -Confirm:$false

# Check multipath status
Get-ScsiLunPath -ScsiLun $lun | Select-Object Name, State, Preferred, LunPath | Format-Table
```

## Scenario: CIS API for Features Without Native Cmdlets

```powershell
# List all available CIS (vCenter REST API) services
Get-CisService -Server $vcenter | Select-Object -First 20

# Access a specific CIS service (e.g., content library subscriptions)
$taggingSvc = Get-CisService -Name "com.vmware.cis.tagging.tag" -Server $vcenter
# List available operations
Get-CisCommand -CisService $taggingSvc | Select-Object Name, Description

# Register a VASA provider (storage array integration for SPBM)
New-VasaProvider -Name "PureStorage-Array1" `
    -Url "https://pure-mgmt.example.com:8443/version" `
    -Credential (Get-Credential) -Force -Server $vcenter

# List registered VASA providers
Get-VasaProvider -Server $vcenter | Select-Object Name, Url, Status | Format-Table
```

## Common Mistakes

### Mistake 1: Setting Advanced Settings on the Wrong Entity

```powershell
# WRONG -- Setting a host-level parameter on a VM
Set-AdvancedSetting -Entity $vm -Name "UserVars.ESXiShellTimeOut" -Value 900
# This creates a VM-level setting that does nothing

# CORRECT -- Target the right entity type
Set-AdvancedSetting -Entity $vmhost -Name "UserVars.ESXiShellTimeOut" -Value 900 -Confirm:$false
```

### Mistake 2: Forgetting to Disconnect CD Drive After Install

```powershell
# WRONG -- ISO stays mounted, VM tries to boot from CD on next restart
Set-CDDrive -CD $cdDrive -IsoPath "[VMFS-ISO-01] ISOs/rhel9.iso" -Connected:$true
# ... install OS, reboot ...
# VM boots into installer again instead of the OS

# CORRECT -- Disconnect and set StartConnected to false
Set-CDDrive -CD $cdDrive -NoMedia -StartConnected:$false -Confirm:$false
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| **Advanced Settings** | | |
| `Get-AdvancedSetting` | Read settings | `-Entity` (VM/Host/vCenter/Cluster), `-Name` (wildcards) |
| `New-AdvancedSetting` | Create setting | `-Entity`, `-Name`, `-Value` |
| `Set-AdvancedSetting` | Modify setting | `-AdvancedSetting`, `-Value` |
| `Remove-AdvancedSetting` | Delete setting | `-AdvancedSetting` |
| **CD/DVD Drives** | | |
| `Get-CDDrive` | List CD drives | `-VM` |
| `New-CDDrive` | Add CD drive | `-VM`, `-IsoPath` |
| `Set-CDDrive` | Mount/unmount ISO | `-IsoPath`, `-Connected`, `-NoMedia`, `-StartConnected` |
| `Remove-CDDrive` | Remove CD drive | `-CD` |
| **SCSI** | | |
| `Get-ScsiController` | List controllers | `-VM` |
| `New-ScsiController` | Add controller | `-HardDisk`, `-Type` (ParaVirtual/LSILogicSAS/etc.) |
| `Get-ScsiLun` | List LUNs | `-VMHost`, `-LunType` (Disk/Cdrom) |
| `Set-ScsiLun` | Set multipath | `-ScsiLun`, `-MultipathPolicy` (RoundRobin/Fixed/MRU) |
| `Get-ScsiLunPath` | List paths | `-ScsiLun` |
| `Set-ScsiLunPath` | Set path state | `-Active`, `-Preferred` |
| **Passthrough/USB** | | |
| `Get-PassthroughDevice` | List devices | `-VM` or `-VMHost`, `-Type` (Scsi/Pci) |
| `Add-PassthroughDevice` | Attach to VM | `-VM`, `-PassthroughDevice` |
| `Remove-PassthroughDevice` | Detach from VM | `-PassthroughDevice` |
| `Get-UsbDevice` | List USB | `-VM` |
| `Remove-UsbDevice` | Detach USB | `-UsbDevice` |
| **VMware Tools** | | |
| `Mount-Tools` | Mount Tools ISO | `-VM` |
| `Dismount-Tools` | Unmount Tools ISO | `-VM` |
| `Wait-Tools` | Wait for Tools ready | `-VM`, `-TimeoutSeconds` |
| **VAIO / VASA** | | |
| `Get-VAIOFilter` | List I/O filters | `-VM`, `-Datastore` |
| `New-VAIOFilter` | Create filter | `-VM`, `-Datastore`, `-Filter` |
| `Get-VasaProvider` | List VASA providers | `-Name`, `-Server` |
| `New-VasaProvider` | Register provider | `-Name`, `-Url`, `-Credential` |
| **CIS API** | | |
| `Get-CisService` | List REST services | `-Name`, `-Server` |
| `Get-CisCommand` | List service operations | `-CisService` |

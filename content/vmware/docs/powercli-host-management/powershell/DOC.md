---
name: powercli-host-management
description: "VMware PowerCLI 13.3 — ESXi host lifecycle: discovery, configuration, maintenance, networking, storage, patching, decommission. Covers Get-VMHost, Set-VMHost, Add-VMHost, Remove-VMHost, host services, firewall, NTP, syslog, networking adapters, storage HBAs, Get-EsxCli"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,host-management,esxi,maintenance-mode,ntp,dns,syslog,firewall,hba,iscsi,esxcli,Get-VMHost,Set-VMHost,Add-VMHost,Remove-VMHost,Move-VMHost,Restart-VMHost,Stop-VMHost,Start-VMHost,Suspend-VMHost,Get-VMHostService,Start-VMHostService,Stop-VMHostService,Restart-VMHostService,Get-VMHostFirewallDefaultPolicy,Set-VMHostFirewallDefaultPolicy,Get-VMHostFirewallException,Set-VMHostFirewallException,Get-VMHostNetworkAdapter,New-VMHostNetworkAdapter,Set-VMHostNetworkAdapter,Get-VMHostNetwork,Set-VMHostNetwork,Get-VMHostStorage,Set-VMHostStorage,Get-VMHostHba,Set-VMHostHba,Get-VMHostDisk,Get-VMHostDiskPartition,Format-VMHostDiskPartition,Get-VMHostNtpServer,Add-VMHostNtpServer,Remove-VMHostNtpServer,Get-VMHostPatch,Install-VMHostPatch,Get-VMHostProfile,Get-VMHostFirmware,Set-VMHostFirmware,Get-VMHostModule,Set-VMHostModule,Get-VMHostSnmp,Set-VMHostSnmp,Test-VMHostSnmp,Get-VMHostRoute,New-VMHostRoute,Remove-VMHostRoute,Get-VMHostAuthentication,Set-VMHostAuthentication,Get-VMHostHardware,Get-VMHostPciDevice,Get-VMHostAdvancedConfiguration,Set-VMHostAdvancedConfiguration,Get-VMHostDiagnosticPartition,Set-VMHostDiagnosticPartition,Get-VMHostSysLogServer,Set-VMHostSysLogServer,Get-VMHostStartPolicy,Set-VMHostStartPolicy,Get-VMHostAvailableTimeZone,Get-VMHostAccount,New-VMHostAccount,Set-VMHostAccount,Remove-VMHostAccount,Get-VMHostTPM,Get-EsxCli,Get-EsxTop,Get-VMHostNetworkStack,Set-VMHostNetworkStack,Add-VDSwitchVMHost,Remove-VDSwitchVMHost,Get-VMHostProfileImageCacheConfiguration,Set-VMHostProfileImageCacheConfiguration,Get-VMHostProfileRequiredInput,Get-VMHostProfileStorageDeviceConfiguration,Set-VMHostProfileStorageDeviceConfiguration,Get-VMHostProfileUserConfiguration,Set-VMHostProfileUserConfiguration,Get-VMHostProfileVmPortGroupConfiguration,Set-VMHostProfileVmPortGroupConfiguration,New-VMHostProfile,Import-VMHostProfile,Export-VMHostProfile,Remove-VMHostProfile,Invoke-VMHostProfile,Test-VMHostProfileCompliance,New-VMHostNetworkAdapter,Remove-VMHostNetworkAdapter,New-VMHostRoute,Remove-VMHostRoute,Install-VMHostPatch,Get-HAPrimaryVMHost,Get-DrsVMHostRule,New-DrsVMHostRule,Set-DrsVMHostRule,Remove-DrsVMHostRule,Get-TrustAuthorityVMHostBaseImage,New-TrustAuthorityVMHostBaseImage,Remove-TrustAuthorityVMHostBaseImage,Export-VMHostImageDb,Export-LcmVMHostDesiredState"
---

# VMware PowerCLI — Host Management

ESXi host lifecycle operations: discovery, configuration, maintenance, networking, storage, patching, and decommission. Module: VMware.VimAutomation (100+ cmdlets).

## Golden Rule

**ESXi host lifecycle: discover -> configure -> maintain -> patch -> decommission. Always evacuate VMs before maintenance. Never change management networking without a rollback plan.**

| Phase | Cmdlets | Use When | Critical Notes |
|-------|---------|----------|----------------|
| Discover | `Get-VMHost` | Inventory, health checks, capacity planning | Filter by state: Connected, Maintenance, Disconnected |
| Add to vCenter | `Add-VMHost` | Onboarding new ESXi hosts | Requires host root credentials; use `-Force` for untrusted certs |
| Configure | `Set-VMHost`, NTP/DNS/Syslog cmdlets | Initial setup or drift remediation | Apply host profiles for consistency across fleet |
| Maintain | `Set-VMHost -State Maintenance` | Patching, hardware work, firmware updates | Evacuate VMs first with `Move-VM` or let DRS handle it |
| Patch | `Install-VMHostPatch` | Apply ESXi updates | Host MUST be in maintenance mode; reboot usually required |
| Decommission | `Remove-VMHost` | Removing host from vCenter inventory | Evacuate VMs, exit maintenance, disconnect first |

## Scenario: Host Inventory and Health Monitoring

Every infrastructure automation starts with knowing what you have. `Get-VMHost` is the foundation cmdlet.

```powershell
# Connect to vCenter
$cred = Get-Credential -UserName "admin@vsphere.local"
Connect-VIServer -Server "vcenter.example.com" -Credential $cred

# Quick inventory: all hosts with state, CPU, RAM
Get-VMHost | Select-Object Name, ConnectionState, PowerState,
    @{N='CPUs';E={$_.NumCpu}},
    @{N='TotalRAM_GB';E={[math]::Round($_.MemoryTotalGB, 1)}},
    @{N='UsedRAM_GB';E={[math]::Round($_.MemoryUsageGB, 1)}},
    @{N='RAMPct';E={[math]::Round(($_.MemoryUsageGB / $_.MemoryTotalGB) * 100, 1)}},
    @{N='VMs';E={($_ | Get-VM).Count}},
    Version, Build |
    Format-Table -AutoSize

# Find hosts NOT in Connected state (problems)
Get-VMHost | Where-Object { $_.ConnectionState -ne "Connected" } |
    Select-Object Name, ConnectionState, PowerState

# Host hardware details: model, serial, BIOS
Get-VMHost "esxi01.example.com" | Get-VMHostHardware |
    Select-Object Manufacturer, Model, SerialNumber, BiosVersion, CpuModel,
    @{N='CpuCores';E={$_.CpuCoreCountTotal}},
    @{N='CpuThreads';E={$_.NicCount}}

# Cluster-level capacity report
Get-Cluster "Production" | Get-VMHost | ForEach-Object {
    [PSCustomObject]@{
        Host      = $_.Name
        State     = $_.ConnectionState
        CPUs      = $_.NumCpu
        CpuUsage  = "$([math]::Round($_.CpuUsageMhz / $_.CpuTotalMhz * 100, 1))%"
        RAM_GB    = [math]::Round($_.MemoryTotalGB, 1)
        RAMUsage  = "$([math]::Round($_.MemoryUsageGB / $_.MemoryTotalGB * 100, 1))%"
        VMCount   = ($_ | Get-VM | Where-Object { $_.PowerState -eq "PoweredOn" }).Count
    }
} | Format-Table -AutoSize

# Check host uptime (via advanced setting)
Get-VMHost | ForEach-Object {
    $bootTime = ($_ | Get-View).Runtime.BootTime
    [PSCustomObject]@{
        Host   = $_.Name
        BootTime = $bootTime
        Uptime   = "{0} days" -f ((Get-Date) - $bootTime).Days
    }
} | Format-Table -AutoSize
```

CRITICAL: `Get-VMHost` without filters returns ALL hosts. In large environments (100+ hosts), always scope by cluster or datacenter: `Get-VMHost -Location (Get-Cluster "Production")`.

## Scenario: Host Configuration (NTP, DNS, Syslog, Services, Firewall)

New hosts need NTP, DNS, syslog, and services configured consistently. Use host profiles for fleet-wide enforcement, but these cmdlets handle one-off fixes and drift remediation.

### NTP Configuration

```powershell
$targetHosts = Get-Cluster "Production" | Get-VMHost

foreach ($vmhost in $targetHosts) {
    # Remove any existing NTP servers
    $existing = Get-VMHostNtpServer -VMHost $vmhost
    if ($existing) {
        Remove-VMHostNtpServer -VMHost $vmhost -NtpServer $existing -Confirm:$false
    }

    # Add corporate NTP servers
    Add-VMHostNtpServer -VMHost $vmhost -NtpServer "ntp1.example.com" | Out-Null
    Add-VMHostNtpServer -VMHost $vmhost -NtpServer "ntp2.example.com" | Out-Null

    # Set ntpd service to start with host and start it now
    $ntpService = Get-VMHostService -VMHost $vmhost | Where-Object { $_.Key -eq "ntpd" }
    Set-VMHostService -HostService $ntpService -Policy "on" | Out-Null
    Start-VMHostService -HostService $ntpService -Confirm:$false | Out-Null

    Write-Host "NTP configured on $($vmhost.Name): $(Get-VMHostNtpServer -VMHost $vmhost)"
}
```

### DNS Configuration

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Set DNS servers and domain
Get-VMHostNetwork -VMHost $vmhost |
    Set-VMHostNetwork -DnsAddress "10.0.0.53", "10.0.0.54" `
    -DomainName "example.com" `
    -SearchDomain "example.com", "lab.example.com" `
    -HostName "esxi01"

# Verify
Get-VMHostNetwork -VMHost $vmhost | Select-Object DnsAddress, DomainName, SearchDomain, HostName
```

### Syslog Configuration

```powershell
$targetHosts = Get-Cluster "Production" | Get-VMHost

foreach ($vmhost in $targetHosts) {
    # Set remote syslog server
    Set-VMHostSysLogServer -VMHost $vmhost -SysLogServer "udp://syslog.example.com:514"

    # Open firewall for syslog traffic
    Get-VMHostFirewallException -VMHost $vmhost -Name "syslog" |
        Set-VMHostFirewallException -Enabled $true

    # Verify
    $syslog = Get-VMHostSysLogServer -VMHost $vmhost
    Write-Host "$($vmhost.Name) syslog: $syslog"
}
```

### Host Services Management

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# List all services and their status
Get-VMHostService -VMHost $vmhost |
    Select-Object Key, Label, Running, Policy | Format-Table -AutoSize

# Common service operations
# Enable SSH (for troubleshooting only — disable after)
$ssh = Get-VMHostService -VMHost $vmhost | Where-Object { $_.Key -eq "TSM-SSH" }
Start-VMHostService -HostService $ssh -Confirm:$false
Set-VMHostService -HostService $ssh -Policy "on"

# Disable SSH after troubleshooting
Stop-VMHostService -HostService $ssh -Confirm:$false
Set-VMHostService -HostService $ssh -Policy "off"

# Restart a service
$vpxa = Get-VMHostService -VMHost $vmhost | Where-Object { $_.Key -eq "vpxa" }
Restart-VMHostService -HostService $vpxa -Confirm:$false
```

### Firewall Configuration

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Check default firewall policy
Get-VMHostFirewallDefaultPolicy -VMHost $vmhost

# Set default policy: block incoming, allow outgoing
Set-VMHostFirewallDefaultPolicy -VMHost $vmhost -AllowIncoming $false -AllowOutgoing $true

# List all firewall exceptions
Get-VMHostFirewallException -VMHost $vmhost |
    Where-Object { $_.Enabled } |
    Select-Object Name, Enabled, IncomingPorts, OutgoingPorts, Protocols | Format-Table

# Enable specific firewall rules
Get-VMHostFirewallException -VMHost $vmhost -Name "SNMP Server" |
    Set-VMHostFirewallException -Enabled $true
```

## Scenario: Maintenance Mode Operations

Maintenance mode is required before patching, hardware changes, or firmware updates. The key is evacuating VMs first.

```powershell
$vmhost = Get-VMHost "esxi03.example.com"

# STEP 1: Check what VMs are on the host
$vmsOnHost = Get-VM -Location $vmhost | Where-Object { $_.PowerState -eq "PoweredOn" }
Write-Host "Powered-on VMs on $($vmhost.Name): $($vmsOnHost.Count)"
$vmsOnHost | Select-Object Name, NumCpu, MemoryGB | Format-Table

# STEP 2: Evacuate VMs to other hosts (manual vMotion)
# If DRS is enabled, entering maintenance mode auto-evacuates.
# For manual evacuation:
$targetHost = Get-VMHost "esxi01.example.com"
foreach ($vm in $vmsOnHost) {
    Write-Host "Migrating $($vm.Name) to $($targetHost.Name)..."
    Move-VM -VM $vm -Destination $targetHost -VMotionPriority "High" -RunAsync
}

# Wait for all migrations to complete
while ((Get-VM -Location $vmhost | Where-Object { $_.PowerState -eq "PoweredOn" }).Count -gt 0) {
    Write-Host "Waiting for migrations to complete..."
    Start-Sleep -Seconds 10
}

# STEP 3: Enter maintenance mode
Write-Host "Entering maintenance mode on $($vmhost.Name)..."
Set-VMHost -VMHost $vmhost -State "Maintenance" -Evacuate:$true -Confirm:$false

# Verify
Get-VMHost $vmhost.Name | Select-Object Name, ConnectionState

# STEP 4: Perform work (patching, hardware, etc.)
# ...

# STEP 5: Exit maintenance mode
Set-VMHost -VMHost $vmhost -State "Connected"
Write-Host "$($vmhost.Name) is back in service"
```

### Rolling Maintenance Across a Cluster

```powershell
function Enter-RollingMaintenance {
    param(
        [string]$ClusterName,
        [scriptblock]$MaintenanceWork
    )

    $cluster = Get-Cluster $ClusterName
    $hosts = $cluster | Get-VMHost | Where-Object { $_.ConnectionState -eq "Connected" }

    foreach ($vmhost in $hosts) {
        Write-Host "`n=== Processing $($vmhost.Name) ===" -ForegroundColor Cyan

        # Enter maintenance mode (DRS auto-evacuates if enabled)
        Write-Host "Entering maintenance mode..."
        Set-VMHost -VMHost $vmhost -State "Maintenance" -Evacuate:$true -Confirm:$false

        # Verify maintenance mode
        $state = (Get-VMHost $vmhost.Name).ConnectionState
        if ($state -ne "Maintenance") {
            Write-Warning "Failed to enter maintenance on $($vmhost.Name). Skipping."
            continue
        }

        # Run the maintenance work
        & $MaintenanceWork $vmhost

        # Exit maintenance mode
        Set-VMHost -VMHost $vmhost -State "Connected"
        Write-Host "$($vmhost.Name) back online"

        # Pause between hosts for stability
        Start-Sleep -Seconds 30
    }
}

# Usage: patch every host in the cluster
Enter-RollingMaintenance -ClusterName "Production" -MaintenanceWork {
    param($vmhost)
    Write-Host "Applying patches to $($vmhost.Name)..."
    # Install-VMHostPatch -VMHost $vmhost -HostPath "/vmfs/volumes/datastore1/patches/*.zip"
    Restart-VMHost -VMHost $vmhost -Confirm:$false -RunAsync
    Start-Sleep -Seconds 120  # Wait for reboot
    while ((Get-VMHost $vmhost.Name).ConnectionState -ne "Maintenance") {
        Start-Sleep -Seconds 15
    }
}
```

## Scenario: Host Networking

ESXi networking is layered: physical NICs (pNICs) -> virtual switches -> VMkernel ports. PowerCLI exposes all layers.

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# List all physical NICs
Get-VMHostNetworkAdapter -VMHost $vmhost -Physical |
    Select-Object Name, Mac, BitRatePerSec, FullDuplex, @{N='SpeedGb';E={$_.BitRatePerSec / 1000}} |
    Format-Table -AutoSize

# List all VMkernel adapters (management, vMotion, storage, vSAN)
Get-VMHostNetworkAdapter -VMHost $vmhost -VMKernel |
    Select-Object Name, IP, SubnetMask, PortGroupName,
    @{N='vMotion';E={$_.VMotionEnabled}},
    @{N='FaultTolerance';E={$_.FaultToleranceLoggingEnabled}},
    @{N='VSAN';E={$_.VsanTrafficEnabled}},
    @{N='Mgmt';E={$_.ManagementTrafficEnabled}} |
    Format-Table -AutoSize

# Get full network configuration
Get-VMHostNetwork -VMHost $vmhost |
    Select-Object VMHostName, DnsAddress, DomainName, HostName,
    @{N='DefaultGateway';E={$_.VMKernelGateway}},
    ConsoleGateway, SearchDomain
```

### Create a vMotion VMkernel Port

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Create VMkernel adapter for vMotion on an existing vSwitch port group
New-VMHostNetworkAdapter -VMHost $vmhost `
    -PortGroup "vMotion-PG" `
    -VirtualSwitch "vSwitch1" `
    -IP "10.10.20.11" `
    -SubnetMask "255.255.255.0" `
    -VMotionEnabled $true

# Verify
Get-VMHostNetworkAdapter -VMHost $vmhost -VMKernel |
    Where-Object { $_.VMotionEnabled } |
    Select-Object Name, IP, PortGroupName
```

### Modify Management Network

```powershell
# DANGER: Changing management network can disconnect the host from vCenter.
# Always have IPMI/iLO/iDRAC access as a fallback.

$vmhost = Get-VMHost "esxi01.example.com"
$mgmtNic = Get-VMHostNetworkAdapter -VMHost $vmhost -VMKernel |
    Where-Object { $_.ManagementTrafficEnabled }

# Change management IP (have console/IPMI ready!)
Set-VMHostNetworkAdapter -VirtualNic $mgmtNic `
    -IP "10.0.1.50" `
    -SubnetMask "255.255.255.0" `
    -Confirm:$false

# Update default gateway
Get-VMHostNetwork -VMHost $vmhost |
    Set-VMHostNetwork -VMKernelGateway "10.0.1.1"
```

### Network Stack Operations

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# List network stacks
Get-VMHostNetworkStack -VMHost $vmhost |
    Select-Object Name, DnsAddress, DnsSearchDomain, VMKernelGateway

# Add static route for storage network
New-VMHostRoute -VMHost $vmhost `
    -Destination "10.20.0.0" `
    -PrefixLength 24 `
    -Gateway "10.10.30.1"

# List routes
Get-VMHostRoute -VMHost $vmhost | Format-Table Destination, PrefixLength, Gateway, Device
```

## Scenario: Host Storage

Storage management covers HBAs, rescans, iSCSI configuration, and disk operations.

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# List storage adapters (FC HBAs, iSCSI, local)
Get-VMHostHba -VMHost $vmhost |
    Select-Object Name, Type, Device, Model, Status,
    @{N='WWN';E={
        if ($_.Type -eq "FibreChannel") {
            "{0:x}" -f $_.NodeWorldWideName
        } else { "N/A" }
    }} |
    Format-Table -AutoSize

# List visible disks
Get-VMHostDisk -VMHost $vmhost |
    Select-Object ScsiLun, TotalSectors, @{N='SizeGB';E={[math]::Round($_.TotalSectors * 512 / 1GB, 1)}} |
    Format-Table

# Storage configuration overview
Get-VMHostStorage -VMHost $vmhost |
    Select-Object VMHost, SoftwareIScsiEnabled

# Enable software iSCSI adapter
Set-VMHostStorage -VMHost $vmhost -SoftwareIScsiEnabled $true
```

### iSCSI Target Configuration

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Get the software iSCSI HBA
$iscsiHba = Get-VMHostHba -VMHost $vmhost -Type IScsi |
    Where-Object { $_.Model -eq "iSCSI Software Adapter" }

# Add iSCSI target (send target discovery)
$esxcli = Get-EsxCli -VMHost $vmhost -V2
$args = $esxcli.iscsi.adapter.discovery.sendtarget.add.CreateArgs()
$args.adapter = $iscsiHba.Device
$args.address = "10.20.0.100"
$esxcli.iscsi.adapter.discovery.sendtarget.add.Invoke($args)

# Rescan storage to discover new LUNs
Get-VMHostStorage -VMHost $vmhost -RescanAllHba -RescanVmfs

Write-Host "Rescan complete. New datastores should now be visible."

# Verify datastores
Get-Datastore -VMHost $vmhost | Select-Object Name, FreeSpaceGB, CapacityGB | Format-Table
```

### Rescan Storage Across a Cluster

```powershell
# After SAN provisioning, rescan all hosts in the cluster
$cluster = Get-Cluster "Production"
$cluster | Get-VMHost | ForEach-Object {
    Write-Host "Rescanning $($_.Name)..."
    Get-VMHostStorage -VMHost $_ -RescanAllHba -RescanVmfs
}
Write-Host "Cluster-wide rescan complete."
```

## Scenario: ESXi CLI Access via Get-EsxCli

`Get-EsxCli` provides direct access to the `esxcli` command framework from PowerCLI. This is essential for operations that have no native PowerCLI cmdlet.

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Always use -V2 for the modern argument syntax
$esxcli = Get-EsxCli -VMHost $vmhost -V2

# Check ESXi version and build
$esxcli.system.version.get.Invoke()

# List installed VIBs (packages)
$esxcli.software.vib.list.Invoke() |
    Select-Object Name, Version, Vendor, InstallDate |
    Sort-Object InstallDate -Descending |
    Select-Object -First 20 | Format-Table

# Check NIC driver versions
$esxcli.network.nic.list.Invoke() |
    Select-Object Name, Driver, Link, Speed, Duplex | Format-Table

# Check VM kernel interfaces
$esxcli.network.ip.interface.list.Invoke() | Format-Table

# Get active firewall rules
$esxcli.network.firewall.ruleset.list.Invoke() |
    Where-Object { $_.Enabled -eq $true } |
    Select-Object Name, Enabled | Format-Table

# System maintenance mode status
$esxcli.system.maintenanceMode.get.Invoke()
```

### Using EsxCli for Advanced Storage

```powershell
$esxcli = Get-EsxCli -VMHost (Get-VMHost "esxi01.example.com") -V2

# List SATP claim rules (multipath policy)
$esxcli.storage.nmp.satp.rule.list.Invoke() |
    Select-Object Name, DefaultPSP, Description | Format-Table

# List all storage devices with path count
$esxcli.storage.core.device.list.Invoke() |
    Select-Object Device, DeviceType, Size, PathCount |
    Where-Object { $_.DeviceType -eq "disk" } | Format-Table

# Set multipath policy for a specific device
$args = $esxcli.storage.nmp.device.set.CreateArgs()
$args.device = "naa.600508b..."
$args.psp = "VMW_PSP_RR"
$esxcli.storage.nmp.device.set.Invoke($args)
```

### Using EsxCli for Host Diagnostics

```powershell
$esxcli = Get-EsxCli -VMHost (Get-VMHost "esxi01.example.com") -V2

# Check coredump configuration
$esxcli.system.coredump.partition.get.Invoke()

# List syslog configuration
$esxcli.system.syslog.config.get.Invoke()

# Check hardware health sensors
$esxcli.hardware.platform.get.Invoke()

# Memory overview
$esxcli.hardware.memory.get.Invoke()
```

## Scenario: Host Profiles and Compliance

Host profiles capture the configuration of a reference host and enforce it across the fleet.

```powershell
# Create a host profile from a reference host
$refHost = Get-VMHost "esxi01.example.com"
$profile = New-VMHostProfile -Name "Production-Baseline-2025" `
    -ReferenceHost $refHost `
    -Description "Production host standard config"

# Check compliance of all hosts against the profile
$cluster = Get-Cluster "Production"
$results = Test-VMHostProfileCompliance -VMHost ($cluster | Get-VMHost) -Profile $profile
$results | Select-Object VMHost, ComplianceStatus,
    @{N='Violations';E={$_.IncomplianceElementList.Count}} |
    Format-Table

# Apply profile to a non-compliant host (host must be in maintenance mode)
$nonCompliant = $results | Where-Object { $_.ComplianceStatus -eq "NonCompliant" }
foreach ($result in $nonCompliant) {
    $vmhost = Get-VMHost $result.VMHost
    Set-VMHost -VMHost $vmhost -State "Maintenance" -Evacuate:$true -Confirm:$false
    Invoke-VMHostProfile -Entity $vmhost -Profile $profile -Confirm:$false
    Set-VMHost -VMHost $vmhost -State "Connected"
}
```

## Scenario: Host Authentication and Accounts

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Check Active Directory join status
Get-VMHostAuthentication -VMHost $vmhost |
    Select-Object VMHost, Domain, DomainMembershipStatus

# Join host to Active Directory
Set-VMHostAuthentication -VMHost $vmhost -Domain "example.com" `
    -JoinDomain -Credential (Get-Credential "EXAMPLE\admin") -Confirm:$false

# Manage local ESXi accounts
Get-VMHostAccount -VMHost $vmhost |
    Select-Object Id, Description | Format-Table

# Create a local account for automation
New-VMHostAccount -Id "automation-svc" -Password "SecurePass123!" `
    -Description "Automation service account" -VMHost $vmhost

# Change local account password
Set-VMHostAccount -UserAccount (Get-VMHostAccount -Id "root" -VMHost $vmhost) `
    -Password "NewRootPassword!"
```

## Scenario: Firmware and Advanced Settings

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Backup host firmware/configuration (requires maintenance mode)
Set-VMHost -VMHost $vmhost -State "Maintenance" -Confirm:$false
$bundle = Get-VMHostFirmware -VMHost $vmhost -BackupConfiguration `
    -DestinationPath "C:\Backups\"
Write-Host "Firmware backup saved to: $($bundle.Data)"
Set-VMHost -VMHost $vmhost -State "Connected"

# Get specific advanced settings
Get-VMHostAdvancedConfiguration -VMHost $vmhost -Name "Mem.ShareForceSalting" |
    Select-Object Name, Value

# Set advanced configuration (TPS salting for security)
Set-VMHostAdvancedConfiguration -VMHost $vmhost `
    -Name "Mem.ShareForceSalting" -Value 2

# Common advanced settings to audit
$securitySettings = @(
    "UserVars.SuppressShellWarning",
    "Security.AccountLockFailures",
    "Security.AccountUnlockTime",
    "Config.HostAgent.plugins.solo.enableMob",
    "Net.BlockGuestBPDU"
)
foreach ($setting in $securitySettings) {
    $val = Get-VMHostAdvancedConfiguration -VMHost $vmhost -Name $setting
    Write-Host "$setting = $($val.Values)"
}
```

## Scenario: SNMP Configuration

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Get current SNMP config
Get-VMHostSnmp -VMHost $vmhost

# Configure SNMPv2c
Set-VMHostSnmp -VMHost $vmhost -Enabled $true `
    -ReadOnlyCommunity @("public-monitoring")

# Add trap target
Set-VMHostSnmp -VMHost $vmhost `
    -AddTarget -TargetHost "10.0.0.200" -TargetPort 162 `
    -TargetCommunity "trap-community"

# Test SNMP configuration
Test-VMHostSnmp -VMHost $vmhost
```

## Scenario: Host Start Policy (VM Autostart)

```powershell
$vmhost = Get-VMHost "esxi01.example.com"

# Get the host's VM autostart policy
Get-VMHostStartPolicy -VMHost $vmhost |
    Select-Object VMHost, Enabled, StartDelay, StopAction, WaitForHeartbeat

# Enable VM autostart on the host
Set-VMHostStartPolicy -VMHostStartPolicy (Get-VMHostStartPolicy -VMHost $vmhost) `
    -Enabled $true -StartDelay 120 -StopAction "GuestShutdown"

# Configure individual VM start order
$vm = Get-VM "critical-dc-01"
$startPolicy = Get-VMStartPolicy -VM $vm
Set-VMStartPolicy -StartPolicy $startPolicy -StartAction "PowerOn" `
    -StartOrder 1 -StartDelay 60 -StopAction "GuestShutdown" -StopDelay 120
```

## Common Mistakes

### WRONG: Entering maintenance mode without checking for VMs

```powershell
# WRONG: This will fail or hang if VMs cannot be evacuated
Set-VMHost -VMHost $vmhost -State "Maintenance"
```

```powershell
# CORRECT: Check VMs, evacuate first, then enter maintenance
$vmsOnHost = Get-VM -Location $vmhost | Where-Object { $_.PowerState -eq "PoweredOn" }
if ($vmsOnHost.Count -gt 0) {
    Write-Host "Evacuating $($vmsOnHost.Count) VMs first..."
    foreach ($vm in $vmsOnHost) {
        Move-VM -VM $vm -Destination (Get-VMHost "esxi02.example.com") -RunAsync
    }
    # Wait for all VMs to migrate off
    while ((Get-VM -Location $vmhost | Where-Object { $_.PowerState -eq "PoweredOn" }).Count -gt 0) {
        Start-Sleep -Seconds 10
    }
}
Set-VMHost -VMHost $vmhost -State "Maintenance" -Confirm:$false
```

### WRONG: Changing management network IP without a rollback plan

```powershell
# WRONG: If the new IP is wrong, you lose connectivity to the host
$mgmtNic = Get-VMHostNetworkAdapter -VMHost $vmhost -VMKernel | Where-Object { $_.ManagementTrafficEnabled }
Set-VMHostNetworkAdapter -VirtualNic $mgmtNic -IP "10.0.99.50" -SubnetMask "255.255.255.0"
```

```powershell
# CORRECT: Document the old config, have IPMI/console access ready
$mgmtNic = Get-VMHostNetworkAdapter -VMHost $vmhost -VMKernel | Where-Object { $_.ManagementTrafficEnabled }
$oldIP = $mgmtNic.IP
$oldMask = $mgmtNic.SubnetMask
Write-Host "CURRENT: IP=$oldIP Mask=$oldMask — have IPMI console ready before proceeding"
Write-Host "ROLLBACK: Set-VMHostNetworkAdapter -VirtualNic `$mgmtNic -IP '$oldIP' -SubnetMask '$oldMask'"
# Only proceed when you have out-of-band console access confirmed
Set-VMHostNetworkAdapter -VirtualNic $mgmtNic -IP "10.0.1.50" -SubnetMask "255.255.255.0" -Confirm:$false
```

### WRONG: Not rescanning storage after adding LUNs on the SAN

```powershell
# WRONG: LUNs provisioned on SAN but ESXi does not see them
Get-Datastore -VMHost $vmhost  # Missing the new LUNs!
```

```powershell
# CORRECT: Rescan HBAs and VMFS after SAN provisioning
Get-VMHostStorage -VMHost $vmhost -RescanAllHba -RescanVmfs
# Now check for new datastores
Get-Datastore -VMHost $vmhost | Select-Object Name, CapacityGB, FreeSpaceGB | Format-Table
```

### WRONG: Modifying host services without checking dependencies

```powershell
# WRONG: Stopping vpxa disconnects the host from vCenter
$vpxa = Get-VMHostService -VMHost $vmhost | Where-Object { $_.Key -eq "vpxa" }
Stop-VMHostService -HostService $vpxa -Confirm:$false
# Host is now disconnected from vCenter!
```

```powershell
# CORRECT: Only stop non-critical services, understand what each service does
$service = Get-VMHostService -VMHost $vmhost | Where-Object { $_.Key -eq "TSM-SSH" }
# SSH is safe to toggle — it does not affect vCenter connectivity
Stop-VMHostService -HostService $service -Confirm:$false
Set-VMHostService -HostService $service -Policy "off"
Write-Host "SSH disabled on $($vmhost.Name)"
# NEVER stop: vpxa (vCenter agent), hostd (management), fdm (HA agent)
```

### WRONG: Forgetting -RunAsync on long-running host operations

```powershell
# WRONG: Blocks your script for 10+ minutes while host reboots
Restart-VMHost -VMHost $vmhost -Confirm:$false
# Script is frozen here until host comes back
Write-Host "This line won't execute until reboot completes"
```

```powershell
# CORRECT: Use -RunAsync and poll for completion
$task = Restart-VMHost -VMHost $vmhost -Confirm:$false -RunAsync
Write-Host "Reboot initiated (Task: $($task.Id)). Polling for completion..."
do {
    Start-Sleep -Seconds 15
    $state = (Get-VMHost $vmhost.Name).ConnectionState
    Write-Host "Host state: $state"
} until ($state -eq "Connected" -or $state -eq "Maintenance")
Write-Host "$($vmhost.Name) is back online."
```

### WRONG: Using Get-EsxCli without -V2

```powershell
# WRONG: V1 syntax is deprecated and uses positional arguments (fragile)
$esxcli = Get-EsxCli -VMHost $vmhost
$esxcli.network.nic.list()
```

```powershell
# CORRECT: Always use -V2 for named argument syntax
$esxcli = Get-EsxCli -VMHost $vmhost -V2
$esxcli.network.nic.list.Invoke()
# V2 uses CreateArgs() for commands with parameters — much safer
$args = $esxcli.storage.nmp.device.set.CreateArgs()
$args.device = "naa.600508b..."
$args.psp = "VMW_PSP_RR"
$esxcli.storage.nmp.device.set.Invoke($args)
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-VMHost` | List/filter ESXi hosts | `-Name`, `-Location`, `-State` |
| `Set-VMHost` | Change host state, license, timezone | `-State`, `-LicenseKey`, `-TimeZone` |
| `Add-VMHost` | Add host to vCenter | `-Name`, `-Location`, `-User`, `-Password`, `-Force` |
| `Remove-VMHost` | Remove host from vCenter inventory | `-VMHost`, `-Confirm` |
| `Move-VMHost` | Move host between folders/clusters | `-VMHost`, `-Destination` |
| `Restart-VMHost` | Reboot ESXi host | `-VMHost`, `-Force`, `-RunAsync` |
| `Stop-VMHost` | Shutdown ESXi host | `-VMHost`, `-Force`, `-RunAsync` |
| `Start-VMHost` | Power on host (via IPMI/iLO) | `-VMHost`, `-RunAsync` |
| `Suspend-VMHost` | Put host in standby | `-VMHost`, `-RunAsync` |
| `Get-VMHostService` | List host services | `-VMHost` |
| `Start-VMHostService` | Start a service | `-HostService` |
| `Stop-VMHostService` | Stop a service | `-HostService` |
| `Restart-VMHostService` | Restart a service | `-HostService` |
| `Get-VMHostFirewallDefaultPolicy` | Default firewall policy | `-VMHost` |
| `Set-VMHostFirewallDefaultPolicy` | Set default policy | `-AllowIncoming`, `-AllowOutgoing` |
| `Get-VMHostFirewallException` | Firewall rules | `-VMHost`, `-Name` |
| `Set-VMHostFirewallException` | Enable/disable rules | `-Enabled` |
| `Get-VMHostNetworkAdapter` | List NICs and VMkernel ports | `-VMHost`, `-Physical`, `-VMKernel` |
| `New-VMHostNetworkAdapter` | Create VMkernel port | `-PortGroup`, `-VirtualSwitch`, `-IP` |
| `Set-VMHostNetworkAdapter` | Modify NIC/VMkernel | `-IP`, `-SubnetMask`, `-VMotionEnabled` |
| `Remove-VMHostNetworkAdapter` | Remove VMkernel port | `-Nic` |
| `Get-VMHostNetwork` | DNS, gateway, hostname | `-VMHost` |
| `Set-VMHostNetwork` | Set DNS, gateway, hostname | `-DnsAddress`, `-DomainName`, `-VMKernelGateway` |
| `Get-VMHostNetworkStack` | Network stack info | `-VMHost` |
| `Set-VMHostNetworkStack` | Modify network stack | `-DnsAddress`, `-VMKernelGateway` |
| `Get-VMHostStorage` | Storage config, rescan | `-VMHost`, `-RescanAllHba`, `-RescanVmfs` |
| `Set-VMHostStorage` | Enable/disable software iSCSI | `-SoftwareIScsiEnabled` |
| `Get-VMHostHba` | List HBAs (FC, iSCSI, local) | `-VMHost`, `-Type` |
| `Set-VMHostHba` | Configure iSCSI HBA | `-IScsiHba`, `-ChapType` |
| `Get-VMHostDisk` | List physical disks | `-VMHost` |
| `Get-VMHostDiskPartition` | Partition table | `-VMHostDisk` |
| `Format-VMHostDiskPartition` | Format disk partition | `-VMHostDiskPartition` |
| `Get-VMHostNtpServer` | List NTP servers | `-VMHost` |
| `Add-VMHostNtpServer` | Add NTP server | `-VMHost`, `-NtpServer` |
| `Remove-VMHostNtpServer` | Remove NTP server | `-NtpServer` |
| `Get-VMHostPatch` | List installed patches | `-VMHost` |
| `Install-VMHostPatch` | Install ESXi patch | `-VMHost`, `-HostPath` |
| `Get-VMHostProfile` | List host profiles | `-Name` |
| `New-VMHostProfile` | Create from reference host | `-ReferenceHost`, `-Name` |
| `Import-VMHostProfile` | Import profile from file | `-FilePath` |
| `Export-VMHostProfile` | Export profile to file | `-FilePath` |
| `Remove-VMHostProfile` | Delete a host profile | `-Profile` |
| `Invoke-VMHostProfile` | Apply profile to host | `-Entity`, `-Profile` |
| `Test-VMHostProfileCompliance` | Check compliance | `-VMHost`, `-Profile` |
| `Get-VMHostFirmware` | Backup host firmware | `-VMHost`, `-BackupConfiguration` |
| `Set-VMHostFirmware` | Restore firmware | `-VMHost`, `-Restore`, `-SourcePath` |
| `Get-VMHostModule` | List kernel modules | `-VMHost`, `-Name` |
| `Set-VMHostModule` | Configure kernel module | `-VMHostModule`, `-Options` |
| `Get-VMHostSnmp` | SNMP configuration | `-VMHost` |
| `Set-VMHostSnmp` | Configure SNMP | `-Enabled`, `-ReadOnlyCommunity` |
| `Test-VMHostSnmp` | Test SNMP setup | `-VMHost` |
| `Get-VMHostRoute` | List static routes | `-VMHost` |
| `New-VMHostRoute` | Add static route | `-Destination`, `-Gateway`, `-PrefixLength` |
| `Remove-VMHostRoute` | Delete static route | `-VMHostRoute` |
| `Get-VMHostAuthentication` | AD join status | `-VMHost` |
| `Set-VMHostAuthentication` | Join/leave AD | `-Domain`, `-JoinDomain`, `-Credential` |
| `Get-VMHostHardware` | Hardware inventory | `-VMHost` |
| `Get-VMHostPciDevice` | PCI devices | `-VMHost` |
| `Get-VMHostAdvancedConfiguration` | Advanced settings | `-VMHost`, `-Name` |
| `Set-VMHostAdvancedConfiguration` | Set advanced settings | `-Name`, `-Value` |
| `Get-VMHostDiagnosticPartition` | Coredump partition | `-VMHost` |
| `Set-VMHostDiagnosticPartition` | Set coredump partition | `-Partition` |
| `Get-VMHostSysLogServer` | Syslog target | `-VMHost` |
| `Set-VMHostSysLogServer` | Set syslog target | `-SysLogServer` |
| `Get-VMHostStartPolicy` | VM autostart policy | `-VMHost` |
| `Set-VMHostStartPolicy` | Configure autostart | `-Enabled`, `-StartDelay`, `-StopAction` |
| `Get-VMHostAvailableTimeZone` | List timezones | `-VMHost` |
| `Get-VMHostAccount` | Local ESXi accounts | `-VMHost`, `-Id` |
| `New-VMHostAccount` | Create local account | `-Id`, `-Password`, `-Description` |
| `Set-VMHostAccount` | Modify account | `-UserAccount`, `-Password` |
| `Remove-VMHostAccount` | Delete account | `-UserAccount` |
| `Get-VMHostTPM` | TPM attestation info | `-VMHost` |
| `Get-EsxCli` | Direct esxcli access | `-VMHost`, `-V2` |
| `Get-EsxTop` | Real-time perf stats | `-VMHost` |
| `Get-DrsVMHostRule` | DRS host affinity rules | `-Cluster`, `-Name` |
| `New-DrsVMHostRule` | Create DRS host rule | `-Name`, `-Cluster`, `-VMGroup`, `-VMHostGroup` |
| `Set-DrsVMHostRule` | Modify DRS host rule | `-Rule`, `-Enabled` |
| `Remove-DrsVMHostRule` | Delete DRS host rule | `-Rule` |
| `Get-HAPrimaryVMHost` | HA primary host | `-Cluster` |
| `Add-VDSwitchVMHost` | Add host to VDS | `-VDSwitch`, `-VMHost` |
| `Remove-VDSwitchVMHost` | Remove host from VDS | `-VDSwitch`, `-VMHost` |

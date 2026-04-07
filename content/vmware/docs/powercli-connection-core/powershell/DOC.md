---
name: powercli-connection-core
description: "VMware PowerCLI 13.3 — vCenter connection, credential management, session reuse, multiple server mode, raw API access via Get-View, PowerCLI configuration"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,connect,vcenter,credential,session,configuration,view,api,Connect-VIServer,Disconnect-VIServer,Get-View,Get-VIObjectByVIView,Get-VICommand,Get-VICredentialStoreItem,New-VICredentialStoreItem,Remove-VICredentialStoreItem,Get-VIProperty,New-VIProperty,Remove-VIProperty,Get-PowerCLIConfiguration,Set-PowerCLIConfiguration,Get-PowerCLIVersion"
---

# VMware PowerCLI — Connection & Core

## Golden Rule

**Every PowerCLI script starts with `Connect-VIServer`. Every multi-vCenter script passes `-Server` to every cmdlet. Store credentials securely — never hardcode passwords.**

| Task | Cmdlet | Use When | Notes |
|------|--------|----------|-------|
| Connect to vCenter | `Connect-VIServer` | Start of every script | Returns a server object you can pass to `-Server` |
| Disconnect | `Disconnect-VIServer` | End of script / cleanup | `-Force` suppresses confirmation |
| Store credentials | `New-VICredentialStoreItem` | Automated/scheduled scripts | Encrypted on disk, per-user |
| Raw vSphere API | `Get-View` | Advanced operations not in PowerCLI cmdlets | Returns .NET managed objects — powerful but complex |
| Config PowerCLI | `Set-PowerCLIConfiguration` | First-time setup, suppress warnings | `-InvalidCertificateAction Ignore` for lab environments |

## Scenario: First-Time PowerCLI Setup

Before using PowerCLI, configure it to handle common issues:

```powershell
# Suppress invalid certificate warnings (lab/test environments)
Set-PowerCLIConfiguration -InvalidCertificateAction Ignore -Confirm:$false -Scope AllUsers

# Disable VMware CEIP telemetry
Set-PowerCLIConfiguration -Scope AllUsers -ParticipateInCEIP $false -Confirm:$false

# Enable multiple server connections (required for multi-vCenter)
Set-PowerCLIConfiguration -DefaultVIServerMode Multiple -Confirm:$false

# Set default timeout for web operations (seconds)
Set-PowerCLIConfiguration -Scope User -WebOperationTimeoutSeconds 600 -Confirm:$false
```

CRITICAL: These settings persist across sessions. Set once per machine/user.

## Scenario: Connect to vCenter (Production Pattern)

```powershell
# Interactive — prompts for credentials
Connect-VIServer -Server "vcenter.example.com"

# With explicit credentials (EVA pattern)
$cred = Get-Credential -UserName "admin@vsphere.local"
$viServer = Connect-VIServer -Server "vcenter.example.com" -Credential $cred

# With stored credentials (automated scripts)
$viServer = Connect-VIServer -Server "vcenter.example.com" -SaveCredentials
# Next time: Connect-VIServer -Server "vcenter.example.com" (auto-uses stored cred)

# Connect to multiple vCenters simultaneously
$servers = @("vc-prod.example.com", "vc-dev.example.com", "vc-dr.example.com")
$servers | ForEach-Object { Connect-VIServer -Server $_ -Credential $cred }

# Check current connections
$global:DefaultVIServers | Select-Object Name, IsConnected, User
```

## Scenario: Multi-vCenter Operations (EVA Pattern)

EVA connects to multiple vCenters and ALWAYS passes `-Server` to every cmdlet:

```powershell
# Connect to all vCenters
$vcProd = Connect-VIServer "vc-prod.example.com" -Credential $cred -NotDefault
$vcDR = Connect-VIServer "vc-dr.example.com" -Credential $cred -NotDefault

# Get VMs from specific vCenter — ALWAYS use -Server
$prodVMs = Get-VM -Name "web-*" -Server $vcProd
$drVMs = Get-VM -Name "web-*" -Server $vcDR

# Compare environments
$comparison = @()
foreach ($vm in $prodVMs) {
    $drMatch = $drVMs | Where-Object { $_.Name -eq $vm.Name }
    $comparison += [PSCustomObject]@{
        Name = $vm.Name
        ProdState = $vm.PowerState
        DRState = if ($drMatch) { $drMatch.PowerState } else { "Missing" }
    }
}
$comparison | Format-Table

# Disconnect all
Disconnect-VIServer -Server $vcProd, $vcDR -Force -Confirm:$false
```

## Scenario: Secure Credential Storage

```powershell
# Store credentials encrypted (per-user, per-machine)
New-VICredentialStoreItem -Host "vcenter.example.com" `
    -User "admin@vsphere.local" -Password "secret"

# List stored credentials
Get-VICredentialStoreItem | Select-Object Host, User

# Connect using stored credential (automatic lookup)
Connect-VIServer -Server "vcenter.example.com"

# Remove stored credential
Remove-VICredentialStoreItem -Host "vcenter.example.com" -User "admin@vsphere.local"
```

NOTE: Credential store is encrypted with Windows DPAPI (Windows) or platform keyring (Linux). Different user accounts have different stores.

## Scenario: Raw API Access with Get-View

When PowerCLI cmdlets don't expose a feature, use `Get-View` for direct vSphere API access:

```powershell
# Get the raw API view of a VM
$vm = Get-VM -Name "web-01"
$vmView = Get-View -VIObject $vm

# Access properties not available through Get-VM
$vmView.Config.Hardware.Device | 
    Where-Object { $_ -is [VMware.Vim.VirtualDisk] } |
    Select-Object @{N='Label';E={$_.DeviceInfo.Label}}, 
                  @{N='SizeGB';E={$_.CapacityInKB/1MB}},
                  @{N='ThinProvisioned';E={$_.Backing.ThinProvisioned}}

# Get performance counters via API (faster than Get-Stat for bulk queries)
$perfMgr = Get-View (Get-View ServiceInstance).Content.PerfManager
$metrics = $perfMgr.QueryAvailablePerfMetric($vmView.MoRef, $null, $null, 20)

# Convert a View object back to a PowerCLI object
$vmObj = Get-VIObjectByVIView -VIView $vmView
```

CRITICAL: `Get-View` returns .NET objects with different property names than PowerCLI cmdlets. Use `$view | Get-Member` to explore. Much faster than PowerCLI cmdlets for bulk operations but harder to use.

## Scenario: Session Management

```powershell
# Save session ID for later reconnection
$server = Connect-VIServer -Server "vcenter.example.com" -Credential $cred
$sessionId = $server.SessionId
$sessionId | Out-File "~/.vcenter-session"

# Reconnect using saved session (no re-authentication needed)
$savedSession = Get-Content "~/.vcenter-session"
Connect-VIServer -Server "vcenter.example.com" -Session $savedSession

# Check session validity
$global:DefaultVIServers | Select-Object Name, IsConnected, SessionId
```

## Common Mistakes

### Mistake 1: Not Using -Server in Multi-vCenter

```powershell
# WRONG — Ambiguous when connected to multiple vCenters
$vm = Get-VM -Name "web-01"
# Returns VMs from ALL connected vCenters — duplicates if same name exists!

# CORRECT — Always specify the server
$vm = Get-VM -Name "web-01" -Server $vcProd
```

### Mistake 2: Hardcoding Passwords

```powershell
# WRONG — Password in plain text in script
Connect-VIServer -Server "vc.example.com" -User "admin" -Password "MyP@ss123"

# CORRECT — Use credential store or prompt
New-VICredentialStoreItem -Host "vc.example.com" -User "admin" -Password "MyP@ss123"
# Then:
Connect-VIServer -Server "vc.example.com"  # Auto-uses stored credential
```

### Mistake 3: Not Handling Certificate Errors

```powershell
# WRONG — Script fails on first run because of certificate warning
Connect-VIServer -Server "vc.example.com"  # ERROR: Invalid certificate

# CORRECT — Configure certificate handling BEFORE connecting
Set-PowerCLIConfiguration -InvalidCertificateAction Ignore -Confirm:$false
Connect-VIServer -Server "vc.example.com"
```

### Mistake 4: Not Disconnecting

```powershell
# WRONG — Session leaks, may hit concurrent session limits
Connect-VIServer -Server "vc.example.com"
# ... do work ...
# Script ends without disconnecting

# CORRECT — Always disconnect in a try/finally block
try {
    $server = Connect-VIServer -Server "vc.example.com" -Credential $cred
    # ... do work ...
} finally {
    if ($server) { Disconnect-VIServer -Server $server -Force -Confirm:$false }
}
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Connect-VIServer` | Connect to vCenter | `-Server`, `-Credential`, `-User`/`-Password`, `-Session`, `-SaveCredentials`, `-AllLinked`, `-NotDefault` |
| `Disconnect-VIServer` | Close connection | `-Server`, `-Force` |
| `Get-View` | Raw vSphere API access | `-VIObject` (from cmdlet), `-Id` (MoRef), `-ViewType` (search), `-Filter` |
| `Get-VIObjectByVIView` | View → PowerCLI object | `-VIView`, `-MORef` |
| `Set-PowerCLIConfiguration` | Configure PowerCLI | `-InvalidCertificateAction`, `-DefaultVIServerMode`, `-ParticipateInCEIP`, `-WebOperationTimeoutSeconds` |
| `Get-PowerCLIConfiguration` | Show current config | No parameters |
| `Get-PowerCLIVersion` | Version info | No parameters |
| `New-VICredentialStoreItem` | Store credentials | `-Host`, `-User`, `-Password` |
| `Get-VICredentialStoreItem` | List stored creds | `-Host`, `-User` |
| `Remove-VICredentialStoreItem` | Delete stored creds | `-Host`, `-User` |
| `Get-VICommand` | List all PowerCLI cmdlets | `-Name` (wildcard) |

---
name: powercli-vm-operations
description: "VMware PowerCLI 13.3 — VM lifecycle, snapshots, power operations, guest scripts, cloning, migration. Covers Get-VM, New-VM, Set-VM, Remove-VM, Start-VM, Stop-VM, Get-Snapshot, New-Snapshot, Remove-Snapshot, Invoke-VMScript, Copy-VMGuestFile, Move-VM"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,vm,virtual-machine,snapshot,power,clone,migrate,vmotion,guest,invoke-vmscript,copy-vmguestfile,Get-VM,New-VM,Set-VM,Remove-VM,Start-VM,Stop-VM,Restart-VM,Suspend-VM,Resume-VM,Get-Snapshot,New-Snapshot,Remove-Snapshot,Set-Snapshot,Move-VM,Copy-VMGuestFile,Invoke-VMScript,Get-VMGuest,Get-VMQuestion,Set-VMQuestion,Get-VMResourceConfiguration,Set-VMResourceConfiguration,Get-VMStartPolicy,Set-VMStartPolicy,Unlock-VM,Copy-HardDisk,Get-UsbDevice,Remove-UsbDevice"
---

# VMware PowerCLI — VM Operations

## Golden Rule

**Always connect to vCenter first, always use `-Server` for multi-vCenter environments, always handle errors.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| Find VMs | `Get-VM` | First step for ANY VM operation | Supports wildcards: `Get-VM -Name "prod-*"` |
| Create VM | `New-VM` | New VM from scratch or template | Requires `-VMHost` or `-ResourcePool` |
| Modify VM | `Set-VM` | Change CPU, RAM, name, guest ID | VM must be powered off for hardware changes |
| Power on | `Start-VM` | Boot a stopped VM | Check VMware Tools status after |
| Graceful shutdown | `Stop-VMGuest` | Production shutdown | Requires VMware Tools running |
| Hard power off | `Stop-VM -Kill` | Emergency or stuck VM | Data loss risk — use only when guest OS is unresponsive |
| Snapshot before changes | `New-Snapshot` | Before patching, upgrades, risky changes | Snapshots degrade performance over time — remove after |
| Clean old snapshots | `Remove-Snapshot` | Cleanup after successful changes | Consolidates disks — can take hours on large VMs |
| Run scripts inside VM | `Invoke-VMScript` | Execute commands in guest OS | Requires VMware Tools + guest credentials |
| Copy files to/from VM | `Copy-VMGuestFile` | Transfer files through VMware Tools | Requires VMware Tools — NOT network-based |
| Move VM (vMotion) | `Move-VM` | Rebalance hosts, evacuate for maintenance | `-VMotionPriority High` for powered-on VMs |
| Delete VM | `Remove-VM` | Remove from inventory | Add `-DeletePermanently` to also delete disk files |

## Scenario: Connect and Find VMs

Every PowerCLI session starts with connecting to vCenter. In multi-vCenter environments, always pass `-Server` to every cmdlet.

```powershell
# Connect to vCenter with credentials
$cred = Get-Credential -UserName "admin@vsphere.local"
Connect-VIServer -Server "vcenter.example.com" -Credential $cred

# Find VMs by name pattern
$prodVMs = Get-VM -Name "prod-*" -Server "vcenter.example.com"
$prodVMs | Select-Object Name, PowerState, NumCpu, MemoryGB, VMHost | Format-Table

# Find VMs on a specific host
Get-VM -Location (Get-VMHost "esxi01.example.com") | 
    Where-Object { $_.PowerState -eq "PoweredOn" } |
    Select-Object Name, NumCpu, MemoryGB
```

CRITICAL: `Get-VM` without `-Name` returns ALL VMs — can be thousands. Always filter.

## Scenario: Snapshot Management (Most Common EVA Workflow)

Snapshots are the most critical safety mechanism. Take before ANY change, clean up after.

```powershell
# Create snapshot before patching
$vm = Get-VM -Name "web-server-01" -Server $vcenter
New-Snapshot -VM $vm -Name "pre-patch-$(Get-Date -Format 'yyyy-MM-dd')" `
    -Description "Before OS patching" -Memory -Quiesce

# List all snapshots for a VM
Get-VM "web-server-01" | Get-Snapshot | 
    Select-Object VM, Name, Created, SizeGB, IsCurrent | Format-Table

# CRITICAL WORKFLOW: Find and remove snapshots older than 30 days
$oldSnapshots = Get-VM -Name "prod-*" | 
    Get-Snapshot | 
    Where-Object { $_.Created -lt (Get-Date).AddDays(-30) }

# Always review before deleting in production
$oldSnapshots | Select-Object @{N='VM';E={$_.VM.Name}}, Name, Created, 
    @{N='SizeGB';E={[math]::Round($_.SizeGB, 2)}}, 
    @{N='AgeDays';E={((Get-Date) - $_.Created).Days}} | 
    Sort-Object AgeDays -Descending | Format-Table

# Remove with confirmation (production) or without (scripted)
$oldSnapshots | Remove-Snapshot -Confirm  # Interactive
# $oldSnapshots | Remove-Snapshot -Confirm:$false  # Scripted (DANGEROUS)

# Monitor removal progress (consolidation can take hours on large VMs)
Get-Task | Where-Object { $_.Name -eq "RemoveSnapshot_Task" -and $_.State -eq "Running" } |
    Select-Object Name, PercentComplete, StartTime
```

CRITICAL: Snapshot removal triggers disk consolidation. On VMs with 500GB+ disks, this can take **hours** and temporarily increases I/O. Schedule during maintenance windows.

## Scenario: Run Commands Inside Guest OS (EVA Pattern)

EVA heavily uses `Invoke-VMScript` to execute commands inside VMs. This requires VMware Tools running.

```powershell
# Run a bash command on a Linux VM
$vm = Get-VM -Name $JobObject.VM -Server $JobObject.VCenter
$cred = New-Object PSCredential("root", (ConvertTo-SecureString "password" -AsPlainText -Force))

$result = Invoke-VMScript -Server $JobObject.VCenter -VM $vm `
    -ScriptText "hostname && df -h && uptime" `
    -ScriptType Bash -Confirm:$false `
    -GuestCredential $cred `
    -ErrorAction SilentlyContinue -WarningAction SilentlyContinue

if ($result) {
    $output = $result.ScriptOutput
    Write-Output "Guest output: $output"
} else {
    Write-Warning "VMware Tools not responding on $($vm.Name)"
}

# Run PowerShell on a Windows VM
$winResult = Invoke-VMScript -Server $vcenter -VM $vm `
    -ScriptText '@(Get-ComputerInfo -Property *OsProductType*).OsProductType' `
    -Confirm:$false -GuestCredential $cred `
    -ErrorAction SilentlyContinue

# Copy files TO the guest (Linux)
Copy-VMGuestFile -Server $vcenter `
    -Source (Get-Item "./deploy-script.sh") `
    -Destination "/var/tmp/" `
    -VM $vm -Force -LocalToGuest `
    -GuestCredential $cred -Confirm:$false

# Copy files FROM the guest
Copy-VMGuestFile -Server $vcenter `
    -Source "/var/log/app.log" `
    -Destination "C:\Temp\" `
    -VM $vm -Force -GuestToLocal `
    -GuestCredential $cred
```

CRITICAL: `Invoke-VMScript` and `Copy-VMGuestFile` go through VMware Tools, NOT the network. If Tools are down, these commands fail. Check Tools status first: `(Get-VMGuest $vm).ToolsStatus`

## Scenario: VM Power Operations

```powershell
# Graceful shutdown (sends shutdown signal through VMware Tools)
$vm = Get-VM -Name "web-01" -Server $vcenter
Stop-VMGuest -VM $vm -Confirm:$false
# Wait for VM to power off
do { Start-Sleep 5; $vm = Get-VM $vm.Name } while ($vm.PowerState -ne "PoweredOff")

# Hard power off (like pulling the power cord — use only when guest is stuck)
Stop-VM -VM $vm -Kill -Confirm:$false

# Power on and wait for VMware Tools
Start-VM -VM $vm
Wait-Tools -VM $vm -TimeoutSeconds 300

# Restart guest OS (graceful reboot)
Get-VM -Name "web-01" | Restart-VMGuest -Confirm:$false
```

## Scenario: Create VM from Template

```powershell
# Deploy from template with customization
$template = Get-Template -Name "ubuntu-22.04-base"
$cluster = Get-Cluster -Name "Production"
$datastore = Get-Datastore -Name "ssd-tier1" | Sort-Object FreeSpaceGB -Descending | Select-Object -First 1
$spec = Get-OSCustomizationSpec -Name "linux-prod"
$portgroup = Get-VDPortgroup -Name "VLAN-100-Web"

$newVM = New-VM -Name "web-server-05" `
    -Template $template `
    -ResourcePool $cluster `
    -Datastore $datastore `
    -OSCustomizationSpec $spec `
    -Location (Get-Folder "Web Servers")

# Set CPU and memory after creation
Set-VM -VM $newVM -NumCpu 4 -MemoryGB 16 -Confirm:$false

# Set network
Get-NetworkAdapter -VM $newVM | 
    Set-NetworkAdapter -Portgroup $portgroup -Connected:$true -Confirm:$false

# Power on
Start-VM -VM $newVM
Wait-Tools -VM $newVM -TimeoutSeconds 300
```

## Scenario: Migrate VM (vMotion)

```powershell
# Live migrate to different host (compute vMotion)
$vm = Get-VM -Name "db-server-01"
$targetHost = Get-VMHost -Name "esxi03.example.com"
Move-VM -VM $vm -Destination $targetHost -VMotionPriority High

# Storage vMotion (move disks to different datastore)
$targetDS = Get-Datastore -Name "fast-ssd-pool"
Move-VM -VM $vm -Datastore $targetDS -DiskStorageFormat Thin

# Combined compute + storage migration
Move-VM -VM $vm -Destination $targetHost -Datastore $targetDS

# Cross-vCenter migration (vSphere 6.0+)
Move-VM -VM $vm -Destination $targetHost `
    -DestinationSslThumbprint $thumbprint `
    -NetworkAdapter (Get-NetworkAdapter $vm) `
    -PortGroup $targetPortGroup
```

CRITICAL: vMotion requires compatible CPUs between hosts. Storage vMotion can run while VM is powered on but increases I/O temporarily.

## Common Mistakes

### Mistake 1: Removing VM Without -DeletePermanently

```powershell
# WRONG — VM removed from inventory but disk files remain (orphaned)
Remove-VM -VM "old-server" -Confirm:$false
# Disk files (.vmdk, .vmx) still consuming datastore space!

# CORRECT — Remove from inventory AND delete disk files
Remove-VM -VM "old-server" -DeletePermanently -Confirm:$false
```

### Mistake 2: Not Specifying -Server in Multi-vCenter

```powershell
# WRONG — Which vCenter? Undefined behavior if multiple are connected
$vm = Get-VM -Name "web-01"

# CORRECT — Always explicit in multi-vCenter environments
$vm = Get-VM -Name "web-01" -Server "vcenter-prod.example.com"
```

EVA ALWAYS uses `-Server $JobObject.VCenter` on every cmdlet call. This is the correct pattern for production automation.

### Mistake 3: Snapshot Left Running for Weeks

```powershell
# WRONG — Create snapshot, forget about it
New-Snapshot -VM "prod-db" -Name "quick-test"
# ... weeks later, snapshot chain is 200GB, performance degraded

# CORRECT — Always set a reminder or automated cleanup
New-Snapshot -VM "prod-db" -Name "patch-$(Get-Date -Format 'yyyyMMdd')" `
    -Description "Remove within 72 hours"

# Automated cleanup script:
Get-VM | Get-Snapshot | 
    Where-Object { $_.Created -lt (Get-Date).AddDays(-3) } | 
    Remove-Snapshot -Confirm:$false
```

### Mistake 4: Using Stop-VM Instead of Stop-VMGuest

```powershell
# WRONG — Hard power off, like pulling the plug
Stop-VM -VM "prod-web" -Confirm:$false
# File system may be corrupted!

# CORRECT — Graceful shutdown through VMware Tools
$vm = Get-VM "prod-web"
Stop-VMGuest -VM $vm -Confirm:$false
# Wait for power off
do { Start-Sleep 5 } while ((Get-VM $vm.Name).PowerState -ne "PoweredOff")
```

### Mistake 5: Invoke-VMScript Fails Silently

```powershell
# WRONG — No error handling, no output capture
Invoke-VMScript -VM $vm -ScriptText "systemctl restart nginx"

# CORRECT — Capture output, check for errors, handle Tools being down
$result = Invoke-VMScript -VM $vm `
    -ScriptText "systemctl restart nginx; echo EXIT_CODE:$?" `
    -ScriptType Bash -GuestCredential $cred `
    -ErrorAction SilentlyContinue -ErrorVariable scriptErr

if ($scriptErr) {
    Write-Warning "VMware Tools issue: $scriptErr"
} elseif ($result.ScriptOutput -notmatch "EXIT_CODE:0") {
    Write-Warning "Script failed: $($result.ScriptOutput)"
} else {
    Write-Output "Success: $($result.ScriptOutput)"
}
```

### Mistake 6: Copy-VMGuestFile Without Checking Tools

```powershell
# WRONG — Assumes VMware Tools is running
Copy-VMGuestFile -Source "file.sh" -Destination "/tmp/" -VM $vm -LocalToGuest -GuestCredential $cred

# CORRECT — Check Tools status first
$guest = Get-VMGuest -VM $vm
if ($guest.ToolsStatus -ne "toolsOk") {
    Write-Warning "VMware Tools status: $($guest.ToolsStatus) — cannot copy files"
    # Fallback: use SSH via Posh-SSH module instead
} else {
    Copy-VMGuestFile -Source "file.sh" -Destination "/tmp/" -VM $vm `
        -LocalToGuest -GuestCredential $cred -Force -Confirm:$false
}
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-VM` | Find VMs | `-Name`, `-Server`, `-Location`, `-Tag`, `-Datastore` |
| `New-VM` | Create VM | `-Name`, `-Template`, `-VMHost`, `-ResourcePool`, `-Datastore`, `-DiskGB`, `-MemoryGB`, `-NumCpu` |
| `Set-VM` | Modify VM | `-Name`, `-NumCpu`, `-MemoryGB`, `-GuestId`, `-Notes`, `-ToTemplate` |
| `Remove-VM` | Delete VM | `-DeletePermanently` (also removes disks), `-RunAsync` |
| `Start-VM` | Power on | `-RunAsync` |
| `Stop-VM` | Hard power off | `-Kill` (force), `-RunAsync` |
| `Stop-VMGuest` | Graceful shutdown | Via VMware Tools — preferred for production |
| `Restart-VM` | Hard restart | Use `Restart-VMGuest` for graceful reboot |
| `Suspend-VM` | Suspend to disk | Saves memory state to .vmss file |
| `Get-Snapshot` | List snapshots | `-Name`, `-VM` |
| `New-Snapshot` | Create snapshot | `-Name`, `-Description`, `-Memory`, `-Quiesce` |
| `Remove-Snapshot` | Delete snapshot | `-RemoveChildren`, `-RunAsync`, `-Confirm:$false` |
| `Set-Snapshot` | Revert to snapshot | `-Name`, `-Description` |
| `Move-VM` | vMotion/migrate | `-Destination` (host), `-Datastore`, `-VMotionPriority`, `-DiskStorageFormat` |
| `Invoke-VMScript` | Run in guest | `-ScriptText`, `-ScriptType` (Bash/PowerShell/Bat), `-GuestCredential` |
| `Copy-VMGuestFile` | File transfer | `-Source`, `-Destination`, `-LocalToGuest`/`-GuestToLocal`, `-GuestCredential` |
| `Get-VMGuest` | Guest OS info | Returns IP, hostname, Tools status, OS name |
| `Wait-Tools` | Wait for Tools | `-TimeoutSeconds` |
| `Get-VMQuestion` | Pending questions | VM may be waiting for user input (e.g., "moved or copied?") |
| `Set-VMQuestion` | Answer question | `-DefaultOption` or `-Option` |
| `Unlock-VM` | Unlock stuck VM | When VM is locked by another operation |
| `Get-Template` | Find templates | `-Name`, `-Location`, `-Datastore` |
| `New-Template` | Create template | `-VM` (convert VM to template), `-Name` |

---
name: powercli-security-permissions
description: "VMware PowerCLI 13.3 — Roles, permissions, privileges, key providers, vTPM, Trust Authority, VM encryption, security policies. Covers Get-VIPermission, New-VIPermission, Get-VIRole, New-VIRole, Get-VIPrivilege, Get-VIAccount, Get-SecurityInfo, Get-VTpm, New-VTpm, Get-KeyProvider, Register-KeyProvider, Get-TrustAuthorityCluster"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,security,permissions,roles,privileges,tpm,encryption,trust-authority,key-provider,certificates,audit,rbac,Get-VIPermission,New-VIPermission,Set-VIPermission,Remove-VIPermission,Get-VIRole,New-VIRole,Set-VIRole,Remove-VIRole,Get-VIPrivilege,Get-VIPrivilegeReport,Get-VIAccount,Get-SecurityInfo,Get-SecurityPolicy,Set-SecurityPolicy,Get-VTpm,New-VTpm,Set-VTpm,Remove-VTpm,Get-VTpmCertificate,Get-VTpmCSR,Get-KeyProvider,Set-KeyProvider,Register-KeyProvider,Unregister-KeyProvider,Export-KeyProvider,Import-KeyProvider,Add-KeyManagementServer,Set-KeyManagementServer,Remove-KeyManagementServer,Get-KeyManagementServer,Get-TrustAuthorityCluster,Set-TrustAuthorityCluster,Get-TrustAuthorityKeyProvider,New-TrustAuthorityKeyProvider,Set-TrustAuthorityKeyProvider,Remove-TrustAuthorityKeyProvider,Get-TrustAuthorityKeyProviderServer,Add-TrustAuthorityKeyProviderServer,Remove-TrustAuthorityKeyProviderServer,Get-TrustAuthorityKeyProviderServerCertificate,Add-TrustAuthorityKeyProviderServerCertificate,Set-TrustAuthorityKeyProviderServerCertificate,Remove-TrustAuthorityKeyProviderServerCertificate,Get-TrustAuthorityKeyProviderClientCertificate,New-TrustAuthorityKeyProviderClientCertificate,Set-TrustAuthorityKeyProviderClientCertificate,Export-TrustAuthorityKeyProviderClientCertificate,Get-TrustAuthorityKeyProviderClientCertificateCSR,New-TrustAuthorityKeyProviderClientCertificateCSR,Get-TrustAuthorityKeyProviderService,Get-TrustAuthorityAttestationService,Get-TrustAuthorityServicesStatus,Export-TrustAuthorityServicesInfo,Import-TrustAuthorityServicesInfo,Get-TrustAuthorityPrincipal,New-TrustAuthorityPrincipal,Remove-TrustAuthorityPrincipal,Get-TrustAuthorityTpm2AttestationSettings,Set-TrustAuthorityTpm2AttestationSettings,Get-TrustAuthorityTpm2CACertificate,New-TrustAuthorityTpm2CACertificate,Remove-TrustAuthorityTpm2CACertificate,Get-TrustAuthorityTpm2EndorsementKey,New-TrustAuthorityTpm2EndorsementKey,Remove-TrustAuthorityTpm2EndorsementKey,Export-Tpm2CACertificate,Export-Tpm2EndorsementKey,Get-Tpm2EndorsementKey,Add-AttestationServiceInfo,Remove-AttestationServiceInfo,Get-AttestationServiceInfo,Add-KeyProviderServiceInfo,Remove-KeyProviderServiceInfo,Get-KeyProviderServiceInfo,Add-EntityDefaultKeyProvider,Remove-EntityDefaultKeyProvider,Get-TrustedPrincipal,Export-TrustedPrincipal,Get-VDSecurityPolicy,Set-VDSecurityPolicy,New-VISamlSecurityContext,Get-VIOAuth2Client,New-VIOAuth2Client,Set-VIOAuth2Client,Remove-VIOAuth2Client,Start-VIOAuth2ClientSecretRotation,Complete-VIOAuth2ClientSecretRotation"
---

# VMware PowerCLI — Security & Permissions

## Golden Rule

**vSphere security model: Users -> Roles -> Permissions -> Propagation.** Every permission assignment binds a user/group to a role on an inventory object. Roles are bundles of privileges. Propagation controls whether child objects inherit the permission.

| Concept | What It Is | Key Cmdlets | Critical Notes |
|---------|-----------|-------------|----------------|
| Privileges | Atomic operations (e.g., VirtualMachine.Interact.PowerOn) | `Get-VIPrivilege` | ~400+ privileges in vSphere — never grant more than needed |
| Roles | Named bundles of privileges | `Get-VIRole`, `New-VIRole`, `Set-VIRole` | Built-in roles (Admin, ReadOnly, NoAccess) cannot be modified |
| Permissions | Binding of user + role + inventory object | `Get-VIPermission`, `New-VIPermission` | `-Propagate $true` makes children inherit — use with caution |
| Accounts | Local ESXi or vCenter SSO users | `Get-VIAccount` | Prefer SSO/AD groups over local accounts for production |
| Security Policies | VM encryption, vTPM, security posture | `Get-SecurityPolicy`, `Set-SecurityPolicy` | Requires key providers configured first |
| Key Providers | KMS/NKP for VM encryption | `Get-KeyProvider`, `Register-KeyProvider` | Must be trusted by vCenter before use |
| vTPM | Virtual Trusted Platform Module | `Get-VTpm`, `New-VTpm` | Requires VM encryption (key provider + storage policy) |
| Trust Authority | vSphere 7+ attestation framework | `Get-TrustAuthorityCluster` | Separates trust decisions from workload clusters |

## Scenario: Audit Permissions Across All Inventory Objects

The most critical security task: know who has access to what across your entire vSphere environment.

```powershell
# Connect to vCenter
$vcenter = "vcenter.example.com"
$cred = Get-Credential -UserName "admin@vsphere.local"
Connect-VIServer -Server $vcenter -Credential $cred

# Full permission audit — every permission on every object
$allPerms = Get-VIPermission -Server $vcenter
$allPerms | Select-Object @{N='Entity';E={$_.Entity.Name}},
    @{N='EntityType';E={$_.Entity.GetType().Name}},
    Principal, Role, Propagate |
    Sort-Object EntityType, Entity |
    Format-Table -AutoSize

# Export to CSV for compliance review
$allPerms | Select-Object @{N='Entity';E={$_.Entity.Name}},
    @{N='EntityType';E={$_.EntityId}},
    Principal, Role, Propagate |
    Export-Csv -Path "C:\Reports\vsphere-permissions-$(Get-Date -Format 'yyyyMMdd').csv" -NoTypeInformation

# Find all users with Administrator role (high-risk)
$adminPerms = Get-VIPermission -Server $vcenter |
    Where-Object { $_.Role -eq "Admin" }
Write-Output "=== ADMIN-LEVEL PERMISSIONS ($($adminPerms.Count) total) ==="
$adminPerms | Select-Object @{N='Entity';E={$_.Entity.Name}}, Principal, Propagate |
    Format-Table -AutoSize

# Find permissions that propagate from datacenter level (overly broad)
$broadPerms = Get-VIPermission -Server $vcenter |
    Where-Object { $_.Propagate -eq $true -and $_.Entity.GetType().Name -eq "Datacenter" }
Write-Output "=== DATACENTER-LEVEL PROPAGATING PERMISSIONS ==="
$broadPerms | Select-Object @{N='Datacenter';E={$_.Entity.Name}}, Principal, Role |
    Format-Table -AutoSize

# Generate privilege report — shows what each user can actually do
Get-VIPrivilegeReport -Server $vcenter |
    Select-Object Principal, Entity, Privilege, IsGranted |
    Export-Csv -Path "C:\Reports\privilege-report-$(Get-Date -Format 'yyyyMMdd').csv" -NoTypeInformation
```

CRITICAL: Run permission audits monthly. Stale permissions from departed employees or completed projects are the most common security gap in vSphere environments.

## Scenario: Create Custom Roles with Specific Privileges

Never use the built-in Administrator role when a subset of privileges will do. Create custom roles that follow least-privilege.

```powershell
# List all available privileges to find what you need
Get-VIPrivilege -Server $vcenter | Select-Object Id, Name, Description |
    Where-Object { $_.Id -like "*VirtualMachine*" } |
    Sort-Object Id | Format-Table -AutoSize

# Create a "VM Operator" role — can power on/off and console, nothing else
$vmOperatorPrivs = Get-VIPrivilege -Id @(
    "VirtualMachine.Interact.PowerOn",
    "VirtualMachine.Interact.PowerOff",
    "VirtualMachine.Interact.Reset",
    "VirtualMachine.Interact.ConsoleInteract",
    "VirtualMachine.Interact.DeviceConnection",
    "VirtualMachine.State.CreateSnapshot",
    "VirtualMachine.State.RemoveSnapshot",
    "VirtualMachine.State.RevertToSnapshot"
) -Server $vcenter

New-VIRole -Name "VM-Operator" -Privilege $vmOperatorPrivs -Server $vcenter

# Create a "VM Provisioner" role — can create and configure VMs
$vmProvisionerPrivs = Get-VIPrivilege -Id @(
    "VirtualMachine.Inventory.Create",
    "VirtualMachine.Inventory.Delete",
    "VirtualMachine.Inventory.Register",
    "VirtualMachine.Inventory.Unregister",
    "VirtualMachine.Config.AddExistingDisk",
    "VirtualMachine.Config.AddNewDisk",
    "VirtualMachine.Config.AddRemoveDevice",
    "VirtualMachine.Config.CPUCount",
    "VirtualMachine.Config.Memory",
    "VirtualMachine.Config.Settings",
    "VirtualMachine.Config.Resource",
    "VirtualMachine.Config.AdvancedConfig",
    "VirtualMachine.Provisioning.DeployTemplate",
    "VirtualMachine.Provisioning.CloneTemplate",
    "VirtualMachine.Provisioning.Clone",
    "Resource.AssignVMToPool",
    "Datastore.AllocateSpace",
    "Network.Assign"
) -Server $vcenter

New-VIRole -Name "VM-Provisioner" -Privilege $vmProvisionerPrivs -Server $vcenter

# Modify an existing custom role — add snapshot privileges
$existingRole = Get-VIRole -Name "VM-Operator" -Server $vcenter
$snapshotPrivs = Get-VIPrivilege -Id @(
    "VirtualMachine.State.CreateSnapshot",
    "VirtualMachine.State.RemoveSnapshot"
) -Server $vcenter
Set-VIRole -Role $existingRole -AddPrivilege $snapshotPrivs -Server $vcenter

# List all custom roles (non-system)
Get-VIRole -Server $vcenter | Where-Object { $_.IsSystem -eq $false } |
    Select-Object Name, @{N='PrivilegeCount';E={($_ | Get-VIPrivilege).Count}} |
    Format-Table -AutoSize

# Inspect exactly what privileges a role grants
Get-VIRole -Name "VM-Operator" -Server $vcenter | Get-VIPrivilege |
    Select-Object Id, Name | Sort-Object Id | Format-Table -AutoSize
```

CRITICAL: Never modify built-in roles (Admin, ReadOnly, NoAccess) — they are system roles. Always create custom roles and name them descriptively so auditors can understand their purpose.

## Scenario: Manage User Accounts and Assign Permissions

Bind users/groups to roles on specific inventory objects. Use AD/SSO groups whenever possible.

```powershell
# List all accounts known to vCenter (SSO users)
Get-VIAccount -Server $vcenter |
    Select-Object Name, Domain, Description | Format-Table -AutoSize

# List only local ESXi accounts (when connected directly to ESXi)
Get-VIAccount -Server "esxi01.example.com" |
    Select-Object Name, Description | Format-Table -AutoSize

# Assign the VM-Operator role to an AD group on a specific cluster
$cluster = Get-Cluster -Name "Production-Cluster" -Server $vcenter
New-VIPermission -Entity $cluster `
    -Principal "CORP\VM-Operators" `
    -Role "VM-Operator" `
    -Propagate $true `
    -Server $vcenter

# Assign read-only access to a specific folder (no propagation)
$folder = Get-Folder -Name "Dev-VMs" -Type VM -Server $vcenter
New-VIPermission -Entity $folder `
    -Principal "CORP\dev-team" `
    -Role "ReadOnly" `
    -Propagate $false `
    -Server $vcenter

# Grant VM-Provisioner role at datacenter level with propagation
$dc = Get-Datacenter -Name "DC-East" -Server $vcenter
New-VIPermission -Entity $dc `
    -Principal "CORP\VM-Provisioners" `
    -Role "VM-Provisioner" `
    -Propagate $true `
    -Server $vcenter

# Change an existing permission — upgrade from ReadOnly to VM-Operator
$perm = Get-VIPermission -Entity $cluster -Principal "CORP\john.doe" -Server $vcenter
Set-VIPermission -Permission $perm -Role "VM-Operator" -Server $vcenter

# Remove a stale permission
$stalePerm = Get-VIPermission -Principal "CORP\former-employee" -Server $vcenter
if ($stalePerm) {
    $stalePerm | Remove-VIPermission -Confirm:$false
    Write-Output "Removed $($stalePerm.Count) permissions for former employee"
}

# Bulk permission cleanup — find and remove all permissions for departed users
$departedUsers = @("CORP\jane.smith", "CORP\bob.jones", "CORP\old-service-account")
foreach ($user in $departedUsers) {
    $perms = Get-VIPermission -Principal $user -Server $vcenter
    if ($perms) {
        Write-Output "Removing $($perms.Count) permissions for $user"
        $perms | Remove-VIPermission -Confirm:$false
    }
}
```

CRITICAL: Always use AD/SSO groups (e.g., `CORP\VM-Operators`) instead of individual user accounts. When someone leaves the team, removing them from the AD group automatically revokes all vSphere permissions.

## Scenario: Security Info and Security Policies

Query and enforce security posture on VMs — encryption status, vTPM presence, secure boot.

```powershell
# Get security information for all VMs
Get-VM -Server $vcenter | Get-SecurityInfo |
    Select-Object @{N='VM';E={$_.Entity.Name}},
        IsEncrypted, IsEncryptionRequired,
        @{N='HasVTpm';E={$_.VTpm -ne $null}} |
    Format-Table -AutoSize

# Find all VMs that are NOT encrypted but should be (compliance check)
$unencrypted = Get-VM -Server $vcenter | Get-SecurityInfo |
    Where-Object { $_.IsEncrypted -eq $false }
Write-Output "=== UNENCRYPTED VMs ($($unencrypted.Count) total) ==="
$unencrypted | Select-Object @{N='VM';E={$_.Entity.Name}} | Format-Table

# Get security policy for a specific VM
$vm = Get-VM -Name "secure-db-01" -Server $vcenter
Get-SecurityPolicy -VM $vm -Server $vcenter

# Set security policy — require encryption on a VM
Set-SecurityPolicy -VM $vm -VTpmRequired $true -Server $vcenter

# VDS (Distributed Switch) security policies
Get-VDSecurityPolicy -VDPortgroup "Production-PG" -Server $vcenter
Set-VDSecurityPolicy -VDPortgroup "Production-PG" `
    -AllowPromiscuous $false `
    -ForgedTransmits $false `
    -MacChanges $false `
    -Server $vcenter
```

## Scenario: Virtual TPM Management (Encrypted VMs)

vTPM enables Windows 11, BitLocker, Credential Guard, and measured boot inside VMs. Requires a key provider configured first.

```powershell
# List all VMs with vTPM
Get-VM -Server $vcenter | Get-VTpm |
    Select-Object @{N='VM';E={$_.VM.Name}}, Id |
    Format-Table -AutoSize

# Add vTPM to an existing VM (VM must be powered off, encryption key provider required)
$vm = Get-VM -Name "win11-desktop" -Server $vcenter
if ((Get-VM $vm).PowerState -ne "PoweredOff") {
    Stop-VMGuest -VM $vm -Confirm:$false
    do { Start-Sleep 5 } while ((Get-VM $vm.Name).PowerState -ne "PoweredOff")
}
New-VTpm -VM $vm -Server $vcenter

# Verify vTPM was added
Get-VTpm -VM $vm -Server $vcenter

# Get vTPM certificate (for attestation verification)
Get-VTpmCertificate -VTpm (Get-VTpm -VM $vm) -Server $vcenter

# Get vTPM Certificate Signing Request
Get-VTpmCSR -VTpm (Get-VTpm -VM $vm) -Server $vcenter

# Remove vTPM from a VM (VM must be powered off)
$vtpm = Get-VTpm -VM $vm -Server $vcenter
Remove-VTpm -VTpm $vtpm -Confirm:$false -Server $vcenter

# Audit: find all VMs that should have vTPM but do not
$allVMs = Get-VM -Server $vcenter
$vmsWithVTpm = Get-VM -Server $vcenter | Get-VTpm | Select-Object -ExpandProperty VM
$vmsWithoutVTpm = $allVMs | Where-Object { $_.Name -notin $vmsWithVTpm.Name }
Write-Output "=== VMs WITHOUT vTPM ($($vmsWithoutVTpm.Count)) ==="
$vmsWithoutVTpm | Select-Object Name, GuestId, PowerState |
    Where-Object { $_.GuestId -like "*windows11*" -or $_.GuestId -like "*windows2022*" } |
    Format-Table -AutoSize
```

CRITICAL: vTPM requires a key provider (Standard or Native) configured on vCenter. Without a key provider, `New-VTpm` will fail. The VM also becomes encrypted when vTPM is added, so ensure your backup solution supports encrypted VMs.

## Scenario: Key Provider Management (VM Encryption)

Key providers supply encryption keys for VM encryption, vTPM, and vSAN encryption. vSphere supports Standard (KMS), Native (NKP, vSphere 7.0u2+), and Trusted (Trust Authority) key providers.

```powershell
# List all key providers configured on vCenter
Get-KeyProvider -Server $vcenter |
    Select-Object Name, Type, DefaultForSystem |
    Format-Table -AutoSize

# Register a new Native Key Provider (NKP, no external KMS needed)
Register-KeyProvider -Name "NativeKP-Prod" -Type NativeKeyProvider -Server $vcenter

# Set the new key provider as the default for the vCenter
Set-KeyProvider -KeyProvider (Get-KeyProvider -Name "NativeKP-Prod") `
    -DefaultForSystem $true -Server $vcenter

# Add a KMIP-based Key Management Server to a standard key provider
Add-KeyManagementServer -Name "KMIP-Server-01" `
    -KeyProvider "StandardKP-Prod" `
    -Address "kms.example.com" `
    -Port 5696 `
    -TrustKeyManagementServer $true `
    -Server $vcenter

# List KMS servers in a key provider
Get-KeyManagementServer -KeyProvider "StandardKP-Prod" -Server $vcenter |
    Select-Object Name, Address, Port | Format-Table -AutoSize

# Configure KMS server credentials
$kmsCred = Get-Credential -Message "KMS Server Credentials"
Set-KeyManagementServer -KeyManagementServer "KMIP-Server-01" `
    -Credential $kmsCred -Server $vcenter

# Set a key provider as default for a specific cluster
$cluster = Get-Cluster -Name "Secure-Cluster" -Server $vcenter
Add-EntityDefaultKeyProvider -KeyProvider (Get-KeyProvider -Name "NativeKP-Prod") `
    -Entity $cluster -Server $vcenter

# Export key provider backup (CRITICAL for disaster recovery)
Export-KeyProvider -KeyProvider (Get-KeyProvider -Name "NativeKP-Prod") `
    -FilePath "C:\Backups\nkp-backup-$(Get-Date -Format 'yyyyMMdd').p12" `
    -Server $vcenter

# Import key provider from backup
Import-KeyProvider -FilePath "C:\Backups\nkp-backup-20260401.p12" `
    -Name "NativeKP-Restored" -Server $vcenter

# Remove a KMS server (careful — VMs using its keys will be inaccessible)
Remove-KeyManagementServer -KeyManagementServer "KMIP-Server-Old" `
    -Confirm:$false -Server $vcenter

# Unregister a key provider entirely
Unregister-KeyProvider -KeyProvider (Get-KeyProvider -Name "OldProvider") `
    -Confirm:$false -Server $vcenter
```

CRITICAL: Always export/backup key providers before making changes. If the key provider is lost and no backup exists, all encrypted VMs and vTPM-enabled VMs become permanently inaccessible. Store backups offline in a secure location.

## Scenario: Certificate and Trust Authority Management (vSphere 7+)

Trust Authority separates attestation and key management from workload clusters, so a compromised ESXi host cannot access encryption keys.

```powershell
# --- TRUST AUTHORITY CLUSTER SETUP ---

# List Trust Authority clusters
Get-TrustAuthorityCluster -Server $vcenter |
    Select-Object Name, State | Format-Table -AutoSize

# Enable Trust Authority on a cluster (changes cluster state)
$taCluster = Get-Cluster -Name "TA-Cluster" -Server $vcenter
Set-TrustAuthorityCluster -Cluster $taCluster -State Enabled -Server $vcenter

# Check Trust Authority services status
Get-TrustAuthorityServicesStatus -TrustAuthorityCluster $taCluster -Server $vcenter

# --- ATTESTATION SERVICE ---

# Get attestation services running on Trust Authority cluster
Get-TrustAuthorityAttestationService -TrustAuthorityCluster $taCluster -Server $vcenter

# Configure TPM 2.0 attestation settings
Get-TrustAuthorityTpm2AttestationSettings -TrustAuthorityCluster $taCluster -Server $vcenter
Set-TrustAuthorityTpm2AttestationSettings -TrustAuthorityCluster $taCluster `
    -RequireEndorsementKey $true -Server $vcenter

# --- TPM 2.0 ENDORSEMENT KEYS ---

# Register ESXi host TPM endorsement keys with Trust Authority
$endorsementKey = Get-Tpm2EndorsementKey -VMHost "esxi01.example.com" -Server $vcenter
New-TrustAuthorityTpm2EndorsementKey -TrustAuthorityCluster $taCluster `
    -EndorsementKey $endorsementKey -Server $vcenter

# List registered endorsement keys
Get-TrustAuthorityTpm2EndorsementKey -TrustAuthorityCluster $taCluster -Server $vcenter

# --- TPM 2.0 CA CERTIFICATES ---

# Register CA certificate for TPM attestation
Export-Tpm2CACertificate -VMHost "esxi01.example.com" `
    -FilePath "C:\Certs\tpm2-ca.pem" -Server $vcenter

New-TrustAuthorityTpm2CACertificate -TrustAuthorityCluster $taCluster `
    -FilePath "C:\Certs\tpm2-ca.pem" -Server $vcenter

# --- KEY PROVIDER SERVICE ---

# Get key provider services on the Trust Authority cluster
Get-TrustAuthorityKeyProviderService -TrustAuthorityCluster $taCluster -Server $vcenter

# Create a Trust Authority key provider (uses KMS behind the scenes)
New-TrustAuthorityKeyProvider -TrustAuthorityCluster $taCluster `
    -Name "TA-KeyProvider" -Server $vcenter

# Add KMS server to Trust Authority key provider
Add-TrustAuthorityKeyProviderServer -TrustAuthorityKeyProvider "TA-KeyProvider" `
    -Name "KMS-01" -Address "kms.example.com" -Port 5696 -Server $vcenter

# Manage server certificates for KMS trust
Get-TrustAuthorityKeyProviderServerCertificate -TrustAuthorityKeyProviderServer "KMS-01" `
    -Server $vcenter

# --- CLIENT CERTIFICATES ---

# Generate CSR for Trust Authority key provider client cert
New-TrustAuthorityKeyProviderClientCertificateCSR `
    -TrustAuthorityKeyProvider "TA-KeyProvider" -Server $vcenter

# After signing CSR externally, import the signed client certificate
New-TrustAuthorityKeyProviderClientCertificate `
    -TrustAuthorityKeyProvider "TA-KeyProvider" `
    -FilePath "C:\Certs\signed-client.pem" -Server $vcenter

# --- TRUSTED PRINCIPALS ---

# Register workload vCenter as a trusted principal
$principal = Get-TrustedPrincipal -Server "workload-vcenter.example.com"
New-TrustAuthorityPrincipal -TrustAuthorityCluster $taCluster `
    -Principal $principal -Server $vcenter

# --- EXPORT/IMPORT SERVICES INFO (for workload vCenter) ---

# Export Trust Authority services info
Export-TrustAuthorityServicesInfo -TrustAuthorityCluster $taCluster `
    -FilePath "C:\Config\ta-services-info.json" -Server $vcenter

# Import on workload vCenter
Import-TrustAuthorityServicesInfo `
    -FilePath "C:\Config\ta-services-info.json" `
    -Server "workload-vcenter.example.com"
```

CRITICAL: Trust Authority setup is a multi-step process involving both the Trust Authority cluster and the workload cluster. Test in a lab first. Misconfiguration can lock out all encrypted workloads.

## Common Mistakes

### Mistake 1: Granting Administrator Role at Datacenter Level with Propagation

```powershell
# WRONG — gives full admin access to EVERYTHING under the datacenter
New-VIPermission -Entity (Get-Datacenter "Production") `
    -Principal "CORP\john.doe" `
    -Role "Admin" `
    -Propagate $true

# CORRECT — create a custom role with only needed privileges, scope to specific objects
New-VIPermission -Entity (Get-Cluster "Web-Cluster") `
    -Principal "CORP\john.doe" `
    -Role "VM-Operator" `
    -Propagate $true
```

### Mistake 2: Not Checking Existing Permissions Before Adding

```powershell
# WRONG — blindly adds permission, may create duplicates or conflicts
New-VIPermission -Entity $cluster -Principal "CORP\team" -Role "VM-Operator" -Propagate $true

# CORRECT — check first, then add or update
$existing = Get-VIPermission -Entity $cluster -Principal "CORP\team" -Server $vcenter
if ($existing) {
    Write-Output "Permission already exists with role: $($existing.Role)"
    # Update if different role is needed
    Set-VIPermission -Permission $existing -Role "VM-Operator"
} else {
    New-VIPermission -Entity $cluster -Principal "CORP\team" -Role "VM-Operator" -Propagate $true
}
```

### Mistake 3: Forgetting -Propagate When Permissions Should Inherit

```powershell
# WRONG — permission applies ONLY to the folder, not VMs inside it
New-VIPermission -Entity (Get-Folder "Production-VMs") `
    -Principal "CORP\operators" -Role "VM-Operator"
# Users can see the folder but cannot interact with any VMs inside!

# CORRECT — set -Propagate $true so child objects inherit the permission
New-VIPermission -Entity (Get-Folder "Production-VMs") `
    -Principal "CORP\operators" -Role "VM-Operator" `
    -Propagate $true
```

### Mistake 4: Using Local Accounts Instead of AD/SSO Groups

```powershell
# WRONG — local accounts per host, no centralized management
# When the employee leaves, you must remove from EVERY ESXi host
New-VIPermission -Entity $cluster -Principal "localuser1" -Role "VM-Operator"

# CORRECT — use Active Directory groups managed centrally
New-VIPermission -Entity $cluster -Principal "CORP\VM-Operators-Team" `
    -Role "VM-Operator" -Propagate $true
# Employee leaves -> remove from AD group -> vSphere access revoked everywhere
```

### Mistake 5: Not Auditing Permissions Regularly

```powershell
# WRONG — set permissions once and never review them
# 18 months later: 47 stale permissions from departed employees, 3 contractor accounts
# still have Admin role, nobody knows who "svc-old-project" is

# CORRECT — scheduled monthly audit with automatic reporting
$allPerms = Get-VIPermission -Server $vcenter
$report = $allPerms | Select-Object @{N='Entity';E={$_.Entity.Name}},
    @{N='Type';E={$_.Entity.GetType().Name}},
    Principal, Role, Propagate

# Flag high-risk items
$highRisk = $report | Where-Object { $_.Role -eq "Admin" -and $_.Propagate -eq $true }
if ($highRisk.Count -gt 5) {
    Write-Warning "AUDIT: $($highRisk.Count) propagating Admin permissions found — review immediately"
}
$report | Export-Csv "C:\Audits\permissions-$(Get-Date -Format 'yyyyMMdd').csv" -NoTypeInformation
```

### Mistake 6: Deleting Key Provider Without Backup

```powershell
# WRONG — unregister key provider with no backup; all encrypted VMs become inaccessible
Unregister-KeyProvider -KeyProvider (Get-KeyProvider "NativeKP-Prod") -Confirm:$false
# DISASTER: all encrypted VMs and vTPM VMs are now permanently locked

# CORRECT — always export backup FIRST, verify backup, then proceed
Export-KeyProvider -KeyProvider (Get-KeyProvider "NativeKP-Prod") `
    -FilePath "C:\Backups\nkp-export-$(Get-Date -Format 'yyyyMMdd').p12"
# Verify the backup file exists and is non-empty
$backup = Get-Item "C:\Backups\nkp-export-*.p12" | Sort-Object LastWriteTime -Descending | Select-Object -First 1
if ($backup.Length -gt 0) {
    Write-Output "Backup verified: $($backup.FullName) ($($backup.Length) bytes)"
} else {
    Write-Error "Backup failed — DO NOT proceed with removal"
}
```

### Mistake 7: Adding vTPM Without Key Provider Configured

```powershell
# WRONG — key provider not set up, New-VTpm fails with cryptic error
New-VTpm -VM (Get-VM "win11-vm")
# Error: "The operation is not supported on the object"

# CORRECT — verify key provider exists and is default before adding vTPM
$kp = Get-KeyProvider -Server $vcenter | Where-Object { $_.DefaultForSystem -eq $true }
if (-not $kp) {
    Write-Error "No default key provider configured — set one up first"
    Write-Output "Run: Register-KeyProvider -Name 'NativeKP' -Type NativeKeyProvider"
} else {
    Write-Output "Using key provider: $($kp.Name)"
    New-VTpm -VM (Get-VM "win11-vm") -Server $vcenter
}
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-VIPermission` | List permissions on inventory objects | `-Entity`, `-Principal`, `-Server` |
| `New-VIPermission` | Assign user/group + role to an object | `-Entity`, `-Principal`, `-Role`, `-Propagate` |
| `Set-VIPermission` | Modify existing permission | `-Permission`, `-Role`, `-Propagate` |
| `Remove-VIPermission` | Revoke a permission | `-Permission`, `-Confirm:$false` |
| `Get-VIRole` | List roles (built-in + custom) | `-Name`, `-Server` |
| `New-VIRole` | Create custom role | `-Name`, `-Privilege` |
| `Set-VIRole` | Add/remove privileges from a role | `-Role`, `-AddPrivilege`, `-RemovePrivilege` |
| `Remove-VIRole` | Delete custom role | `-Role`, `-Force` |
| `Get-VIPrivilege` | List available privileges | `-Id` (e.g., `VirtualMachine.Interact.PowerOn`) |
| `Get-VIPrivilegeReport` | Detailed privilege audit per user/object | `-Entity`, `-Principal` |
| `Get-VIAccount` | List user accounts | `-Domain`, `-Server` |
| `Get-SecurityInfo` | VM encryption/vTPM status | `-VM`, `-Server` |
| `Get-SecurityPolicy` | VM security policy settings | `-VM`, `-Server` |
| `Set-SecurityPolicy` | Enforce security requirements | `-VTpmRequired`, `-Server` |
| `Get-VTpm` | List virtual TPMs | `-VM`, `-Server` |
| `New-VTpm` | Add vTPM to VM | `-VM` (requires key provider) |
| `Remove-VTpm` | Remove vTPM from VM | `-VTpm`, `-Confirm:$false` |
| `Get-VTpmCertificate` | Get vTPM attestation certificate | `-VTpm` |
| `Get-VTpmCSR` | Get vTPM certificate signing request | `-VTpm` |
| `Get-KeyProvider` | List key providers (NKP, Standard, Trusted) | `-Name`, `-Server` |
| `Register-KeyProvider` | Create new key provider | `-Name`, `-Type` (NativeKeyProvider, etc.) |
| `Unregister-KeyProvider` | Remove key provider | `-KeyProvider` (BACKUP FIRST) |
| `Set-KeyProvider` | Configure key provider settings | `-DefaultForSystem` |
| `Export-KeyProvider` | Backup key provider to file | `-FilePath` (CRITICAL for DR) |
| `Import-KeyProvider` | Restore key provider from backup | `-FilePath`, `-Name` |
| `Add-KeyManagementServer` | Add KMIP server to key provider | `-Address`, `-Port`, `-KeyProvider` |
| `Get-KeyManagementServer` | List KMS servers | `-KeyProvider` |
| `Set-KeyManagementServer` | Configure KMS credentials | `-Credential` |
| `Remove-KeyManagementServer` | Remove KMS from key provider | `-KeyManagementServer` |
| `Get-TrustAuthorityCluster` | List Trust Authority clusters | `-Server` |
| `Set-TrustAuthorityCluster` | Enable/disable Trust Authority | `-State Enabled` |
| `Get-TrustAuthorityServicesStatus` | Check TA service health | `-TrustAuthorityCluster` |
| `Get-VDSecurityPolicy` | VDS port group security settings | `-VDPortgroup` |
| `Set-VDSecurityPolicy` | Set promiscuous/forged/MAC policy | `-AllowPromiscuous`, `-ForgedTransmits` |
| `Add-EntityDefaultKeyProvider` | Set default key provider per cluster | `-KeyProvider`, `-Entity` |

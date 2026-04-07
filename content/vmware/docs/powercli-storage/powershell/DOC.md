---
name: powercli-storage
description: "VMware PowerCLI 13.3 — Datastores, datastore clusters, vSAN, SPBM storage policies, virtual disks, CNS volumes, storage vMotion, capacity monitoring"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,storage,datastore,datastore-cluster,vsan,spbm,storage-policy,virtual-disk,hard-disk,vdisk,cns,thin-provisioning,thick-provisioning,storage-vmotion,capacity,Get-Datastore,New-Datastore,Set-Datastore,Remove-Datastore,Move-Datastore,Get-DatastoreCluster,New-DatastoreCluster,Set-DatastoreCluster,Remove-DatastoreCluster,Get-HardDisk,New-HardDisk,Set-HardDisk,Remove-HardDisk,Copy-HardDisk,Move-HardDisk,Get-VDisk,New-VDisk,Copy-VDisk,Remove-VDisk,Move-VDisk,Set-VDisk,Get-SpbmStoragePolicy,New-SpbmStoragePolicy,Set-SpbmStoragePolicy,Remove-SpbmStoragePolicy,Get-SpbmEntityConfiguration,Set-SpbmEntityConfiguration,Get-SpbmCompatibleStorage,Get-SpbmCapability,Get-SpbmFaultDomain,Get-SpbmPointInTimeReplica,Get-SpbmReplicationGroup,Get-SpbmReplicationPair,Get-SpbmView,Export-SpbmStoragePolicy,Import-SpbmStoragePolicy,New-SpbmRule,New-SpbmRuleSet,Start-SpbmReplicationFailover,Start-SpbmReplicationPrepareFailover,Start-SpbmReplicationPromote,Start-SpbmReplicationReverse,Start-SpbmReplicationTestFailover,Stop-SpbmReplicationTestFailover,Sync-SpbmReplicationGroup,Get-VsanClusterConfiguration,Set-VsanClusterConfiguration,Get-VsanDisk,Get-VsanDiskGroup,New-VsanDisk,New-VsanDiskGroup,Remove-VsanDisk,Remove-VsanDiskGroup,Get-VsanFaultDomain,New-VsanFaultDomain,Set-VsanFaultDomain,Remove-VsanFaultDomain,Get-VsanSpaceUsage,Get-VsanStat,Get-VsanComponent,Get-VsanDirectDisk,New-VsanDirectDisk,Remove-VsanDirectDisk,Get-VsanObject,Get-VsanRuntimeInfo,Get-VsanResyncingComponent,Get-VsanResyncingOverview,Get-VsanClusterPowerState,Get-VsanEnterMaintenanceModeReport,Get-VsanEvacuationPlan,Get-VsanEsaEligibleDisk,Get-VsanStoragePoolDisk,Add-VsanStoragePoolDisk,Remove-VsanStoragePoolDisk,Get-VsanHCIMeshDatastore,Get-VsanHCIMeshDatastoreSource,New-VsanHCIMeshDatastoreSource,Remove-VsanHCIMeshDatastoreSource,Get-VsanFileServiceDomain,New-VsanFileServiceDomain,Set-VsanFileServiceDomain,Remove-VsanFileServiceDomain,Get-VsanFileShare,New-VsanFileShare,Set-VsanFileShare,Remove-VsanFileShare,Get-VsanFileShareSnapshot,New-VsanFileShareSnapshot,Remove-VsanFileShareSnapshot,Get-VsanIscsiInitiatorGroup,New-VsanIscsiInitiatorGroup,Set-VsanIscsiInitiatorGroup,Remove-VsanIscsiInitiatorGroup,Get-VsanIscsiInitiatorGroupTargetAssociation,New-VsanIscsiInitiatorGroupTargetAssociation,Remove-VsanIscsiInitiatorGroupTargetAssociation,Get-VsanIscsiLun,New-VsanIscsiLun,Set-VsanIscsiLun,Remove-VsanIscsiLun,Get-VsanIscsiTarget,New-VsanIscsiTarget,Set-VsanIscsiTarget,Remove-VsanIscsiTarget,Add-VsanFileServiceOvf,Get-VsanFileServiceOvfInfo,Add-VsanObjectToRepairQueue,New-VsanFileServerIpConfig,New-VsanFileShareNetworkPermission,New-VsanHealthCheckThreshold,New-RemoteVsanServerClusterConfig,Get-VsanWipeDiskStatus,Start-VsanWipeDisk,Stop-VsanWipeDisk,Start-VsanCluster,Stop-VsanCluster,Start-VsanClusterDiskUpdate,Start-VsanClusterRebalance,Stop-VsanClusterRebalance,Start-VsanEncryptionConfiguration,Start-VsanRelayoutObjects,Test-VsanClusterHealth,Test-VsanNetworkPerformance,Test-VsanStoragePerformance,Update-VsanHclDatabase,Get-VsanView,Get-VasaStorageArray,Get-VvolStorageContainer,Get-CnsVolume,New-CnsVolume,Set-CnsVolume,Remove-CnsVolume,New-CnsVolumeAttachment,Remove-CnsVolumeAttachment,New-CnsVolumeMetadata,Copy-DatastoreItem,New-DatastoreDrive"
---

# VMware PowerCLI — Storage

Datastores, datastore clusters, vSAN, SPBM storage policies, virtual disks, CNS volumes. Module: VMware.VimAutomation (132 cmdlets).

## Golden Rule

**Know which storage abstraction you are working with. The cmdlet families are different, the failure modes are different, and mixing them up causes silent data loss.**

| Storage Type | When to Use | Key Cmdlets | Critical Notes |
|-------------|-------------|-------------|----------------|
| **Datastore** | Individual VMFS/NFS volumes — most common | `Get-Datastore`, `New-Datastore`, `Set-Datastore` | Always check free space before provisioning |
| **Datastore Cluster** (SDRS) | Automated load balancing across datastores | `Get-DatastoreCluster`, `New-DatastoreCluster` | SDRS must be enabled; VMs placed by recommendation |
| **vSAN** | Hyper-converged — host-local disks pooled into shared storage | `Get-VsanClusterConfiguration`, `Get-VsanDiskGroup` | Requires minimum 3 hosts; fault domains protect against rack failure |
| **SPBM (Storage Policy)** | Governance — enforce storage requirements via policy | `Get-SpbmStoragePolicy`, `Set-SpbmEntityConfiguration` | Assign policies BEFORE deploying VMs, not after |
| **CNS (Cloud Native Storage)** | Kubernetes persistent volumes on vSphere | `Get-CnsVolume`, `New-CnsVolume` | Requires vSphere CSI driver in the K8s cluster |
| **Virtual Disk** | Individual VMDK operations — resize, move, convert | `Get-HardDisk`, `New-HardDisk`, `Set-HardDisk` | Thin vs thick has major performance implications |

**Key decisions before writing any storage automation:**
1. Are you managing the physical storage layer (Datastore/vSAN) or the logical layer (HardDisk/SPBM)?
2. Will SDRS handle placement, or are you pinning VMs to specific datastores?
3. Is thin provisioning acceptable, or does the workload require guaranteed IOPS (thick eager-zeroed)?

## Scenario: Datastore Inventory and Capacity Monitoring

Capacity monitoring is the single most important storage automation. Running out of datastore space causes VM panics, snapshot failures, and silent corruption.

```powershell
# Inventory all datastores with calculated capacity fields
Get-Datastore -Server $vcenter | 
    Select-Object Name, 
        @{N='CapacityGB';E={[math]::Round($_.CapacityGB, 1)}},
        @{N='FreeGB';E={[math]::Round($_.FreeSpaceGB, 1)}},
        @{N='UsedGB';E={[math]::Round($_.CapacityGB - $_.FreeSpaceGB, 1)}},
        @{N='UsedPct';E={[math]::Round(($_.CapacityGB - $_.FreeSpaceGB) / $_.CapacityGB * 100, 1)}},
        @{N='Type';E={$_.Type}},
        @{N='State';E={$_.State}} |
    Sort-Object UsedPct -Descending | Format-Table -AutoSize
```

Build a free-space alert that flags datastores above a threshold. This is the pattern EVA uses for capacity checking before any provisioning operation.

```powershell
# Alert on datastores above 85% usage
$threshold = 85
$criticalStores = Get-Datastore -Server $vcenter | Where-Object {
    $usedPct = ($_.CapacityGB - $_.FreeSpaceGB) / $_.CapacityGB * 100
    $usedPct -ge $threshold
}

foreach ($ds in $criticalStores) {
    $usedPct = [math]::Round(($ds.CapacityGB - $ds.FreeSpaceGB) / $ds.CapacityGB * 100, 1)
    $freeGB = [math]::Round($ds.FreeSpaceGB, 1)
    Write-Warning "CRITICAL: $($ds.Name) is ${usedPct}% full — only ${freeGB} GB free"
}

# Check a specific datastore before creating a VM (EVA pattern)
function Test-DatastoreCapacity {
    param(
        [string]$DatastoreName,
        [decimal]$RequiredGB,
        [string]$Server
    )
    $ds = Get-Datastore -Name $DatastoreName -Server $Server
    if ($ds.FreeSpaceGB -lt $RequiredGB) {
        throw "Datastore '$DatastoreName' has $([math]::Round($ds.FreeSpaceGB,1)) GB free but $RequiredGB GB required"
    }
    return $true
}

# Use it before any provisioning
Test-DatastoreCapacity -DatastoreName "VMFS-Prod-01" -RequiredGB 200 -Server $vcenter
```

For datastore clusters, check the aggregate capacity and SDRS status.

```powershell
# Inventory datastore clusters with member counts and aggregated capacity
Get-DatastoreCluster -Server $vcenter | ForEach-Object {
    $members = Get-Datastore -RelatedObject $_ -Server $vcenter
    $totalGB = ($members | Measure-Object -Property CapacityGB -Sum).Sum
    $freeGB = ($members | Measure-Object -Property FreeSpaceGB -Sum).Sum
    [PSCustomObject]@{
        Cluster      = $_.Name
        Members      = $members.Count
        TotalTB      = [math]::Round($totalGB / 1024, 2)
        FreeTB       = [math]::Round($freeGB / 1024, 2)
        UsedPct      = [math]::Round(($totalGB - $freeGB) / $totalGB * 100, 1)
        SDRSEnabled  = $_.SdrsAutomationLevel -ne 'Disabled'
    }
} | Format-Table -AutoSize
```

CRITICAL: `Get-Datastore` returns provisioned capacity, not actual usage when thin provisioning is in play. Thin-provisioned VMs can over-commit a datastore — the `FreeSpaceGB` can go negative when thin disks inflate. Monitor both provisioned space and actual usage.

## Scenario: Storage Policy Management (SPBM)

Storage Policy-Based Management (SPBM) is how vSphere enforces storage requirements. Policies define what kind of storage a VM or disk needs (replication, encryption, IOPS limits), and vSphere ensures compliance.

```powershell
# List all storage policies
Get-SpbmStoragePolicy -Server $vcenter | 
    Select-Object Name, Description, 
        @{N='Rules';E={($_ | Get-SpbmStoragePolicy).AnyOfRuleSets.Count}} |
    Format-Table -AutoSize

# Find which policy is assigned to a VM and its disks
$vm = Get-VM -Name "prod-db-01" -Server $vcenter
Get-SpbmEntityConfiguration -VM $vm -Server $vcenter | 
    Select-Object Entity, StoragePolicy, ComplianceStatus | Format-Table

# Check compliance across all VMs — noncompliant means the storage 
# no longer meets the policy requirements (e.g., mirror degraded)
Get-VM -Server $vcenter | Get-SpbmEntityConfiguration -Server $vcenter |
    Where-Object { $_.ComplianceStatus -ne "compliant" } |
    Select-Object @{N='VM';E={$_.Entity.Name}}, StoragePolicy, ComplianceStatus |
    Format-Table
```

Assign and change storage policies. This is essential when migrating VMs between storage tiers.

```powershell
# Assign a storage policy to a VM (applies to VM home and all disks)
$policy = Get-SpbmStoragePolicy -Name "Gold-Replicated" -Server $vcenter
$vm = Get-VM -Name "prod-db-01" -Server $vcenter
Set-SpbmEntityConfiguration -Configuration (Get-SpbmEntityConfiguration -VM $vm) `
    -StoragePolicy $policy -Server $vcenter

# Find datastores compatible with a policy (use BEFORE creating VMs)
$policy = Get-SpbmStoragePolicy -Name "Gold-Replicated" -Server $vcenter
$compatibleDS = Get-SpbmCompatibleStorage -StoragePolicy $policy -Server $vcenter
$compatibleDS | Select-Object Name, FreeSpaceGB, Type | Format-Table

# Create a custom SPBM policy with rules
$ruleVMEncryption = New-SpbmRule -Capability (Get-SpbmCapability -Name "VASA.VMEncryption" -Server $vcenter) `
    -Value "Required"
$ruleSet = New-SpbmRuleSet -AllOfRules $ruleVMEncryption
New-SpbmStoragePolicy -Name "Encrypted-Tier" -Description "Requires encryption at rest" `
    -AnyOfRuleSets $ruleSet -Server $vcenter

# Export and import policies between vCenters
Export-SpbmStoragePolicy -StoragePolicy $policy -FilePath "C:\Policies\gold-replicated.json"
Import-SpbmStoragePolicy -FilePath "C:\Policies\gold-replicated.json" -Server $targetVcenter
```

CRITICAL: Changing a storage policy on a running VM does NOT automatically migrate data. The policy is metadata that vSphere checks for compliance. If the underlying datastore no longer satisfies the policy, the VM shows as noncompliant, but it keeps running. You must storage-vMotion to a compliant datastore to fix compliance.

## Scenario: Virtual Disk Operations

Virtual disks (VMDKs) are managed through `Get-HardDisk`, `New-HardDisk`, and `Set-HardDisk`. Understanding thin vs thick provisioning is essential for every storage operation.

| Format | Disk Behavior | IOPS | Use When |
|--------|--------------|------|----------|
| **Thin** | Allocates on write — grows as needed | Lower (first-write penalty) | Dev/test, non-critical, overcommit OK |
| **Thick Lazy Zeroed** | Full allocation, zeroed on first write | Medium | General production |
| **Thick Eager Zeroed** | Full allocation, zeroed at creation time | Highest (no first-write penalty) | Databases, latency-sensitive, FT-required |

```powershell
# List all hard disks on a VM with provisioning details
$vm = Get-VM -Name "prod-db-01" -Server $vcenter
Get-HardDisk -VM $vm | 
    Select-Object Name, 
        @{N='CapacityGB';E={$_.CapacityGB}},
        @{N='StorageFormat';E={$_.StorageFormat}},
        @{N='Filename';E={$_.Filename}},
        @{N='Datastore';E={($_.Filename -split ']')[0].TrimStart('[')}} |
    Format-Table -AutoSize

# Add a new 100GB thin disk to a VM
New-HardDisk -VM $vm -CapacityGB 100 -StorageFormat Thin `
    -Datastore "VMFS-Prod-01" -Server $vcenter

# Add a thick eager-zeroed disk for a database VM
New-HardDisk -VM $vm -CapacityGB 500 -StorageFormat EagerZeroedThick `
    -Datastore "VMFS-DB-01" -Server $vcenter

# Expand an existing disk (online — works while VM is powered on)
$disk = Get-HardDisk -VM $vm | Where-Object { $_.Name -eq "Hard disk 2" }
Set-HardDisk -HardDisk $disk -CapacityGB 200 -Confirm:$false
```

CRITICAL: `Set-HardDisk -CapacityGB` can only INCREASE the disk size, never shrink. Shrinking a VMDK requires guest OS operations (shrink the partition first, then remove and re-create the VMDK). Also, expanding a disk does NOT expand the guest partition — you must extend the filesystem inside the guest OS after.

```powershell
# Move a disk to a different datastore (storage vMotion for a single disk)
$disk = Get-HardDisk -VM $vm | Where-Object { $_.Name -eq "Hard disk 2" }
Move-HardDisk -HardDisk $disk -Datastore "VMFS-Prod-02" `
    -StorageFormat Thin -Confirm:$false

# Copy a hard disk to a new location (does not remove original)
Copy-HardDisk -HardDisk $disk -DestinationPath "[VMFS-Backup-01] backups/" `
    -DestinationStorageFormat Thin -Confirm:$false

# Remove a hard disk from a VM (detach only, keep VMDK file)
Remove-HardDisk -HardDisk $disk -Confirm:$false

# Remove a hard disk AND delete the VMDK file
Remove-HardDisk -HardDisk $disk -DeletePermanently -Confirm:$false
```

## Scenario: vSAN Operations

vSAN pools local disks from ESXi hosts into a shared datastore. It uses disk groups (one cache SSD + capacity disks) in the original architecture (OSA), or storage pools in the newer ESA architecture.

```powershell
# Check vSAN cluster configuration
$cluster = Get-Cluster -Name "vSAN-Cluster" -Server $vcenter
Get-VsanClusterConfiguration -Cluster $cluster |
    Select-Object Cluster, VsanEnabled, StretchedClusterEnabled,
        SpaceEfficiencyEnabled, EncryptionEnabled, PerformanceServiceEnabled

# View disk groups across all hosts
Get-VsanDiskGroup -Cluster $cluster | ForEach-Object {
    [PSCustomObject]@{
        Host       = $_.VMHost.Name
        DiskGroup  = $_.Name
        CacheDisk  = ($_.CacheDisk | Select-Object -First 1).CanonicalName
        CapDisks   = ($_.CapacityDisk | Measure-Object).Count
        CapacityGB = [math]::Round(($_.CapacityDisk | Measure-Object -Property CapacityGB -Sum).Sum, 1)
    }
} | Format-Table -AutoSize

# Check vSAN space usage — the most important health metric
Get-VsanSpaceUsage -Cluster $cluster | 
    Select-Object @{N='TotalCapacityGB';E={[math]::Round($_.TotalCapacityGB, 1)}},
        @{N='FreeCapacityGB';E={[math]::Round($_.FreeCapacityGB, 1)}},
        @{N='UsedPct';E={[math]::Round(($_.TotalCapacityGB - $_.FreeCapacityGB) / $_.TotalCapacityGB * 100, 1)}}
```

Fault domains partition hosts into failure zones (typically rack-aligned). vSAN distributes data replicas across fault domains so that losing an entire rack does not lose data.

```powershell
# List fault domains
Get-VsanFaultDomain -Cluster $cluster | 
    Select-Object Name, @{N='Hosts';E={($_.VMHost | ForEach-Object {$_.Name}) -join ", "}} |
    Format-Table

# Create fault domains for rack-based placement
$rack1Hosts = Get-VMHost "esxi01.example.com", "esxi02.example.com" -Server $vcenter
$rack2Hosts = Get-VMHost "esxi03.example.com", "esxi04.example.com" -Server $vcenter
$rack3Hosts = Get-VMHost "esxi05.example.com", "esxi06.example.com" -Server $vcenter

New-VsanFaultDomain -Name "Rack-A" -VMHost $rack1Hosts -Server $vcenter
New-VsanFaultDomain -Name "Rack-B" -VMHost $rack2Hosts -Server $vcenter
New-VsanFaultDomain -Name "Rack-C" -VMHost $rack3Hosts -Server $vcenter
```

Monitor vSAN health and resync status. Resyncing happens after host failures, disk replacements, or policy changes.

```powershell
# Run a comprehensive vSAN health check
Test-VsanClusterHealth -Cluster $cluster | 
    Select-Object TestName, TestHealth, TestDescription |
    Where-Object { $_.TestHealth -ne "green" } | Format-Table

# Check resync progress (critical during maintenance)
Get-VsanResyncingOverview -Cluster $cluster |
    Select-Object TotalObjectsToSync, TotalBytesToSync, TotalRecoveryETA

# Get individual resyncing components for detailed tracking
Get-VsanResyncingComponent -Cluster $cluster | 
    Select-Object ComponentUuid, ResyncReason, BytesToSync, 
        @{N='ProgressPct';E={if($_.BytesToSync -gt 0){[math]::Round(($_.BytesSynced / $_.BytesToSync) * 100, 1)}else{100}}} |
    Format-Table
```

CRITICAL: Never remove a disk group or put a host into maintenance mode without first checking the evacuation plan. Removing capacity from vSAN while objects still rely on it causes data unavailability.

```powershell
# ALWAYS check evacuation plan before maintenance
$host = Get-VMHost "esxi03.example.com" -Server $vcenter
$plan = Get-VsanEvacuationPlan -VMHost $host
if ($plan.IsFeasible -eq $false) {
    Write-Warning "Evacuation NOT feasible: $($plan.Reason)"
    Write-Warning "Cannot safely enter maintenance mode"
} else {
    Write-Output "Evacuation feasible — estimated time: $($plan.EstimatedDuration)"
}

# Get a pre-maintenance report showing what data needs to move
Get-VsanEnterMaintenanceModeReport -VMHost $host -MaintenanceMode EnsureAccessibility
```

## Scenario: Datastore Maintenance and Storage vMotion

Storage vMotion moves VM files between datastores while the VM is running. This is essential for evacuating a datastore before decommissioning, rebalancing capacity, or changing storage tiers.

```powershell
# Storage vMotion a single VM to a new datastore
$vm = Get-VM -Name "prod-web-01" -Server $vcenter
$targetDS = Get-Datastore -Name "VMFS-Prod-02" -Server $vcenter

# Check target has enough space first
$vmUsedGB = ($vm.UsedSpaceGB)
if ($targetDS.FreeSpaceGB -lt ($vmUsedGB * 1.2)) {
    Write-Warning "Target datastore too full: $([math]::Round($targetDS.FreeSpaceGB,1)) GB free, need $([math]::Round($vmUsedGB * 1.2, 1)) GB"
    return
}

Move-VM -VM $vm -Datastore $targetDS -DiskStorageFormat Thin -Server $vcenter

# Evacuate an entire datastore (move ALL VMs to another)
$sourceDS = Get-Datastore -Name "VMFS-Decomm-01" -Server $vcenter
$targetDS = Get-Datastore -Name "VMFS-Prod-02" -Server $vcenter

$vmsOnSource = Get-VM -Datastore $sourceDS -Server $vcenter
foreach ($vm in $vmsOnSource) {
    Write-Output "Migrating $($vm.Name) ($([math]::Round($vm.UsedSpaceGB, 1)) GB)..."
    Move-VM -VM $vm -Datastore $targetDS -DiskStorageFormat Thin `
        -VMotionPriority High -RunAsync -Server $vcenter
}

# Monitor migration tasks
Get-Task -Server $vcenter | 
    Where-Object { $_.Name -eq "RelocateVM_Task" -and $_.State -eq "Running" } |
    Select-Object @{N='VM';E={$_.ObjectId}}, PercentComplete, StartTime | Format-Table
```

Copy files between datastores using the PowerCLI datastore provider. This works at the file level, not the VM level.

```powershell
# Copy an ISO to a datastore
Copy-DatastoreItem -Item "C:\ISOs\rhel9.iso" `
    -Destination "vmstores:\vcenter@443\DC1\VMFS-ISO-01\ISOs\" -Force

# Copy files between datastores
Copy-DatastoreItem -Item "vmstores:\vcenter@443\DC1\VMFS-Prod-01\templates\*" `
    -Destination "vmstores:\vcenter@443\DC1\VMFS-Prod-02\templates\" `
    -Recurse -Force

# Map a datastore as a PSDrive for easy navigation
New-DatastoreDrive -Datastore (Get-Datastore "VMFS-Prod-01") -Name "prod01"
Get-ChildItem prod01: | Select-Object Name, ItemType, Length
```

## Common Mistakes

### Mistake 1: Not Checking Datastore Capacity Before VM Creation

```powershell
# WRONG — Create VM without checking space, datastore runs out during provisioning
New-VM -Name "new-server" -VMHost $esxi -Datastore "VMFS-Prod-01" `
    -DiskGB 500 -MemoryGB 32 -NumCpu 8

# CORRECT — Check free space with margin before creating
$ds = Get-Datastore -Name "VMFS-Prod-01" -Server $vcenter
$requiredGB = 500 + 32 + 10  # disk + swap (= RAM size) + overhead
if ($ds.FreeSpaceGB -lt ($requiredGB * 1.15)) {
    throw "Insufficient space: $([math]::Round($ds.FreeSpaceGB,1)) GB free, need $([math]::Round($requiredGB * 1.15, 1)) GB (with 15% buffer)"
}
New-VM -Name "new-server" -VMHost $esxi -Datastore $ds `
    -DiskGB 500 -MemoryGB 32 -NumCpu 8 -Server $vcenter
```

### Mistake 2: Using Thick Provisioning When Thin Is Appropriate

```powershell
# WRONG — Thick eager-zeroed for a dev VM wastes hours and space
New-HardDisk -VM $devVM -CapacityGB 2000 -StorageFormat EagerZeroedThick
# This takes 20+ minutes to zero 2TB and immediately reserves the full 2TB

# CORRECT — Thin for dev/test, thick eager-zeroed only for latency-critical production
New-HardDisk -VM $devVM -CapacityGB 2000 -StorageFormat Thin
# Instant creation, grows on demand

# Thick eager-zeroed is correct for production databases
New-HardDisk -VM $prodDBvm -CapacityGB 500 -StorageFormat EagerZeroedThick `
    -Datastore "VMFS-DB-01"
```

### Mistake 3: Not Specifying -DiskStorageFormat During Migration

```powershell
# WRONG — Move-VM without -DiskStorageFormat uses the source format
# If the source was thick and you want thin, you silently keep thick
Move-VM -VM $vm -Datastore $targetDS

# CORRECT — Always specify the desired storage format explicitly
Move-VM -VM $vm -Datastore $targetDS -DiskStorageFormat Thin -Server $vcenter

# Also correct — preserve original format intentionally
Move-VM -VM $vm -Datastore $targetDS -DiskStorageFormat SameAsSource -Server $vcenter
```

### Mistake 4: Ignoring SPBM Compliance Status

```powershell
# WRONG — Deploy VM, assign policy, never check compliance again
Set-SpbmEntityConfiguration -Configuration (Get-SpbmEntityConfiguration -VM $vm) `
    -StoragePolicy $goldPolicy
# VM runs for months on degraded storage, nobody notices

# CORRECT — Check compliance regularly and alert on violations
$noncompliant = Get-VM -Server $vcenter | 
    Get-SpbmEntityConfiguration -Server $vcenter |
    Where-Object { $_.ComplianceStatus -ne "compliant" -and $_.StoragePolicy }

if ($noncompliant) {
    foreach ($entity in $noncompliant) {
        Write-Warning "NONCOMPLIANT: $($entity.Entity.Name) — Policy: $($entity.StoragePolicy.Name) — Status: $($entity.ComplianceStatus)"
    }
    # Remediation: find compliant storage and migrate
    $compliantDS = Get-SpbmCompatibleStorage -StoragePolicy $goldPolicy -Server $vcenter
    Write-Output "Compatible datastores: $($compliantDS.Name -join ', ')"
}
```

### Mistake 5: Removing vSAN Disk Group Without Checking Evacuation

```powershell
# WRONG — Remove disk group immediately, causes data unavailability
$diskGroup = Get-VsanDiskGroup -VMHost "esxi03.example.com"
Remove-VsanDiskGroup -VsanDiskGroup $diskGroup -Confirm:$false
# Objects that had replicas ONLY on this disk group are now inaccessible!

# CORRECT — Check evacuation feasibility first, then evacuate data
$host = Get-VMHost "esxi03.example.com" -Server $vcenter
$report = Get-VsanEnterMaintenanceModeReport -VMHost $host -MaintenanceMode FullDataMigration

if ($report.OverallStatus -eq "red") {
    Write-Warning "Cannot safely remove disk group — data migration not feasible"
    Write-Warning "Reason: $($report.UnmovableObjects) objects cannot be relocated"
} else {
    Write-Output "Safe to proceed — evacuating data first"
    $diskGroup = Get-VsanDiskGroup -VMHost $host
    Remove-VsanDiskGroup -VsanDiskGroup $diskGroup -DataMigrationMode Full -Confirm:$false
    # Monitor resync until complete
    do {
        Start-Sleep 30
        $resync = Get-VsanResyncingOverview -Cluster (Get-Cluster -VMHost $host)
        Write-Output "Resyncing: $($resync.TotalObjectsToSync) objects remaining"
    } while ($resync.TotalObjectsToSync -gt 0)
}
```

### Mistake 6: Expanding Disk Without Extending Guest Filesystem

```powershell
# WRONG — Expand VMDK and assume the guest OS sees the space
Set-HardDisk -HardDisk $disk -CapacityGB 500 -Confirm:$false
# The VMDK is now 500GB but the guest partition is still the old size!

# CORRECT — Expand VMDK, then extend the partition inside the guest
Set-HardDisk -HardDisk $disk -CapacityGB 500 -Confirm:$false

# Linux guest: rescan and extend
Invoke-VMScript -VM $vm -ScriptType Bash -GuestCredential $cred `
    -ScriptText "echo 1 > /sys/class/block/sdb/device/rescan && growpart /dev/sdb 1 && resize2fs /dev/sdb1" `
    -ErrorAction Stop

# Windows guest: extend volume
Invoke-VMScript -VM $vm -ScriptType PowerShell -GuestCredential $cred `
    -ScriptText 'Update-Disk -Number 1; $part = Get-Partition -DiskNumber 1 -PartitionNumber 2; $size = (Get-PartitionSupportedSize -DiskNumber 1 -PartitionNumber 2).SizeMax; Resize-Partition -DiskNumber 1 -PartitionNumber 2 -Size $size' `
    -ErrorAction Stop
```

### Mistake 7: Using Get-Datastore Without Filtering in Large Environments

```powershell
# WRONG — Returns ALL datastores, can be thousands, slow and memory-heavy
$all = Get-Datastore
$target = $all | Where-Object { $_.Name -eq "VMFS-Prod-01" }

# CORRECT — Filter at the cmdlet level
$target = Get-Datastore -Name "VMFS-Prod-01" -Server $vcenter

# ALSO CORRECT — Scope by location
$clusterDS = Get-Datastore -RelatedObject (Get-Cluster "Production") -Server $vcenter
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-Datastore` | Find datastores | `-Name`, `-Server`, `-RelatedObject`, `-Location` |
| `New-Datastore` | Create VMFS/NFS datastore | `-Name`, `-VMHost`, `-Path`, `-Nfs`/`-Vmfs`, `-FileSystemVersion` |
| `Set-Datastore` | Rename or modify | `-Name`, `-MaintenanceMode`, `-CongestionThresholdMillisecond` |
| `Remove-Datastore` | Remove datastore | `-VMHost`, `-Confirm:$false` — unmounts, does NOT delete data |
| `Move-Datastore` | Move datastore to folder | `-Destination` (folder) |
| `Get-DatastoreCluster` | Find SDRS clusters | `-Name`, `-Server`, `-VM` |
| `New-DatastoreCluster` | Create SDRS cluster | `-Name`, `-Location` (datacenter/folder) |
| `Set-DatastoreCluster` | Configure SDRS | `-SdrsAutomationLevel`, `-IOLatencyThresholdMillisecond` |
| `Get-HardDisk` | List VM disks | `-VM`, `-Datastore`, `-DiskType` |
| `New-HardDisk` | Add disk to VM | `-VM`, `-CapacityGB`, `-StorageFormat` (Thin/Thick/EagerZeroedThick), `-Datastore` |
| `Set-HardDisk` | Resize/move disk | `-CapacityGB` (increase only), `-StorageFormat`, `-Datastore` |
| `Remove-HardDisk` | Remove disk | `-DeletePermanently` (also deletes VMDK file) |
| `Copy-HardDisk` | Copy VMDK | `-DestinationPath`, `-DestinationStorageFormat` |
| `Move-HardDisk` | Relocate VMDK | `-Datastore`, `-StorageFormat` |
| `Get-SpbmStoragePolicy` | List policies | `-Name`, `-Server` |
| `New-SpbmStoragePolicy` | Create policy | `-Name`, `-AnyOfRuleSets` |
| `Set-SpbmEntityConfiguration` | Assign policy to VM | `-StoragePolicy`, `-Configuration` |
| `Get-SpbmEntityConfiguration` | Check policy assignment | `-VM`, `-HardDisk` — shows ComplianceStatus |
| `Get-SpbmCompatibleStorage` | Find compliant storage | `-StoragePolicy` — returns datastores that satisfy the policy |
| `Export-SpbmStoragePolicy` | Export policy to file | `-StoragePolicy`, `-FilePath` |
| `Import-SpbmStoragePolicy` | Import policy from file | `-FilePath`, `-Name`, `-Server` |
| `Get-VsanClusterConfiguration` | vSAN cluster info | `-Cluster` — shows enabled features |
| `Get-VsanDiskGroup` | List disk groups | `-Cluster`, `-VMHost` |
| `New-VsanDiskGroup` | Create disk group | `-VMHost`, `-SsdCanonicalName`, `-DataDiskCanonicalName` |
| `Remove-VsanDiskGroup` | Remove disk group | `-DataMigrationMode` (Full/EnsureAccessibility/NoDataMigration) |
| `Get-VsanFaultDomain` | List fault domains | `-Cluster` |
| `New-VsanFaultDomain` | Create fault domain | `-Name`, `-VMHost` |
| `Get-VsanSpaceUsage` | vSAN capacity | `-Cluster` — total, free, used |
| `Get-VsanStat` | Performance stats | `-Entity`, `-Name` (IOPS, Throughput, Latency) |
| `Test-VsanClusterHealth` | Health check | `-Cluster` — returns all test results |
| `Get-VsanResyncingOverview` | Resync status | `-Cluster` — objects and bytes remaining |
| `Get-VsanEvacuationPlan` | Pre-maintenance check | `-VMHost` — is evacuation feasible? |
| `Get-VsanEnterMaintenanceModeReport` | Maintenance impact | `-VMHost`, `-MaintenanceMode` |
| `Get-CnsVolume` | List K8s PVs | `-Server` |
| `New-CnsVolume` | Create K8s PV | `-Name`, `-StoragePolicy`, `-Datastore`, `-CapacityGB` |
| `Copy-DatastoreItem` | Copy files on datastores | `-Item`, `-Destination`, `-Recurse`, `-Force` |
| `New-DatastoreDrive` | Map datastore as PSDrive | `-Datastore`, `-Name` |

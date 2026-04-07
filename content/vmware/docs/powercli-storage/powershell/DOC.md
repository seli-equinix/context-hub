---
name: powercli-storage
description: "VMware PowerCLI storage cmdlets -- vSAN disk management, disk groups, cluster configuration, and SPBM storage policies"
metadata:
  languages: "powershell"
  versions: "13.3,9.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsan,storage,spbm,storage-policy,datastore,disk-group,vmfs"
---

# VMware PowerCLI -- Storage Modules Reference

This covers the `VMware.VimAutomation.Storage` (vSAN, VMFS) and `VMware.VimAutomation.Spbm` (Storage Policy Based Management) modules.

> Ground truth: PowerCLI built-in help and Broadcom Developer Portal.

## Module: VMware.VimAutomation.Storage

### Get-VsanDisk

Retrieves host disks that belong to a vSAN disk group.

```
Get-VsanDisk [[-CanonicalName] <String[]>]
    [-VsanDiskGroup <VsanDiskGroup[]>]
    [-Server <VIServer[]>]

Get-VsanDisk [[-CanonicalName] <String[]>]
    -VMHost <VMHost[]>
    [-Server <VIServer[]>]

Get-VsanDisk -Id <String[]> [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CanonicalName` | String[] | No (pos 0) | Disk canonical names (e.g., `naa.xxx`) |
| `-VsanDiskGroup` | VsanDiskGroup[] | No | Filter by disk group |
| `-VMHost` | VMHost[] | Yes (in VMHost set) | Get disks from specific host(s) |
| `-Id` | String[] | Yes (in Id set) | Get by ID |

**Returns**: `VsanDisk` objects

```powershell
# All vSAN disks on a host:
Get-VsanDisk -VMHost "esxi01"

# Disks in a specific disk group:
$dg = Get-VsanDiskGroup -VMHost "esxi01" | Select-Object -First 1
Get-VsanDisk -VsanDiskGroup $dg

# By canonical name:
Get-VsanDisk -CanonicalName "naa.50000396581e4a00"
```

### Get-VsanDiskGroup

Retrieves vSAN disk groups.

```
Get-VsanDiskGroup [[-Name] <String[]>]
    [-Cluster <Cluster[]>]
    [-Server <VIServer[]>]

Get-VsanDiskGroup -VMHost <VMHost[]>
    [-DiskCanonicalName <String[]>]
    [-Server <VIServer[]>]

Get-VsanDiskGroup -Id <String[]> [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | String[] | No (pos 0) | Disk group names |
| `-Cluster` | Cluster[] | No | Filter by cluster |
| `-VMHost` | VMHost[] | Yes (in VMHost set) | Get disk groups from host(s) |
| `-DiskCanonicalName` | String[] | No | Filter by disk canonical name |

**Returns**: `VsanDiskGroup` objects

```powershell
# All disk groups in a cluster:
Get-VsanDiskGroup -Cluster (Get-Cluster "vSAN-Cluster")

# Disk groups on a host:
Get-VsanDiskGroup -VMHost "esxi01"

# Enumerate disks per group:
Get-VsanDiskGroup -VMHost "esxi01" | ForEach-Object {
    Write-Host "Group: $($_.Name)"
    Get-VsanDisk -VsanDiskGroup $_ | Select-Object CanonicalName, IsSsd, IsCacheDisk
}
```

### Get-VsanClusterConfiguration

Retrieves vSAN-related configuration from clusters.

```
Get-VsanClusterConfiguration [[-Cluster] <Cluster[]>]
    [-Server <VIServer[]>]
```

**Returns**: `VsanClusterConfiguration` objects

**Key properties**: `VsanEnabled`, `StretchedClusterEnabled`, `SpaceEfficiencyEnabled`, `EncryptionEnabled`

```powershell
# Get vSAN config for all clusters:
Get-Cluster | Get-VsanClusterConfiguration |
    Select-Object Cluster, VsanEnabled, SpaceEfficiencyEnabled

# Check specific cluster:
Get-VsanClusterConfiguration -Cluster (Get-Cluster "vSAN-Prod")
```

---

## Module: VMware.VimAutomation.Spbm

### Get-SpbmStoragePolicy

Returns storage policies (requirement and resource policies).

```
Get-SpbmStoragePolicy [[-Name] <String[]>]
    [-Namespace <String[]>] [-Capability <SpbmCapability[]>]
    [-Tag <Tag[]>]
    [-Requirement] [-Resource]
    [-Server <VIServer[]>]

Get-SpbmStoragePolicy [-Id <String[]>] [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | String[] | No (pos 0) | Policy names |
| `-Namespace` | String[] | No | Filter by namespace |
| `-Capability` | SpbmCapability[] | No | Filter by capability |
| `-Tag` | Tag[] | No | Filter by tag |
| `-Requirement` | Switch | No | Return only requirement policies |
| `-Resource` | Switch | No | Return only resource policies |

**Returns**: `SpbmStoragePolicy` objects

```powershell
# All storage policies:
Get-SpbmStoragePolicy

# Specific policy by name:
Get-SpbmStoragePolicy -Name "VM Encryption Policy"

# Requirement policies only:
Get-SpbmStoragePolicy -Requirement

# Apply policy to VM:
$policy = Get-SpbmStoragePolicy -Name "Gold-Tier"
Set-VM -VM "WebServer01" -StoragePolicy $policy -Confirm:$false

# Apply policy to hard disk:
$policy = Get-SpbmStoragePolicy -Name "Gold-Tier"
$disk = Get-HardDisk -VM "WebServer01" -Name "Hard disk 1"
Set-HardDisk -HardDisk $disk -StoragePolicy $policy -Confirm:$false
```

---

## Common vSAN Patterns

### vSAN Health Check

```powershell
# Check vSAN status across all clusters:
Get-Cluster | Where-Object { $_.VsanEnabled } | ForEach-Object {
    $config = Get-VsanClusterConfiguration -Cluster $_
    $diskGroups = Get-VsanDiskGroup -Cluster $_
    [PSCustomObject]@{
        Cluster         = $_.Name
        VsanEnabled     = $config.VsanEnabled
        DiskGroups      = $diskGroups.Count
        Encryption      = $config.EncryptionEnabled
        SpaceEfficiency = $config.SpaceEfficiencyEnabled
    }
}
```

### Datastore Capacity Report

```powershell
# Combine datastore info with storage policies:
Get-Datastore | Select-Object Name, Type,
    @{N='CapacityGB'; E={[math]::Round($_.CapacityGB, 2)}},
    @{N='FreeSpaceGB'; E={[math]::Round($_.FreeSpaceGB, 2)}},
    @{N='UsedPercent'; E={[math]::Round((1 - $_.FreeSpaceGB/$_.CapacityGB) * 100, 1)}} |
    Sort-Object UsedPercent -Descending
```

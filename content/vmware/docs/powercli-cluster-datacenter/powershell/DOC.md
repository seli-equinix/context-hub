---
name: powercli-cluster-datacenter
description: "VMware PowerCLI 13.3 — Clusters, datacenters, resource pools, folders, DRS rules, inventory"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,cluster-datacenter,Add-TrustedClusterAttestationServiceInfo, Add-TrustedClusterKeyProviderServiceInfo, Copy-HardDisk, Export-LcmClusterDesiredState, Get-Cluster, Get-Datacenter, Get-DrsClusterGroup, Get-DrsRecommendation, Get-DrsRule, Get-Folder, Get-HardDisk, Get-Inventory, Get-LcmClusterDesiredStateRecommendation, Get-LcmHardwareCompatibility, Get-ResourcePool, Get-TrustAuthorityCluster, Get-TrustedCluster, Get-TrustedClusterAppliedStatus, Get-VDTrafficShapingPolicy, Import-LcmClusterDesiredState, Invoke-DrsRecommendation, Move-Cluster, Move-Datacenter, Move-Folder, Move-HardDisk, Move-Inventory, Move-ResourcePool, New-Cluster, New-CnsContainerCluster, New-Datacenter, New-DrsClusterGroup, New-DrsRule, New-Folder, New-HardDisk, New-ResourcePool, New-VIInventoryDrive, Remove-Cluster, Remove-Datacenter, Remove-DrsClusterGroup, Remove-DrsRule, Remove-Folder, Remove-HardDisk, Remove-Inventory, Remove-ResourcePool, Remove-TrustedClusterAttestationServiceInfo, Remove-TrustedClusterKeyProviderServiceInfo, Set-Cluster, Set-Datacenter, Set-DrsClusterGroup, Set-DrsRule, Set-Folder, Set-HardDisk, Set-ResourcePool, Set-TrustAuthorityCluster, Set-TrustedCluster, Set-VDTrafficShapingPolicy, Test-LcmClusterCompliance, Test-LcmClusterHealth"
---

# VMware PowerCLI — Clusters & Datacenters

Clusters, datacenters, resource pools, folders, DRS rules, inventory. Module: VMware.VimAutomation (58 cmdlets).

## Cmdlet Reference (58 cmdlets)

### Add

#### `Add-TrustedClusterAttestationServiceInfo`

This cmdlet adds the attestation service information configured in the workload vCenter Server system to the trusted hosts in the given trusted cluster.

**Parameters**: `TrustedCluster, AttestationServiceInfo, Server`

#### `Add-TrustedClusterKeyProviderServiceInfo`

This cmdlet adds the key provider service information configured in the workload vCenter Server system to the trusted hosts in the given trusted cluster.

**Parameters**: `TrustedCluster, KeyProviderServiceInfo, Server`

### Copy

#### `Copy-HardDisk`

Copies a virtual hard disk to another destination.

**Parameters**: `HardDisk, DestinationPath, DestinationStorageFormat, Force, RunAsync`

### Export

#### `Export-LcmClusterDesiredState`

This cmdlet exports the desired state of a vSphere Lifecycle Manager cluster.

**Parameters**: `Cluster, Destination, ExportIsoImage, ExportOfflineBundle, RunAsync, Server`

### Get

#### `Get-Cluster`

This cmdlet retrieves the clusters available on a vCenter Server system.

**Parameters**: `RelatedObject, Name, VM, VMHost, Location, NoRecursion, Tag, Server, Id`

#### `Get-Datacenter`

This cmdlet retrieves the datacenters available on a vCenter Server system.

**Parameters**: `Name, VM, Cluster, VMHost, Location, NoRecursion, Tag, RelatedObject, Server, Id`

#### `Get-DrsClusterGroup`

This cmdlet retrieves DRS cluster groups for the specified cluster, VM, or VM host.

**Parameters**: `Name, Cluster, Type, VM, VMHost, Server`

#### `Get-DrsRecommendation`

This cmdlet retrieves the available DRS recommendations from the provided clusters.

**Parameters**: `Cluster, Refresh, Priority, Server`

#### `Get-DrsRule`

This cmdlet retrieves the list of DRS rules for the specified clusters.

**Parameters**: `Name, Cluster, VM, VMHost, Type, Server`

#### `Get-Folder`

This cmdlet retrieves the folders available on a vCenter Server system.

**Parameters**: `Location, Type, Tag, RelatedObject, Server, Name, Id, NoRecursion`

#### `Get-HardDisk`

This cmdlet retrieves the virtual hard disks available on a vCenter Server system.

**Parameters**: `RelatedObject, Id, Path, Datastore, DatastorePath, DiskType, VMGuestDisk, Server, VM, Template, Snapshot, Name`

#### `Get-Inventory`

This cmdlet retrieves the inventory items available on a vCenter Server system.

**Parameters**: `Location, Name, Id, NoRecursion, Server`

#### `Get-LcmClusterDesiredStateRecommendation`

This cmdlet generates a desired state recommendation of a vSphere Lifecycle Manager cluster.

**Parameters**: `Cluster, Latest, Current, RunAsync, Server`

#### `Get-LcmHardwareCompatibility`

This cmdlet verifies that the components in the base image are compatible with all storage controllers on the hosts in the cluster in accordance with the VMware Compatibility Guide.

**Parameters**: `Cluster, VMHost, Server, RunAsync`

#### `Get-ResourcePool`

This cmdlet retrieves the resource pools available on a vCenter Server system.

**Parameters**: `Name, VM, Location, Id, Server, RelatedObject, Tag, NoRecursion`

#### `Get-TrustAuthorityCluster`

This cmdlet retrieves the Trust Authority clusters from the Trust Authority vCenter Server system.

**Parameters**: `Name, State, Id, Server`

#### `Get-TrustedCluster`

This cmdlet retrieves the trusted clusters from the connected workload vCenter Server system.

**Parameters**: `Name, State, Id, Server`

#### `Get-TrustedClusterAppliedStatus`

This cmdlet retrieves the applied status of the trusted service information on the trusted clusters in the workload vCenter Server system.

**Parameters**: `TrustedCluster, Server`

#### `Get-VDTrafficShapingPolicy`

This cmdlet retrieves the traffic shaping policy for distributed ports.

**Parameters**: `Direction, VDPortgroup, VDSwitch, VDPort, Server`

### Import

#### `Import-LcmClusterDesiredState`

This cmdlet imports a specification file to set a desired state of a vSphere Lifecycle Manager cluster.

**Parameters**: `Cluster, JsonSpecContent, LocalSpecLocation, RemoteSpecLocation, Server, RunAsync`

### Invoke

#### `Invoke-DrsRecommendation`

This cmdlet applies the specified DRS recommendations.

**Parameters**: `DrsRecommendation, RunAsync`

### Move

#### `Move-Cluster`

This cmdlet moves a vCenter Server cluster from one location to another.

**Parameters**: `Cluster, Destination, Server, RunAsync`

#### `Move-Datacenter`

This cmdlet moves a vCenter Server datacenter from one location to another.

**Parameters**: `Datacenter, Destination, Server, RunAsync`

#### `Move-Folder`

This cmdlet moves a vCenter Server folder from one location to another.

**Parameters**: `Folder, Destination, Server`

#### `Move-HardDisk`

This cmdlet moves a hard disk from one location to another.

**Parameters**: `HardDisk, Datastore, StorageFormat, Server, RunAsync`

#### `Move-Inventory`

This cmdlet moves a vCenter Server inventory item from one location to another.

**Parameters**: `Item, Destination, DestinationSslThumbprint, RunAsync, Server`

#### `Move-ResourcePool`

This cmdlet moves a resource pool from one location to another.

**Parameters**: `ResourcePool, Destination, Server`

### New

#### `New-Cluster`

This cmdlet creates a new cluster.

**Parameters**: `HARestartPriority, HAIsolationResponse, VMSwapfilePolicy, Name, Location, HAEnabled, HAAdmissionControlEnabled, HAFailoverLevel, DrsEnabled, DrsMode, DrsAutomationLevel, VsanDiskClaimMode` (+7 more)

#### `New-CnsContainerCluster`

This cmdlet creates a vSAN file service IP configuration at the client side.

**Parameters**: `ClusterFlavor, KubernetesClusterId, ClusterType, VSphereUser`

#### `New-Datacenter`

This cmdlet creates a new datacenter.

**Parameters**: `Location, Name, Server`

#### `New-DrsClusterGroup`

This cmdlet creates either a VM or VM host DRS cluster group, depending on the used parameter set.

**Parameters**: `Name, Cluster, VM, VMHost, Server, RunAsync`

#### `New-DrsRule`

This cmdlet creates a new DRS rule.

**Parameters**: `Name, Cluster, Enabled, KeepTogether, VM, RunAsync, Server`

#### `New-Folder`

This cmdlet creates a new folder on a vCenter Server system.

**Parameters**: `Name, Location, Server`

#### `New-HardDisk`

This cmdlet creates a new hard disk on the specified location.

**Parameters**: `AdvancedOption, Persistence, Controller, DiskType, VDisk, CapacityKB, CapacityGB, Split, ThinProvisioned, StorageFormat, DeviceName, Datastore` (+5 more)

#### `New-ResourcePool`

This cmdlet creates a new resource pool.

**Parameters**: `Location, Name, CpuExpandableReservation, CpuLimitMhz, CpuReservationMhz, CpuSharesLevel, MemExpandableReservation, MemLimitMB, MemLimitGB, MemReservationMB, MemReservationGB, MemSharesLevel` (+3 more)

#### `New-VIInventoryDrive`

This function creates a new drive for an inventory item.

**Parameters**: `Name, Location`

### Remove

#### `Remove-Cluster`

This cmdlet deletes the specified clusters.

**Parameters**: `Cluster, Server, RunAsync`

#### `Remove-Datacenter`

This cmdlet removes the specified datacenters from their locations.

**Parameters**: `Datacenter, RunAsync, Server`

#### `Remove-DrsClusterGroup`

This cmdlet removes the specified DRS cluster groups from the cluster on which it resides.

**Parameters**: `DrsClusterGroup, RunAsync, Server`

#### `Remove-DrsRule`

This cmdlet removes the specified DRS rules.

**Parameters**: `Rule, RunAsync`

#### `Remove-Folder`

This cmdlet removes the specified folders from their locations.

**Parameters**: `Folder, DeletePermanently, Server`

#### `Remove-HardDisk`

This cmdlet removes the specified virtual hard disks.

**Parameters**: `HardDisk, DeletePermanently`

#### `Remove-Inventory`

This cmdlet removes the specified inventory items from their locations.

**Parameters**: `Item, RunAsync, Server`

#### `Remove-ResourcePool`

This cmdlet removes the specified resource pools from their locations.

**Parameters**: `ResourcePool, Server`

#### `Remove-TrustedClusterAttestationServiceInfo`

This cmdlet removes the attestation services information from the specified trusted cluster in the workload vCenter Server system.

**Parameters**: `TrustedCluster, AttestationServiceInfo, Server`

#### `Remove-TrustedClusterKeyProviderServiceInfo`

This cmdlet removes the key provider services information from the specified trusted cluster in the workload vCenter Server system.

**Parameters**: `TrustedCluster, KeyProviderServiceInfo, Server`

### Set

#### `Set-Cluster`

This cmldlet modifies the configuration of a cluster.

**Parameters**: `HARestartPriority, HAIsolationResponse, VMSwapfilePolicy, Cluster, Name, HAEnabled, HAAdmissionControlEnabled, HAFailoverLevel, DrsEnabled, DrsMode, DrsAutomationLevel, VsanEnabled` (+15 more)

#### `Set-Datacenter`

This cmdlet modifies the properties of the specified datacenter.

**Parameters**: `Datacenter, Name, Server, RunAsync`

#### `Set-DrsClusterGroup`

This cmdlet adds or removes either virtual machines or VM hosts to or from the specified DRS cluster group, depending on the used parameter set.

**Parameters**: `DrsClusterGroup, VM, VMHost, Add, Remove, Server, RunAsync`

#### `Set-DrsRule`

This cmdlet modifies an existing DRS rule.

**Parameters**: `Enabled, Rule, Name, VM, RunAsync, Server`

#### `Set-Folder`

This cmdlet modifies the properties of the specified folder.

**Parameters**: `Folder, Name, Server`

#### `Set-HardDisk`

This cmdlet modifies the properties of the specified virtual hard disk.

**Parameters**: `HardDisk, CapacityKB, CapacityGB, Persistence, Datastore, StorageFormat, Inflate, Controller, ZeroOut, KeyProvider, StoragePolicy, DisableEncryption` (+12 more)

#### `Set-ResourcePool`

This cmdlet modifies the properties of the specified resource pool.

**Parameters**: `ResourcePool, Name, CpuExpandableReservation, CpuLimitMhz, CpuReservationMhz, CpuSharesLevel, MemExpandableReservation, MemLimitMB, MemLimitGB, MemReservationMB, MemReservationGB, MemSharesLevel` (+3 more)

#### `Set-TrustAuthorityCluster`

This cmdlet modifies the configuration of the specified Trust Authority clusters in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, State, Server, RunAsync`

#### `Set-TrustedCluster`

This cmdlet modifies the configuration of the trusted clusters in the workload vCenter Server system.

**Parameters**: `TrustedCluster, State, Remediate, Server`

#### `Set-VDTrafficShapingPolicy`

This cmdlet modifies the traffic shaping policy for distributed ports.

**Parameters**: `Policy, Enabled, EnabledInherited, AverageBandwidth, AverageBandwidthInherited, BurstSize, BurstSizeInherited, PeakBandwidth, PeakBandwidthInherited`

### Test

#### `Test-LcmClusterCompliance`

This cmdlet tests cluster's hosts compliance respective to its target state.

**Parameters**: `Cluster, RunAsync, Server`

#### `Test-LcmClusterHealth`

This cmdlet tests cluster's hosts health respective to its target state.

**Parameters**: `Cluster, Server`

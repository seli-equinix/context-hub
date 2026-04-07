---
name: powercli-storage
description: "VMware PowerCLI 13.3 — Datastores, vSAN, SPBM storage policies, virtual disks, CNS volumes"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,storage,Add-VsanFileServiceOvf, Add-VsanObjectToRepairQueue, Add-VsanStoragePoolDisk, Copy-DatastoreItem, Copy-VDisk, Export-SpbmStoragePolicy, Get-CnsVolume, Get-Datastore, Get-DatastoreCluster, Get-SpbmCapability, Get-SpbmCompatibleStorage, Get-SpbmEntityConfiguration, Get-SpbmFaultDomain, Get-SpbmPointInTimeReplica, Get-SpbmReplicationGroup, Get-SpbmReplicationPair, Get-SpbmStoragePolicy, Get-SpbmView, Get-VasaStorageArray, Get-VDisk, Get-VsanClusterConfiguration, Get-VsanClusterPowerState, Get-VsanComponent, Get-VsanDirectDisk, Get-VsanDisk, Get-VsanDiskGroup, Get-VsanEnterMaintenanceModeReport, Get-VsanEsaEligibleDisk, Get-VsanEvacuationPlan, Get-VsanFaultDomain, Get-VsanFileServiceDomain, Get-VsanFileServiceOvfInfo, Get-VsanFileShare, Get-VsanFileShareSnapshot, Get-VsanHCIMeshDatastore, Get-VsanHCIMeshDatastoreSource, Get-VsanIscsiInitiatorGroup, Get-VsanIscsiInitiatorGroupTargetAssociation, Get-VsanIscsiLun, Get-VsanIscsiTarget, Get-VsanObject, Get-VsanPerformanceContributor, Get-VsanResyncingComponent, Get-VsanResyncingOverview, Get-VsanRuntimeInfo, Get-VsanSpaceUsage, Get-VsanStat, Get-VsanStoragePoolDisk, Get-VsanView, Get-VsanWipeDiskStatus, Get-VvolStorageContainer, Import-SpbmStoragePolicy, Move-Datastore, Move-VDisk, New-CnsVolume, New-CnsVolumeAttachment, New-CnsVolumeMetadata, New-Datastore, New-DatastoreCluster, New-DatastoreDrive, New-RemoteVsanServerClusterConfig, New-SpbmRule, New-SpbmRuleSet, New-SpbmStoragePolicy, New-VDisk, New-VsanDirectDisk, New-VsanDisk, New-VsanDiskGroup, New-VsanFaultDomain, New-VsanFileServerIpConfig, New-VsanFileServiceDomain, New-VsanFileShare, New-VsanFileShareNetworkPermission, New-VsanFileShareSnapshot, New-VsanHCIMeshDatastoreSource, New-VsanHealthCheckThreshold, New-VsanIscsiInitiatorGroup, New-VsanIscsiInitiatorGroupTargetAssociation, New-VsanIscsiLun, New-VsanIscsiTarget, Remove-CnsVolume, Remove-CnsVolumeAttachment, Remove-Datastore, Remove-DatastoreCluster, Remove-SpbmStoragePolicy, Remove-VDisk, Remove-VsanDirectDisk, Remove-VsanDisk, Remove-VsanDiskGroup, Remove-VsanFaultDomain, Remove-VsanFileServiceDomain, Remove-VsanFileShare, Remove-VsanFileShareSnapshot, Remove-VsanHCIMeshDatastoreSource, Remove-VsanIscsiInitiatorGroup, Remove-VsanIscsiInitiatorGroupTargetAssociation, Remove-VsanIscsiLun, Remove-VsanIscsiTarget, Remove-VsanStoragePoolDisk, Set-CnsVolume, Set-Datastore, Set-DatastoreCluster, Set-SpbmEntityConfiguration, Set-SpbmStoragePolicy, Set-VDisk, Set-VsanClusterConfiguration, Set-VsanFaultDomain, Set-VsanFileServiceDomain, Set-VsanFileShare, Set-VsanIscsiInitiatorGroup, Set-VsanIscsiLun, Set-VsanIscsiTarget, Start-SpbmReplicationFailover, Start-SpbmReplicationPrepareFailover, Start-SpbmReplicationPromote, Start-SpbmReplicationReverse, Start-SpbmReplicationTestFailover, Start-VsanCluster, Start-VsanClusterDiskUpdate, Start-VsanClusterRebalance, Start-VsanEncryptionConfiguration, Start-VsanRelayoutObjects, Start-VsanWipeDisk, Stop-SpbmReplicationTestFailover, Stop-VsanCluster, Stop-VsanClusterRebalance, Stop-VsanWipeDisk, Sync-SpbmReplicationGroup, Test-VsanClusterHealth, Test-VsanNetworkPerformance, Test-VsanStoragePerformance, Update-VsanHclDatabase"
---

# VMware PowerCLI — Storage

Datastores, vSAN, SPBM storage policies, virtual disks, CNS volumes. Module: VMware.VimAutomation (132 cmdlets).

## Cmdlet Reference (132 cmdlets)

### Add

#### `Add-VsanFileServiceOvf`

This cmdlet downloads a file service OVF file of the specified URL into the OVF repository in vSphere.

**Parameters**: `Url, Server, Cluster`

#### `Add-VsanObjectToRepairQueue`

This cmdlet puts a list of vSAN objects on a repair queue.

**Parameters**: `Cluster, VsanObject, Server`

#### `Add-VsanStoragePoolDisk`

This cmdlet adds one or multiple disks to the unique storage pool under a certain host. This cmdlet returns VsanStoragePoolDisk information of a disk that is claimed by a storage pool. Storage pool refers to vSAN ESA disks.

**Parameters**: `VMHost, VsanStoragePoolDiskType, DiskCanonicalNames, Server, RunAsync`

### Copy

#### `Copy-DatastoreItem`

This cmdlet copies items between datastores and between a datastore and a local file system provider.

**Parameters**: `Item, Destination, Force, PassThru, Recurse`

#### `Copy-VDisk`

This cmdlet copies the specified VDisk objects to the specified datastore.

**Parameters**: `VDisk, Name, StorageFormat, Datastore, ScsiLun, RunAsync, Server`

### Export

#### `Export-SpbmStoragePolicy`

This cmdlet exports the specified storage policy to a file.

**Parameters**: `FilePath, StoragePolicy, Force, Server`

### Get

#### `Get-CnsVolume`

This cmdlet retrieves a Cloud Native Storage (CNS) volume based on the name or ID filter.

**Parameters**: `CnsVolumeType, Name, Id, Datastore, Server`

#### `Get-Datastore`

This cmdlet retrieves the datastores available on a vCenter Server system.

**Parameters**: `Server, Id, Name, Location, RelatedObject, Refresh, Tag`

```powershell
Get-Datastore | Select-Object Name, FreeSpaceGB, CapacityGB, @{N="UsedPct";E={[math]::Round((1-$_.FreeSpaceGB/$_.CapacityGB)*100,1)}}
```

#### `Get-DatastoreCluster`

This cmdlet retrieves datastore clusters.

**Parameters**: `Id, Name, Location, VM, Template, Datastore, Tag, RelatedObject, Server`

#### `Get-SpbmCapability`

This cmdlet retrieves capability schema.

**Parameters**: `Name, Category, SpbmLineOfServiceType, Server`

#### `Get-SpbmCompatibleStorage`

This cmdlet performs placement compatibility checking based on a storage requirement policy.

**Parameters**: `StoragePolicy, CandidateStorage, Server`

#### `Get-SpbmEntityConfiguration`

This cmdlet retrieves SPBM-related configuration data of Virtual Machine, Hard Disk, and Datastore objects.

**Parameters**: `VM, HardDisk, Datastore, StoragePolicy, VMsOnly, HardDisksOnly, CheckComplianceNow, Server`

#### `Get-SpbmFaultDomain`

This cmdlet retrieves fault domains based on name or ID filter.

**Parameters**: `Name, VasaProvider, Id, Server`

#### `Get-SpbmPointInTimeReplica`

This cmdlet retrieves the point in time replica objects for the specified target replication groups.

**Parameters**: `Name, ReplicationGroup, VasaTag, VasaProvider, FromDate, ToDate, Count, Id, Server`

#### `Get-SpbmReplicationGroup`

This cmdlet retrieves replication groups.

**Parameters**: `Name, Id, FaultDomain, VasaProvider, FailedOver, VM, HardDisk, StoragePolicy, Datastore, Server`

#### `Get-SpbmReplicationPair`

This cmdlet retrieves the relation of replication groups in a pair of source and target replication group.

**Parameters**: `SourceFaultDomain, TargetFaultDomain, Source, Target, Server`

#### `Get-SpbmStoragePolicy`

This cmdlet returns all available requirement policies and resource policies.

**Parameters**: `Id, Requirement, Resource, Name, Namespace, Capability, Tag, Server`

#### `Get-SpbmView`

This cmdlet retrieves SPBM views for the managed objects in the SPBM server.

**Parameters**: `Id, ServiceContent, Server`

#### `Get-VDisk`

This cmdlet lists VDisk objects based on the specified filters.

**Parameters**: `Datastore, Name, Id, Server`

#### `Get-VasaStorageArray`

This cmdlet retrieves the list of storage arrays managed by registered VASA providers.

**Parameters**: `Name, VasaProvider, Id, Lun, StorageContainer, Refresh, Server`

#### `Get-VsanClusterConfiguration`

This cmdlet retrieves vSAN related configuration data from clusters.

**Parameters**: `Cluster, Server`

#### `Get-VsanClusterPowerState`

This cmdlets retrieves the power state of a vSAN cluster.

**Parameters**: `Cluster, Server`

#### `Get-VsanComponent`

This cmdlet retrieves basic information about the vSAN component, including its universal unique identifier (UUID), the vSAN object it belongs to, the disk it resides on, and its status and type.

**Parameters**: `Server, VsanDisk, VsanStoragePoolDisk, VsanObject, Id`

#### `Get-VsanDirectDisk`

This cmdlet retrieves vSAN Direct disks based on the specified filters.

**Parameters**: `Cluster, VMHost, Id, DiskCanonicalName, Server`

#### `Get-VsanDisk`

This cmdlet retrieves the host disks that belong to a vSAN disk group.

**Parameters**: `Server, VsanDiskGroup, CanonicalName, Id, VMHost`

#### `Get-VsanDiskGroup`

This cmdlet retrieves vSAN disk groups.

**Parameters**: `Cluster, Name, Id, DiskCanonicalName, VMHost, Server`

#### `Get-VsanEnterMaintenanceModeReport`

This cmdlet retrieves the report of capacity or objects which may have accessbility or compliance issues, if a virtual machine host enters maintenance mode.

**Parameters**: `VsanDataMigrationMode, VMHost, Capacity, AccessbilityAndCompliance, Server`

#### `Get-VsanEsaEligibleDisk`

This cmdlet fetches ScsiLun information for all vSAN ESA eligible disks of the target object which can be a vSAN cluster or a list of hosts.

**Parameters**: `VMHost, Cluster, ScsiLun, Server`

#### `Get-VsanEvacuationPlan`

This cmdlet retrieves information about the entity (disk, disk group, or host) you want to evacuate in various modes.

**Parameters**: `Entity, EvacuationMode, Server`

#### `Get-VsanFaultDomain`

This cmdlet retrieves vSAN fault domains based on name or ID filter.

**Parameters**: `Cluster, VMHost, Name, Id, Server`

#### `Get-VsanFileServiceDomain`

This cmdlet retrieves vSAN file service domains in a vSAN cluster.

**Parameters**: `Name, Cluster, Id, Server`

#### `Get-VsanFileServiceOvfInfo`

This cmdlet retrieves a vSAN file service OVF information.

**Parameters**: `Server`

#### `Get-VsanFileShare`

This cmdlet retrieves vSAN file shares based on the name or ID filter.

**Parameters**: `Cluster, Name, FileServiceDomain, Id, Server`

#### `Get-VsanFileShareSnapshot`

This cmdlet retrieves vSAN file share snapshots based on the name or other filters.

**Parameters**: `FileShare, Name, EndTime, StartTime, Server`

#### `Get-VsanHCIMeshDatastore`

This cmdlet retrieves vSAN HCI Mesh datastores based on the specified filters.

**Parameters**: `VsanHCIMeshDatastoreSource, Server`

#### `Get-VsanHCIMeshDatastoreSource`

This cmdlet retrieves vSAN HCI Mesh datastore sources based on the specified filters.

**Parameters**: `VCHost, Server`

#### `Get-VsanIscsiInitiatorGroup`

This cmdlet retrieves vSAN iSCSI initiator groups.

**Parameters**: `Name, Cluster, Id, Server`

#### `Get-VsanIscsiInitiatorGroupTargetAssociation`

This cmdlet retrieves all pairs of associations between vSAN iSCSI targets and initiator groups, which have access to the corresponding targets.

**Parameters**: `Target, InitiatorGroup, Server`

#### `Get-VsanIscsiLun`

This cmdlet retrieves the vSAN iSCSI LUNs from a cluster or target.

**Parameters**: `VsanIscsiTarget, Name, LunId, Cluster, Id, Server`

#### `Get-VsanIscsiTarget`

This cmdlet retrieves vSAN iSCSI targets from clusters.

**Parameters**: `Cluster, Name, IscsiQualifiedName, Id, Server`

#### `Get-VsanObject`

This cmdlet retrieves vSAN objects based on the specified filters.

**Parameters**: `Cluster, Id, Type, VM, VsanDisk, VsanStoragePoolDisk, Server`

#### `Get-VsanPerformanceContributor`

This cmdlet retrieves a list of the most impactful vSAN performance contributors, based on the specified entity type. The list includes the contributors that exhibit the highest IOPS, throughput, or latency consumption within the provided start and end times in the specified vSAN cluster.

**Parameters**: `Cluster, StartTime, Entity, EndTime, MetricId, EntityCountLimit, Server`

#### `Get-VsanResyncingComponent`

This cmdlet retrieves the details of components going through synchronization in a vSAN cluster.

**Parameters**: `Cluster, Server`

#### `Get-VsanResyncingOverview`

This cmdlet retrieves the overview of objects going through synchronization in a vSAN cluster. It will query information about vSAN objects that are currently syncing data.

**Parameters**: `Cluster, Server`

#### `Get-VsanRuntimeInfo`

This cmdlet retrieves the runtime information of a vSAN cluster.

**Parameters**: `Cluster, Server`

#### `Get-VsanSpaceUsage`

This cmdlet retrieves space usage details of a vSAN cluster. (Note that the output attribute denoted with 'GB' signifies the unit of Gibibytes (GiB), utilizing a base-2 binary representation.)

**Parameters**: `Cluster, StoragePolicy, Server`

#### `Get-VsanStat`

This cmdlet retrieves vSAN performance statistics for the specified server entity.

**Parameters**: `Name, Entity, StartTime, EndTime, PredefinedTimeRange, Server`

#### `Get-VsanStoragePoolDisk`

This cmdlet fetches VsanStoragePoolDisk information from a certain host or cluster. It also enables you to fetch storage pool disks by disk canonical name. If both host and disk canonical name are specified, the system uses both parameters.

**Parameters**: `VMHost, DiskCanonicalName, VsanStoragePoolDiskType, Cluster, Server`

#### `Get-VsanView`

This cmdlet retrieves vSAN views that match the specified IDs.

**Parameters**: `Id, Server`

#### `Get-VsanWipeDiskStatus`

This cmdlet retrieves a disk level information about securely wiping disks.

**Parameters**: `VMHost, CanonicalName, Server`

#### `Get-VvolStorageContainer`

This cmdlet retrieves the list of Virtual Volume (vVol) storage containers that are reported by the registered VASA providers.

**Parameters**: `Name, VasaProvider, StorageArray, Id, Server`

### Import

#### `Import-SpbmStoragePolicy`

This cmdlet imports a storage policy from a file.

**Parameters**: `FilePath, Name, Description, Server`

### Move

#### `Move-Datastore`

This cmdlet moves datastores from one location to another.

**Parameters**: `Datastore, Destination, Server`

#### `Move-VDisk`

This cmdlet moves the specified VDisk objects to the specified datastore.

**Parameters**: `VDisk, StorageFormat, Datastore, ScsiLun, RunAsync, Server`

### New

#### `New-CnsVolume`

This cmdlet creates a Cloud Native Storage (CNS) volume.

**Parameters**: `FileShare, Name, VDisk, CnsVolumeMetadata, FileShareNetworkPermission, SoftQuotaGB, CapacityMB, Datastore, StoragePolicy, StaticFileShare, DynamicBlock, StaticBlock` (+3 more)

#### `New-CnsVolumeAttachment`

New-CnsVolumeAttachment -CnsVolume <CnsVolume> -VM <VirtualMachine> [-Server <VIServer[]>] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>]

**Parameters**: `CnsVolume, VM, Server, RunAsync`

#### `New-CnsVolumeMetadata`

This cmdlet creates a Cloud Native Storage (CNS) volume metadata at the client side.

**Parameters**: `ContainerCluster, CnsEntityMetadata`

#### `New-Datastore`

This cmdlet creates a new datastore.

**Parameters**: `Server, VMHost, Name, Path, Nfs, NfsHost, ReadOnly, Kerberos, Vmfs, BlockSizeMB, FileSystemVersion, VvolStorageContainer`

#### `New-DatastoreCluster`

This cmdlet creates a new datastore cluster.

**Parameters**: `Name, Location, Server`

#### `New-DatastoreDrive`

This function creates a new datastore drive.

**Parameters**: `Name, Datastore`

#### `New-RemoteVsanServerClusterConfig`

Creates a local object of type RemoteVsanServerClusterConfig that you use to mount a remote vSAN datastore from a vSAN stretched cluster.

**Parameters**: `NetWorkTopology, Cluster, ClientSiteName, ServerSiteName, Server`

#### `New-SpbmRule`

This cmdlet creates an SPBM rule in the client side.

**Parameters**: `Capability, Value, AnyOfTags, SpbmOperatorType, Server`

#### `New-SpbmRuleSet`

This cmdlet creates an SPBM rule set.

**Parameters**: `AllOfRules, Name`

#### `New-SpbmStoragePolicy`

This cmdlet creates a requirement storage policy in an SPBM server.

**Parameters**: `Name, Description, AnyOfRuleSets, CommonRule, Server`

#### `New-VDisk`

This cmdlet creates a managed VDisk object whose lifecycle is independent of a virtual machine`s lifecycle on the specified datastore.

**Parameters**: `Name, StorageFormat, CapacityGB, DiskType, VMHost, Datastore, ScsiLun, HardDisk, Server`

#### `New-VsanDirectDisk`

This cmdlet creates a vSAN Direct disk from a specified hard disk.

**Parameters**: `VMHost, DiskCanonicalName, Server, RunAsync`

#### `New-VsanDisk`

This cmdlet adds a host SCSI disk to a vSAN disk group.

**Parameters**: `VsanDiskGroup, CanonicalName, RunAsync`

#### `New-VsanDiskGroup`

This cmdlet creates a new vSAN disk group backed by the specified devices.

**Parameters**: `VMHost, SsdCanonicalName, DataDiskCanonicalName, Server, RunAsync`

#### `New-VsanFaultDomain`

This cmdlet creates a new vSAN fault domain in a cluster with specified virtual machine hosts.

**Parameters**: `VMHost, Name, Server, RunAsync`

#### `New-VsanFileServerIpConfig`

This cmdlet creates a vSAN file service IP configuration at the client side.

**Parameters**: `Gateway, IpAddress, SubnetMask, Fqdn, IsPrimary`

#### `New-VsanFileServiceDomain`

This cmdlet creates a file service domain in a vSAN cluster.

**Parameters**: `Cluster, Name, VsanFileServerIpConfig, DnsSuffix, DnsServerAddress, Server`

#### `New-VsanFileShare`

This cmdlet creates a new vSAN file share in a specified file service domain.

**Parameters**: `HardQuotaGB, Label, Name, SoftQuotaGB, StoragePolicy, FileShareNetworkPermission, FileServiceDomain, Server`

#### `New-VsanFileShareNetworkPermission`

New-VsanFileShareNetworkPermission -IPSetOrSubnet <string> -VsanFileShareAccessPermission <VsanFileShareAccessType> [-AllowSquashRoot] [-WhatIf] [-Confirm] [<CommonParameters>]

**Parameters**: `AllowSquashRoot, IPSetOrSubnet, VsanFileShareAccessPermission`

#### `New-VsanFileShareSnapshot`

This cmdlet creates a vSAN file share snapshot for the specified vSAN file share.

**Parameters**: `Name, FileShare, Server`

#### `New-VsanHCIMeshDatastoreSource`

This cmdlet creates a new vSAN HCI Mesh datastore source for the local vCenter Server from a remote vCenter Server.

**Parameters**: `User, Password, VCHost, Server, RunAsync`

#### `New-VsanHealthCheckThreshold`

This cmdlet creates a vSAN health check threshold object locally. This cmdlet is used to set a capacity threshold in Set-VsanClusterConfiguration.

**Parameters**: `Enabled, RedValue, YellowValue, Target`

#### `New-VsanIscsiInitiatorGroup`

This cmdlet adds a new vSAN iSCSI initiator group to a cluster.

**Parameters**: `Name, Cluster, Server`

#### `New-VsanIscsiInitiatorGroupTargetAssociation`

This cmdlet associates the specified vSAN iSCSI initiator group with specified vSAN iSCSI target to provide access to the target.

**Parameters**: `InitiatorGroup, Target, Server`

#### `New-VsanIscsiLun`

This cmdlet adds a new vSAN iSCSI LUN to a target.

**Parameters**: `Target, Name, LunId, CapacityGB, StoragePolicy, Server, RunAsync`

#### `New-VsanIscsiTarget`

This cmdlet adds a new vSAN iSCSI target to a cluster.

**Parameters**: `Cluster, Name, IscsiQualifiedName, NetworkInterface, TcpPort, AuthenticationType, IncomingChapUser, IncomingChapSecret, OutgoingChapUser, OutgoingChapSecret, StoragePolicy, Server` (+1 more)

### Remove

#### `Remove-CnsVolume`

This cmdlet removes the specified Cloud Native Storage (CNS) volumes.

**Parameters**: `CnsVolume, RunAsync, Server`

#### `Remove-CnsVolumeAttachment`

Remove-CnsVolumeAttachment -CnsVolume <CnsVolume> -VM <VirtualMachine> [-Server <VIServer[]>] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>]

**Parameters**: `CnsVolume, VM, Server, RunAsync`

#### `Remove-Datastore`

This cmdlet removes the specified datastores from their locations.

**Parameters**: `Datastore, VMHost, Server, RunAsync`

#### `Remove-DatastoreCluster`

This cmdlet deletes the specified datastore clusters.

**Parameters**: `DatastoreCluster, Server`

#### `Remove-SpbmStoragePolicy`

This cmdlet deletes storage policies.

**Parameters**: `StoragePolicy, Server`

#### `Remove-VDisk`

This cmdlet removes VDisk objects and the associated backings from the datastore.

**Parameters**: `VDisk`

#### `Remove-VsanDirectDisk`

This cmdlet removes vSAN Direct disks from a vSAN cluster.

**Parameters**: `VsanDataMigrationMode, Purpose, VsanDirectDisk, Cluster, Server, RunAsync`

#### `Remove-VsanDisk`

This cmdlet removes the specified hard disks from the specified vSAN disk group.

**Parameters**: `VsanDisk, DataMigrationMode, RunAsync`

#### `Remove-VsanDiskGroup`

This cmdlet removes vSAN disk groups.

**Parameters**: `VsanDiskGroup, DataMigrationMode, RunAsync`

#### `Remove-VsanFaultDomain`

This cmdlet removes vSAN fault domains.

**Parameters**: `VsanFaultDomain, RunAsync, Server`

#### `Remove-VsanFileServiceDomain`

This cmdlet removes the specified vSAN file service domain from the vSAN clusters.

**Parameters**: `VsanFileServiceDomain, Server`

#### `Remove-VsanFileShare`

This cmdlet removes vSAN file shares.

**Parameters**: `FileShare, Force, Server`

#### `Remove-VsanFileShareSnapshot`

This cmdlet removes vSAN file share snapshots.

**Parameters**: `FileShareSnapshot, Server`

#### `Remove-VsanHCIMeshDatastoreSource`

This cmdlet removes a vSAN HCI Mesh datastore source with the specified information.

**Parameters**: `VsanHCIMeshDatastoreSource, User, Password, Server, RunAsync`

#### `Remove-VsanIscsiInitiatorGroup`

This cmdlet removes the specified vSAN iSCSI initiator groups from their clusters.

**Parameters**: `InitiatorGroup, Server`

#### `Remove-VsanIscsiInitiatorGroupTargetAssociation`

This cmdlet removes the specified association of vSAN iSCSI initiator group and target.

**Parameters**: `InitiatorGroupTargetAssociation`

#### `Remove-VsanIscsiLun`

This cmdlet removes vSAN iSCSI LUNs from their iSCSI targets.

**Parameters**: `Lun, RunAsync, Server`

#### `Remove-VsanIscsiTarget`

This cmdlet removes vSAN iSCSI targets form their clusters.

**Parameters**: `Target, RunAsync, Server`

#### `Remove-VsanStoragePoolDisk`

This cmdlet removes a single or multiple storage pool disks on a vSAN cluster.

**Parameters**: `Purpose, VsanStoragePoolDisk, VsanDataMigrationMode, Server, RunAsync`

### Set

#### `Set-CnsVolume`

This cmdlet modifies the Cloud Native Storage (CNS) volume metadata of a specified CNS volume.

**Parameters**: `CnsVolume, CnsVolumeMetadata, RunAsync, Server`

#### `Set-Datastore`

This cmdlet modifies the properties of the specified datastore.

**Parameters**: `Datastore, Name, CongestionThresholdMillisecond, StorageIOControlEnabled, MaintenanceMode, EvacuateAutomatically, RunAsync, Server`

#### `Set-DatastoreCluster`

This cmdlet modifies the configuration of the specified datastore cluster.

**Parameters**: `DatastoreCluster, IOLatencyThresholdMillisecond, IOLoadBalanceEnabled, Name, SdrsAutomationLevel, SpaceUtilizationThresholdPercent, Server`

#### `Set-SpbmEntityConfiguration`

This cmdlet sets SPBM-related configuration data for VirtualMachine, HardDisk, and Datastore objects.

**Parameters**: `Configuration, StoragePolicy, AutoReplicationGroup, ReplicationGroup, Server`

#### `Set-SpbmStoragePolicy`

This cmdlet overrides the current name, description, and rule sets of an existing storage policy in an SPBM server.

**Parameters**: `StoragePolicy, Name, Description, AnyOfRuleSets, CommonRule, Server`

#### `Set-VDisk`

This cmdlet renames, inflates, or extends the size of the specified VDisk object.

**Parameters**: `VDisk, Name, Inflate, CapacityGB`

#### `Set-VsanClusterConfiguration`

This cmdlet modifies vSAN configuration settings for a cluster.

**Parameters**: `Configuration, HealthCheckIntervalMinutes, HostRebuildReservationState, VsanOperationReservationState, SpaceEfficiencyEnabled, SpaceCompressionEnabled, PerformanceServiceEnabled, AllowReducedRedundancy, StoragePolicy, StretchedClusterEnabled, PreferredFaultDomain, WitnessHost` (+34 more)

#### `Set-VsanFaultDomain`

This cmdlet changes the configuration of a specified vSAN fault domain.

**Parameters**: `VsanFaultDomain, AddVMHost, RemoveVMHost, Name, RunAsync, Server`

#### `Set-VsanFileServiceDomain`

This cmdlet modifies the settings of the given vSAN file domains.

**Parameters**: `Name, FileServerIpConfig, VsanFileServiceDomain, DnsSuffix, DnsServerAddress, Server`

#### `Set-VsanFileShare`

This cmdlet modifies the configuration of a specified vSAN file share.

**Parameters**: `Name, SoftQuotaGB, StoragePolicy, FileShare, HardQuotaGB, SetLabel, FileShareNetworkPermission, RemoveLabel, Force, Server`

#### `Set-VsanIscsiInitiatorGroup`

This cmdlet modifies the specified vSAN iSCSI initiator groups.

**Parameters**: `InitiatorGroup, AddInitiator, RemoveInitiator, Server`

#### `Set-VsanIscsiLun`

This cmdlet modifies the specified vSAN iSCSI LUNs.

**Parameters**: `Lun, Name, IsOnline, CapacityGB, LunId, StoragePolicy, Server, RunAsync`

#### `Set-VsanIscsiTarget`

This cmdlet modifies the settings of the specified vSAN iSCSI targets.

**Parameters**: `Target, Name, NetworkInterface, TcpPort, AuthenticationType, IncomingChapUser, IncomingChapSecret, OutgoingChapUser, OutgoingChapSecret, StoragePolicy, AddInitiator, RemoveInitiator` (+2 more)

### Start

#### `Start-SpbmReplicationFailover`

This cmdlet performs a failover of the devices in the specified replication groups.

**Parameters**: `ReplicationGroup, CheckOnly, Unplanned, SourceVvolIdMap, PointInTimeReplica, RunAsync, Server`

#### `Start-SpbmReplicationPrepareFailover`

This cmdlet prepares the specified replication groups to fail over.

**Parameters**: `ReplicationGroup, RunAsync, Server`

#### `Start-SpbmReplicationPromote`

This cmdlet promotes a target replication group from InTest to FailedOver state.

**Parameters**: `ReplicationGroup, Unplanned, RunAsync, Server`

#### `Start-SpbmReplicationReverse`

This cmdlet initiates reverse replication, by making the currently failed over replication group the source and its peer replication group the target.

**Parameters**: `ReplicationGroup, RunAsync, Server`

#### `Start-SpbmReplicationTestFailover`

This cmdlet performs a test failover of a target replication group.

**Parameters**: `ReplicationGroup, CheckOnly, Unplanned, SourceVvolIdMap, PointInTimeReplica, RunAsync, Server`

#### `Start-VsanCluster`

This cmdlet executes vSAN cluster power on.

**Parameters**: `Cluster, PowerOnReason, Server`

#### `Start-VsanClusterDiskUpdate`

This cmdlet starts the update of all vSAN disks of a cluster to the latest vSAN disk format version supported by the cluster.

**Parameters**: `Cluster, AllowReducedRedundancy, SpaceEfficiencyEnabled, EncryptionEnabled, EraseDisksBeforeUse, KeyProvider, SkipHostRemediation, Server`

#### `Start-VsanClusterRebalance`

This cmdlet starts the proactive rebalance of the vSAN objects on the cluster hosts based on the vSAN disks usage when the disks are in imbalanced state.

**Parameters**: `Cluster, Server`

#### `Start-VsanEncryptionConfiguration`

This cmdlet starts an encryption configuration on a vSAN cluster.

**Parameters**: `Cluster, EncryptionEnabled, EraseDisksBeforeUse, KeyProvider, ShallowRekey, DeepRekey, AllowReducedRedundancy, Server`

#### `Start-VsanRelayoutObjects`

This cmdlet starts the task of relayouting objects for specified vSAN clusters.

**Parameters**: `Cluster, Server`

#### `Start-VsanWipeDisk`

This cmdlet starts the secure wipe of the specified host SCSI disks.

**Parameters**: `VMHost, CanonicalName, Server`

### Stop

#### `Stop-SpbmReplicationTestFailover`

This cmdlet stops the test failover on the specified replication groups and tries to perform a cleanup on the target site.

**Parameters**: `ReplicationGroup, Force, RunAsync, Server`

#### `Stop-VsanCluster`

This cmdlet powers off a vSAN cluster.

**Parameters**: `Cluster, PowerOffReason, InfraVMs, Server`

#### `Stop-VsanClusterRebalance`

This cmdlet stops the proactive rebalance of the vSAN objects on the cluster hosts.

**Parameters**: `Cluster, Server`

#### `Stop-VsanWipeDisk`

This cmdlet stops the secure wipe of the specified host SCSI disks.

**Parameters**: `VMHost, CanonicalName, Server`

### Sync

#### `Sync-SpbmReplicationGroup`

This cmdlet synchronizes the data between source and replica for the specified replication group.

**Parameters**: `ReplicationGroup, PointInTimeReplicaName, RunAsync, Server`

### Test

#### `Test-VsanClusterHealth`

This cmdlet runs a health test on the specified vSAN clusters and returns the test results.

**Parameters**: `Cluster, UseCache, VMCreateTimeoutSeconds, TestResultFilter, Perspective, Server`

#### `Test-VsanNetworkPerformance`

This cmdlet runs a network performance test on the specified vSAN clusters and returns the test results.

**Parameters**: `Cluster, UseCache, DurationInSecond, Server`

#### `Test-VsanStoragePerformance`

This cmdlet runs a storage performance test on the specified vSAN clusters and returns the test results.

**Parameters**: `Cluster, RunAsync, TestDurationSeconds, StoragePolicy, UseCache, Workload, Server`

### Update

#### `Update-VsanHclDatabase`

This cmdlet updates the vSAN hardware compatibility list (HCL) database.

**Parameters**: `FilePath, Server, RunAsync`

---
name: powercli-storage
description: "VMware PowerCLI 13.3 — Datastores, vSAN, SPBM storage policies, virtual disks, CNS volumes"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 2
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,storage,Add-VsanFileServiceOvf, Add-VsanObjectToRepairQueue, Add-VsanStoragePoolDisk, Copy-DatastoreItem, Copy-VDisk, Export-SpbmStoragePolicy, Get-CnsVolume, Get-Datastore, Get-DatastoreCluster, Get-SpbmCapability, Get-SpbmCompatibleStorage, Get-SpbmEntityConfiguration, Get-SpbmFaultDomain, Get-SpbmPointInTimeReplica, Get-SpbmReplicationGroup, Get-SpbmReplicationPair, Get-SpbmStoragePolicy, Get-SpbmView, Get-VasaStorageArray, Get-VDisk, Get-VsanClusterConfiguration, Get-VsanClusterPowerState, Get-VsanComponent, Get-VsanDirectDisk, Get-VsanDisk, Get-VsanDiskGroup, Get-VsanEnterMaintenanceModeReport, Get-VsanEsaEligibleDisk, Get-VsanEvacuationPlan, Get-VsanFaultDomain, Get-VsanFileServiceDomain, Get-VsanFileServiceOvfInfo, Get-VsanFileShare, Get-VsanFileShareSnapshot, Get-VsanHCIMeshDatastore, Get-VsanHCIMeshDatastoreSource, Get-VsanIscsiInitiatorGroup, Get-VsanIscsiInitiatorGroupTargetAssociation, Get-VsanIscsiLun, Get-VsanIscsiTarget, Get-VsanObject, Get-VsanPerformanceContributor, Get-VsanResyncingComponent, Get-VsanResyncingOverview, Get-VsanRuntimeInfo, Get-VsanSpaceUsage, Get-VsanStat, Get-VsanStoragePoolDisk, Get-VsanView, Get-VsanWipeDiskStatus, Get-VvolStorageContainer, Import-SpbmStoragePolicy, Move-Datastore, Move-VDisk, New-CnsVolume, New-CnsVolumeAttachment, New-CnsVolumeMetadata, New-Datastore, New-DatastoreCluster, New-DatastoreDrive, New-RemoteVsanServerClusterConfig, New-SpbmRule, New-SpbmRuleSet, New-SpbmStoragePolicy, New-VDisk, New-VsanDirectDisk, New-VsanDisk, New-VsanDiskGroup, New-VsanFaultDomain, New-VsanFileServerIpConfig, New-VsanFileServiceDomain, New-VsanFileShare, New-VsanFileShareNetworkPermission, New-VsanFileShareSnapshot, New-VsanHCIMeshDatastoreSource, New-VsanHealthCheckThreshold, New-VsanIscsiInitiatorGroup, New-VsanIscsiInitiatorGroupTargetAssociation, New-VsanIscsiLun, New-VsanIscsiTarget, Remove-CnsVolume, Remove-CnsVolumeAttachment, Remove-Datastore, Remove-DatastoreCluster, Remove-SpbmStoragePolicy, Remove-VDisk, Remove-VsanDirectDisk, Remove-VsanDisk, Remove-VsanDiskGroup, Remove-VsanFaultDomain, Remove-VsanFileServiceDomain, Remove-VsanFileShare, Remove-VsanFileShareSnapshot, Remove-VsanHCIMeshDatastoreSource, Remove-VsanIscsiInitiatorGroup, Remove-VsanIscsiInitiatorGroupTargetAssociation, Remove-VsanIscsiLun, Remove-VsanIscsiTarget, Remove-VsanStoragePoolDisk, Set-CnsVolume, Set-Datastore, Set-DatastoreCluster, Set-SpbmEntityConfiguration, Set-SpbmStoragePolicy, Set-VDisk, Set-VsanClusterConfiguration, Set-VsanFaultDomain, Set-VsanFileServiceDomain, Set-VsanFileShare, Set-VsanIscsiInitiatorGroup, Set-VsanIscsiLun, Set-VsanIscsiTarget, Start-SpbmReplicationFailover, Start-SpbmReplicationPrepareFailover, Start-SpbmReplicationPromote, Start-SpbmReplicationReverse, Start-SpbmReplicationTestFailover, Start-VsanCluster, Start-VsanClusterDiskUpdate, Start-VsanClusterRebalance, Start-VsanEncryptionConfiguration, Start-VsanRelayoutObjects, Start-VsanWipeDisk, Stop-SpbmReplicationTestFailover, Stop-VsanCluster, Stop-VsanClusterRebalance, Stop-VsanWipeDisk, Sync-SpbmReplicationGroup, Test-VsanClusterHealth, Test-VsanNetworkPerformance, Test-VsanStoragePerformance, Update-VsanHclDatabase"
---

# VMware PowerCLI — Storage

Datastores, vSAN, SPBM storage policies, virtual disks, CNS volumes. Module: VMware.VimAutomation (132 cmdlets).

## Add

### `Add-VsanFileServiceOvf`

**This cmdlet downloads a file service OVF file of the specified URL into the OVF repository in vSphere.**

This cmdlet downloads a file service OVF file of the specified URL into the OVF repository in vSphere. If no URL is specified, a compatible vSAN file service OVF download URL for the target cluster is searched and used.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the vSAN cluster for which a compatible OVF is searched and downloaded. If the URL is specified, this parameter is ignored.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Url [String[]] (Optional) Specifies the URL from which you want to download the OVF file.

**Examples:**

```powershell
Add-VsanFileServiceOvf -Url $url
```
_Downloads an OVF file from the specified URL into the vSphere OVF repository._

### `Add-VsanObjectToRepairQueue`

**This cmdlet puts a list of vSAN objects on a repair queue.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster from which you want to repair objects.
- -VsanObject [VsanObject[]] (Required) Specifies the vSAN objects you want to repair.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Add-VsanObjectToRepairQueue -Cluster $vsanCluster
```
_Puts the vSAN objects of the $vsanCluster cluster in the repair queue._

```powershell
Add-VsanObjectToRepairQueue -VasnObject $vsanObject
```
_Puts the $vsanObject object in the repair queue._

### `Add-VsanStoragePoolDisk`

**This cmdlet adds one or multiple disks to the unique storage pool under a certain host. This cmdlet returns VsanStoragePoolDisk information of a disk that is claimed by a storage pool. Storage pool refers to vSAN ESA disks.**

**Parameters:**

- -DiskCanonicalNames [String[]] (Required) Specifies the canonical names of hard disks that must be added to one storage pool. The parameter also accepts ScsiLun and VMHostDisk objects through argument transformation.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the vSphere PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost] (Required) Specifies the VMHost from which you want to create a vSAN ESA storage pool.
- -VsanStoragePoolDiskType [VsanStoragePoolDiskType] (Required) Specifies the type of vSAN storage pool disk. The disks can be used in single tier.

**Examples:**

```powershell
Add-VsanStoragePoolDisk -VMHost (Get-VMHost 10.192.201.50) -VsanStoragePoolDiskType "singleTier" -DiskCanonicalName ("mpx.vmhba0:C0:T11:L0","mpx.vmhba0:C0:T12:L0")
```
_Adds disks with specified canonical names from a specified host as "singleTier" vSAN storage pool disks._

```powershell
Add-VsanStoragePoolDisk -VMHost (Get-VMHost 10.192.201.50) -VsanStoragePoolDiskType "singleTier" -DiskCanonicalName "mpx.vmhba0:C0:T6:L0"
```
_Adds a disk with a specified canonical name from a specified host as "singleTier" vSAN storage pool disks._

## Copy

### `Copy-DatastoreItem`

**This cmdlet copies items between datastores and between a datastore and a local file system provider.**

**Parameters:**

- -Destination [Object] (Optional) Specifies the destination where you want to copy the datastore item. You can use a string to specify a relative path to the destination object in the current provider location. For more information about the PowerCLI datastore provider, run "Get-Help about_vimdatastore".
- -Force [SwitchParameter] (Optional) Indicates whether to overwrite all items with the same name at the provided destination.
- -Item [Object[]] (Required) Specifies the datastore item you want to copy. You can use a string to provide a relative path to the item in the current provider location. For more information about the PowerCLI datastore provider, run "Get-Help about_vimdatastore".
- -PassThru [SwitchParameter] (Optional) Indicates that the cmdlet returns the copied item.
- -Recurse [SwitchParameter] (Optional) Indicates that you want to copy not only the item, but its children items as well.

**Examples:**

```powershell
Copy-DatastoreItem vmstore:\Datacenter\Storage1\MyVM\* c:\VMFolder\MyVM\
```
_Copies the contents of a datastore folder in a local folder._

```powershell
Copy-DatastoreItem c:\VMFolder\MyVM\* vmstore:\Datacenter\Storage1\NewVM\ -Force
```
_Copies the contents of a local folder into a datastore folder. If the destination folder does not exist, the Force parameter enforces its creation._

```powershell
Copy-DatastoreItem c:\VMFolder\* vmstore:\Datacenter\Storage1\VMs\ -Force -Recurse
```
_Copies recursively the contents of a local folder into a datastore folder._

### `Copy-VDisk`

**This cmdlet copies the specified VDisk objects to the specified datastore.**

This cmdlet copies the specified VDisk objects to the specified datastore. For RDM (RawVDisk), only one VDisk can be copied at once, and only copying from VMFS to VMFS is supported.

**Parameters:**

- -Datastore [Datastore] (Required) Specifies the datastore to which you want to copy the metadata of the VDisk object. For flat disk, the contents of the disk are also copied to the specified datastore.
- -Name [String] (Optional) Specifies the name of the copy of the VDisk object.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -ScsiLun [ScsiLun] (Required) Specifies the backing SCSI LUN for the copy of the VDisk object.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageFormat [VDiskStorageFormat] (Optional) Specifies the storage format of the copy of the VDisk object.
- -VDisk [VDisk[]] (Required) Specifies the VDisk objects you want to copy.

**Examples:**

```powershell
Copy-VDisk -VDisk $vDisk -Datastore $ds
```
_Copies the flat VDisk object $vDisk on the $ds datastore._

```powershell
Copy-VDisk -VDisk $vDisk -ScsiLun $scsiLun -Datastore $ds
```
_Copies the raw VDisk object $vDisk on the $scsiLun SCSI LUN and stores metadata of this object on the $ds datastore._

## Export

### `Export-SpbmStoragePolicy`

**This cmdlet exports the specified storage policy to a file.**

This cmdlet exports the specified storage policy to a file. If the Force parameter is not specified and the destination file exists or the target parent directory does not exist, a terminating error is generated.

**Parameters:**

- -FilePath [String] (Required) Specifies the path to the file or directory where you want to export the storage policy.
- -Force [SwitchParameter] (Optional) Indicates whether the cmdlet overwrites the existing destination files.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Required) Specifies the storage policy you want to export.

**Examples:**

```powershell
Export-SpbmStoragePolicy -StoragePolicy $policy -FilePath C:\policies\
```
_Exports a storage policy to a file in C:\policies\. If the C:\policies\ directory exists, a file with the name of the policy is created in this directory._

```powershell
Export-SpbmStoragePolicy -StoragePolicy $policy -FilePath C:\policy.xml -Force
```
_Exports a storage policy to the policy.xml file in C:\. If a file with the same name already exists in this location, the file is overwritten._

## Get

### `Get-CnsVolume`

**This cmdlet retrieves a Cloud Native Storage (CNS) volume based on the name or ID filter.**

This cmdlet retrieves CNS volume based on the name or ID filter.

**Parameters:**

- -Datastore [Datastore[]] (Optional) Specifies the datastore in which the CNS volume resides.
- -CnsVolumeType [CnsVolumeType[]] (Optional) Specifies the type of the CNS volume. If not specified, all types are queried.
- -Id [String[]] (Required) Filters the retrieved vSAN file share by ID.
- -Name [String[]] (Optional) Filters the retrieved vSAN file share by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-CnsVolume -FileServiceDomain $fileServiceDomain
```
_Retrieves the vSAN file share which belongs to the $fileServiceDomain file service domain._

```powershell
Get-CnsVolume -Datastore $datastore -Name "volume1"
```
_Retrieves the CNS volume named "volume1" that resides in the $datastore datastore._

### `Get-Datastore`

**This cmdlet retrieves the datastores available on a vCenter Server system.**

This cmdlet retrieves the datastores available on a vCenter Server system. Returns a set of datastores that correspond to the filter criteria defined by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the datastores you want to retrieve.
- -Location [VIObject[]] (Optional) Specifies vSphere container objects that you want to search for datastores. This parameter accepts Datacenter, Folder, and DatastoreCluster objects.
- -Name [String[]] (Optional) Specifies the names of the datastores you want to retrieve.
- -Refresh [SwitchParameter] (Optional) Indicates that the cmdlet first refreshes the storage system information and then retrieves the specified datastores.
- -RelatedObject [DatastoreRelatedObjectBase[]] (Optional) Specifies objects to retrieve one or more Datastore objects that are related to them. This parameter accepts vSphere VirtualMachine, VMHost, Datacenter, DatastoreCluster, Cluster, Folder, HardDisk, and OMResource objects, as well as vCloud Datastore objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the datastores that are associated with any of the specified tags.

**Examples:**

```powershell
Get-VMHost -Name VMHost1, VMHost2 | Get-Datastore
```
_Retrieves datastores from the VMHost1 and VMHost2 hosts._

```powershell
Get-Datastore -Name MyDatastore* -Location MyDatacenter
```
_Retrieves the datastores from the MyDatacenter datacenter that have names starting with MyDatastore._

```powershell
$vm1 = Get-VM -Name myVM1
```
_Retrieves the datastores for a specified array of virtual machines._

### `Get-DatastoreCluster`

**This cmdlet retrieves datastore clusters.**

**Parameters:**

- -Datastore [Datastore[]] (Optional) Filters the datastore clusters by the datastores located in them.
- -Id [String[]] (Optional) Specifies the IDs of the datastore clusters you want to retrieve.
- -Location [VIContainer[]] (Optional) Specifies the datacenters and folders from which you want to retrieve datastore clusters.
- -Name [String[]] (Optional) Specifies the names of the datastore clusters you want to retrieve.
- -RelatedObject [DatastoreClusterRelatedObjectBase[]] (Required) Specifies objects to retrieve one or more DatastoreCluster objects that are related to them. This parameter accepts OMResource objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the datastore clusters that are associated with any of the specified tags.
- -Template [Template[]] (Optional) Filters the datastore clusters by the virtual machine templates located in them.
- -VM [VirtualMachine[]] (Optional) Filters the datastore clusters by the virtual machines located in them.

**Examples:**

```powershell
Get-DatastoreCluster
```
_Retrieves all datastore clusters._

```powershell
Get-DatastoreCluster -Name DatastoreCluster1
```
_Retrieves a datastore cluster by name._

```powershell
Get-VM -Name WebServerVM | Get-DatastoreCluster
```
_Retrieves datastore clusters through filtering by virtual machine._

### `Get-SpbmCapability`

**This cmdlet retrieves capability schema.**

This cmdlet retrieves capability schema sorted by alphabetical order of the Name field. Each capability schema object has a unique identifier and contains the namespace to which the capability schema object belongs. Each registered namespace must be unique. You can relate a capability schema object with a unique vendor and resource type by using the namespace. After any VAIOFilter CRUD operation, there is an expected delay of approximately 30 seconds before the changes are reflected in the Get-SpbmCapability cmdlet.

**Parameters:**

- -Category [String[]] (Optional) Specifies the capability subcategory of the capability schema object you want to retrieve.
- -Name [String[]] (Optional) Optional filter, based on full name of the capability schema object you want to retrieve. The full name must be in the format <namespace>.<CapabilityId> for the capability that contains only one property or <namespace>.<CapabilityId>.<PropertyId> for the capability that contains more than one property.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SpbmLineOfServiceType [SpbmLineOfServiceType[]] (Optional) Specifies the line of service types for the SPBM capabilities.

**Examples:**

```powershell
Get-SpbmCapability -Name "VSAN.stripeWidth"
```
_Returns all SPBM capability schemas named "VSAN.stripeWidth". The name is unique for the capability schemas._

```powershell
Get-SpbmCapability -Name VSAN*
```
_Returns all SPBM capability schemas whose name starts with VSAN._

```powershell
Get-SpbmCapability -Name "VSAN*" -Category "Performance"
```
_Returns all SPBM capability schemas whose name starts with "VSAN" and are of category "Performance"._

### `Get-SpbmCompatibleStorage`

**This cmdlet performs placement compatibility checking based on a storage requirement policy.**

This cmdlet performs placement compatibility checking based on a storage requirement policy. If the compatibility checking for a hub does not produce any errors, the hub is considered as a viable candidate for virtual machine file storage.

**Parameters:**

- -CandidateStorage [StorageResource[]] (Optional) Specifies a list of datastores and storage pods that are candidates for storage resources. If you do not specify this parameter, the server uses all of the datastores and storage pods for placement compatibility checking.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Required) Specifies a storage requirement policy.

**Examples:**

```powershell
Get-SpbmCompatibileStorage -StoragePolicy $policy
```
_Returns all datastores and datastore clusters that are in compliance with storage policy._

```powershell
Get-SpbmCompatibileStorage -StoragePolicy $policy -CandidateStorage $ListOfDatastoreOrDatastoreCluster
```
_Returns all datastores and datastore clusters from the $ListOfDatastoreOrDatastoreCluster list that are in compliance with the $policy storage policy._

### `Get-SpbmEntityConfiguration`

**This cmdlet retrieves SPBM-related configuration data of Virtual Machine, Hard Disk, and Datastore objects.**

This cmdlet retrieves SPBM-related configuration data of Virtual Machine, Hard Disk, and Datastore objects. The configuration data includes: 1. Associated storage policy for virtual machines or hard disks. 2. Compliance status for virtual machines or hard disks. 3. Associated default storage policy for datastores.

**Parameters:**

- -CheckComplianceNow [SwitchParameter] (Optional) If the value is $true, checks the compliance status and updates the server cache. If $false, returns the latest available compliance status from the server cache.
- -HardDisk [HardDisk[]] (Optional) Specifies virtual disks for which you want to check compliance.
- -HardDisksOnly [SwitchParameter] (Optional) If the value is $true, retrieves the configuration data only for hard disks.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StoragePolicy [SpbmStoragePolicy[]] (Optional) Specifies the storage policies against which the compliance status will be evaluated. A storage policy can be associated with one or multiple StorageObjects (VM Home or Disks). There will be one association object with compliance status for each policy - entity combination. If no storage policy is specified, the cmdlet returns the status for all available storage policies.
- -VM [VIObject[]] (Optional) Specifies the virtual machines, hard disks, and datastores for which you want to retrieve SPBM-related configuration data.
- -VMsOnly [SwitchParameter] (Optional) If the value is $true, retrieves the configuration data only for virtual machines.
- -Datastore [Datastore[]] (Optional) Specifies the datastores for which you want to retrieve default storage policy data.

**Examples:**

```powershell
Get-SpbmEntityConfiguration -StoragePolicy $policy
```
_Returns the SPBM configuration and compliance status of all Virtual Machine and Hard Disk objects associated with the $policy storage policy._

```powershell
Get-SpbmEntityConfiguration -StoragePolicy $policy -CheckComplianceNow
```
_Returns the SPBM configuration and compliance status of all Virtual Machine and Hard Disk objects associated with the $policy storage policy and updates the server cache._

```powershell
Get-SpbmEntityConfiguration -StoragePolicy $policy -HardDisksOnly
```
_Returns the SPBM configuration and compliance status of all Hard Disk objects associated with the $policy storage policy._

### `Get-SpbmFaultDomain`

**This cmdlet retrieves fault domains based on name or ID filter.**

This cmdlet retrieves fault domains based on name or ID filter. The fault domain ID is globally unique.

**Parameters:**

- -Id [String[]] (Required) Filters the retrieved fault domains by ID.
- -Name [String[]] (Optional) Filters the retrieved fault domains by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VasaProvider [VasaProvider[]] (Optional) Specifies the list of VASA providers. You can retrieve fault domains reported by these VASA providers.

**Examples:**

```powershell
Get-SpbmFaultDomain -Name 'FaultDomain' -VasaProvider $vasaProvider
```
_Retrieves fault domains named 'FaultDomain' from the $vasaProvider VASA provider._

```powershell
Get-SpbmFaultDomain -Id 'FaultDomainId'
```
_Retrieves the fault domain with ID 'FaultDomainId'._

### `Get-SpbmPointInTimeReplica`

**This cmdlet retrieves the point in time replica objects for the specified target replication groups.**

This cmdlet retrieves the point in time replica objects for the specified target replication groups. The cmdlet retrieves the point in time replicas by replication group, from date (inclusive), to date (exclusive), name, VASA tag, VASA provider, and replica ID.

**Parameters:**

- -Count [Int32] (Optional) Specifies the number of point in time replica objects you want to retrieve for each replication group. This restricts the result to a maximum count number of replica objects for each replication group.
- -FromDate [DateTime] (Optional) Retrieves point in time replica objects created on the specified date or later.
- -Id [String[]] (Required) Filters the retrieved point in time replica objects by ID.
- -Name [String[]] (Optional) Filters the retrieved point in time replica objects by name.
- -ReplicationGroup [SpbmReplicationGroup[]] (Optional) Specifies the target replication group for which you want to retrieve replica objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -ToDate [DateTime] (Optional) Retrieves point in time replica objects created earlier than the specified date.
- -VasaProvider [VasaProvider[]] (Optional) Specifies the VASA provider from which you want to retrieve replica objects.
- -VasaTag [String[]] (Optional) Restricts results to replica objects that have at least one of the specified VASA tags. The tags are case-sensitive.

**Examples:**

```powershell
Get-SpbmPointInTimeReplica -ReplicationGroup $targetRg
```
_Retrieves all point in time replicas from the $targetRg target replication group._

```powershell
Get-SpbmPointInTimeReplica -VasaProvider $vasaProvider -FromDate $from -ToDate $to
```
_Retrieves point in time replicas created between $from and $to by the $vasaProvider VASA provider for all its target replication groups._

### `Get-SpbmReplicationGroup`

**This cmdlet retrieves replication groups.**

This cmdlet retrieves replication groups. The replication groups can be of type source or target.

**Parameters:**

- -Datastore [Datastore[]] (Optional) Specifies the datastore to which replication groups apply. If not specified, all datastores which are compatible with the specified storage policy are considered.
- -FailedOver [SwitchParameter] (Optional) Returns only failed over replication groups.
- -FaultDomain [SpbmFaultDomain[]] (Optional) Specifies the fault domains which the replication groups are in.
- -HardDisk [HardDisk[]] (Optional) Specifies virtual disk objects to which replication groups apply.
- -Id [String[]] (Required) Filters the retrieved replication groups by ID.
- -Name [String[]] (Optional) Specifies names of replication groups you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Required) Specifies the storage policy to which the replication groups comply.
- -VasaProvider [VasaProvider[]] (Optional) Specifies the VASA provider to retrieve replication groups from.
- -VM [VIObject[]] (Optional) Specifies the virtual machines to which replication groups apply. This parameter accepts both virtual machine and hard disk objects.

**Examples:**

```powershell
Get-SpbmReplicationGroup -Name 'ReplicationGroup' -FaultDomain $faultDomain
```
_Retrieves replication groups named 'ReplicationGroup' in the $faultDomain fault domain._

```powershell
Get-SpbmReplicationGroup -Datastore $datastore -StoragePolicy $policy
```
_Retrieves replication groups which are applicable to the $datastore datastore and comply with the $policy storage policy._

```powershell
Get-SpbmReplicationGroup -VM $vm -HardDisk $hd
```
_Retrieves replication groups which are associated with the $vm virtual machine and the $hd hard disk._

### `Get-SpbmReplicationPair`

**This cmdlet retrieves the relation of replication groups in a pair of source and target replication group.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Source [SpbmReplicationGroup[]] (Optional) Specifies the source replication group.
- -SourceFaultDomain [SpbmFaultDomain[]] (Optional) Specifies the list of fault domains to get source replication group of the pair.
- -Target [SpbmReplicationGroup[]] (Optional) Specifies the target replication group.
- -TargetFaultDomain [SpbmFaultDomain[]] (Optional) Specifies the list of fault domains to get target replication group of the pair.

**Examples:**

```powershell
Get-SpbmReplicationPair -Source $rg
```
_Retrieves replication pairs for which the $rg replication group is source group._

```powershell
Get-SpbmReplicationPair -SourceFaultDomain $sourceFd -TargetFaultDomain $targetFd
```
_Retrieves replication pairs for which the source replication group is in the $sourceFd fault domain and the target replication group is in the $targetFd fault domain._

### `Get-SpbmStoragePolicy`

**This cmdlet returns all available requirement policies and resource policies.**

**Parameters:**

- -Capability [SpbmCapability[]] (Optional) Filters the storage policies by capability schema.
- -Id [String[]] (Optional) Filters the storage policies by ID.
- -Name [String[]] (Optional) Filters the storage policies by name.
- -Namespace [String[]] (Optional) Filters the storage policies by namespace.
- -Requirement [SwitchParameter] (Optional) Specifies the policy category. Policy category can be either "requirement" or "resource". If nothing specified, retrieves both.
- -Resource [SwitchParameter] (Optional) Specifies the policy category. Policy category can be either "requirement" or "resource". If nothing specified, retrieves both.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Filters the storage policies by tag.

**Examples:**

```powershell
Get-SpbmStoragePolicy -Name "MyPolicy"
```
_Returns all storage policies named "MyPolicy"._

```powershell
Get-SpbmStoragePolicy -Requirement -Namespace "VSAN" -Tag $tag1, $tag2
```
_Returns all storage policies of type Requirement containing one or more rules which contain one or more capabilities from the "VSAN" namespace and any of the $tag1 or $tag2 tags._

```powershell
Get-SpbmStoragePolicy -Id "PolicyId"
```
_Returns a storage policy with ID "PolicyId"._

### `Get-SpbmView`

**This cmdlet retrieves SPBM views for the managed objects in the SPBM server.**

This cmdlet retrieves SPBM views for the managed objects in the SPBM server. The following options are supported: 1. By the specified IDs. The string value of the ID is in format <type>-<value> as it is in the PowerShell toolkit objects. 2. By the SPBM service contents. Returns views for all the managed objects available in the SPBM service contents.

**Parameters:**

- -Id [ManagedObjectReference[]] (Required) Specifies the ManagedObjectReference for which you want to retrieve the view. This parameter also accepts strings by silently converting them to ManagedObjectReference by using ArgumentTransformationAttribute.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ServiceContent [SwitchParameter] (Optional) When specified, returns views for all the managed objects in the SPBM service contents.

**Examples:**

```powershell
Get-SpbmView -ServiceContent -Server "MyServer"
```
_Retrieves all SPBM view objects of the SPBM service content from the "MyServer" connected server._

```powershell
Get-SpbmView -Id "ManagedObjectId"
```
_Retrieves the SPBM view object of a SPBM managed object with a "ManagedObjectId" ID._

```powershell
$serviceInstanceView = Get-SpbmView -Id "PbmServiceInstance-ServiceInstance"
```
_Retrieves the SPBM view object of the ProfileManager singleton managed object._

### `Get-VDisk`

**This cmdlet lists VDisk objects based on the specified filters.**

**Parameters:**

- -Datastore [Datastore[]] (Optional) Specifies the datastore from which you want to retrieve the VDisk objects.
- -Id [String[]] (Required) Filters the VDisk objects by ID.
- -Name [String[]] (Optional) Filters the VDisk objects by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VDisk -Name 'MyDisk' -Datastore $ds
```
_Retrieves the VDisk objects named 'MyDisk' from the $ds datastore._

```powershell
Get-VDisk -Id 'VDiskId'
```
_Retrieves the VDisk with Id 'VDiskId'._

### `Get-VasaStorageArray`

**This cmdlet retrieves the list of storage arrays managed by registered VASA providers.**

**Parameters:**

- -Id [String[]] (Required) Retrieves all storage arrays with an ID set to "MyArrayId".
- -Lun [ScsiLun[]] (Optional) Filters the retrieved storage arrays by LUN. If not specified, all storage arrays are retrieved. You can retrieve LUN objects by using the Get-ScsiLun cmdlet.
- -Name [String[]] (Optional) Filters the retrieved storage arrays by name.
- -Refresh [SwitchParameter] (Optional) Synchronizes the storage arrays before retrieving data. The operation is synchronous.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VasaProvider [VasaProvider[]] (Optional) Filters the retrieved storage arrays by provider. If not specified, all storage arrays are retrieved. You can retrieve the provider objects by using the Get-VasaProvider cmdlet.
- -StorageContainer [VvolStorageContainer[]] (Optional) Filters the retrieved storage arrays by the Virtual Volume (vVol) storage containers. You can retrieve the storage container objects by using the Get-VvolStorageContainer cmdlet.

**Examples:**

```powershell
Get-VasaStorageArray -Name "MyArray" -Refresh
```
_Synchronizes the providers and retrieves the storage array named "MyArray"._

```powershell
Get-VasaStorageArray -Id "MyArrayId"
```
_Retrieves all storage arrays with ID set to "MyArrayId"._

### `Get-VsanClusterConfiguration`

**This cmdlet retrieves vSAN related configuration data from clusters.**

This cmdlet retrieves vSAN related configuration data from clusters. Some fields are smart lazy initialized.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters from which you want to retrieve vSAN configuration data. If not specified, retrieves vSAN configuration data from all clusters.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanClusterConfiguration -Cluster "MyCluster"
```
_Retrieves the vSAN cluster configuration of the clusters named "MyCluster"._

### `Get-VsanClusterPowerState`

**This cmdlets retrieves the power state of a vSAN cluster.**

This cmdlets retrieves the power state of a vSAN cluster. You can use this cmdlet to check the power state of vSAN clusters, especially after powering them on or off.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster for which you want to retrieve the power state.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanClusterPowerState -Cluster "VSAN-Cluster"
```
_Retrieves the power state of the specified cluster._

### `Get-VsanComponent`

**This cmdlet retrieves basic information about the vSAN component, including its universal unique identifier (UUID), the vSAN object it belongs to, the disk it resides on, and its status and type.**

This cmdlet retrieves basic information about the vSAN component, including its uuid, the vSAN object it belongs to, the disk it resides on, its status and type.

**Parameters:**

- -Id [String[]] (Optional) Filters vSAN components by ID.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -VsanDisk [VsanDisk[]] (Optional) Filters vSAN components by the specific vSAN disk.
- -VsanStoragePoolDisk [VsanStoragePoolDisk[]] (Optional) Filters vSAN components by the specific vSAN storage pool disk. This parameter is available starting from vSphere8.0.
- -VsanObject [VsanObject[]] (Optional) Filters vSAN components by the specific vSAN object.

**Examples:**

```powershell
Get-VsanComponent -Id $id
```
_Retrieves vSAN components by filtering them by ID._

```powershell
Get-VsanComponent -VsanObject $vsanObject
```
_Retrieves the component that belongs to the vSAN object._

```powershell
Get-VsanComponent -VsanDisk $vsanDisk
```
_Retrieves the component that resides on the vSAN disk._

### `Get-VsanDirectDisk`

**This cmdlet retrieves vSAN Direct disks based on the specified filters.**

This cmdlet retrieves vSAN Direct disks based on the specified filters. This cmdlet is not supported in a vSAN ESA enabled cluster. You can use this cmdlet starting from vSAN 7.0 Update 1.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the cluster from which to fetch the vSAN Direct disk info.
- -DiskCanonicalName [String[]] (Optional) Specifies the identifier of the disk. It accepts one or more disk canonical names.
- -Id [String[]] (Required) Specifies the ID(s) of the vSAN Direct disk(s) that you want to retrieve. The ID format is "{uuid}/{host}".
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts from which to fetch the vSAN Direct disk info.

**Examples:**

```powershell
Get-VsanDirectDisk -diskcanonicalname "mpx.vmhba0:C0:T3:L0"
```
_Retrieves all vSAN Direct disks with the specified canonical name._

```powershell
Get-VsanDirectDisk -vmhost "10.212.18.213"
```
_Retrieves all vSAN Direct disks from the specified host._

```powershell
Get-VsanDirectDisk -id "HostSystem-host-16/0000000000766d686261303a333a30"
```
_Retrieves the vSAN Direct disks with the specified ID._

### `Get-VsanDisk`

**This cmdlet retrieves the host disks that belong to a vSAN disk group.**

This cmdlet retrieves the host disks that belong to a vSAN disk group. The cmdlet retrieves both SSD and HDD types of disks.

**Parameters:**

- -CanonicalName [String[]] (Optional) Specifies the canonical names of the retrieved disks.
- -Id [String[]] (Required) Specifies the IDs of the retrieved disks.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts that the retrieved disks are attached to.
- -VsanDiskGroup [VsanDiskGroup[]] (Optional) Specifies the vSAN disk groups that the disks are part of.

**Examples:**

```powershell
Get-VsanDisk -CanonicalName "DiskCanonicalName" -VMHost $vmHost
```
_Retrieves all vSAN disks with canonical name "DiskCanonicalName" from the $vmHost virtual machine host._

```powershell
Get-VsanDisk -CanonicalName "DiskCanonicalName" -VsanDiskGroup $vsanDiskGroup
```
_Retrieves all vSAN disks with canonical name "DiskCanonicalName" from the $vsanDiskGroup vSAN disk group._

```powershell
Get-VsanDisk -Id "MyVsanDiskId"
```
_Retrieves the vSAN disk with ID "MyVsanDiskId"._

### `Get-VsanDiskGroup`

**This cmdlet retrieves vSAN disk groups.**

This cmdlet retrieves vSAN disk groups in a cluster or a host, by ID, name, or the canonical name of a disk within the disk group.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters that the retrieved groups are on.
- -DiskCanonicalName [String[]] (Optional) Specifies the canonical names of disks that are part of the retrieved groups.
- -Id [String[]] (Required) Specifies the IDs of disks that are part of the retrieved groups.
- -Name [String[]] (Optional) Specifies the name of the vSAN disk group you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the hosts that the retrieved groups are on.

**Examples:**

```powershell
Get-VsanDiskGroup -DiskCanonicalName "DiskCanonicalName" -VMHost $vmHost
```
_Retrieves all vSAN disk groups that contain a disk with canonical name "DiskCanonicalName" from the $vmHost virtual machine host._

```powershell
Get-VsanDiskGroup -Name "MyVsanDiskGroup" -Cluster $cluster
```
_Retrieves all vSAN disk groups named "MyVsanDiskGroup" from the $cluster cluster._

```powershell
Get-VsanDiskGroup -Id "MyVsanDiskGroupId"
```
_Retrieves the vSAN disk group with ID "MyVsanDiskGroupId"._

### `Get-VsanEnterMaintenanceModeReport`

**This cmdlet retrieves the report of capacity or objects which may have accessbility or compliance issues, if a virtual machine host enters maintenance mode.**

This cmdlet retrieves the report of capacity or objects which may have accessbility or compliance issues, if a virtual machine host enters maintenance mode. The report data includes: 1. Overall state: The possible statuses are:    Green - resource check passed for the queried operation. There is sufficient resource in the vSAN cluster to perform the queried operation.    Yellow - resource check passed for the queried operation, but there is an existing issue in the cluster, for example, network partition.    Red - resource check failed for the queried operation. Extra resource is required to make the given operation succeed. 2. Each virtual machine host's capacity report for the Capacity parameter set. 3. Objects which may have accessbility or compliance issues for the AccessbilityAndCompliance parameter set.

**Parameters:**

- -AccessbilityAndCompliance [SwitchParameter] (Optional) If specified, retrieves inaccessible or noncompliant objects.
- -Capacity [SwitchParameter] (Optional) If specified, retrieves details of the resource check.
- -VMHost [VMHost] (Required) Specifies the virtual machine host that enters the maintenance mode.
- -VsanDataMigrationMode [String] (Required) Specifies the vSAN data migration mode. The valid values are: ensureObjectAccessibility: The vSAN data reconfiguration should be performed to ensure storage object accessibility. evacuateAllData: The vSAN data evacuation should be performed in such a way that you can remove all storage object data from the virtual machine host. noAction: No special action should take place regarding the vSAN data.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanEnterMaintenanceModeReport -VMHost $vmHost -AccessbilityAndCompliance
```
_Retrieves one VsanEnterMaintenanceModeReport with objects which may have accessbility or compliance issues._

```powershell
Get-VsanEnterMaintenanceModeReport -VMHost $vmHost -Capacity
```
_Retrieves one VsanEnterMaintenanceModeReport with each virtual machine host's capacity report._

### `Get-VsanEsaEligibleDisk`

**This cmdlet fetches ScsiLun information for all vSAN ESA eligible disks of the target object which can be a vSAN cluster or a list of hosts.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters from which to fetch the vSAN ESA eligible disks.
- -ScsiLun [ScsiLun[]] (Required) Specifies the ScsiLun objects to be validated and returns only the vSAN ESA eligible ones.
- -VMHost [VMHost[]] (Required) Specifies the hosts from which to fetch the vSAN ESA eligible disks.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanEsaEligibleDisk -VMHost (get-vmhost 10.78.193.26)
```
_Retrieves vSAN ESA eligible disks by a specified host._

```powershell
Get-VsanEsaEligibleDisk -Cluster $config.cluster
```
_Retrieves vSAN ESA eligible disks by a specified cluster._

```powershell
$disk = Get-scsilun -VMHost (get-vmhost 10.78.193.26)
```
_Validates and retrieves vSAN ESA eligible disks by a range of ScsiLun data objects._

### `Get-VsanEvacuationPlan`

**This cmdlet retrieves information about the entity (disk, disk group, or host) you want to evacuate in various modes.**

This cmdlet retrieves information about the entity (disk, disk group, or host) you want to evacuate in various modes. You receive information about capacity usage only when the cmdlet determines that an entity can be evacuated in a given mode.

**Parameters:**

- -Entity [VIObjectCore[]] (Required) Specifies the entity for which you want to retrieve evacuation information. This parameter accepts VMHost, VsanDisk, VsanDiskGroup, and VsanStoragePoolDisk(vSphere 8.0 and later) entity types. OBN and wildcard are supported for VMHost type only.
- -EvacuationMode [VsanDataMigrationMode[]] (Optional) Filters the results by data migration mode options.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanEvacuationPlan -Entity $vmHost
```
_Retrieves the evacuation plan about removing the $vmHost virtual machine host from the cluster._

```powershell
Get-VsanEvacuationPlan -Entity $diskGroup -EvacuationPlan Full
```
_Retrieves the evacuation plan about removing the $diskGroup vSAN disk group for vSAN full data migration mode._

```powershell
Get-VsanEvacuationPlan -Entity $vsanStoragePoolDisk -EvacuationPlan Full
```
_Retrieves the evacuation plan about removing the $vsanStoragePoolDisk vSAN storage pool disk for vSAN full data migration mode. Note: The VsanStoragePoolDisk entity type is available from vSphere 8.0._

### `Get-VsanFaultDomain`

**This cmdlet retrieves vSAN fault domains based on name or ID filter.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the vSAN cluster to which the fault domain belongs.
- -Id [String[]] (Required) Filters the retrieved vSAN fault domains by ID.
- -Name [String[]] (Optional) Filters the retrieved vSAN fault domains by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies the list of virtual machine hosts to filter the vSAN fault domains. Filters the fault domains that contain any of the given hosts.

**Examples:**

```powershell
Get-VsanFaultDomain -VMHost $vmHost
```
_Retrieves the vSAN fault domain which contains the $vmHost virtual machine host._

```powershell
Get-VsanFaultDomain -Cluster $cluster -Name "MyFaultDomain"
```
_Retrieves the vSAN fault domain named "MyFaultDomain" from the $cluster vSAN cluster._

### `Get-VsanFileServiceDomain`

**This cmdlet retrieves vSAN file service domains in a vSAN cluster.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the vSAN cluster to which the file service domain belongs.
- -Id [String[]] (Required) Filters the retrieved vSAN file service domains by ID.
- -Name [String[]] (Optional) Filters the retrieved vSAN file service domains by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanFileServiceDomain -Cluster $cluster
```
_Retrieves the vSAN file service domain from the $cluster vSAN cluster._

```powershell
Get-VsanFileServiceDomain -Cluster $cluster -Name "MyDomain"
```
_Retrieves the vSAN file service domain named "MyDomain" from the $cluster vSAN cluster._

### `Get-VsanFileServiceOvfInfo`

**This cmdlet retrieves a vSAN file service OVF information.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanFileServiceOvfInfo
```
_Retrieves the vSAN file service OVF information._

### `Get-VsanFileShare`

**This cmdlet retrieves vSAN file shares based on the name or ID filter.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the vSAN cluster to which the file share belongs.
- -FileServiceDomain [VsanFileServiceDomain[]] (Optional) Specifies the vSAN file service domain to which the vSAN file share belongs. If not specified, the vSAN file shares under all vSAN file service domains will be queried.
- -Id [String[]] (Required) Filters the retrieved vSAN file share by ID.
- -Name [String[]] (Optional) Filters the retrieved vSAN file share by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanFileShare -FileServiceDomain $fileServiceDomain
```
_Retrieves the vSAN file share which belongs to the $fileServiceDomain file service domain._

```powershell
Get-VsanFileShare -Cluster $cluster -Name "FileShare1"
```
_Retrieves the vSAN file share named "FileShare1" from the $cluster vSAN cluster._

### `Get-VsanFileShareSnapshot`

**This cmdlet retrieves vSAN file share snapshots based on the name or other filters.**

This cmdlet retrieves vSAN file share snapshots based on name or other filters.

**Parameters:**

- -EndTime [DateTime] (Optional) Specifies end time of creation for the vSAN file share snapshots you want to retrieve.
- -FileShare [VsanFileShare[]] (Optional) Specifies the vSAN file share to which the file share snapshots belong.
- -Name [String[]] (Optional) Filters the retrieved vSAN file share snapshots by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StartTime [DateTime] (Optional) Specifies start time of creation for the vSAN file share snapshots you want to retrieve.

**Examples:**

```powershell
Get-VsanFileShareSnapshot -Name "SnapshotName"
```
_Retrieves the vSAN file share snapshots whose name is "SnapshotName"._

```powershell
Get-VsanFileShareSnapshot -StartTime "12/21/2020" -EndTime "12/22/2020"
```
_Retrieves the vSAN file share snapshots which have been created in the specified time interval._

### `Get-VsanHCIMeshDatastore`

**This cmdlet retrieves vSAN HCI Mesh datastores based on the specified filters.**

This cmdlet retrieves vSAN HCI Mesh datastores based on the specified filters. You can use this cmdlet starting from vSAN 8.0 Update 1.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VsanHCIMeshDatastoreSource [VsanHCIMeshDatastoreSource[]] (Required) Specifies the vSAN HCI Mesh datastore source(s) from which to retrieve the datastore.

**Examples:**

```powershell
$ds = Get-VsanHCIMeshDatastoreSource -VCHost ('10.161.94.0')
```
_Retrieves a vSAN HCI Mesh datastore from the specified HCI Mesh datastore source._

### `Get-VsanHCIMeshDatastoreSource`

**This cmdlet retrieves vSAN HCI Mesh datastore sources based on the specified filters.**

This cmdlet retrieves vSAN HCI Mesh datastore sources based on the specified filters. You can use this cmdlet starting from vSAN 8.0 Update 1.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VCHost [String[]] (Required) Specifies the remote vCenter Server IP address or FQDN from which to retrieve the HCI Mesh datastore source(s).

**Examples:**

```powershell
Get-VsanHCIMeshDatastoreSource -VCHost ('10.186.46.61')
```
_Retrieves the vSAN HCI Mesh datastore sources with the specified VCHost._

### `Get-VsanIscsiInitiatorGroup`

**This cmdlet retrieves vSAN iSCSI initiator groups.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the list of clusters to query for initiator groups.
- -Id [String[]] (Required) Filters the retrieved initiator groups by ID.
- -Name [String[]] (Optional) Filters the retrieved initiator groups by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanIscsiInitiatorGroup -Cluster "vsan-cluster"
```
_Retrieves all vSAN iSCSI initiator groups from the "vsan-cluster" cluster._

### `Get-VsanIscsiInitiatorGroupTargetAssociation`

**This cmdlet retrieves all pairs of associations between vSAN iSCSI targets and initiator groups, which have access to the corresponding targets.**

**Parameters:**

- -InitiatorGroup [VsanIscsiInitiatorGroup[]] (Optional) Specifies the vSAN iSCSI initiator groups.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Target [VsanIscsiTarget[]] (Optional) Specifies the vSAN iSCSI targets.

**Examples:**

```powershell
Get-VsanIscsiInitiatorGroupTargetAssociation -Target $target
```
_Retrieves all initiator group associations for the $target iSCSI target._

```powershell
Get-VsanIscsiInitiatorGroupTargetAssociation -InitiatorGroup $initiatorGroup
```
_Retrieves all target associations for the $initiatorGroup initiator group._

### `Get-VsanIscsiLun`

**This cmdlet retrieves the vSAN iSCSI LUNs from a cluster or target.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters from which to retrieve LUNs.
- -Id [String[]] (Required) Filters the retrieved vSAN iSCSI LUNs by ID.
- -LunId [Int32[]] (Optional) Filters the retrieved vSAN iSCSI LUNs by LUN ID.
- -Name [String[]] (Optional) Filters the retrieved vSAN iSCSI LUNs by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VsanIscsiTarget [VsanIscsiTarget[]] (Optional) Specifies the vSAN iSCSI targets from which to retrieve LUNs.

**Examples:**

```powershell
Get-VsanIscsiLun -Cluster "vsan-cluster"
```
_Retrieves all vSAN iSCSI LUNs from the "vsan-cluster" cluster._

```powershell
Get-VsanIscsiLun -Target $target -LunId 1
```
_Retrieves the vSAN iSCSI LUNs with LunId 1 from the $target iSCSI target._

### `Get-VsanIscsiTarget`

**This cmdlet retrieves vSAN iSCSI targets from clusters.**

This cmdlet retrieves vSAN iSCSI targets from clusters. The cmdlet can filter targets by IQN and aliases.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters from which to retrieve vSAN iSCSI targets.
- -Id [String[]] (Required) Filters the retrieved vSAN iSCSI targets by ID.
- -IscsiQualifiedName [String[]] (Optional) Filters the retrieved vSAN iSCSI targets by IQN.
- -Name [String[]] (Optional) Filters the retrieved vSAN iSCSI targets by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanIscsiTarget -Cluster "vsan-cluster"
```
_Retrieves all vSAN iSCSI targets from the "vsan-cluster" cluster._

```powershell
Get-VsanIscsiTarget -Cluster $cluster -Name "Target1"
```
_Retrieves the vSAN iSCSI target named "Target1" from the $cluster vSAN cluster._

### `Get-VsanObject`

**This cmdlet retrieves vSAN objects based on the specified filters.**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters from which to retrieve the vSAN objects.
- -Type [VsanObjectType[]] (Optional) Specifies the types of the vSAN objects to be retrieved.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines to which the vSAN objects you want to retrieve belong.
- -VsanDisk [VsanDisk[]] (Optional) Specifies the vSAN disk on which the vSAN objects you want to retrieve reside.
- -VsanStoragePoolDisk [VsanStoragePoolDisk[]] (Optional) Specifies the vSAN storage pool disk on which the vSAN objects you want to retrieve reside. The disks are managed as a vSAN storage pool disk in a vSAN ESA enabled cluster. This parameter is available starting from vSphere8.0.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Id [String[]] (Required) Specifies the vSAN UUID of that vSAN objects that you want to retrieve.

**Examples:**

```powershell
Get-VsanObject -Cluster $clusters
```
_Retrieves information of all vSAN objects from the specified clusters._

```powershell
Get-VsanObject -Cluster $clusters -VM $vms
```
_Retrieves information of the vSAN objects in the specified clusters. The vSAN objects should associate with the specified virtual machines._

```powershell
Get-VsanObject -Cluster $clusters -VsanDisk $disks
```
_Retrieves information of the vSAN objects in the specified clusters. The vSAN objects should reside in the specified vSAN disks._

### `Get-VsanPerformanceContributor`

**This cmdlet retrieves a list of the most impactful vSAN performance contributors, based on the specified entity type. The list includes the contributors that exhibit the highest IOPS, throughput, or latency consumption within the provided start and end times in the specified vSAN cluster.**

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the cluster for which you want to retrieve vSAN performance contributors.
- -Entity [VsanPerfContributorEntityType] (Required) Specifies the entity for which you want to retrieve vSAN performance contributors. Represents the managed object type of the top entities. The accepted values are VirtualMachine, DiskGroup, HostDomClient, HostDomCompmgr, and VsanEsaDiskLayer.
- -MetricId [VsanPerfContributorMetricIdType] (Required) Specifies the metric for which you want to retrieve vSAN performance contributors. The valid metric types for the "VirtualMachine", "DiskGroup", "HostDomClient", and "HostDomCompmgr" entities are "IopsRead", "IopsWrite", "ThroughputRead", "ThroughputWrite", "LatencyRead", "LatencyWrite". The valid metric types for the "VsanEsaDiskLayer" entity are "IopsReadCapacity", "IopsWriteCapacity", "TputReadCapacity", "TputWriteCapacity", "AvgLatReadCapacity", and "AvgLatWriteCapacity".
- -EntityCountLimit [Int32] (Optional) Specifies the number of vSAN performance contributors that you want to retrieve. The default value is 10 and the maximum is 64.
- -StartTime [DateTime] (Required) Specifies the client local start time for which you want to retrieve vSAN performance contributors. Please note that the maximum allowable duration between StartTime and EndTime is 24 hours.
- -EndTime [DateTime] (Required) Specifies the client local end time for which you want to retrieve vSAN performance contributors.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
$cluster = get-cluster
```
_Retrieves the vSAN performance entities given the time constraints, the "HostDomClient" entity type, and the "LatencyWrite" metric._

```powershell
get-vsanperformanceContributor -startTime 2023-08-27T05:17:00 -entity "VirtualMachine" -endtime 2023-08-28T06:17:00 -cluster $cluster -EntityCountLimit 5 -MetricId "IopsWrite"
```
_Retrieves the top five vSAN performance entities given the time constraints, the "VirtualMachine" entity type, and the "IopsWrite" metric._

### `Get-VsanResyncingComponent`

**This cmdlet retrieves the details of components going through synchronization in a vSAN cluster.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster for which to retrieve synchronization details.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanResyncingComponent -Cluster $cluster
```
_Retrieves the vSAN resyncing components from the $cluster cluster._

### `Get-VsanResyncingOverview`

**This cmdlet retrieves the overview of objects going through synchronization in a vSAN cluster. It will query information about vSAN objects that are currently syncing data.**

This cmdlet retrieves the overview of objects going through synchronization in a vSAN cluster.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster for which you want to retrieve synchronization details.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanResyncingOverview -Cluster $cluster
```
_Retrieves the vSAN resyncing overview of objects from the $cluster cluster._

### `Get-VsanRuntimeInfo`

**This cmdlet retrieves the runtime information of a vSAN cluster.**

This cmdlet retrieves the runtime information and of a vSAN cluster, such as resynchronization traffic information of the ongoing resynchronization operation.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster from which you want to retrieve runtime information.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanRuntimeInfo -Cluster $vsanCluster
```
_Retrieves the vSAN runtime information of the $vsanCluster cluster._

### `Get-VsanSpaceUsage`

**This cmdlet retrieves space usage details of a vSAN cluster. (Note that the output attribute denoted with 'GB' signifies the unit of Gibibytes (GiB), utilizing a base-2 binary representation.)**

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the vSAN clusters for which to retrieve space usage details.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy[]] (Optional) Get usable free capacity and total capacity if all objects in the vSAN datastore use the specified storage policy.

**Examples:**

```powershell
Get-VsanSpaceUsage -Cluster $cluster
```
_Retrieves space usage details of the $cluster vSAN cluster._

```powershell
Get-VsanSpaceUsage -Cluster $cluster -StoragePolicy "vSAN Default Storage Policy"
```
_Retrieves space usage details of the $cluster vSAN cluster and what-if usable free space if all new vSAN objects using the specified vSAN storage policy._

### `Get-VsanStat`

**This cmdlet retrieves vSAN performance statistics for the specified server entity.**

**Parameters:**

- -Name [String[]] (Optional) Specifies the performance metrics you want to retrieve. If not specified, all the metrics are returned. The value is in the format 'ViewName.MetricName'.
- -Entity [VIObjectCore[]] (Optional) Specifies the entity for which you want to retrieve vSAN performance metrics. OBN is supported for the Cluster, VMHost, VirtualMachine, VsanIscsiTarget, and VsanStoragePoolDisk (vSphere 8.0 and later) entity types.
- -StartTime [DateTime] (Optional) Specifies the client local time from which you want to retrieve statistics. The returned samples do not include the sample at StartTime.
- -EndTime [DateTime] (Optional) Specifies the client local time up to which you want to retrieve statistics. If the specified value is later than current server time, the value is replaced by the current server time. The returned samples include the sample at EndTime.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -PredefinedTimeRange [VsanPredefinedTimeRange] (Required) A list of predefined time ranges (Last5Minutes, Last15Minutes, Last30Minutes, LastHour, Last24Hours, LastWeek) provides a more efficient way to specify time range in querying vSAN performance metric than using the StartTime and EndTime parameters.

**Examples:**

```powershell
$diskGroups = Get-VsanDiskGroup -Cluster "vsan-cluster"
```
_Retrieves all vSAN performance samples for vSAN disk groups of the "vsan-cluster" cluster._

```powershell
Get-VsanStat -Entity "vsan-cluster" -Name "Backend.ReadThroughput"
```
_Retrieves vSAN performance samples for backend read throughput of the "vsan-cluster" cluster._

```powershell
$cluster = Get-Cluster -Name "vsan-cluster"
```
_Retrieves the read IOPS stats relevant to the VM consumption view of the "vsan-cluster" cluster in the $startTime to $endTime local time range._

### `Get-VsanStoragePoolDisk`

**This cmdlet fetches VsanStoragePoolDisk information from a certain host or cluster. It also enables you to fetch storage pool disks by disk canonical name. If both host and disk canonical name are specified, the system uses both parameters.**

**Parameters:**

- -DiskCanonicalName [String[]] (Optional) Specifies the identifier of the disk. It accepts one or more disk canonical names.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the VMHost from which to fetch the storage pool disk info.
- -Cluster [Cluster[]] (Required) Specifies the Cluster from which to fetch the storage pool disk info.
- -VsanStoragePoolDiskType [VsanStoragePoolDiskType] (Optional) Specifies the type of vSAN storage pool disk. Accepted values are single tier, capacity tier and performance tier. Note: This parameter is not currently supported and will be activated in a future release.

**Examples:**

```powershell
Get-VsanstoragepoolDisk -Cluster $config.cluster
```
_Retrieves all vSAN storage pool disks from the specified cluster._

```powershell
Get-VsanStoragePoolDisk -VMHost (Get-VMHost 10.192.207.142)
```
_Retrieves all vSAN storage pool disks from the specified host._

```powershell
Get-VsanStoragePoolDisk -VMHost (Get-VMHost 10.192.207.142) -DiskCanonicalName "mpx.vmhba0:C0:T4:L0"
```
_Retrieves all vSAN storage pool disks from the specified host and with the specified canonical name._

### `Get-VsanView`

**This cmdlet retrieves vSAN views that match the specified IDs.**

This cmdlet retrieves vSAN views that match the specified IDs. The string value of the ID is in format <type>-<value> as it is in the PowerShell toolkit objects.

**Parameters:**

- -Id [ManagedObjectReference[]] (Optional) Specifies the ManagedObjectReference for which you want to retrieve the view. This parameter also accepts strings by silently converting them to ManagedObjectReference by using ArgumentTransformationAttribute. If not specified, all vSAN view objects available on the server are returned.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VsanView -Server "MyServer"
```
_Retrieves all singleton vSAN view objects from the "MyServer" connected server._

```powershell
Get-VsanView -Id "ManagedObjectId"
```
_Retrieves the view object of a vSAN managed object with ID "ManagedObjectId"._

### `Get-VsanWipeDiskStatus`

**This cmdlet retrieves a disk level information about securely wiping disks.**

**Parameters:**

- -CanonicalName [String[]] (Required) Specifies the canonical name of the host SCSI disk.
- -VMHost [VMHost] (Required) Specifies the hosts on which the disks belong.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-VsanWipeDiskStatus -CanonicalName "DiskCanonicalName" -VMHost $host
```
_Retrieves the vSAN wipe disk status of "DiskCanonicalName" from the $host host._

### `Get-VvolStorageContainer`

**This cmdlet retrieves the list of Virtual Volume (vVol) storage containers that are reported by the registered VASA providers.**

This cmdlet retrieves the list of vVol storage containers that are reported by the registered VASA providers.

**Parameters:**

- -Id [String[]] (Required) Retrieves the vVol storage containers by ID.
- -Name [String[]] (Optional) Filters the retrieved vVol storage containers by name.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StorageArray [VasaStorageArray[]] (Optional) Filters the retrieved storage containers by array. You can retrieve the provider objects by using the Get-VasaStorageArray cmdlet.
- -VasaProvider [VasaProvider[]] (Optional) Filters the retrieved storage containers by provider. You can retrieve the provider objects by using the Get-VasaProvider cmdlet.

**Examples:**

```powershell
Get-VvolStorageContainer -Name "MyStorageContainer"
```
_Retrieves all vVol storage containers named "MyStorageContainer"._

```powershell
Get-VvolStorageContainer -VasaProvider "MyProvider"
```
_Retrieves all vVol storage containers reported by the VASA provider named "MyProvider"._

```powershell
Get-VvolStorageContainer -Id "MyStorageContainerId"
```
_Retrieves all vVol storage containers with an ID set to "MyStorageContainerId"._

## Import

### `Import-SpbmStoragePolicy`

**This cmdlet imports a storage policy from a file.**

This cmdlet imports a storage policy from a file. The file path must be accessible from the VMware PowerCLI client side.

**Parameters:**

- -Description [String] (Optional) Specifies a description for the imported storage policy.
- -FilePath [String] (Required) Specifies the path to the file, from which you want to import a storage policy. If relative, it is relative to the current PS provider path.
- -Name [String] (Required) Specifies a name of the imported storage policy. The maximum length of the name is 80 characters.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Import-SpbmStoragePolicy -Name "MyPolicy" -Description "PolicyDescription" -FilePath C:\policy.xml
```
_Imports a storage policy with name "MyPolicy" and description "PolicyDescription" from the policy.xml file to a server. A new storage policy is created on the server._

## Move

### `Move-Datastore`

**This cmdlet moves datastores from one location to another.**

**Parameters:**

- -Datastore [Datastore[]] (Required) Specifies the datastore that you want to move.
- -Destination [VIObject] (Required) Specifies a datastore cluster, folder, or datacenter where you want to place the datastore.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Move-Datastore "MyDatastore" -Destination "MyDatastoreFolder"
```
_Moves the MyDatastore datastore to the specified folder._

```powershell
$myDatastoreCluster = Get-DatastoreCluster -Name "MyDatatoreCluster"
```
_Moves two datastores to a specified datastore cluster._

### `Move-VDisk`

**This cmdlet moves the specified VDisk objects to the specified datastore.**

This cmdlet moves the specified VDisk objects to the specified datastore. For RDM (RawVDisk), only one VDisk object can be moved at once, and only moving from VMFS to VMFS is supported.

**Parameters:**

- -Datastore [Datastore] (Required) Specifies the datastore to which you want to move the metadata of the VDisk object. For flat disk, the contents of the disk are also moved to the specified datastore.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -ScsiLun [ScsiLun] (Required) Specifies the new backing SCSI LUN for the RDM VDisk object that is moved.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageFormat [VDiskStorageFormat] (Optional) Specifies the new storage format of the flat VDisk object that is moved.
- -VDisk [VDisk[]] (Required) Specifies the VDisk objects you want to move.

**Examples:**

```powershell
Move-VDisk -VDisk $vDisk -Datastore $ds
```
_Moves the flat VDisk object $vDisk to the $ds datastore._

```powershell
Move-VDisk -VDisk $vDisk -ScsiLun $scsiLun -Datastore $ds
```
_Moves the raw VDisk object $vDisk on the $scsiLun SCSI LUN and stores metadata of this object on the $ds datastore._

## New

### `New-CnsVolume`

**This cmdlet creates a Cloud Native Storage (CNS) volume.**

**Parameters:**

- -Name [String] (Required) Specifies the name of the CNS volume.
- -CnsVolumeMetadata [CnsVolumeMetadata] (Required) Specifies the metadata for the CNS volume.
- -SoftQuotaGB [Decimal] (Optional) Specifies the soft quota configuration at the vSAN file share level. This is the soft quota for the file share.
- -CapacityMB [long] (Required) Specifies the container volume capacity in MB.
- -Datastore [Datastore[]] (Required) Specifies the datastores that you want to use for the volume placement. In case of multiple placement candidate datastores, the server selects one datastore (subject to change) based on various factors such as storage policy and available free space.
- -StoragePolicy [StoragePolicy] (Optional) Specifies the storage profile for the container volume. A vSAN datastore default policy  is used when this field is not set.
- -FileShareNetworkPermission [FileShareNetworkPermission] (Required) Specifies the permission parameters that you want to use for this vSAN file share. If this field is not set, no user can access this vSAN file share.
- -VDisk [VDisk] (Required) Specifies the block backing for a container volume.
- -FileShare [VsanFileShare] (Required) Specifies the vSAN file share backing for a container volume.
- -StaticFileShare [SwitchParameter] (Required) Indicates that the StaticFileShareCnsVolume parameter is set.
- -StaticBlock [SwitchParameter] (Required) Indicates that the StaticBlockCnsVolume parameter is set.
- -DynamicBlock [SwitchParameter] (Required) Indicates that the DynamicBlockCnsVolume parameter is set.
- -DynamicFileShare [SwitchParameter] (Required) Indicates that the DynamicFileShareCnsVolume parameter is set.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.

**Examples:**

```powershell
New-CnsVolume -Name 'test-cns' -VDisk $vdisk -CnsVolumeMetadata $metadata -StaticBlock
```
_Creates a CNS volume with 'test-cns' as ?? volume name, $vdisk as ?? block backing for a container volume, and $metadata as a CNS volume metadata._

```powershell
New-CnsVolume -Name 'test-cns' -FileShare $fileshare -CnsVolumeMetadata $metadata -StaticFileShare
```
_Creates a CNS volume with 'test-cns' as a volume name, $fileshare as a file share backing for a container volume, and $metadata as a CNS volume metadata._

```powershell
New-CnsVolume -Name 'test-cns' -CnsVolumeMetadata $metadata -CapacityMB 1024 -Datastore $datastore -DynamicBlock
```
_Creates a CNS volume dynamically with 'test-cns' as a volume name, '1024' as a container volume capacity in MB, $datastore as a CNS volume placement, and $metadata as a CNS volume metadata._

### `New-CnsVolumeAttachment`

**New-CnsVolumeAttachment -CnsVolume <CnsVolume> -VM <VirtualMachine> [-Server <VIServer[]>] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>]**

**Parameters:**

- -CnsVolume [CnsVolume] (Required) 
- -RunAsync [switch] (Optional) 
- -Server [VIServer[]] (Optional) 
- -VM [VirtualMachine] (Required) 

### `New-CnsVolumeMetadata`

**This cmdlet creates a Cloud Native Storage (CNS) volume metadata at the client side.**

**Parameters:**

- -CnsEntityMetadata [CnsEntityMetadata[]] (Required) Specifies the CNS entity metadata associated with the CNS volume within a container orchestrator like Kubernetes.
- -ContainerCluster [CnsContainerCluster[]] (Required) Specifies the list of all container orchestrator clusters where you can use the CNS volume.

**Examples:**

```powershell
New-CnsVolumeMetadata -CnsEntityMetadata $cnsEntityMetadata -ContainerCluster $containerCluster
```
_Creates a CNS volume metadata with $cnsEntityMetadata as a CNS entity metadata and $containerCluster as a container cluster._

### `New-Datastore`

**This cmdlet creates a new datastore.**

This cmdlet creates a new datastore based on the provided parameters. The following characters cannot be used in a datastore name: slash (/), backslash (\), and percent (%).

**Parameters:**

- -BlockSizeMB [Int32] (Optional) Specifies the maximum file size of VMFS in megabytes (MB). If no value is given, the maximum file size for the current system platform is used.
- -FileSystemVersion [String] (Optional) Specifies the file system you want to use on the new datastore.
- -Kerberos [SwitchParameter] (Optional) By default, NFS datastores are created with AUTH_SYS as the authentication protocol. This parameter indicates that the NFS datastore uses Kerberos version 5 for authentication. This parameter is available only for NFS version 4.1 datastores.
- -Name [String] (Required) Specifies a name for the new datastore.
- -Nfs [SwitchParameter] (Optional) Indicates that you want to create an NFS datastore.
- -NfsHost [String[]] (Required) Specifies the NFS host where you want to create the new datastore.
- -Path [String] (Required) If you want to create an NFS datastore, specify the remote path of the NFS mount point. If you want to create a VMFS datastore, specify the canonical name of the SCSI logical unit that will contain new VMFS datastores.
- -ReadOnly [SwitchParameter] (Optional) Indicates that the access mode for the mount point is ReadOnly. The default access mode is ReadWrite.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Vmfs [SwitchParameter] (Optional) Indicates that you want to create a VMFS datastore.
- -VMHost [VMHost] (Required) Specifies a host where you want to create the new datastore. Passing multiple values to this parameter is obsolete.
- -VvolStorageContainer [StorageContainer] (Required) Specifies the backing virtual volume (vVol) storage container to create the datastore. You can retrieve the storage container objects by using the Get-VvolStorageContainer cmdlet.

**Examples:**

```powershell
New-Datastore -VMHost $vmhost -Name Datastore -Path $scsiLun.CanonicalName -Vmfs -FileSystemVersion 3
```
_Creates a VMFS datastore by specifying the file system type._

```powershell
New-Datastore -Nfs -VMHost 10.23.112.60 -Name NFSDatastore -Path /mynfs -NfsHost 10.23.84.73
```
_Creates a NFS datastore._

```powershell
$vmhost1, $vmhost2 | New-Datastore -Nfs -Name NFS1 -Path "/mnt/nfs1/nfs11/test1" -NfsHost 10.23.113.55 -ReadOnly
```
_Creates a read-only NFS datastore across multiple virtual machine hosts._

### `New-DatastoreCluster`

**This cmdlet creates a new datastore cluster.**

This cmdlet creates a new datastore cluster. By default, Storage DRS is deactivated. To enable Storage DRS, run Set-DatastoreCluster.

**Parameters:**

- -Location [VIContainer] (Required) Specifies a container object (Datacenter or Folder) where you want to place the new datastore cluster.
- -Name [String] (Required) Specifies a name for the datastore cluster that you want to create.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-DatastoreCluster -Name 'MyDatastoreCluster' -Location 'MyDatacenter'
```
_Creates a new datastore cluster on the specified datacenter._

### `New-DatastoreDrive`

**This function creates a new datastore drive.**

This function creates a new drive that is mapped to a location in a datastore.

**Parameters:**

- -Name [String] (Optional) Specifies a name for the new drive.
- -Datastore [Object] (Optional) Specifies the datastore for which you want to create a new drive.

### `New-RemoteVsanServerClusterConfig`

**Creates a local object of type RemoteVsanServerClusterConfig that you use to mount a remote vSAN datastore from a vSAN stretched cluster.**

Creates a local object of type RemoteVsanServerClusterConfig that you use to mount a remote vSAN datastore from a vSAN stretched cluster. You can use this cmdlet starting from vSAN 8.0 Update 1. You pass the created object by using the Set-VsanClusterConfiguration cmdlet.

**Parameters:**

- -Cluster [Cluster] (Required) The server cluster which the client cluster uses to mount the remote vSAN datastore.
- -NetworkTopology [VsanRemoteNetWorkTopologyType] (Required) The network topology between the client and the server cluster in an HCI Mesh configuration.
- -ServerSiteName [String] (Optional) Specifies the remote server site to be coupled with the client site. You must use a stretched cluster fault domain such as Preferred or Secondary. Do not use this parameter for the symmetric network topology.
- -ClientSiteName [String] (Optional) The client site to be used to set up inter-cluster site fault domain coupling to the server cluster. Do not use this parameter for a single-site client or if you pass a symmetric network topology.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$serverConfig = New-RemoteVsanServerClusterConfig -cluster $clusterServer -networktopology "Symmetric"
```
_Creates a local RemoteVsanServerClusterConfig with the Symmetric network topology type and the $clusterServer server cluster for the mounted remote vSAN datastore. Mounts the $datastore datastore from the $clusterServer cluster as a remote datastore on the $clusterClient cluster with the $serverconfig object._

```powershell
New-RemoteVsanServerClusterConfig -cluster $cluster -networktopology "Asymmetric" -ServerSideName "Secondary"
```
_Creates a local RemoteVsanServerClusterConfig object with the Asymmetric network topology type, Secondary as the remote server site to be coupled with the client site, and the $cluster cluster as the server cluster to be mounted to the remote vSAN datastore._

```powershell
New-RemoteVsanServerClusterConfig -cluster $cluster -networktopology "Asymmetric" -ServerSideName "Secondary" -ClientSideName "Preferred"
```
_Creates a local RemoteVsanServerClusterConfig object with the Asymmetric network topology type, Secondary as the server site to be coupled with the client site, Preferred as the remote server site to be coupled with the client site, and $cluster as the server cluster to be mounted to the remote vSAN datastore._

### `New-SpbmRule`

**This cmdlet creates an SPBM rule in the client side.**

**Parameters:**

- -AnyOfTags [Tag[]] (Required) Specifies tag objects for the new rule. All specified tags should be of the same tag category. You can find all available tags by running the Get-Tag cmdlet. You can use the Get-TagCategory and Get-Tag cmdlets to find a specific tag.
- -Capability [SpbmCapability] (Required) Specifies an SPBM capability object. You must select one of the available capability objects for the given namespace. OBN for this object uses full name of the object, including the namespace name. You can find all available Capability objects and their data types under a namespace by using the Get-SpbmCapability cmdlet.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Value [Object] (Required) Specifies a capability property value. A property value is a single value or a collection of values. A single property value is expressed as a scalar value (Object), while a collection of values is expressed as a range of values (VMware.VimAutomation.VICore.Types.V1.Range), or an array (Object[]) of values. The type of each value can be Long, Int, String, Boolean, Double, DateTime, or TimeSpan.
- -SpbmOperatorType [SpbmOperatorType] (Optional) Specifies the logical operator for the values. Currently only NOT is supported.

**Examples:**

```powershell
New-SpbmRule -Capability (Get-SpbmCapability -Name "VSAN.forceProvisioning") -Value $true
```
_Creates a new SPBM rule with capability named "VSAN.forceProvisioning" and Boolean value set to true._

```powershell
New-SpbmRule -Capability (Get-SpbmCapability -Name VSAN.stripeWidth) -Value 2
```
_Creates a new SPBM rule with capability named "VSAN.stripewidth" and integer value set to 2._

```powershell
New-SpbmRule -AnyOfTags (Get-Tag -Category "category1")
```
_Creates a new SPBM rule with all the tags from the "category1" category._

### `New-SpbmRuleSet`

**This cmdlet creates an SPBM rule set.**

This cmdlet creates an SPBM rule set. An SpbmRuleSet object consists of multiple SpbmRule objects. It contains both capability-based and tag-based rules. Each of the capability-based rules must be of the same namespace.

**Parameters:**

- -AllOfRules [SpbmRule[]] (Required) Specifies an array of SPBM rule objects for the new rule set.
- -Name [String] (Optional) Specifies a name for the new rule set.

**Examples:**

```powershell
New-SpbmRuleSet -AllOfRules (New-SpbmRule -AnyOfTags $tag1, $tag2)
```
_Creates an SPBM rule set with a rule of tag objects $tag1, $tag2._

```powershell
New-SpbmRuleSet -AllOfRules $rule1, $rule2, $rule3
```
_Creates an SPBM rule set with rule objects $rule1, $rule2, and $rule3._

### `New-SpbmStoragePolicy`

**This cmdlet creates a requirement storage policy in an SPBM server.**

This cmdlet creates a requirement storage policy in an SPBM server. A requirement policy contains requirements that are derived from tag-defined capabilities or from VMware VSAN capabilities. A policy is a collection of rule sets. A rule set references storage capabilities and defines requirements based on those capabilities. Rules from the VAIOFilter namespace are only accepted as value by the CommonRule parameter. These rules apply to all rule sets as common requirements.

**Parameters:**

- -AnyOfRuleSets [SpbmRuleSet[]] (Optional) Specifies an array of rule sets that define the storage requirements. An SPBM rule with the VAIOFilter namespace cannot be added in any of these rule sets.
- -CommonRule [SpbmRule[]] (Optional) Specifies the SPBM rules from the VAIOFilter namespace only. These rules are considered with all the SPBM rule sets as common requirements.
- -Description [String] (Optional) Specifies the text description associated with the policy.
- -Name [String] (Required) Specifies the name of the capability-based policy to be created. The maximum length of the name is 80 characters.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-SpbmStoragePolicy -Name "MyPolicy" -Description "MyPolicyDescription" -AnyOfRuleSets $ruleset1, $ruleset2, $ruleset3
```
_Creates a new storage policy named "MyPolicy", with description "MyPolicyDescription" and with rule set objects $ruleset1, $ruleset2 and $ruleset3._

```powershell
New-SpbmStoragePolicy -Name "MyPolicy" -AnyOfRuleSets (New-SpbmRuleSet -AllOfRules $rule1, $rule2, $rule3)
```
_Creates a new storage policy named "MyPolicy" with a rule set containing rule objects $rule1, $rule2, and $rule3._

```powershell
$c = Get-SpbmCapability -Name IOFILTERS*
```
_Creates a storage policy with one rule set and one VAIOFilter common rule._

### `New-VDisk`

**This cmdlet creates a managed VDisk object whose lifecycle is independent of a virtual machine`s lifecycle on the specified datastore.**

This cmdlet creates a managed VDisk object whose lifecycle is independent of a virtual machine`s lifecycle on the specified datastore. For RDM (RawVDisk), you must specify the device name of the SCSI LUN and the virtual machine host which is connected to the SCSI LUN.

**Parameters:**

- -CapacityGB [Decimal] (Required) Specifies the capacity of the newly created VDisk object in gigabytes (GB).
- -Datastore [Datastore] (Required) Specifies the datastore on which you want to store the metadata of the VDisk object. For flat disk, the contents of the disk are also stored on the specified datastore.
- -DiskType [DiskType] (Optional) Specifies the type of the newly created VDisk object.
- -HardDisk [HardDisk] (Required) Specifies the virtual hard disk object which you want to promote as a VDisk object.
- -Name [String] (Required) Specifies the name of the newly created VDisk object.
- -ScsiLun [ScsiLun] (Required) Specifies the backing SCSI LUN for the newly created VDisk object.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageFormat [VDiskStorageFormat] (Optional) Specifies the storage format of the newly created VDisk object.
- -VMHost [VMHost] (Optional) Specifies the virtual machine host which is connected to the SCSI LUN.

**Examples:**

```powershell
New-VDisk -Name 'MyDisk' -CapacityGB 1 -Datastore $ds -DiskType Flat -StorageFormat Thin
```
_Creates a new thin-provisioned flat VDisk object named 'MyDisk' on the $ds datastore with capacity of 1 GB._

```powershell
New-VDisk -Name 'MyDisk' -Datastore $ds -DiskType RawPhysical -ScsiLun $scsiLun
```
_Creates a new physical raw VDisk object named 'MyDisk' backed by the $scsiLun SCSI LUN and with metadata on the $ds datastore._

```powershell
New-VDisk -HardDisk $hd -Name $newName
```
_Promotes the $hd virtual hard disk to a VDisk object._

### `New-VsanDirectDisk`

**This cmdlet creates a vSAN Direct disk from a specified hard disk.**

This cmdlet creates a vSAN Direct disk from a specified hard disk that is not a part of any existing vSAN disk group. You can use vSAN Direct disk for direct access from cloud-native applications that require stateful storage. This cmdlet is not supported in a vSAN ESA enabled cluster. You can use this cmdlet starting from vSAN 7.0 Update 1.

**Parameters:**

- -DiskCanonicalName [String] (Required) Specifies the canonical name of a hard disk from which to create a vSAN direct disk.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the vSphere PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost] (Required) Specifies the VMHost from which to create vSAN Direct disks.

**Examples:**

```powershell
New-VsanDirectDisk -diskcanonicalname "mpx.vmhba0:C0:T1:L0" -vmhost "10.161.138.179"
```
_Creates a new vSAN Direct disk with the specified canonical name on the specified host._

### `New-VsanDisk`

**This cmdlet adds a host SCSI disk to a vSAN disk group.**

**Parameters:**

- -CanonicalName [String] (Required) Specifies the canonical name of the host SCSI disk that is added to the group.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -VsanDiskGroup [VsanDiskGroup] (Required) Specifies the disk group that the disk is added to.

**Examples:**

```powershell
New-VsanDisk -CanonicalName "DiskCanonicalName" -VsanDiskGroup $vsanDiskGroup
```
_Creates a new vSAN disk and adds the disk to the $vsanDiskGroup vSAN disk group._

### `New-VsanDiskGroup`

**This cmdlet creates a new vSAN disk group backed by the specified devices.**

This cmdlet creates a new vSAN disk group backed by the specified solid-state device and hard disk devices.

**Parameters:**

- -DataDiskCanonicalName [String[]] (Required) Specifies the canonical name of hard disks that should be included in this disk group and used for data.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SsdCanonicalName [String] (Required) Specifies the canonical name of a solid-state device that would be used by this disk group.
- -VMHost [VMHost] (Required) Specifies the hosts that the created groups are on.

**Examples:**

```powershell
New-VsanDiskGroup -VMHost $vmHost -SsdCanonicalName "MySsdCanonicalName" -DataDiskCanonicalName DataDisk1,DataDisk2
```
_Creates a new vSAN disk group at the $vmHost virtual machine host with a solid-state drive named "MySsdCanonicalName" and hard disks named DataDisk1 and DataDisk2._

### `New-VsanFaultDomain`

**This cmdlet creates a new vSAN fault domain in a cluster with specified virtual machine hosts.**

**Parameters:**

- -Name [String] (Required) Specifies the name of the new vSAN fault domain. The name should be unique within a cluster. The length of fault domain name should not exceed 256 characters.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Required) Specifies the list of virtual machine hosts to become part of the fault domain. These hosts should be in same cluster.

**Examples:**

```powershell
New-VsanFaultDomain -VMHost $vmHost1, $vmHost2 -Name "MyFaultDomainName"
```
_Creates a new vSAN fault domain named "MyFaultDomainName", which has virtual machine hosts $vmHost1 and $vmHost2._

### `New-VsanFileServerIpConfig`

**This cmdlet creates a vSAN file service IP configuration at the client side.**

**Parameters:**

- -Gateway [String] (Required) Specifies the default gateway IP address for the file service access point. The gateway IP must be the same for all the file  servers in this domain.
- -IpAddress [String] (Required) Specifies the IP address for the file service access point.
- -SubnetMask [String] (Required) Specifies the subnet mask for the IP address for the file service access point.
- -Fqdn [String] (Required) Specifies the FQDN that you want to use with the IP addresses for the vSAN file service instance. You have to map the IP address and FQDN before the vSAN file service configuration. You might have to update the DNS records. You can use the first component of FQDN as netBIOS name for the file service instances. It must not exceed 15 characters in length.
- -IsPrimary [SwitchParameter] (Optional) Specifies whether the IP address is served as the primary IP address for the file  service. The file server running with the primary IP serves as the NFS referral  server which might point to the file shares served by other file servers in this cluster.  Only one primary IP address is supported in one domain.

**Examples:**

```powershell
New-VsanFileServerIpConfig -Gateway "192.128.3.253" -SubnetMask "255.255.255.0" -IpAddress "192.128.3.11" -Fqdn "h1.vmware.com" -IsPrimary
```
_Creates a primary new vSAN file server IP configuration with "192.128.3.253" as a gateway,  "192.128.3.11" as an IP address, "h1.vmware.com" as FQDN, and "255.255.255.0" as a subnet mask._

### `New-VsanFileServiceDomain`

**This cmdlet creates a file service domain in a vSAN cluster.**

This cmdlet creates a file service domain in the vSAN cluster.

**Parameters:**

- -Name [String] (Required) Specifies the name of the new vSAN file service domain. The name should be unique within  a cluster. The length of the file service domain name should not exceed 256 characters.
- -Cluster [Cluster] (Required) Specifies the vSAN cluster where you want to create the new file service domain.
- -VsanFileServerIpConfig [VsanFileServerIpConfig[]] (Required) Specifies a pool of IP addresses that will be used by vSAN file service to provide file access from  multiple file servers. A minimum of one such address is needed. Considering the workload, it  is recommended to have equal or greater number of IP addresses than the number of hosts  in the cluster.
- -DnsServerAddress [String[]] (Required) Specifies the DNS server address which you want to use to resolve the hostnames within the DNS domain.nThis parameter is optional if the DNS name is provided in the access point configuration or is not required for an NFS access.
- -DnsSuffix [String[]] (Required) Specifies the list of DNS server addresses that can be resolved by the DNS servers. The DNS suffix is required if the DNS servers are provided.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the file service servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
New-VsanFileServiceDomain -Name "myDomain" -Cluster $cluster
```
_Creates a new vSAN file service domain named "myDomain" in the $cluster vSAN cluster with  "10.172.199.240" as its DNS server address and "vmware.com" as its DNS suffix.  The domains's IP pool are $ipconfig1 and $ipconfig2._

### `New-VsanFileShare`

**This cmdlet creates a new vSAN file share in a specified file service domain.**

**Parameters:**

- -FileServiceDomain [VsanFileServiceDomain] (Required) Specifies the vSAN file service domain to which the vSAN file share belongs.
- -FileShareNetworkPermission [VsanFileShareNetworkPermission[]] (Optional) Specifies the new file share network permission settings of the vSAN file share.
- -HardQuotaGB [Decimal] (Optional) Specifies the new hard quota in GB of the vSAN file share.
- -Label [Hashtable] (Optional) Specifies the new labels of the vSAN file share.
- -Name [String] (Required) Specifies the new name of the vSAN file share.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SoftQuotaGB [Decimal] (Optional) Specifies the new soft quota in GB of the vSAN file share.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the new storage policy of the vSAN file share.

**Examples:**

```powershell
New-VsanFileShare -FileServiceDomain $fileServieDomain -Name "FileShare1" -FileShareNetworkPermission $permission
```
_Creates a new vSAN file share named "FileShare1" in the $fileServieDomain file service domain with a $permission network permision._

### `New-VsanFileShareNetworkPermission`

**New-VsanFileShareNetworkPermission -IPSetOrSubnet <string> -VsanFileShareAccessPermission <VsanFileShareAccessType> [-AllowSquashRoot] [-WhatIf] [-Confirm] [<CommonParameters>]**

**Parameters:**

- -AllowSquashRoot [switch] (Optional) 
- -IPSetOrSubnet [string] (Required) 
- -VsanFileShareAccessPermission [VsanFileShareAccessType] (Required) 

### `New-VsanFileShareSnapshot`

**This cmdlet creates a vSAN file share snapshot for the specified vSAN file share.**

**Parameters:**

- -FileShare [VsanFileShare] (Required) Specifies the vSAN file share for which to create the vSAN file share snapshot.
- -Name [String] (Required) Specifies the name of the vSAN file share snapshot.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
New-VsanFileShareSnapshot -Name "FileShareSnapshot1" -FileShare $fileShare
```
_Creates a vSAN file share snapshot named "FileShareSnapshot1" for the $fileShare file share._

### `New-VsanHCIMeshDatastoreSource`

**This cmdlet creates a new vSAN HCI Mesh datastore source for the local vCenter Server from a remote vCenter Server.**

Creates a new vSAN HCI Mesh datastore source for the local vCenter Server from a remote vCenter Server. You can use this cmdlet starting from vSAN 8.0 Update 1.

**Parameters:**

- -VCHost [String] (Required) Specifies the IP address or FQDN of the remote vCenter Server.
- -User [String] (Required) Specifies the user name to log in to the remote vCenter.
- -Password [String] (Required) Specifies the password to log in to the remote vCenter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the vSphere PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-VsanHCIMeshDatastoreSource -User 'administrator@vsphere.local' -VCHost '10.186.46.61' -Password 'IDRJ*tvu:k5g8MjO'
```
_Creates a new vSAN HCI Mesh datastore source for the local vCenter Server from the specified remote vCenter Server._

### `New-VsanHealthCheckThreshold`

**This cmdlet creates a vSAN health check threshold object locally. This cmdlet is used to set a capacity threshold in Set-VsanClusterConfiguration.**

**Parameters:**

- -Enabled [Boolean] (Required) Specifies whether the health check threshold is enabled.
- -YellowValue [Int64] (Required) Specifies the yellow line value, which is a percentage ranging from 0 to 100.
- -RedValue [Int64] (Required) Specifies the red line value, which is a percentage ranging from 0 to 100.
- -Target [VsanHealthCheckThresholdTarget] (Required) Specifies the target, on which you want to set a health check threshold. The possible values are VsanDatastore and VsanDirectDatastore.

**Examples:**

```powershell
New-VsanHealthCheckThreshold -Enabled 1 -YellowValue 95 -RedValue 99 -Target VsanDatastore
```
_Creates a vSAN health check threshold object locally with 95 yellow value, 99 red value, and VsanDatastore as the target._

```powershell
New-VsanHealthCheckThreshold -Enabled 1 -YellowValue 90 -RedValue 99 -Target VsanDirectDatastore
```
_Creates a vSAN health check threshold object locally with 90 yellow value, 99 red value, and VsanDirectDatastore as the target._

### `New-VsanIscsiInitiatorGroup`

**This cmdlet adds a new vSAN iSCSI initiator group to a cluster.**

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the clusters to which you want to add the vSAN iSCSI initiator group.
- -Name [String] (Required) Specifies the name of the new vSAN iSCSI initiator group. The name should be unique within a cluster.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
New-VsanIscsiInitiatorGroup -Name "Group1" -Cluster "vsan-cluster"
```
_Creates a new vSAN iSCSI initiator group named "Group1" in the "vsan-cluster" cluster._

### `New-VsanIscsiInitiatorGroupTargetAssociation`

**This cmdlet associates the specified vSAN iSCSI initiator group with specified vSAN iSCSI target to provide access to the target.**

**Parameters:**

- -InitiatorGroup [VsanIscsiInitiatorGroup] (Required) Specifies the vSAN iSCSI initiator group associated with the vSAN iSCSI target to which you have provided access.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Target [VsanIscsiTarget] (Required) Specifies the vSAN iSCSI target to which you want to provide access.

**Examples:**

```powershell
New-VsanIscsiInitiatorGroupTargetAssociation -InitiatorGroup $initiatorGroup -Target $target
```
_Associates the $initiatorGroup initiator group with the $target iSCSI target._

### `New-VsanIscsiLun`

**This cmdlet adds a new vSAN iSCSI LUN to a target.**

**Parameters:**

- -CapacityGB [Decimal] (Required) Specifies the capacity of the newly created vSAN iSCSI LUN in gigabytes (GB).
- -LunId [Int32] (Optional) Specifies the ID of the LUN. The value must be in the range from 0 to 255. If specified, the ID should be unique within a target.
- -Name [String] (Optional) Specifies the name of the newly created vSAN iSCSI LUN. The name can indicate additional information about the LUN.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy associated with the newly created vSAN iSCSI LUN. If not specified, the default storage policy defined in the iSCSI service is used.
- -Target [VsanIscsiTarget] (Required) Specifies the vSAN iSCSI target to which you want to add the LUN.

**Examples:**

```powershell
New-VsanIscsiLun -Name "FirstLun" -Target $target -LunId 3 -CapacityGB 2
```
_Creates a new vSAN iSCSI LUN of capacity 2 GB named "FirstLun" in the $target iSCSI target and sets the value of LunId to 3._

### `New-VsanIscsiTarget`

**This cmdlet adds a new vSAN iSCSI target to a cluster.**

**Parameters:**

- -AuthenticationType [VsanIscsiTargetAuthenticationType] (Optional) Specifies the authentication type for the vSAN iSCSI target.
- -Cluster [Cluster] (Required) Specifies the vSAN cluster on which you want to create the vSAN iSCSI target.
- -IncomingChapSecret [SecureString] (Optional) Specifies the CHAP user secret for the target. Applicable when the authentication type is Chap or MutualChap.
- -IncomingChapUser [String] (Optional) Specifies the CHAP user name for the target. Applicable when the authentication type is Chap or MutualChap.
- -IscsiQualifiedName [String] (Optional) Specifies the IQN of the target. This parameter is optional and should be unique if specified. If not specified, the server generates a unique IQN.
- -Name [String] (Required) Specifies the name of the newly created vSAN iSCSI target. The name should be unique within a cluster.
- -NetworkInterface [String] (Optional) Specifies the VMkernel network interface which handles the iSCSI traffic. If not specified, the default VMkernel network interface defined in iSCSI target service is used. This parameter accepts an object of type HostVMKernelVirtualNic by silently converting it to the string name by using ArgumentTransformationAttribute.
- -OutgoingChapSecret [SecureString] (Optional) Specifies the CHAP user secret you want to attach to the initiator. Applicable when the authentication type is MutualChap.
- -OutgoingChapUser [String] (Optional) Specifies the CHAP user name you want to attach to the initiator. Applicable when the authentication type is MutualChap.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy applied to the vSAN namespace of the iSCSI target. If not specified, the default storage policy defined in iSCSI service is used.
- -TcpPort [Int32] (Optional) Specifies the network port on which the target is accessible. If specified, NetworkInterface should also be specified. If not specified, and if NetworkInterface is also not specified, the default port specified in iSCSI target service is used. If NetworkInterface is specified, the default port 3260 is used. The server automatically opens the firewall for the specified port.

**Examples:**

```powershell
New-VsanIscsiTarget -Name "Target1" -Cluster "vsan-cluster" -NetworkInterface "vmk0"
```
_Creates a new vSAN iSCSI target named "Target1" in the "vsan-cluster" cluster which uses a VMkernel network interface named "vmk0" for traffic._

## Remove

### `Remove-CnsVolume`

**This cmdlet removes the specified Cloud Native Storage (CNS) volumes.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -CnsVolume [CnsVolume[]] (Required) Specifies the CNS volumes you want to remove.

**Examples:**

```powershell
Remove-CnsVolume -CnsVolume $CnsVolume -Confirm:$false
```
_Removes the $CnsVolume CNS volume without asking for confirmation._

### `Remove-CnsVolumeAttachment`

**Remove-CnsVolumeAttachment -CnsVolume <CnsVolume> -VM <VirtualMachine> [-Server <VIServer[]>] [-RunAsync] [-WhatIf] [-Confirm] [<CommonParameters>]**

**Parameters:**

- -CnsVolume [CnsVolume] (Required) 
- -RunAsync [switch] (Optional) 
- -Server [VIServer[]] (Optional) 
- -VM [VirtualMachine] (Required) 

### `Remove-Datastore`

**This cmdlet removes the specified datastores from their locations.**

This cmdlet removes the specified datastores from their locations. The cmdlet permanently deletes the content of the removed datastores, unless they are shared (NFS).

**Parameters:**

- -Datastore [Datastore[]] (Required) Specifies the datastores you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost] (Required) Specifies the host to which the datastore you want to remove belongs.

**Examples:**

```powershell
Remove-Datastore -Datastore Datastore -VMHost 10.23.112.234 -Confirm:$false
```
_Removes the Datastore datastore from the host._

### `Remove-DatastoreCluster`

**This cmdlet deletes the specified datastore clusters.**

**Parameters:**

- -DatastoreCluster [DatastoreCluster[]] (Required) Specifies the datastore cluster that you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-DatastoreCluster -Name 'MyDatastoreCluster' | Remove-DatastoreCluster -Confirm $false
```
_Removes the specified datastore cluster without asking for confirmation._

### `Remove-SpbmStoragePolicy`

**This cmdlet deletes storage policies.**

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy[]] (Required) Specifies the storage policies to be deleted.

**Examples:**

```powershell
Remove-SpbmStoragePolicy -StoragePolicy $policy1, $policy2
```
_Deletes all storage policies represented by the $policy1 and $policy2 objects._

```powershell
Remove-SpbmStoragePolicy -StoragePolicy policytest*
```
_Deletes all storage policies whose name starts with "policytest"._

### `Remove-VDisk`

**This cmdlet removes VDisk objects and the associated backings from the datastore.**

This cmdlet removes VDisk objects and the associated backings from the datastore. Removal of VDisk objects which are attached to a virtual machine is not allowed.

**Parameters:**

- -VDisk [VDisk[]] (Required) Specifies the VDisk objects you want to remove.

**Examples:**

```powershell
Remove-VDisk -VDisk $vDisk
```
_Removes the $vDisk VDisk object from the server and datastore._

### `Remove-VsanDirectDisk`

**This cmdlet removes vSAN Direct disks from a vSAN cluster.**

This cmdlet removes vSAN Direct disks from a vSAN cluster. This cmdlet is not supported in a vSAN ESA enabled cluster. You can use this cmdlet starting from vSAN 7.0 Update 1.

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the cluster from which to remove vSAN Direct disks.
- -Purpose [String] (Optional) Specifies the purpose for removing the disk.
- -VsanDataMigrationMode [VsanDataMigrationMode] (Optional) Specifies the decommissioning mode of removing the vSAN Direct disks. Full = 0, EnsureAccessibility = 1, NoDataMigration = 2
- -VsanDirectDisk [VsanDirectDisk[]] (Required) Specifies the vSAN Direct disks to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the vSphere PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-VsanDirectDisk -cluster "VSAN-Cluster" -Vsandirectdisk $disk[0]
```
_Removes the specified vSAN Direct disks from the specified cluster._

### `Remove-VsanDisk`

**This cmdlet removes the specified hard disks from the specified vSAN disk group.**

**Parameters:**

- -DataMigrationMode [VsanDataMigrationMode] (Optional) Specifies the action pertaining to vSAN data when the disk is removed. If not specified, the default value is Full.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -VsanDisk [VsanDisk[]] (Required) Specifies the hard disks you want to remove.

**Examples:**

```powershell
Remove-VsanDisk -VsanDisk $vsanDisk -Confirm:$false
```
_Removes the $vsanDisk vSAN disk without asking for confirmation._

### `Remove-VsanDiskGroup`

**This cmdlet removes vSAN disk groups.**

**Parameters:**

- -DataMigrationMode [VsanDataMigrationMode] (Optional) Specifies the action pertaining to vSAN data when the disk group is removed. If not specified, the default value is Full.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -VsanDiskGroup [VsanDiskGroup[]] (Required) Specifies the vSAN disk groups you want to remove.

**Examples:**

```powershell
Remove-VsanDiskGroup -VsanDiskGroup $vsanDiskGroup -Confirm:$false
```
_Removes the $vsanDiskGroup vSAN disk group without asking for confirmation._

### `Remove-VsanFaultDomain`

**This cmdlet removes vSAN fault domains.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VsanFaultDomain [VsanFaultDomain[]] (Required) Specifies the list of VSAN fault domains you want to remove.

**Examples:**

```powershell
Remove-VsanFaultDomain -VsanFaultDomain $vsanFaultDomain -Confirm:$false
```
_Removes the $vsanFaultDomain vSAN fault domain without asking for confirmation._

### `Remove-VsanFileServiceDomain`

**This cmdlet removes the specified vSAN file service domain from the vSAN clusters.**

**Parameters:**

- -VsanFileServiceDomain [VsanFileServiceDomain[]] (Required) Specifies the list of vSAN file service domains you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet. .

**Examples:**

```powershell
Remove-VsanFileServiceDomain -VsanFileServiceDomain $domain serviceDomain -Confirm:$false
```
_Removes the vSAN file service domain without asking for confirmation._

### `Remove-VsanFileShare`

**This cmdlet removes vSAN file shares.**

**Parameters:**

- -FileShare [VsanFileShare[]] (Required) Specifies the list of VSAN file shares you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Force [SwitchParameter] (Optional) Indicates that you want to remove the vSAN file share (for example, the file share whose ManagingEntity is the Cloud Native Storage (CNS) service).

**Examples:**

```powershell
Remove-VsanFileShare -FileShare $vsanFileShare -Confirm:$false
```
_Removes the $vsanFileShare vSAN file share without asking for confirmation._

### `Remove-VsanFileShareSnapshot`

**This cmdlet removes vSAN file share snapshots.**

**Parameters:**

- -FileShareSnapshot [VsanFileShareSnapshot[]] (Required) Specifies the list of VSAN file share snapshots you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Remove-VsanFileShareSnapshot -FileShareSnapshot $vsanFileShareSnapshot -Confirm:$false
```
_Removes the $vsanFileShareSnapshot vSAN file share snapshot without asking for confirmation._

### `Remove-VsanHCIMeshDatastoreSource`

**This cmdlet removes a vSAN HCI Mesh datastore source with the specified information.**

This cmdlet removes a vSAN HCI Mesh datastore source with the specified information. You can use this cmdlet starting from vSAN 8.0 Update 1.

**Parameters:**

- -User [String] (Required) Specifies the user name to log in to the remote vCenter.
- -VsanHCIMeshDatastoreSource [VsanHCIMeshDatastoreSource] (Optional) Specifies the VsanHCIMeshDatastoreSource to remove.
- -Password [String] (Required) Specifies the password to log in to the remote vCenter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the vSphere PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
$ds = Get-VsanHCIMeshDatastoreSource -VCHost ('10.186.46.61')
```
_Removes the specified vSAN HCI Mesh datastore source from the specified vCenter Server._

### `Remove-VsanIscsiInitiatorGroup`

**This cmdlet removes the specified vSAN iSCSI initiator groups from their clusters.**

**Parameters:**

- -InitiatorGroup [VsanIscsiInitiatorGroup[]] (Required) Specifies the vSAN iSCSI initiator groups you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-VsanIscsiInitiatorGroup -InitiatorGroup $initiatorGroup -Confirm:$false
```
_Removes the $initiatorGroup iSCSI initiator group without asking for confirmation._

### `Remove-VsanIscsiInitiatorGroupTargetAssociation`

**This cmdlet removes the specified association of vSAN iSCSI initiator group and target.**

**Parameters:**

- -InitiatorGroupTargetAssociation [VsanIscsiInitiatorGroupTargetAssociation[]] (Required) Specifies the vSAN iSCSI initiator group and target associations you want to remove.

**Examples:**

```powershell
Remove-VsanIscsiInitiatorGroupTargetAssociation -InitiatorGroupTargetAssociation $association -Confirm:$false
```
_Removes the iSCSI initiator group to the $association target association without asking for confirmation._

### `Remove-VsanIscsiLun`

**This cmdlet removes vSAN iSCSI LUNs from their iSCSI targets.**

**Parameters:**

- -Lun [VsanIscsiLun[]] (Required) Specifies the vSAN iSCSI LUNs you want to remove.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-VsanIscsiLun -Lun $lun -Confirm:$false
```
_Removes the $lun iSCSI LUN without asking for confirmation._

### `Remove-VsanIscsiTarget`

**This cmdlet removes vSAN iSCSI targets form their clusters.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Target [VsanIscsiTarget[]] (Required) Specifies the vSAN iSCSI targets you want to remove.

**Examples:**

```powershell
Remove-VsanIscsiTarget -Target $target -Confirm:$false
```
_Removes the $target iSCSI target without asking for confirmation._

### `Remove-VsanStoragePoolDisk`

**This cmdlet removes a single or multiple storage pool disks on a vSAN cluster.**

**Parameters:**

- -Purpose [String] (Optional) Specifies the purpose for removing the disk.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the vSphere PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VsanDataMigrationMode [VsanDataMigrationMode] (Optional) Specifies the decommissioning mode of removing the storage pool disks. Full = 0, EnsureAccessibility = 1, NoDataMigration = 2
- -VsanStoragePoolDisk [VsanStoragePoolDisk[]] (Required) Specifies the vSAN storage pool disks to remove.

**Examples:**

```powershell
$disks =get-vsanstoragepooldisk -VMHost (Get-VMHost 10.192.201.50)
```
_Removes vSAN storage pool disks from the specified host without confirmation._

## Set

### `Set-CnsVolume`

**This cmdlet modifies the Cloud Native Storage (CNS) volume metadata of a specified CNS volume.**

**Parameters:**

- -CnsVolume [CnsVolume[]] (Required) Specifies the CNS volumes you want to update.
- -CnsVolumeMetadata [CnsVolumeMetadata] (Required) Specifies the metadata for the CNS volume.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Set-CnsVolume -CnsVolume $cnsVolume -CnsVolumeMetadata $cnsVolumeMetadata
```
_Updates the $cnsVolumeMetadata CNS volume metadata to the $cnsVolume CNS volume._

### `Set-Datastore`

**This cmdlet modifies the properties of the specified datastore.**

This cmdlet modifies the properties of the specified datastore. You can use the following characters in a path, but not in a datastore name: slash (/), backslash (\), and percent (%).

**Parameters:**

- -CongestionThresholdMillisecond [Int32] (Optional) Specifies the latency period beyond which the storage array is considered congested. The range of this value is between 10 to 100 milliseconds.
- -Datastore [Datastore[]] (Required) Specifies the datastore whose properties you want to change.
- -EvacuateAutomatically [SwitchParameter] (Optional) Specifies whether you want to automatically migrate all virtual machines to another datastore if the value of MaintenanceMode is $true. When the Storage DRS automation level is  set to Fully Automated, you do not need to specify the EvacuateAutomatically parameter because Storage DRS will migrate all virtual machines automatically.
- -MaintenanceMode [Boolean] (Required) Specifies whether you want to put the datastore in maintenance mode. The operation completes when no virtual machines are present and no provisioning processes are running on the datastore.
- -Name [String] (Optional) Specifies a new name for the datastore. Do not use slash (/), backslash (\), and percent (%) characters in datastore names.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageIOControlEnabled [Boolean] (Optional) Indicates whether you want to enable the IO control.

**Examples:**

```powershell
Get-Datastore -Name Datastore1 | Set-Datastore -Name Datastore2
```
_Renames the Datastore1 datastore to Datastore2._

```powershell
Set-Datastore $datastore1, $datastore2 -StorageIOControlEnabled $true -CongestionThresholdMillisecond 80
```
_Enables the Storage IO Control and set a congestion threshold of 80 milliseconds for the specified datastores._

```powershell
Get-Datastore -Name 'MyDatastore1' | Set-Datastore -MaintenanceMode $true -EvacuateAutomatically
```
_Puts the MyDatastore1 datastore in maintenance mode and specifies that all virtual machines on the datastore will be automatically migrated to another datastore._

### `Set-DatastoreCluster`

**This cmdlet modifies the configuration of the specified datastore cluster.**

**Parameters:**

- -DatastoreCluster [DatastoreCluster[]] (Required) Specifies the datastore cluster that you want to configure.
- -IOLatencyThresholdMillisecond [Int32] (Optional) Specifies the maximum I/O latency in milliseconds allowed before Storage DRS is triggered for the datastore cluster. The parameter accepts values in the range of 5 to 100. If the value of IOLoadBalancing is $false, the setting for the I/O latency threshold is not applied.
- -IOLoadBalanceEnabled [Boolean] (Optional) Specifies whether I/O load balancing is enabled for the datastore cluster. If the value is $false, I/O load balancing is deactivated and the settings for the I/O latency threshold and utilized space threshold are not applied.
- -Name [String] (Optional) Specifies a new name for the datastore cluster.
- -SdrsAutomationLevel [DrsAutomationLevel] (Optional) Specifies the Storage DRS automation level for the datastore cluster. This parameter accepts Disabled, Manual, and FullyAutomated values.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -SpaceUtilizationThresholdPercent [Int32] (Optional) Specifies the maximum percentage of consumed space allowed before Storage DRS is triggered for the datastore cluster. The parameter accepts values in the range of 50 to 100. If the value of IOLoadBalancing is $false, the setting for the utilized space threshold is not applied.

**Examples:**

```powershell
Set-DatastoreCluster -DatastoreCluster MyDatastoreCluster1 -Name 'MyDatastoreCluster2'
```
_Changes the name of the specified datastore cluster._

```powershell
Set-DatastoreCluster -DatastoreCluster MyDatastoreCluster -IOLatencyThresholdMillisecond 5
```
_Sets the maximum I/O latency in milliseconds allowed before Storage DRS is triggered for the specified datastore cluster to 5 milliseconds._

```powershell
Set-DatastoreCluster -DatastoreCluster MyDatastoreCluster -SdrsAutomationLevel FullyAutomated
```
_Changes the Storage DRS automation level of the specified datastore cluster to Fully Automated._

### `Set-SpbmEntityConfiguration`

**This cmdlet sets SPBM-related configuration data for VirtualMachine, HardDisk, and Datastore objects.**

This cmdlet sets SPBM-related configuration data for VirtualMachine, HardDisk, and Datastore objects. The configuration data includes storage policy association for VirtualMachine and HardDisk objects and SPBM enablement for Datastore objects.

**Parameters:**

- -AutoReplicationGroup [SwitchParameter] (Optional) Specify this if you do not want to explicitly provide a replication group and instead you want to place the entity in the default replication group decided by the VASA provider. If ReplicationGroup and AutoReplicationGroup are both specified, an error is thrown. If none of them are specified, the entity is not placed in any replication group.
- -Configuration [SpbmEntityConfiguration[]] (Required) Specifies the configuration to modify. The supported types are SpbmDatastoreConfiguration, SpbmVMConfiguration, and SpbmHardDiskConfiguration. This parameter supports OBN based on the names of the associated Datastore and VirtualMachine objects. This parameter also directly accepts objects of type Datastore, VirtualMachine, and HardDisk by silently converting them to the corresponding configuration object through an ArgumentTransformationAttribute object.
- -ReplicationGroup [SpbmReplicationGroup] (Optional) Specifies the replication group in which you want to put the VirtualMachine and HardDisk objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy that you want to apply to all Datastore, VirtualMachine, and HardDisk objects defined in the Configuration objects. If the value is $null, removes the current policy association for the VirtualMachine and HardDisk objects.

**Examples:**

```powershell
Set-SpbmEntityConfiguration -Configuration (Get-SpbmEntityConfiguration $datastore1) -StoragePolicy $policy
```
_Assigns the $policy storage policy as default storage policy to the $datastore1 datastore._

```powershell
Set-SpbmEntityConfiguration -Configuration $datastore1 -StoragePolicy $policy
```
_Assigns the $policy storage policy as default storage policy to the $datastore1 datastore._

```powershell
Set-SpbmEntityConfiguration -Configuration (Get-SpbmEntityConfiguration $vm1, $vm2) -StoragePolicy $policy
```
_Associates the $policy storage policy to the $vm1 and $vm2 virtual machines._

### `Set-SpbmStoragePolicy`

**This cmdlet overrides the current name, description, and rule sets of an existing storage policy in an SPBM server.**

**Parameters:**

- -AnyOfRuleSets [SpbmRuleSet[]] (Optional) Specifies an array to overwrite the current rule sets in the policy. The SPBM rule sets should not contain SPBM rules from the VAIOFilter namespace.
- -CommonRule [SpbmRule[]] (Optional) Specifies the SPBM rules from the VAIOFilter namespace only. These rules are considered with all the SPBM rule sets as common requirements.
- -Description [String] (Optional) Specifies a new description for the storage policy.
- -Name [String] (Optional) Specifies a new name for the storage policy. The maximum length of the name is 80 characters.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy[]] (Required) Specifies the storage policy to modify.

**Examples:**

```powershell
Set-SpbmStoragePolicy -StoragePolicy $policy -Name "NewName" -Description NewDescription
```
_Modifies the name and description of the $policy policy object._

```powershell
Set-SpbmStoragePolicy -StoragePolicy $policy -AnyOfRuleSets $ruleset1, $ruleset2
```
_Updates the $policy policy object with the $ruleset1 and $ruleset2 rule set objects which overwrite the existing rule sets in the policy._

```powershell
$p2 = Set-SpbmStoragePolicy -StoragePolicy $p1 -CommonRule $cr
```
_Modifies a storage policy to add a VAIOFilter rule._

### `Set-VDisk`

**This cmdlet renames, inflates, or extends the size of the specified VDisk object.**

This cmdlet renames, inflates, or extends the size of the specified VDisk object. If multiple options are specified, they are performed in the following order. 1. Rename 2. Inflate 3. Extend the size

**Parameters:**

- -CapacityGB [Decimal] (Optional) Specifies the new capacity of the VDisk object in gigabytes (GB).
- -Inflate [SwitchParameter] (Optional) Indicates to inflate the specified VDisk object. Inflating is supported only on thin-provisioned VDisk objects.
- -Name [String] (Optional) Specifies the new name you want to set for the VDisk object.
- -VDisk [VDisk[]] (Required) Specifies the VDisk objects you want to modify.

**Examples:**

```powershell
Set-VDisk -VDisk $vDisk -Name 'NewName' -CapacityGB 2
```
_Renames $vDisk VDisk object to 'NewName' and sets its capacity to 2 GB._

```powershell
Set-VDisk -VDisk $vDisk -Inflate
```
_Inflates the $vDisk VDisk object._

### `Set-VsanClusterConfiguration`

**This cmdlet modifies vSAN configuration settings for a cluster.**

**Parameters:**

- -AddSilentHealthCheck [String[]] (Optional) Specifies the health checks list you want to add to the silent list.
- -AllowReducedRedundancy [Boolean] (Optional) Allows a reduced redundancy state. This optional parameter is applicable to specific vSAN cluster reconfigure operations that need to migrate data across cluster for changing the vSAN disk format. When specified, it might make the process move lesser data in order to ensure storage object accessibility, and some objects are kept at reduced redundancy state, which means at a higher risk in case of a hardware failure during the migration process. This is applicable to the SpaceEfficiencyEnabled parameter only. The default value is False.
- -Configuration [VsanClusterConfiguration[]] (Required) Specifies the configurations that you want to modify. This parameter supports OBN based on the names of the associated cluster. This parameter also directly accepts objects of type Cluster by silently converting them to the configuration object through ArgumentTransformationAttribute.
- -CapacityThreshold [VsanHealthCheckThreshold[]] (Optional) Specifies the list of capacity thresholds for different kinds of datastores.
- -DefaultIncomingChapSecret [SecureString] (Optional) Specifies the default CHAP secret for iSCSI targets on this cluster. Applicable when the authentication type is Chap or MutualChap.
- -DefaultIncomingChapUser [String] (Optional) Specifies the default CHAP user name for the iSCSI targets on this cluster. Applicable when the authentication type is Chap or MutualChap.
- -DefaultIscsiNetworkInterface [String] (Optional) Specifies the default VMkernel network interface which handles the iSCSI traffic. This can be overridden per target. It's mandatory if IscsiTargetServiceEnabled is specified as $true. This parameter accepts an object of type HostVMKernelVirtualNic by silently converting it to the string name by using ArgumentTransformationAttribute.
- -DefaultIscsiTargetAuthenticationType [VsanIscsiTargetAuthenticationType] (Optional) Specifies the default authentication type for the vSAN iSCSI targets in this cluster.
- -DefaultIscsiTcpPort [Int32] (Optional) Specifies the default network port for the iSCSI targets. This can be overridden per target. If not provided, the default port 3260 is used. The server automatically opens the firewall for the specified port.
- -DefaultOutgoingChapSecret [SecureString] (Optional) Specifies the default CHAP user secret you want to attach to the initiator. This is applicable when the authentication type is MutualChap.
- -DefaultOutgoingChapUser [String] (Optional) Specifies the default CHAP user name you want to attach to the initiator. This is applicable when the authentication type is MutualChap.
- -FileServiceEnabled [Boolean] (Optional) Specifies whether to enable the file service or not. If the value is True, a suitable network should be provided. Note that the file service enablement process takes a long time. Set WebOperationsTimeout to a value such as 1 hour by running Set-PowerCLIConfiguration -WebOperationTimeoutSeconds 3600.
- -FileServiceNetwork [Network] (Optional) Specifies the network on which you want to deploy the file service to provide file access. The vSAN File services is supported on DVS version 6.6.0 or later. Creates a dedicated port group for the vSAN File Service in the DVS. The Promiscuous mode and Forged transmits are enabled as part of the vSAN file services enablement process for the provided network entity. If you use NSX-based networks, ensure that similar settings are configured for the provided network entity from the NSX admin console.
- -HostRebuildReservationState [VsanCapacityReservationState] (Optional) Specifies whether the host rebuild threshold is reported from the Get-VsanSpaceUsage cmdlet or vSAN should reserve the capacity to repair objects after a host failure.
- -VsanOperationReservationState [VsanCapacityReservationState] (Optional) Specifies whether the vSAN operation space threshold is reported from the Get-VsanSpaceUsage cmdlet or vSAN should reserve the capacity to perform internal operations.
- -GuestTrimUnmap [Boolean] (Optional) Specifies the TRIM/UNMAP for the respective ATA and SCSI protocols. If this setting switches from deactivated to activated for any UNMAP request to the vSAN datastore from powered on virtual machines, this takes effect and succeeds immediately. If you switch it from activated to deactivated dynamically, the running virtual machines that reside on this vSAN datastore understand this change until virtual machine rebooting happens. The default value is False.
- -SiteReadLocalityEnabled [Boolean] (Optional) Activates and deactivates site read locality. The default value is True.
- -CustomizedSwapObjectEnabled [Boolean] (Optional) Activates and deactivates customer's control over the 'proportionalCapacity' policy for the swap object. The default value is False.
- -LargeClusterSupported [Boolean] (Optional) Specifies whether large cluster supported feature is enabled or not. If this option is changed before vSAN enabled, you can apply it at the host side immediately. If you change it on a vSAN cluster, all hosts are required to reboot to apply the change. After setting this, review the vSAN health check result which can help to figure out which host requires rebooting. The default value is False.
- -ObjectRepairTimerMinutes [Int64] (Optional) Determines the delay time in minutes for the missing component to come back before starting the repair process. Allowed values: 0 to 4294967295 Default value: 60.
- -HealthCheckIntervalMinutes [Int32] (Optional) Specifies the health check interval in minutes. If the value of the parameter is non-zero, the health check feature is enabled on the cluster and a health check frequency is set to the specified value. If the value of the parameter is zero, the health check feature is deactivated on the cluster. The accepted values are in the range of 15 minutes to one day (1440 minutes).
- -HistoricalHealthEnabled [Boolean] (Optional) Activates or deactivates the historical health service on a vSAN cluster.
- -IscsiTargetServiceEnabled [Boolean] (Optional) Activates or deactivates the iSCSI target service on a vSAN cluster.
- -PerformanceServiceEnabled [Boolean] (Optional) Activates or deactivates the performance service on a vSAN cluster.
- -PreferredFaultDomain [VsanFaultDomain] (Optional) Specifies the preferred fault domain. If stretched cluster configuration is enabled, this becomes the preferred fault domain for this cluster. The other fault domain in this stretched cluster becomes the secondary fault domain.
- -MountRemoteDatastore [Datastore[]] (Optional) Specifies the remote vSAN datastores (provided by other vSAN clusters) to be mounted to the target vSAN cluster.
- -UnmountRemoteDatastore [Datastore[]] (Optional) Specifies the remote vSAN datastores (provided by other vSAN clusters) to be unmounted from the target vSAN cluster.
- -RemoteVsanServerClusterConfig [RemoteVsanServerClusterConfig] (Optional) Specifies the remote vSAN server cluster configuration of a stretched cluster for the datastore to be mounted. Use this parameter in combination with the MountRemoteDatastore parameter with one datastore at a time. You can use this parameter starting from vSAN 8.0 Update 1.
- -MountXVCDatastore [VsanHCIMeshDatastore[]] (Optional) Specifies the remote vSAN datastores from a remote vCenter to be mounted to the target vSAN cluster. You can use this parameter starting from vSAN 8.0 Update 1.
- -UnmountXVCDatastore [VsanHCIMeshDatastore[]] (Optional) Specifies the remote vSAN datastores from a remote vCenter to be unmounted from the target vSAN cluster. You can use this parameter starting from vSAN 8.0 Update 1.
- -VsanMaxEnabled [Boolean] (Optional) Specifies whether to enable vSAN Max service. If the value is True, the cluster should be vSAN ESA enabled.
- -RemoveSilentHealthCheck [String[]] (Optional) Specifies the health checks list you want to remove from the silent list.
- -ResyncThrottlingMbps [Int32] (Optional) Specifies the resynchronization traffic limit in Mbps for each disk group in the cluster. The valid values are from 1 to 512. If the value of the parameter is zero, throttling resynchronization traffic limits are deactivated.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SpaceEfficiencyEnabled [Boolean] (Optional) Activates or deactivates the deduplication and compression on a vSAN cluster. Both deduplication and compression are activated or deactivated together.
- -SpaceCompressionEnabled [Boolean] (Optional) Activates or deactivates the compression only mode on a vSAN cluster.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy. This parameter is applicable in the context of enabling the vSAN performance service. The vSAN performance history database is stored as a vSAN object. The policy controls the availability, space consumption, and performance of that object. If the object becomes unavailable, the performance history for that cluster is also unavailable.
- -StoragePolicyForIscsiTargetService [SpbmStoragePolicy] (Optional) Specifies the storage policy for the iSCSI target service. When you enable the iSCSI target service, vSAN creates a home object that stores metadata for the iSCSI target service. The storage policy for the home object should have a number of failures to tolerate.
- -StretchedClusterEnabled [Boolean] (Optional) Activates or deactivates a stretched cluster configuration.
- -WitnessHost [VMHost] (Optional) Specifies the witness host virtual machine in case StretchedClusterEnabled is enabled. It can also be a vSphere virtual appliance called witness appliance.
- -WitnessHostCacheDisk [String] (Optional) Specifies ? cache disk canonical name for the disk group that you want to create on the witness host. This parameter accepts ScsiLun or VMHostDisk objects through argument transformation.
- -WitnessHostCapacityDisk [String[]] (Optional) Specifies the capacity disk canonical names for the disk group that you want to create on the witness host. This parameter accepts ScsiLun or VMHostDisk objects through argument transformation.
- -WitnessHostStoragePoolDisk [String[]] (Optional) Specifies the disk canonical names for the storage pool that you want to create on the witness host. This parameter accepts ScsiLun or VMHostDisk objects through argument transformation. This parameter is available starting from vSphere 8.0.
- -VsanBaselinePreference [VsanBaselinePreferenceType] (Optional) Specifies the baseline preference policy for the current vSAN cluster.
- -ProactiveRebalanceEnabled [Boolean] (Optional) Specifies whether the proactive rebalance is enabled. If the value is set to True, rebalance data movement starts when the following requirements are met within the vSAN cluster: 1. Current disk fullness - lowest disk fullness > proactive threshold. 2. Current disk fullness > mean disk fulless within cluster. The default value is False.
- -ProactiveRebalanceThreshold [Int32] (Optional) Indicates the extent of the imbalance that the cluster can tolerate in percentage. If the disk imbalance (current disk fullness - lowest disk fullness) is below the rebalance threshold, the proactive rebalance will not be triggered. The allowed values are from 25 to 75. The default value is 30.

**Examples:**

```powershell
Set-VsanClusterConfiguration -Configuration (Get-VsanClusterConfiguration $cluster) -SpaceEfficiencyEnabled $true -HealthCheckIntervalMinutes 120
```
_Enables the space efficiency on the $cluster cluster and sets the periodic health check interval to 120 minutes._

```powershell
Set-VsanClusterConfiguration -Configuration "MyCluster" -StretchedClusterEnabled $true -PreferredFaultDomain $fd -WitnessHost $vmHost
```
_Enables a stretched cluster on the "MyCluster" cluster and specifies $fd as the primary fault domain and $vmHost as the witness host._

```powershell
Set-VsanClusterConfiguration -Configuration "MyCluster" -PerformanceServiceEnabled $true -StoragePolicy $policy
```
_Enables a performance service on the "MyCluster" cluster and associates the performance history database object with the $policy storage policy._

### `Set-VsanFaultDomain`

**This cmdlet changes the configuration of a specified vSAN fault domain.**

This cmdlet changes the configuration of a specified vSAN fault domain. You can change the name and specify a list of hosts to move in or out.

**Parameters:**

- -AddVMHost [VMHost[]] (Optional) Specifies the list of virtual machine hosts you want to move into this vSAN fault domain. Virtual machine hosts should be part of the cluster in which this fault domain exists.
- -Name [String] (Optional) Specifies the new name of the vSAN fault domain.
- -RemoveVMHost [VMHost[]] (Optional) Specifies the list of virtual machine hosts you want to move out of this vSAN fault domain. Virtual machine hosts should be part of this fault domain.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VsanFaultDomain [VsanFaultDomain[]] (Required) Specifies the list of vSAN fault domains you want to update.

**Examples:**

```powershell
Set-VsanFaultDomain -VsanFaultDomain $fd -Name "NewName" -AddVMHost $vmHost1, $vmHost2 -RemoveVMHost $vmHost3
```
_Renames the $fd vSAN fault domain to "NewName" and adds the $vmHost1 and $vmHost2 virtual machine hosts to it. Also, removes the $vmHost3 virtual machine host from the renamed vSAN fault domain._

### `Set-VsanFileServiceDomain`

**This cmdlet modifies the settings of the given vSAN file domains.**

This cmdlet modifies the settings of the given vSAN file service domains.

**Parameters:**

- -Name [String] (Optional) Specifies the new name of the vSAN file service domain.
- -VsanFileServiceDomain [VsanFileServiceDomain[]] (Required) Specifies the list of VSAN file service domains you want to remove.
- -DnsServerAddress [String[]] (Optional) Specifies the DNS server address which you want to use to resolve the hostnames within the DNS domain. This parameter is optional if the DNS name is provided in the access point configuration or is not required for an NFS access.
- -DnsSuffix [String[]] (Optional) Specifies the list of DNS server addresses that can be resolved by the DNS servers. The DNS suffix is required if the DNS servers are provided.
- -FileServerIpConfig [VsanFileServerIpConfig[]] (Optional) Specifies a pool of IP addresses that will be used by vSAN file service to provide file access from  multiple file servers. A minimum of one such address is needed. Considering the workload, it  is recommended to have equal or greater number of IP addresses than the number of hosts  in the cluster.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Set-VsanFileServiceDomain -VsanFileServiceDomain $domain -DnsServerAddress "10.172.199.240"
```
_Adds $ipconfig1 and $ipconfig2 to the $domain file service IP pool, sets the DNS server address to  "10.172.199.240", and the DNS suffix to "vmware.com"_

### `Set-VsanFileShare`

**This cmdlet modifies the configuration of a specified vSAN file share.**

**Parameters:**

- -FileShare [VsanFileShare[]] (Required) Specifies the list of vSAN file shares you want to update.
- -FileShareNetworkPermission [VsanFileShareNetworkPermission[]] (Optional) Specifies the new file share network permission settings of the vSAN file share.
- -HardQuotaGB [Decimal] (Optional) Specifies the new hard quota in GB of the vSAN file share.
- -SetLabel [Hashtable] (Optional) Specifies the newly added or updated labels of the vSAN file share. If the label key does not exist in file share, it is added with the provided value. If the label key exists in file share, the value of the key is updated.
- -RemoveLabel [String[]] (Optional) Specifies the label key that you want to remove from the vSAN file share. If a specified label key does not exist in the vSAN file share, the deletion of this label is ignored.
- -Name [String] (Optional) Specifies the new name of the vSAN file share.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SoftQuotaGB [Decimal] (Optional) Specifies the new soft quota in GB of the vSAN file share.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the new storage policy of the vSAN file share.
- -Force [SwitchParameter] (Optional) Indicates that you want to remove the vSAN file share (for example, the file share whose ManagingEntity is the Cloud Native Storage (CNS) service).

**Examples:**

```powershell
Set-VsanFileShare -FileShare $fileShare -Name "NewName" -SoftQuotaGB 20
```
_Renames the $fileShare vSAN file share to "NewName" and sets the soft quota to 20 GB._

### `Set-VsanIscsiInitiatorGroup`

**This cmdlet modifies the specified vSAN iSCSI initiator groups.**

**Parameters:**

- -AddInitiator [String[]] (Optional) Specifies the names of the vSAN iSCSI initiators which you want to add to the initiator group.
- -InitiatorGroup [VsanIscsiInitiatorGroup[]] (Required) Specifies the vSAN iSCSI initiator group to which you want to add or remove initiators.
- -RemoveInitiator [String[]] (Optional) Specifies the names of the vSAN iSCSI initiators which you want to remove from the initiator group.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Set-VsanIscsiInitiatorGroup -InitiatorGroup $initiatorGroup -AddInitiator "initiator1-iqn", "initiator2-iqn" -RemoveInitiator "initiator3-iqn"
```
_Adds iSCSI initiators with IQN "initiator1-iqn" and "initiator2-iqn" to the $initiatorGroup initiator group and removes iSCSI initiator with IQN "initiator3-iqn" from the initiator group._

### `Set-VsanIscsiLun`

**This cmdlet modifies the specified vSAN iSCSI LUNs.**

**Parameters:**

- -CapacityGB [Decimal] (Optional) Specifies the new capacity of the vSAN iSCSI LUN in gigabytes (GB). The LUN size can only increase. This operation is possible only when the LUN is in offline state.
- -IsOnline [Boolean] (Optional) Puts the iSCSI LUN in offline or online state.
- -Lun [VsanIscsiLun[]] (Required) Specifies the vSAN iSCSI LUNs you want to modify.
- -LunId [Int32] (Optional) Specifies the new LUN ID of the iSCSI LUN. The value must be in the range from 0 to 255. The LUN ID can be changed only when the LUN is in offline state.
- -Name [String] (Optional) Specifies the new name of the vSAN iSCSI LUN.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy associated with the vSAN iSCSI LUN.

**Examples:**

```powershell
Set-VsanIscsiLun -Lun $lun -CapacityGB 3
```
_Increases the capacity of the $lun iSCSI LUN to 3 GB._

```powershell
Set-VsanIscsiLun -Lun $lun -IsOnline $false
```
_Puts the $lun iSCSI LUN in offline state._

### `Set-VsanIscsiTarget`

**This cmdlet modifies the settings of the specified vSAN iSCSI targets.**

This cmdlet modifies the settings of the specified vSAN iSCSI targets. The cmdlet first adds and then removes the initiators if specified. After those operations are completed, other reconfigurations can occur.

**Parameters:**

- -AddInitiator [String[]] (Optional) Specifies the names of the vSAN iSCSI initiators which you want to add to the allowed access list.
- -AuthenticationType [VsanIscsiTargetAuthenticationType] (Optional) Specifies the authentication type for the iSCSI target.
- -IncomingChapSecret [SecureString] (Optional) Specifies the CHAP user secret for the target. Applicable when the authentication type is Chap or MutualChap.
- -IncomingChapUser [String] (Optional) Specifies the CHAP user name for the target. Applicable when the authentication type is Chap or MutualChap.
- -Name [String] (Optional) Specifies the new name of the vSAN iSCSI target. The name should be unique within a cluster.
- -NetworkInterface [String] (Optional) Specifies the VMkernel network interface which handles the iSCSI traffic. This parameter accepts an object of type HostVMKernelVirtualNic by silently converting it to the string name by using ArgumentTransformationAttribute.
- -OutgoingChapSecret [SecureString] (Optional) Specifies the CHAP user secret you want to attach to the initiator. Applicable when the authentication type is MutualChap.
- -OutgoingChapUser [String] (Optional) Specifies the CHAP user name you want to attach to the initiator. Applicable when the authentication type is MutualChap.
- -RemoveInitiator [String[]] (Optional) Specifies the names of the vSAN iSCSI initiators which you want to remove from the allowed access list.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy applied to the vSAN namespace of the iSCSI target.
- -Target [VsanIscsiTarget[]] (Required) Specifies the list of vSAN iSCSI targets you want to modify.
- -TcpPort [Int32] (Optional) Specifies the network port on which the target is accessible. If specified, NetworkInterface should also be specified.

**Examples:**

```powershell
Set-VsanIscsiTarget -Target $target -Name "NewName" -AddInitiator "initiator1-iqn", "initiator2-iqn" -RemoveInitiator "initiator3-iqn"
```
_Renames the $target vSAN iSCSI target to "NewName" and adds iSCSI initiators with IQN "initiator1-iqn" and "initiator2-iqn" to iSCSI target. The command removes iSCSI initiator with IQN "initiator3-iqn" from the iSCSI target._

## Start

### `Start-SpbmReplicationFailover`

**This cmdlet performs a failover of the devices in the specified replication groups.**

This cmdlet performs a failover of the devices in the specified replication groups. This cmdlet should be called at the replication target location. After the operation succeeds, the devices will be ready to be registered by using the virtual machine file path.

**Parameters:**

- -CheckOnly [SwitchParameter] (Optional) Does not perform the failover, but checks if the configuration is correct to perform the failover.
- -PointInTimeReplica [SpbmPointInTimeReplica[]] (Optional) Specifies the point in time replica object you want to use for the corresponding replication group failover. If no replica is specified for a replication group, the latest available replica is used by default by the VASA provider. If more than one replica is specified for a replication group, a non-terminating error is generated for that replication group.
- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the target replication groups to failover at.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SourceVvolIdMap [Hashtable] (Optional) This parameter is no longer required and will be removed in a future release. This will contain a map of sourceVvolId (of the devices) to containerId (of the VVol datastore) for all the devices in the specified replication groups.
- -Unplanned [SwitchParameter] (Optional) Specifies an unplanned failover.

**Examples:**

```powershell
Start-SpbmReplicationFailover -ReplicationGroup $targetRg -CheckOnly
```
_Checks whether the target replication group has the correct configuration to perform the failover._

```powershell
Start-SpbmReplicationFailover -ReplicationGroup $targetRg -Unplanned
```
_Performs an unplanned failover on the $targetRg target replication group._

### `Start-SpbmReplicationPrepareFailover`

**This cmdlet prepares the specified replication groups to fail over.**

**Parameters:**

- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the replication group you want to prepare for failover. The replication group should be a source replication group.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Start-SpbmReplicationPrepareFailover -ReplicationGroup $sourceRg
```
_Performs the preparation of a planned failover on the $sourceRg source replication group._

### `Start-SpbmReplicationPromote`

**This cmdlet promotes a target replication group from InTest to FailedOver state.**

**Parameters:**

- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the replication groups to promote to FailedOver state.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Unplanned [SwitchParameter] (Optional) Indicates if the promote operation is unplanned or planned.

**Examples:**

```powershell
Start-SpbmReplicationPromote -ReplicationGroup $targetRg
```
_Promotes the $targetRg target replication group from InTest state to FailedOver._

### `Start-SpbmReplicationReverse`

**This cmdlet initiates reverse replication, by making the currently failed over replication group the source and its peer replication group the target.**

This cmdlet initiates reverse replication, by making the currently failed over replication group the source and its peer replication group the target. The devices in the replication group will start getting replicated to this new target site, which was the source before the failover.

**Parameters:**

- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the replication groups which are in failed over state and are to be converted to source group.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Start-SpbmReplicationReverse -ReplicationGroup $targetRg
```
_Reverses the direction of replication for $targetRg target replication group. The $targetRg replication group becomes the source replication group and the corresponding source replication group becomes the target replication group._

### `Start-SpbmReplicationTestFailover`

**This cmdlet performs a test failover of a target replication group.**

This cmdlet performs a test failover of a target replication group. If the operation succeeds, the replication state of the replication group becomes InTest.

**Parameters:**

- -CheckOnly [SwitchParameter] (Optional) Does not perform the test failover, but checks if the configuration is correct to perform the test failover.
- -PointInTimeReplica [SpbmPointInTimeReplica[]] (Optional) Specifies the point in time replica object you want to use for the corresponding replication group test failover. If no replica is specified for a replication group, the latest available replica is used by default by the VASA provider. If more than one replica is specified for a replication group, a non-terminating error is generated for that replication group.
- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the replication group on which you want to perform the test failover.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SourceVvolIdMap [Hashtable] (Optional) This parameter is no longer required and will be removed in a future release. This will contain a map of sourceVvolId (of the devices) to containerId (of the VVol datastore) for all the devices in the specified replication groups.
- -Unplanned [SwitchParameter] (Optional) Specifies an unplanned test failover.

**Examples:**

```powershell
Start-SpbmReplicationTestFailover -ReplicationGroup $targetRg -CheckOnly
```
_Checks if the target replication group has the correct configuration to perform a test failover._

```powershell
Start-SpbmReplicationTestFailover -ReplicationGroup $targetRg -Unplanned -PointInTimeReplica $replica
```
_Performs a test failover of an unplanned type on the $targetRg target replication group by using the $replica point in time replica._

### `Start-VsanCluster`

**This cmdlet executes vSAN cluster power on.**

This cmdlet powers on a vSAN cluster.

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the vSAN cluster to power on.
- -PowerOnReason [String] (Optional) Specifies the reason for powering on. The allowed length is up to 512 characters.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Start-VsanCluster -Cluster "VSAN-Cluster"
```
_Powers on the specified cluster._

### `Start-VsanClusterDiskUpdate`

**This cmdlet starts the update of all vSAN disks of a cluster to the latest vSAN disk format version supported by the cluster.**

This cmdlet starts the update of all vSAN disks of a cluster to the latest vSAN disk format version supported by the cluster. After the update finishes successfully, all vSAN disks in the cluster use the latest disk format version supported by the cluster. The cmdlet returns a task object that you can wait upon and query for progress.

**Parameters:**

- -AllowReducedRedundancy [Boolean] (Optional) This optional parameter is applicable to specific vSAN cluster reconfigure operations that need to migrate data for changing the vSAN disk format across the cluster. When specified, the process might move less data to ensure storage object accessibility, and some objects might be kept at "reduced redundancy" state, which means at a higher risk in case of a hardware failure during the migration process. The default value is $false.
- -Cluster [Cluster[]] (Required) Specifies the cluster for which you want to update all vSAN disks.
- -EncryptionEnabled [Boolean] (Optional) Specifies that you want to use encryption to format the disks in the cluster. The encryption configuration of the cluster does not change when you set this parameter.
- -EraseDisksBeforeUse [Boolean] (Optional) Specifies whether disks should be formatted when a normal disk is converted to an encrypted disk. The encryption configuration of the cluster does not change when you set this parameter.
- -KeyProvider [KeyProvider] (Optional) Specifies the key provider you want to use to format disks in the cluster. The encryption configuration of the cluster does not change when you set this parameter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -SkipHostRemediation [SwitchParameter] (Optional) Indicates that host configuration remediation is skipped as part of the disk format conversion. By default, remediation runs to ensure hosts are consistent. If hosts are inconsistent, the disk format conversion prevents errors. If all hosts are already consistent and have the latest configuration, you can set the value to $true.
- -SpaceEfficiencyEnabled [Boolean] (Optional) Specifies whether to activate or deactivate vSAN data efficiency from the disk format layer. This parameter is only applicable to all-flash clusters. The encryption configuration of the cluster does not change when you set this parameter.

**Examples:**

```powershell
Start-VsanClusterDiskUpdate -Cluster "vsan-cluster"
```
_Updates the disk format of all vSAN disks in the "vsan-cluster" cluster to the latest disk format version supported by that cluster._

### `Start-VsanClusterRebalance`

**This cmdlet starts the proactive rebalance of the vSAN objects on the cluster hosts based on the vSAN disks usage when the disks are in imbalanced state.**

This cmdlet starts the proactive rebalance of the vSAN objects on the cluster hosts based on the vSAN disks usage when the disks are in imbalanced state. The typical use case is to add a new host or disk to the vSAN cluster. Rebalancing increases the background I/O requirements for data movements.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster on which you want to start the proactive rebalance of the vSAN objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Start-VsanClusterRebalance -Cluster $vsanCluster
```
_Starts the proactive rebalance of the $vsanCluster vSAN cluster._

### `Start-VsanEncryptionConfiguration`

**This cmdlet starts an encryption configuration on a vSAN cluster.**

**Parameters:**

- -AllowReducedRedundancy [Boolean] (Optional) This optional parameter is applicable to specific vSAN cluster reconfigure operations that need to migrate data for changing the vSAN disk format across the cluster. When specified, the process might move less data to ensure storage object accessibility, and some objects might be kept at "reduced redundancy" state, which means at a higher risk in case of a hardware failure during the migration process. The default value is $false.
- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster on which you want to start the encryption configuration of the vSAN objects.
- -DeepRekey [SwitchParameter] (Optional) Specifies that you want to perform a deep rekey operation. When a deep rekey operation runs, all disks are re-encrypted with new data encryption keys. The deep rekey operation takes long time to finish.
- -EncryptionEnabled [Boolean] (Optional) Specifies whether you want to activate or deactivate the encryption.
- -EraseDisksBeforeUse [Boolean] (Optional) Specifies whether the disk should be formatted when a normal disk is converted to an encrypted disk, it is claimed as encrypted disk, or it runs deep rekey. If the value of this parameter is $true, every sector on the disk is written with random data. Disk cleanup reduces the possibility of data leak and increases the potential intruder's cost to reveal sensitive data. Turn the disk cleanup on only when necessary, as it takes long time to finish. If the value of this parameter is $false, the disk will not be formatted.
- -KeyProvider [KeyProvider] (Optional) Specifies the key provider you want to use for the encryption.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -ShallowRekey [SwitchParameter] (Optional) Specifies that you want to perform a shallow rekey operation. When a shallow rekey operation runs, only the key encryption key (KEK) is changed and the data encryption keys (DEKs) are rewrapped with new key encryption keys.

**Examples:**

```powershell
Start-VsanEncryptionConfiguration -Cluster $vsanCluster -EncryptionEnabled $true -KeyProvider 'ThalesCluster'
```
_Enables the encryption on the $vsanCluster vSAN cluster with 'ThalesCluster' as the key provider._

```powershell
Start-VsanEncryptionConfiguration -Cluster $vsanCluster -EncryptionEnabled $false
```
_Deactivates the encryption on the $vsanCluster vSAN cluster._

```powershell
Start-VsanEncryptionConfiguration -Cluster $vsanCluster -DeepRekey
```
_Performs a deep rekey operation on all disks of the $vsanCluster vSAN cluster. All data on the disks is re-encrypted._

### `Start-VsanRelayoutObjects`

**This cmdlet starts the task of relayouting objects for specified vSAN clusters.**

This cmdlet starts the task of relayouting objects for specified vSAN clusters. After a cluster is upgraded to vSAN 7.0 U1 or later from vSAN 7.0 or earlier version, the objects greater than 255 GB created with the older version must be rewritten in the new format so that vSAN can perform operations on an object with the new free space requirements. A new object format health alert is displayed after an upgrade, if there are objects that must be fixed to the new object format. You can fix the cluster health state by starting a task to relayout objects for the specified vSAN clusters.

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster on which you want to relayout objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Start-VsanRelayoutObjects -Cluster $cluster
```
_Starts the re-layout object task of $cluster._

### `Start-VsanWipeDisk`

**This cmdlet starts the secure wipe of the specified host SCSI disks.**

**Parameters:**

- -CanonicalName [String[]] (Required) Specifies the canonical name of the host SCSI disk.
- -VMHost [VMHost] (Required) Specifies the host on which the disks belong.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Start-VsanWipeDisk -CanonicalName "DiskCanonicalName" -VMHost $host
```
_Starts the secure wipe disk process of "DiskCanonicalName" from the $host host._

## Stop

### `Stop-SpbmReplicationTestFailover`

**This cmdlet stops the test failover on the specified replication groups and tries to perform a cleanup on the target site.**

This cmdlet stops the test failover on the specified replication groups and tries to perform a cleanup on the target site. After successful completion the replication group state returns to Target.

**Parameters:**

- -Force [SwitchParameter] (Optional) If specified, VASA Provider should force-unbind all Virtual Volumes and move the replication group from InTest to Target state. If not specified, VP reports all the Virtual Volumes that need to be cleaned up before a failover operation can be initiated.
- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the replication groups on which you want to stop the test failover.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Stop-SpbmReplicationTestFailover -ReplicationGroup $targetRg
```
_Performs the cleanup of a test failover done on the $targetRg target replication group._

### `Stop-VsanCluster`

**This cmdlet powers off a vSAN cluster.**

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the vSAN cluster to power off.
- -InfraVMs [VirtualMachine[]] (Optional) Specifies the UUIDs of infrastructure VMs that will be forced to power off during the vSAN cluster power-off and will be automatically powered on afterwards. Some VMs are deployed with vCeter Server-dependent services such as DNS. You can use this parameter to power off such VMs as they must power off together with their vCenter Server.
- -PowerOffReason [String] (Required) Specifies the reason for powering off. The allowed length is up to 512 characters.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Stop-VsanCluster -Cluster "VSAN-Cluster"
```
_Powers off the specified cluster._

### `Stop-VsanClusterRebalance`

**This cmdlet stops the proactive rebalance of the vSAN objects on the cluster hosts.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the vSAN cluster on which you want to stop the proactive rebalance of the vSAN objects.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Stop-VsanClusterRebalance -Cluster $vsanCluster
```
_Stops the ongoing proactive rebalance of the $vsanCluster vSAN cluster._

### `Stop-VsanWipeDisk`

**This cmdlet stops the secure wipe of the specified host SCSI disks.**

**Parameters:**

- -CanonicalName [String[]] (Required) Specifies the canonical name of the host SCSI disk.
- -VMHost [VMHost] (Required) Specifies the host on which the disks belong.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Stop-VsanWipeDisk -CanonicalName "DiskCanonicalName" -VMHost $host
```
_Stops the secure wipe disk process of "DiskCanonicalName" from the $host host._

## Sync

### `Sync-SpbmReplicationGroup`

**This cmdlet synchronizes the data between source and replica for the specified replication group.**

This cmdlet synchronizes the data between source and replica for the specified replication group. The replicas of the devices in the replication group are updated and a new point in time replica is created. This function should be called at the replication target location.

**Parameters:**

- -PointInTimeReplicaName [String] (Required) Specifies the name of the point in time replica which will be created by this synchronization operation on the target site.
- -ReplicationGroup [SpbmReplicationGroup[]] (Required) Specifies the target replication groups you want to synchronize with their corresponding source replication groups.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Sync-SpbmReplicationGroup -ReplicationGroup $targetRg -PointInTimeReplicaName 'MyReplica'
```
_Synchronizes the devices in the source replication group that corresponds to the $targetRg target replication group, creates a point in time replica of the devices at the target site, and names the replica 'MyReplica'._

## Test

### `Test-VsanClusterHealth`

**This cmdlet runs a health test on the specified vSAN clusters and returns the test results.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters on which you want to run a vSAN health test.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TestResultFilter [VsanClusterHealthResultFilter[]] (Optional) Specifies a subset of health test results. Only the specified test result fields are returned.
- -UseCache [SwitchParameter] (Optional) Indicates to return the result directly from cache instead of running the full health check. The cache is updated periodically and keeps the latest vSAN health summary check result, either triggered from a user on-demand request or the periodical vSAN health check for triggering a health event or alarm.
- -VMCreateTimeoutSeconds [Int32] (Optional) Specifies the timeout to run virtual machine creation tests in seconds. The default value is 120.
- -Perspective [VsanHealthPerspectiveType] (Optional) Specifies the health check perspective. This parameter declares the perspective of the vSAN health check depending on its purpose. For example, you can do a customized health check before running a vSAN cluster power-off by using ClusterPowerOffPrecheck as the parameter value. You can use this parameter starting from vSAN 7.0 Update 3.

**Examples:**

```powershell
Test-VsanClusterHealth -Cluster $cluster
```
_Runs the vSAN cluster health test on $cluster vSAN cluster and returns the result of the test._

```powershell
Test-VsanClusterHealth -Cluster $cluster -UseCache -TestResultFilter NetworkHealth, DiskBalance
```
_Gets the result of the last health test run on $cluster vSAN cluster. Returns test result fields for network health and disk balance._

```powershell
Test-VsanClusterHealth -Cluster $cluster -Perspective "clusterPowerOffPrecheck"
```
_Runs a health test on the specified vSAN cluster for the purposes of a precheck before powering off a vSAN cluster._

### `Test-VsanNetworkPerformance`

**This cmdlet runs a network performance test on the specified vSAN clusters and returns the test results.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters on which you want to run a vSAN network performance test.
- -DurationInSecond [Int32] (Optional) The duration of network performance test in seconds.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -UseCache [SwitchParameter] (Optional) Indicates whether to get a cached result from the server. If specified, a test is not run on the server and the last result cached on the server side is returned. If not specified, a test is run on the server side and the result is returned.

**Examples:**

```powershell
Test-VsanNetworkPerformance -Cluster $cluster
```
_Runs the network performance test on the $cluster vSAN cluster and returns the result of the test._

```powershell
Test-VsanNetworkPerformance -Cluster $cluster -UseCache
```
_Gets the result of the last network performance test run on the $cluster vSAN cluster._

```powershell
Test-VsanNetworkPerformance -Cluster $cluster -DurationInSecond 10
```
_Runs the network performance test on the $cluster vSAN cluster for 10 seconds and returns the result of the test._

### `Test-VsanStoragePerformance`

**This cmdlet runs a storage performance test on the specified vSAN clusters and returns the test results.**

**Parameters:**

- -Cluster [Cluster[]] (Required) Specifies the clusters on which you want to run a vSAN storage performance test.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StoragePolicy [SpbmStoragePolicy] (Optional) Specifies the storage policy you want to use.
- -TestDurationSeconds [Int32] (Optional) Specifies the duration of the storage performance test in seconds. When the UseCache parameter is not specified, TestDurationSeconds must be specified.
- -UseCache [SwitchParameter] (Optional) Indicates whether to get a cached result from the server. If specified, a test is not run on the server and the last result cached on the server side is returned. If not specified, a test is run on the server side and the result is returned.
- -Workload [VsanStorageWorkloadType] (Optional) Specifies the type of workload which should be run to test the storage performance.

**Examples:**

```powershell
Test-VsanStoragePerformance -Cluster $cluster -TestDurationsSeconds 120 -StoragePolicy $policy -WorkLoad BasicSanityTest
```
_Runs the storage performance test of basic sanity workload type with test duration of 120 seconds, using the $policy storage policy on the $cluster vSAN cluster, and returns the result of the test._

```powershell
Test-VsanStoragePerformance -Cluster $cluster -UseCache
```
_Gets the result of the last storage performance test run on the $cluster vSAN cluster._

## Update

### `Update-VsanHclDatabase`

**This cmdlet updates the vSAN hardware compatibility list (HCL) database.**

This cmdlet updates the vSAN hardware compatibility list (HCL) database. It can be updated by using the latest online version or from a file, if Internet is not accessible. The cmdlet updates the HCL database for all clusters on the specified servers.

**Parameters:**

- -FilePath [String] (Optional) Specifies the path to file from which vSAN HCL database is updated. If not specified, the database is updated with latest version from the Internet.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Update-VsanHclDatabase -FilePath "LocalHclDbFilepath"
```
_Updates the vSAN HCL database on the vSphere server by using the content of the "LocalHclDbFilepath" file._

```powershell
Update-VsanHclDatabase
```
_Updates the vSAN HCL database on the vSphere server by using the latest version from the Internet._

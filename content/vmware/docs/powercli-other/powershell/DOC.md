---
name: powercli-other
description: "VMware PowerCLI 13.3 — Additional VMware PowerCLI cmdlets"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,other,Add-PassthroughDevice, Dismount-Tools, Get-AdvancedSetting, Get-CDDrive, Get-CisCommand, Get-CisService, Get-FloppyDrive, Get-KmipClientCertificate, Get-NetworkAdapter, Get-PassthroughDevice, Get-ScsiController, Get-ScsiLun, Get-ScsiLunPath, Get-Snapshot, Get-UsbDevice, Get-VAIOFilter, Get-VApp, Get-VasaProvider, Get-VDBlockedPolicy, Get-VDUplinkLacpPolicy, Get-VDUplinkTeamingPolicy, Mount-Tools, Move-VApp, New-AdvancedSetting, New-CDDrive, New-CnsKubernetesEntityMetadata, New-CnsKubernetesEntityReference, New-FloppyDrive, New-KmipClientCertificate, New-NetworkAdapter, New-ScsiController, New-Snapshot, New-VAIOFilter, New-VApp, New-VasaProvider, Remove-AdvancedSetting, Remove-CDDrive, Remove-FloppyDrive, Remove-NetworkAdapter, Remove-PassthroughDevice, Remove-Snapshot, Remove-UsbDevice, Remove-VAIOFilter, Remove-VApp, Remove-VasaProvider, Set-AdvancedSetting, Set-CDDrive, Set-FloppyDrive, Set-NetworkAdapter, Set-ScsiController, Set-ScsiLun, Set-ScsiLunPath, Set-Snapshot, Set-VAIOFilter, Set-VApp, Set-VDBlockedPolicy, Set-VDUplinkLacpPolicy, Set-VDUplinkTeamingPolicy, Set-VDVlanConfiguration, Start-VApp, Stop-VApp, TabExpansion2, Wait-Tools"
---

# VMware PowerCLI — Other

Additional VMware PowerCLI cmdlets. Module: VMware.VimAutomation (63 cmdlets).

## Add

### `Add-PassthroughDevice`

**This cmdlet attaches pass-through devices to the specified virtual machine.**

This cmdlet attaches pass-through devices to the specified virtual machine. Note that the value of the ControllerKey property of the returned device might not be up to date, if a new SCSI controller creation process  is running in the background.

**Parameters:**

- -PassthroughDevice [PassThroughDevice[]] (Required) Specifies the passthrough devices you want to add to the virtual machine.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machine to which you want to attach the passthrough devices.

**Examples:**

```powershell
$scsiDeviceList = Get-PassthroughDevice -VMHost Host -Type Scsi

Add-PassthroughDevice -VM $vm -PassthroughDevice $scsiDeviceList[0]
```
_Adds the first SCSI passthrough device of the Host host to the $vm virtual machine._

## Dismount

### `Dismount-Tools`

**This cmdlet dismounts the VMware Tools installer CD.**

This cmdlet dismounts the VMware Tools installer CD from one or more virtual machines operating systems specified by the VM and Guest parameters. To specify a server different from the default one, use the Server parameter. The virtual machines must be powered on.

**Parameters:**

- -Guest [VMGuest[]] (Optional) Specifies the guest operating systems from which you want to remove the VMware Tools.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which the search for virtual machine names passed by the VM parameter is performed. If no value is given to this parameter, the search for the virtual machine names is performed on the default server.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines from which you want to remove the VMware Tools.

**Examples:**

```powershell
Dismount-Tools VM
```
_Dismounts the VMware Tools from the VM virtual machine. The virtual machine must be powered on._

```powershell
Get-VMGuest VM | Dismount-Tools
```
_Dismounts the VMware Tools from the virtual machine specified by its guest operating system. The virtual machine must be powered on._

## Get

### `Get-AdvancedSetting`

**This cmdlet retrieves the advanced settings for the specified entity.**

**Parameters:**

- -Entity [VIObject[]] (Required) Specifies the entities for which you want to retrieve the advanced settings. This parameter accepts VIServer, VirtualMachine, VMHost, DatastoreCluster, and Cluster objects.
- -Name [String[]] (Optional) Specifies the names of the advanced settings you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-AdvancedSetting -Entity (Get-Cluster -Name Cluster)
```
_Retrieves the advanced settings of the cluster named Cluster._

```powershell
Get-AdvancedSetting -Entity (Get-Cluster -Name Cluster) -Name SettingName
```
_Retrieves the advanced setting named SettingName of the Cluster cluster._

```powershell
Get-AdvancedSetting -Entity Server -Name '*smtp*'
```
_Retrieve all smtp settings for the specified server._

### `Get-CDDrive`

**This cmdlet retrieves virtual CD drives.**

This cmdlet returns a set of virtual CD drives  that belong to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the CD drives you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the CD drives you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Snapshot [Snapshot[]] (Optional) Specifies the snapshots from which you want to retrieve virtual CD drives.
- -Template [Template[]] (Optional) Specifies the virtual machine templates from which you want to retrieve virtual CD drives.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines from which you want to retrieve virtual CD drives.

**Examples:**

```powershell
Get-VM -Name VM | Get-CDDrive
```
_Connects to a vSphere server and retrieves the CD drive of the virtual machine named VM._

### `Get-CisCommand`

**This function retrieves all commands of the VMware.VimAutomation.Cis.Core module.**

This function retrieves all commands of the VMware.VimAutomation.Cis.Core module, including cmdlets, aliases, and functions.

**Parameters:**

- -Name [String] (Optional) Specifies the name of the command you want to retrieve.

### `Get-CisService`

**This cmdlet retrieves PSObject objects that represent a proxy to a vSphere Automation SDK API service and can be used to invoke the operations of that vSphere Automation SDK API service.**

This cmdlet retrieves PSObject objects that represent a proxy to a vSphere Automation SDK API service and can be used to invoke the operations of that vSphere Automation SDK API service. The cmdlet  returns one PSObject object for every service available on the vSphere Automation SDK server.

**Parameters:**

- -Name [String[]] (Optional) Specifies the service type ID.
- -Server [CisServer[]] (Optional) Specifies the vSphere Automation SDK servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-CisServer.

**Examples:**

```powershell
Get-CisService -Name 'com.vmware.cis.tagging.tag'
```
_Retrieves the binding for the specified service._

```powershell
# Connect to the vSphere Automation SDK API
Connect-CisServer -Server $serverAddress -User $user -Password $pass

# Get the service for VM management
$vmService = Get-CisService com.vmware.vcenter.VM

# Create a VM creation specification
$createSpec = $vmService.Help.create.spec.Create()

# Fill in the creation details
$createSpec.name = "ExampleVM"
$createSpec.guest_OS = "WINDOWS_7_64"

# Create a placement specification
$createSpec.placement = $vmService.Help.create.spec.placement.Create()

# Fill in the placement details
$createSpec.placement.folder = (Get-Folder vm).ExtensionData.MoRef.Value
$createSpec.placement.host = (Get-VMHost)[0].ExtensionData.MoRef.Value
$createSpec.placement.datastore = (Get-Datastore)[0].ExtensionData.MoRef.Value

# Call the create method passing the specification
$vmService.create( $createSpec )
```
_Connects to a vSphere Automation SDK server, retrieves the service for virtual machine management, and  creates a virtual machine, based on the provided creation details by passing the specification to the create method._

### `Get-FloppyDrive`

**This cmdlet retrieves the virtual floppy drives available on a vCenter Server system.**

This cmdlet retrieves the virtual floppy drives available on a vCenter Server system. Returns a set of virtual floppy drives that belong to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the floppy drives you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the floppy drives you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Snapshot [Snapshot[]] (Optional) Specifies the snapshots from which you want to retrieve virtual CD drives.
- -Template [Template[]] (Optional) Specifies the templates from which you want to retrieve virtual CD drives.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines from which you want to retrieve virtual floppy drives.

**Examples:**

```powershell
Get-FloppyDrive -VM VM
```
_Retrieves the floppy drive of the virtual machine named VM._

### `Get-KmipClientCertificate`

**This cmdlet retrieves the latest generated self-signed certificate or certificate-signing request for the key provider.**

This cmdlet retrieves the latest generated self-signed certificate or certificate-signing request for the key provider. The self-signed certificate or certificate-signing request is available until the key provider is updated with the generated certificate by using the Set-KeyProvider cmdlet.

**Parameters:**

- -CertificateSigningRequest [SwitchParameter] (Optional) Indicates whether a certificate-signing request should be retrieved. This certificate-signing request should be signed by the key management server and uploaded to the vCenter Server system.
- -FilePath [String] (Optional) Specifies the file path to which you want to export the self-signed certificate or certificate-signing request.
- -KeyProvider [KeyProvider] (Required) Specifies the key provider for which you want to use the certificate as a client certificate.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-KmipClientCertificate -KeyProvider $keyProvider
```
_Retrieves the latest generated self-signed client certificate for the $keyProvider key provider._

```powershell
Get-KmipClientCertificate -KeyProvider $keyProvider -CertificateSigningRequest -FilePath $filePath
```
_Retrieves the latest generated certificate-signing request for the $keyProvider key provider and exports it to the $filePath file path._

### `Get-NetworkAdapter`

**This cmdlet retrieves the virtual network adapters  available on a vCenter Server system.**

This cmdlet retrieves the virtual network adapters  available on a vCenter Server system. The cmdlet returns a set of virtual network adapters assigned to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the network adapters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the network adapters you want to retrieve.
- -RelatedObject [NetworkAdapterRelatedObjectBase[]] (Required) Specify an object to retrieve one or more network adapters that are related to the object. This parameter accepts standard and distributed port groups.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Snapshot [Snapshot[]] (Optional) Specifies the snapshots from which you want to retrieve virtual network adapters.
- -Template [Template[]] (Optional) Specifies the templates from which you want to retrieve virtual network adapters.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines from which you want to retrieve virtual network adapters.

**Examples:**

```powershell
Get-NetworkAdapter -VM MyVM
```
_Retrieves the network adapters added to the the MyVM virtual machine._

```powershell
$myVDPortgroup = Get-VDPortGroup -Name "MyVDPortGroup"
$myNetworkAdapters = Get-NetworkAdapter -RelatedObject $myVDPortgroup
```
_Retrieves all network adapters connected to the specified port group and stores them in the myNetworkAdapters variable._

### `Get-PassthroughDevice`

**This cmdlet retrieves the pass-through devices available on the specified hosts, virtual machines, and templates.**

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the pass-through devices you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the pass-through devices you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Template [Template[]] (Optional) Specifies the virtual machine templates for which you want to retrieve the pass-through devices.
- -Type [PassthroughDeviceType] (Optional) Specifies the type of the pass-through devices you want to retrieve. The valid values are SCSI and PCI. PCI is supported only on vCenter Server 4.1 and ESX 4.1 and later.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines for which you want to retrieve the pass-through devices.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve the pass-through devices.

**Examples:**

```powershell
Get-PassthroughDevice -VMHost Host -Type Scsi
```
_Retrieves the SCSI passthrough devices of the Host host._

### `Get-ScsiController`

**This cmdlet retrieves the virtual SCSI controllers assigned to the specified HardDisk, VirtualMachine, Template, and Snapshot objects.**

**Parameters:**

- -HardDisk [HardDisk[]] (Optional) Filters the SCSI controllers by the hard disks they belong to.
- -Id [String[]] (Optional) Specifies the IDs of the SCSI controllers you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the SCSI controllers you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Snapshot [Snapshot[]] (Optional) Filters the SCSI controllers by the snapshots they belong to.
- -Template [Template[]] (Optional) Filters the SCSI controllers by the virtual machine templates they belong to.
- -VM [VirtualMachine[]] (Optional) Filters the SCSI controllers by the virtual machines they belong to.

**Examples:**

```powershell
Get-VM VM1, VM2 | Get-ScsiController
```
_Retrieves the SCSI controllers of the VM1 and VM2 virtual machines._

```powershell
Get-VM VM | Get-Snapshot Snapshot | Get-ScsiController
```
_Retrieves the SCSI controllers of a virtual machine snapshot._

```powershell
$disk = Get-VM VM | Get-HardDisk | Select -First 2

Get-ScsiController -HardDisk $disk
```
_Retrieves the SCSI controllers of the first two hard disks of a virtual machine._

### `Get-ScsiLun`

**This cmdlet retrieves the SCSI devices available on the vCenter Server system.**

This cmdlet retrieves the SCSI devices available on the vCenter Server system. Examples of SCSI logical unit objects include disks which may contain file system volumes or parts of volumes for the host or might serve as raw disks to a virtual machine. Other examples include SCSI passthrough devices that can be used by virtual machines. When retrieving ScsiLun objects by Datastore, the cmdlet returns a ScsiLun object for each host connected to the specified datastore. ScsiLun objects can be differed by their VMHost property.

**Parameters:**

- -CanonicalName [String[]] (Optional) Specifies the canonical name of the SCSI devices you want to retrieve. An example of a SCSI canonical name for Windows is "vmhba0:0:0:0".
- -Datastore [Datastore[]] (Required) Specifies the datastores for which you want to retrieve the SCSI devices. This parameter is supported only for VMFS volumes.
- -Hba [Hba[]] (Required) Specifies the storage adapters for which you want to retrieve the SCSI devices.
- -Id [String[]] (Required) Specifies the IDs of the SCSI devices that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Key [String[]] (Optional) Specifies the linkable identifiers of the SCSI devices you want to retrieve.
- -LunType [String[]] (Optional) Specifies the type of the SCSI devices you want to retrieve. The following types are valid:   cdrom communications disk enclosure mediaChanger opticalDevice printer processor scanner storageArrayController tape unknown worm
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VmHost [VMHost[]] (Required) Specifies the hosts from which you want to retrieve the virtual SCSI devices.

**Examples:**

```powershell
Get-ScsiLun -VMHost 10.23.123.100 -LunType disk
```
_Retrieves the SCSI devices of "disk" type for the virtual machine host with an IP address 10.23.123.100._

```powershell
Get-VMHost | Get-ScsiLun -CanonicalName "naa.*"
```
_Retrieves the SCSI devices with canonical names that starts with "naa." on the provided host._

```powershell
$hba = Get-VMHost | Get-VMHostHba -Type ParallelScsi

Get-ScsiLun -Hba $hba -LunType disk
```
_Retrieves the SCSI devices of "disk" type for the specified HBA devices._

### `Get-ScsiLunPath`

**This cmdlet retrieves the list of vmhba paths to a specified SCSI device.**

**Parameters:**

- -Name [String[]] (Optional) Specifies the name of the SCSI device whose vmhba paths you want to retrieve.
- -ScsiLun [ScsiLun[]] (Required) Specifies the SCSI device whose vmhba paths you want to retrieve.

**Examples:**

```powershell
$scsilun = Get-ScsiLun -VMHost 10.23.123.100 -LunType disk

Get-ScsiLunPath $scsilun
```
_Retrieves the vmhba path to the specified SCSI device._

### `Get-Snapshot`

**This cmdlet retrieves the virtual machine snapshots available on a vCenter Server system.**

This cmdlet returns information about the snapshots that correspond to the filter criteria provided by the Name and VM parameters. The disk size of the snapshots is retrieved only if you have the "Datastore/Browse datastore" privilege to the datastore where the shapshot is located. Otherwise, the following message is displayed: "Unable to populate snapshot size due to unsufficient permissions."

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the snapshots you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the snapshots you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines whose snapshots you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing scripts on future PowerCLI versions, specify the parameter by name.

**Examples:**

```powershell
Get-Snapshot -VM VM -Name 'Before ServicePack 2'
```
_Retrieves the snapshot named "Before ServicePack2" of the VM virtual machine._

### `Get-UsbDevice`

**This cmdlet retrieves the USB devices available on a vCenter Server system.**

This cmdlet retrieves the USB devices available on a vCenter Server system. The cmdlet returns a set of virtual USB devices assigned to the virtual machines, templates, and snapshots specified by the  VirtualMachine, Template, and Snapshot parameters. At least one of these parameters must be provided. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Id [String[]] (Optional) Specifies the IDs of the USB devices you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the USB devices you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Snapshot [Snapshot[]] (Optional) Specifies the virtual machine snapshots whose virtual USB you want to retrieve. Supported only on vCenter Server 4.1 and ESX 4.1 and later.
- -Template [Template[]] (Optional) Specifies the virtual machine templates whose virtual USB drives you want to retrieve.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines whose virtual USB drives you want to retrieve.

**Examples:**

```powershell
Get-UsbDevice -VM (Get-VM -Location Host)
```
_Retrieves the USB devices attached to the virtual machines on the Host host._

### `Get-VAIOFilter`

**This cmdlet returns a list of VAIOFilter objects filtered by the specified parameters.**

This cmdlet returns a list of VAIOFilter objects filtered by the specified parameters. If no parameters are specified, the cmdlet returns all filters installed on all default servers.

**Parameters:**

- -Cluster [Cluster[]] (Optional) Specifies the clusters on which to search for VAIO filters.
- -Id [String[]] (Required) Filters the VAIO filters by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the name of the VAIO filter you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-VAIOFilter -Name "MyVAIOFilter"
```
_Retrieves all VAIO filters named "MyVAIOFilter"._

```powershell
Get-VAIOFilter -Name "MyVAIOFilter" -Cluster $cluster
```
_Retrieves the VAIO filter named "MyVAIOFilter" from the $cluster cluster._

```powershell
Get-VAIOFilter -Id "MyVAIOFilterId"
```
_Retrieves all VAIO filters with ID "MyVAIOFilterId"._

### `Get-VApp`

**This cmdlet retrieves vApps.**

**Parameters:**

- -Id [String[]] (Required) Specifies the IDs of the vApps that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Location [VIContainer[]] (Optional) Specifies Folder, Cluster, Datacenter, VMHost, and ResourcePool objects you want to search for vApps.
- -Name [String[]] (Optional) Specifies the names of the vApps that you want to retrieve.
- -NoRecursion [SwitchParameter] (Optional) Indicates that you want to deactivate the recursive behavior of the command.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Tag [Tag[]] (Optional) Returns only the vApps that are associated with any of the specified tags.

**Examples:**

```powershell
Get-ResourcePool MyResourcePool1 | Get-VApp -NoRecursion
```
_Retrieves all the vApps in the ResourcePool resource pool with no recursion._

### `Get-VDBlockedPolicy`

**This cmdlet retrieves the blocking policy for distributed ports.**

This cmdlet retrieves the blocking policy for distributed ports. For distributed port group and vSphere distributed switch parameter sets, the default port policy at the distributed port group or switch level is retrieved.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPort [VDPort[]] (Required) Specifies the distributed ports for which you want to retrieve the blocking policy.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies a distributed port group for which you want to retrieve the default blocking policy.
- -VDSwitch [VDSwitch[]] (Required) Specifies a vSphere distributed switch for which you want to retrieve the default blocking policy.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDBlockedPolicy
```
_Retrieves the blocking policy of a vSphere distributed switch named "MyVDSwitch"._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDPort | Get-VDBlockedPolicy
```
_Retrieves the blocking policies of all ports inside a distributed port group named "MyVDPortgroup"._

### `Get-VDUplinkLacpPolicy`

**This cmdlet retrieves the Link Aggregation Control Protocol policy for uplink ports.**

This cmdlet retrieves the Link Aggregation Control Protocol policy for uplink ports. For uplink port group and vSphere distributed switch parameter sets, the default port policy at the uplink port group or switch level is retrieved.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPort [VDPort[]] (Required) Specifies the uplink port for which you want to retrieve the Link Aggregation Control Protocol policy.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies an uplink port group for which you want to retrieve the default Link Aggregation Control Protocol policy.
- -VDSwitch [VDSwitch[]] (Required) Specifies a vSphere distributed switch for which you want to retrieve the default Link Aggregation Control Protocol policy.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDUplinkLacpPolicy
```
_Retrieves the Link Aggregation Control Protocol policy of a vSphere distributed switch named "MyVDSwitch"._

```powershell
Get-VDSwitch "MyVDSwitch" | Get-UplinkPortgroup "MyVDPortgroup" | Get-VDUplinkLacpPolicy
```
_Retrieves the Link Aggregation Control Protocol policy of an uplink port group named "MyUplinkPortgroup" inside a vSphere distributed switch named "MyVDSwitch"._

### `Get-VDUplinkTeamingPolicy`

**This cmdlet retrieves the uplink teaming policy for distributed ports.**

This cmdlet retrieves the uplink teaming policy for distributed ports. For distributed port group and vSphere distributed switch parameter sets, the default port policy at the distributed port group or switch level is retrieved.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VDPort [VDPort[]] (Required) Specifies the distributed port for which you want to retrieve the uplink teaming policy.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies a distributed port group for which you want to retrieve the default uplink teaming policy.
- -VDSwitch [VDSwitch[]] (Required) Specifies a vSphere distributed switch for which you want to retrieve the default uplink teaming policy.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDUplinkTeamingPolicy
```
_Retrieves the uplink teaming policy of a vSphere distributed switch named "MyVDSwitch"._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDPort | Get-VDUplinkTeamingPolicy
```
_Retrieves the uplink teaming policy of all ports inside a distributed port group named "MyVDPortgroup"._

### `Get-VasaProvider`

**This cmdlet retrieves the list of VASA providers that are currently registered with Storage Manager.**

**Parameters:**

- -Id [String[]] (Required) Filters the retrieved providers by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Filters the retrieved providers by name.
- -Refresh [SwitchParameter] (Optional) Synchronizes the providers before retrieving data. The operation is synchronous.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StorageContainer [VvolStorageContainer[]] (Optional) Filters the retrieved VASA providers by the Virtual Volume (vVol) storage containers. You can retrieve the storage container objects by using the Get-VvolStorageContainer cmdlet.

**Examples:**

```powershell
Get-VasaProvider -Name "MyProvider"
```
_Retrieves all VASA providers named "MyProvider"._

```powershell
Get-VasaProvider -Name "MyProvider" -Refresh
```
_Synchronizes the providers and retrieves the VASA provider named "MyProvider"._

```powershell
Get-VasaProvider -Id "MyProviderId"
```
_Retrieves all VASA providers with an ID set to "MyProviderId"._

## Mount

### `Mount-Tools`

**This cmdlet mounts the VMware Tools CD installer as a CD-ROM on the guest operating system.**

This cmdlet mounts the VMware Tools CD installer as a CD-ROM on the guest operating system that is specified by the Guest or VM parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Guest [VMGuest[]] (Optional) Specifies the guest operating systems on which you want to mount VMware Tools.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine[]] (Optional) Specifies the virtual machines on which you want to mount VMware Tools.

**Examples:**

```powershell
Mount-Tools VM
```
_Mounts the VMware Tools on the specified virtual machine. The virtual machine must be powered on._

```powershell
Get-VMGuest VM | Mount-Tools
```
_Mounts the VMware Tools on the virtual machine specified by its guest operating system. The virtual machine must be powered on._

## Move

### `Move-VApp`

**This cmdlet moves the specified virtual appliances to a new location.**

This cmdlet moves the specified vApps to a new location. If the destination is a host or a cluster, the vApps are moved to the system "Resources" resource pool.

**Parameters:**

- -Destination [VIContainer] (Required) Specifies where you want to move the specified vApps. Supported types are Folder, VMHost, Cluster, ResourcePool, VApp, and Datacenter.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VApp [VApp[]] (Required) Specifies the vApps you want to move.

**Examples:**

```powershell
$vmHost = Get-VMHost -Name "MyVMHost1"
$myDestinationRP = New-ResourcePool -Name "vApp ResourcePool" -Location $vmHost
Move-VApp -VApp (Get-Vapp -Name "MyVApp1" -Location $vmHost) -Destination $myDestinationRP
```
_Moves a vApp from a host to a resource pool from the same host._

```powershell
$vmHost = Get-VMHost -Name "MyVMHost1"
$myDestinationVApp = New-VApp -Name "MyvApp1" -Location $vmHost
(Get-Vapp -Name "MyvApp2" -Location (Get-ResourcePool -Name "MyResourcePool1") | Move-VApp -Destination $myDestinationVApp
```
_Moves a vApp from a resource pool to another vApp._

```powershell
Move-VApp -Name "MyvApp1" (Get-VMHost -Name "MyVMHost1")
```
_Moves a vApp from a resource pool to a host._

## New

### `New-AdvancedSetting`

**This cmdlet creates a new advanced setting for the specified entity.**

**Parameters:**

- -Entity [VIObject] (Required) Specifies the entity for which you want to create a new advanced setting. This parameter accepts VIServer, VirtualMachine, DatastoreCluster, and Cluster objects. Passing multiple values to this parameter is obsolete.
- -Force [SwitchParameter] (Optional) Indicates that you want to create the new advanced setting even if another setting with the same name exists for the specified object type.
- -Name [String] (Required) Specifies a name for the advanced setting.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Type [AdvancedSettingType] (Optional) Specifies the type of the new advanced setting.
- -Value [Object] (Required) Specifies a value for the advanced setting.

**Examples:**

```powershell
New-AdvancedSetting -Entity (Get-Cluster -Name Cluster) -Name SettingName -Value SettingValue -Type ClusterHA
```
_Creates a new advanced setting for the Cluster cluster - of type CLusterHA, with name SettingName and value SettingValue._

### `New-CDDrive`

**This cmdlet creates a new virtual CD drive.**

This cmdlet creates a new virtual CD drive for each of the provided virtual machines. If an ISO location is provided, sets the CD to point to the ISO.

**Parameters:**

- -ContentLibraryIso [ContentLibraryItem] (Required) Specifies the content library item of type ISO that you want to mount on the new CD drive.
- -HostDevice [String] (Optional) Specifies the path to the CD drive on the virtual machine host that backs the virtual CD drive. Do not set this parameter if the ISOPath parameter is set.
- -IsoPath [String] (Optional) Specifies the datastore path to the ISO (CD image) file that backs the virtual CD drive. Do not set this parameter if the HostDevice parameter is set.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StartConnected [SwitchParameter] (Optional) Indicates that the virtual CD drive starts connected when the virtual machine associated with it powers on.
- -VM [VirtualMachine] (Required) Specifies the virtual machine to which the new virtual CD drive belongs. Passing multiple values to this parameter is obsolete.

**Examples:**

```powershell
New-CDDrive -VM $vm -ISOPath "Path_to_ISO\test.iso"
```
_Creates a CD drive on the specified virtual machine and attach an ISO image to it._

### `New-CnsKubernetesEntityMetadata`

**This cmdlet creates a Cloud Native Storage (CNS) Kubernetes entity metadata at a client side.**

**Parameters:**

- -CnsKubernetesEntityReference [CnsKubernetesEntityReference] (Required) Specifies the Kubernetes entity to which you want to refer. For example, a persistent volume claim (PVC) refers to a persistent volume (PV), a POD refers to one or more PVCs, and so on. An entity might not refer to anything. For example, a PV does not refer to a PVC, and so on.
- -EntityName [String] (Required) Specifies the name of the entity.
- -EntityType [String] (Required) Specifies the type of the entity in Kubernetes.
- -KubernetesClusterId [String] (Required) Specifies the container orchestrator Kubernetes cluster to which the entity belongs.
- -Label [Hashtable] (Optional) Specifies the labels for this entity. A maximum of 32 labels are supported for each entity. The label key should be less than 320 bytes and the value should be less than 64 bytes.
- -Namespace [String] (Optional) Specifies the namespace in Kubernetes to which the entity belongs.

**Examples:**

```powershell
New-CnsKubernetesEntityMetadata -EntityType Pod -Namespace 'default' -CnsKubernetesEntityReference $refer1 -KubernetesClusterId 'k8_cls_1' -EntityName 'myVolumePod' -Label $label
```
_Creates a CNS Kubernetes entity metadata with POD as an entity type, "default" as a namespace, $refer1 as a CNS Kubernetes entity reference, 'k8_cls_1' as a Cluster ID, 'myVolumePod' as an entity name, and $label as a label._

### `New-CnsKubernetesEntityReference`

**This cmdlet creates a Cloud Native Storage (CNS) Kubernetes entity reference at the client side.**

**Parameters:**

- -EntityName [string] (Required) Specifies the name of the entity.
- -EntityType [CnsKubernetesEntityType] (Required) Specifies the type of the entity.
- -KubernetesClusterId [string] (Optional) Specifies the Kubernetes cluster to which the entity belongs.
- -Namespace [string] (Optional) Specifies the namespace in Kubernetes to which the entity belongs, if applicable. You must not set the namespace for an entity of type persistent volume. You  must set it for entities of type persistent volume claim and POD.

**Examples:**

```powershell
New-CnsKubernetesEntityReference -EntityName 'myVolumePVC' -EntityType PersistentVolumeClaim
```
_Creates a CNS Kubernetes entity reference with 'myVolumePVC' as an entity name and PersistentVolumeClaim as an entity type._

### `New-FloppyDrive`

**This cmdlet creates a new virtual floppy drive.**

This cmdlet creates a new virtual floppy drive for each of the provided virtual machines. If a floppy image path is provided, sets the floppy drive to point to the image. If both the FloppyImagePath and HostDevice parameters are specified, an error is generated.

**Parameters:**

- -FloppyImagePath [String] (Optional) Specifies the datastore path to the floppy image file backing the virtual floppy drive. Do not use this parameter together with the HostDevice parameter.
- -HostDevice [String] (Optional) Specifies the path to the floppy drive on the host which will back this virtual floppy drive. Do not use this parameter together with the FloppyImagePath parameter.
- -NewFloppyImagePath [String] (Optional) Specifies a new datastore path to a floppy image file backing the virtual floppy drive. Do not use this parameter together with the HostDevice parameter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StartConnected [SwitchParameter] (Optional) Indicates that the virtual floppy drive starts connected when its associated virtual machine powers on.
- -VM [VirtualMachine] (Required) Specifies the virtual machine to which you want to attach the new virtual floppy drive. Passing multiple values to this parameter is obsolete.

**Examples:**

```powershell
New-FloppyDrive -VM VM -HostDevice '/dev/fd0' -StartConnected
```
_Creates a floppy drive backed by the client device /dev/fd0 and sets it to start connected when the virtual machine is powered on._

### `New-KmipClientCertificate`

**This cmdlet creates a new self-signed certificate or certificate-signing request for the key management server cluster.**

**Parameters:**

- -CertificateSigningRequest [SwitchParameter] (Optional) Indicates whether a certificate-signing request should be retrieved. This certificate-signing request should be signed by the key management server and uploaded to the vCenter Server system.
- -FilePath [String] (Optional) Specifies the file path to which you want to export the self-signed certificate or certificate-signing request.
- -KeyProvider [KeyProvider] (Required) Specifies the key provider for which you want to use the certificate as a client certificate.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer cmdlet.

**Examples:**

```powershell
New-KmipClientCertificate -KeyProvider $keyProvider
```
_Creates a self-signed client certificate for the $keyProvider key provider._

```powershell
New-KmipClientCertificate -KeyProvider $keyProvider -CertificateSigningRequest -FilePath $filePath
```
_Creates a certificate-signing request for the $keyProvider key provider and exports it to the $filePath file path._

### `New-NetworkAdapter`

**This cmdlet creates a new virtual network adapter.**

This cmdlet creates a new virtual network adapter for each of the provided virtual machines and sets the optional properties if provided.

**Parameters:**

- -DeviceProtocol [VrdmaDeviceProtocol] (Optional) Specifies the device protocol for a Vmxnet3Vrdma adapter. If omitted, the server applies a default value.
- -DistributedSwitch [DistributedSwitch] (Required) Specifies a virtual switch to which you want to connect the network adapter.
- -MacAddress [String] (Optional) Specifies an optional MAC address for the new virtual network adapter.
- -NetworkName [String] (Required) Specifies the name of the network to which you want to add the new virtual network adapter. Specifying a distributed port group name is obsolete. Use the Portgroup parameter instead.
- -PhysicalFunction [String] (Optional) Specifies the PCI ID of the physical device, backing a SriovEthernetCard adapter. If omitted, automatic mode is used for the physical function.
- -Portgroup [VirtualPortGroupBase] (Required) Specifies a standard or a distributed port group to which you want to connect the new network adapter.
- -PortId [String] (Required) Specifies the port of the specified distributed switch to which you want to connect the network adapter. Use this parameter only if the DistributedSwitch parameter is specified.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StartConnected [SwitchParameter] (Optional) Indicates that the virtual network adapter starts connected when the virtual machine associated with it powers on.
- -Type [VirtualNetworkAdapterType] (Optional) Specifies the type of the new network adapter. The valid types are e1000, Flexible, Vmxnet, EnhancedVmxnet, Vmxnet3, SriovEthernetCard, Vmxnet3Vrdma, and Unknown. If no value is given to the parameter, the new network adapter is of the type recommended by VMware for the given guest OS.
- -VM [VirtualMachine] (Required) Specifies the virtual machine to which you want to attach the new virtual network adapter. Passing multiple values to this parameter is obsolete.
- -WakeOnLan [SwitchParameter] (Optional) Indicates that wake-on-LAN is enabled on the newly created virtual network adapter.

**Examples:**

```powershell
Get-VM VM | New-NetworkAdapter  -NetworkName "VM Network" -MacAddress '00:50:56:a1:00:00' -WakeOnLan -StartConnected -Type EnhancedVmxnet
```
_Create a virtual network adapter with the specified parameters._

```powershell
$myVm = Get-VM -Name MyVM
$MyVDPortgroup = Get-VDPortgroup -Name MyVDPortGroup
New-NetworkAdapter -VM $myVM -Portgroup $MyVDPortgroup
```
_Adds a new network adapter to the specified virtual machine and connects it to the specified distributed port group._

```powershell
$myVM = Get-VM -Name MyVM
$MyVDSwitch = Get-VDSwitch -Name MyVDSwitch
New-NetworkAdapter -VM $myVM -DistributedSwitch $MyVDSwitch -PortId 100
```
_Adds a new network adapter to the specified virtual machine and connects it to the specified port on the specified vSphere distributed switch._

### `New-ScsiController`

**This cmdlet creates a new SCSI controller.**

**Parameters:**

- -BusSharingMode [ScsiBusSharingMode] (Optional) Specifies the bus sharing mode of the SCSI controller. The valid values are NoSharing, Physical, and Virtual.
- -HardDisk [HardDisk] (Required) Specifies the hard disk you want to attach to the new SCSI controller. Passing multiple values to this parameter is obsolete.
- -Type [ScsiControllerType] (Optional) Specifies the type of the SCSI controller. The valid values are ParaVirtual, VirtualBusLogic, VirtualLsiLogic, and VirtualLsiLogicSAS.

**Examples:**

```powershell
$vm = Get-VM VM | New-HardDisk -CapacityKB 10485760 | New-ScsiController
```
_Creates a new 10GB hard disk and a new SCSI controller with default values for the BusSharingMode and Type properties._

```powershell
$disk = Get-HardDisk -VM VM | Select -First 2
$disk | New-ScsiController -BusSharingMode Physical -Type VirtualLsiLogicSAS
```
_Creates for the first two hard disks of VM a new SCSI controller of VirtualLsiLogicSAS type and with Physical bus sharing mode._

### `New-Snapshot`

**This cmdlet creates a new snapshot of a virtual machine.**

This cmdlet creates a new snapshot of a virtual machine with the provided inputs.

**Parameters:**

- -Description [String] (Optional) Provide a description of the new snapshot.
- -Memory [SwitchParameter] (Optional) If the value is $true and if the virtual machine is powered on, the virtual machine's memory state is preserved with the snapshot.
- -Name [String] (Required) Specifies a name for the new snapshot.
- -Quiesce [SwitchParameter] (Optional) If the value is $true and the virtual machine is powered on, VMware Tools are used to quiesce the file system of the virtual machine. This assures that a disk snapshot represents a consistent state of the guest file systems. If the virutal machine is powered off or VMware Tools are not available, the Quiesce parameter is ignored.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VM [VirtualMachine] (Required) Specifies the virtual machine you want to snapshot. Passing multiple values to this parameter is obsolete.

**Examples:**

```powershell
New-Snapshot -VM VM -Name BeforePatch
```
_Creates a new snapshot of the VM virtual machine named BeforePatch._

```powershell
New-Snapshot -VM VM2 -Name PoweredOnVM -Memory $true
```
_Creates a new snapshot of the VM2 powered-on virtual machine and preserves its memory state._

### `New-VAIOFilter`

**This cmdlet installs a VAIO filter on the specified cluster.**

This cmdlet installs a VAIO filter on the specified cluster. The SPBM metadata of the VAIO filter might not appear immediately in the list of capabilities.

**Parameters:**

- -Cluster [Cluster] (Required) Specifies the cluster on which to install the VAIO filter.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VibUrl [String] (Required) Specifies the URL that points to the VAIO filter VIB package. The accepted formats are HTTP and HTTPS.

**Examples:**

```powershell
New-VAIOFilter -Cluster $cluster -VibUrl "MyVibUrl"
```
_Installs a new VAIO filter defined by "MyVibUrl" on the $cluster cluster._

### `New-VApp`

**This cmdlet creates a new vApp.**

**Parameters:**

- -ContentLibraryItem [ContentLibraryItem] (Required) Specifies the content library template to deploy the vApp from.
- -CpuExpandableReservation [Boolean] (Optional) Indicates that the CPU reservation can grow beyond the specified value if there are available resources.
- -CpuLimitMhz [Int64] (Optional) Specifies a CPU usage limit in MHz. Utilization will not exceed this limit even if there are available resources.
- -CpuReservationMhz [Int64] (Optional) Specifies the CPU size in MHz that is guaranteed to be available.
- -CpuSharesLevel [SharesLevel] (Optional) Specifies the CPU allocation level for this vApp. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal.
- -Datastore [Datastore] (Optional) Specifies the datastore where you want to store the copied vApp. If you do not specify a datastore, the cmdlet takes the first datastore of the host or cluster.
- -DiskStorageFormat [VirtualDiskStorageFormat] (Optional) Specifies the storage format of the disks of the vApp.
- -InventoryLocation [FolderContainer] (Optional) Specifies a datacenter or a virtual machine folder where you want to place the new vApp.
- -Location [VIContainer] (Required) Specifies a VApp, ResourcePool, VMHost, or Cluster object where you want to place the new vApp.
- -MemExpandableReservation [Boolean] (Optional) If the value is $true, the memory reservation can grow beyond the specified value if there are available resources.
- -MemLimitGB [Decimal] (Optional) Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemLimitMB [Int64] (Optional) This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemReservationGB [Decimal] (Optional) Specifies the guaranteed available memory in gigabytes (GB).
- -MemReservationMB [Int64] (Optional) This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB).
- -MemSharesLevel [SharesLevel] (Optional) Specifies the memory allocation level for this vApp. This property is used in relative allocation between resource consumers. The valid values are Custom, High, Low, and Normal.
- -Name [String] (Required) Specifies a name for the new vApp.
- -NumCpuShares [Int32] (Optional) Specifies the CPU allocation level for this vApp. This property is used in relative allocation between resource consumers. This parameter is ignored unless the CpuSharesLevel parameter is set to Custom.
- -NumMemShares [Int32] (Optional) Specifies the memory allocation level for this vApp. This property is used in relative allocation between resource consumers. This parameter is ignored unless the MemSharesLevel parameter is set to Custom.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the Center Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VApp [VApp] (Required) Specifies a vApp you want to copy.
- -VMHost [VMHost] (Optional) Specifies the host where you want to run the copied vApp.

**Examples:**

```powershell
New-VApp -Name MyVApp1 -CpuLimitMhz 4000 -CpuReservationMhz 1000 -Location MyVMHost1
```
_Creates a new vApp on the MyVMHost1 host._

### `New-VasaProvider`

**This cmdlet registers a VASA provider.**

**Parameters:**

- -Certificate [String] (Optional) Specifies the VASA provider certificate.
- -Credential [PSCredential] (Optional) Specifies credentials in the form of a PSCredential object. The Username and Password parameter pair is an alternative to the Credential parameter. If sufficient information about user and password, or credential is not specified, the cmdlet provides a credential prompt.
- -Description [String] (Optional) Specifies the description of the provider.
- -Force [SwitchParameter] (Optional) Forces the server to trust the provider and store the provider certificate for future reference. If not set, the server throws error in case the provider certificate is not in the list of trusted certificates.
- -Name [String] (Required) Specifies the name of the provider. The maximum length of the name is 80 characters. If not specified, a default name based on the provider namespace and ID is used.
- -Password [SecureString] (Optional) Specifies the password for connecting to a provider. The maximum length of the password is 255 characters. The Username and Password parameter pair is an alternative to the Credential parameter. If sufficient information about user and password, or credential is not specified, the cmdlet provides a credential prompt. This parameter is of type SecureString but it also accepts objects of type System.String.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Url [String] (Required) Specifies the URL of the VASA provider service.
- -Username [String] (Optional) Specifies the user name for connecting to a provider. The maximum length of the user name is 255 characters. The Username and Password parameter pair is an alternative to the Credential parameter. If sufficient information about user and password, or credential is not specified, the cmdlet provides a credential prompt.

**Examples:**

```powershell
New-VasaProvider -Name "MyProvider" -Username "UserName" -Password "Password" -Url "MyUrl"
```
_Registers a VASA provider running at "MyUrl" with the Storage Monitoring Service._

```powershell
New-VasaProvider -Name "MyProvider" -Credential "MyCredential" -Url "MyUrl" -Force
```
_Registers a VASA provider by using the "MyCredential" credential and forcing the Storage Monitoring Service to accept the certificate of the provider._

## Other

### `TabExpansion2`

**TabExpansion2 [-inputScript] <string> [-cursorColumn] <int> [[-options] <hashtable>] [<CommonParameters>]**

**Parameters:**

- -ast [Ast] (Required) 
- -cursorColumn [int] (Required) 
- -inputScript [string] (Required) 
- -options [hashtable] (Optional) 
- -positionOfCursor [IScriptPosition] (Required) 
- -tokens [Token[]] (Required) 

## Remove

### `Remove-AdvancedSetting`

**This cmdlet removes the specified advanced setting.**

**Parameters:**

- -AdvancedSetting [AdvancedSetting[]] (Required) Specifies the advanced settings you want to remove.   Note: You can only remove advanced settings from virtual machines in ESXi or vCenter Server environments version 5.5 or later.

**Examples:**

```powershell
Get-AdvancedSetting -Entity (Get-Cluster -Name Cluster) | Remove-AdvancedSetting -Confirm:$false
```
_Removes the advanced settings of the cluster named Cluster._

### `Remove-CDDrive`

**This cmdlet removes virtual CD drives from their locations.**

**Parameters:**

- -CD [CDDrive[]] (Required) Specifies the virtual CD drives you want to remove.

**Examples:**

```powershell
$cd = Get-CDDrive -VM $vm

Remove-CDDrive -CD $cd
```
_Removes all CD drives for the specified virtual machines and templates._

### `Remove-FloppyDrive`

**This cmdlet removes the virtual floppy drives from their locations.**

**Parameters:**

- -Floppy [FloppyDrive[]] (Required) Specifies the virtual floppy drives you want to remove.

**Examples:**

```powershell
$floppy = Get-FloppyDrive -VM VM

Remove-FloppyDrive -Floppy $floppy
```
_Removes the floppy drive of the virtual machine named VM._

### `Remove-NetworkAdapter`

**This cmdlet removes the virtual network adapters from their locations.**

**Parameters:**

- -NetworkAdapter [NetworkAdapter[]] (Required) Specifies the virtual network adapters you want to remove.

**Examples:**

```powershell
$nic = Get-NetworkAdapter -VM VM

Remove-NetworkAdapter -NetworkAdapter $nic
```
_Removes the network adapter of the VM virtual machine._

### `Remove-PassthroughDevice`

**This cmdlet removes the specified pass-through devices.**

This cmdlet removes the specified pass-through devices. You can remove only those pass-through devices that are retrieved from virtual machines.

**Parameters:**

- -PassthroughDevice [PassThroughDevice[]] (Required) Specifies the pass-through devices you want to remove. You can remove only those pass-through devices that are retrieved from virtual machines.

**Examples:**

```powershell
Get-PassthroughDevice -VM VM | Remove-PassthroughDevice
```
_Removes all pass-through devices of the VM virtual machine._

### `Remove-Snapshot`

**This cmdlet removes the specified virtual machine snapshots.**

This cmdlet removes the specified virtual machine snapshots. If the value of the RemoveChildren parameter is $true, the cmdlet removes the child snapshots as well.

**Parameters:**

- -RemoveChildren [SwitchParameter] (Optional) Indicates that you want to remove the children of the specified snapshots as well.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Snapshot [Snapshot[]] (Required) Specifies the snapshots you want to remove.

**Examples:**

```powershell
Remove-Snapshot -Snapshot $snapshot1 -RemoveChildren
```
_Removes the snapshot in the $snapshot variable and its children._

### `Remove-UsbDevice`

**This cmdlet removes the specified USB devices from a virtual machine.**

**Parameters:**

- -UsbDevice [UsbDevice[]] (Required) Specifies the USB devices you want to remove.

**Examples:**

```powershell
Get-UsbDevice -VM (Get-VM -Location $vmhost) | Remove-UsbDevice
```
_Retrieves the virtual machines on the host stored in the $vmhost variable and removes their USB devices._

### `Remove-VAIOFilter`

**This cmdlet uninstalls VAIO filters from the clusters on which they are installed.**

This cmdlet uninstalls VAIO filters from the clusters on which they are installed. In case of failure, the exception references to the VAIOFilter as target object.

**Parameters:**

- -Filter [VAIOFilter[]] (Required) Specifies the VAIO filter to be uninstalled from the cluster.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-VAIOFilter -Filter $filter -Confirm:$false
```
_Uninstalls the $filter VAIO filter from the cluster it is installed on without asking for user confirmation._

### `Remove-VApp`

**This cmdlet removes vApps from the server.**

**Parameters:**

- -DeletePermanently [SwitchParameter] (Optional) Indicates that you want not only to remove the vApps from the inventory, but also to delete the virtual machines they contain from the datastore.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VApp [VApp[]] (Required) Specifies the vApp you want to remove.

**Examples:**

```powershell
Get-VMHost -Name MyVMHost1 | Get-VApp | Remove-VApp
```
_Retrieves and removes all vApps available on the MyVMHost1 host._

### `Remove-VasaProvider`

**This cmdlet unregisters the specified VASA providers.**

**Parameters:**

- -Provider [VasaProvider[]] (Required) Specifies the VASA provider you want to unregister. If not specified, all providers are unregistered.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-VasaProvider -Provider $provider -Confirm:$false
```
_Unregisters the $provider VASA provider from the Storage Monitoring Service without asking for confirmation._

## Set

### `Set-AdvancedSetting`

**This cmdlet modifies the specified advanced setting.**

**Parameters:**

- -AdvancedSetting [AdvancedSetting[]] (Required) Specifies the advanced setting you want to modify.
- -Value [Object] (Required) Specifies a new value for the advanced setting.

**Examples:**

```powershell
Get-AdvancedSetting -Entity (Get-Cluster -Name Cluster) -Name SettingName | Set-AdvancedSetting -Value NewValue
```
_Changes the value of the advanced setting SettingName of the Cluster cluster._

```powershell
Get-AdvancedSetting -Entity Server -Name 'mail.smtp.server' | Set-AdvancedSetting -Value 'test.vmware.com'
```
_Changes the value of the advanced setting mail.smtp.server of the specified server to test.vmware.com._

### `Set-CDDrive`

**This cmdlet modifies the configuration of a virtual CD drive.**

This cmdlet updates a virtual CD drive. If an ISO location is provided, sets the CD to point to the ISO. Changes the StartConnected and Connected flags if StartConnected and/or Connected is set. If NoMedia parameter is set to $true, removes the CD drive's media backing and disconnects it. Note that the Connected parameter can be specified only if the corresponding virtual machine is powered on.

**Parameters:**

- -CD [CDDrive[]] (Required) Specifies the virtual CD drive you want to configure.
- -Connected [Boolean] (Optional) Indicates that the virtual CD drive is connected after its creation. This parameter can be specified only if the corresponding virtual machine is powered on.
- -HostDevice [String] (Optional) Specifies the path to the CD drive on the host which backs this virtual CD drive. Do not use this parameter when the ISOPath and NoMedia parameters are specified.
- -IsoPath [String] (Optional) Specifies the datastore path to the ISO (CD image) file that backs the virtual CD drive. Do not use this parameter when the HostDevice and NoMedia parameters are specified.
- -NoMedia [SwitchParameter] (Optional) Indicates that you want to detach from the CD drive any type of connected media - ISO from datastore or host device. Do not use this parameter when the ISOPath or HostDevice parameters are specified.
- -StartConnected [Boolean] (Optional) Indicates that the virtual CD drive starts connected when the virtual machine associated with it powers on.

**Examples:**

```powershell
$cd = New-CDDrive -VM VM -ISOPath "[sof-20666-esx:storage1] ISO\testISO.iso"

Set-CDDrive -CD $cd -NoMedia
```
_Creates a CD drive on the VM virtual machine and attaches testISO.iso, previously uploaded. Then disconnects the ISO._

### `Set-FloppyDrive`

**This cmdlet modifies the configuration of the specified virtual floppy drive.**

This cmdlet modifies the configuration of the specified virtual floppy drive. If a floppy image path is provided, the cmdlet sets the floppy drive to point to the image. Also, the cmdlet updates the StartConnected and Connected properties. If the value of the NoMedia parameter is $true, the cmdlet removes the floppy drive's media backing and disconnects it. The FloppyImagePath, HostDevice, and NoMedia parameters cannot be used together. The Connected parameter can be specified only if the corresponding virtual machine is powered on.

**Parameters:**

- -Connected [Boolean] (Optional) If the value is $true, the virtual floppy drive is connected after its creation. If the value is $false, the floppy drive is disconnected. This parameter can be specified only if the corresponding virtual machine is powered on.
- -Floppy [FloppyDrive[]] (Required) Specifies the virtual floppy drive you want to configure.
- -FloppyImagePath [String] (Optional) Specifies the datastore path to the floppy image file that backs the virtual floppy drive. Do not use this parameter when the HostDevice and NoMedia parameters are specified.
- -HostDevice [String] (Optional) Specifies the path to the floppy drive on the host that backs this virtual floppy drive. Do not use this parameter when the FloppyImagePath and NoMedia parameters are specified.
- -NoMedia [SwitchParameter] (Optional) Indicates that the floppy drive is to have no media (similar to removing the floppy from a physical drive). Do not use this parameter when the FloppyImagePath and HostDevice parameters are specified.
- -StartConnected [Boolean] (Optional) If the value is $true, the virtual floppy drive starts connected when its associated virtual machine powers on. If the value is $false, it starts disconnected.

**Examples:**

```powershell
Set-FloppyDrive -Floppy $floppy -StartConnected:$true
```
_Sets a floppy to start connected._

### `Set-NetworkAdapter`

**This cmdlet modifies the configuration of the virtual network adapter.**

This cmdlet modifies the configuration of the virtual network adapter. You can change the MAC address and the network name, and to configure the Connected, StartConnected, and WakeOnLan properties of the adapter.

**Parameters:**

- -Connected [Boolean] (Optional) If the value is $true, the virtual network adapter is connected after its creation. If the value is $false, it is disconnected.
- -DistributedSwitch [DistributedSwitch] (Required) Specifies a virtual switch to which you want to connect the network adapter.
- -MacAddress [String] (Optional) Specifies an optional MAC address for the virtual network adapter.
- -NetworkAdapter [NetworkAdapter[]] (Required) Specifies the virtual network adapter you want to configure.
- -NetworkName [String] (Optional) Specifies the name of the network to which you want to connect the virtual network adapter. Specifying a distributed port group name is obsolete. Use the Portgroup parameter instead.
- -Portgroup [VirtualPortGroupBase] (Required) Specifies a standard or a distributed port group to which you want to connect the network adapter.
- -PortId [String] (Required) Specifies the port of the virtual switch to which you want to connect the network adapter. Use this parameter only if the DistributedSwitch parameter is specified.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StartConnected [Boolean] (Optional) If the value is $true, the virtual network adapter starts connected when its associated virtual machine powers on. If the value is $false, it starts disconnected.
- -Type [VirtualNetworkAdapterType] (Optional) Specifies the type of the network adapter. The valid types are e1000, Flexible, Vmxnet, EnhancedVmxnet, and Vmxnet3, and Unknown.
- -WakeOnLan [Boolean] (Optional) Indicates that wake-on-LAN is enabled on the virtual network adapter.

**Examples:**

```powershell
Get-VM VM | Get-NetworkAdapter | Set-NetworkAdapter -MacAddress '00:50:56:a1:00:00' -WakeOnLan:$true
```
_Configures the  Mac address and the WakeOnLan setting of a virtual network adapter._

```powershell
Get-VM VM | Get-NetworkAdapter | Set-NetworkAdapter -Type EnhancedVmxnet
```
_Sets the type of the virtual network adapter._

```powershell
Get-VM VM | Get-NetworkAdapter | Set-NetworkAdapter -Connected:$true
```
_Sets the connection state of the virtual network adapter._

### `Set-ScsiController`

**This cmdlet modifies the specified SCSI controllers.**

This cmdlet modifies the specified SCSI controllers. Set-ScsiController cannot set both the Type and BusSharing parameters at the same time. First run the cmdlet to set the type and then run it again to configure the bus sharing mode.

**Parameters:**

- -BusSharingMode [ScsiBusSharingMode] (Optional) Specifies the bus sharing mode of the SCSI controller. The valid values are NoSharing, Physical, and Virtual.
- -ScsiController [ScsiController[]] (Required) Specifies the SCSI controller you want to modify.
- -Type [ScsiControllerType] (Optional) Specifies the type of the SCSI controller. The valid values are ParaVirtual, VirtualBusLogic, VirtualLsiLogic, and VirtualLsiLogicSAS.

**Examples:**

```powershell
Get-ScsiController -VM VM | Set-ScsiController -BusSharingMode Physical
```
_Configures the bus sharing mode of the SCSI controllers of a virtual machine to Physical mode._

```powershell
$scsiController = Get-HardDisk -VM VM | Select -First 1 | Get-ScsiController

Set-ScsiController -ScsiController $scsiController -Type VirtualLsiLogic
```
_Changes the type of the SCSI controller of the first hard disk of the VM virtual machine to VirtualLsiLogic._

### `Set-ScsiLun`

**This cmdlet modifies the configuration of a SCSI device.**

**Parameters:**

- -BlocksToSwitchPath [Int32] (Optional) Specifies the maximum number of I/O blocks that you want to issue on a given path before the system tries to select a different path. Modifying this setting affects all SCSI LUN devices that are connected to the same ESX/ESXi host. The default value is 2048.
- -CommandsToSwitchPath [Int32] (Optional) Specifies the maximum number of I/O requests that you want to issue on a given path before the system tries to select a different path. Modifying this setting affects all SCSI LUN devices that are connected to the same ESX host. The default value is 50. This parameter is not supported on vCenter Server 4.x.
- -DeletePartitions [SwitchParameter] (Optional) Removes all partitions from the SCSI disk. A confirmation prompt appears. If Force is specified, the confirmation prompt does not appear and partitions are removed.
- -Force [SwitchParameter] (Optional) Indicates that you want to suppress the prompt that appears when the DeletePartitions parameter is specified. If the Force parameter is specified, you are not asked for confirmation when deleting disk partitions.
- -IsLocal [Boolean] (Optional) Marks the SCSI disk as local or remote. If the value is $true, the SCSI disk is local. If the value is $false, the SCSI disk is remote.
- -IsLocatorLedOn [Boolean] (Optional) Turns the LED locator of a SCSI disk on or off.
- -IsSsd [Boolean] (Optional) Marks the SCSI disk as an SSD or HDD. If the value is $true, the SCSI disk is an SSD type. If the value is $false, the SCSI disk is an HDD type.
- -MultipathPolicy [ScsiLunMultipathPolicy] (Optional) Specifies the policy that the logical unit must use when choosing a path. The following values are valid:   Fixed - uses the preferred path whenever possible. RoundRobin - load balance. MostRecentlyUsed - uses the most recently used path. Unknown - supported only when connected to vCenter Server 4.1/ESX 4.1.   Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -NoBlocksSwitch [SwitchParameter] (Optional) This parameter is deprecated and scheduled for removal. Indicates that switching based on blocks is deactivated. Not supported on vCenter Server 4.x.
- -NoCommandsSwitch [SwitchParameter] (Optional) This parameter is deprecated and scheduled for removal. Indicates that switching based on commands is deactivated. Not supported on vCenter Server 4.x.
- -PreferredPath [ScsiLunPath] (Optional) Specifies the preferred path to access the SCSI logical unit. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -ScsiLun [ScsiLun[]] (Required) Specifies the SCSI device you want to configure.

**Examples:**

```powershell
$scsilun = Get-ScsiLun -VMHost 10.23.123.100 -LunType disk

Set-ScsiLun -ScsiLun $scsilun -CommandsToSwitchPath 100
```
_Configures the SCSI LUN device of the virtual machine host so that the maximum number of I/O requests that you want to issue before the system tries to select a different path is 100._

### `Set-ScsiLunPath`

**This cmdlet configures a vmhba path to a SCSI device.**

**Parameters:**

- -Active [Boolean] (Optional) Indicates that the specified path is active.
- -Preferred [SwitchParameter] (Optional) Indicates that the specified path is preferred. Only one path can be preferred, so when a path is made preferred, the preference is removed from the previously preferred path.
- -ScsiLunPath [ScsiLunPath[]] (Required) Specifies a path to the SCSI logical unit you want to configure.

**Examples:**

```powershell
$scsilun = Get-ScsiLun -VMHost 10.23.123.100 -LunType disk

$scsipath = Get-ScsiLunPath -ScsiLun $scsilun

Set-ScsiLunPath -ScsiLunPath $scsipath -Preferred $true
```
_Sets the specified SCSI Lun path as preferred._

### `Set-Snapshot`

**This cmdlet modifies the specified virtual machine snapshot.**

This cmdlet modifies the name and the description of the specified virtual machine snapshot.

**Parameters:**

- -Description [String] (Optional) Provides a new description for the snapshot.
- -Name [String] (Optional) Specifies a new name for the snapshot.
- -Snapshot [Snapshot[]] (Required) Specifies the snapshot whose properties you want to change.

**Examples:**

```powershell
Set-Snapshot -Snapshot $snapshot -Name BeforePatch -Description "Before windows update"
```
_Sets the name and the description of the snapshot in the $snapshot variable._

```powershell
Get-VM | Get-Snapshot -Name "InitialState" | Set-Snapshot -Description "This snapshot is created right after the OS installation."
```
_Updates the description of all snapshots with name InitialState, from all virtual machines._

### `Set-VAIOFilter`

**This cmdlet upgrades a VAIO filter on the cluster it is installed.**

This cmdlet upgrades a VAIO filter on the cluster it is installed. The updated SPBM metadata of the VAIO filter might not appear immediately in the list of capabilities. In case of failure, the exception contains a reference to the VAIO filter as a target object.

**Parameters:**

- -Filter [VAIOFilter[]] (Required) Specifies the VAIO filter to upgrade.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VibUrl [String] (Required) Specifies the URL that points to the VAIO filter VIB package. The accepted formats are HTTP and HTTPS.

**Examples:**

```powershell
Set-VAIOFilter -Filter $filter -VibUrl "NewVibUr"
```
_Updates the $filter VAIO filter and sets the VIB URL to "NewVibUrl". The version of the new VIB should be higher than the existing filter version._

### `Set-VApp`

**This cmdlet modifies the specified vApp.**

**Parameters:**

- -CpuExpandableReservation [Boolean] (Optional) Indicates that the CPU reservation can grow beyond the specified value if there are available resources.
- -CpuLimitMhz [Int64] (Optional) Specifies a CPU usage limit in MHz. If this parameter is set, utilization will not exceed this limit even if there are available resources.
- -CpuReservationMhz [Int64] (Optional) Specifies the guaranteed available CPU in MHz.
- -CpuSharesLevel [SharesLevel] (Optional) Specifies the CPU allocation level for this vApp. This property is used in relative allocation between resource consumers. This parameter accepts Custom, High, Low, and Normal values.
- -MemExpandableReservation [Boolean] (Optional) Indicates that the memory reservation can grow beyond the specified value if there are available resources.
- -MemLimitGB [Decimal] (Optional) Specifies a memory usage limit in gigabytes (GB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemLimitMB [Int64] (Optional) This parameter is obsolete. Use MemLimitGB instead. Specifies a memory usage limit in megabytes (MB). If this parameter is set, utilization will not exceed the specified limit even if there are available resources.
- -MemReservationGB [Decimal] (Optional) Specifies the guaranteed available memory in gigabytes (GB).
- -MemReservationMB [Int64] (Optional) This parameter is obsolete. Use MemReservationGB instead. Specifies the guaranteed available memory in megabytes (MB).
- -MemSharesLevel [SharesLevel] (Optional) Specifies the memory allocation level for the vApp. This property is used in relative allocation between resource consumers. This cmdlet accepts Custom, High, Low, and Normal values.
- -Name [String] (Optional) Modifies the name of the vApp.
- -NumCpuShares [Int32] (Optional) Specifies the CPU allocation level for the vApp. This property is used in relative allocation between resource consumers. This parameter is ignored unless the CpuSharesLevel parameter is set to Custom.
- -NumMemShares [Int32] (Optional) Specifies the memory allocation level for the resource pool. This property is used in relative allocation between resource consumers. This parameter is ignored unless the MemSharesLevel parameter is set to Custom.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VApp [VApp[]] (Required) Specifies the vApp that you want to configure.

**Examples:**

```powershell
Get-VApp -Name MyTestVApp1 | Set-VApp -CpuSharesLevel Low -MemSharesLevel Normal
```
_Modifies the CpuSharesLevel and MemSharesLevel properties of the MyTestVApp1 virtual appliance._

```powershell
$myvApp = Get-VApp -Location MyDatacenter1
Set-VApp -VApp $myvApp -CpuExpandableReservation:$true -CpuLimitMhz 4000 -MemExpandableReservation:$true -MemLimitGB 2
```
_Modifies the properties of the vApps available on the MyDatacenter1 datacenter._

### `Set-VDBlockedPolicy`

**This cmdlet modifies the blocking policy for distributed ports.**

This cmdlet modifies the blocking policy for distributed ports at switch, port group, or port level (depending on the input policy).

**Parameters:**

- -Blocked [Boolean] (Optional) Specifies whether packet forwarding is stopped for the corresponding distributed port, port group, or switch.
- -BlockedInherited [Boolean] (Optional) Specifies whether the Blocked setting is inherited from a parent object, such as a distributed port group or switch.
- -Policy [BlockedPolicy[]] (Required) Specifies the blocking policy that you want to configure.

**Examples:**

```powershell
Get-VDPort -VDSwitch "MyVDSwitch" -ActiveOnly | Get-VDBlockedPolicy | Set-VDBlockedPolicy -Blocked
```
_Retrieves all active distributed ports and updates their blocking policy to stop packet forwarding through them._

```powershell
Get-VDportgroup "MyVDPortgroup" | Get-VDPort | Get-VDBlockedPolicy | Set-VDBlockedPolicy -BlockedInherited
```
_Retrieves the specified "MyVDPortgroup" distributed port group and updates the blocking policy of all ports inside the group to inherit the setting for packet forwarding from the one set on the distributed port group level._

### `Set-VDUplinkLacpPolicy`

**This cmdlet modifies the Link Aggregation Control Protocol policy for uplink ports.**

This cmdlet modifies the Link Aggregation Control Protocol policy for uplink ports at switch or uplink  port group level.

**Parameters:**

- -Enabled [Boolean] (Optional) Specifies whether the Link Aggregation Control Protocol is enabled for the corresponding uplink port group or vSphere distributed switch.
- -EnabledInherited [Boolean] (Optional) Specifies whether the Enabled setting is inherited from a parent object, such as a vSphere distributed switch.
- -Mode [UplinkLacpMode] (Optional) Specifies the mode of the Link Aggregation Control Protocol policy for the corresponding uplink port group or vSphere distributed switch. The value can be Active or Passive.
- -ModeInherited [Boolean] (Optional) Specifies whether the Mode setting is inherited from a parent object, such as a vSphere distributed switch.
- -Policy [UplinkLacpPolicy[]] (Required) Specifies the Link Aggregation Control Protocol policy that you want to configure.

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDUplinkLacpPolicy | Set-VDUplinkLacpPolicy -Enabled $true -Mode Active
```
_Retrieves a vSphere distributed switch named "MyVDSwitch" and updates its policy to enable the Link Aggregation Control Protocol, and sets the corresponding policy mode to active._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDUplinkLacpPolicy | Set-VDUplinkLacpPolicy -ModeInherited $true
```
_Retrieves a distributed port group named "MyVDPortgroup" and updates its Link Aggregation Control Protocol mode based on its parent object's setting values._

### `Set-VDUplinkTeamingPolicy`

**This cmdlet modifies the uplink teaming policy for distributed ports.**

This cmdlet modifies the uplink teaming policy for distributed ports at switch, port group, or port level.

**Parameters:**

- -ActiveUplinkPort [String[]] (Optional) Specifies the active uplink ports used for load balancing for a corresponding vSphere distributed switch.
- -EnableFailback [Boolean] (Optional) Specifies whether to use failback when restoring links. If, for example, the explicit link order is (vmnic9, vmnic0), and vmnic9 goes down, vmnic0 is activated. However, when vmnic9 comes back up, if EnableFailback is set to $true, vmnic9 is restored as specified in the explicit order. If EnableFailback is set to $false, vmnic0 continues to be used and vmnic9 remains on standby.   This parameter replaces the obsolete ObsoleteParameterDisableFailback parameter, which is an alias fort the Failback parameter. Note that passing $false to the obsolete Failback parameter is equivalent to passing $true to the new EnableFailback parameter and the reverse.
- -FailbackInherited [Boolean] (Optional) Specifies whether the Failback setting is inherited from a parent object, such as a distributed port group or switch.
- -FailoverDetectionPolicy [NetworkFailoverDetectionPolicy] (Optional) Specifies the method to use for failover detection for the corresponding distributed port, port group, or switch. The value can be LinkStatus or BeaconProbing.
- -FailoverDetectionPolicyInherited [Boolean] (Optional) Specifies whether the FailoverDetectionPolicy setting is inherited from a parent object, such as a distributed port group or switch.
- -LoadBalancingPolicy [LoadBalancingPolicy] (Optional) Specifies the load balancing policy for the corresponding distributed port, port group, or switch. The value can be LoadBalanceIP, LoadBalanceLoadBased, LoadBalanceSrcMac, LoadBalanceSrcId, or ExplicitFailover.
- -LoadBalancingPolicyInherited [Boolean] (Optional) Specifies whether the LoadBalancingPolicy setting is inherited from a parent object, such as a distributed port group or switch.
- -NotifySwitches [Boolean] (Optional) Specifies whether to notify switches in the case of failover.
- -NotifySwitchesInherited [Boolean] (Optional) Specifies whether the NotifySwitches setting is inherited from a parent object, such as a distributed port group or switch.
- -ObsoleteParameterDisableFailback [Boolean] (Optional) This parameter and its alias, Failback, are obsolete and should not be used. They exist for compatibility with earlier PowerCLI versions. Use the EnableFailback parameter instead. Note that passing $false to the obsolete Failback parameter is equivalent to passing $true to the new EnableFailback parameter and the reverse.
- -Policy [UplinkTeamingPolicy[]] (Required) Specifies the uplink teaming policy that you want to configure.
- -StandbyUplinkPort [String[]] (Optional) Specifies the standby uplink ports for the corresponding vSphere distributed switch.
- -UnusedUplinkPort [String[]] (Optional) Specifies the unused uplink ports for the corresponding vSphere distributed switch.
- -UplinkPortOrderInherited [Boolean] (Optional) Specifies whether the UplinkPortOrder setting is inherited from a parent object, such as a distributed port group or switch.

**Examples:**

```powershell
$activePortsList = "Port0"
$standbyPortsList = "Port1", "Port2"
Get-VDSwitch "MyVDSwitch" | Get-VDPortgroup | Get-VDUplinkTeamingPolicy | Set-VDUplinkTeamingPolicy -ActiveUplinkPort $activePortsList -StandbyUplinkPort $standbyPortsList
```
_Retrieves all distributed port groups from a vSphere distributed switch named "MyVDSwitch" and updates their teaming policies with information about the active and standby uplinks that will be used when the adapter connectivity is up or down._

```powershell
Get-VDPortgroup "MyVDPortgroup" | Get-VDUplinkTeamingPolicy | Set-VDUplinkTeamingPolicy -NotifySwitches $true -FailoverDetectionPolicy LinkStatus
```
_Updates the teaming policy of a distributed port group named "MyVDPortgroup" with a link status method for failover detection and with the ability to notify the corresponding distributed switch when any adapter failover occurs._

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDPort "Port2" | Get-VDUplinkTeamingPolicy | Set-VDUplinkTeamingPolicy -LoadBalancingPolicy LoadBalanceSrcId -FailBack $true
```
_Updates the uplink teaming policy of a distributed port named "Port2" inside the "MyVDSwitch" vSphere distributed switch to enable failback and to choose an uplink based on the current loads of physical NICs._

### `Set-VDVlanConfiguration`

**This cmdlet modifies the virtual distributed port's VLAN configuration.**

This cmdlet modifies the virtual distributed port's VLAN configuration. For vSphere distributed switch and port group parameter sets, the cmdlet modifies the respective default port configuration.

**Parameters:**

- -DisableVlan [SwitchParameter] (Optional) Sets the VLAN type to None.
- -PrivateVlanId [Int32] (Optional) Specifies the secondary VLAN ID of a vSphere distributed switch's private VLAN configuration entry. The VLAN IDs of 0 and 4095 are reserved and cannot be used.
- -VDPort [VDPort[]] (Required) Specifies the port whose VLAN configuration you want to modify.
- -VDPortgroup [VDPortgroup[]] (Required) Specifies the port group whose default VLAN port configuration you want to modify.
- -VDSwitch [VDSwitch[]] (Required) Specifies the vSphere distributed switch whose default VLAN port configuration you want to modify.
- -VlanId [Int32] (Optional) Specifies a new VLAN ID. The VLAN IDs of 0 and 4095 are reserved and cannot be used.
- -VlanTrunkRange [VlanRangeList] (Optional) Specifies a new VLAN trunk range. Valid values are strings representing ranges of IDs. For example, "1-4, 6, 8-9".

**Examples:**

```powershell
Get-VDSwitch "MyVDSwitch" | Get-VDPort -ActiveOnly | Set-VDVlanConfiguration -PrivateVlanId 4
```
_Assigns all active ports of a specific vSphere distributed switch named "MyVDSwitch" to a private VLAN with ID "4"._

```powershell
Get-VDPortgroup "MyVDPorgroup" | Get-VDPort | Set-VDVlanConfiguration -VlanId 3
```
_Assigns all ports of a specific distributed port group named "MyVDPorgroup" to a VLAN with ID "3"._

## Start

### `Start-VApp`

**This cmdlet starts vApps.**

**Parameters:**

- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VApp [VApp[]] (Required) Specifies the vApp that you want to start.

**Examples:**

```powershell
Get-VMHost MyVMHost1 | Get-VApp | Start-VApp
```
_Starts all vApps on the specified host._

## Stop

### `Stop-VApp`

**This cmdlet stops vApps.**

**Parameters:**

- -Force [SwitchParameter] (Optional) Indicates that the virtual machines are powered off regardless of the auto-start configuration of the vApps.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VApp [VApp[]] (Required) Specifies the vApp that you want to stop.

**Examples:**

```powershell
Get-VMHost MyVMHost1 | Get-VApp | Stop-VApp
```
_Stops all virtual appliances on the specified host._

## Wait

### `Wait-Tools`

**This cmdlet waits for VMware Tools on the specified virtual machines to load.**

This cmdlet waits for VMware Tools of the specified virtual machines to load. The cmdlet returns the virtual machines or guests on which VMware Tools have loaded successfully within the specified time limits. You can cancel the operation before completion using Ctrl+C. The successful completion of Wait-Tools means that VMware Tools  have loaded, but it does not guarantee for the start of other services. Updating the returned VMGuest objects requires additional communication with VMware Tools and some of their properties (OSFullName, IPAddress, HostName, and other) might be still empty right after the completion of Wait-Tools.

**Parameters:**

- -Guest [VMGuest[]] (Required) Specifies the guest operating systems for which you want to wait VMware Tools to load.
- -HostCredential [PSCredential] (Optional) Specifies credentials for authenticating with the ESX/ESXi host of the specified virtual machine. This parameter is needed only if you have authenticated with vCenter Server via SSPI. If SSPI is not used, the credentials for authentication with vCenter Server are used.
- -HostPassword [SecureString] (Optional) Specifies a password for authenticating with the ESX host of the specified virtual machine. This parameter is needed only if you have authenticated with the vCenter Server via SSPI. If no SSPI is used, the password for authentication with vCenter Server is used.
- -HostUser [String] (Optional) Specifies a username for authenticating with the ESX/ESXi host of the specified virtual machine. This parameter is needed only if you have authenticated with vCenter Server via SSPI. If SSPI is not used, the username for authentication with vCenter Server is used.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -TimeoutSeconds [Int32] (Optional) Specifies the time period in seconds to wait for VMware Tools to start before cancelling the operation.
- -VM [VirtualMachine[]] (Required) Specifies the virtual machines for which you want to wait VMware Tools to load.

**Examples:**

```powershell
$vm = Start-VM VM* | Wait-Tools
```
_Starts the virtual machines with names starting with VM and Waits for their VMware Tools to load._

```powershell
Wait-Tools -VM $vm -TimeoutSeconds 180
```
_Waits for the VMware Tools of the virtual machines in the $vm variable to start. If VMware Tools do not load after 180 seconds, the operation is aborted._

```powershell
Wait-Tools -VM VM* -TimeoutSeconds 120 -HostCredential $vmhostCredential
```
_Waits for the VMware Tools of the virtual machines in the $vm variable to start. If VMware Tools do not load after 120 seconds, the operation is aborted. Host credentials are required when you run the cmdlet on environments older than vSphere 4.0._

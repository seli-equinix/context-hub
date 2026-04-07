---
name: powercli-other
description: "VMware PowerCLI 13.3 — Additional VMware PowerCLI cmdlets"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,other,Add-PassthroughDevice, Dismount-Tools, Get-AdvancedSetting, Get-CDDrive, Get-CisCommand, Get-CisService, Get-FloppyDrive, Get-KmipClientCertificate, Get-NetworkAdapter, Get-PassthroughDevice, Get-ScsiController, Get-ScsiLun, Get-ScsiLunPath, Get-Snapshot, Get-UsbDevice, Get-VAIOFilter, Get-VApp, Get-VasaProvider, Get-VDBlockedPolicy, Get-VDUplinkLacpPolicy, Get-VDUplinkTeamingPolicy, Mount-Tools, Move-VApp, New-AdvancedSetting, New-CDDrive, New-CnsKubernetesEntityMetadata, New-CnsKubernetesEntityReference, New-FloppyDrive, New-KmipClientCertificate, New-NetworkAdapter, New-ScsiController, New-Snapshot, New-VAIOFilter, New-VApp, New-VasaProvider, Remove-AdvancedSetting, Remove-CDDrive, Remove-FloppyDrive, Remove-NetworkAdapter, Remove-PassthroughDevice, Remove-Snapshot, Remove-UsbDevice, Remove-VAIOFilter, Remove-VApp, Remove-VasaProvider, Set-AdvancedSetting, Set-CDDrive, Set-FloppyDrive, Set-NetworkAdapter, Set-ScsiController, Set-ScsiLun, Set-ScsiLunPath, Set-Snapshot, Set-VAIOFilter, Set-VApp, Set-VDBlockedPolicy, Set-VDUplinkLacpPolicy, Set-VDUplinkTeamingPolicy, Set-VDVlanConfiguration, Start-VApp, Stop-VApp, TabExpansion2, Wait-Tools"
---

# VMware PowerCLI — Other

Additional VMware PowerCLI cmdlets. Module: VMware.VimAutomation (63 cmdlets).

## Cmdlet Reference (63 cmdlets)

### Add

#### `Add-PassthroughDevice`

This cmdlet attaches pass-through devices to the specified virtual machine.

**Parameters**: `VM, PassthroughDevice, Server`

### Dismount

#### `Dismount-Tools`

This cmdlet dismounts the VMware Tools installer CD.

**Parameters**: `Guest, VM, Server`

### Get

#### `Get-AdvancedSetting`

This cmdlet retrieves the advanced settings for the specified entity.

**Parameters**: `Entity, Name, Server`

#### `Get-CDDrive`

This cmdlet retrieves virtual CD drives.

**Parameters**: `Id, Server, VM, Template, Snapshot, Name`

#### `Get-CisCommand`

This function retrieves all commands of the VMware.VimAutomation.Cis.Core module.

**Parameters**: `Name`

#### `Get-CisService`

This cmdlet retrieves PSObject objects that represent a proxy to a vSphere Automation SDK API service and can be used to invoke the operations of that vSphere Automation SDK API service.

**Parameters**: `Name, Server`

#### `Get-FloppyDrive`

This cmdlet retrieves the virtual floppy drives available on a vCenter Server system.

**Parameters**: `Id, Server, VM, Template, Snapshot, Name`

#### `Get-KmipClientCertificate`

This cmdlet retrieves the latest generated self-signed certificate or certificate-signing request for the key provider.

**Parameters**: `KeyProvider, CertificateSigningRequest, FilePath, Server`

#### `Get-NetworkAdapter`

This cmdlet retrieves the virtual network adapters  available on a vCenter Server system.

**Parameters**: `Id, RelatedObject, Server, VM, Template, Snapshot, Name`

#### `Get-PassthroughDevice`

This cmdlet retrieves the pass-through devices available on the specified hosts, virtual machines, and templates.

**Parameters**: `VM, VMHost, Template, Type, Name, Id, Server`

#### `Get-ScsiController`

This cmdlet retrieves the virtual SCSI controllers assigned to the specified HardDisk, VirtualMachine, Template, and Snapshot objects.

**Parameters**: `Id, HardDisk, Server, VM, Template, Snapshot, Name`

#### `Get-ScsiLun`

This cmdlet retrieves the SCSI devices available on the vCenter Server system.

**Parameters**: `Id, CanonicalName, VmHost, Hba, Datastore, Key, LunType, Server`

#### `Get-ScsiLunPath`

This cmdlet retrieves the list of vmhba paths to a specified SCSI device.

**Parameters**: `Name, ScsiLun`

#### `Get-Snapshot`

This cmdlet retrieves the virtual machine snapshots available on a vCenter Server system.

**Parameters**: `Name, Id, VM, Server`

```powershell
Get-VM "my-vm" | Get-Snapshot | Select-Object VM, Name, Created, SizeGB
```

#### `Get-UsbDevice`

This cmdlet retrieves the USB devices available on a vCenter Server system.

**Parameters**: `Id, Server, VM, Template, Snapshot, Name`

#### `Get-VAIOFilter`

This cmdlet returns a list of VAIOFilter objects filtered by the specified parameters.

**Parameters**: `Name, Cluster, Id, Server`

#### `Get-VApp`

This cmdlet retrieves vApps.

**Parameters**: `Location, Tag, Name, Id, NoRecursion, Server`

#### `Get-VDBlockedPolicy`

This cmdlet retrieves the blocking policy for distributed ports.

**Parameters**: `VDPortgroup, VDSwitch, VDPort, Server`

#### `Get-VDUplinkLacpPolicy`

This cmdlet retrieves the Link Aggregation Control Protocol policy for uplink ports.

**Parameters**: `VDPortgroup, VDSwitch, VDPort, Server`

#### `Get-VDUplinkTeamingPolicy`

This cmdlet retrieves the uplink teaming policy for distributed ports.

**Parameters**: `VDPortgroup, VDSwitch, VDPort, Server`

#### `Get-VasaProvider`

This cmdlet retrieves the list of VASA providers that are currently registered with Storage Manager.

**Parameters**: `Name, Id, Refresh, StorageContainer, Server`

### Mount

#### `Mount-Tools`

This cmdlet mounts the VMware Tools CD installer as a CD-ROM on the guest operating system.

**Parameters**: `Guest, VM, Server`

### Move

#### `Move-VApp`

This cmdlet moves the specified virtual appliances to a new location.

**Parameters**: `Destination, VApp, Server, RunAsync`

### New

#### `New-AdvancedSetting`

This cmdlet creates a new advanced setting for the specified entity.

**Parameters**: `Name, Value, Entity, Type, Force, Server`

#### `New-CDDrive`

This cmdlet creates a new virtual CD drive.

**Parameters**: `IsoPath, HostDevice, StartConnected, ContentLibraryIso, VM, Server`

#### `New-CnsKubernetesEntityMetadata`

This cmdlet creates a Cloud Native Storage (CNS) Kubernetes entity metadata at a client side.

**Parameters**: `EntityType, Namespace, CnsKubernetesEntityReference, KubernetesClusterId, EntityName, Label`

#### `New-CnsKubernetesEntityReference`

This cmdlet creates a Cloud Native Storage (CNS) Kubernetes entity reference at the client side.

**Parameters**: `EntityName, EntityType, Namespace, KubernetesClusterId`

#### `New-FloppyDrive`

This cmdlet creates a new virtual floppy drive.

**Parameters**: `FloppyImagePath, NewFloppyImagePath, HostDevice, StartConnected, VM, Server`

#### `New-KmipClientCertificate`

This cmdlet creates a new self-signed certificate or certificate-signing request for the key management server cluster.

**Parameters**: `KeyProvider, CertificateSigningRequest, FilePath, Server`

#### `New-NetworkAdapter`

This cmdlet creates a new virtual network adapter.

**Parameters**: `MacAddress, NetworkName, StartConnected, WakeOnLan, Type, DeviceProtocol, PhysicalFunction, PortId, DistributedSwitch, Portgroup, VM, Server`

#### `New-ScsiController`

This cmdlet creates a new SCSI controller.

**Parameters**: `HardDisk, Type, BusSharingMode`

#### `New-Snapshot`

This cmdlet creates a new snapshot of a virtual machine.

**Parameters**: `VM, Name, Description, Memory, Quiesce, Server, RunAsync`

```powershell
New-Snapshot -VM "my-vm" -Name "pre-update" -Description "Before patching" -Memory -Quiesce
```

#### `New-VAIOFilter`

This cmdlet installs a VAIO filter on the specified cluster.

**Parameters**: `Cluster, VibUrl, Server`

#### `New-VApp`

This cmdlet creates a new vApp.

**Parameters**: `Location, InventoryLocation, Name, CpuExpandableReservation, CpuLimitMhz, CpuReservationMhz, CpuSharesLevel, MemExpandableReservation, MemLimitMB, MemLimitGB, MemReservationMB, MemReservationGB` (+10 more)

#### `New-VasaProvider`

This cmdlet registers a VASA provider.

**Parameters**: `Name, Url, Credential, Username, Password, Description, Certificate, Force, Server`

### Other

#### `TabExpansion2`

TabExpansion2 [-inputScript] <string> [-cursorColumn] <int> [[-options] <hashtable>] [<CommonParameters>]  TabExpansion2 [-ast] <Ast> [-tokens] <Token[]> [-positionOfCursor] <IScriptPosition> [[-options] <hashtable>] [<CommonParameters>]

**Parameters**: `inputScript, cursorColumn, ast, tokens, positionOfCursor, options`

### Remove

#### `Remove-AdvancedSetting`

This cmdlet removes the specified advanced setting.

**Parameters**: `AdvancedSetting`

#### `Remove-CDDrive`

This cmdlet removes virtual CD drives from their locations.

**Parameters**: `CD`

#### `Remove-FloppyDrive`

This cmdlet removes the virtual floppy drives from their locations.

**Parameters**: `Floppy`

#### `Remove-NetworkAdapter`

This cmdlet removes the virtual network adapters from their locations.

**Parameters**: `NetworkAdapter`

#### `Remove-PassthroughDevice`

This cmdlet removes the specified pass-through devices.

**Parameters**: `PassthroughDevice`

#### `Remove-Snapshot`

This cmdlet removes the specified virtual machine snapshots.

**Parameters**: `Snapshot, RemoveChildren, RunAsync`

```powershell
Get-VM "my-vm" | Get-Snapshot | Where-Object {$_.Created -lt (Get-Date).AddDays(-30)} | Remove-Snapshot -Confirm:$false
```

#### `Remove-UsbDevice`

This cmdlet removes the specified USB devices from a virtual machine.

**Parameters**: `UsbDevice`

#### `Remove-VAIOFilter`

This cmdlet uninstalls VAIO filters from the clusters on which they are installed.

**Parameters**: `Filter, Server`

#### `Remove-VApp`

This cmdlet removes vApps from the server.

**Parameters**: `DeletePermanently, VApp, Server, RunAsync`

#### `Remove-VasaProvider`

This cmdlet unregisters the specified VASA providers.

**Parameters**: `Provider, Server`

### Set

#### `Set-AdvancedSetting`

This cmdlet modifies the specified advanced setting.

**Parameters**: `AdvancedSetting, Value`

#### `Set-CDDrive`

This cmdlet modifies the configuration of a virtual CD drive.

**Parameters**: `CD, IsoPath, HostDevice, NoMedia, StartConnected, Connected`

#### `Set-FloppyDrive`

This cmdlet modifies the configuration of the specified virtual floppy drive.

**Parameters**: `Floppy, FloppyImagePath, HostDevice, NoMedia, StartConnected, Connected`

#### `Set-NetworkAdapter`

This cmdlet modifies the configuration of the virtual network adapter.

**Parameters**: `NetworkAdapter, MacAddress, NetworkName, StartConnected, Connected, WakeOnLan, Type, PortId, DistributedSwitch, Portgroup, RunAsync, Server`

#### `Set-ScsiController`

This cmdlet modifies the specified SCSI controllers.

**Parameters**: `ScsiController, BusSharingMode, Type`

#### `Set-ScsiLun`

This cmdlet modifies the configuration of a SCSI device.

**Parameters**: `MultipathPolicy, PreferredPath, ScsiLun, CommandsToSwitchPath, BlocksToSwitchPath, NoCommandsSwitch, NoBlocksSwitch, IsSsd, IsLocal, IsLocatorLedOn, DeletePartitions, Force`

#### `Set-ScsiLunPath`

This cmdlet configures a vmhba path to a SCSI device.

**Parameters**: `Active, ScsiLunPath, Preferred`

#### `Set-Snapshot`

This cmdlet modifies the specified virtual machine snapshot.

**Parameters**: `Snapshot, Name, Description`

#### `Set-VAIOFilter`

This cmdlet upgrades a VAIO filter on the cluster it is installed.

**Parameters**: `Filter, VibUrl, Server`

#### `Set-VApp`

This cmdlet modifies the specified vApp.

**Parameters**: `VApp, Name, CpuExpandableReservation, CpuLimitMhz, CpuReservationMhz, CpuSharesLevel, MemExpandableReservation, MemLimitMB, MemLimitGB, MemReservationMB, MemReservationGB, MemSharesLevel` (+3 more)

#### `Set-VDBlockedPolicy`

This cmdlet modifies the blocking policy for distributed ports.

**Parameters**: `Policy, Blocked, BlockedInherited`

#### `Set-VDUplinkLacpPolicy`

This cmdlet modifies the Link Aggregation Control Protocol policy for uplink ports.

**Parameters**: `Policy, Enabled, EnabledInherited, Mode, ModeInherited`

#### `Set-VDUplinkTeamingPolicy`

This cmdlet modifies the uplink teaming policy for distributed ports.

**Parameters**: `ActiveUplinkPort, ObsoleteParameterDisableFailback, EnableFailback, FailbackInherited, FailoverDetectionPolicy, FailoverDetectionPolicyInherited, LoadBalancingPolicy, LoadBalancingPolicyInherited, NotifySwitches, NotifySwitchesInherited, Policy, StandbyUplinkPort` (+2 more)

#### `Set-VDVlanConfiguration`

This cmdlet modifies the virtual distributed port's VLAN configuration.

**Parameters**: `VDPortgroup, VDSwitch, VDPort, DisableVlan, VlanId, VlanTrunkRange, PrivateVlanId`

### Start

#### `Start-VApp`

This cmdlet starts vApps.

**Parameters**: `VApp, Server, RunAsync`

### Stop

#### `Stop-VApp`

This cmdlet stops vApps.

**Parameters**: `Force, VApp, Server, RunAsync`

### Wait

#### `Wait-Tools`

This cmdlet waits for VMware Tools on the specified virtual machines to load.

**Parameters**: `VM, TimeoutSeconds, HostCredential, HostUser, HostPassword, Guest, Server`

---
name: powercli-host-management
description: "VMware PowerCLI 13.3 — ESXi host operations — configure, maintain, monitor hosts"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,host-management,Add-VDSwitchVMHost, Add-VMHost, Add-VMHostNtpServer, Export-LcmVMHostDesiredState, Export-VMHostImageDb, Export-VMHostProfile, Format-VMHostDiskPartition, Get-DrsVMHostRule, Get-EsxCli, Get-EsxTop, Get-HAPrimaryVMHost, Get-TrustAuthorityVMHostBaseImage, Get-VMHost, Get-VMHostAccount, Get-VMHostAdvancedConfiguration, Get-VMHostAuthentication, Get-VMHostAvailableTimeZone, Get-VMHostDiagnosticPartition, Get-VMHostDisk, Get-VMHostDiskPartition, Get-VMHostFirewallDefaultPolicy, Get-VMHostFirewallException, Get-VMHostFirmware, Get-VMHostHardware, Get-VMHostHba, Get-VMHostModule, Get-VMHostNetwork, Get-VMHostNetworkAdapter, Get-VMHostNetworkStack, Get-VMHostNtpServer, Get-VMHostPatch, Get-VMHostPciDevice, Get-VMHostProfile, Get-VMHostProfileImageCacheConfiguration, Get-VMHostProfileRequiredInput, Get-VMHostProfileStorageDeviceConfiguration, Get-VMHostProfileUserConfiguration, Get-VMHostProfileVmPortGroupConfiguration, Get-VMHostRoute, Get-VMHostService, Get-VMHostSnmp, Get-VMHostStartPolicy, Get-VMHostStorage, Get-VMHostSysLogServer, Get-VMHostTPM, Import-VMHostProfile, Install-VMHostPatch, Invoke-VMHostProfile, Move-VMHost, New-DrsVMHostRule, New-TrustAuthorityVMHostBaseImage, New-VMHostAccount, New-VMHostNetworkAdapter, New-VMHostProfile, New-VMHostProfileVmPortGroupConfiguration, New-VMHostRoute, Remove-DrsVMHostRule, Remove-TrustAuthorityVMHostBaseImage, Remove-VDSwitchVMHost, Remove-VMHost, Remove-VMHostAccount, Remove-VMHostNetworkAdapter, Remove-VMHostNtpServer, Remove-VMHostProfile, Remove-VMHostProfileVmPortGroupConfiguration, Remove-VMHostRoute, Restart-VMHost, Restart-VMHostService, Set-DrsVMHostRule, Set-VMHost, Set-VMHostAccount, Set-VMHostAdvancedConfiguration, Set-VMHostAuthentication, Set-VMHostDiagnosticPartition, Set-VMHostFirewallDefaultPolicy, Set-VMHostFirewallException, Set-VMHostFirmware, Set-VMHostHba, Set-VMHostModule, Set-VMHostNetwork, Set-VMHostNetworkAdapter, Set-VMHostNetworkStack, Set-VMHostProfile, Set-VMHostProfileImageCacheConfiguration, Set-VMHostProfileStorageDeviceConfiguration, Set-VMHostProfileUserConfiguration, Set-VMHostProfileVmPortGroupConfiguration, Set-VMHostRoute, Set-VMHostService, Set-VMHostSnmp, Set-VMHostStartPolicy, Set-VMHostStorage, Set-VMHostSysLogServer, Start-VMHost, Start-VMHostService, Stop-VMHost, Stop-VMHostService, Suspend-VMHost, Test-VMHostProfileCompliance, Test-VMHostSnmp"
---

# VMware PowerCLI — Host Management

ESXi host operations — configure, maintain, monitor hosts. Module: VMware.VimAutomation (100 cmdlets).

## Cmdlet Reference (100 cmdlets)

### Add

#### `Add-VDSwitchVMHost`

This cmdlet adds hosts to the specified vSphere distributed switch.

**Parameters**: `VDSwitch, VMHost, Server, RunAsync`

#### `Add-VMHost`

This cmdlet adds a host to be managed by a vCenter Server system.

**Parameters**: `Name, Port, Location, Credential, User, Password, Force, RunAsync, Server`

#### `Add-VMHostNtpServer`

This cmdlet adds the specified NTP servers to the NTP server list of the specified hosts.

**Parameters**: `NtpServer, VMHost, Server`

### Export

#### `Export-LcmVMHostDesiredState`

This cmdlet exports the desired state of an ESXi host that is managed by vSphere Lifecycle Manager. The desired state consists of the host's base image and the installed software packages.

**Parameters**: `VMHost, Destination, ExportIsoImage, ExportOfflineBundle, RunAsync, Server`

#### `Export-VMHostImageDb`

This cmdlet exports the specified host's base image database to a file that is in a .tgz format.

**Parameters**: `VMHost, FilePath, Force, Server, RunAsync`

#### `Export-VMHostProfile`

This cmdlet exports the specified host profile to a file.

**Parameters**: `FilePath, Profile, Force, Server`

### Format

#### `Format-VMHostDiskPartition`

This cmdlet formats a new VMFS (Virtual Machine File System) on each of the specified host disk partitions.

**Parameters**: `VolumeName, VMHostDiskPartition`

### Get

#### `Get-DrsVMHostRule`

This cmdlet retrieves VM to VMHost DRS rules that match the specified filters.

**Parameters**: `Name, Cluster, Type, VMGroup, VMHostGroup, Server`

#### `Get-EsxCli`

This cmdlet exposes the ESXCLI functionality.

**Parameters**: `VMHost, V2, Server`

#### `Get-EsxTop`

This cmdlet exposes the esxtop functionality.

**Parameters**: `CounterName, Counter, TopologyInfo, Topology, Server`

#### `Get-HAPrimaryVMHost`

On vCenter Server 5.0 and later, this cmdlet retrieves the primary host of the specified HA cluster. On vCenter Server versions earlier than 5.0, this cmdlet retrieves the primary HA (High-Availability) hosts for the specified clusters.

**Parameters**: `Cluster, Server`

#### `Get-TrustAuthorityVMHostBaseImage`

This cmdlet retrieves the Trust Authority virtual machine host base image from the specified Trust Authority clusters in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, Health, VMHostVersion, Id, Server`

#### `Get-VMHost`

This cmdlet retrieves the hosts on a vCenter Server system.

**Parameters**: `Name, NoRecursion, VM, ResourcePool, Datastore, State, Location, DistributedSwitch, Tag, Server, RelatedObject, Id`

```powershell
Get-VMHost | Select-Object Name, ConnectionState, PowerState, NumCpu, MemoryTotalGB
```

#### `Get-VMHostAccount`

This cmdlet retrieves the host accounts available on a vCenter Server system.

**Parameters**: `Group, User, Id, Server`

#### `Get-VMHostAdvancedConfiguration`

This cmdlet retrieves the advanced configuration of the hosts.

**Parameters**: `Name, VMHost, Server`

#### `Get-VMHostAuthentication`

This cmdlet retrieves authentication information for the specified hosts.

**Parameters**: `Id, VMHost, Server`

#### `Get-VMHostAvailableTimeZone`

This cmdlet retrieves the time zones available on the specified host.

**Parameters**: `VMHost, Name, Server`

#### `Get-VMHostDiagnosticPartition`

This cmdlet retrieves a list of  the diagnostic partitions on the specified hosts.

**Parameters**: `VMHost, All, Server`

#### `Get-VMHostDisk`

This cmdlet retrieves information about the specified SCSI LUN disk.

**Parameters**: `Id, ScsiLun, VMHost, Server`

#### `Get-VMHostDiskPartition`

This cmdlet retrieves the partitions of a host disk (LUN).

**Parameters**: `Id, VMHostDisk, Server`

#### `Get-VMHostFirewallDefaultPolicy`

This cmdlet retrieves the firewall default policy of the specified hosts.

**Parameters**: `VMHost, Server`

#### `Get-VMHostFirewallException`

This cmdlet retrieves the exceptions from the firewall policy on the specified hosts.

**Parameters**: `Name, VMHost, Port, Enabled, Server`

#### `Get-VMHostFirmware`

This cmdlet retrieves hosts firmware information.

**Parameters**: `VMHost, BackupConfiguration, DestinationPath, Server`

#### `Get-VMHostHardware`

This cmdlet retrieves ESXi host hardware and firmware information.

**Parameters**: `Id, VMHost, WaitForAllData, SkipCACheck, SkipCNCheck, SkipRevocationCheck, SkipAllSslCertificateChecks, Server`

#### `Get-VMHostHba`

This cmdlet retrieves information about the available HBAs (Host Bus Adapter).

**Parameters**: `VMHost, Device, Type, Server`

#### `Get-VMHostModule`

This cmdlet retrieves the option strings of the specified host modules.

**Parameters**: `VMHost, Name, Server`

#### `Get-VMHostNetwork`

THis cmdlet retrieves the host networks on a vCenter Server system.

**Parameters**: `Server, VMHost`

#### `Get-VMHostNetworkAdapter`

This cmdlet retrieves the host network adapters on a vCenter Server system.

**Parameters**: `VMHost, VirtualSwitch, PortGroup, Physical, VMKernel, Console, Name, Id, Server`

#### `Get-VMHostNetworkStack`

This cmdlet retrieves the host network stacks on a vCenter Server system.

**Parameters**: `VMHost, Name, Id, Server`

#### `Get-VMHostNtpServer`

This cmdlet retrieves the NTP servers on the specified hosts.

**Parameters**: `VMHost, Server`

#### `Get-VMHostPatch`

This cmdlet retrieves information about the host patches installed on the specified hosts. This cmdlet is deprecated and will not return any results for ESX hosts version 5.0 and later. Use (Get-ESXCli).software.vib.list() as an alternative.

**Parameters**: `VMHost, Server`

#### `Get-VMHostPciDevice`

This cmdlet retrieves the PCI devices on the specified hosts.

**Parameters**: `Name, VMHost, DeviceClass, Server`

#### `Get-VMHostProfile`

This cmdlet retrieves the available host profiles.

**Parameters**: `Name, Description, Entity, ReferenceHost, Id, Server`

#### `Get-VMHostProfileImageCacheConfiguration`

Retrieves an image cache configuration for the given host profile.

**Parameters**: `HostProfile, Server`

#### `Get-VMHostProfileRequiredInput`

This cmdlet performs a check whether the available information is sufficient to apply a host profile.

**Parameters**: `VMHost, Variable, Profile, Inapplicable, Server`

#### `Get-VMHostProfileStorageDeviceConfiguration`

Retrieves the storage device configuration for the given host profile.

**Parameters**: `HostProfile, DeviceName, Server`

#### `Get-VMHostProfileUserConfiguration`

This cmdlet retrieves the user password configuration for the given host profile.

**Parameters**: `HostProfile, UserName, Server`

#### `Get-VMHostProfileVmPortGroupConfiguration`

Retrieves the virtual machine port group configuration for the given host profile.

**Parameters**: `HostProfile, PortGroupName, Server`

#### `Get-VMHostRoute`

This cmdlet retrieves the routes from the routing table of the specified hosts.

**Parameters**: `VMHost, Server`

#### `Get-VMHostService`

This cmdlet retrieves information about a host service.

**Parameters**: `VMHost, Refresh, Server`

#### `Get-VMHostSnmp`

This cmdlet retrieves hosts SNMP configuration.

**Parameters**: `Server`

#### `Get-VMHostStartPolicy`

This cmdlet retrieves the start policy of hosts.

**Parameters**: `VMHost, Server`

#### `Get-VMHostStorage`

This cmdlet retrieves the host storages on a vCenter Server system.

**Parameters**: `Id, VMHost, Refresh, RescanAllHba, RescanVmfs, Server`

#### `Get-VMHostSysLogServer`

This cmdlet displays the remote syslog servers of the specified hosts.

**Parameters**: `VMHost, Server`

#### `Get-VMHostTPM`

This cmdlet retrieves the TPM 2.0 devices from the specified host.

**Parameters**: `VMHost, Id, Server`

### Import

#### `Import-VMHostProfile`

This cmdlet imports a host profile from a file. The file path must be accessible from the VMware PowerCLI client side.

**Parameters**: `FilePath, Name, ReferenceHost, Description, Server`

### Install

#### `Install-VMHostPatch`

This cmdlet updates the specified hosts.

**Parameters**: `VMHost, HostPath, WebPath, LocalPath, HostUsername, HostPassword, HostCredential, Server, RunAsync`

### Invoke

#### `Invoke-VMHostProfile`

This cmdlet applies a host profile to the specified host or cluster.

**Parameters**: `Entity, Profile, Variable, AssociateOnly, ApplyOnly, RunAsync, Server`

### Move

#### `Move-VMHost`

This cmdlet moves hosts to another location.

**Parameters**: `VMHost, Destination, Server, RunAsync`

### New

#### `New-DrsVMHostRule`

This cmdlet creates a new VM to VMHost DRS rule.

**Parameters**: `Name, Enabled, Cluster, VMGroup, VMHostGroup, Type, Server, RunAsync`

#### `New-TrustAuthorityVMHostBaseImage`

This cmdlet creates a Trust Authority virtual machine host base image in the Trust Authority vCenter Server system.

**Parameters**: `TrustAuthorityCluster, FilePath, Server`

#### `New-VMHostAccount`

This cmdlet creates a new host user or group account.

**Parameters**: `Id, Password, Description, GroupAccount, UserAccount, AssignUsers, AssignGroups, GrantShellAccess, Server`

#### `New-VMHostNetworkAdapter`

This cmdlet creates a new HostVirtualNIC (Service Console or VMKernel) on the specified host.

**Parameters**: `VMHost, PortGroup, PortId, VirtualSwitch, IP, SubnetMask, Mac, Mtu, ConsoleNic, VMotionEnabled, FaultToleranceLoggingEnabled, IPv6ThroughDhcp` (+6 more)

#### `New-VMHostProfile`

This cmdlet creates a new  host profile based on a reference host.

**Parameters**: `Name, ReferenceHost, Description, CompatibilityMode, Server`

#### `New-VMHostProfileVmPortGroupConfiguration`

This cmdlet creates a new virtual machine port group configuration.

**Parameters**: `HostProfile, PortGroupName, VSwitchName, VLanId, Server`

#### `New-VMHostRoute`

This cmdlet creates a new route in the routing table of a host.

**Parameters**: `VMHost, Destination, Gateway, PrefixLength, Server`

### Remove

#### `Remove-DrsVMHostRule`

This cmdlet removes the specified VM to VMHost DRS rule.

**Parameters**: `Rule, Server, RunAsync`

#### `Remove-TrustAuthorityVMHostBaseImage`

This cmdlet removes the Trust Authority virtual machine host base images from the Trust Authority cluster in the Trust Authority vCenter Server system.

**Parameters**: `VMHostBaseImage`

#### `Remove-VDSwitchVMHost`

This cmdlet removes hosts from the specified vSphere distributed switches.

**Parameters**: `VDSwitch, VMHost, Server, RunAsync`

#### `Remove-VMHost`

This cmdlet removes the specified hosts from the inventory.

**Parameters**: `VMHost, Server`

#### `Remove-VMHostAccount`

This cmdlet removes the specified host accounts.

**Parameters**: `HostAccount, Server`

#### `Remove-VMHostNetworkAdapter`

This cmdlet removes the specified host network adapters.

**Parameters**: `Nic`

#### `Remove-VMHostNtpServer`

This cmdlet removes the specified NTP servers from the NTP server list of the specified hosts.

**Parameters**: `NtpServer, VMHost, Server`

#### `Remove-VMHostProfile`

This cmdlet removes the specified host profiles.

**Parameters**: `Profile, Entity, Server`

#### `Remove-VMHostProfileVmPortGroupConfiguration`

Removes the given virtual machine port group configuration from the host profile.

**Parameters**: `VmPortGroupConfiguration, Server`

#### `Remove-VMHostRoute`

This cmdlet removes host routes.

**Parameters**: `VMHostRoute`

### Restart

#### `Restart-VMHost`

This cmdlet restarts the specified hosts.

**Parameters**: `VMHost, Force, Evacuate, Reason, Server, RunAsync`

#### `Restart-VMHostService`

This cmdlet restarts the specified host services.

**Parameters**: `HostService`

### Set

#### `Set-DrsVMHostRule`

This cmdlet modifies the specified VM to VMHost DRS rule.

**Parameters**: `Enabled, Name, VMGroup, VMHostGroup, Rule, Type, Server, RunAsync`

#### `Set-VMHost`

This cmdlet modifies the configuration of the host.

**Parameters**: `VMHost, State, VMSwapfilePolicy, VMSwapfileDatastore, Profile, Evacuate, TimeZone, LicenseKey, VsanDataMigrationMode, Reason, BaseImage, VendorAddOn` (+8 more)

#### `Set-VMHostAccount`

This cmdlet configures a host account.

**Parameters**: `GroupAccount, UserAccount, Password, Description, AssignUsers, UnassignUsers, AssignGroups, UnassignGroups, GrantShellAccess, Server`

#### `Set-VMHostAdvancedConfiguration`

This cmdlet modifies the advanced configuration settings of a host.

**Parameters**: `NameValue, Name, Value, VMHost, Server`

#### `Set-VMHostAuthentication`

This cmdlet modifies the host authentication information.

**Parameters**: `Domain, Username, Password, Credential, JoinDomain, Force, LeaveDomain, VMHostAuthentication`

#### `Set-VMHostDiagnosticPartition`

This cmdlet activates or deactivates the diagnostic partitions of  hosts.

**Parameters**: `Active, VMHostDiagnosticPartition`

#### `Set-VMHostFirewallDefaultPolicy`

This cmdlet sets the default policy for the specified host firewall.

**Parameters**: `AllowIncoming, AllowOutgoing, Policy`

#### `Set-VMHostFirewallException`

This cmdlet activates or deactivates host firewall exceptions.

**Parameters**: `Enabled, Exception`

#### `Set-VMHostFirmware`

This cmdlet configures hosts firmware settings.

**Parameters**: `VMHost, BackupConfiguration, DestinationPath, ResetToDefaults, Restore, SourcePath, Force, HostCredential, HostUser, HostPassword, Server`

#### `Set-VMHostHba`

This cmdlet configures the CHAP properties of the specified iSCSI HBAs.

**Parameters**: `IScsiHba, IScsiName, ChapType, ChapName, ChapPassword, MutualChapEnabled, MutualChapName, MutualChapPassword, Server`

#### `Set-VMHostModule`

This cmdlet overrides the host module options with the given ones.

**Parameters**: `HostModule, Options`

#### `Set-VMHostNetwork`

This cmdlet updates the specified virtual network.

**Parameters**: `Network, ConsoleGateway, VMKernelGateway, VMKernelGatewayDevice, ConsoleGatewayDevice, DomainName, HostName, DnsFromDhcp, DnsDhcpDevice, DnsAddress, SearchDomain, IPv6Enabled` (+4 more)

#### `Set-VMHostNetworkAdapter`

This cmdlet configures the specified host network adapter.

**Parameters**: `PhysicalNic, Duplex, BitRatePerSecMb, AutoNegotiate, VirtualNic, Dhcp, IP, SubnetMask, Mac, Mtu, VMotionEnabled, FaultToleranceLoggingEnabled` (+11 more)

#### `Set-VMHostNetworkStack`

This cmdlet modifies the specified host network stack.

**Parameters**: `NetworkStack, Name, VMKernelGateway, VMKernelV6Gateway, MaxNumberOfConnections, CongestionControlAlgoritm, DomainName, HostName, DnsFromDhcp, DnsAddress, SearchDomain, Server`

#### `Set-VMHostProfile`

This cmdlet modifies the specified host profile.

**Parameters**: `Name, ReferenceHost, Profile, Description, Server`

#### `Set-VMHostProfileImageCacheConfiguration`

This cmdlet modifies image cache configuration for given host profile.

**Parameters**: `ImageCacheConfiguration, InstallationType, InstallationDevice, DiskArguments, IgnoreSsd, OverwriteVmfs, Server`

#### `Set-VMHostProfileStorageDeviceConfiguration`

This cmdlet modifies the storage device configuration for the given host profile.

**Parameters**: `StorageDeviceConfiguration, DeviceStateOn, IsPerenniallyReserved, IsSharedClusterwide, NumReqOutstanding, QueueFullSampleSize, QueueFullThreshold, PspName, ConfigInfo, Server`

#### `Set-VMHostProfileUserConfiguration`

This cmdlet modifies the user password configuration for the specified account within a host profile.

**Parameters**: `UserConfiguration, PasswordPolicy, Password, Server`

#### `Set-VMHostProfileVmPortGroupConfiguration`

This cmdlet modifies the virtual machine port group configuration for the given host profile.

**Parameters**: `VmPortGroupConfiguration, VSwitchName, VLanId, Server`

#### `Set-VMHostRoute`

This cmdlet modifies a route in the host routing table.

**Parameters**: `VMHostRoute, Destination, Gateway, PrefixLength`

#### `Set-VMHostService`

This cmdlet modifies a host service.

**Parameters**: `HostService, Policy`

#### `Set-VMHostSnmp`

This cmdlet modifies the host SNMP configuration.

**Parameters**: `HostSnmp, Enabled, Port, ReadOnlyCommunity, TargetCommunity, TargetPort, TargetHost, AddTarget, RemoveTarget, TrapTargetToRemove`

#### `Set-VMHostStartPolicy`

This cmdlet modifies the host default start policy.

**Parameters**: `VMHostStartPolicy, Enabled, StartDelay, StopAction, StopDelay, WaitForHeartBeat`

#### `Set-VMHostStorage`

This cmdlet configures a host storage.

**Parameters**: `VMHostStorage, SoftwareIScsiEnabled`

#### `Set-VMHostSysLogServer`

This cmdlet configures the remote syslog server of the specified hosts.

**Parameters**: `SysLogServer, VMHost, SysLogServerPort, Server`

### Start

#### `Start-VMHost`

This cmdlet starts the specified hosts.

**Parameters**: `VMHost, TimeoutSeconds, Server, RunAsync`

#### `Start-VMHostService`

This cmdlet starts the specified host services.

**Parameters**: `HostService`

### Stop

#### `Stop-VMHost`

This cmdlet powers off the specified hosts.

**Parameters**: `VMHost, Force, Reason, Server, RunAsync`

#### `Stop-VMHostService`

This cmdlet stops the specified host services.

**Parameters**: `HostService`

### Suspend

#### `Suspend-VMHost`

This cmdlet suspends hosts.

**Parameters**: `VMHost, TimeoutSeconds, Evacuate, Server, RunAsync`

### Test

#### `Test-VMHostProfileCompliance`

This cmdlet tests hosts for profile compliance.

**Parameters**: `VMHost, Profile, UseCache, Server`

#### `Test-VMHostSnmp`

This cmdlet tests the host SNMP.

**Parameters**: `HostSnmp`

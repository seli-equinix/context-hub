---
name: powercli-vmhost
description: "VMware PowerCLI 13.3 — ESXi host management: add/remove hosts, networking, NTP, services, profiles"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Add-VMHost,Add-VMHostNtpServer,Apply-VMHostProfile,Export-LcmVMHostDesiredState,Export-VMHostProfile,Format-VMHostDiskPartition,Get-DrsVMHostRule,Get-EsxCli,Get-HAPrimaryVMHost,Get-VMHost,Get-VMHostAccount,Get-VMHostAdvancedConfiguration,Get-VMHostAuthentication,Get-VMHostAvailableTimeZone,Get-VMHostDiagnosticPartition,Get-VMHostDisk,Get-VMHostDiskPartition,Get-VMHostFirewallDefaultPolicy,Get-VMHostFirewallException,Get-VMHostFirmware,Get-VMHostHardware,Get-VMHostHba,Get-VMHostModule,Get-VMHostNetwork,Get-VMHostNetworkAdapter,Get-VMHostNetworkStack,Get-VMHostNtpServer,Get-VMHostPatch,Get-VMHostPciDevice,Get-VMHostProfile,Get-VMHostProfileImageCacheConfiguration,Get-VMHostProfileRequiredInput,Get-VMHostProfileStorageDeviceConfiguration,Get-VMHostProfileUserConfiguration,Get-VMHostProfileVmPortGroupConfiguration,Get-VMHostRoute,Get-VMHostService,Get-VMHostSnmp,Get-VMHostStartPolicy,Get-VMHostStorage,Get-VMHostSysLogServer,Import-VMHostProfile,Install-VMHostPatch,Invoke-VMHostProfile,Move-VMHost,New-DrsVMHostRule,New-VMHostAccount,New-VMHostNetworkAdapter,New-VMHostProfile,New-VMHostProfileVmPortGroupConfiguration,New-VMHostRoute,Remove-DrsVMHostRule,Remove-VMHost,Remove-VMHostAccount,Remove-VMHostNetworkAdapter,Remove-VMHostNtpServer,Remove-VMHostProfile,Remove-VMHostProfileVmPortGroupConfiguration,Remove-VMHostRoute,Restart-VMHost,Restart-VMHostService,Set-DrsVMHostRule,Set-VMHost,Set-VMHostAccount,Set-VMHostAdvancedConfiguration,Set-VMHostAuthentication,Set-VMHostDiagnosticPartition,Set-VMHostFirewallDefaultPolicy,Set-VMHostFirewallException,Set-VMHostFirmware,Set-VMHostHba,Set-VMHostModule,Set-VMHostNetwork,Set-VMHostNetworkAdapter,Set-VMHostNetworkStack,Set-VMHostProfile,Set-VMHostProfileImageCacheConfiguration,Set-VMHostProfileStorageDeviceConfiguration,Set-VMHostProfileUserConfiguration,Set-VMHostProfileVmPortGroupConfiguration,Set-VMHostRoute,Set-VMHostService,Set-VMHostSnmp,Set-VMHostStartPolicy,Set-VMHostStorage,Set-VMHostSysLogServer,Start-VMHost,Start-VMHostService,Stop-VMHost,Stop-VMHostService,Suspend-VMHost,Test-VMHostProfileCompliance,Test-VMHostSnmp"
---

# VMware PowerCLI — ESXi host management

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-VMHost` | This cmdlet adds a host to be managed by a vCenter Server system. |
| `Add-VMHostNtpServer` | This cmdlet adds the specified NTP servers to the NTP server list of the specified hosts. |
| `Apply-VMHostProfile` | This cmdlet applies a host profile to the specified host or cluster. |
| `Export-LcmVMHostDesiredState` | This cmdlet exports the desired state of an ESXi host that is managed by vSphere Lifecycle Manage... |
| `Export-VMHostProfile` | This cmdlet exports the specified host profile to a file. |
| `Format-VMHostDiskPartition` | This cmdlet formats a new VMFS (Virtual Machine File System) on each of the specified host disk p... |
| `Get-DrsVMHostRule` | This cmdlet retrieves VM to VMHost DRS rules that match the specified filters. |
| `Get-EsxCli` | This cmdlet exposes the ESXCLI functionality. |
| `Get-HAPrimaryVMHost` | On vCenter Server 5.0 and later, this cmdlet retrieves the primary host of the specified HA clust... |
| `Get-VMHost` | This cmdlet retrieves the hosts on a vCenter Server system. |
| `Get-VMHostAccount` | This cmdlet retrieves the host accounts available on a vCenter Server system. |
| `Get-VMHostAdvancedConfiguration` | This cmdlet retrieves the advanced configuration of the hosts. |
| `Get-VMHostAuthentication` | This cmdlet retrieves authentication information for the specified hosts. |
| `Get-VMHostAvailableTimeZone` | This cmdlet retrieves the time zones available on the specified host. |
| `Get-VMHostDiagnosticPartition` | This cmdlet retrieves a list of  the diagnostic partitions on the specified hosts. |
| `Get-VMHostDisk` | This cmdlet retrieves information about the specified SCSI LUN disk. |
| `Get-VMHostDiskPartition` | This cmdlet retrieves the partitions of a host disk (LUN). |
| `Get-VMHostFirewallDefaultPolicy` | This cmdlet retrieves the firewall default policy of the specified hosts. |
| `Get-VMHostFirewallException` | This cmdlet retrieves the exceptions from the firewall policy on the specified hosts. |
| `Get-VMHostFirmware` | This cmdlet retrieves hosts firmware information. |
| `Get-VMHostHardware` | This cmdlet retrieves ESXi host hardware and firmware information. |
| `Get-VMHostHba` | This cmdlet retrieves information about the available HBAs (Host Bus Adapter). |
| `Get-VMHostModule` | This cmdlet retrieves the option strings of the specified host modules. |
| `Get-VMHostNetwork` | THis cmdlet retrieves the host networks on a vCenter Server system. |
| `Get-VMHostNetworkAdapter` | This cmdlet retrieves the host network adapters on a vCenter Server system. |
| `Get-VMHostNetworkStack` | This cmdlet retrieves the host network stacks on a vCenter Server system. |
| `Get-VMHostNtpServer` | This cmdlet retrieves the NTP servers on the specified hosts. |
| `Get-VMHostPatch` | This cmdlet retrieves information about the host patches installed on the specified hosts. This c... |
| `Get-VMHostPciDevice` | This cmdlet retrieves the PCI devices on the specified hosts. |
| `Get-VMHostProfile` | This cmdlet retrieves the available host profiles. |
| `Get-VMHostProfileImageCacheConfiguration` | Retrieves an image cache configuration for the given host profile. |
| `Get-VMHostProfileRequiredInput` | This cmdlet performs a check whether the available information is sufficient to apply a host prof... |
| `Get-VMHostProfileStorageDeviceConfiguration` | Retrieves the storage device configuration for the given host profile. |
| `Get-VMHostProfileUserConfiguration` | This cmdlet retrieves the user password configuration for the given host profile. |
| `Get-VMHostProfileVmPortGroupConfiguration` | Retrieves the virtual machine port group configuration for the given host profile. |
| `Get-VMHostRoute` | This cmdlet retrieves the routes from the routing table of the specified hosts. |
| `Get-VMHostService` | This cmdlet retrieves information about a host service. |
| `Get-VMHostSnmp` | This cmdlet retrieves hosts SNMP configuration. |
| `Get-VMHostStartPolicy` | This cmdlet retrieves the start policy of hosts. |
| `Get-VMHostStorage` | This cmdlet retrieves the host storages on a vCenter Server system. |
| `Get-VMHostSysLogServer` | This cmdlet displays the remote syslog servers of the specified hosts. |
| `Import-VMHostProfile` | This cmdlet imports a host profile from a file. The file path must be accessible from the VMware ... |
| `Install-VMHostPatch` | This cmdlet updates the specified hosts. |
| `Invoke-VMHostProfile` | This cmdlet applies a host profile to the specified host or cluster. |
| `Move-VMHost` | This cmdlet moves hosts to another location. |
| `New-DrsVMHostRule` | This cmdlet creates a new VM to VMHost DRS rule. |
| `New-VMHostAccount` | This cmdlet creates a new host user or group account. |
| `New-VMHostNetworkAdapter` | This cmdlet creates a new HostVirtualNIC (Service Console or VMKernel) on the specified host. |
| `New-VMHostProfile` | This cmdlet creates a new  host profile based on a reference host. |
| `New-VMHostProfileVmPortGroupConfiguration` | This cmdlet creates a new virtual machine port group configuration. |
| `New-VMHostRoute` | This cmdlet creates a new route in the routing table of a host. |
| `Remove-DrsVMHostRule` | This cmdlet removes the specified VM to VMHost DRS rule. |
| `Remove-VMHost` | This cmdlet removes the specified hosts from the inventory. |
| `Remove-VMHostAccount` | This cmdlet removes the specified host accounts. |
| `Remove-VMHostNetworkAdapter` | This cmdlet removes the specified host network adapters. |
| `Remove-VMHostNtpServer` | This cmdlet removes the specified NTP servers from the NTP server list of the specified hosts. |
| `Remove-VMHostProfile` | This cmdlet removes the specified host profiles. |
| `Remove-VMHostProfileVmPortGroupConfiguration` | Removes the given virtual machine port group configuration from the host profile. |
| `Remove-VMHostRoute` | This cmdlet removes host routes. |
| `Restart-VMHost` | This cmdlet restarts the specified hosts. |
| `Restart-VMHostService` | This cmdlet restarts the specified host services. |
| `Set-DrsVMHostRule` | This cmdlet modifies the specified VM to VMHost DRS rule. |
| `Set-VMHost` | This cmdlet modifies the configuration of the host. |
| `Set-VMHostAccount` | This cmdlet configures a host account. |
| `Set-VMHostAdvancedConfiguration` | This cmdlet modifies the advanced configuration settings of a host. |
| `Set-VMHostAuthentication` | This cmdlet modifies the host authentication information. |
| `Set-VMHostDiagnosticPartition` | This cmdlet activates or deactivates the diagnostic partitions of  hosts. |
| `Set-VMHostFirewallDefaultPolicy` | This cmdlet sets the default policy for the specified host firewall. |
| `Set-VMHostFirewallException` | This cmdlet activates or deactivates host firewall exceptions. |
| `Set-VMHostFirmware` | This cmdlet configures hosts firmware settings. |
| `Set-VMHostHba` | This cmdlet configures the CHAP properties of the specified iSCSI HBAs. |
| `Set-VMHostModule` | This cmdlet overrides the host module options with the given ones. |
| `Set-VMHostNetwork` | This cmdlet updates the specified virtual network. |
| `Set-VMHostNetworkAdapter` | This cmdlet configures the specified host network adapter. |
| `Set-VMHostNetworkStack` | This cmdlet modifies the specified host network stack. |
| `Set-VMHostProfile` | This cmdlet modifies the specified host profile. |
| `Set-VMHostProfileImageCacheConfiguration` | This cmdlet modifies image cache configuration for given host profile. |
| `Set-VMHostProfileStorageDeviceConfiguration` | This cmdlet modifies the storage device configuration for the given host profile. |
| `Set-VMHostProfileUserConfiguration` | This cmdlet modifies the user password configuration for the specified account within a host prof... |
| `Set-VMHostProfileVmPortGroupConfiguration` | This cmdlet modifies the virtual machine port group configuration for the given host profile. |
| `Set-VMHostRoute` | This cmdlet modifies a route in the host routing table. |
| `Set-VMHostService` | This cmdlet modifies a host service. |
| `Set-VMHostSnmp` | This cmdlet modifies the host SNMP configuration. |
| `Set-VMHostStartPolicy` | This cmdlet modifies the host default start policy. |
| `Set-VMHostStorage` | This cmdlet configures a host storage. |
| `Set-VMHostSysLogServer` | This cmdlet configures the remote syslog server of the specified hosts. |
| `Start-VMHost` | This cmdlet starts the specified hosts. |
| `Start-VMHostService` | This cmdlet starts the specified host services. |
| `Stop-VMHost` | This cmdlet powers off the specified hosts. |
| `Stop-VMHostService` | This cmdlet stops the specified host services. |
| `Suspend-VMHost` | This cmdlet suspends hosts. |
| `Test-VMHostProfileCompliance` | This cmdlet tests hosts for profile compliance. |
| `Test-VMHostSnmp` | This cmdlet tests the host SNMP. |

---

### Add-VMHost

This cmdlet adds a host to be managed by a vCenter Server system.

This cmdlet adds a host to be managed by a vCenter Server system. The host is added to the datacenter or folder specified by the Location parameter. One of the User/Password and Credential parameters must be provided in order to authenticate with the host. If both are specified, the Credential parameter is used and the User and Password parameters are ignored.

**Returns**: `VMHost`

```
Add-VMHost
    [-Credential <PSCredential>]
    [-Force]
    -Location <VIContainer>
    -Name <String>
    [-Password <String>]
    [-Port <Int32>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-User <String>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the virtual machine host. |
| `-Force` | `SwitchParameter` | No | Indicates that the cmdlet runs even if the authenticity of the host SSL certificate cannot be verified. |
| `-Location` | `VIContainer` | Yes | Specifies a datacenter or folder where you want to place the host. |
| `-Name` | `String` | Yes | Specifies the name of the host you want to add to a vCenter Server system. |
| `-Password` | `String` | No | Specifies the password you want to use for authenticating with the host. |
| `-Port` | `Int32` | No | Specifies the port on the host you want to use for the connection. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-User` | `String` | No | Specifies the user name you want to use for authenticating with the host. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Add-VMHostNtpServer

This cmdlet adds the specified NTP servers to the NTP server list of the specified hosts.

This cmdlet adds the specified NTP servers to the NTP server list of the specified hosts. If a server is already in the list, a non-terminating error is generated and a duplicate is not created.

**Returns**: `System`

```
Add-VMHostNtpServer
    -NtpServer <String[]>
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-NtpServer` | `String[]` | Yes | Specifies the domain name or the IP address of the NTP server you want to add to the host. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies a host to which you want to add the NTP server. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Apply-VMHostProfile

This cmdlet applies a host profile to the specified host or cluster.

This cmdlet applies a host profile to the specified host or cluster. The host or cluster must be in a maintenance mode. If no value is provided to the Profile parameter, the profile currently associated with the  host or cluster is applied.

**Returns**: `VMHost`

```
Apply-VMHostProfile
    [-ApplyOnly]
    [-AssociateOnly]
    -Entity <InventoryItem[]>
    [-Profile <VMHostProfile>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Variable <Hashtable>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApplyOnly` | `SwitchParameter` | No | Indicates whether to apply the host profile to the specified virtual machine host without associating it. |
| `-AssociateOnly` | `SwitchParameter` | No | Indicates whether to associate the host profile to the specified host or cluster without applying it. |
| `-Entity` | `InventoryItem[]` | Yes | Specifies hosts or clusters to which you want to apply the virtual machine host profile. |
| `-Profile` | `VMHostProfile` | No | Specifies the host profile you want to apply. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Variable` | `Hashtable` | No | Specifies a hash table object that provides values for the host profile required variables. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Export-LcmVMHostDesiredState

This cmdlet exports the desired state of an ESXi host that is managed by vSphere Lifecycle Manager. The desired state consists of the host's base image and the installed software packages.

This cmdlet exports the desired state of an ESXi host that is managed by vSphere Lifecycle Manager. The desired state consists of the host's base image and the installed software packages. The desired state is exported as a JSON metadata file, as an installable ISO image, or as a ZIP offline bundle. The exported files can be imported in other ESXi hosts or clusters managed by vSphere Lifecycle Manager.

**Returns**: `System.IO.FileInfo`

```
Export-LcmVMHostDesiredState
    [-Destination <String>]
    [-ExportIsoImage]
    [-ExportOfflineBundle]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `String` | No | Specifies a local directory where you want to save the JSON metadata file, the installable ISO image, or the ZIP offline bundle. If no value is provided, your current directory will be used. |
| `-ExportIsoImage` | `SwitchParameter` | No | Specifies whether to export the ESXi base image as an installable ISO image. |
| `-ExportOfflineBundle` | `SwitchParameter` | No | Specifies whether to export an offline ZIP bundle containing all software packages that can be imported into the vSphere Lifecycle Manager depot. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost` | Yes | Specifies the name of the ESXi host whose desired state you want to export. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Export-VMHostProfile

This cmdlet exports the specified host profile to a file.

This cmdlet exports the specified host profile to a file that is in the VMware profile format (.vpf). If the value of the Force parameter is $false and the destination file exists or the target parent directory does not exist, a terminating error is generated. If the value of the Force parameter is $true, the existing destination file is overwritten and directories are created to complete the specified file path.

**Returns**: `FileInfo`

```
Export-VMHostProfile
    -FilePath <String>
    [-Force]
    -Profile <VMHostProfile>
    [-Server <VIServer>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-FilePath` | `String` | Yes | Specifies the path to the file where you want to export the host profile. |
| `-Force` | `SwitchParameter` | No | Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path. |
| `-Profile` | `VMHostProfile` | Yes | Specifies the host profile you want to export. |
| `-Server` | `VIServer` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Format-VMHostDiskPartition

This cmdlet formats a new VMFS (Virtual Machine File System) on each of the specified host disk partitions.

**Returns**: `VMHostDiskPartition`

```
Format-VMHostDiskPartition
    -VMHostDiskPartition <VMHostDiskPartition[]>
    -VolumeName <String>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VMHostDiskPartition` | `VMHostDiskPartition[]` | Yes | Specifies the disk partitions on which you want to format a new VMFS. |
| `-VolumeName` | `String` | Yes | Specifies a name for the new VMFS. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-DrsVMHostRule

This cmdlet retrieves VM to VMHost DRS rules that match the specified filters.

**Returns**: `DrsVMHostRule`

```
Get-DrsVMHostRule
    [-Cluster <Cluster[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Type <DrsVMHostRuleType[]>]
    [-VMGroup <DrsClusterVMGroup[]>]
    [-VMHostGroup <DrsClusterVMHostGroup[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | No | Specifies the DRS clusters from which you want to retrieve rules. |
| `-Name` | `String[]` | No | Specifies the names of the DRS rules you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `DrsVMHostRuleType[]` | No | Specifies the types of DRS rules you want to retrieve. This parameter accepts MustRunOn, ShouldRunOn, MustNotRunOn, and ShouldNotRunOn values. |
| `-VMGroup` | `DrsClusterVMGroup[]` | No | Filters rules by VM group. |
| `-VMHostGroup` | `DrsClusterVMHostGroup[]` | No | Filters rules by VMHost group. |

---

### Get-EsxCli

This cmdlet exposes the ESXCLI functionality.

**Returns**: `EsxCli`

```
Get-EsxCli
    [-Server <VIServer[]>]
    [-V2]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-V2` | `SwitchParameter` | No | If specified, the cmdlet returns an EsxCli object version 2 (V2), otherwise an EsxCli object version 1 (V1) is returned. Interface V2 supports specifying method arguments only by name. This is the ... |
| `-VMHost` | `VMHost[]` | Yes | Specifies hosts on which you want to expose the ESXCLI functionality. |

---

### Get-HAPrimaryVMHost

On vCenter Server 5.0 and later, this cmdlet retrieves the primary host of the specified HA cluster. On vCenter Server versions earlier than 5.0, this cmdlet retrieves the primary HA (High-Availability) hosts for the specified clusters.

On vCenter Server 5.0 and later, the cmdlet retrieves the primary host of the specified HA cluster. On vCenter Server versions earlier than 5.0, the cmdlet retrieves the primary HA (High-Availability) hosts for the specified clusters.

**Returns**: `VMHost`

```
Get-HAPrimaryVMHost
    [-Cluster <Cluster[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | No | Specifies the clusters for which you want to retrieve the HA primary hosts. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VMHost

This cmdlet retrieves the hosts on a vCenter Server system.

This cmdlet retrieves the hosts on a vCenter Server system. Returns a set of hosts that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter. When working directly on an ESX host, the Name property of the returned VMHost object  contains either the DNS name or the IP of the ESX host, depending on which of them was specified when connecting with Connect-VIServer.

**Returns**: `VMHost`

```
Get-VMHost
    [-Datastore <StorageResource[]>]
    [-DistributedSwitch <DistributedSwitch[]>]
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NoRecursion]
    -RelatedObject <VMHostRelatedObjectBase[]>
    [-ResourcePool <ResourcePool[]>]
    [-Server <VIServer[]>]
    [-State <VMHostState[]>]
    [-Tag <Tag[]>]
    [-VM <VirtualMachine[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Datastore` | `StorageResource[]` | No | Specifies the datastores or datastore clusters to which the hosts that you want to retrieve are associated. Passing values to this parameter through a pipeline is deprecated and will be removed in ... |
| `-DistributedSwitch` | `DistributedSwitch[]` | No | Filters the available hosts by the virtual switches they are connected to. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the hosts you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string va... |
| `-Location` | `VIContainer[]` | No | Specifies the vSphere container objects (such as folders, datacenters, and clusters) you want to search for hosts. |
| `-Name` | `String[]` | No | Specifies the names of the hosts you want to retrieve. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-RelatedObject` | `VMHostRelatedObjectBase[]` | Yes | Specifies objects to retrieve one or more VMHost objects that are related to them. This parameter accepts OMResource objects. |
| `-ResourcePool` | `ResourcePool[]` | No | Specifies resource pools associated with the hosts you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-State` | `VMHostState[]` | No | Specifies the state of the hosts you want to retrieve. The valid values are Connected, Disconnected, NotResponding, and Maintenance. |
| `-Tag` | `Tag[]` | No | Returns only the virtual machine hosts that are associated with any of the specified tags. |
| `-VM` | `VirtualMachine[]` | No | Specifies virtual machines whose hosts you want to retrieve. |

---

### Get-VMHostAccount

This cmdlet retrieves the host accounts available on a vCenter Server system.

This cmdlet retrieves the host accounts available on a vCenter Server system. If both User and Group parameters are set to $true, in the list returned by the command, group accounts come out on top. If none of the User and Group switch parameters are provided, the cmdlet retrieves only the user accounts. If the ID parameter is set, the cmdlet filters the host accounts by their IDs. To specify a server different from the default one, use the Server parameter. Note: The specified server must be...

**Returns**: `HostAccount`

```
Get-VMHostAccount
    [-Group]
    [-Id <String[]>]
    [-Server <VIServer[]>]
    [-User]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Group` | `SwitchParameter` | No | Indicates that you want to retrieve only group host accounts. Starting with ESXi 5.1, this parameter is not supported. |
| `-Id` | `String[]` | No | Specifies the IDs of the host accounts you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the s... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-User` | `SwitchParameter` | No | Indicates that you want to retrieve only user host accounts. |

---

### Get-VMHostAdvancedConfiguration

This cmdlet retrieves the advanced configuration of the hosts.

This cmdlet is deprecated. Use Get-AdvancedSetting instead.

**Returns**: `System`

```
Get-VMHostAdvancedConfiguration
    [-Name <String[]>]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String[]` | No | Specifies the names of the host configuration settings you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts for which you want to retrieve the configuration settings. |

---

### Get-VMHostAuthentication

This cmdlet retrieves authentication information for the specified hosts.

**Returns**: `VMHostAuthentication`

```
Get-VMHostAuthentication
    -Id <String[]>
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the host authentication information that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that match... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve authentication information. |

---

### Get-VMHostAvailableTimeZone

This cmdlet retrieves the time zones available on the specified host.

**Returns**: `VMHostTimeZone`

```
Get-VMHostAvailableTimeZone
    [-Name <String[]>]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String[]` | No | Specifies the names of the available time zones you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host for which you want to retrieve the available time zones. |

---

### Get-VMHostDiagnosticPartition

This cmdlet retrieves a list of  the diagnostic partitions on the specified hosts.

This cmdlet retrieves a list of the diagnostic partitions on the specified hosts. The list is ordered by the partitions preference. Local diagnostic partitions are more preferable than shared diagnostic partitions because multiple servers cannot share the same partition. The most preferred diagnostic partition is first in the list.

**Returns**: `VMHostDiagnosticPartition`

```
Get-VMHostDiagnosticPartition
    [-All]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-All` | `SwitchParameter` | No | Indicates that you want to retrieve all diagnostic partitions on the specified hosts. By default, only the active partitions are retrieved. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts for which you want to retrieve diagnostic partitions. |

---

### Get-VMHostDisk

This cmdlet retrieves information about the specified SCSI LUN disk.

**Returns**: `VMHostDisk`

```
Get-VMHostDisk
    -Id <String[]>
    [-ScsiLun <ScsiLun[]>]
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the SCSI LUN disks that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of... |
| `-ScsiLun` | `ScsiLun[]` | No | Specifies the SCSI LUN for which you want to retrieve information. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies hosts to retrieve the hard disks attached to them. |

---

### Get-VMHostDiskPartition

This cmdlet retrieves the partitions of a host disk (LUN).

**Returns**: `VMHostDiskPartition`

```
Get-VMHostDiskPartition
    -Id <String[]>
    [-Server <VIServer[]>]
    [-VMHostDisk <VMHostDisk[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the host disk partitions that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHostDisk` | `VMHostDisk[]` | No | Specifies the host disk for which you want to retrieve the partitions. |

---

### Get-VMHostFirewallDefaultPolicy

This cmdlet retrieves the firewall default policy of the specified hosts.

This cmdlet retrieves the firewall default policy of the specified hosts. The firewall policy determines whether the outgoing and incoming connections are allowed.

**Returns**: `VMHostFirewallDefaultPolicy`

```
Get-VMHostFirewallDefaultPolicy
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts whose firewall default policy you want to retrieve. |

---

### Get-VMHostFirewallException

This cmdlet retrieves the exceptions from the firewall policy on the specified hosts.

This cmdlet retrieves the exceptions from the firewall policy on the specified hosts. The exceptions can be filtered using the VMHost, Name, Port, and Enabled parameters.

**Returns**: `VMHostFirewallException`

```
Get-VMHostFirewallException
    [-Enabled <Boolean>]
    [-Name <String[]>]
    [-Port <Int32[]>]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Enabled` | `Boolean` | No | Indicates whether you want to retrieve only the enabled hosts firewall exceptions. |
| `-Name` | `String[]` | No | Specifies the names of the firewall exceptions you want to retrieve. |
| `-Port` | `Int32[]` | No | Specifies the number of the port for which you want to retrieve the firewall exceptions. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts for which you want to retrieve firewall exceptions. |

---

### Get-VMHostFirmware

This cmdlet retrieves hosts firmware information.

This cmdlet retrieves firmware information for the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter. To run this cmdlet, you need to have the "Host.Config.Firmware" permission to the ESX.

**Returns**: `HostFirmware`

```
Get-VMHostFirmware
    [-BackupConfiguration]
    -DestinationPath <String>
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BackupConfiguration` | `SwitchParameter` | No | Indicates that you want to backup the host firmware configuration and download the bundle to the specified DestinationPath. |
| `-DestinationPath` | `String` | Yes | Specifies a destination path where to download the host configuration backup bundle if the BackupConfiguration parameter is set. |
| `-Server` | `VIServer[]` | No | This parameter is required when you specify the host by name. In this case, the host with the specified name is searched on the specified servers and firmware information is retrieved from it. If a... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts for which you want to retrieve firmware information. |

---

### Get-VMHostHardware

This cmdlet retrieves ESXi host hardware and firmware information.

This cmdlet retrieves hardware and firmware information for the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMHostHardware`

```
Get-VMHostHardware
    -Id <String[]>
    [-Server <VIServer[]>]
    [-SkipAllSslCertificateChecks]
    [-SkipCACheck]
    [-SkipCNCheck]
    [-SkipRevocationCheck]
    [-VMHost <VMHost[]>]
    [-WaitForAllData]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Filters the ESXi hosts by ID.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list. |
| `-Server` | `VIServer[]` | No | This parameter is required when you specify the host by name. In this case, the host with the specified name is searched on the specified servers and hardware information is retrieved from it. If a... |
| `-SkipAllSslCertificateChecks` | `SwitchParameter` | No | Indicates that all checks for SSL server certificates are skipped.   Note: You should use this parameter only for trusted computers. |
| `-SkipCACheck` | `SwitchParameter` | No | Indicates that when connecting through HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).   Note: You should use this parameter onl... |
| `-SkipCNCheck` | `SwitchParameter` | No | Indicates that the certificate common name (CN) of the server does not need to match the hostname of the server.   Note: You should use this parameter only for trusted computers. |
| `-SkipRevocationCheck` | `SwitchParameter` | No | Indicates that the revocation check for server certificates is skipped.   Note: You should use this parameter only for trusted computers. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve hardware information. If not specified, the cmdlet retrieves hardware information for all hosts on all default connections. |
| `-WaitForAllData` | `SwitchParameter` | No | If specified, forces all data for each result object to be retrieved before that object is returned. If this parameter is not specified, retrieval of some of the data in the output objects might be... |

---

### Get-VMHostHba

This cmdlet retrieves information about the available HBAs (Host Bus Adapter).

**Returns**: `Hba`

```
Get-VMHostHba
    [-Device <String[]>]
    [-Server <VIServer[]>]
    [-Type <HbaType[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Device` | `String[]` | No | Specifies the devices of the HBA you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `HbaType[]` | No | Specifies the type of the HBAs you want to retrieve. The valid values are Block, FibreChannel, iSCSI, and ParallelSCSI. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve HBAs. |

---

### Get-VMHostModule

This cmdlet retrieves the option strings of the specified host modules.

This cmdlet retrieves the option strings of the specified host modules. To specify a server different from the default one, use the Server parameter.

**Returns**: `VmHostModule`

```
Get-VMHostModule
    [-Name <String[]>]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String[]` | No | Specifies the names of the host modules you want to retrieve. To find a list of the valid module names for different servers, see the vSphere documentation or in the ESX console, run "esxcfg-module... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies hosts to retrieve their modules. |

---

### Get-VMHostNetwork

THis cmdlet retrieves the host networks on a vCenter Server system.

This cmdlet retrieves the host networks on a vCenter Server system. This command retrieves the networking configuration of the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMHostNetworkInfo`

```
Get-VMHostNetwork
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts whose networking configuration you want to retrieve. |

---

### Get-VMHostNetworkAdapter

This cmdlet retrieves the host network adapters on a vCenter Server system.

**Returns**: `HostVirtualNic`

```
Get-VMHostNetworkAdapter
    [-Console]
    [-Id <String[]>]
    [-Name <String[]>]
    [-Physical]
    [-PortGroup <VirtualPortGroupBase[]>]
    [-Server <VIServer[]>]
    [-VirtualSwitch <VirtualSwitchBase[]>]
    [-VMHost <VMHost[]>]
    [-VMKernel]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Console` | `SwitchParameter` | No | Indicates that you want to retrieve only service console virtual network adapters. |
| `-Id` | `String[]` | No | Specifies the IDs of the host network adapters you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one ... |
| `-Name` | `String[]` | No | Specifies the names of the host network adapters you want to retrieve. The position of this parameter is deprecated and will be changed in a future release. To avoid errors when you run existing sc... |
| `-Physical` | `SwitchParameter` | No | Indicates that you want to retrieve only physical network adapters. |
| `-PortGroup` | `VirtualPortGroupBase[]` | No | Specifies the port groups to which network adapters that you want to retrieve are connected. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualSwitch` | `VirtualSwitchBase[]` | No | Specifies the virtual switches to which network adapters that you want to retrieve are connected. The position of this parameter is deprecated and will be changed in a future release. To avoid erro... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts whose network adapters you want to retrieve. The position of this parameter is deprecated and might change in a following release. |
| `-VMKernel` | `SwitchParameter` | No | Indicates that you want to retrieve only VMKernel virtual network adapters. |

---

### Get-VMHostNetworkStack

This cmdlet retrieves the host network stacks on a vCenter Server system.

**Returns**: `HostNetworkStack`

```
Get-VMHostNetworkStack
    -Id <String[]>
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the host network stacks you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of... |
| `-Name` | `String[]` | No | Specifies the names of the host network stacks you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts whose network stacks you want to retrieve. |

---

### Get-VMHostNtpServer

This cmdlet retrieves the NTP servers on the specified hosts.

**Returns**: `String`

```
Get-VMHostNtpServer
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts, whose NTP servers you want to retrieve. |

---

### Get-VMHostPatch

This cmdlet retrieves information about the host patches installed on the specified hosts. This cmdlet is deprecated and will not return any results for ESX hosts version 5.0 and later. Use (Get-ESXCli).software.vib.list() as an alternative.

**Returns**: `VMHostPatch`

```
Get-VMHostPatch
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve the available patches. |

---

### Get-VMHostPciDevice

This cmdlet retrieves the PCI devices on the specified hosts.

**Returns**: `VMHostPciDevice`

```
Get-VMHostPciDevice
    [-DeviceClass <PciDeviceClass[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeviceClass` | `PciDeviceClass[]` | No | Limits results to devices of the specified classes. |
| `-Name` | `String[]` | No | Filters the PCI devices by name.   Note: This parameter is not case-sensitive. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts whose PCI devices you want to retrieve. If not specified, the cmdlet retrieves PCI devices for all hosts on all default connections. |

---

### Get-VMHostProfile

This cmdlet retrieves the available host profiles.

This cmdlet retrieves the available host profiles. A host profile encapsulates the host settings and helps to manage the host configuration.

**Returns**: `VMHostProfile`

```
Get-VMHostProfile
    [-Description <String[]>]
    [-Entity <InventoryItem[]>]
    [-Id <String[]>]
    [-Name <String[]>]
    [-ReferenceHost <VMHost[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Description` | `String[]` | No | Specifies a phrase from the description of the host profiles you want to retrieve. |
| `-Entity` | `InventoryItem[]` | No | Specifies inventory objects associated with the host profiles you want to retrieve. |
| `-Id` | `String[]` | No | Specifies the IDs of the host profiles you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the s... |
| `-Name` | `String[]` | No | Specifies the names of the host profiles you want to retrieve. |
| `-ReferenceHost` | `VMHost[]` | No | Specifies the reference hosts of the profiles you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VMHostProfileImageCacheConfiguration

Retrieves an image cache configuration for the given host profile.

Retrieves an image cache configuration for the given host profile. This configuration encapsulates the host image caching settings.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileImageCacheConfiguration[]`

```
Get-VMHostProfileImageCacheConfiguration
    -HostProfile <VMHostProfile[]>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostProfile` | `VMHostProfile[]` | Yes | Specifies the virtual machine host profile. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VMHostProfileRequiredInput

This cmdlet performs a check whether the available information is sufficient to apply a host profile.

This cmdlet performs a check whether the available information is sufficient to apply a host profile, and returns missing values. If the cmdlet returns no output, the information in the hashtable passed to the Variable parameter is sufficient to apply the host profile to the host by using the Apply-VMHostProfile cmdlet.

**Returns**: `VMHostProfileInput`

```
Get-VMHostProfileRequiredInput
    [-Inapplicable]
    [-Profile <VMHostProfile>]
    [-Server <VIServer[]>]
    [-Variable <Hashtable>]
    -VMHost <VMHost>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Inapplicable` | `SwitchParameter` | No | Indicates that you want to view also the elements that are inapplicable to the operation. |
| `-Profile` | `VMHostProfile` | No | Specifies a host profile to check if the provided information is sufficient for applying it to the specified host. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Variable` | `Hashtable` | No | Provides a hash table that contains the available values required for applying the specified profile to the the specified host. |
| `-VMHost` | `VMHost` | Yes | Specifies a host to check if the provided information is sufficient for applying the specified host profile. |

---

### Get-VMHostProfileStorageDeviceConfiguration

Retrieves the storage device configuration for the given host profile.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileStorageDeviceConfiguration[]`

```
Get-VMHostProfileStorageDeviceConfiguration
    [-DeviceName <String[]>]
    -HostProfile <VMHostProfile[]>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeviceName` | `String[]` | No | There can be multiple devices within a host profile. This parameter filters the result for a particular device. If no value is passed to this parameter, configurations are returned for all devices ... |
| `-HostProfile` | `VMHostProfile[]` | Yes | Specifies the virtual machine host profile. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VMHostProfileUserConfiguration

This cmdlet retrieves the user password configuration for the given host profile.

This cmdlet retrieves the user password configuration for the given host profile. The user password configuration encapsulates the hosts password policy type and password.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileUserConfiguration[]`

```
Get-VMHostProfileUserConfiguration
    -HostProfile <VMHostProfile[]>
    [-Server <VIServer[]>]
    [-UserName <String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostProfile` | `VMHostProfile[]` | Yes | virtual machine host profile |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-UserName` | `String[]` | No | There can be multiple accounts within a host profile. This parameter filters the result for a particular account. If no value is passed to this parameter, configurations are returned for all accoun... |

---

### Get-VMHostProfileVmPortGroupConfiguration

Retrieves the virtual machine port group configuration for the given host profile.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileVmPortGroupConfiguration[]`

```
Get-VMHostProfileVmPortGroupConfiguration
    -HostProfile <VMHostProfile[]>
    [-PortGroupName <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostProfile` | `VMHostProfile[]` | Yes | Specifies the virtual machine host profile. |
| `-PortGroupName` | `String[]` | No | Specifies the port group name that is unique for the host profile. The port group name can be passed to filter results for the particular port group. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VMHostRoute

This cmdlet retrieves the routes from the routing table of the specified hosts.

**Returns**: `VMHostRoute`

```
Get-VMHostRoute
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve routes. |

---

### Get-VMHostService

This cmdlet retrieves information about a host service.

This cmdlet retrieves information about a host service. If the Refresh parameter is set to $true, the cmdlet refreshes the host services information before retrieving it. To specify a server different from the default one, use the Server parameter.

**Returns**: `HostService`

```
Get-VMHostService
    [-Refresh]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Refresh` | `SwitchParameter` | No | Indicates whether the cmdlet refreshes the service information before retrieving it. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies hosts for which you want to retrieve the available services. |

---

### Get-VMHostSnmp

This cmdlet retrieves hosts SNMP configuration.

This cmdlet retrieves hosts SNMP configuration. To specify a server different from the default one, use the Server parameter.

**Returns**: `VmHostSnmp`

```
Get-VMHostSnmp
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VMHostStartPolicy

This cmdlet retrieves the start policy of hosts.

This cmdlet retrieves the start policy of the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMHostStartPolicy`

```
Get-VMHostStartPolicy
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts whose start policy you want to retrieve. |

---

### Get-VMHostStorage

This cmdlet retrieves the host storages on a vCenter Server system.

This cmdlet retrieves the host storages on a vCenter Server system. The cmdlet returns a list of the storages on the hosts specified by the VMHost parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMHostStorageInfo`

```
Get-VMHostStorage
    -Id <String[]>
    [-Refresh]
    [-RescanAllHba]
    [-RescanVmfs]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the host storages that you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of ... |
| `-Refresh` | `SwitchParameter` | No | Indicates whether the cmdlet refreshes the storage system information before retrieving the specified host storages. |
| `-RescanAllHba` | `SwitchParameter` | No | Indicates whether to issue a request to rescan all virtual machine hosts bus adapters for new storage devices prior to retrieving the storage information. |
| `-RescanVmfs` | `SwitchParameter` | No | Indicates whether to perform a re-scan for new virtual machine file systems that might have been added, prior to retrieving the storage information. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts for which you want to retrieve storage information. |

---

### Get-VMHostSysLogServer

This cmdlet displays the remote syslog servers of the specified hosts.

This cmdlet displays the remote syslog servers of the specified hosts. The returned object contains the server address and the port if configured.

**Returns**: `NamedIPEndPoint`

```
Get-VMHostSysLogServer
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host whose remote syslog server you want to display. |

---

### Import-VMHostProfile

This cmdlet imports a host profile from a file. The file path must be accessible from the VMware PowerCLI client side.

**Returns**: `VMHostProfile`

```
Import-VMHostProfile
    [-Description <String>]
    -FilePath <String>
    -Name <String>
    [-ReferenceHost <VMHost>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Description` | `String` | No | Specifies a description for the imported host profile. |
| `-FilePath` | `String` | Yes | Specifies the path to the file, from which you want to import a host profile. |
| `-Name` | `String` | Yes | Specifies a name of the imported host profile. |
| `-ReferenceHost` | `VMHost` | No | Specifies a reference host for the imported host profile. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Install-VMHostPatch

This cmdlet updates the specified hosts.

This cmdlet updates the specified hosts. The cmdlet installs patches on the host. The patches that can be located locally, on a Web location, or in a host file system. When using the LocalPath or WebPath parameters, the ESX/ESXi host attempts to store the patch contents in its local temporary directory. Because ESXi hosts might not have enough free space on their  local drives, this cannot apply to large size patches. The best practice for upgrading an ESXi host is to upload the patch content...

**Returns**: `VMHostPatchResult`

```
Install-VMHostPatch
    [-HostCredential <PSCredential>]
    [-HostPassword <SecureString>]
    -HostPath <String[]>
    [-HostUsername <String>]
    -LocalPath <String[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    -WebPath <String[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostCredential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the host. |
| `-HostPassword` | `SecureString` | No | Specifies the password you want to use to authenticate with the host. |
| `-HostPath` | `String[]` | Yes | Specifies a file path on the ESX/ESXi host to the patches you want to install. |
| `-HostUsername` | `String` | No | Specifies the username you want to use to authenticate with the host. |
| `-LocalPath` | `String[]` | Yes | Specifies the local file system path to the patches you want to install. Providing credentials when installing a patch from a local path is mandatory. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to update. |
| `-WebPath` | `String[]` | Yes | Specifies the Web location of the patches you want to install. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Invoke-VMHostProfile

This cmdlet applies a host profile to the specified host or cluster.

This cmdlet applies a host profile to the specified host or cluster. The host or cluster must be in a maintenance mode. If no value is provided to the Profile parameter, the profile currently associated with the  host or cluster is applied.

**Returns**: `VMHost`

```
Invoke-VMHostProfile
    [-ApplyOnly]
    [-AssociateOnly]
    -Entity <InventoryItem[]>
    [-Profile <VMHostProfile>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Variable <Hashtable>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApplyOnly` | `SwitchParameter` | No | Indicates whether to apply the host profile to the specified virtual machine host without associating it. |
| `-AssociateOnly` | `SwitchParameter` | No | Indicates whether to associate the host profile to the specified host or cluster without applying it. |
| `-Entity` | `InventoryItem[]` | Yes | Specifies hosts or clusters to which you want to apply the virtual machine host profile. |
| `-Profile` | `VMHostProfile` | No | Specifies the host profile you want to apply. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Variable` | `Hashtable` | No | Specifies a hash table object that provides values for the host profile required variables. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Move-VMHost

This cmdlet moves hosts to another location.

This cmdlet moves hosts to the location that is specified by the Destination parameter. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMHost`

```
Move-VMHost
    -Destination <VIContainer>
    [-RunAsync]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `VIContainer` | Yes | Specifies the location where you want to move the hosts. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to move to another location. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-DrsVMHostRule

This cmdlet creates a new VM to VMHost DRS rule.

**Returns**: `DrsVMHostRule`

```
New-DrsVMHostRule
    [-Cluster <Cluster>]
    [-Enabled <Boolean>]
    -Name <String>
    [-RunAsync]
    [-Server <VIServer[]>]
    -Type <DrsVMHostRuleType>
    -VMGroup <DrsClusterVMGroup>
    -VMHostGroup <DrsClusterVMHostGroup>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster` | No | Specifies the clusters on which you want to create the new rule. |
| `-Enabled` | `Boolean` | No | Specifies whether to enable the new rule. |
| `-Name` | `String` | Yes | Specifies the name for the new rule. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `DrsVMHostRuleType` | Yes | Specifies the type of the rule you want to create. This parameter accepts MustRunOn, ShouldRunOn, MustNotRunOn, and ShouldNotRunOn values. |
| `-VMGroup` | `DrsClusterVMGroup` | Yes | Specifies the VMGroup you want to use for the new rule. |
| `-VMHostGroup` | `DrsClusterVMHostGroup` | Yes | Specifies the VMHostGroup you want to use for the new rule. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VMHostAccount

This cmdlet creates a new host user or group account.

This cmdlet creates a new host user or group account using the provided parameters.

**Returns**: `HostUserAccount`

```
New-VMHostAccount
    [-AssignGroups <String[]>]
    [-AssignUsers <String[]>]
    [-Description <String>]
    [-GrantShellAccess]
    [-GroupAccount]
    -Id <String>
    -Password <String>
    [-Server <VIServer[]>]
    [-UserAccount]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AssignGroups` | `String[]` | No | If the UserAccount parameter is set to $true, use AssignGroups to specify the groups to which the newly created user belongs. |
| `-AssignUsers` | `String[]` | No | If the GroupAccount parameter is set to $true, use AssignUsers to specify the users that belong to the newly created group account. |
| `-Description` | `String` | No | Provide a description of the new host account. The maximum length of the text is 255 symbols. |
| `-GrantShellAccess` | `SwitchParameter` | No | Indicates that the new account is allowed to access the ESX shell. |
| `-GroupAccount` | `SwitchParameter` | No | Indicates that the new host account is a group account. Starting with ESXi 5.1, this parameter is not supported. |
| `-Id` | `String` | Yes | Specifies an ID for the new host account. |
| `-Password` | `String` | Yes | Specifies a password for the new host account. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-UserAccount` | `SwitchParameter` | No | Indicates that the new host account is a user account. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VMHostNetworkAdapter

This cmdlet creates a new HostVirtualNIC (Service Console or VMKernel) on the specified host.

This cmdlet creates a new HostVirtualNIC (Service Console or VMKernel) on the specified host. Creates a port group with a name specified by the PortGroup parameter on the virtual switch passed through the VirtualSwitch parameter. Adds either a Console NIC if ConsoleNIC is set, or a VMKernel NIC otherwise.

**Returns**: `HostVirtualNic`

```
New-VMHostNetworkAdapter
    [-AutomaticIPv6]
    [-ConsoleNic]
    [-FaultToleranceLoggingEnabled <Boolean>]
    [-IP <String>]
    [-IPv6 <String[]>]
    [-IPv6ThroughDhcp]
    [-Mac <String>]
    [-ManagementTrafficEnabled <Boolean>]
    [-Mtu <Int32>]
    [-PortGroup <String>]
    [-PortId <String>]
    [-Server <VIServer[]>]
    [-SubnetMask <String>]
    -VirtualSwitch <VirtualSwitchBase>
    [-VMHost <VMHost>]
    [-VMotionEnabled <Boolean>]
    [-VsanTrafficEnabled <Boolean>]
    -NetworkStack <HostNetworkStack>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutomaticIPv6` | `SwitchParameter` | No | Indicates that the IPv6 address is obtained through a router advertisement. |
| `-ConsoleNic` | `SwitchParameter` | No | If the value is $true, indicates that you want to create a service console virtual network adapter. If the value is $false, indicates that you want to create a virtual host/VMkernel network adapter... |
| `-FaultToleranceLoggingEnabled` | `Boolean` | No | Indicates that the network adapter is enabled for Fault Tolerance (FT) logging. This parameter is supported only on ESX/vCenter Server 4.1 and later. |
| `-IP` | `String` | No | Specifies an IP address for the new network adapter. All IP addresses are specified using IPv4 dot notation. If IP is not specified, DHCP mode is enabled. For VMKernel network adapters, the DHCP mo... |
| `-IPv6` | `String[]` | No | Specifies multiple static addresses using the following format: <IPv6>/<subnet_prefix_length> or <IPv6>. If you skip <subnet_prefix_length>, the default value of 64 is used. |
| `-IPv6ThroughDhcp` | `SwitchParameter` | No | Indicates that the IPv6 address is obtained through DHCP. |
| `-Mac` | `String` | No | Specifies a media access control (MAC) address for the new virtual network adapter. |
| `-ManagementTrafficEnabled` | `Boolean` | No | Indicates that you want to enable the network adapter for management traffic. This parameter is supported only on ESX/ESXi/vCenter Server 4.1 and later. |
| `-Mtu` | `Int32` | No | Specifies the MTU size. This parameter is supported only on ESX/vCenter Server 4.1 and later. |
| `-PortGroup` | `String` | No | Specifies the port group to which you want to add the new adapter. If a distributed switch is passed to the VirtualSwitch parameter, an existing port group name should be specified. For standard vi... |
| `-PortId` | `String` | No | Specifies the port of the specified distributed switch to which you want to connect the network adapter. Use this parameter only if a distributed switch is passed to the VirtualSwitch parameter. |
| `-Server` | `VIServer[]` | No | The Server parameter is required when the host is specified by name. In this case, the host with the specified name is searched for on the specified Servers and a network adapter is added to it. If... |
| `-SubnetMask` | `String` | No | Specifies a subnet mask for the new network adapter. |
| `-VirtualSwitch` | `VirtualSwitchBase` | Yes | Specifies the virtual switch to which you want to add the new network adapter. |
| `-VMHost` | `VMHost` | No | Specifies the host to which you want to add the new adapter. This parameter is mandatory when creating a network adapter on a distributed switch. |
| `-VMotionEnabled` | `Boolean` | No | Indicates that you want to use the new virtual host/VMKernel network adapter for VMotion. |
| `-VsanTrafficEnabled` | `Boolean` | No | Indicates that Virtual SAN traffic is enabled on this network adapter. |
| `-NetworkStack` | `HostNetworkStack` | Yes | Specifies the host network stack to which you want to add the new adapter. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VMHostProfile

This cmdlet creates a new  host profile based on a reference host.

This cmdlet creates a new host profile based on a reference host.

**Returns**: `VMHostProfile`

```
New-VMHostProfile
    [-CompatibilityMode]
    [-Description <String>]
    -Name <String>
    -ReferenceHost <VMHost>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CompatibilityMode` | `SwitchParameter` | No | If you are connected to a vCenter Server/ESX 5.0 or later, use this parameter to indicate that you want the new profile to be compatible with hosts running ESX/vCenter Server versions earlier than ... |
| `-Description` | `String` | No | Provides a description for the new host profile. |
| `-Name` | `String` | Yes | Specifies a name for the new host profile. |
| `-ReferenceHost` | `VMHost` | Yes | Specifies the reference host, on which the new virtual machine host profile is based. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VMHostProfileVmPortGroupConfiguration

This cmdlet creates a new virtual machine port group configuration.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileVmPortGroupConfiguration`

```
New-VMHostProfileVmPortGroupConfiguration
    -HostProfile <VMHostProfile>
    -PortGroupName <String>
    [-Server <VIServer[]>]
    [-VLanId <Int32>]
    -VSwitchName <String>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostProfile` | `VMHostProfile` | Yes | Specifies the virtual machine host profile. |
| `-PortGroupName` | `String` | Yes | Specifies the name of the new virtual machine port group configuration. This name is unique for the particual host profile. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VLanId` | `Int32` | No | Specifies the VLAN ID for the new configuration. |
| `-VSwitchName` | `String` | Yes | Specifies the virtual switch name for the new configuration. |

---

### New-VMHostRoute

This cmdlet creates a new route in the routing table of a host.

**Returns**: `VMHostRoute`

```
New-VMHostRoute
    -Destination <IPAddress>
    -Gateway <IPAddress>
    -PrefixLength <Int32>
    [-Server <VIServer[]>]
    -VMHost <VMHost>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `IPAddress` | Yes | Specifies a destination IP address for the new route. |
| `-Gateway` | `IPAddress` | Yes | Specifies a gateway IP address for the new route. |
| `-PrefixLength` | `Int32` | Yes | Specifies the prefix length of the destination IP address. For IPv4, the valid values are from 0 to 32, and for IPv6 - from 0 to 128. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost` | Yes | Specifies the host for which you want to create a new route. Passing multiple values to this parameter is obsolete. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-DrsVMHostRule

This cmdlet removes the specified VM to VMHost DRS rule.

**Returns**: `None`

```
Remove-DrsVMHostRule
    -Rule <DrsVMHostRule[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Rule` | `DrsVMHostRule[]` | Yes | Specifies the rules you want to remove. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VMHost

This cmdlet removes the specified hosts from the inventory.

**Returns**: `None`

```
Remove-VMHost
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VMHostAccount

This cmdlet removes the specified host accounts.

This cmdlet removes the specified host accounts . These can be  HostGroupAccount objects, HostUserAccount objects, or both.

**Returns**: `None`

```
Remove-VMHostAccount
    -HostAccount <HostAccount[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostAccount` | `HostAccount[]` | Yes | Specifies the host accounts you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VMHostNetworkAdapter

This cmdlet removes the specified host network adapters.

**Returns**: `None`

```
Remove-VMHostNetworkAdapter
    -Nic <HostVirtualNic[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Nic` | `HostVirtualNic[]` | Yes | Specifies the network adapters you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VMHostNtpServer

This cmdlet removes the specified NTP servers from the NTP server list of the specified hosts.

**Returns**: `None`

```
Remove-VMHostNtpServer
    -NtpServer <String[]>
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-NtpServer` | `String[]` | Yes | Specifies the NTP servers you want to remove from the NTP servers list of the specified host. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host whose NTP servers you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VMHostProfile

This cmdlet removes the specified host profiles.

This cmdlet removes the specified host profiles. If the Entity parameter is provided, the cmdlet removes the profile association for the specified entity. Otherwise, the cmdlet removes the profile object.

**Returns**: `None`

```
Remove-VMHostProfile
    -Entity <InventoryItem[]>
    -Profile <VMHostProfile[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `InventoryItem[]` | Yes | Specifies the host or cluster whose host profile association you want to remove. |
| `-Profile` | `VMHostProfile[]` | Yes | Specifies the host profiles you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VMHostProfileVmPortGroupConfiguration

Removes the given virtual machine port group configuration from the host profile.

**Returns**: `None`

```
Remove-VMHostProfileVmPortGroupConfiguration
    [-Server <VIServer[]>]
    -VmPortGroupConfiguration <VMHostProfileVmPortGroupConfiguration[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VmPortGroupConfiguration` | `VMHostProfileVmPortGroupConfiguration[]` | Yes | Specifies the configuration that you want to remove. |

---

### Remove-VMHostRoute

This cmdlet removes host routes.

**Returns**: `None`

```
Remove-VMHostRoute
    -VMHostRoute <VMHostRoute[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-VMHostRoute` | `VMHostRoute[]` | Yes | Specifies the host routes you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Restart-VMHost

This cmdlet restarts the specified hosts.

**Returns**: `VMHost`

```
Restart-VMHost
    [-Evacuate]
    [-Force]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
    [-Reason <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Evacuate` | `SwitchParameter` | No | Indicates that vCenter Server automatically reregisters the virtual machines that are compatible for reregistration. If they are not compatible, they remain on the rebooted host. If there are power... |
| `-Force` | `SwitchParameter` | No | Indicates that you want to restart the hosts even if they are not in a maintenance mode. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to restart. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-Reason` | `String` | No | Specifies a short message containing the reason for restarting the host. The message cannot be null or empty string. |

---

### Restart-VMHostService

This cmdlet restarts the specified host services.

**Returns**: `HostService`

```
Restart-VMHostService
    -HostService <HostService[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostService` | `HostService[]` | Yes | Specifies the host service you want to restart. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-DrsVMHostRule

This cmdlet modifies the specified VM to VMHost DRS rule.

**Returns**: `DrsVMHostRule`

```
Set-DrsVMHostRule
    [-Enabled <Boolean>]
    [-Name <String>]
    -Rule <DrsVMHostRule[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-Type <DrsVMHostRuleType>]
    [-VMGroup <DrsClusterVMGroup>]
    [-VMHostGroup <DrsClusterVMHostGroup>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Enabled` | `Boolean` | No | Specifies whether to activate or deactivate the modified rule. |
| `-Name` | `String` | No | Specifies the new name for the modified rule. |
| `-Rule` | `DrsVMHostRule[]` | Yes | Specifies the rules you want to modify. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `DrsVMHostRuleType` | No | Specifies the new type for the modified rule. |
| `-VMGroup` | `DrsClusterVMGroup` | No | Specifies the VMGroup you want to use for the modified rule. |
| `-VMHostGroup` | `DrsClusterVMHostGroup` | No | Specifies the VMHostGroup you want to use for the modified rule. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHost

This cmdlet modifies the configuration of the host.

**Returns**: `VMHost`

```
Set-VMHost
    [-BaseImage <BaseImage>]
    [-Component <Component[]>]
    [-DepotOverride <String[]>]
    -DisableCryptoSafe
    [-Evacuate]
    [-FirmwareAddon <Package>]
    -KeyProvider <KeyProvider>
    [-LicenseKey <String>]
    [-Profile <VMHostProfile>]
    [-Reason <String>]
    [-RemovedComponent <String[]>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-State <VMHostState>]
    [-TimeZone <VMHostTimeZone>]
    [-VendorAddOn <AddOn>]
    -VMHost <VMHost[]>
    [-VMSwapfileDatastore <Datastore>]
    [-VMSwapfilePolicy <VMSwapfilePolicy>]
    [-VsanDataMigrationMode <VsanDataMigrationMode>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BaseImage` | `BaseImage` | No | Specifies the ESXi base image that the host should comply with. |
| `-Component` | `Component[]` | No | Specifies the ESXi component(s) that the host should comply with. |
| `-DepotOverride` | `String[]` | No | Specifies a depot address from where the host can fetch metadata and resources for the vSphere Lifecycle Manager operations. |
| `-DisableCryptoSafe` | `SwitchParameter` | Yes | If the value is $true and the VMHost's previous CryptoState is Safe, the VMHost enters a PendingIncapable state. Otherwise, the VMHost remains in an Incapable state. For the PendingIncapable state,... |
| `-Evacuate` | `SwitchParameter` | No | If the value is $true, vCenter Server system automatically reregisters the virtual machines that are compatible for reregistration. If they are not compatible, they remain on the host. If there are... |
| `-FirmwareAddon` | `Package` | No | Specifies a package from a hardware support manager that the host should comply with. |
| `-KeyProvider` | `KeyProvider` | Yes | Specifies the key provider you want to use to make the VMHost cryptographically "Safe" or rekey the VMHost's host key. |
| `-LicenseKey` | `String` | No | Specifies the license key to be used by the host. You can set the host to evaluation mode by passing the 00000-00000-00000-00000-00000 evaluation key. |
| `-Profile` | `VMHostProfile` | No | Specifies a host profile you want to associate with the host. If the value of this parameter is $null, the current profile association is removed. |
| `-Reason` | `String` | No | Specifies a short message containing the reason for putting the host in maintenance mode. The message cannot be null or empty string. This parameter can only be used when passing "Maintenance" valu... |
| `-RemovedComponent` | `String[]` | No | Specifies a list of components that you want to remove from the base image.   Calling the commandlet with a new value for this parameter overrides any previously configured value. It does not add n... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-State` | `VMHostState` | No | Specifies the state of the host. The valid values are Connected, Disconnected, and Maintenance. If there are powered on virtual machines on the host, you can set the host into a maintenance mode, o... |
| `-TimeZone` | `VMHostTimeZone` | No | Specifies the time zone for the host by using its name or by providing the corresponding time zone object. Time zone names support wildcards. If the wildcards match more than one time zone, an erro... |
| `-VendorAddOn` | `AddOn` | No | Specifies the ESXi vendor add-on that the host should comply with. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host you want to configure. |
| `-VMSwapfileDatastore` | `Datastore` | No | Specifies a datastore that is visible to the host and can be used for storing swapfiles for the virtual machines that run on this host. Using a host-specific swap location might degrade the vMotion... |
| `-VMSwapfilePolicy` | `VMSwapfilePolicy` | No | Specifies the swapfile placement policy. The following values are valid:   InHostDataStore - stores the swapfile in the datastore specified by the VMSwapfileDatastoreID property of the virtual mach... |
| `-VsanDataMigrationMode` | `VsanDataMigrationMode` | No | Specifies the special action to take regarding the vSAN data when moving in maintenance mode. The VsanDataMigrationMode parameter is valid only when connected to a vCenter Server system and when th... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostAccount

This cmdlet configures a host account.

This cmdlet configures a host account. When configuring a host user account, you can include or exclude the user from the specified groups. When configuring a host group account, you can include or exclude the specified users from this group.

**Returns**: `HostUserAccount`

```
Set-VMHostAccount
    [-AssignGroups <String[]>]
    [-AssignUsers <String[]>]
    [-Description <String>]
    [-GrantShellAccess <Boolean>]
    -GroupAccount <HostGroupAccount[]>
    [-Password <String>]
    [-Server <VIServer[]>]
    [-UnassignGroups <String[]>]
    [-UnassignUsers <String[]>]
    -UserAccount <HostUserAccount[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AssignGroups` | `String[]` | No | If a user host account is to be configured, specifies the group to which you want to add the account. Starting with ESXi 5.1, you cannot configure group host accounts. |
| `-AssignUsers` | `String[]` | No | If a group host account is configured, specify the users you want to add to the account. Starting with ESXi 5.1, you cannot configure group host accounts. |
| `-Description` | `String` | No | Provides a description of the specified account. The maximum length of the text is 255 symbols. |
| `-GrantShellAccess` | `Boolean` | No | Indicates that the account is allowed to access the ESX shell. |
| `-GroupAccount` | `HostGroupAccount[]` | Yes | Specifies the host group account you want to configure. Starting with ESXi 5.1, you cannot configure group host accounts. |
| `-Password` | `String` | No | Specifies a new password for the account. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-UnassignGroups` | `String[]` | No | If a user host account is to be configured, specifies a group from which you want to remove the account. Starting with ESXi 5.1, you cannot configure group host accounts. |
| `-UnassignUsers` | `String[]` | No | If a group host account is to be configured, specifies the users you want to remove from the account. |
| `-UserAccount` | `HostUserAccount[]` | Yes | Specifies the host user account you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostAdvancedConfiguration

This cmdlet modifies the advanced configuration settings of a host.

This cmdlet is deprecated. Use New-AdvancedSetting, Set-AdvancedSetting, or Remove-AdvancedSetting instead.

**Returns**: `System`

```
Set-VMHostAdvancedConfiguration
    [-Name <String>]
    [-NameValue <Hashtable>]
    [-Server <VIServer[]>]
    [-Value <Object>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | No | Specifies the name of the host configuration setting you want to change. |
| `-NameValue` | `Hashtable` | No | Provides a hash table that maps values to settings. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Value` | `Object` | No | Specifies a new value of the host configuration setting that you want to modify. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host whose advanced configuration settings you want to change. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostAuthentication

This cmdlet modifies the host authentication information.

**Returns**: `VMHostAuthentication`

```
Set-VMHostAuthentication
    [-Credential <PSCredential>]
    -Domain <String>
    [-Force]
    -JoinDomain
    -LeaveDomain
    [-Password <SecureString>]
    [-Username <String>]
    -VMHostAuthentication <VMHostAuthentication[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `PSCredential` | No | Specifies a credential object for authentication. |
| `-Domain` | `String` | Yes | Specifies a domain you want to join. |
| `-Force` | `SwitchParameter` | No | If the value is $true, any existing permissions on the managed objects for Active Directory users are deleted and the cmdlet completes. If the value is $false, the cmdlet cannot run if there are an... |
| `-JoinDomain` | `SwitchParameter` | Yes | Indicates whether you want to join the specified domain. |
| `-LeaveDomain` | `SwitchParameter` | Yes | Indicates whether you want to leave the currently joined domain. |
| `-Password` | `SecureString` | No | Specifies a password for authentication. |
| `-Username` | `String` | No | Specifies a user name for authentication. |
| `-VMHostAuthentication` | `VMHostAuthentication[]` | Yes | Specifies the VMHostAuthentication object you want to modify. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostDiagnosticPartition

This cmdlet activates or deactivates the diagnostic partitions of  hosts.

This cmdlet activates or deactivates the diagnostic partitions of hosts.

**Returns**: `VMHostDiagnosticPartition`

```
Set-VMHostDiagnosticPartition
    -Active <Boolean>
    -VMHostDiagnosticPartition <VMHostDiagnosticPartition[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Active` | `Boolean` | Yes | If the value of this parameter is $true, the partition state is changed to active. If the value is $false, the partition state is set to inactive. |
| `-VMHostDiagnosticPartition` | `VMHostDiagnosticPartition[]` | Yes | Specifies the host diagnostic partition you want to set. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostFirewallDefaultPolicy

This cmdlet sets the default policy for the specified host firewall.

This cmdlet sets the default policy for the specified host firewall. This policy specifies whether outgoing or incoming connections are allowed. At least one of the AllowIncoming and AllowOutgoing parameters must be set. When you configure the default firewall policy of an ESX/ESXi host version 5.0, you must provide the same value for the AllowIncoming and AllowOutgoing parameters.

**Returns**: `VMHostFirewallDefaultPolicy`

```
Set-VMHostFirewallDefaultPolicy
    [-AllowIncoming <Boolean>]
    [-AllowOutgoing <Boolean>]
    -Policy <VMHostFirewallDefaultPolicy[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowIncoming` | `Boolean` | No | If the value of this parameter is $true, all incoming connections are allowed. If the value is $false, all incoming connections are disallowed. |
| `-AllowOutgoing` | `Boolean` | No | If the value of this parameter is $true, all outcoming connections are allowed. If the value is $false, all outcoming connections are disallowed. |
| `-Policy` | `VMHostFirewallDefaultPolicy[]` | Yes | Specifies the host firewall default policy you want to apply. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostFirewallException

This cmdlet activates or deactivates host firewall exceptions.

**Returns**: `VMHostFirewallException`

```
Set-VMHostFirewallException
    -Enabled <Boolean>
    -Exception <VMHostFirewallException[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Enabled` | `Boolean` | Yes | If the value is $true, the specified firewall exceptions are activated. If the value is $false, the firewall exceptions are deactivated. |
| `-Exception` | `VMHostFirewallException[]` | Yes | Specifies the firewall exceptions you want to activate or deactivate. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostFirmware

This cmdlet configures hosts firmware settings.

This cmdlet configures hosts firmware settings. If the BackupConfiguration parameter is set, backups the host configuration and downloads the bundle to the specified DestinationPath. In order to use the Restore and ResetToDefaults parameters, the host needs to be in maintenance mode. The Backup functionality of Set-VMHostFirmware is deprecated and scheduled for removal. For making backups, use the Get-VMHostFirmware cmdlet instead.

**Returns**: `HostFirmware`

```
Set-VMHostFirmware
    [-BackupConfiguration]
    -DestinationPath <String>
    [-Force]
    [-HostCredential <PSCredential>]
    [-HostPassword <SecureString>]
    [-HostUser <String>]
    [-ResetToDefaults]
    [-Restore]
    [-Server <VIServer[]>]
    [-SourcePath <String>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BackupConfiguration` | `SwitchParameter` | No | The Backup functionality of Set-VMHostFirmware is deprecated and scheduled for removal. For making backups, use the Get-VMHostFirmware cmdlet instead.   Indicates that you want to backup the host f... |
| `-DestinationPath` | `String` | Yes | Specifies a destination path where to download the host configuration backup bundle if the BackupConfiguration parameter is set. |
| `-Force` | `SwitchParameter` | No | Indicates that you want to apply the configuration even if the bundle is mismatched. Use this parameter in combination with the Restore parameter. |
| `-HostCredential` | `PSCredential` | No | Specifies the credential object you want to use for authenticating with the host when uploading a firmware configuration bundle. Do not use this parameter if the HostUser and HostPassword parameter... |
| `-HostPassword` | `SecureString` | No | Specifies a password for the authenticating with the host when uploading a firmware configuration bundle. |
| `-HostUser` | `String` | No | Specifies a username for authenticating with the host when uploading a firmware configuration bundle. |
| `-ResetToDefaults` | `SwitchParameter` | No | Indicates that you want to reset all configuration settings, including the "admin" password, to the factory defaults. The host is rebooted immediately. The host needs to be in a maintenance in orde... |
| `-Restore` | `SwitchParameter` | No | Indicates that you want to restore the configuration of the host to the one that is specified in the provided bundle. The bundle is uploaded to the URL retrieved via Get-VMHostFirmware. This method... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SourcePath` | `String` | No | Specifies the path to the host configuration backup bundle you want to restore. The bundle is uploaded to an URL address which you can retrieve by using the Get-VMHostFirmware cmdlet. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host whose firmware you want to configure (it must be an ESX visor). |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostHba

This cmdlet configures the CHAP properties of the specified iSCSI HBAs.

This cmdlet configures the CHAP properties of the specified iSCSI HBAs. If (Mutual)ChapType is set to a value different than "Prohibited", (Mutual)ChapPassword must be set. ChapType, MutualChapType, MutualChapName, MutualChapPassword - these are only available on 4.1 or later. Note: Run Set-VmHostHba directly against ESX. When Set-VmHostHba is run against vCenter Server, changing the iScsiName property of an iSCSI adapter modifies its AuthenticationCapabilities property.

**Returns**: `IScsiHba`

```
Set-VMHostHba
    [-ChapName <String>]
    [-ChapPassword <String>]
    [-ChapType <ChapType>]
    -IScsiHba <IScsiHba[]>
    [-IScsiName <String>]
    [-MutualChapEnabled <Boolean>]
    [-MutualChapName <String>]
    [-MutualChapPassword <String>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ChapName` | `String` | No | Specifies the CHAP initiator name if CHAP is enabled. |
| `-ChapPassword` | `String` | No | Specifies the CHAP password if CHAP is enabled. |
| `-ChapType` | `ChapType` | No | Specifies the type of the CHAP authorization. The valid values are Prohibited, Discouraged, Preferred, and Required. |
| `-IScsiHba` | `IScsiHba[]` | Yes | Specifies the iSCSI HBA device you want to configure. |
| `-IScsiName` | `String` | No | Specifies a new name for the host HBA device. |
| `-MutualChapEnabled` | `Boolean` | No | Indicates that Mutual CHAP authorization is enabled. |
| `-MutualChapName` | `String` | No | Specifies the Mutual CHAP initiator name if Mutual CHAP is enabled. |
| `-MutualChapPassword` | `String` | No | Specifies the Mutual CHAP password if Mutual CHAP is enabled. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostModule

This cmdlet overrides the host module options with the given ones.

**Returns**: `VmHostModule`

```
Set-VMHostModule
    -HostModule <VmHostModule[]>
    -Options <String>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostModule` | `VmHostModule[]` | Yes | Specifies the host module you want to configure. |
| `-Options` | `String` | Yes | Specifies the new options of the host module. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostNetwork

This cmdlet updates the specified virtual network.

This cmdlet updates the specified virtual network. The service console and the VMkernel are often not connected to the same network, and therefore each needs its own gateway information. A gateway is needed for connectivity to machines not on the same IP subnet as the service console or VMkernel.

**Returns**: `VMHostNetworkInfo`

```
Set-VMHostNetwork
    [-ConsoleGateway <String>]
    [-ConsoleGatewayDevice <String>]
    [-ConsoleV6Gateway <String>]
    [-ConsoleV6GatewayDevice <String>]
    [-DnsAddress <String[]>]
    [-DnsDhcpDevice <Object>]
    [-DnsFromDhcp <Boolean>]
    [-DomainName <String>]
    [-HostName <String>]
    [-IPv6Enabled <Boolean>]
    -Network <VMHostNetworkInfo[]>
    [-SearchDomain <String[]>]
    [-VMKernelGateway <String>]
    [-VMKernelGatewayDevice <String>]
    [-VMKernelV6Gateway <String>]
    [-VMKernelV6GatewayDevice <String>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ConsoleGateway` | `String` | No | Specifies a new console gateway. |
| `-ConsoleGatewayDevice` | `String` | No | Specifies a new console gateway device. |
| `-ConsoleV6Gateway` | `String` | No | Specifies a console V6 gateway address. Not supported on ESXi. |
| `-ConsoleV6GatewayDevice` | `String` | No | Specifies a console V6 gateway device. Not supported on ESXi. |
| `-DnsAddress` | `String[]` | No | Specifies a new DNS address. |
| `-DnsDhcpDevice` | `Object` | No | This parameter is mandatory if the value of the DnsFromDhcp parameter is 'true'. Otherwise, it is disregarded. If the DnsDhcpDevice parameter is set, the Dhcp DNS of the service console or VMKernel... |
| `-DnsFromDhcp` | `Boolean` | No | Indicates that you want to obtain the network settings from a Dhcp server. |
| `-DomainName` | `String` | No | Specifies a new domain name. |
| `-HostName` | `String` | No | Specifies a new host name. |
| `-IPv6Enabled` | `Boolean` | No | Indicates that IPv6 configuration is enabled. Setting this parameter to $false deactivates the ConsoleV6Gateway, ConsoleV6GatewayDevice, and VMKernelV6Gateway parameters. IPv6 is supported only on ... |
| `-Network` | `VMHostNetworkInfo[]` | Yes | Specifies the host network you want to configure. |
| `-SearchDomain` | `String[]` | No | Specifies a new search domain. |
| `-VMKernelGateway` | `String` | No | Specifies a new kernel gateway. |
| `-VMKernelGatewayDevice` | `String` | No | Specifies a new kernel gateway device. |
| `-VMKernelV6Gateway` | `String` | No | Specifies a VMKernel V6 gateway address. This parameter is supported only on ESX hosts. |
| `-VMKernelV6GatewayDevice` | `String` | No | Specifies a VMKernel V6 gateway device. This parameter is supported only on ESX hosts. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostNetworkAdapter

This cmdlet configures the specified host network adapter.

This cmdlet configures the specified host network adapter. For a physical NIC, you can change the duplex and the bit rate settings (10, 100, 1000, 10000). For a regular virtual NIC, you can change the IP address and the subnet mask. For a console virtual NIC, you can modify the IP and the subnet mask, or choose DHCP mode.

**Returns**: `HostNic`

```
Set-VMHostNetworkAdapter
    [-AutomaticIPv6 <Boolean>]
    [-AutoNegotiate]
    [-BitRatePerSecMb <Int32>]
    [-Dhcp]
    [-Duplex <String>]
    [-FaultToleranceLoggingEnabled <Boolean>]
    [-IP <String>]
    [-IPv6 <String[]>]
    [-IPv6Enabled <Boolean>]
    [-IPv6ThroughDhcp <Boolean>]
    [-Mac <String>]
    [-ManagementTrafficEnabled <Boolean>]
    [-Mtu <Int32>]
    -PhysicalNic <PhysicalNic[]>
    -PortGroup <DistributedPortGroup>
    [-SubnetMask <String>]
    -VirtualNic <HostVirtualNic[]>
    [-VMotionEnabled <Boolean>]
    [-VsanTrafficEnabled <Boolean>]
    [-ProvisioningEnabled <Boolean>]
    [-VSphereReplicationEnabled <Boolean>]
    [-VSphereReplicationNfcEnabled <Boolean>]
    [-VSphereBackupNfcEnabled <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutomaticIPv6` | `Boolean` | No | Indicates that the IPv6 address is obtained through a router advertisement. |
| `-AutoNegotiate` | `SwitchParameter` | No | Indicates that the host network adapter speed/duplex settings are configured automatically. Use this parameter only if the Duplex and BitRatePerSecMb parameters are not set. |
| `-BitRatePerSecMb` | `Int32` | No | Specifies the bit rate of the link. Only valid when configuring a physical NIC. Use this parameter only if the AutoNegotiate parameter is not set. Note that updating the speed (BitRatePerSec) of a ... |
| `-Dhcp` | `SwitchParameter` | No | Indicates whether the host network adapter uses a Dhcp server. This parameter works only on ESXi hosts. For VMKernel adapters, Dhcp is supported only on ESX 4.1 and later. |
| `-Duplex` | `String` | No | Indicates whether the link is capable of full-duplex. The valid values are Full and Half. You can set this parameter only when updating a PhysicalNIC. Use this parameter only if the AutoNegotiate p... |
| `-FaultToleranceLoggingEnabled` | `Boolean` | No | Indicates that the network adapter is enabled for Fault Tolerance (FT) logging. This parameter is supported only on ESX/vCenter Server 4.1 and later. |
| `-IP` | `String` | No | Specifies an IP address for the network adapter using an IPv4 dot notation. If the NIC has no subnet mask previously defined, you must also set the SubnetMask parameter. If the IP parameter is not ... |
| `-IPv6` | `String[]` | No | Specifies static addresses using the following format: <IPv6>/<subnet_prefix_length> or <IPv6>. If you skip <subnet_prefix_length>, the default value of 64 is used. Specifying a value for IPv6 para... |
| `-IPv6Enabled` | `Boolean` | No | Indicates that IPv6 configuration is enabled. Setting this parameter to $false deactivates all IPv6-related parameters. If the value is $true", you need to provide values for at least one of the IP... |
| `-IPv6ThroughDhcp` | `Boolean` | No | Indicates that the IPv6 address is obtained through DHCP. |
| `-Mac` | `String` | No | Specifies the media access control (MAC) address of the virtual network adapter. Only valid when configuring a virtual NIC. |
| `-ManagementTrafficEnabled` | `Boolean` | No | Indicates that you want to enable the network adapter for management traffic. This parameter is supported only on ESX/ESXi/vCenter Server 4.1 and later. |
| `-Mtu` | `Int32` | No | Specifies the MTU size. |
| `-PhysicalNic` | `PhysicalNic[]` | Yes | Specifies the PhysicalNIC objects you want to update. |
| `-PortGroup` | `DistributedPortGroup` | Yes | Specifies a distributed port group to which you want to connect the host network adapter. You can use this parameter only to migrate a virtual network adapter from a standard port group to a distri... |
| `-SubnetMask` | `String` | No | Specifies a subnet mask for the NIC. If the NIC has a subnet mask previously defined, specifying the SubnetMask parameter when configuring the IP address is not mandatory unless you want to modify ... |
| `-VirtualNic` | `HostVirtualNic[]` | Yes | Provide a list of the host network adapters you want to configure. |
| `-VMotionEnabled` | `Boolean` | No | Indicates that you want to use the virtual host/VMKernel network adapter for VMotion. |
| `-VsanTrafficEnabled` | `Boolean` | No | Specifies whether Virtual SAN traffic is enabled on this network adapter. |
| `-ProvisioningEnabled` | `Boolean` | No | Specifies whether vSphere Provisioning is enabled on this network adapter. |
| `-VSphereReplicationEnabled` | `Boolean` | No | Specifies whether vSphere Replication traffic is enabled on this network adapter. |
| `-VSphereReplicationNfcEnabled` | `Boolean` | No | Specifies whether vSphere Replication Network File Copy (NFC) traffic is enabled on this network adapter. |
| `-VSphereBackupNfcEnabled` | `Boolean` | No | Specifies whether backup through NFC is enabled on this network adapter. This parameter is supported in vSphere 7.0 and later. |
| `-Confirm` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostNetworkStack

This cmdlet modifies the specified host network stack.

This cmdlet configures the specified host network stack.

**Returns**: `HostNetworkStack`

```
Set-VMHostNetworkStack
    [-CongestionControlAlgoritm <HostNetworkStackCongestionControlAlgoritm>]
    [-DnsAddress <String[]>]
    [-DnsFromDhcp <Boolean>]
    [-DomainName <String>]
    [-HostName <String>]
    [-MaxNumberOfConnections <Int32>]
    [-Name <String>]
    -NetworkStack <HostNetworkStack[]>
    [-SearchDomain <String[]>]
    [-VMKernelGateway <String>]
    [-VMKernelV6Gateway <String>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CongestionControlAlgoritm` | `HostNetworkStackCongestionControlAlgoritm` | No | Specifies the TCP congest control algorithm used by the network stack. |
| `-DnsAddress` | `String[]` | No | Specifies the IP addresses of the DNS servers, placed in order of preference.   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set. |
| `-DnsFromDhcp` | `Boolean` | No | Specifies whether or not DHCP (dynamic host control protocol) is used to determine DNS configuration automatically. |
| `-DomainName` | `String` | No | Specifies the domain name portion of the DNS name. For example, "vmware.com".   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set. |
| `-HostName` | `String` | No | Specifies the host name portion of DNS name. For example, "esx01".   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be set. |
| `-MaxNumberOfConnections` | `Int32` | No | Specifies the maximum number of socket connections that can be requested on the network stack. |
| `-Name` | `String` | No | Specifies a new name for the network stack. |
| `-NetworkStack` | `HostNetworkStack[]` | Yes | Specifies the network stack that you want to configure. |
| `-SearchDomain` | `String[]` | No | Specifies the domain in which to search for hosts, placed in order of preference.   Note: When DHCP is not enabled, the property can be set explicitly. When DHCP is enabled, the property cannot be ... |
| `-VMKernelGateway` | `String` | No | Specifies an IP address for the default gateway using an IPv4 dot notation. |
| `-VMKernelV6Gateway` | `String` | No | Specifies the default IPv6 gateway using the following format: <IPv6>/<subnet_prefix_length> or <IPv6>. If you skip <subnet_prefix_length>, the default value of 64 is used. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostProfile

This cmdlet modifies the specified host profile.

**Returns**: `VMHostProfile`

```
Set-VMHostProfile
    [-Description <String>]
    [-Name <String>]
    -Profile <VMHostProfile[]>
    [-ReferenceHost <VMHost>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Description` | `String` | No | Specifies a new description for the host profile. |
| `-Name` | `String` | No | Specifies a new name for the host profile. |
| `-Profile` | `VMHostProfile[]` | Yes | Specifies the host profile you want to modify. |
| `-ReferenceHost` | `VMHost` | No | Specifies a reference host for the host profile. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostProfileImageCacheConfiguration

This cmdlet modifies image cache configuration for given host profile.

This cmdlet modifies the image cache configuration for the given host profile.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileImageCacheConfiguration[]`

```
Set-VMHostProfileImageCacheConfiguration
    [-DiskArguments <String>]
    [-IgnoreSsd <Boolean>]
    -ImageCacheConfiguration <VMHostProfileImageCacheConfiguration[]>
    [-InstallationDevice <VMHostProfileInstallationDevice>]
    -InstallationType <VMHostProfileInstallationType>
    [-OverwriteVmfs <Boolean>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DiskArguments` | `String` | No | Specify a comma-separated list of disks that you want to use based on your order of preference. You can specify more than one disk. Default value is the local disk for this argument. |
| `-IgnoreSsd` | `Boolean` | No | Excludes solid-state disks from eligibility. |
| `-ImageCacheConfiguration` | `VMHostProfileImageCacheConfiguration[]` | Yes | Specifies the configuration that you want to modify. |
| `-InstallationDevice` | `VMHostProfileInstallationDevice` | No | Specifies the installation device that can be either on a host (Disk) or on a USB disk. |
| `-InstallationType` | `VMHostProfileInstallationType` | Yes | Specifies the installation type that can be either stateless caching or statefull install. |
| `-OverwriteVmfs` | `Boolean` | No | Allows the system to overwrite existing VMFS volumes, if the space is not enough to store the image. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Set-VMHostProfileStorageDeviceConfiguration

This cmdlet modifies the storage device configuration for the given host profile.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileStorageDeviceConfiguration[]`

```
Set-VMHostProfileStorageDeviceConfiguration
    [-ConfigInfo <String>]
    [-DeviceStateOn <Boolean>]
    [-IsPerenniallyReserved <Boolean>]
    [-IsSharedClusterwide <Boolean>]
    [-NumReqOutstanding <Int32>]
    [-PspName <String>]
    [-QueueFullSampleSize <Int32>]
    [-QueueFullThreshold <Int32>]
    [-Server <VIServer[]>]
    -StorageDeviceConfiguration <VMHostProfileStorageDeviceConfiguration[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ConfigInfo` | `String` | No | Speicifies configuration information for the device. |
| `-DeviceStateOn` | `Boolean` | No | Specifies if the device state is switched On. |
| `-IsPerenniallyReserved` | `Boolean` | No | Specifies if the device is perennially reserved. |
| `-IsSharedClusterwide` | `Boolean` | No | Specifies if the device is shared clusterwide. |
| `-NumReqOutstanding` | `Int32` | No | Specifies the maximum number of outstanding disk requests. |
| `-PspName` | `String` | No | Specifies the path selection plug-in name. |
| `-QueueFullSampleSize` | `Int32` | No | Specifies the queue full sample size value. |
| `-QueueFullThreshold` | `Int32` | No | Specifies the queue full threshhold value. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StorageDeviceConfiguration` | `VMHostProfileStorageDeviceConfiguration[]` | Yes | Specifies the configuration that you want to modify. |

---

### Set-VMHostProfileUserConfiguration

This cmdlet modifies the user password configuration for the specified account within a host profile.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileUserConfiguration[]`

```
Set-VMHostProfileUserConfiguration
    [-Password <String>]
    -PasswordPolicy <VMHostProfilePasswordPolicy>
    [-Server <VIServer[]>]
    -UserConfiguration <VMHostProfileUserConfiguration[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Password` | `String` | No | Specifies the user account password. This parameter is required in case of fixed password policy. |
| `-PasswordPolicy` | `VMHostProfilePasswordPolicy` | Yes | Specifies the desired password policy type. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-UserConfiguration` | `VMHostProfileUserConfiguration[]` | Yes | Specifies the user configuration that you want to modify. |

---

### Set-VMHostProfileVmPortGroupConfiguration

This cmdlet modifies the virtual machine port group configuration for the given host profile.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Host.Profile.VMHostProfileVmPortGroupConfiguration[]`

```
Set-VMHostProfileVmPortGroupConfiguration
    [-Server <VIServer[]>]
    [-VLanId <Int32>]
    -VmPortGroupConfiguration <VMHostProfileVmPortGroupConfiguration[]>
    [-VSwitchName <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VLanId` | `Int32` | No | Specifies the VLAN ID for the port group. |
| `-VmPortGroupConfiguration` | `VMHostProfileVmPortGroupConfiguration[]` | Yes | Specifies the configuration that you want to modify. |
| `-VSwitchName` | `String` | No | Specifies the virtual switch name for the port group. |

---

### Set-VMHostRoute

This cmdlet modifies a route in the host routing table.

**Returns**: `VMHostRoute`

```
Set-VMHostRoute
    [-Destination <IPAddress>]
    [-Gateway <IPAddress>]
    [-PrefixLength <Int32>]
    -VMHostRoute <VMHostRoute[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Destination` | `IPAddress` | No | Changes the destination IP address of the route. |
| `-Gateway` | `IPAddress` | No | Changes the gateway IP address of the route. |
| `-PrefixLength` | `Int32` | No | Modifies the prefix length of the destination IP address. For IPv4, the valid values are from 0 to 32, and for IPv6 - from 0 to 128. |
| `-VMHostRoute` | `VMHostRoute[]` | Yes | Specifies the route you want to modify. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostService

This cmdlet modifies a host service.

**Returns**: `HostService`

```
Set-VMHostService
    -HostService <HostService[]>
    -Policy <HostServicePolicy>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostService` | `HostService[]` | Yes | Specifies the host service you want to update. |
| `-Policy` | `HostServicePolicy` | Yes | Specifies an activation policy for the host service. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostSnmp

This cmdlet modifies the host SNMP configuration.

This cmdlet modifies the host SNMP configuration. If specified, adds or removes a trap target (removing can be specified by either TrapTargetToRemove parameter or by any of the following parameters (or combination of them): TargetCommunity, TargetHost, TargetPort). If the user passes $null, an empty array or string to the ReadOnlyCommunities parameter,  the old values of this property are erased. This results in a NULL value of this property of the output object.

**Returns**: `VmHostSnmp`

```
Set-VMHostSnmp
    -AddTarget
    [-Enabled <Boolean>]
    -HostSnmp <VmHostSnmp[]>
    [-Port <Int32>]
    [-ReadOnlyCommunity <String[]>]
    -RemoveTarget
    -TargetCommunity <String>
    -TargetHost <String>
    [-TargetPort <Int32>]
    -TrapTargetToRemove <TrapTarget>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AddTarget` | `SwitchParameter` | Yes | Indicates that you want to add a new trap target to the host SNMP configuration. A trap target consists of three elements - Community (mandatory), HostName (mandatory), Port (optional - defaults to... |
| `-Enabled` | `Boolean` | No | Indicates that the SNMP feature is enabled on the specified host. |
| `-HostSnmp` | `VmHostSnmp[]` | Yes | Specifies the host Snmp object you want to modify. |
| `-Port` | `Int32` | No | Specifies the port on which the host listens to SNMP messages. |
| `-ReadOnlyCommunity` | `String[]` | No | Provide a list of communities, identifying who is able to send SNMP requests to that host. If $null, an empty array or string are passed to this parameter, its old values are erased and the output ... |
| `-RemoveTarget` | `SwitchParameter` | Yes | Indicates that you want to remove a trap target from the host SNMP configuration. There are two ways to specify a trap target: * Pass the trap target to the TrapTargetToRemove parameter.   * Use a ... |
| `-TargetCommunity` | `String` | Yes | Specifies the community identifier of the trap target. |
| `-TargetHost` | `String` | Yes | Specifies the identifier of the target host - a host name or an IP address. |
| `-TargetPort` | `Int32` | No | Specifies the port on which the target host listens to SNMP messages. |
| `-TrapTargetToRemove` | `TrapTarget` | Yes | Specifies the trap target you want to remove. The trap target can be obtained from the "TrapTargets" property of the HostSNMP object (an array of TrapTarget objects). |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostStartPolicy

This cmdlet modifies the host default start policy.

This cmdlet modifies the host default start policy. Start policy defines what happens to virtual machines when the server starts up or stops.

**Returns**: `VMHostStartPolicy`

```
Set-VMHostStartPolicy
    [-Enabled <Boolean>]
    [-StartDelay <Int32>]
    [-StopAction <VmStopAction>]
    [-StopDelay <Int32>]
    -VMHostStartPolicy <VMHostStartPolicy[]>
    [-WaitForHeartBeat <Boolean>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Enabled` | `Boolean` | No | Indicates that the service that controls the host start policies is enabled. If it is enabled, the default start policies and the start policies of the specified hosts are applied. If deactivated, ... |
| `-StartDelay` | `Int32` | No | Specifies a default start delay of the virtual machines in seconds. |
| `-StopAction` | `VmStopAction` | No | Specifies the default action that is applied to the virtual machines when the server stops. The valid values are None, Suspend, PowerOff, or GuestShutDown. |
| `-StopDelay` | `Int32` | No | Specifies a default stop delay of the virtual machines in seconds. |
| `-VMHostStartPolicy` | `VMHostStartPolicy[]` | Yes | Specifies the host start policy you want to modify. |
| `-WaitForHeartBeat` | `Boolean` | No | Specifies whether the virtual machines should start after receiving a heartbeat from the host, ignore heartbeats, and start after the StartDelay has elapsed ($true), or follow the system default be... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostStorage

This cmdlet configures a host storage.

This cmdlet configures a host storage. The cmdlet activates or deactivates the software iSCSI support for the specified VMHostStorage objects.

**Returns**: `VMHostStorageInfo`

```
Set-VMHostStorage
    -SoftwareIScsiEnabled <Boolean>
    -VMHostStorage <VMHostStorageInfo[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-SoftwareIScsiEnabled` | `Boolean` | Yes | Indicates that on this storage, software iSCSI is enabled. |
| `-VMHostStorage` | `VMHostStorageInfo[]` | Yes | Specifies the host storage you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMHostSysLogServer

This cmdlet configures the remote syslog server of the specified hosts.

**Returns**: `NamedIPEndPoint`

```
Set-VMHostSysLogServer
    [-Server <VIServer[]>]
    [-SysLogServer <NamedIPEndPoint[]>]
    [-SysLogServerPort <Int32>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SysLogServer` | `NamedIPEndPoint[]` | No | Specifies the sys log servers you want to configure. The parameter accepts objects of the NamedIPEndPoint, IPEndPoint, IPAddress, and String types. The accepted formats, if string is used, are DNS ... |
| `-SysLogServerPort` | `Int32` | No | Specifies the sys log server port. Must be specified if the string that is passed to the SysLogServer parameter does not contain the port value, or the argument of the SysLogServer is an IP address. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host whose syslog servers you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Start-VMHost

This cmdlet starts the specified hosts.

This cmdlet starts the specified hosts. The task completes when the host successfully exits standby state and sends a heartbeat signal. If nothing is received from the host for the time defined by the TimeoutSeconds parameter, the host is declared timed out, and the task is assumed failed.

**Returns**: `VMHost`

```
Start-VMHost
    [-RunAsync]
    [-Server <VIServer[]>]
    [-TimeoutSeconds <Int32>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TimeoutSeconds` | `Int32` | No | Specifies a time period in seconds to wait for a heartbeat signal from the host. If nothing is received from the host for the specified time, the host is declared timed out, and the task is assumed... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to start. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Start-VMHostService

This cmdlet starts the specified host services.

**Returns**: `HostService`

```
Start-VMHostService
    -HostService <HostService[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostService` | `HostService[]` | Yes | Specifies the host services you want to start. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Stop-VMHost

This cmdlet powers off the specified hosts.

This cmdlet powers off the specified hosts. When the cmdlet runs asynchronously (with the RunAsync parameter) and you are connected directly to the host, the returned task object contains no indicator of success.

**Returns**: `VMHost`

```
Stop-VMHost
    [-Force]
    [-RunAsync]
    [-Server <VIServer[]>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
    [-Reason <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `SwitchParameter` | No | Indicates that you want to stop the hosts even if they are not in a maintenance mode. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to power off. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-Reason` | `String` | No | Specifies a short message containing the reason for stopping the host. The message cannot be null or empty string. |

---

### Stop-VMHostService

This cmdlet stops the specified host services.

This cmdlet stops the host service specified by the Service parameter.

**Returns**: `HostService`

```
Stop-VMHostService
    -HostService <HostService[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostService` | `HostService[]` | Yes | Specifies the host services you want to stop. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Suspend-VMHost

This cmdlet suspends hosts.

This cmdlet puts the specified host machines in standby mode. You can use the suspend feature to make resources available on a short-term basis or for other situations in which you want to put a host on hold without powering it off.

**Returns**: `VMHost`

```
Suspend-VMHost
    [-Evacuate]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-TimeoutSeconds <Int32>]
    -VMHost <VMHost[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Evacuate` | `SwitchParameter` | No | If the value is $true, vCenter Server automatically reregisters the virtual machines that are compatible for reregistration. If they are not compatible, they remain on the suspended host. If there ... |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TimeoutSeconds` | `Int32` | No | Specifies a time period in seconds to wait for the host to enter standby mode. If the host is not suspended for the specified time, the host is declared timed out, and the task is assumed failed. T... |
| `-VMHost` | `VMHost[]` | Yes | Specifies the hosts you want to suspend. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Test-VMHostProfileCompliance

This cmdlet tests hosts for profile compliance.

This cmdlet tests hosts for profile compliance. The Profile and VMHost parameters cannot be set at the same time. If the Profile parameter is set, the specified host profile is tested for compliance with the hosts, to which it is associated. If the VMHost parameter is specified, the host is tested for compliance with the profiles associated with it. If no profiles are associated with the host, then the profile associated with the cluster is applied.

**Returns**: `VMHostProfileIncompliance`

```
Test-VMHostProfileCompliance
    -Profile <VMHostProfile[]>
    [-Server <VIServer[]>]
    [-UseCache]
    -VMHost <VMHost[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Profile` | `VMHostProfile[]` | Yes | Specifies a host profile against which to test the specified host for compliance with the host to which it is associated. Do not set this parameter if the VMHost parameter is set. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-UseCache` | `SwitchParameter` | No | Indicates that you want the vCenter Server to return cached information. If vCenter Server does not have cached information, a compliance scanning is performed. |
| `-VMHost` | `VMHost[]` | Yes | Specifies the host you want to test for profile compliance with the profile associated with it. If no profile is associated with it, the host is tested for compliance with the profile associated wi... |

---

### Test-VMHostSnmp

This cmdlet tests the host SNMP.

This cmdlet tests the host SNMP specified by the HostSNMP parameter.

**Returns**: `VmHostSnmp`

```
Test-VMHostSnmp
    -HostSnmp <VmHostSnmp[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-HostSnmp` | `VmHostSnmp[]` | Yes | Specifies the host SNMP you want to test. |

---

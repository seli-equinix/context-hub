---
name: powercli-advanced
description: "VMware PowerCLI 13.3 — advanced settings, licensing, VApp, host profiles, OSCustomization, and other cmdlets"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Export-VM,Get-AdvancedSetting,Get-ApplianceBackupJob,Get-ApplianceBackupPart,Get-ESX,Get-EsxTop,Get-EventType,Get-IScsiHbaTarget,Get-LcmHardwareCompatibility,Get-LcmImage,Get-Log,Get-LogType,Get-Metric,Get-NicTeamingPolicy,Get-OSCustomizationNicMapping,Get-OSCustomizationSpec,Get-PowerCLIDocumentation,Get-SecurityPolicy,Get-VC,Get-VIAccount,Get-VIOAuth2Client,Get-VIPermission,Get-VIPrivilege,Get-VIPrivilegeReport,Get-VIRole,Get-VIServer,Get-VIToolkitConfiguration,Get-VIToolkitVersion,Get-VirtualNetwork,HookGetViewAutoCompleter,New-AdvancedSetting,New-ApplianceBackupJob,New-IScsiHbaTarget,New-LcmOfflineDepot,New-OSCustomizationNicMapping,New-OSCustomizationSpec,New-VIOAuth2Client,New-VIPermission,New-VIRole,New-VISamlSecurityContext,Open-VMConsoleWindow,Remove-AdvancedSetting,Remove-IScsiHbaTarget,Remove-OSCustomizationNicMapping,Remove-OSCustomizationSpec,Remove-VIOAuth2Client,Remove-VIPermission,Remove-VIRole,Set-AdvancedSetting,Set-IScsiHbaTarget,Set-NicTeamingPolicy,Set-OSCustomizationNicMapping,Set-OSCustomizationSpec,Set-SecurityPolicy,Set-VIOAuth2Client,Set-VIPermission,Set-VIRole,Set-VIToolkitConfiguration,Set-VMQuestion,Start-VIOAuth2ClientSecretRotation,Stop-ApplianceBackupJob,TabExpansion2,Wait-ApplianceBackupJob"
---

# VMware PowerCLI — advanced settings, licensing, VApp, host profiles, OSCustomization, and other cmdlets

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Export-VM` | This cmdlet exports a vApp or a single virtual machine to the specified destination. |
| `Get-AdvancedSetting` | This cmdlet retrieves the advanced settings for the specified entity. |
| `Get-ApplianceBackupJob` | This cmdlet retrieves a list of backup jobs for a vCenter Server system. |
| `Get-ApplianceBackupPart` | This cmdlet retrieves backup parts that can be included in a backup for a vCenter Server system. |
| `Get-ESX` | This cmdlet establishes a connection to a vCenter Server system. |
| `Get-EsxTop` | This cmdlet exposes the esxtop functionality. |
| `Get-EventType` | This cmdlet retrieves the available event types on a vCenter Server system. |
| `Get-IScsiHbaTarget` | This cmdlet retrieves the available iSCSI HBA targets. |
| `Get-LcmHardwareCompatibility` | This cmdlet verifies that the components in the base image are compatible with all storage contro... |
| `Get-LcmImage` | This cmdlet retrieves the vSphere Lifecycle Manager images available on a vCenter Server system. |
| `Get-Log` | This cmdlet retrieves entries from vSphere logs. |
| `Get-LogType` | This cmdlet retrieves information about the log types available on a virtual machine host. |
| `Get-Metric` | This cmdlet retrieves the available metrics on a vCenter Server system. |
| `Get-NicTeamingPolicy` | This cmdlet retrieves the NIC teaming policies of the specified virtual switches and virtual port... |
| `Get-OSCustomizationNicMapping` | This cmdlet retrieves the configured NIC setting mappings for the specified OS customization spec... |
| `Get-OSCustomizationSpec` | This cmdlet retrieves the OS customization specifications available on a vCenter Server system. |
| `Get-PowerCLIDocumentation` | Get-PowerCLIHelp |
| `Get-SecurityPolicy` | This cmdlet retrieves the security policy for virtual port groups or the default port security po... |
| `Get-VC` | This cmdlet establishes a connection to a vCenter Server system. |
| `Get-VIAccount` | This cmdlet retrieves the accounts from the ESX/ESXi or vCenter Server. |
| `Get-VIOAuth2Client` | This cmdlet retrieves the OAuth2 clients available on a vCenter Server system. |
| `Get-VIPermission` | This cmdlet retrieves the permissions defined on the specified inventory objects. |
| `Get-VIPrivilege` | This cmdlet retrieves the privilege groups and items for the provided servers. |
| `Get-VIPrivilegeReport` | This cmdlet records the privilege checks that occur for the specified sessions during the executi... |
| `Get-VIRole` | This cmdlet retrieves all roles defined on the provided servers. |
| `Get-VIServer` | This cmdlet establishes a connection to a vCenter Server system. |
| `Get-VIToolkitConfiguration` | This cmdlet retrieves the VMware PowerCLI proxy configuration and default servers policy. |
| `Get-VIToolkitVersion` | This cmdlet retrieves the versions of the installed PowerCLI snapins. |
| `Get-VirtualNetwork` | The cmdlet retrieves all virtual networks on a vCenter server system. |
| `HookGetViewAutoCompleter` | HookGetViewAutoCompleter |
| `New-AdvancedSetting` | This cmdlet creates a new advanced setting for the specified entity. |
| `New-ApplianceBackupJob` | This cmdlet starts a backup job for a vCenter Server system. |
| `New-IScsiHbaTarget` | This cmdlet creates a new iSCSI HBA target. |
| `New-LcmOfflineDepot` | This cmdlet creates a new vSphere Lifecycle Manager offline depot. |
| `New-OSCustomizationNicMapping` | This cmdlet adds NIC settings mappings to the specified OS customization specifications. |
| `New-OSCustomizationSpec` | This cmdlet creates a new OS customization specification. |
| `New-VIOAuth2Client` | Creates a new OAuth2 client registration with the VMware Identity Broker. |
| `New-VIPermission` | This cmdlet creates new permissions on the specified inventory objects for the provided users and... |
| `New-VIRole` | This cmdlet creates a new role on the specified servers and applies the provided privileges. |
| `New-VISamlSecurityContext` | Creates an SAML2 security context object that can be used to authenticate a user with any VMware ... |
| `Open-VMConsoleWindow` | This cmdlet opens a window to the virtual machine's console. |
| `Remove-AdvancedSetting` | This cmdlet removes the specified advanced setting. |
| `Remove-IScsiHbaTarget` | This cmdlet removes targets from their iSCSI HBAs. |
| `Remove-OSCustomizationNicMapping` | This cmdlet removes the specified OS customization NIC mappings. |
| `Remove-OSCustomizationSpec` | This cmdlet removes the specified OS customization specifications. |
| `Remove-VIOAuth2Client` | Deletes a registration for a specified OAuth2 client from the VMware Identity Broker. |
| `Remove-VIPermission` | This cmdlet removes the specified permissions. |
| `Remove-VIRole` | This cmdlet removes the specified roles. |
| `Set-AdvancedSetting` | This cmdlet modifies the specified advanced setting. |
| `Set-IScsiHbaTarget` | This cmdlet modifies the configuration of an iSCSI HBA target. |
| `Set-NicTeamingPolicy` | This cmdlet modifies the specified NIC teaming policy. |
| `Set-OSCustomizationNicMapping` | This cmdlet modifies the provided OS customization NIC mappings. |
| `Set-OSCustomizationSpec` | This cmdlet modifies the specified OS customization specification. |
| `Set-SecurityPolicy` | This cmdlet modifies the security policy for virtual port groups or the default port security pol... |
| `Set-VIOAuth2Client` | Updates the configuration of the OAuth2 client registered with the VMware Identity Broker. |
| `Set-VIPermission` | This cmdlet modifies the properties of the specified permissions. |
| `Set-VIRole` | This cmdlet modifies the privileges of the provided roles. |
| `Set-VIToolkitConfiguration` | This cmdlet modifies the VMware PowerCLI configuration. |
| `Set-VMQuestion` | This cmdlet answers the specified virtual machine question. |
| `Start-VIOAuth2ClientSecretRotation` | Initiates a rotation of the secret of an OAuth 2 client. |
| `Stop-ApplianceBackupJob` | This cmdlet stops running backup jobs on a vCenter Server system. |
| `TabExpansion2` | TabExpansion2 [-inputScript] <string> [-cursorColumn] <int> [[-options] <hashtable>] [<CommonPara... |
| `Wait-ApplianceBackupJob` | This cmdlet monitors the progress of a backup job and returns the ApplianceBackupJob object when ... |

---

### Export-VM

This cmdlet exports a vApp or a single virtual machine to the specified destination.

This cmdlet exports a vApp or a single virtual machine to the specified destination. If no destination is specified, the cmdlet creates a new folder in the current working directory and exports the vApp or the virtual machine to it. The name of the new folder is the same as the name of the vApp or the virtual machine as it appears in vCenter Server.

**Returns**: `FileInfo`

```
Export-VM
    [-CreateSeparateFolder]
    [-Description <String>]
    [-Destination <String>]
    [-Force]
    [-Format <VAppStorageFormat>]
    [-Name <String>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-SHAAlgorithm <SHAAlgorithm>]
    -VApp <VApp[]>
    -VM <VirtualMachine[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CreateSeparateFolder` | `SwitchParameter` | No | Indicates that you want to create a separate folder for each vApp or virtual machine. |
| `-Description` | `String` | No | Provides a description of the exported vApp or virtual machine. |
| `-Destination` | `String` | No | Specifies a destination path to the file system location where you want to export the vApp or the virtual machine. If the value of the Destination parameter is a folder, the vApp or the virtual mac... |
| `-Force` | `SwitchParameter` | No | Indicates that the cmdlet overwrites the existing destination files and creates directories to complete the specified file path. |
| `-Format` | `VAppStorageFormat` | No | Specifies the file format of the specified vApp or virtual machine. The default format is OVF. The valid values are OVF and OVA. |
| `-Name` | `String` | No | Specifies a name for the exported vApp or virtual machine. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is given to this parameter, the command runs on the default servers. For more information about default servers... |
| `-SHAAlgorithm` | `SHAAlgorithm` | No | Specifies the hashing algorithm that you want to use in the manifest checksums. The default value is SHA256. The valid values are SHA256 and SHA1. |
| `-VApp` | `VApp[]` | Yes | Specifies the vApp that you want to export. |
| `-VM` | `VirtualMachine[]` | Yes | Specifies the virtual machine that you want to export. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-AdvancedSetting

This cmdlet retrieves the advanced settings for the specified entity.

**Returns**: `AdvancedSetting`

```
Get-AdvancedSetting
    -Entity <VIObject[]>
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObject[]` | Yes | Specifies the entities for which you want to retrieve the advanced settings. This parameter accepts VIServer, VirtualMachine, VMHost, DatastoreCluster, and Cluster objects. |
| `-Name` | `String[]` | No | Specifies the names of the advanced settings you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-ApplianceBackupJob

This cmdlet retrieves a list of backup jobs for a vCenter Server system.

This cmdlet retrieves a list of finished or currently running backup jobs.

**Returns**: `ApplianceBackupJob`

```
Get-ApplianceBackupJob
    [-EndDate <DateTime>]
    [-Id <String[]>]
    [-Server <VIServer[]>]
    [-StartDate <DateTime>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-EndDate` | `DateTime` | No | Retrieves backup jobs with end time later than the provided time. |
| `-Id` | `String[]` | No | Retrieves backup jobs whose IDs match the specified IDs. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StartDate` | `DateTime` | No | Retrieves backup jobs with start time later than the provided time. |

---

### Get-ApplianceBackupPart

This cmdlet retrieves backup parts that can be included in a backup for a vCenter Server system.

Retrieves a list of parts that can be included in a backup job, and their estimated backup size. Non-optional backup parts are always included in the backup.

**Returns**: `ApplianceBackupPart`

```
Get-ApplianceBackupPart
    -Id <String[]>
    [-Name <String[]>]
    [-OptionalOnly]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Retrieves only those backup parts whose IDs match the provided IDs. |
| `-Name` | `String[]` | No | Retrieves only those backup parts whose names match the provided names. |
| `-OptionalOnly` | `SwitchParameter` | No | Returns optional backup parts only. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-ESX

This cmdlet establishes a connection to a vCenter Server system.

This cmdlet establishes a connection to a vCenter Server system. The cmdlet starts a new session or re-establishes a previous session with a vCenter Server system using the specified parameters.

**Returns**: `VIServer`

```
Get-ESX
    [-AllLinked]
    [-Credential <PSCredential>]
    [-Force]
    -Menu
    [-NotDefault]
    [-Password <String>]
    [-Port <Int32>]
    [-Protocol <String>]
    -SamlSecurityContext <SamlSecurityContext>
    [-SaveCredentials]
    -Server <String[]>
    [-Session <String>]
    [-User <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllLinked` | `SwitchParameter` | No | Indicates whether you want to connect to vCenter Server in linked mode. If you specify $true for the AllLinked parameter and the server to which you want to connect is a part of a federation vCente... |
| `-Credential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the server. For more information about the server authentication logic of PowerCLI, run "help about_server_authenti... |
| `-Force` | `SwitchParameter` | No | Suppresses all user interface prompts during the cmdlet execution. Currently, these include 'Multiple default servers' and 'Invalid certificate action'. |
| `-Menu` | `SwitchParameter` | Yes | Indicates that you want to select a connection server from a list of recently connected servers. If Menu is set to $true, the cmdlet retrieves a list of the last visited servers and enters a nested... |
| `-NotDefault` | `SwitchParameter` | No | Indicates that you do not want to include the server to which you connect into the $defaultVIServers variable. |
| `-Password` | `String` | No | Specifies the password you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentica... |
| `-Port` | `Int32` | No | Specifies the port on the server you want to use for the connection. |
| `-Protocol` | `String` | No | Specifies the Internet protocol you want to use for the connection. It can be either http or https. |
| `-SamlSecurityContext` | `SamlSecurityContext` | Yes | Specifies the SAML2 security context for the vCenter Server system. For more information about security contexts, see the about_security_context (about_security_context.html)article. |
| `-SaveCredentials` | `SwitchParameter` | No | Indicates that you want to save the specified credentials in the local credential store.   Note: This parameter is not supported on the Core edition of PowerShell. |
| `-Server` | `String[]` | Yes | Specifies the IP address or the DNS name of the vSphere server to which you want to connect. You can also specify a server by providing its IPv6 address enclosed in square brackets, for example [fe... |
| `-Session` | `String` | No | Specifies the ID of an existing vCenter Server session you want to re-establish. |
| `-User` | `String` | No | Specifies the user name you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentic... |

---

### Get-EsxTop

This cmdlet exposes the esxtop functionality.

This cmdlet exposes the esxtop functionality. The default parameter set is CounterValues. The Counter parameter filters the specified statistics. To retrieve all available counters, use the CounterInfo parameter set. The properties of each counter are returned through the Fields property (an array) of the CounterInfo output object. You can also retrieve stats topologies using the TopogyInfo parameter set. This information contains either inventory data that does not change or a counter instan...

**Returns**: `Counter`

```
Get-EsxTop
    -Counter
    [-CounterName <String[]>]
    [-Server <VIServer[]>]
    [-Topology <String[]>]
    -TopologyInfo
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Counter` | `SwitchParameter` | Yes | Indicates that you want to retrieve counters information. |
| `-CounterName` | `String[]` | No | Specifies the name of the counter for which you want to retrieve information. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Topology` | `String[]` | No | Specifies the topologies for which you want to retrieve information. |
| `-TopologyInfo` | `SwitchParameter` | Yes | Indicates that you want to retrieve topologies of the statistics. |

---

### Get-EventType

This cmdlet retrieves the available event types on a vCenter Server system.

This cmdlet retrieves the available event types on a vCenter Server system. The cmdlet returns a set of event types that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.EventType`

```
Get-EventType
    [-Category <EventCategory>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `EventCategory` | No | Specifies the category of the event type that you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vSphere servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information ... |

---

### Get-IScsiHbaTarget

This cmdlet retrieves the available iSCSI HBA targets.

This cmdlet retrieves the available iSCSI HBA targets. The cmdlet retrieves the configured targets (send and static) on the specified iSCSI storage adapters. If IPEndPoint is specified, filters the result by <Address>:<Port>. If no IScsiHba is provided - retrieves all targets from the entire inventory.

**Returns**: `IScsiHbaSendTarget`

```
Get-IScsiHbaTarget
    [-IPEndPoint <String[]>]
    [-IScsiHba <IScsiHba[]>]
    [-Server <VIServer[]>]
    [-Type <IScsiHbaTargetType[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-IPEndPoint` | `String[]` | No | Specifies <Address>:<Port> to filter the available iSCSI HBA targets. |
| `-IScsiHba` | `IScsiHba[]` | No | Specifies the iSCSI HBA whose targets you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `IScsiHbaTargetType[]` | No | Specifies the type of the iSCSI HBA targets you want to retrieve. The valid values are Send and Static. |

---

### Get-LcmHardwareCompatibility

This cmdlet verifies that the components in the base image are compatible with all storage controllers on the hosts in the cluster in accordance with the VMware Compatibility Guide.

This cmdlet verifies that the components in the base image are compatible with all vSAN storage controllers on the hosts in the cluster in accordance with the VMware Compatibility Guide. vSphere Lifecycle Manager scans the base image and checks whether the physical I/O device controllers are compatible with the specified ESXi version. Compatibility is checked for the vSAN storage controllers only.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Lcm.LcmHardwareCompatibility`

```
Get-LcmHardwareCompatibility
    -Cluster <Cluster[]>
    [-RunAsync]
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Cluster` | `Cluster[]` | Yes | Specifies the name of the cluster to check for hardware compatibility. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the name of the host to check for hardware compatibility. |

---

### Get-LcmImage

This cmdlet retrieves the vSphere Lifecycle Manager images available on a vCenter Server system.

This cmdlet retrieves the vSphere Lifecycle Manager images available on a vCenter Server system. The cmdlet returns a set of vSphere Lifecycle Manager images that correspond to the filter criteria specified by the provided parameters. To specify a server different from the default one, use the -Server parameter.

**Returns**: `LcmImage`

```
Get-LcmImage
    [-Category <LcmImageCategory[]>]
    -Id <String[]>
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Type <LcmImageType>]
    [-Version <String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `LcmImageCategory[]` | No | Specifies the categories of the vSphere Lifecycle Manager images you want to retrieve. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the vSphere Lifecycle Manager images you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects have an ID that matches exactly... |
| `-Name` | `String[]` | No | Specifies the names of the vSphere Lifecycle Manager images you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `LcmImageType` | No | Specifies the type of the vSphere Lifecycle Manager images you want to retrieve.   Note: LcmImageType is a flag enumeration. If you want to pass multiple image types, you might use "-bor" to group ... |
| `-Version` | `String[]` | No | Specifies the versions of the vSphere Lifecycle Manager images you want to retrieve. |

---

### Get-Log

This cmdlet retrieves entries from vSphere logs.

This cmdlet retrieves entries from vSphere logs. Returns portions of the log files according to the criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `Log`

```
Get-Log
    [-Bundle]
    -DestinationPath <String>
    -Key <String[]>
    [-NumLines <Int32>]
    [-RunAsync]
    [-Server <VIServer[]>]
    [-StartLineNum <Int32>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Bundle` | `SwitchParameter` | No | Indicates whether to retrieve a diagnostic bundle of logs from vCenter Server. |
| `-DestinationPath` | `String` | Yes | Specifies a local file path where you want to save the log bundle. |
| `-Key` | `String[]` | Yes | Specifies the key identifier of the log file you want to retrieve. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release. |
| `-NumLines` | `Int32` | No | Specifies the number of the lines you want to retrieve from the logs. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter r... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StartLineNum` | `Int32` | No | Specifies the start line number for reading from the logs. |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts for which you want to retrieve logs. If no value is given to this parameter, the command returns logs only for the default vCenter Server system. |

---

### Get-LogType

This cmdlet retrieves information about the log types available on a virtual machine host.

This cmdlet retrieves information about the log types available on a virtual machine host. If no virtual machine host is specified, the cmdlet retrieves the log types for the default vCenter Server system. To specify a server different from the default one, use the Server parameter.

**Returns**: `LogDescriptor`

```
Get-LogType
    [-Server <VIServer[]>]
    [-VMHost <VMHost[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VMHost` | `VMHost[]` | No | Specifies the hosts you want to search for log types. If no value is given to this parameter, the command searches for logs only on the default vCenter Server system. |

---

### Get-Metric

This cmdlet retrieves the available metrics on a vCenter Server system.

This cmdlet retrieves the available metrics on a vCenter Server system. The cmdlet returns a set of metrics that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Metric`

```
Get-Metric
    [-MetricGroup <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-MetricGroup` | `String[]` | No | Specifies the metric groups of the metrics that you want to retrieve. |
| `-Name` | `String[]` | No | Specifies the names of the metrics that you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vSphere servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information ... |

---

### Get-NicTeamingPolicy

This cmdlet retrieves the NIC teaming policies of the specified virtual switches and virtual port groups.

This cmdlet retrieves the NIC teaming policies of the specified virtual switches and virtual port groups. The NIC teaming policy determines how network traffic is distributed between adapters and how traffic is reorganized in case of adapter failure.

**Returns**: `NicTeamingVirtualSwitchPolicy`

```
Get-NicTeamingPolicy
    [-Server <VIServer[]>]
    -VirtualPortGroup <VirtualPortGroup[]>
    -VirtualSwitch <VirtualSwitch[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualPortGroup` | `VirtualPortGroup[]` | Yes | Specifies the port groups whose NIC teaming policy you want to retrieve. |
| `-VirtualSwitch` | `VirtualSwitch[]` | Yes | Specifies the virtual switches whose NIC teaming policy you want to retrieve. |

---

### Get-OSCustomizationNicMapping

This cmdlet retrieves the configured NIC setting mappings for the specified OS customization specification.

**Returns**: `OSCustomizationNicMapping`

```
Get-OSCustomizationNicMapping
    -OSCustomizationSpec <OSCustomizationSpec[]>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-OSCustomizationSpec` | `OSCustomizationSpec[]` | Yes | Specifies the OS customization specification for which you want to retrieve the NIC settings mapping. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-OSCustomizationSpec

This cmdlet retrieves the OS customization specifications available on a vCenter Server system.

This cmdlet retrieves the OS customization specifications available on a vCenter Server system. To specify a server different from the default one, use the Server parameter.

**Returns**: `OSCustomizationSpec`

```
Get-OSCustomizationSpec
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-Type <OSCustomizationSpecType>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the OS customization specifications you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches ex... |
| `-Name` | `String[]` | No | Specifies the names of the OS customization specifications you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `OSCustomizationSpecType` | No | Specifis the type of the OS customization specifications you want to retrieve. The valid values are Persistent and NonPersistent. |

---

### Get-PowerCLIDocumentation

Get-PowerCLIHelp

**Returns**: `returnValue`

```
Get-PowerCLIDocumentation
```

---

### Get-SecurityPolicy

This cmdlet retrieves the security policy for virtual port groups or the default port security policy for virtual switches.

**Returns**: `VirtualSwitchSecurityPolicy`

```
Get-SecurityPolicy
    [-Server <VIServer[]>]
    -VirtualPortGroup <VirtualPortGroup[]>
    -VirtualSwitch <VirtualSwitch[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VirtualPortGroup` | `VirtualPortGroup[]` | Yes | Specifies a virtual port group for which you want to retrieve the security policy. |
| `-VirtualSwitch` | `VirtualSwitch[]` | Yes | Specifies a virtual switch for which you want to retrieve the default port security policy. |

---

### Get-VC

This cmdlet establishes a connection to a vCenter Server system.

This cmdlet establishes a connection to a vCenter Server system. The cmdlet starts a new session or re-establishes a previous session with a vCenter Server system using the specified parameters.

**Returns**: `VIServer`

```
Get-VC
    [-AllLinked]
    [-Credential <PSCredential>]
    [-Force]
    -Menu
    [-NotDefault]
    [-Password <String>]
    [-Port <Int32>]
    [-Protocol <String>]
    -SamlSecurityContext <SamlSecurityContext>
    [-SaveCredentials]
    -Server <String[]>
    [-Session <String>]
    [-User <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllLinked` | `SwitchParameter` | No | Indicates whether you want to connect to vCenter Server in linked mode. If you specify $true for the AllLinked parameter and the server to which you want to connect is a part of a federation vCente... |
| `-Credential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the server. For more information about the server authentication logic of PowerCLI, run "help about_server_authenti... |
| `-Force` | `SwitchParameter` | No | Suppresses all user interface prompts during the cmdlet execution. Currently, these include 'Multiple default servers' and 'Invalid certificate action'. |
| `-Menu` | `SwitchParameter` | Yes | Indicates that you want to select a connection server from a list of recently connected servers. If Menu is set to $true, the cmdlet retrieves a list of the last visited servers and enters a nested... |
| `-NotDefault` | `SwitchParameter` | No | Indicates that you do not want to include the server to which you connect into the $defaultVIServers variable. |
| `-Password` | `String` | No | Specifies the password you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentica... |
| `-Port` | `Int32` | No | Specifies the port on the server you want to use for the connection. |
| `-Protocol` | `String` | No | Specifies the Internet protocol you want to use for the connection. It can be either http or https. |
| `-SamlSecurityContext` | `SamlSecurityContext` | Yes | Specifies the SAML2 security context for the vCenter Server system. For more information about security contexts, see the about_security_context (about_security_context.html)article. |
| `-SaveCredentials` | `SwitchParameter` | No | Indicates that you want to save the specified credentials in the local credential store.   Note: This parameter is not supported on the Core edition of PowerShell. |
| `-Server` | `String[]` | Yes | Specifies the IP address or the DNS name of the vSphere server to which you want to connect. You can also specify a server by providing its IPv6 address enclosed in square brackets, for example [fe... |
| `-Session` | `String` | No | Specifies the ID of an existing vCenter Server session you want to re-establish. |
| `-User` | `String` | No | Specifies the user name you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentic... |

---

### Get-VIAccount

This cmdlet retrieves the accounts from the ESX/ESXi or vCenter Server.

This cmdlet retrieves the accounts from the ESX/ESXi or vCenter Server. The Group and User switch parameters let you retrieve group and user accounts. By default, the cmdlet lists only user accounts. If the Domain parameter is specified, the cmdlet retrieves only the accounts on the specified AD domain. Otherwise, only local accounts are listed.

**Returns**: `VIAccount`

```
Get-VIAccount
    [-Domain <String>]
    [-Group]
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
    [-User]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Domain` | `String` | No | Specifies AD domains to search for accounts. |
| `-Group` | `SwitchParameter` | No | Specifies that you want to retrieve only group accounts. |
| `-Id` | `String[]` | No | Specifies the IDs of the accounts you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string... |
| `-Name` | `String[]` | No | Specifies the names of the accounts you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-User` | `SwitchParameter` | No | Specifies that you want to retrieve only user accounts. |

---

### Get-VIOAuth2Client

This cmdlet retrieves the OAuth2 clients available on a vCenter Server system.

**Returns**: `Zero or more OAuth2Client objects`

```
Get-VIOAuth2Client
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Filters the OAuth2 clients by ID. |
| `-Name` | `String[]` | No | Filters the OAuth2 clients by name. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VIPermission

This cmdlet retrieves the permissions defined on the specified inventory objects.

This cmdlet retrieves the permissions defined on the specified inventory objects. If no inventory objects are specified, the cmdlet retrieves all permissions available on the server.

**Returns**: `Permission`

```
Get-VIPermission
    [-Entity <VIObject[]>]
    [-Principal <VIAccount[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObject[]` | No | Specifies the inventory items for which you want to retrieve permissions. |
| `-Principal` | `VIAccount[]` | No | Specifies the users and groups for which you want to retrieve permissions. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VIPrivilege

This cmdlet retrieves the privilege groups and items for the provided servers.

**Returns**: `Privilege`

```
Get-VIPrivilege
    -Group <PrivilegeGroup[]>
    [-Id <String[]>]
    [-Name <String[]>]
    [-PrivilegeGroup]
    [-PrivilegeItem]
    -Role <Role[]>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Group` | `PrivilegeGroup[]` | Yes | Specifies the privilege group whose items you want to retrieve. |
| `-Id` | `String[]` | No | Specifies the IDs of the privileges you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the stri... |
| `-Name` | `String[]` | No | Specifies the names of the privileges you want to retrieve. |
| `-PrivilegeGroup` | `SwitchParameter` | No | Indicates that you want to retrieve only the privilege groups and not the privilege items in them. |
| `-PrivilegeItem` | `SwitchParameter` | No | Indicates that you want to retrieve only the privilege items and not the privilege groups. |
| `-Role` | `Role[]` | Yes | Specifies the roles whose privileges you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VIPrivilegeReport

This cmdlet records the privilege checks that occur for the specified sessions during the execution of a specified script block.

This cmdlet records the privilege checks that occur for the specified sessions during the execution of a specified script block. The vCenter Server systems on which the script block is executed must be managed within the script block.

**Returns**: `PrivilegeCheck`

```
Get-VIPrivilegeReport
    -ScriptBlock <ScriptBlock>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ScriptBlock` | `ScriptBlock` | Yes | Specifies the script block to be executed to collect required privileges. The vCenter Server systems on which the script block is executed must be managed within the script block. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to collect a privilege report. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. Fo... |

---

### Get-VIRole

This cmdlet retrieves all roles defined on the provided servers.

**Returns**: `Role`

```
Get-VIRole
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | No | Specifies the IDs of the roles you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string va... |
| `-Name` | `String[]` | No | Specifies the names of the roles you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-VIServer

This cmdlet establishes a connection to a vCenter Server system.

This cmdlet establishes a connection to a vCenter Server system. The cmdlet starts a new session or re-establishes a previous session with a vCenter Server system using the specified parameters.

**Returns**: `VIServer`

```
Get-VIServer
    [-AllLinked]
    [-Credential <PSCredential>]
    [-Force]
    -Menu
    [-NotDefault]
    [-Password <String>]
    [-Port <Int32>]
    [-Protocol <String>]
    -SamlSecurityContext <SamlSecurityContext>
    [-SaveCredentials]
    -Server <String[]>
    [-Session <String>]
    [-User <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllLinked` | `SwitchParameter` | No | Indicates whether you want to connect to vCenter Server in linked mode. If you specify $true for the AllLinked parameter and the server to which you want to connect is a part of a federation vCente... |
| `-Credential` | `PSCredential` | No | Specifies a PSCredential object that contains credentials for authenticating with the server. For more information about the server authentication logic of PowerCLI, run "help about_server_authenti... |
| `-Force` | `SwitchParameter` | No | Suppresses all user interface prompts during the cmdlet execution. Currently, these include 'Multiple default servers' and 'Invalid certificate action'. |
| `-Menu` | `SwitchParameter` | Yes | Indicates that you want to select a connection server from a list of recently connected servers. If Menu is set to $true, the cmdlet retrieves a list of the last visited servers and enters a nested... |
| `-NotDefault` | `SwitchParameter` | No | Indicates that you do not want to include the server to which you connect into the $defaultVIServers variable. |
| `-Password` | `String` | No | Specifies the password you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentica... |
| `-Port` | `Int32` | No | Specifies the port on the server you want to use for the connection. |
| `-Protocol` | `String` | No | Specifies the Internet protocol you want to use for the connection. It can be either http or https. |
| `-SamlSecurityContext` | `SamlSecurityContext` | Yes | Specifies the SAML2 security context for the vCenter Server system. For more information about security contexts, see the about_security_context (about_security_context.html)article. |
| `-SaveCredentials` | `SwitchParameter` | No | Indicates that you want to save the specified credentials in the local credential store.   Note: This parameter is not supported on the Core edition of PowerShell. |
| `-Server` | `String[]` | Yes | Specifies the IP address or the DNS name of the vSphere server to which you want to connect. You can also specify a server by providing its IPv6 address enclosed in square brackets, for example [fe... |
| `-Session` | `String` | No | Specifies the ID of an existing vCenter Server session you want to re-establish. |
| `-User` | `String` | No | Specifies the user name you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentic... |

---

### Get-VIToolkitConfiguration

This cmdlet retrieves the VMware PowerCLI proxy configuration and default servers policy.

**Returns**: `PowerCLIConfiguration`

```
Get-VIToolkitConfiguration
    [-Scope <ConfigurationScope>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Scope` | `ConfigurationScope` | No | Specifies a scope to filter VMware PowerCLI settings by. The parameter accepts Session, User, and All Users values. |

---

### Get-VIToolkitVersion

This cmdlet retrieves the versions of the installed PowerCLI snapins.

**Returns**: `PowerCLIVersion`

```
Get-VIToolkitVersion
```

---

### Get-VirtualNetwork

The cmdlet retrieves all virtual networks on a vCenter server system.

This cmdlet retrieves all virtual networks that match the specified filters for each default connection to the vCenter server system or all specified connections in the -Server parameter.

**Returns**: `Network`

```
Get-VirtualNetwork
    -Id <String[]>
    [-Location <VIContainer[]>]
    [-Name <String[]>]
    [-NetworkType <NetworkType[]>]
    [-NoRecursion]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `String[]` | Yes | Specifies the IDs of the virtual networks that you want to retrieve. |
| `-Location` | `VIContainer[]` | No | Specifies vSphere container objects that you want to search for virtual networks. This parameter accepts Folder and Datacenter objects. |
| `-Name` | `String[]` | No | Specifies the names of the virtual networks that you want to retrieve. |
| `-NetworkType` | `NetworkType[]` | No | Specifies the network types of the virtual networks that you want to retrieve. The accepted values are Network, Distributed, and Opaque. |
| `-NoRecursion` | `SwitchParameter` | No | Indicates that you want to deactivate the recursive behavior of the command. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### HookGetViewAutoCompleter

HookGetViewAutoCompleter

**Returns**: `returnValue`

```
HookGetViewAutoCompleter
```

---

### New-AdvancedSetting

This cmdlet creates a new advanced setting for the specified entity.

**Returns**: `AdvancedSetting`

```
New-AdvancedSetting
    -Entity <VIObject>
    [-Force]
    -Name <String>
    [-Server <VIServer[]>]
    [-Type <AdvancedSettingType>]
    -Value <Object>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObject` | Yes | Specifies the entity for which you want to create a new advanced setting. This parameter accepts VIServer, VirtualMachine, DatastoreCluster, and Cluster objects. Passing multiple values to this par... |
| `-Force` | `SwitchParameter` | No | Indicates that you want to create the new advanced setting even if another setting with the same name exists for the specified object type. |
| `-Name` | `String` | Yes | Specifies a name for the advanced setting. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `AdvancedSettingType` | No | Specifies the type of the new advanced setting. |
| `-Value` | `Object` | Yes | Specifies a value for the advanced setting. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-ApplianceBackupJob

This cmdlet starts a backup job for a vCenter Server system.

This cmdlet starts a file-based backup job for a vCenter Server system to a backup server.

**Returns**: `ApplianceBackupJob`

```
New-ApplianceBackupJob
    -BackupServer <String>
    [-BackupServerPassword <SecureString>]
    [-BackupServerPort <Int32>]
    -BackupServerType <String>
    [-BackupServerUsername <String>]
    [-Confirm]
    [-Description <String>]
    -FolderPath <String>
    [-OptionalBackupParts <ApplianceBackupPart[]>]
    [-Password <SecureString>]
    [-Server <VIServer>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BackupServer` | `String` | Yes | The IP or FQDN of the backup server to be used for the backup. |
| `-BackupServerPassword` | `SecureString` | No | Password for the given backup server. If unset, authentication will not be used for the specified backup server. |
| `-BackupServerPort` | `Int32` | No | The backup server port to be used for the backup. |
| `-BackupServerType` | `String` | Yes | The type of the backup server. Currently supported types are FTP, HTTP, FTPS, HTTPS, SCP, SFTP, NFS, SMB |
| `-BackupServerUsername` | `String` | No | Username for the given backup server. If unset, authentication will not be used for the specified backup server. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Description` | `String` | No | Provides a custom comment to the backup job. If unset, the comment will be empty. |
| `-FolderPath` | `String` | Yes | A folder path on the backup server where the backup will be created. It must be an empty or non-existing folder. In case the folder doesn't exist it will be created. |
| `-OptionalBackupParts` | `ApplianceBackupPart[]` | No | A list of optional backup parts that will be included in the backup job. You can use Get-ApplianceBackupPart -OptinalOnly to retrieve a list of the available parts. |
| `-Password` | `SecureString` | No | You can set a password for encryption of a backup. The password must adhere to the following requirements. The length must be at least 8 characters but not more than 20 characters. It must include ... |
| `-Server` | `VIServer` | No | Specifies the vCenter Server system on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default server. Note: This cmdle... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-IScsiHbaTarget

This cmdlet creates a new iSCSI HBA target.

This cmdlet creates a new iSCSI HBA target. The cmdlet also enables and configures the CHAP (Challenge Handshake Authentication Protocol) authentication settings of the new target.

**Returns**: `IScsiHbaTarget`

```
New-IScsiHbaTarget
    -Address <String>
    [-ChapName <String>]
    [-ChapPassword <String>]
    [-ChapType <ChapType>]
    [-InheritChap <Boolean>]
    [-InheritMutualChap <Boolean>]
    -IScsiHba <IScsiHba>
    [-IScsiName <String>]
    [-MutualChapEnabled <Boolean>]
    [-MutualChapName <String>]
    [-MutualChapPassword <String>]
    [-Port <Int32>]
    [-Server <VIServer[]>]
    [-Type <IScsiHbaTargetType>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Address` | `String` | Yes | Specifies the address of the new iSCSI HBA target. Passing multiple values to this parameter is obsolete. |
| `-ChapName` | `String` | No | Specifies a CHAP authentication name for the new target. |
| `-ChapPassword` | `String` | No | Specifies a CHAP authentication password for the new target. |
| `-ChapType` | `ChapType` | No | Specifies the type of the CHAP (Challenge Handshake Authentication Protocol) you want the new target to use. The valid values are Prohibited, Discouraged, Preferred, and Required. |
| `-InheritChap` | `Boolean` | No | Indicates that the CHAP setting is inherited from the iSCSI HBA. |
| `-InheritMutualChap` | `Boolean` | No | Indicates that the Mutual CHAP setting is inherited from the iSCSI HBA. |
| `-IScsiHba` | `IScsiHba` | Yes | Specifies the iSCSI HBA for which you want to create the new target. Passing multiple values to this parameter is obsolete. |
| `-IScsiName` | `String` | No | Specifies the iSCSI name of the target. It can be specified only for Static targets. |
| `-MutualChapEnabled` | `Boolean` | No | Indicates that Mutual CHAP is enabled. |
| `-MutualChapName` | `String` | No | Specifies a Mutual CHAP authentication name for the new target. |
| `-MutualChapPassword` | `String` | No | Specifies a Mutual CHAP authentication password for the new target. |
| `-Port` | `Int32` | No | Specifies the TCP port of the target. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Type` | `IScsiHbaTargetType` | No | Specifies the type of the target. The valid values are Static and Send. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-LcmOfflineDepot

This cmdlet creates a new vSphere Lifecycle Manager offline depot.

This cmdlet creates a new vSphere Lifecycle Manager offline depot from a provided online location.

**Returns**: `LcmOfflineDepot`

```
New-LcmOfflineDepot
    [-Confirm]
    [-Description <String>]
    [-Location <Uri>]
    [-OwnerData <String>]
    [-RunAsync]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Description` | `String` | No | Provides a description of the depot that you want to create. |
| `-Location` | `Uri` | No | The URL of the depot update file from which to create the offline depot. |
| `-OwnerData` | `String` | No | Any string that you want to associate and store with the depot. |
| `-RunAsync` | `SwitchParameter` | No | Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter, ... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-OSCustomizationNicMapping

This cmdlet adds NIC settings mappings to the specified OS customization specifications.

This cmdlet adds  NIC settings mappings to the specified OS customization specifications. If the given specification is server-side, it is updated on the server. If it is client-side, the reference that is kept in-memory is updated but the variable that is passed to the cmdlet is not modified.

**Returns**: `OSCustomizationNicMapping`

```
New-OSCustomizationNicMapping
    [-AlternateGateway <String>]
    [-DefaultGateway <String>]
    [-Dns <String[]>]
    [-IpAddress <String>]
    [-IpMode <OSCustomizationIPMode>]
    [-NetworkAdapterMac <String[]>]
    -OSCustomizationSpec <OSCustomizationSpec>
    [-Position <Int32[]>]
    [-Ipv6Address <String>]
    [-Ipv6AlternateGateway <String>]
    [-Ipv6Gateway <String>]
    [-Ipv6Mode <OSCustomizationIPMode>]
    [-Ipv6Prefix <Int32>]
    [-Ipv6VcApplicationArgument <String>]
    [-Server <VIServer[]>]
    [-SubnetMask <String>]
    [-VCApplicationArgument <String>]
    [-Wins <String[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlternateGateway` | `String` | No | Specifies an alternate gateway. |
| `-DefaultGateway` | `String` | No | Specifies a default gateway. |
| `-Dns` | `String[]` | No | Specifies a DNS address. This parameter applies only to Windows operating systems. |
| `-IpAddress` | `String` | No | Specifies an IP address. Using this parameter automatically sets the IpMode parameter to UseStaticIp. |
| `-IpMode` | `OSCustomizationIPMode` | No | Specifies the IP configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, and UseStaticIP. |
| `-NetworkAdapterMac` | `String[]` | No | Specifies the MAC addresses of the network adapters to which you want to map the new OS customization specifications. |
| `-OSCustomizationSpec` | `OSCustomizationSpec` | Yes | Specifies the OS customization specification to which you want to add the NIC setting mapping. Passing multiple values to this parameter is obsolete. |
| `-Position` | `Int32[]` | No | Specifies the position of the NIC to which you want to map the OS customization specification. |
| `-Ipv6Address` | `String` | No | Specifies an IPv6 address. |
| `-Ipv6AlternateGateway` | `String` | No | Specifies an alternate IPv6 gateway. |
| `-Ipv6Gateway` | `String` | No | Specifies the default IPv6 gateway. |
| `-Ipv6Mode` | `OSCustomizationIPMode` | No | Specifies the IPv6 configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, UseStaticIP, UseStatelessIpv6 and UseAutoIpv6. |
| `-Ipv6Prefix` | `Int32` | No | Specifies the IPv6 prefix. |
| `-Ipv6VcApplicationArgument` | `String` | No | Specifies a new argument to pass to a vCenter Server application to obtain an IPv6 address. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SubnetMask` | `String` | No | Specifies a subnet mask. |
| `-VCApplicationArgument` | `String` | No | Specifies an optional argument you want to pass to the vCenter Server to obtain an IP address. |
| `-Wins` | `String[]` | No | Specifies WINS servers. This parameter applies only to Windows operating systems. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-OSCustomizationSpec

This cmdlet creates a new OS customization specification.

This cmdlet creates a new OS customization specification or clones an existing one. If a name is provided, creates and adds the specified customization specification to the server. Otherwise, creates and returns the requested specification object. If the Name parameter is not specified, the OSCustomizationSpec object is not persisted on the server. Either the Domain or the Workgroup parameters should be provided if a Windows specification is created. If a Linux specification is created, the D...

**Returns**: `OSCustomizationSpec`

```
New-OSCustomizationSpec
    [-AdminPassword <String>]
    [-AutoLogonCount <Int32>]
    [-ChangeSid]
    [-CustomizationScript <String>]
    [-DeleteAccounts]
    [-Description <String>]
    [-DnsServer <String[]>]
    [-DnsSuffix <String[]>]
    [-Domain <String>]
    [-DomainCredentials <PSCredential>]
    [-DomainPassword <String>]
    [-DomainUsername <String>]
    -FullName <String>
    [-GuiRunOnce <String[]>]
    [-LicenseMaxConnections <Int32>]
    [-LicenseMode <LicenseMode>]
    [-Name <String>]
    [-NamingPrefix <String>]
    [-NamingScheme <String>]
    -OrgName <String>
    -OSCustomizationSpec <OSCustomizationSpec>
    [-OSType <String>]
    [-ProductKey <String>]
    [-Server <VIServer[]>]
    [-TimeZone <String>]
    [-Type <OSCustomizationSpecType>]
    [-Workgroup <String>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdminPassword` | `String` | No | Specifies a new OS administrator's password. This parameter applies only to Windows operating systems. If not specified, the administrator's password is set to blank. |
| `-AutoLogonCount` | `Int32` | No | Specifies the number of times the virtual machine automatically logs in as administrator without prompting for user credentials. The valid values are in the range between 0 and Int32.MaxValue. Spec... |
| `-ChangeSid` | `SwitchParameter` | No | Indicates that the customization should modify the system security identifier (SID). This parameter applies only to Windows operating systems. |
| `-CustomizationScript` | `String` | No | Specifies a bash script that runs before and after the customization of the guest operating system. You can use this parameter only for Linux-based operating systems. Use the bash script itself and... |
| `-DeleteAccounts` | `SwitchParameter` | No | Indicates that you want to delete all user accounts. This parameter applies only to Windows operating systems. |
| `-Description` | `String` | No | Provides a description for the new specification. |
| `-DnsServer` | `String[]` | No | Specifies the DNS server settings. This parameter applies only to Linux operating systems. |
| `-DnsSuffix` | `String[]` | No | Specifies the DNS suffix settings. This parameter applies only to Linux operating systems. |
| `-Domain` | `String` | No | Specifies a domain name. |
| `-DomainCredentials` | `PSCredential` | No | Specifies the credentials you want to use for domain authentication. This parameter applies only to Windows operating systems. |
| `-DomainPassword` | `String` | No | Specifies the password you want to use for domain authentication. This parameter applies only to Windows operating systems. |
| `-DomainUsername` | `String` | No | Specifies the user name you want to use for domain authentication. This parameter applies only to Windows operating systems. |
| `-FullName` | `String` | Yes | Specifies the administrator's full name. This parameter applies only to Windows operating systems. |
| `-GuiRunOnce` | `String[]` | No | Specifies a list of commands. These commands run when a user logs in for the first time after the customization completes. This parameter applies only to Windows operating systems. |
| `-LicenseMaxConnections` | `Int32` | No | Specifies the maximum connections for server license mode. Use this parameter only if the LicenseMode parameter is set to Perserver. This parameter applies only to Windows operating systems. |
| `-LicenseMode` | `LicenseMode` | No | Specifies the license mode of the Windows 2000/2003 guest operating system. The valid values are Perseat, Perserver, and Notspecified. If Perserver is set, use the LicenseMaxConnection parameter to... |
| `-Name` | `String` | No | Specifies a name for the new specification. |
| `-NamingPrefix` | `String` | No | Depends on the customization naming scheme - Custom, NamingPrefix, or Prefix. If the "Custom" naming scheme is used, NamingPrefix is an optional argument that is passed to the utility for this IP a... |
| `-NamingScheme` | `String` | No | Specifies the naming scheme for the virtual machine. The following values are valid:   Custom - Specifies that vCenter Server will launch an external application to generate the (hostname/IP). The ... |
| `-OrgName` | `String` | Yes | Specifies the name of the organization to which the administrator belongs. |
| `-OSCustomizationSpec` | `OSCustomizationSpec` | Yes | Specifies an OS customization specification that you want to clone. |
| `-OSType` | `String` | No | Specifies the type of the operating system. The valid values are Linux and Windows. |
| `-ProductKey` | `String` | No | Specifies the MS product key. If the guest OS version is earlier than Vista, this parameter is required in order to make the customization unattended. For Vista or later, the OS customization is un... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TimeZone` | `String` | No | Specifies the name or ID of the time zone for a Windows guest OS only. Using wildcards is supported. The following time zones are available:     000 Int'l Dateline 001 Samoa 002 Hawaii 003 Alaskan ... |
| `-Type` | `OSCustomizationSpecType` | No | Specifies the type of the OS customization specification. The valid values are Persistent and NonPersistent. |
| `-Workgroup` | `String` | No | Specifies a workgroup. This parameter applies only to Windows operating systems. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VIOAuth2Client

Creates a new OAuth2 client registration with the VMware Identity Broker.

Creates a new OAuth2 client registration with the vCenter Identity Broker. The VMware Identity Broker is an OAuth2 relay that is used by client applications to authenticate with vCenter using OAuth2.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.IdentityBroker.OAuth2Client`

```
New-VIOAuth2Client
    [-AccessTokenTimeToLiveMinutes <Int32>]
    -ClientId <String>
    -GrantTypes <String[]>
    [-Name <String>]
    [-PkceEnforced <Boolean>]
    [-PostLogoutRedirectUris <String[]>]
    [-PublicClient <Boolean>]
    [-RedirectUris <String[]>]
    [-RefreshTokenIdleTimeToLiveMinutes <Int32>]
    [-RefreshTokenTimeToLiveMinutes <Int32>]
    [-RuleSetNames <String[]>]
    -Scope <String[]>
    [-Secret <SecureString>]
    [-SecretTimeToLiveInMinutes <Int32>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AccessTokenTimeToLiveMinutes` | `Int32` | No | How long in minutes new access tokens issued to this client should live. |
| `-ClientId` | `String` | Yes | OAuth 2.0 Client identifier that the client uses to identify itself during the OAuth 2.0 exchanges. The client ID must contain only alphanumeric (A-Z, a-z, 0-9), period (.), underscore (_), hyphen ... |
| `-GrantTypes` | `String[]` | Yes | Specifies a list of OAuth 2.0 Access Grant Types that are enabled in this OAuth 2.0 Client.   Possible values are: password , client_credentials , refresh_token , authorization_code , token , id_token |
| `-Name` | `String` | No | Specifies the user-friendly name that you set for this OAuth 2.0 client.   This parameter is available only for vCenter instances of version 8.0 Update 3 and later. |
| `-PkceEnforced` | `Boolean` | No | Specifies whether PKCE is enforced for the OAuth2 client. If not specified, the value is 'false'.   This parameter is available only for vCenter instances of version 8.0 Update 3 and later. |
| `-PostLogoutRedirectUris` | `String[]` | No | Specifies a list of absolute URLs to the OAuth2 Relaying Party. When a logout occurs, the Auth2 Relaying Party might request that the User Agent of the End-User is redirected to one of these absolu... |
| `-PublicClient` | `Boolean` | No | Specifies whether the OAuth 2.0 client is public or not. A public client is one that does not have a secret. If not specified, the value is 'false'.   This parameter is available only for vCenter i... |
| `-RedirectUris` | `String[]` | No | Specifies a list of absolute URIs of application endpoints that are allowed to receive the authorization code and access token.  The redirect URI sent by the application as part of the Authorizatio... |
| `-RefreshTokenIdleTimeToLiveMinutes` | `Int32` | No | Specifies how long in minutes new refresh tokens issued to this client should live.  Only applicable and mandatory if the GrantTypes parameter includes "refresh_token". |
| `-RefreshTokenTimeToLiveMinutes` | `Int32` | No | Specifies how long in minutes new refresh tokens issued to this client can be idle. Only applicable and mandatory if GrantTypes includes "refresh_token". Its value should be less than the refresh t... |
| `-RuleSetNames` | `String[]` | No | Specifies a list of built in rule set names to associate this client with.  Each ruleset, allows the client to call a specific set of tenant APIs.   Possible values are: TENANT_ADMIN , IDP_AND_DIRE... |
| `-Scope` | `String[]` | Yes | Specifies a list of access request scopes that are allowed by this OAuth 2.0 Client.   Available scope options are: admin, user, profile, email, openid, group   admin - Admin Level Access   user - ... |
| `-Secret` | `SecureString` | No | Specifies the OAuth 2.0 Client secret.   If secret string is not provided, an auto-generated secret will be returned.   For additional security, the stored secret will not be returned by the Get-VI... |
| `-SecretTimeToLiveInMinutes` | `Int32` | No | Specifies after what time in minutes the secret must be rotated.   This parameter is available only for vCenter instances of version 8.0 Update 3 and later. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `SwitchParameter` | No | Shows what would happen when the cmdlet runs. Note that the cmdlet is actually not started. |

---

### New-VIPermission

This cmdlet creates new permissions on the specified inventory objects for the provided users and groups in the role.

This cmdlet creates new permissions on the specified inventory objects for the provided users and groups in the role. By default, new permissions are propagated down the hierarchy to sub-entities. You cannot create new permissions for the following objects: - direct child folders of a datacenter

**Returns**: `Permission`

```
New-VIPermission
    -Entity <VIObject>
    -Principal <VIAccount>
    [-Propagate <Boolean>]
    -Role <Role>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObject` | Yes | Specifies the inventory objects for which you want to create new permissions. Passing multiple values to this parameter is obsolete. |
| `-Principal` | `VIAccount` | Yes | Specifies users and groups to which you want to apply the new permissions. If you specify principal names by using the "domain\name" syntax, wildcards are not supported. Passing multiple values to ... |
| `-Propagate` | `Boolean` | No | Indicates that you want to propagate the new permissions to the child inventory objects. |
| `-Role` | `Role` | Yes | Specifies the roles for which you want to create new permissions. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VIRole

This cmdlet creates a new role on the specified servers and applies the provided privileges.

**Returns**: `Role`

```
New-VIRole
    -Name <String>
    [-Privilege <Privilege[]>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | Specifies a name for the new role. |
| `-Privilege` | `Privilege[]` | No | Specifies the privileges you want to apply to the new role. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-VISamlSecurityContext

Creates an SAML2 security context object that can be used to authenticate a user with any VMware vCenter Server services.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.VISamlSecurityContext`

```
New-VISamlSecurityContext
    [-IgnoreSslValidationErrors]
    -OAuthSecurityContext <OAuth2SecurityContext>
    [-Port <Int32>]
    -VCenterServer <String>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-IgnoreSslValidationErrors` | `SwitchParameter` | No | If specified, any errors with the SSL certificate of the server will be ignored. |
| `-OAuthSecurityContext` | `OAuth2SecurityContext` | Yes | Specifies the OAuth2 security context from an authentication server that the vCenter Server instance is configured to trust. |
| `-Port` | `Int32` | No | Specifies the port where the vCenter vAPI Endpoint is listening on. The default is 443. |
| `-VCenterServer` | `String` | Yes | Specifies the IP address or the DNS name of the vSphere server that authenticates the user. |

---

### Open-VMConsoleWindow

This cmdlet opens a window to the virtual machine's console.

**Returns**: `None documented`

```
Open-VMConsoleWindow
    [-FullScreen]
    [-Server <VIConnection[]>]
    [-UrlOnly]
    -VM <RemoteConsoleVM[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-FullScreen` | `SwitchParameter` | No | If specified, opens the virtual machine's console window in full-screen mode. |
| `-Server` | `VIConnection[]` | No | Specifies the vCenter Server systems or cloud server instances on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the defau... |
| `-UrlOnly` | `SwitchParameter` | No | If specified, the cmdlet returns the URL for opening a console window to the virtual machine without actually opening the console window.   Note: The URL is valid for 30 seconds. After 30 seconds, ... |
| `-VM` | `RemoteConsoleVM[]` | Yes | Specifies the virtual machine for which you want to open a remote console. Supports vCloud and vSphere virtual machines. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-AdvancedSetting

This cmdlet removes the specified advanced setting.

**Returns**: `None`

```
Remove-AdvancedSetting
    -AdvancedSetting <AdvancedSetting[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdvancedSetting` | `AdvancedSetting[]` | Yes | Specifies the advanced settings you want to remove.   Note: You can only remove advanced settings from virtual machines in ESXi or vCenter Server environments version 5.5 or later. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-IScsiHbaTarget

This cmdlet removes targets from their iSCSI HBAs.

**Returns**: `None`

```
Remove-IScsiHbaTarget
    [-Server <VIServer[]>]
    -Target <IScsiHbaTarget[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Target` | `IScsiHbaTarget[]` | Yes | Specifies the iSCSI HBA targets you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-OSCustomizationNicMapping

This cmdlet removes the specified OS customization NIC mappings.

**Returns**: `None`

```
Remove-OSCustomizationNicMapping
    -OSCustomizationNicMapping <OSCustomizationNicMapping[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-OSCustomizationNicMapping` | `OSCustomizationNicMapping[]` | Yes | Specifies the OSCustomizationNicMapping objects you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-OSCustomizationSpec

This cmdlet removes the specified OS customization specifications.

**Returns**: `None`

```
Remove-OSCustomizationSpec
    -OSCustomizationSpec <OSCustomizationSpec[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-OSCustomizationSpec` | `OSCustomizationSpec[]` | Yes | Specifies the customization specifications you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VIOAuth2Client

Deletes a registration for a specified OAuth2 client from the VMware Identity Broker.

**Returns**: `None documented`

```
Remove-VIOAuth2Client
    [-OAuth2Client <OAuth2Client[]>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-OAuth2Client` | `OAuth2Client[]` | No | Specifies the registrations that must be removed. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `SwitchParameter` | No | Shows what would happen when the cmdlet runs. Note that the cmdlet is actually not started. |

---

### Remove-VIPermission

This cmdlet removes the specified permissions.

**Returns**: `None`

```
Remove-VIPermission
    -Permission <Permission[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Permission` | `Permission[]` | Yes | Specifies the permissions you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VIRole

This cmdlet removes the specified roles.

This cmdlet removes the specified roles. To remove a role that is associated with a permission, you need to set the Force parameter to $true.

**Returns**: `None`

```
Remove-VIRole
    [-Force]
    -Role <Role[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `SwitchParameter` | No | Indicates that you want to remove the role even if it is associated with a permission. |
| `-Role` | `Role[]` | Yes | Specifies the roles you want to remove. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-AdvancedSetting

This cmdlet modifies the specified advanced setting.

**Returns**: `AdvancedSetting`

```
Set-AdvancedSetting
    -AdvancedSetting <AdvancedSetting[]>
    -Value <Object>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdvancedSetting` | `AdvancedSetting[]` | Yes | Specifies the advanced setting you want to modify. |
| `-Value` | `Object` | Yes | Specifies a new value for the advanced setting. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-IScsiHbaTarget

This cmdlet modifies the configuration of an iSCSI HBA target.

This cmdlet modifies the configuration of an iSCSI HBA target. The cmdlet modifies the CHAP and Digest properties of an iSCSI HBA target. You must specify at least one of the CHAP-related (or Mutual CHAP) parameters. Otherwise, an error message is displayed.

**Returns**: `IScsiHbaTarget`

```
Set-IScsiHbaTarget
    [-ChapName <String>]
    [-ChapPassword <String>]
    [-ChapType <ChapType>]
    [-InheritChap <Boolean>]
    [-InheritMutualChap <Boolean>]
    [-MutualChapEnabled <Boolean>]
    [-MutualChapName <String>]
    [-MutualChapPassword <String>]
    [-Server <VIServer[]>]
    -Target <IScsiHbaTarget[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ChapName` | `String` | No | Specifies the CHAP initiator name if CHAP is enabled. |
| `-ChapPassword` | `String` | No | Specifies the CHAP password if CHAP is enabled. |
| `-ChapType` | `ChapType` | No | Specifies the type of the CHAP authorization. The valid values are Prohibited, Discouraged, Preferred, and Required. If you set ChapType to Discouraged, Preferred, or Required, then you must specif... |
| `-InheritChap` | `Boolean` | No | Indicates that the CHAP setting is inherited from the iSCSI HBA device. |
| `-InheritMutualChap` | `Boolean` | No | Indicates that the Mutual CHAP setting is inherited from the iSCSI HBA device. |
| `-MutualChapEnabled` | `Boolean` | No | Indicates that mutual CHAP is enabled. In this case, you must specify the MutualChapPassword parameter as well. |
| `-MutualChapName` | `String` | No | Specifies the Mutual CHAP initiator name if CHAP is enabled. |
| `-MutualChapPassword` | `String` | No | Specifies the Mutual CHAP password if CHAP is enabled. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Target` | `IScsiHbaTarget[]` | Yes | Specifies the iSCSI HBA target you want to configure. To identify the target, you can provide an IScsiTarget object or use an <Address>:<Port> string. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-NicTeamingPolicy

This cmdlet modifies the specified NIC teaming policy.

This cmdlet modifies the specified NIC teaming policy. You can change the load balancing and failover settings. Default NIC teaming policies are set for the entire virtual switch and can be overridden at port group level.

**Returns**: `NicTeamingVirtualSwitchPolicy`

```
Set-NicTeamingPolicy
    [-BeaconInterval <Int32>]
    [-FailbackEnabled <Boolean>]
    [-InheritFailback <Boolean>]
    [-InheritFailoverOrder <Boolean>]
    [-InheritLoadBalancingPolicy <Boolean>]
    [-InheritNetworkFailoverDetectionPolicy <Boolean>]
    [-InheritNotifySwitches <Boolean>]
    [-LoadBalancingPolicy <LoadBalancingPolicy>]
    [-MakeNicActive <PhysicalNic[]>]
    [-MakeNicStandby <PhysicalNic[]>]
    [-MakeNicUnused <PhysicalNic[]>]
    [-NetworkFailoverDetectionPolicy <NetworkFailoverDetectionPolicy>]
    [-NotifySwitches <Boolean>]
    -VirtualPortGroupPolicy <NicTeamingVirtualPortGroupPolicy[]>
    -VirtualSwitchPolicy <NicTeamingVirtualSwitchPolicy[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BeaconInterval` | `Int32` | No | Specifies the interval at which the server sends out beacon probes on all NICs in the team. The value must be a positive integer. This parameter is used when the value of the NetworkFailoverDetecti... |
| `-FailbackEnabled` | `Boolean` | No | Specifies how a physical adapter is returned to active duty after recovering from a failure. If the value is $true, the adapter is returned to active duty immediately on recovery, displacing the st... |
| `-InheritFailback` | `Boolean` | No | Indicates that the value of the FailbackEnabled parameter is inherited from the virtual switch. |
| `-InheritFailoverOrder` | `Boolean` | No | Indicates that the value of the MakeNicActive, MakeNicStandBy, and MakeNicUnused parameters are inherited from the virtual switch. |
| `-InheritLoadBalancingPolicy` | `Boolean` | No | Indicates that the value of the LoadBalancingPolicy parameter is inherited from the virtual switch. |
| `-InheritNetworkFailoverDetectionPolicy` | `Boolean` | No | Indicates that the value of the NetworkFailoverDetectionPolicy parameter is inherited from the virtual switch. |
| `-InheritNotifySwitches` | `Boolean` | No | Indicates that the value of the NotifySwitches parameter is inherited from the virtual switch. |
| `-LoadBalancingPolicy` | `LoadBalancingPolicy` | No | Determines how network traffic is distributed between the network adapters assigned to a switch. The following values are valid:   LoadBalanceIP - Route based on IP hash. Choose an uplink based on ... |
| `-MakeNicActive` | `PhysicalNic[]` | No | Specifies the adapters you want to continue to use when the network adapter connectivity is available and active. |
| `-MakeNicStandby` | `PhysicalNic[]` | No | Specifies the adapters you want to use if one of the active adapter's connectivity is unavailable. |
| `-MakeNicUnused` | `PhysicalNic[]` | No | Specifies the adapters you do not want to use. |
| `-NetworkFailoverDetectionPolicy` | `NetworkFailoverDetectionPolicy` | No | Specifies how to reroute traffic in the event of an adapter failure. The following values are valid:   LinkStatus - Relies solely on the link status that the network adapter provides. This option d... |
| `-NotifySwitches` | `Boolean` | No | Indicates that whenever a virtual NIC is connected to the virtual switch or whenever that virtual NIC's traffic is routed over a different physical NIC in the team because of a failover event, a no... |
| `-VirtualPortGroupPolicy` | `NicTeamingVirtualPortGroupPolicy[]` | Yes | Specifies the virtual port group policy to configure. |
| `-VirtualSwitchPolicy` | `NicTeamingVirtualSwitchPolicy[]` | Yes | Specifies the virtual switch policy to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-OSCustomizationNicMapping

This cmdlet modifies the provided OS customization NIC mappings.

This cmdlet modifies the provided OS customization NIC mappings. If the parent spec of the provided NIC mapping is a server-side spec, it is updated on the server. If the parent spec is client-side, the reference that is kept in the memory is updated, but the variable that is passed to the cmdlet is not modified.

**Returns**: `OSCustomizationNicMapping`

```
Set-OSCustomizationNicMapping
    [-AlternateGateway <String>]
    [-DefaultGateway <String>]
    [-Dns <String[]>]
    [-IpAddress <String>]
    [-IpMode <OSCustomizationIPMode>]
    [-NetworkAdapterMac <String>]
    -OSCustomizationNicMapping <OSCustomizationNicMapping[]>
    [-Position <Int32>]
    [-Ipv6Address <String>]
    [-Ipv6AlternateGateway <String>]
    [-Ipv6Gateway <String>]
    [-Ipv6Mode <OSCustomizationIPMode>]
    [-Ipv6Prefix <Int32>]
    [-Ipv6VcApplicationArgument <String>]
    [-Server <VIServer[]>]
    [-SubnetMask <String>]
    [-VCApplicationArgument <String>]
    [-Wins <String[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlternateGateway` | `String` | No | Specifies an alternate gateway. |
| `-DefaultGateway` | `String` | No | Specifies a default gateway. |
| `-Dns` | `String[]` | No | Specifies a DNS address. This parameter applies only to Windows operating systems. |
| `-IpAddress` | `String` | No | Specifies an IP address. Using this parameter automatically sets the IpMode parameter to UseStaticIp. |
| `-IpMode` | `OSCustomizationIPMode` | No | Specifies the IP configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, and UseStaticIP. |
| `-NetworkAdapterMac` | `String` | No | Specifies the MAC address of the network adapter to which you want to map the OS customization specification. |
| `-OSCustomizationNicMapping` | `OSCustomizationNicMapping[]` | Yes | Specifies the OS customization NIC mapping you want to configure. |
| `-Position` | `Int32` | No | Specifies the position of the mapping you want to modify. |
| `-Ipv6Address` | `String` | No | Specifies an IPv6 address. |
| `-Ipv6AlternateGateway` | `String` | No | Specifies an alternate IPv6 gateway. |
| `-Ipv6Gateway` | `String` | No | Specifies the default IPv6 gateway. |
| `-Ipv6Mode` | `OSCustomizationIPMode` | No | Specifies the IPv6 configuration mode. The valid values are UseDhcp, PromptUser, UseVCApplication, UseStaticIP, UseStatelessIpv6 and UseAutoIpv6. |
| `-Ipv6Prefix` | `Int32` | No | Specifies the IPv6 prefix. |
| `-Ipv6VcApplicationArgument` | `String` | No | Specifies a new argument to pass to a vCenter Server application to obtain an IPv6 address. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-SubnetMask` | `String` | No | Specifies a subnet mask. |
| `-VCApplicationArgument` | `String` | No | Specifies a new argument you want to pass to VCApplication in order to obtain an IP address. |
| `-Wins` | `String[]` | No | Specifies WINS servers. This parameter applies only to Windows operating systems. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-OSCustomizationSpec

This cmdlet modifies the specified OS customization specification.

This cmdlet modifies the specified OS customization specification. The specification to be updated is identified by one or both of the Name and Spec parameters. If a Windows specification is to be updated, one of the  Domain and Workgroup parameters must be provided. If a Linux specification is to be updated, the Domain parameter must be provided.

**Returns**: `OSCustomizationSpec`

```
Set-OSCustomizationSpec
    [-AdminPassword <String>]
    [-AutoLogonCount <Int32>]
    [-ChangeSID <Boolean>]
    [-CustomizationScript <String>]
    [-DeleteAccounts <Boolean>]
    [-Description <String>]
    [-DnsServer <String[]>]
    [-DnsSuffix <String[]>]
    [-Domain <String>]
    [-DomainCredentials <PSCredential>]
    [-DomainPassword <String>]
    [-DomainUsername <String>]
    [-FullName <String>]
    [-GuiRunOnce <String[]>]
    [-LicenseMaxConnections <Int32>]
    [-LicenseMode <LicenseMode>]
    [-Name <String>]
    [-NamingPrefix <String>]
    [-NamingScheme <String>]
    [-NewSpec <OSCustomizationSpec>]
    [-OrgName <String>]
    -OSCustomizationSpec <OSCustomizationSpec[]>
    [-ProductKey <String>]
    [-Server <VIServer[]>]
    [-TimeZone <String>]
    [-Type <OSCustomizationSpecType>]
    [-Workgroup <String>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdminPassword` | `String` | No | Specifies the new OS administrator's password. This parameter applies only to Windows operating systems. |
| `-AutoLogonCount` | `Int32` | No | Specifies the number of times the virtual machine should automatically login as an administrator. The valid values are in the range between 0 and Int32.MaxValue. Specifying 0 deactivates auto log-o... |
| `-ChangeSID` | `Boolean` | No | Indicates that the customization should modify the system security identifier (SID). This parameter applies only to Windows operating systems. |
| `-CustomizationScript` | `String` | No | Specifies a bash script that runs before and after the customization of the guest operating system. You can use this parameter only for Linux-based operating systems. Use the bash script itself and... |
| `-DeleteAccounts` | `Boolean` | No | Indicates that you want to delete all user accounts. This parameter applies only to Windows operating systems. |
| `-Description` | `String` | No | Provides a new description for the specification. |
| `-DnsServer` | `String[]` | No | Specifies the DNS server. This parameter applies only to Linux operating systems. |
| `-DnsSuffix` | `String[]` | No | Specifies the DNS suffix. This parameter applies only to Linux operating systems. |
| `-Domain` | `String` | No | Specifies the domain name. |
| `-DomainCredentials` | `PSCredential` | No | Specifies credentials for authentication with the specified domain. This parameter applies only to Windows operating systems. |
| `-DomainPassword` | `String` | No | Specifies a password for authentication with the specified domain. This parameter applies only to Windows operating systems. |
| `-DomainUsername` | `String` | No | Specifies a username for authentication with the specified domain. This parameter applies only to Windows operating systems. |
| `-FullName` | `String` | No | Specifies the administrator's full name. This parameter applies only to Windows operating systems. |
| `-GuiRunOnce` | `String[]` | No | Provides a list of commands to run after first user login. This parameter applies only to Windows operating systems. |
| `-LicenseMaxConnections` | `Int32` | No | Specifies the maximum connections for server license mode. Use this parameter only if the LicenseMode parameter is set to Perserver. This parameter applies only to Windows operating systems. |
| `-LicenseMode` | `LicenseMode` | No | Specifies the license mode of the Windows 2000/2003 guest operating system. The valid values are Perseat, Perserver, and NotSpecified. If Perserver is set, use the LicenseMaxConnection parameter to... |
| `-Name` | `String` | No | Specifies a new name for the OS customization specification. |
| `-NamingPrefix` | `String` | No | The behavior of this parameter is related to the customization scheme. If a Custom customization scheme is specified, NamingPrefix is an optional argument that is passed to the utility for this IP ... |
| `-NamingScheme` | `String` | No | Specifies the naming scheme for the virtual machine. The valid values are Custom, Fixed, Prefix, and Vm. |
| `-NewSpec` | `OSCustomizationSpec` | No | If no other parameters are provided, this parameter specifies a specification from which to retrieve information for the updated specification. |
| `-OrgName` | `String` | No | Specifies the name of the organization to which the administrator belongs. |
| `-OSCustomizationSpec` | `OSCustomizationSpec[]` | Yes | Specifies the specification you want to modify. |
| `-ProductKey` | `String` | No | Specifies the MS product key. If the guest OS version is earlier than Vista, this parameter is required in order to make the customization unattended. For Windows Vista and later, the OS customizat... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-TimeZone` | `String` | No | Specifies the name or ID of the time zone for a Windows guest OS only. Using wildcards is supported. The following time zones are available:     000 Int'l Dateline 001 Samoa 002 Hawaii 003 Alaskan ... |
| `-Type` | `OSCustomizationSpecType` | No | Sets the type of the OS customization specification. The valid values are Persistent and NonPersistent. |
| `-Workgroup` | `String` | No | Specifies the workgroup. This parameter applies only to Windows operating systems. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-SecurityPolicy

This cmdlet modifies the security policy for virtual port groups or the default port security policy for virtual switches.

This cmdlet modifies the security policy for virtual port groups or the default port security policy for virtual switches. Specifying a parameter automatically changes the parameter's Inherited setting to 'false'. Specifying the parameter's Inherited setting as 'true' automatically applies the switch level security policy to the parameter.

**Returns**: `VirtualSwitchSecurityPolicy`

```
Set-SecurityPolicy
    [-AllowPromiscuous <Boolean>]
    [-AllowPromiscuousInherited <Boolean>]
    [-ForgedTransmits <Boolean>]
    [-ForgedTransmitsInherited <Boolean>]
    [-MacChanges <Boolean>]
    [-MacChangesInherited <Boolean>]
    -VirtualPortGroupPolicy <VirtualPortgroupSecurityPolicy[]>
    -VirtualSwitchPolicy <VirtualSwitchSecurityPolicy[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowPromiscuous` | `Boolean` | No | Specifies whether promiscuous mode is enabled for the corresponding virtual port group or switch. |
| `-AllowPromiscuousInherited` | `Boolean` | No | Specifies whether the AllowPromiscuous setting is inherited from the parent virtual switch. |
| `-ForgedTransmits` | `Boolean` | No | Specifies whether forged transmits are enabled for the corresponding virtual port group or switch. |
| `-ForgedTransmitsInherited` | `Boolean` | No | Specifies whether the ForgedTransmits setting is inherited from the parent virtual switch. |
| `-MacChanges` | `Boolean` | No | Specifies whether MAC address changes are enabled for the corresponding virtual port group or switch. |
| `-MacChangesInherited` | `Boolean` | No | Specifies whether the MacChanges setting is inherited from the parent virtual switch. |
| `-VirtualPortGroupPolicy` | `VirtualPortgroupSecurityPolicy[]` | Yes | Specifies the virtual port group security policy that you want to configure. |
| `-VirtualSwitchPolicy` | `VirtualSwitchSecurityPolicy[]` | Yes | Specifies the virtual switch security policy that you want to configure. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VIOAuth2Client

Updates the configuration of the OAuth2 client registered with the VMware Identity Broker.

Updates the configuration of the OAuth2 client registered with the VMware Identity Broker. The VMware Identity Broker is an OAuth2 relay that is used by client applications to authenticate with vCenter using OAuth2.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.IdentityBroker.OAuth2Client`

```
Set-VIOAuth2Client
    [-AccessTokenTimeToLiveMinutes <Int32>]
    [-GrantTypes <String[]>]
    [-Name <String>]
    [-OAuth2Client <OAuth2Client[]>]
    [-PkceEnforced <Boolean>]
    [-PostLogoutRedirectUris <String[]>]
    [-RedirectUris <String[]>]
    [-RefreshTokenIdleTimeToLiveMinutes <Int32>]
    [-RefreshTokenTimeToLiveMinutes <Int32>]
    [-RuleSetNames <String[]>]
    [-Scope <String[]>]
    [-Secret <SecureString>]
    [-SecretTimeToLiveInMinutes <Int32>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AccessTokenTimeToLiveMinutes` | `Int32` | No | How long in minutes new access tokens issued to this client should live. |
| `-GrantTypes` | `String[]` | No | A list of OAuth 2.0 Access Grant Types that are enabled in this OAuth 2.0 Client.   Possible values are: password , client_credentials , refresh_token , authorization_code , token , id_token |
| `-Name` | `String` | No | The user-friendly name that you set for this OAuth 2.0 client. |
| `-OAuth2Client` | `OAuth2Client[]` | No | Specifies the OAuth 2 clients whose configuration you want to modify. |
| `-PkceEnforced` | `Boolean` | No | Indicates whether PKCE is enforced for the OAuth2 client.   This parameter is available only for vCenter instances of version 8.0 Update 3 and later. |
| `-PostLogoutRedirectUris` | `String[]` | No | The OAuth2 Relaying Party provides a list of absolute URLs with the PostLogoutRedirectUris parameter. When a logout occurs, the Auth2 Relaying Party might request that the User Agent of the End-Use... |
| `-RedirectUris` | `String[]` | No | Specifies a list of absolute URIs of application endpoints that are allowed to receive the authorization code and access token. The redirect URI sent by the application as part of the Authorization... |
| `-RefreshTokenIdleTimeToLiveMinutes` | `Int32` | No | Specifies how long in minutes new refresh tokens issued to this client should live. Only applicable and mandatory if the GrantTypes parameter includes ?refresh_token?. |
| `-RefreshTokenTimeToLiveMinutes` | `Int32` | No | How long in minutes new refresh tokens issued to this client can be idle. Only applicable and mandatory if GrantTypes includes ?refresh_token?. Its value should be less than the refresh token TTL v... |
| `-RuleSetNames` | `String[]` | No | Specifies a list of built-in rule set names to associate this client with. Each ruleset, allows the client to call a specific set of tenant APIs.   Possible values are: TENANT_ADMIN , IDP_AND_DIREC... |
| `-Scope` | `String[]` | No | A list of access request scopes that are allowed by this OAuth 2.0 Client.   Available scope options are: admin, user, profile, email, openid, group   admin - Admin Level Access   user - User Level... |
| `-Secret` | `SecureString` | No | Specifies the OAuth 2.0 Client secret. For additional security, the stored secret will not be returned by the Get-VIOAuth2Client and this command output. |
| `-SecretTimeToLiveInMinutes` | `Int32` | No | Specifies after what time in minutes the secret must be rotated.   This parameter is available only for vCenter instances of version 8.0 Update 3 and later. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `SwitchParameter` | No | Shows what would happen when the cmdlet runs. Note that the cmdlet is actually not started. |

---

### Set-VIPermission

This cmdlet modifies the properties of the specified permissions.

This cmdlet modifies the properties of the specified permissions. The cmdlet can change the role and define whether the permission propagates down the hierarchy to child inventory objects.

**Returns**: `Permission`

```
Set-VIPermission
    -Permission <Permission[]>
    [-Propagate <Boolean>]
    [-Role <Role>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Permission` | `Permission[]` | Yes | Specifies the permissions you want to modify. |
| `-Propagate` | `Boolean` | No | Indicates that you want to propagate the new permissions to the child inventory objects. |
| `-Role` | `Role` | No | Specifies a new role for the permissions. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VIRole

This cmdlet modifies the privileges of the provided roles.

**Returns**: `Role`

```
Set-VIRole
    [-AddPrivilege <Privilege[]>]
    [-Name <String>]
    [-RemovePrivilege <Privilege[]>]
    -Role <Role[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AddPrivilege` | `Privilege[]` | No | Specifies privileges and privilege groups you want to add to the provided roles. |
| `-Name` | `String` | No | Provides a new name for the provided role. |
| `-RemovePrivilege` | `Privilege[]` | No | Specifies privileges or privilege groups you want to remove from the provided roles. |
| `-Role` | `Role[]` | Yes | Specifies the roles you want to modify. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VIToolkitConfiguration

This cmdlet modifies the VMware PowerCLI configuration.

**Returns**: `PowerCLIConfiguration`

```
Set-VIToolkitConfiguration
    [-CEIPDataTransferProxyPolicy <ProxyPolicy>]
    [-DefaultVIServerMode <DefaultVIServerMode>]
    [-DisplayDeprecationWarnings <Boolean>]
    [-InvalidCertificateAction <BadCertificateAction>]
    [-ParticipateInCeip <Boolean>]
    [-ProxyPolicy <ProxyPolicy>]
    [-Scope <ConfigurationScope>]
    [-VMConsoleWindowBrowser <String>]
    [-WebOperationTimeoutSeconds <Int32>]
    [-PythonPath <String>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CEIPDataTransferProxyPolicy` | `ProxyPolicy` | No | Specifies the proxy policy for the connection through which Customer Experience Improvement Program (CEIP) data is sent to VMware. Setting this option is valid only when ParticipateInCEIP option is... |
| `-DefaultVIServerMode` | `DefaultVIServerMode` | No | Specifies the server connection mode. The new configuration takes effect immediately after you run the cmdlet. The following values are valid:   - Single - Switching to "single" removes all server ... |
| `-DisplayDeprecationWarnings` | `Boolean` | No | Indicates whether you want to see warnings about deprecated elements. |
| `-InvalidCertificateAction` | `BadCertificateAction` | No | Define the action to take when an attempted connection to a server fails due to a certificate error. The following values are valid:   Unset - this is the default value and it acts as a "Fail".   P... |
| `-ParticipateInCeip` | `Boolean` | No | Specifies if PowerCLI should send anonymous usage information to VMware. For more information about the Customer Experience Improvement Program (CEIP), see the PowerCLI User's Guide. Setting this o... |
| `-ProxyPolicy` | `ProxyPolicy` | No | Specifies whether VMware PowerCLI uses a system proxy server to connect to the vCenter Server system. The valid values are NoProxy and UseSystemProxy. |
| `-Scope` | `ConfigurationScope` | No | Specifies the scope of the setting that you want to modify. The parameter accepts Session, User, and All Users values.      *Session - the setting is valid for the current VMware PowerCLI session o... |
| `-VMConsoleWindowBrowser` | `String` | No | Specifies the Web browser to be used for opening virtual machine console windows (by using the Open-VMConsoleWindow cmdlet). The browser must be 32-bit. |
| `-WebOperationTimeoutSeconds` | `Int32` | No | Defines the timeout for Web operations. The default value is 300 sec. To specify an infinite operation timeout, pass a negative integer to this parameter. Changing this setting requires a restart o... |
| `-PythonPath` | `String` | No | Specifies the path to the Python executable, to be used by the VMware.ImageBuilder module. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-VMQuestion

This cmdlet answers the specified virtual machine question.

This cmdlet answers the specified virtual machine question using the value of the Option parameter. If the DefaultOption parameter is set to $true, the cmdlet answers the question with a default option, if any.

**Returns**: `VMQuestion`

```
Set-VMQuestion
    -DefaultOption
    -Option <Object>
    -VMQuestion <VMQuestion[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DefaultOption` | `SwitchParameter` | Yes | Indicates that you want to answer the virtual machine question using a default option. If no default option exists for the question, an error is generated. |
| `-Option` | `Object` | Yes | Specifies an object or string to provide an option to the virtual machine question. Wildcards are supported for string values. The string can be used to specify an option ID or label. If the string... |
| `-VMQuestion` | `VMQuestion[]` | Yes | Specifies the virtual machine question you want to answer. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Start-VIOAuth2ClientSecretRotation

Initiates a rotation of the secret of an OAuth 2 client.

Initiates a rotation of the secret of an OAuth 2 client. While the rotation process is running, both the old and the new client secret will be valid. To complete the rotation manually, use the Complete-VIOAuth2ClientSecretRotation command, or specify a time period after which the secret rotation must start automatically.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.IdentityBroker.OAuth2Client`

```
Start-VIOAuth2ClientSecretRotation
    [-OAuth2Client <OAuth2Client[]>]
    [-PrimarySecretAutoRetireDurationInMinutes <Int32>]
    -SecondarySecret <SecureString>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-OAuth2Client` | `OAuth2Client[]` | No | Specifies the OAuth 2 clients whose client secret you want to rotate. |
| `-PrimarySecretAutoRetireDurationInMinutes` | `Int32` | No | Sets how long, in minutes, before the primary secret is automatically retired. The default value is 1 day. The maximum value is 7 days. |
| `-SecondarySecret` | `SecureString` | Yes | Specifies an alternative secret to the client primary secret that will replace the existing primary secret when the secret rotation ends. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `SwitchParameter` | No | Shows what would happen when the cmdlet runs. Note that the cmdlet is actually not started. |

---

### Stop-ApplianceBackupJob

This cmdlet stops running backup jobs on a vCenter Server system.

This cmdlet stops a list of running backup jobs matching the specified parameters.

**Returns**: `ApplianceBackupJob`

```
Stop-ApplianceBackupJob
    [-BackupJob <ApplianceBackupJob[]>]
    [-Confirm]
    -Id <String[]>
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BackupJob` | `ApplianceBackupJob[]` | No | A list of ApplianceBackupJob objects representing the backup jobs to be stopped. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Id` | `String[]` | Yes | Stops backup jobs whose IDs match the specified IDs. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### TabExpansion2

TabExpansion2 [-inputScript] <string> [-cursorColumn] <int> [[-options] <hashtable>] [<CommonParameters>]

TabExpansion2 [-ast] <Ast> [-tokens] <Token[]> [-positionOfCursor] <IScriptPosition> [[-options] <hashtable>] [<CommonParameters>]

**Returns**: `returnValue`

```
TabExpansion2
    -ast <Ast>
    -cursorColumn <int>
    -inputScript <string>
    [-options <hashtable>]
    -positionOfCursor <IScriptPosition>
    -tokens <Token[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ast` | `Ast` | Yes |  |
| `-cursorColumn` | `int` | Yes |  |
| `-inputScript` | `string` | Yes |  |
| `-options` | `hashtable` | No |  |
| `-positionOfCursor` | `IScriptPosition` | Yes |  |
| `-tokens` | `Token[]` | Yes |  |

---

### Wait-ApplianceBackupJob

This cmdlet monitors the progress of a backup job and returns the ApplianceBackupJob object when the backup job is complete.

**Returns**: `ApplianceBackupJob`

```
Wait-ApplianceBackupJob
    [-BackupJob <ApplianceBackupJob[]>]
    -Id <String[]>
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BackupJob` | `ApplianceBackupJob[]` | No | Specifies one or more ApplianceBackupJob object(s) representing the backup jobs you want to monitor and receive when finished. |
| `-Id` | `String[]` | Yes | Specifies the IDs of the backup jobs you want to monitor and receive when finished. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

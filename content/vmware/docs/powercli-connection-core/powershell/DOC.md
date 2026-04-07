---
name: powercli-connection-core
description: "VMware PowerCLI 13.3 — vCenter connection, credentials, PowerCLI config, views, API access"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,connection-core,Connect-CisServer, Connect-VIServer, Disconnect-CisServer, Disconnect-VIServer, Get-PowerCLIConfiguration, Get-PowerCLIVersion, Get-VICommand, Get-VICredentialStoreItem, Get-View, Get-VIObjectByVIView, Get-VIProperty, HookGetViewAutoCompleter, New-VICredentialStoreItem, New-VIProperty, Remove-VICredentialStoreItem, Remove-VIProperty, Set-PowerCLIConfiguration"
---

# VMware PowerCLI — Connection & Core

vCenter connection, credentials, PowerCLI config, views, API access. Module: VMware.VimAutomation (17 cmdlets).

## Connect

### `Connect-CisServer`

**This cmdlet establishes a connection to a vSphere Automation SDK server.**

This cmdlet establishes a connection to the vSphere Automation SDK server specified by the -Server parameter.

**Parameters:**

- -Credential [PSCredential] (Required) Specifies a PSCredential object that contains credentials for authenticating with the server. For more information about the server authentication logic of PowerCLI, run "help about_server_authentication".
- -Force [SwitchParameter] (Optional) Suppresses all user interface prompts during the cmdlet execution. Currently, these include 'Multiple default servers' and 'Invalid certificate action'.
- -Menu [SwitchParameter] (Required) Indicates that you want to select a connection server from a list of recently connected servers. If Menu is set to $true, the cmdlet retrieves a list of the last visited servers and enters a nested command prompt, so that you can select a server from the list.
- -NotDefault [SwitchParameter] (Optional) Specifies that you do not want to save the specified servers as default servers.
- -Password [SecureString] (Optional) Specifies the password you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentication logic of PowerCLI, run "help about_server_authentication".   Note: If the password contains special characters, enclose the entire string in single quotes (').
- -Port [Int32] (Optional) Specifies the port on the server you want to use for the connection.
- -SamlSecurityContext [SamlSecurityContext] (Required) Specifies the SAML2 security context for the vCenter Server system. For more information about security contexts, see the about_security_context (about_security_context.html)article.
- -SaveCredentials [SwitchParameter] (Optional) Indicates that you want to save the specified credentials in the local credential store.
- -Server [String[]] (Required) Specifies the IP or DNS addresses of the vSphere Automation SDK servers you want to connect to.
- -SessionSecret [String] (Required) Specifies the ID of an existing vSphere Automation SDK session you want to reestablish.
- -User [String] (Optional) Specifies the user name you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentication logic of PowerCLI, run "help about_server_authentication".   Note: If the user name contains special characters, enclose the entire string in single quotes (').

**Examples:**

```powershell
Connect-CisServer -Server $serverAddress -User $user -Password $pass
```
_Connects to a vSphere Automation SDK server by using the User and Password parameters._

```powershell
$credential = Get-Credential
Connect-CisServer -Server $serverAddress -Credential $credential
```
_Connects to a vSphere Automation SDK server by using the Credential parameter._

```powershell
$serverConnection = Connect-CisServer -Server $serverAddress -User $user -Password $pass
Connect-CisServer -Server $serverAddress -SessionSecret $serverConnection.SessionSecret
```
_Connects to a vSphere Automation SDK server by using the SessionSecret parameter._

### `Connect-VIServer`

**This cmdlet establishes a connection to a vCenter Server system.**

This cmdlet establishes a connection to a vCenter Server system. The cmdlet starts a new session or re-establishes a previous session with a vCenter Server system using the specified parameters.

**Parameters:**

- -AllLinked [SwitchParameter] (Optional) Indicates whether you want to connect to vCenter Server in linked mode. If you specify $true for the AllLinked parameter and the server to which you want to connect is a part of a federation vCenter Server, you'll be connected to all members of the linked vCenter Server.   To use this option, PowerCLI must be configured to work in multiple servers connection mode. To configure PowerCLI to support multiple servers connection, specify Multiple for the DefaultVIServerMode parameter of the Set-PowerCLIConfiguration cmdlet.
- -Credential [PSCredential] (Optional) Specifies a PSCredential object that contains credentials for authenticating with the server. For more information about the server authentication logic of PowerCLI, run "help about_server_authentication". Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -Force [SwitchParameter] (Optional) Suppresses all user interface prompts during the cmdlet execution. Currently, these include 'Multiple default servers' and 'Invalid certificate action'.
- -Menu [SwitchParameter] (Required) Indicates that you want to select a connection server from a list of recently connected servers. If Menu is set to $true, the cmdlet retrieves a list of the last visited servers and enters a nested command prompt, so that you can select a server from the list.
- -NotDefault [SwitchParameter] (Optional) Indicates that you do not want to include the server to which you connect into the $defaultVIServers variable.
- -Password [String] (Optional) Specifies the password you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentication logic of PowerCLI, run "help about_server_authentication".   Note: If the password contains special characters, enclose the entire string in single quotes (').
- -Port [Int32] (Optional) Specifies the port on the server you want to use for the connection.
- -Protocol [String] (Optional) Specifies the Internet protocol you want to use for the connection. It can be either http or https.
- -SamlSecurityContext [SamlSecurityContext] (Required) Specifies the SAML2 security context for the vCenter Server system. For more information about security contexts, see the about_security_context (about_security_context.html)article.
- -SaveCredentials [SwitchParameter] (Optional) Indicates that you want to save the specified credentials in the local credential store.   Note: This parameter is not supported on the Core edition of PowerShell.
- -Server [String[]] (Required) Specifies the IP address or the DNS name of the vSphere server to which you want to connect. You can also specify a server by providing its IPv6 address enclosed in square brackets, for example [fe80::250:56ff:feb0:74bd%4].
- -Session [String] (Optional) Specifies the ID of an existing vCenter Server session you want to re-establish.
- -User [String] (Optional) Specifies the user name you want to use for authenticating with the server. If the Credential parameter is also specified, this parameter is ignored. For more information about the server authentication logic of PowerCLI, run "help about_server_authentication". Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.   Note: If the user name contains special characters, enclose the entire string in single quotes (').

**Examples:**

```powershell
Connect-VIServer -Server 10.23.112.235 -Protocol https -User admin -Password pass
```
_Connects to a vSphere server by using the User and Password parameters._

```powershell
Connect-VIServer Server -Credential $myCredentialsObject -Port 1234
```
_Connects to a vSphere server by using a credential object._

```powershell
Connect-VIServer "Server" -Session $sessionId
```
_Connects by using a server session ID. Once you connect to a server, you can save the session ID - $serverObject.SessionId, so that you can restore the existing server connection instead of reconnecting._

## Disconnect

### `Disconnect-CisServer`

**This cmdlet closes the connection to one or more vSphere Automation SDK servers.**

**Parameters:**

- -Force [SwitchParameter] (Optional) Specifies that you want to remove all existing connections to the specified servers.
- -Server [CisServer[]] (Optional) Specifies the vSphere Automation SDK servers you want to disconnect from.

**Examples:**

```powershell
$server = Connect-CisServer -Server 'server_name' -User 'user@domain' -Password 'user_password'
Disconnect-CisServer $server -Confirm:$false
```
_Disconnects the specified vSphere Automation SDK server without asking for confirmation._

```powershell
Connect-CisServer -Server 'server_name' -User 'user@domain' -Password 'user_password'
Connect-CisServer -Server 'server2_name' -User 'user@domain' -Password 'user_password'
Disconnect-CisServer * -Confirm:$false
```
_Disconnects all connected vSphere Automation SDK servers without asking for confirmation._

### `Disconnect-VIServer`

**This cmdlet closes the connection to a vCenter Server system.**

This cmdlet closes the connection to a vCenter Server system. In PowerCLI, you can have multiple connections to a server. In order to disconnect from a server, you must close all active connections to it. By default, Disconnect-VIServer closes only the last connection to the specified server. To close all active connections to a server, use the Force parameter or run the cmdlet for each connection. When a server is disconnected, it is removed from the default servers list. For more information about default servers, see the description of Connect-VIServer.

**Parameters:**

- -Force [SwitchParameter] (Optional) Indicates that you want to close all active connections to the specified server and disconnect from it. If the value is $false, the cmdlet closes only the last connection to the specified server and you must run Disconnect-VIServer for each active connection to this server in order to disconnect from it.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems you want to disconnect from.

**Examples:**

```powershell
$Server = Connect-VIServer 10.23.112.235

Disconnect-VIServer -Server $Server
```
_Connects to a server with an IP address 10.23.112.235 and saves the returned VIServer object in the $Server variable. Then disconnects from the specified server._

```powershell
Disconnect-VIServer -Server $global:DefaultVIServers -Force
```
_Closes all connections to the default servers._

```powershell
Disconnect-VIServer -Server * -Force
```
_Disconnects all server connections._

## Get

### `Get-PowerCLIConfiguration`

**This cmdlet retrieves the VMware PowerCLI proxy configuration and default servers policy.**

**Parameters:**

- -Scope [ConfigurationScope] (Optional) Specifies a scope to filter VMware PowerCLI settings by. The parameter accepts Session, User, and All Users values.

**Examples:**

```powershell
Get-PowerCLIConfiguration
```
_Retrieves information about the VMware PowerCLI configuration for every scope._

```powershell
Get-PowerCLIConfiguration -Scope User
```
_Retrieves information about the VMware PowerCLI configuration for the User scope._

```powershell
Get-PowerCLIConfiguration -Scope ([VMware.VimAutomation.ViCore.Types.V1.ConfigurationScope]::Session -bor [VMware.VimAutomation.ViCore.Types.V1.ConfigurationScope]::User)
```
_Retrieves information about the VMware PowerCLI configuration for the User and Session scopes._

### `Get-PowerCLIVersion`

**This cmdlet retrieves the versions of the installed PowerCLI snapins.**

**Examples:**

```powershell
Get-PowerCLIVersion
```
_Retrieves the version of VMware PowerCLI._

```powershell
Get-PowerCLIVersion | select -expand SnapinVersions
```
_Lists the versions of additional PowerCLI snapins._

### `Get-VICommand`

**This function retrieves all commands of the VMware modules.**

This function retrieves all commands of the imported VMware modules, including cmdlets, aliases, and functions.

**Parameters:**

- -Name [String] (Optional) Specifies the name of the command you want to retrieve.

### `Get-VICredentialStoreItem`

**This cmdlet retrieves the credential store items available on a vCenter Server system.**

This cmdlet retrieves the credential store items that correspond to the filter criteria defined by the Host and User parameters. Both the Host and User parameters support wildcards. If none of the Host and User parameters are specified, all available credential store items are returned. If the Host and User parameters are specified without using wildcards, and no item is found, non-terminating errors are reported for the Host and User parameters. If no file is specified, items are retrieved from the default credential store file %APPDATA%\VMware\credstore\vicredentials.xml.

**Parameters:**

- -File [String] (Optional) Specifies a path to a file where the credential store items that you want to retrieve are saved.
- -Host [String] (Optional) Specifies hosts for which you want to retrieve credential store items.
- -User [String] (Optional) Specifies users for which you want to retrieve credential store items.

**Examples:**

```powershell
Get-VICredentialStoreItem -User admin -Host 192.168.1.10 -File 'credentials.xml'
```
_Retrieves the credentials for the 'admin' user on the specified host from a credential store file._

### `Get-VIObjectByVIView`

**This cmdlet converts a vSphere View object to a VIObject.**

This cmdlet converts a vSphere View object to a VIObject using the object ID provided by the MoRef parameter. If the View object is a ServiceInstance, you cannot convert it to a VIObject.

**Parameters:**

- -MORef [ManagedObjectReference[]] (Required) Specifies the managed object ID, obtained from a property of another managed object or a view.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VIView [ViewBase[]] (Required) Specifies the vSphere .NET View object you want to convert to a VMware PowerCLI object.

**Examples:**

```powershell
$view = Get-VM VM | Stop-VM | Get-View

$vm = Get-VIObjectByVIView $view | Start-VM
```
_Gets the VM virtual machine, stops it, and gets its view object. Then, the command gets the virtual machine object using the Get-VIObjectByVIView cmdlet and starts the VM virtual machine._

### `Get-VIProperty`

**This cmdlet retrieves extended object properties.**

This cmdlet retrieves the extended properties and filters them by using  the provided cmdlet parameters.

**Parameters:**

- -DeclaredOnly [SwitchParameter] (Optional) Indicates that you want to retrieve only the extended properties that have been directly defined for the specified object types.
- -Name [String[]] (Optional) Specifies the names of the extended properties you want to retrieve.
- -ObjectType [String[]] (Optional) Specifies the object types for which you want to retrieve extended properties.

**Examples:**

```powershell
Get-VIProperty -Name "property*"
```
_Retrieve all custom properties that match the specified name pattern._

```powershell
Get-VIProperty -ObjectType 'VirtualMachine'
```
_Retrieve all custom properties for the specified object type._

```powershell
Get-VIProperty -ObjectType 'VirtualMachine' -DeclaredOnly
```
_Retrieve all custom properties for the specified object type that are not inherited._

### `Get-View`

**This cmdlet returns the vSphere View objects that correspond to the specified search criteria.**

This cmdlet returns the vSphere View objects that correspond to the specified search criteria. The cmdlet retrieves the vSphere View objects specified by their IDs or by their corresponding vSphere inventory objects (VIObject). A View object ID is a <type>-<value> string. For objects with constant names such as AlarmManager and ServiceInstance, the ID format is <type> (see the examples).

**Parameters:**

- -Filter [Hashtable] (Optional) Specifies a hash of <name>-<value> pairs, where <name> represents the property value to test, and <value> represents a regex pattern the property must match. If more than one pair is present, all the patterns must match.
- -Id [ManagedObjectReference[]] (Required) Specifies the IDs of the View objects you want to retrieve. A view object ID is a <type>-<value> string. For objects with constant names such as AlarmManager and ServiceInstance, the ID format is <type> (see the examples).   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Property [String[]] (Optional) Specifies the properties of the view object you want to retrieve. If no value is given, all properties are shown.
- -RelatedObject [ViewBaseMirroredObject[]] (Required) Specifies view-related objects to retrieve their views.
- -SearchRoot [ManagedObjectReference] (Optional) Specifies a starting point for the search (in the context of the inventory).
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -ViewType [Type] (Required) Specifies the type of the View objects you want to retrieve. This parameter accepts ClusterComputeResource, ComputeResource, Datacenter,Datastore, DistributedVirtualPortgroup, DistributedVirtualSwitch, Folder, HostSystem, Network, OpaqueNetwork, ResourcePool,StoragePod, VirtualApp, VirtualMachine, and VmwareDistributedVirtualSwitch values.
- -VIObject [VIObject[]] (Required) Specifies the vSphere managed object that corresponds to the View object you want to retrieve.   When you pass VIServer, Get-View returns ServiceInstance. When the retrieved View object is a ServiceInstance, you cannot convert it to a VIObject with Get-VIObjectByVIView.

**Examples:**

```powershell
$vm = Get-View -ViewType VirtualMachine -Filter @{"Name" = "VM"}

$vmhostView = Get-View -ID $vm.Runtime.Host

$vmhostView.Summary.Runtime
```
_Gets the VM virtual machine using a filter by name, populates the view object and retrieves the runtime information._

```powershell
$folder = Get-Folder Folder | Get-View

Get-View -SearchRoot $folder.MoRef -ViewType "VirtualMachine"
```
_Gets the view objects of virtual machines by specifying the root folder - MoRef._

```powershell
$folder = Get-Folder VM

$folderView = Get-View $folder -Property "[VirtualMachine]ChildEntity.Network.*"

$folderView.LinkedView.ChildEntity[0].LinkedView.Network
```
_Gets the view of a folder by specifying for the Property parameter a property path, which leads to the networks of the virtual machines in the specified folder. Retrieves the first of the returned networks._

## New

### `New-VICredentialStoreItem`

**This cmdlet creates a new entry in the credential store.**

This cmdlet creates a new entry in the credential store. If there is an existing entry for the specified host and user, it is overwritten. If the credential store file does not exist, it is created (along with its directory if needed). If no file is specified, the item is created in the default credential store file %APPDATA%\VMware\credstore\vicredentials.xml. Credential store items for vCloud Director servers must contain user name and organization in the following format: user_name:organization_name, where both names are lower-cased.

**Parameters:**

- -File [String] (Optional) Specifies a file path where you want to store the new credentials.
- -Host [String] (Required) Specifies the host for which you want to create the new credentials item.
- -Password [String] (Optional) Specifies a password.
- -User [String] (Required) Specifies a user name.

**Examples:**

```powershell
New-VICredentialStoreItem -Host 192.168.1.10 -User Admin -Password pass
```
_Adds a new item in the default credential store file._

### `New-VIProperty`

**This cmdlet creates a new extension property on the specified object type.**

This cmdlet creates a new extension property on the specified object type. Changes take effect upon the next retrieval of the corresponding objects.

**Parameters:**

- -BasedOnExtensionProperty [String[]] (Optional) Specifies a list of strings that maps the properties of the $this.ExtensionData object. Use this parameter to specify which members of ExtensionData are used by the script block provided for the Value parameter. This parameter is case-sensitive.
- -Force [SwitchParameter] (Optional) Indicates that you want to create the new property even if another property with the same name exists for the specified object type. This parameter is not applicable for core properties of an object type.
- -Name [String] (Required) Specifies a name for the new extension property. Names are case-sensitive and can include only letters, numbers, and the underscore symbol. The name of a property must start with a letter or underscore.
- -ObjectType [String[]] (Required) Specifies the object types to which you want to append the new property. All PowerCLI object types are supported.
- -Value [ScriptBlock] (Required) Specifies a script block you want to use to compute the value of the new extended property.
- -ValueFromExtensionProperty [String] (Required) Specifies a string that maps a property of the $this.ExtensionData object. This parameter is case-sensitive.

**Examples:**

```powershell
New-VIProperty -ObjectType VirtualMachine -Name CommittedSpaceMB -Value { $vm = $args[0]; $sum = 0; $vm.ExtensionData.Storage.PerDatastoreUsage | foreach { $sum += $_.Committed} ; $sum = [int]($sum / 1024 / 1024); return $sum }

Get-VM | select Name, CommittedSpaceMB
```
_Creates a script-based property for the VirtualMachine object type that calculates the committed space of a virtual machine._

```powershell
New-VIProperty -ObjectType VirtualMachine -Name CommittedSpaceMB -Value { $vm = $args[0]; $sum = 0; $vm.ExtensionData.Storage.PerDatastoreUsage | foreach { $sum += $_.Committed} ; $sum = [int]($sum / 1024 / 1024); return $sum } -BasedOnExtensionProperty 'Storage.PerDatastoreUsage.Committed' -Force

Get-VM | select Name, CommittedSpaceMB
```
_Creates a property that calculates the committed space of a virtual machine. The cmdlet uses the BasedOnExtensionProperty parameter to specify which   ExtensionData member is used by the script block. This mean that during the creation of each virtual machine, only the specified property of extension data - Storage.PerDatastoreUsage.Committed will be filled up._

```powershell
New-VIProperty -ObjectType VirtualMachine -Name CommittedSpace -ValueFromExtensionProperty 'SUM Storage.PerDatastoreUsage.Committed'
```
_Creates a new property that calculates the committed storage based on the property and aggregation function SUM specified by the ValueFromExtensionProperty parameter._

## Other

### `HookGetViewAutoCompleter`

**HookGetViewAutoCompleter**

## Remove

### `Remove-VICredentialStoreItem`

**This cmdlet removes the specified credential store items.**

This cmdlet removes the credential store items that match the specified Host and User parameters. At least one of the Host and User parameters must be provided. To remove all passwords,  call "Remove-VICredentialStoreItem *", which is a wildcard matching all hosts.

**Parameters:**

- -CredentialStoreItem [VICredentialStoreItem[]] (Required) Specifies the credential store items you want to remove.
- -File [String] (Optional) Specifies the file location of the credential store items that are to be removed.
- -Host [String] (Optional) Specifies a host to filter the credential store items you want to remove.
- -User [String] (Optional) Specifies a user to filter the credential store items you want to remove.

**Examples:**

```powershell
Remove-VICredentialStoreItem -Host 192.168.1.100 -Confirm
```
_Removes all credentials for the specified host from the default credential store file._

```powershell
Remove-VICredentialStoreItem -User 'admin' -Host '192.168.*' -File 'credentials.xml' -Confirm
```
_Removes all credentials for the specified user and network from a credential store file._

### `Remove-VIProperty`

**This cmdlet removes the extended properties from the specified object types.**

This cmdlet removes the extended properties from the specified object types. Changes take effect upon the next retrieval of the corresponding objects.

**Parameters:**

- -Name [String[]] (Required) Specifies the names of the extended properties you want to remove.
- -ObjectType [String[]] (Required) Specifies the object types to which the extended properties you want to remove belong.
- -VIProperty [VIProperty[]] (Required) Specifies the extended object properties you want to remove.

**Examples:**

```powershell
Remove-VIProperty -Name * -ObjectType *
```
_Removes all custom properties._

```powershell
Remove-VIProperty -Name * -ObjectType VirtualMachine
```
_Removes all custom properties for the VirtualMachine object type._

```powershell
Remove-VIProperty -Name OverallStatus, ConfigStatus -ObjectType VirtualMachine
```
_Removes the OverallStatus and ConfigStatus for the VirtualMachine object type._

## Set

### `Set-PowerCLIConfiguration`

**This cmdlet modifies the VMware PowerCLI configuration.**

**Parameters:**

- -CEIPDataTransferProxyPolicy [ProxyPolicy] (Optional) Specifies the proxy policy for the connection through which Customer Experience Improvement Program (CEIP) data is sent to VMware. Setting this option is valid only when ParticipateInCEIP option is set to $true. Changing this setting requires a restart of PowerCLI before it takes effect.
- -DefaultVIServerMode [DefaultVIServerMode] (Optional) Specifies the server connection mode. The new configuration takes effect immediately after you run the cmdlet. The following values are valid:   - Single - Switching to "single" removes all server connections except the last established one. If no target servers are specified, cmdlets run only on the last connected server.   - Multiple - All servers connected after switching to "multiple" mode are stored together with the current server connection in an array variable. If no target servers are specified, cmdlets run on the servers in the variable.   For more information on default servers, see the description of Connect-VIServer.
- -DisplayDeprecationWarnings [Boolean] (Optional) Indicates whether you want to see warnings about deprecated elements.
- -InvalidCertificateAction [BadCertificateAction] (Optional) Define the action to take when an attempted connection to a server fails due to a certificate error. The following values are valid:   Unset - this is the default value and it acts as a "Fail".   Prompt - if the server certificate is not trusted the cmdlet will prompt you for a course of action before it continues. There are several options:             - Deny - Cancel the server connection.   - Connect once - Establish the server connection and suppress further warnings for the current PowerShell session.   - Add a permanent exception for the server_address/certificate pair - Persist the server certificate in the PowerCLI Trusted Certificate Store (PCTCS) for the current user and establish the server connection.   - Add a permanent exception for all users - Persist the server/certificate pair both in the current user PowerCLI Trusted Certificate Store (PCTCS) and in the All Users PCTCS and establish the server connection.     Fail - the cmdlet will not establish connection if the certificate is not valid.   Ignore - the cmdlet will establish the connection without taking into account that the certificate is invalid.   Warn - the cmdlet will display a warning saying that the certificate is not valid, the reason why it is not considered valid and then will print additional information about the certificate.   On PowerShell Core, only the Fail and Ignore options are supported.  For more information about invalid certificates, run 'Get-Help about_invalid_certificates'.
- -ParticipateInCeip [Boolean] (Optional) Specifies if PowerCLI should send anonymous usage information to VMware. For more information about the Customer Experience Improvement Program (CEIP), see the PowerCLI User's Guide. Setting this option is valid only for the AllUsers and User configuration scopes. Changing this setting requires a restart of PowerCLI before it takes effect.
- -ProxyPolicy [ProxyPolicy] (Optional) Specifies whether VMware PowerCLI uses a system proxy server to connect to the vCenter Server system. The valid values are NoProxy and UseSystemProxy.
- -Scope [ConfigurationScope] (Optional) Specifies the scope of the setting that you want to modify. The parameter accepts Session, User, and All Users values.      *Session - the setting is valid for the current VMware PowerCLI session only and overrides any User and All Users settings.      *User - the setting is valid for the current Windows user only, overrides All Users settings, and is applied only if a Session setting cannot be detected.      *All Users - the setting is valid for all users and is applied only if Session and User settings cannot be detected.
- -VMConsoleWindowBrowser [String] (Optional) Specifies the Web browser to be used for opening virtual machine console windows (by using the Open-VMConsoleWindow cmdlet). The browser must be 32-bit.
- -WebOperationTimeoutSeconds [Int32] (Optional) Defines the timeout for Web operations. The default value is 300 sec. To specify an infinite operation timeout, pass a negative integer to this parameter. Changing this setting requires a restart of PowerCLI before it takes effect.
- -PythonPath [String] (Optional) Specifies the path to the Python executable, to be used by the VMware.ImageBuilder module.

**Examples:**

```powershell
Set-PowerCLIConfiguration -ProxyPolicy NoProxy -Scope Session
```
_Modifies the proxy policy of VMware PowerCLI for the Session scope._

```powershell
Set-PowerCLIConfiguration -ProxyPolicy NoProxy -DefaultVIServerMode Single
```
_Changes the default server connection mode and the proxy policy of VMware PowerCLI for the User scope._

```powershell
Set-PowerCLIConfiguration -DefaultVIServerMode 'Single' -Scope ([VMware.VimAutomation.ViCore.Types.V1.ConfigurationScope]::User -bor [VMware.VimAutomation.ViCore.Types.V1.ConfigurationScope]::AllUsers)
```
_Changes the default server connection mode of VMware PowerCLI for the User and AllUsers scopes._

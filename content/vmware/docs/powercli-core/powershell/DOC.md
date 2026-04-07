---
name: powercli-core
description: "VMware PowerCLI 13.3 — vCenter connection, configuration, credential store, raw API access via Get-View"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Complete-VIOAuth2ClientSecretRotation,Connect-VIServer,Disconnect-VIServer,Get-PowerCLIConfiguration,Get-PowerCLIVersion,Get-VICommand,Get-VICredentialStoreItem,Get-VIObjectByVIView,Get-VIProperty,Get-View,New-VICredentialStoreItem,New-VIProperty,Remove-VICredentialStoreItem,Remove-VIProperty,Set-PowerCLIConfiguration"
---

# VMware PowerCLI — vCenter connection, configuration, credential store, raw API access via Get-View

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Complete-VIOAuth2ClientSecretRotation` | Forces an immediate secret rotation for a specific OAuth 2 client. |
| `Connect-VIServer` | This cmdlet establishes a connection to a vCenter Server system. |
| `Disconnect-VIServer` | This cmdlet closes the connection to a vCenter Server system. |
| `Get-PowerCLIConfiguration` | This cmdlet retrieves the VMware PowerCLI proxy configuration and default servers policy. |
| `Get-PowerCLIVersion` | This cmdlet retrieves the versions of the installed PowerCLI snapins. |
| `Get-VICommand` | This function retrieves all commands of the VMware modules. |
| `Get-VICredentialStoreItem` | This cmdlet retrieves the credential store items available on a vCenter Server system. |
| `Get-VIObjectByVIView` | This cmdlet converts a vSphere View object to a VIObject. |
| `Get-VIProperty` | This cmdlet retrieves extended object properties. |
| `Get-View` | This cmdlet returns the vSphere View objects that correspond to the specified search criteria. |
| `New-VICredentialStoreItem` | This cmdlet creates a new entry in the credential store. |
| `New-VIProperty` | This cmdlet creates a new extension property on the specified object type. |
| `Remove-VICredentialStoreItem` | This cmdlet removes the specified credential store items. |
| `Remove-VIProperty` | This cmdlet removes the extended properties from the specified object types. |
| `Set-PowerCLIConfiguration` | This cmdlet modifies the VMware PowerCLI configuration. |

---

### Complete-VIOAuth2ClientSecretRotation

Forces an immediate secret rotation for a specific OAuth 2 client.

Forces an immediate secret rotation for a specific OAuth 2 client. The new secret becomes the current secret of the OAuth 2 client.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.IdentityBroker.OAuth2Client`

```
Complete-VIOAuth2ClientSecretRotation
    [-OAuth2Client <OAuth2Client[]>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-OAuth2Client` | `OAuth2Client[]` | No | Specifies the OAuth 2 client whose secrete rotation you want to force immediately. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `SwitchParameter` | No | Shows what would happen when the cmdlet runs. Note that the cmdlet is actually not started. |

---

### Connect-VIServer

This cmdlet establishes a connection to a vCenter Server system.

This cmdlet establishes a connection to a vCenter Server system. The cmdlet starts a new session or re-establishes a previous session with a vCenter Server system using the specified parameters.

**Returns**: `VIServer`

```
Connect-VIServer
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

### Disconnect-VIServer

This cmdlet closes the connection to a vCenter Server system.

This cmdlet closes the connection to a vCenter Server system. In PowerCLI, you can have multiple connections to a server. In order to disconnect from a server, you must close all active connections to it. By default, Disconnect-VIServer closes only the last connection to the specified server. To close all active connections to a server, use the Force parameter or run the cmdlet for each connection. When a server is disconnected, it is removed from the default servers list. For more informatio...

**Returns**: `None`

```
Disconnect-VIServer
    [-Force]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `SwitchParameter` | No | Indicates that you want to close all active connections to the specified server and disconnect from it. If the value is $false, the cmdlet closes only the last connection to the specified server an... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems you want to disconnect from. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Get-PowerCLIConfiguration

This cmdlet retrieves the VMware PowerCLI proxy configuration and default servers policy.

**Returns**: `PowerCLIConfiguration`

```
Get-PowerCLIConfiguration
    [-Scope <ConfigurationScope>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Scope` | `ConfigurationScope` | No | Specifies a scope to filter VMware PowerCLI settings by. The parameter accepts Session, User, and All Users values. |

---

### Get-PowerCLIVersion

This cmdlet retrieves the versions of the installed PowerCLI snapins.

**Returns**: `PowerCLIVersion`

```
Get-PowerCLIVersion
```

---

### Get-VICommand

This function retrieves all commands of the VMware modules.

This function retrieves all commands of the imported VMware modules, including cmdlets, aliases, and functions.

**Returns**: `None documented`

```
Get-VICommand
    [-Name <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | No | Specifies the name of the command you want to retrieve. |

---

### Get-VICredentialStoreItem

This cmdlet retrieves the credential store items available on a vCenter Server system.

This cmdlet retrieves the credential store items that correspond to the filter criteria defined by the Host and User parameters. Both the Host and User parameters support wildcards. If none of the Host and User parameters are specified, all available credential store items are returned. If the Host and User parameters are specified without using wildcards, and no item is found, non-terminating errors are reported for the Host and User parameters. If no file is specified, items are retrieved f...

**Returns**: `VICredentialStoreItem`

```
Get-VICredentialStoreItem
    [-File <String>]
    [-Host <String>]
    [-User <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-File` | `String` | No | Specifies a path to a file where the credential store items that you want to retrieve are saved. |
| `-Host` | `String` | No | Specifies hosts for which you want to retrieve credential store items. |
| `-User` | `String` | No | Specifies users for which you want to retrieve credential store items. |

---

### Get-VIObjectByVIView

This cmdlet converts a vSphere View object to a VIObject.

This cmdlet converts a vSphere View object to a VIObject using the object ID provided by the MoRef parameter. If the View object is a ServiceInstance, you cannot convert it to a VIObject.

**Returns**: `VIObject`

```
Get-VIObjectByVIView
    -MORef <ManagedObjectReference[]>
    [-Server <VIServer[]>]
    -VIView <ViewBase[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-MORef` | `ManagedObjectReference[]` | Yes | Specifies the managed object ID, obtained from a property of another managed object or a view. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-VIView` | `ViewBase[]` | Yes | Specifies the vSphere .NET View object you want to convert to a VMware PowerCLI object. |

---

### Get-VIProperty

This cmdlet retrieves extended object properties.

This cmdlet retrieves the extended properties and filters them by using  the provided cmdlet parameters.

**Returns**: `VIProperty`

```
Get-VIProperty
    [-DeclaredOnly]
    [-Name <String[]>]
    [-ObjectType <String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DeclaredOnly` | `SwitchParameter` | No | Indicates that you want to retrieve only the extended properties that have been directly defined for the specified object types. |
| `-Name` | `String[]` | No | Specifies the names of the extended properties you want to retrieve. |
| `-ObjectType` | `String[]` | No | Specifies the object types for which you want to retrieve extended properties. |

---

### Get-View

This cmdlet returns the vSphere View objects that correspond to the specified search criteria.

This cmdlet returns the vSphere View objects that correspond to the specified search criteria. The cmdlet retrieves the vSphere View objects specified by their IDs or by their corresponding vSphere inventory objects (VIObject). A View object ID is a <type>-<value> string. For objects with constant names such as AlarmManager and ServiceInstance, the ID format is <type> (see the examples).

**Returns**: `ViewBase`

```
Get-View
    [-Filter <Hashtable>]
    -Id <ManagedObjectReference[]>
    [-Property <String[]>]
    -RelatedObject <ViewBaseMirroredObject[]>
    [-SearchRoot <ManagedObjectReference>]
    [-Server <VIServer[]>]
    -ViewType <Type>
    -VIObject <VIObject[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Filter` | `Hashtable` | No | Specifies a hash of <name>-<value> pairs, where <name> represents the property value to test, and <value> represents a regex pattern the property must match. If more than one pair is present, all t... |
| `-Id` | `ManagedObjectReference[]` | Yes | Specifies the IDs of the View objects you want to retrieve. A view object ID is a <type>-<value> string. For objects with constant names such as AlarmManager and ServiceInstance, the ID format is <... |
| `-Property` | `String[]` | No | Specifies the properties of the view object you want to retrieve. If no value is given, all properties are shown. |
| `-RelatedObject` | `ViewBaseMirroredObject[]` | Yes | Specifies view-related objects to retrieve their views. |
| `-SearchRoot` | `ManagedObjectReference` | No | Specifies a starting point for the search (in the context of the inventory). |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-ViewType` | `Type` | Yes | Specifies the type of the View objects you want to retrieve. This parameter accepts ClusterComputeResource, ComputeResource, Datacenter,Datastore, DistributedVirtualPortgroup, DistributedVirtualSwi... |
| `-VIObject` | `VIObject[]` | Yes | Specifies the vSphere managed object that corresponds to the View object you want to retrieve.   When you pass VIServer, Get-View returns ServiceInstance. When the retrieved View object is a Servic... |

---

### New-VICredentialStoreItem

This cmdlet creates a new entry in the credential store.

This cmdlet creates a new entry in the credential store. If there is an existing entry for the specified host and user, it is overwritten. If the credential store file does not exist, it is created (along with its directory if needed). If no file is specified, the item is created in the default credential store file %APPDATA%\VMware\credstore\vicredentials.xml. Credential store items for vCloud Director servers must contain user name and organization in the following format: user_name:organiz...

**Returns**: `VICredentialStoreItem`

```
New-VICredentialStoreItem
    [-File <String>]
    -Host <String>
    [-Password <String>]
    -User <String>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-File` | `String` | No | Specifies a file path where you want to store the new credentials. |
| `-Host` | `String` | Yes | Specifies the host for which you want to create the new credentials item. |
| `-Password` | `String` | No | Specifies a password. |
| `-User` | `String` | Yes | Specifies a user name. |

---

### New-VIProperty

This cmdlet creates a new extension property on the specified object type.

This cmdlet creates a new extension property on the specified object type. Changes take effect upon the next retrieval of the corresponding objects.

**Returns**: `VIProperty`

```
New-VIProperty
    [-BasedOnExtensionProperty <String[]>]
    [-Force]
    -Name <String>
    -ObjectType <String[]>
    -Value <ScriptBlock>
    -ValueFromExtensionProperty <String>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BasedOnExtensionProperty` | `String[]` | No | Specifies a list of strings that maps the properties of the $this.ExtensionData object. Use this parameter to specify which members of ExtensionData are used by the script block provided for the Va... |
| `-Force` | `SwitchParameter` | No | Indicates that you want to create the new property even if another property with the same name exists for the specified object type. This parameter is not applicable for core properties of an objec... |
| `-Name` | `String` | Yes | Specifies a name for the new extension property. Names are case-sensitive and can include only letters, numbers, and the underscore symbol. The name of a property must start with a letter or unders... |
| `-ObjectType` | `String[]` | Yes | Specifies the object types to which you want to append the new property. All PowerCLI object types are supported. |
| `-Value` | `ScriptBlock` | Yes | Specifies a script block you want to use to compute the value of the new extended property. |
| `-ValueFromExtensionProperty` | `String` | Yes | Specifies a string that maps a property of the $this.ExtensionData object. This parameter is case-sensitive. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VICredentialStoreItem

This cmdlet removes the specified credential store items.

This cmdlet removes the credential store items that match the specified Host and User parameters. At least one of the Host and User parameters must be provided. To remove all passwords,  call "Remove-VICredentialStoreItem *", which is a wildcard matching all hosts.

**Returns**: `None`

```
Remove-VICredentialStoreItem
    -CredentialStoreItem <VICredentialStoreItem[]>
    [-File <String>]
    [-Host <String>]
    [-User <String>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CredentialStoreItem` | `VICredentialStoreItem[]` | Yes | Specifies the credential store items you want to remove. |
| `-File` | `String` | No | Specifies the file location of the credential store items that are to be removed. |
| `-Host` | `String` | No | Specifies a host to filter the credential store items you want to remove. |
| `-User` | `String` | No | Specifies a user to filter the credential store items you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-VIProperty

This cmdlet removes the extended properties from the specified object types.

This cmdlet removes the extended properties from the specified object types. Changes take effect upon the next retrieval of the corresponding objects.

**Returns**: `None`

```
Remove-VIProperty
    -Name <String[]>
    -ObjectType <String[]>
    -VIProperty <VIProperty[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String[]` | Yes | Specifies the names of the extended properties you want to remove. |
| `-ObjectType` | `String[]` | Yes | Specifies the object types to which the extended properties you want to remove belong. |
| `-VIProperty` | `VIProperty[]` | Yes | Specifies the extended object properties you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-PowerCLIConfiguration

This cmdlet modifies the VMware PowerCLI configuration.

**Returns**: `PowerCLIConfiguration`

```
Set-PowerCLIConfiguration
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

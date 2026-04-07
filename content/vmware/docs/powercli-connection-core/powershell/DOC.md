---
name: powercli-connection-core
description: "VMware PowerCLI 13.3 — vCenter connection, credentials, PowerCLI config, views, API access"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,connection-core,Connect-CisServer, Connect-VIServer, Disconnect-CisServer, Disconnect-VIServer, Get-PowerCLIConfiguration, Get-PowerCLIVersion, Get-VICommand, Get-VICredentialStoreItem, Get-View, Get-VIObjectByVIView, Get-VIProperty, HookGetViewAutoCompleter, New-VICredentialStoreItem, New-VIProperty, Remove-VICredentialStoreItem, Remove-VIProperty, Set-PowerCLIConfiguration"
---

# VMware PowerCLI — Connection & Core

vCenter connection, credentials, PowerCLI config, views, API access. Module: VMware.VimAutomation (17 cmdlets).

## Cmdlet Reference (17 cmdlets)

### Connect

#### `Connect-CisServer`

This cmdlet establishes a connection to a vSphere Automation SDK server.

**Parameters**: `Server, User, Password, Port, Credential, NotDefault, Force, SaveCredentials, SessionSecret, Menu, SamlSecurityContext`

#### `Connect-VIServer`

This cmdlet establishes a connection to a vCenter Server system.

**Parameters**: `Server, Port, Protocol, Credential, User, Password, Session, SamlSecurityContext, NotDefault, SaveCredentials, AllLinked, Force` (+1 more)

```powershell
Connect-VIServer -Server "vcenter.example.com" -Credential (Get-Credential)
```

### Disconnect

#### `Disconnect-CisServer`

This cmdlet closes the connection to one or more vSphere Automation SDK servers.

**Parameters**: `Server, Force`

#### `Disconnect-VIServer`

This cmdlet closes the connection to a vCenter Server system.

**Parameters**: `Server, Force`

### Get

#### `Get-PowerCLIConfiguration`

This cmdlet retrieves the VMware PowerCLI proxy configuration and default servers policy.

**Parameters**: `Scope`

#### `Get-PowerCLIVersion`

This cmdlet retrieves the versions of the installed PowerCLI snapins.

**Parameters**: None

#### `Get-VICommand`

This function retrieves all commands of the VMware modules.

**Parameters**: `Name`

#### `Get-VICredentialStoreItem`

This cmdlet retrieves the credential store items available on a vCenter Server system.

**Parameters**: `Host, User, File`

#### `Get-VIObjectByVIView`

This cmdlet converts a vSphere View object to a VIObject.

**Parameters**: `Server, MORef, VIView`

#### `Get-VIProperty`

This cmdlet retrieves extended object properties.

**Parameters**: `Name, ObjectType, DeclaredOnly`

#### `Get-View`

This cmdlet returns the vSphere View objects that correspond to the specified search criteria.

**Parameters**: `Server, VIObject, Id, SearchRoot, ViewType, Filter, Property, RelatedObject`

### New

#### `New-VICredentialStoreItem`

This cmdlet creates a new entry in the credential store.

**Parameters**: `Host, User, Password, File`

#### `New-VIProperty`

This cmdlet creates a new extension property on the specified object type.

**Parameters**: `Name, ObjectType, Value, Force, ValueFromExtensionProperty, BasedOnExtensionProperty`

### Other

#### `HookGetViewAutoCompleter`

HookGetViewAutoCompleter

**Parameters**: None

### Remove

#### `Remove-VICredentialStoreItem`

This cmdlet removes the specified credential store items.

**Parameters**: `CredentialStoreItem, Host, User, File`

#### `Remove-VIProperty`

This cmdlet removes the extended properties from the specified object types.

**Parameters**: `Name, ObjectType, VIProperty`

### Set

#### `Set-PowerCLIConfiguration`

This cmdlet modifies the VMware PowerCLI configuration.

**Parameters**: `ProxyPolicy, DefaultVIServerMode, InvalidCertificateAction, ParticipateInCeip, CEIPDataTransferProxyPolicy, DisplayDeprecationWarnings, WebOperationTimeoutSeconds, VMConsoleWindowBrowser, Scope, PythonPath`

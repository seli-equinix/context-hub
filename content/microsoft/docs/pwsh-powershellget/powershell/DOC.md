---
name: pwsh-powershellget
description: "PowerShell 7.5 PowerShellGet cmdlets — Find, Install, Publish, Update modules and scripts from PSGallery"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Find-Command,Find-DscResource,Find-Module,Find-RoleCapability,Find-Script,Get-CredsFromCredentialProvider,Get-InstalledModule,Get-InstalledScript,Get-PSRepository,Install-Module,Install-Script,New-ScriptFileInfo,Publish-Module,Publish-Script,Register-PSRepository,Save-Module,Save-Script,Set-PSRepository,Test-ScriptFileInfo,Uninstall-Module,Uninstall-Script,Unregister-PSRepository,Update-Module,Update-ModuleManifest,Update-Script,Update-ScriptFileInfo"
---

# PowerShell 7.5 — Find

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Find-Command` | Find-Command [[-Name] <string[]>] [-ModuleName <string>] [-MinimumVersion <string>] [-MaximumVers... |
| `Find-DscResource` | Find-DscResource [[-Name] <string[]>] [-ModuleName <string>] [-MinimumVersion <string>] [-Maximum... |
| `Find-Module` | Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-Required... |
| `Find-RoleCapability` | Find-RoleCapability [[-Name] <string[]>] [-ModuleName <string>] [-MinimumVersion <string>] [-Maxi... |
| `Find-Script` | Find-Script [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-Required... |
| `Get-CredsFromCredentialProvider` | Get-CredsFromCredentialProvider [[-SourceLocation] <uri>] [[-isRetry] <bool>] [<CommonParameters>] |
| `Get-InstalledModule` | Get-InstalledModule [[-Name] <string[]>] [-MinimumVersion <string>] [-RequiredVersion <string>] [... |
| `Get-InstalledScript` | Get-InstalledScript [[-Name] <string[]>] [-MinimumVersion <string>] [-RequiredVersion <string>] [... |
| `Get-PSRepository` | Get-PSRepository [[-Name] <string[]>] [<CommonParameters>] |
| `Install-Module` | Install-Module [-Name] <string[]> [-MinimumVersion <string>] [-MaximumVersion <string>] [-Require... |
| `Install-Script` | Install-Script [-Name] <string[]> [-MinimumVersion <string>] [-MaximumVersion <string>] [-Require... |
| `New-ScriptFileInfo` | New-ScriptFileInfo [[-Path] <string>] -Description <string> [-Version <string>] [-Author <string>... |
| `Publish-Module` | Publish-Module -Name <string> [-RequiredVersion <string>] [-NuGetApiKey <string>] [-Repository <s... |
| `Publish-Script` | Publish-Script -Path <string> [-NuGetApiKey <string>] [-Repository <string>] [-Credential <pscred... |
| `Register-PSRepository` | Register-PSRepository [-Name] <string> [-SourceLocation] <uri> [-PublishLocation <uri>] [-ScriptS... |
| `Save-Module` | Save-Module [-Name] <string[]> [-Path] <string> [-MinimumVersion <string>] [-MaximumVersion <stri... |
| `Save-Script` | Save-Script [-Name] <string[]> [-Path] <string> [-MinimumVersion <string>] [-MaximumVersion <stri... |
| `Set-PSRepository` | Set-PSRepository [-Name] <string> [[-SourceLocation] <uri>] [-PublishLocation <uri>] [-ScriptSour... |
| `Test-ScriptFileInfo` | Test-ScriptFileInfo [-Path] <string> [<CommonParameters>]  Test-ScriptFileInfo -LiteralPath <stri... |
| `Uninstall-Module` | Uninstall-Module [-Name] <string[]> [-MinimumVersion <string>] [-RequiredVersion <string>] [-Maxi... |
| `Uninstall-Script` | Uninstall-Script [-Name] <string[]> [-MinimumVersion <string>] [-RequiredVersion <string>] [-Maxi... |
| `Unregister-PSRepository` | Unregister-PSRepository [-Name] <string[]> [<CommonParameters>] |
| `Update-Module` | Update-Module [[-Name] <string[]>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-Crede... |
| `Update-ModuleManifest` | Update-ModuleManifest [-Path] <string> [-NestedModules <Object[]>] [-Guid <guid>] [-Author <strin... |
| `Update-Script` | Update-Script [[-Name] <string[]>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-Proxy... |
| `Update-ScriptFileInfo` | Update-ScriptFileInfo [-Path] <string> [-Version <string>] [-Author <string>] [-Guid <guid>] [-De... |

---

### Find-Command

Find-Command [[-Name] <string[]>] [-ModuleName <string>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-AllVersions] [-AllowPrerelease] [-Tag <string[]>] [-Filter <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>] [<CommonParameters>]

**Returns**: `returnValue`

```
Find-Command
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-Filter <string>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-ModuleName <string>]
    [-Name <string[]>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-Tag <string[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Filter` | `string` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-ModuleName` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Tag` | `string[]` | No |  |

---

### Find-DscResource

Find-DscResource [[-Name] <string[]>] [-ModuleName <string>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-AllVersions] [-AllowPrerelease] [-Tag <string[]>] [-Filter <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>] [<CommonParameters>]

**Returns**: `returnValue`

```
Find-DscResource
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-Filter <string>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-ModuleName <string>]
    [-Name <string[]>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-Tag <string[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Filter` | `string` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-ModuleName` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Tag` | `string[]` | No |  |

---

### Find-Module

Find-Module [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>] [-Tag <string[]>] [-Includes <string[]>] [-DscResource <string[]>] [-RoleCapability <string[]>] [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>] [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]

**Returns**: `returnValue`

```
Find-Module
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-Command <string[]>]
    [-Credential <pscredential>]
    [-DscResource <string[]>]
    [-Filter <string>]
    [-IncludeDependencies <switch>]
    [-Includes <string[]>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-Name <string[]>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-RoleCapability <string[]>]
    [-Tag <string[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Command` | `string[]` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-DscResource` | `string[]` | No |  |
| `-Filter` | `string` | No |  |
| `-IncludeDependencies` | `switch` | No |  |
| `-Includes` | `string[]` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-RoleCapability` | `string[]` | No |  |
| `-Tag` | `string[]` | No |  |

---

### Find-RoleCapability

Find-RoleCapability [[-Name] <string[]>] [-ModuleName <string>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-AllVersions] [-AllowPrerelease] [-Tag <string[]>] [-Filter <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>] [<CommonParameters>]

**Returns**: `returnValue`

```
Find-RoleCapability
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-Filter <string>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-ModuleName <string>]
    [-Name <string[]>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-Tag <string[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Filter` | `string` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-ModuleName` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Tag` | `string[]` | No |  |

---

### Find-Script

Find-Script [[-Name] <string[]>] [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-AllVersions] [-IncludeDependencies] [-Filter <string>] [-Tag <string[]>] [-Includes <string[]>] [-Command <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Repository <string[]>] [-Credential <pscredential>] [-AllowPrerelease] [<CommonParameters>]

**Returns**: `returnValue`

```
Find-Script
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-Command <string[]>]
    [-Credential <pscredential>]
    [-Filter <string>]
    [-IncludeDependencies <switch>]
    [-Includes <string[]>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-Name <string[]>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-Tag <string[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Command` | `string[]` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Filter` | `string` | No |  |
| `-IncludeDependencies` | `switch` | No |  |
| `-Includes` | `string[]` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Tag` | `string[]` | No |  |

---

### Get-CredsFromCredentialProvider

Get-CredsFromCredentialProvider [[-SourceLocation] <uri>] [[-isRetry] <bool>] [<CommonParameters>]

**Returns**: `returnValue`

```
Get-CredsFromCredentialProvider
    [-SourceLocation <uri>]
    [-isRetry <bool>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-SourceLocation` | `uri` | No |  |
| `-isRetry` | `bool` | No |  |

---

### Get-InstalledModule

Get-InstalledModule [[-Name] <string[]>] [-MinimumVersion <string>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-AllVersions] [-AllowPrerelease] [<CommonParameters>]

**Returns**: `returnValue`

```
Get-InstalledModule
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-Name <string[]>]
    [-RequiredVersion <string>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |

---

### Get-InstalledScript

Get-InstalledScript [[-Name] <string[]>] [-MinimumVersion <string>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-AllowPrerelease] [<CommonParameters>]

**Returns**: `returnValue`

```
Get-InstalledScript
    [-AllowPrerelease <switch>]
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    [-Name <string[]>]
    [-RequiredVersion <string>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowPrerelease` | `switch` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |

---

### Get-PSRepository

Get-PSRepository [[-Name] <string[]>] [<CommonParameters>]

**Returns**: `returnValue`

```
Get-PSRepository
    [-Name <string[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `string[]` | No |  |

---

### Install-Module

Install-Module [-Name] <string[]> [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-Repository <string[]>] [-Credential <pscredential>] [-Scope <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]

Install-Module [-InputObject] <psobject[]> [-Credential <pscredential>] [-Scope <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Install-Module
    [-AcceptLicense <switch>]
    [-AllowClobber <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    -InputObject <psobject[]>
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    -Name <string[]>
    [-PassThru <switch>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-Scope <string>]
    [-SkipPublisherCheck <switch>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `switch` | No |  |
| `-AllowClobber` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-InputObject` | `psobject[]` | Yes |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | Yes |  |
| `-PassThru` | `switch` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Scope` | `string` | No |  |
| `-SkipPublisherCheck` | `switch` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Install-Script

Install-Script [-Name] <string[]> [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-Repository <string[]>] [-Scope <string>] [-NoPathUpdate] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]

Install-Script [-InputObject] <psobject[]> [-Scope <string>] [-NoPathUpdate] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Install-Script
    [-AcceptLicense <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    -InputObject <psobject[]>
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    -Name <string[]>
    [-NoPathUpdate <switch>]
    [-PassThru <switch>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-Scope <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-InputObject` | `psobject[]` | Yes |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | Yes |  |
| `-NoPathUpdate` | `switch` | No |  |
| `-PassThru` | `switch` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Scope` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### New-ScriptFileInfo

New-ScriptFileInfo [[-Path] <string>] -Description <string> [-Version <string>] [-Author <string>] [-Guid <guid>] [-CompanyName <string>] [-Copyright <string>] [-RequiredModules <Object[]>] [-ExternalModuleDependencies <string[]>] [-RequiredScripts <string[]>] [-ExternalScriptDependencies <string[]>] [-Tags <string[]>] [-ProjectUri <uri>] [-LicenseUri <uri>] [-IconUri <uri>] [-ReleaseNotes <string[]>] [-PrivateData <string>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
New-ScriptFileInfo
    [-Author <string>]
    [-CompanyName <string>]
    [-Confirm <switch>]
    [-Copyright <string>]
    -Description <string>
    [-ExternalModuleDependencies <string[]>]
    [-ExternalScriptDependencies <string[]>]
    [-Force <switch>]
    [-Guid <guid>]
    [-IconUri <uri>]
    [-LicenseUri <uri>]
    [-PassThru <switch>]
    [-Path <string>]
    [-PrivateData <string>]
    [-ProjectUri <uri>]
    [-ReleaseNotes <string[]>]
    [-RequiredModules <Object[]>]
    [-RequiredScripts <string[]>]
    [-Tags <string[]>]
    [-Version <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Author` | `string` | No |  |
| `-CompanyName` | `string` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Copyright` | `string` | No |  |
| `-Description` | `string` | Yes |  |
| `-ExternalModuleDependencies` | `string[]` | No |  |
| `-ExternalScriptDependencies` | `string[]` | No |  |
| `-Force` | `switch` | No |  |
| `-Guid` | `guid` | No |  |
| `-IconUri` | `uri` | No |  |
| `-LicenseUri` | `uri` | No |  |
| `-PassThru` | `switch` | No |  |
| `-Path` | `string` | No |  |
| `-PrivateData` | `string` | No |  |
| `-ProjectUri` | `uri` | No |  |
| `-ReleaseNotes` | `string[]` | No |  |
| `-RequiredModules` | `Object[]` | No |  |
| `-RequiredScripts` | `string[]` | No |  |
| `-Tags` | `string[]` | No |  |
| `-Version` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Publish-Module

Publish-Module -Name <string> [-RequiredVersion <string>] [-NuGetApiKey <string>] [-Repository <string>] [-Credential <pscredential>] [-FormatVersion <version>] [-ReleaseNotes <string[]>] [-Tags <string[]>] [-LicenseUri <uri>] [-IconUri <uri>] [-ProjectUri <uri>] [-Exclude <string[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]

Publish-Module -Path <string> [-NuGetApiKey <string>] [-Repository <string>] [-Credential <pscredential>] [-FormatVersion <version>] [-ReleaseNotes <string[]>] [-Tags <string[]>] [-LicenseUri <uri>] [-IconUri <uri>] [-ProjectUri <uri>] [-Force] [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Publish-Module
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Exclude <string[]>]
    [-Force <switch>]
    [-FormatVersion <version>]
    [-IconUri <uri>]
    [-LicenseUri <uri>]
    -Name <string>
    [-NuGetApiKey <string>]
    -Path <string>
    [-ProjectUri <uri>]
    [-ReleaseNotes <string[]>]
    [-Repository <string>]
    [-RequiredVersion <string>]
    [-SkipAutomaticTags <switch>]
    [-Tags <string[]>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Exclude` | `string[]` | No |  |
| `-Force` | `switch` | No |  |
| `-FormatVersion` | `version` | No |  |
| `-IconUri` | `uri` | No |  |
| `-LicenseUri` | `uri` | No |  |
| `-Name` | `string` | Yes |  |
| `-NuGetApiKey` | `string` | No |  |
| `-Path` | `string` | Yes |  |
| `-ProjectUri` | `uri` | No |  |
| `-ReleaseNotes` | `string[]` | No |  |
| `-Repository` | `string` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-SkipAutomaticTags` | `switch` | No |  |
| `-Tags` | `string[]` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Publish-Script

Publish-Script -Path <string> [-NuGetApiKey <string>] [-Repository <string>] [-Credential <pscredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

Publish-Script -LiteralPath <string> [-NuGetApiKey <string>] [-Repository <string>] [-Credential <pscredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Publish-Script
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    -LiteralPath <string>
    [-NuGetApiKey <string>]
    -Path <string>
    [-Repository <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-LiteralPath` | `string` | Yes |  |
| `-NuGetApiKey` | `string` | No |  |
| `-Path` | `string` | Yes |  |
| `-Repository` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Register-PSRepository

Register-PSRepository [-Name] <string> [-SourceLocation] <uri> [-PublishLocation <uri>] [-ScriptSourceLocation <uri>] [-ScriptPublishLocation <uri>] [-Credential <pscredential>] [-InstallationPolicy <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-PackageManagementProvider <string>] [<CommonParameters>]

Register-PSRepository -Default [-InstallationPolicy <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [<CommonParameters>]

**Returns**: `returnValue`

```
Register-PSRepository
    [-Credential <pscredential>]
    -Default <switch>
    [-InstallationPolicy <string>]
    -Name <string>
    [-PackageManagementProvider <string>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-PublishLocation <uri>]
    [-ScriptPublishLocation <uri>]
    [-ScriptSourceLocation <uri>]
    -SourceLocation <uri>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `pscredential` | No |  |
| `-Default` | `switch` | Yes |  |
| `-InstallationPolicy` | `string` | No |  |
| `-Name` | `string` | Yes |  |
| `-PackageManagementProvider` | `string` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-PublishLocation` | `uri` | No |  |
| `-ScriptPublishLocation` | `uri` | No |  |
| `-ScriptSourceLocation` | `uri` | No |  |
| `-SourceLocation` | `uri` | Yes |  |

---

### Save-Module

Save-Module [-Name] <string[]> [-Path] <string> [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-Repository <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

Save-Module [-Name] <string[]> -LiteralPath <string> [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-Repository <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

Save-Module [-InputObject] <psobject[]> -LiteralPath <string> [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

Save-Module [-InputObject] <psobject[]> [-Path] <string> [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Save-Module
    [-AcceptLicense <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    -InputObject <psobject[]>
    -LiteralPath <string>
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    -Name <string[]>
    -Path <string>
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-InputObject` | `psobject[]` | Yes |  |
| `-LiteralPath` | `string` | Yes |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | Yes |  |
| `-Path` | `string` | Yes |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Save-Script

Save-Script [-Name] <string[]> [-Path] <string> [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-Repository <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

Save-Script [-Name] <string[]> -LiteralPath <string> [-MinimumVersion <string>] [-MaximumVersion <string>] [-RequiredVersion <string>] [-Repository <string[]>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

Save-Script [-InputObject] <psobject[]> -LiteralPath <string> [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

Save-Script [-InputObject] <psobject[]> [-Path] <string> [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Save-Script
    [-AcceptLicense <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    -InputObject <psobject[]>
    -LiteralPath <string>
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    -Name <string[]>
    -Path <string>
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-Repository <string[]>]
    [-RequiredVersion <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-InputObject` | `psobject[]` | Yes |  |
| `-LiteralPath` | `string` | Yes |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | Yes |  |
| `-Path` | `string` | Yes |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-Repository` | `string[]` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Set-PSRepository

Set-PSRepository [-Name] <string> [[-SourceLocation] <uri>] [-PublishLocation <uri>] [-ScriptSourceLocation <uri>] [-ScriptPublishLocation <uri>] [-Credential <pscredential>] [-InstallationPolicy <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-PackageManagementProvider <string>] [<CommonParameters>]

**Returns**: `returnValue`

```
Set-PSRepository
    [-Credential <pscredential>]
    [-InstallationPolicy <string>]
    -Name <string>
    [-PackageManagementProvider <string>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-PublishLocation <uri>]
    [-ScriptPublishLocation <uri>]
    [-ScriptSourceLocation <uri>]
    [-SourceLocation <uri>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `pscredential` | No |  |
| `-InstallationPolicy` | `string` | No |  |
| `-Name` | `string` | Yes |  |
| `-PackageManagementProvider` | `string` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-PublishLocation` | `uri` | No |  |
| `-ScriptPublishLocation` | `uri` | No |  |
| `-ScriptSourceLocation` | `uri` | No |  |
| `-SourceLocation` | `uri` | No |  |

---

### Test-ScriptFileInfo

Test-ScriptFileInfo [-Path] <string> [<CommonParameters>]

Test-ScriptFileInfo -LiteralPath <string> [<CommonParameters>]

**Returns**: `returnValue`

```
Test-ScriptFileInfo
    -LiteralPath <string>
    -Path <string>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-LiteralPath` | `string` | Yes |  |
| `-Path` | `string` | Yes |  |

---

### Uninstall-Module

Uninstall-Module [-Name] <string[]> [-MinimumVersion <string>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-AllVersions] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]

Uninstall-Module [-InputObject] <psobject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Uninstall-Module
    [-AllVersions <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Force <switch>]
    -InputObject <psobject[]>
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    -Name <string[]>
    [-RequiredVersion <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Force` | `switch` | No |  |
| `-InputObject` | `psobject[]` | Yes |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | Yes |  |
| `-RequiredVersion` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Uninstall-Script

Uninstall-Script [-Name] <string[]> [-MinimumVersion <string>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-Force] [-AllowPrerelease] [-WhatIf] [-Confirm] [<CommonParameters>]

Uninstall-Script [-InputObject] <psobject[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Uninstall-Script
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Force <switch>]
    -InputObject <psobject[]>
    [-MaximumVersion <string>]
    [-MinimumVersion <string>]
    -Name <string[]>
    [-RequiredVersion <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Force` | `switch` | No |  |
| `-InputObject` | `psobject[]` | Yes |  |
| `-MaximumVersion` | `string` | No |  |
| `-MinimumVersion` | `string` | No |  |
| `-Name` | `string[]` | Yes |  |
| `-RequiredVersion` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Unregister-PSRepository

Unregister-PSRepository [-Name] <string[]> [<CommonParameters>]

**Returns**: `returnValue`

```
Unregister-PSRepository
    -Name <string[]>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `string[]` | Yes |  |

---

### Update-Module

Update-Module [[-Name] <string[]>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-Credential <pscredential>] [-Scope <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Update-Module
    [-AcceptLicense <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    [-MaximumVersion <string>]
    [-Name <string[]>]
    [-PassThru <switch>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-RequiredVersion <string>]
    [-Scope <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-PassThru` | `switch` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-Scope` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Update-ModuleManifest

Update-ModuleManifest [-Path] <string> [-NestedModules <Object[]>] [-Guid <guid>] [-Author <string>] [-CompanyName <string>] [-Copyright <string>] [-RootModule <string>] [-ModuleVersion <version>] [-Description <string>] [-ProcessorArchitecture <ProcessorArchitecture>] [-CompatiblePSEditions <string[]>] [-PowerShellVersion <version>] [-ClrVersion <version>] [-DotNetFrameworkVersion <version>] [-PowerShellHostName <string>] [-PowerShellHostVersion <version>] [-RequiredModules <Object[]>] [-TypesToProcess <string[]>] [-FormatsToProcess <string[]>] [-ScriptsToProcess <string[]>] [-RequiredAssemblies <string[]>] [-FileList <string[]>] [-ModuleList <Object[]>] [-FunctionsToExport <string[]>] [-AliasesToExport <string[]>] [-VariablesToExport <string[]>] [-CmdletsToExport <string[]>] [-DscResourcesToExport <string[]>] [-PrivateData <hashtable>] [-Tags <string[]>] [-ProjectUri <uri>] [-LicenseUri <uri>] [-IconUri <uri>] [-ReleaseNotes <string[]>] [-Prerelease <string>] [-HelpInfoUri <uri>] [-PassThru] [-DefaultCommandPrefix <string>] [-ExternalModuleDependencies <string[]>] [-PackageManagementProviders <string[]>] [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Update-ModuleManifest
    [-AliasesToExport <string[]>]
    [-Author <string>]
    [-ClrVersion <version>]
    [-CmdletsToExport <string[]>]
    [-CompanyName <string>]
    [-CompatiblePSEditions <string[]>]
    [-Confirm <switch>]
    [-Copyright <string>]
    [-DefaultCommandPrefix <string>]
    [-Description <string>]
    [-DotNetFrameworkVersion <version>]
    [-DscResourcesToExport <string[]>]
    [-ExternalModuleDependencies <string[]>]
    [-FileList <string[]>]
    [-FormatsToProcess <string[]>]
    [-FunctionsToExport <string[]>]
    [-Guid <guid>]
    [-HelpInfoUri <uri>]
    [-IconUri <uri>]
    [-LicenseUri <uri>]
    [-ModuleList <Object[]>]
    [-ModuleVersion <version>]
    [-NestedModules <Object[]>]
    [-PackageManagementProviders <string[]>]
    [-PassThru <switch>]
    -Path <string>
    [-PowerShellHostName <string>]
    [-PowerShellHostVersion <version>]
    [-PowerShellVersion <version>]
    [-Prerelease <string>]
    [-PrivateData <hashtable>]
    [-ProcessorArchitecture <ProcessorArchitecture>]
    [-ProjectUri <uri>]
    [-ReleaseNotes <string[]>]
    [-RequireLicenseAcceptance <switch>]
    [-RequiredAssemblies <string[]>]
    [-RequiredModules <Object[]>]
    [-RootModule <string>]
    [-ScriptsToProcess <string[]>]
    [-Tags <string[]>]
    [-TypesToProcess <string[]>]
    [-VariablesToExport <string[]>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AliasesToExport` | `string[]` | No |  |
| `-Author` | `string` | No |  |
| `-ClrVersion` | `version` | No |  |
| `-CmdletsToExport` | `string[]` | No |  |
| `-CompanyName` | `string` | No |  |
| `-CompatiblePSEditions` | `string[]` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Copyright` | `string` | No |  |
| `-DefaultCommandPrefix` | `string` | No |  |
| `-Description` | `string` | No |  |
| `-DotNetFrameworkVersion` | `version` | No |  |
| `-DscResourcesToExport` | `string[]` | No |  |
| `-ExternalModuleDependencies` | `string[]` | No |  |
| `-FileList` | `string[]` | No |  |
| `-FormatsToProcess` | `string[]` | No |  |
| `-FunctionsToExport` | `string[]` | No |  |
| `-Guid` | `guid` | No |  |
| `-HelpInfoUri` | `uri` | No |  |
| `-IconUri` | `uri` | No |  |
| `-LicenseUri` | `uri` | No |  |
| `-ModuleList` | `Object[]` | No |  |
| `-ModuleVersion` | `version` | No |  |
| `-NestedModules` | `Object[]` | No |  |
| `-PackageManagementProviders` | `string[]` | No |  |
| `-PassThru` | `switch` | No |  |
| `-Path` | `string` | Yes |  |
| `-PowerShellHostName` | `string` | No |  |
| `-PowerShellHostVersion` | `version` | No |  |
| `-PowerShellVersion` | `version` | No |  |
| `-Prerelease` | `string` | No |  |
| `-PrivateData` | `hashtable` | No |  |
| `-ProcessorArchitecture` | `ProcessorArchitecture` | No |  |
| `-ProjectUri` | `uri` | No |  |
| `-ReleaseNotes` | `string[]` | No |  |
| `-RequireLicenseAcceptance` | `switch` | No |  |
| `-RequiredAssemblies` | `string[]` | No |  |
| `-RequiredModules` | `Object[]` | No |  |
| `-RootModule` | `string` | No |  |
| `-ScriptsToProcess` | `string[]` | No |  |
| `-Tags` | `string[]` | No |  |
| `-TypesToProcess` | `string[]` | No |  |
| `-VariablesToExport` | `string[]` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Update-Script

Update-Script [[-Name] <string[]>] [-RequiredVersion <string>] [-MaximumVersion <string>] [-Proxy <uri>] [-ProxyCredential <pscredential>] [-Credential <pscredential>] [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Update-Script
    [-AcceptLicense <switch>]
    [-AllowPrerelease <switch>]
    [-Confirm <switch>]
    [-Credential <pscredential>]
    [-Force <switch>]
    [-MaximumVersion <string>]
    [-Name <string[]>]
    [-PassThru <switch>]
    [-Proxy <uri>]
    [-ProxyCredential <pscredential>]
    [-RequiredVersion <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `switch` | No |  |
| `-AllowPrerelease` | `switch` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Credential` | `pscredential` | No |  |
| `-Force` | `switch` | No |  |
| `-MaximumVersion` | `string` | No |  |
| `-Name` | `string[]` | No |  |
| `-PassThru` | `switch` | No |  |
| `-Proxy` | `uri` | No |  |
| `-ProxyCredential` | `pscredential` | No |  |
| `-RequiredVersion` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

### Update-ScriptFileInfo

Update-ScriptFileInfo [-Path] <string> [-Version <string>] [-Author <string>] [-Guid <guid>] [-Description <string>] [-CompanyName <string>] [-Copyright <string>] [-RequiredModules <Object[]>] [-ExternalModuleDependencies <string[]>] [-RequiredScripts <string[]>] [-ExternalScriptDependencies <string[]>] [-Tags <string[]>] [-ProjectUri <uri>] [-LicenseUri <uri>] [-IconUri <uri>] [-ReleaseNotes <string[]>] [-PrivateData <string>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

Update-ScriptFileInfo [-LiteralPath] <string> [-Version <string>] [-Author <string>] [-Guid <guid>] [-Description <string>] [-CompanyName <string>] [-Copyright <string>] [-RequiredModules <Object[]>] [-ExternalModuleDependencies <string[]>] [-RequiredScripts <string[]>] [-ExternalScriptDependencies <string[]>] [-Tags <string[]>] [-ProjectUri <uri>] [-LicenseUri <uri>] [-IconUri <uri>] [-ReleaseNotes <string[]>] [-PrivateData <string>] [-PassThru] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

**Returns**: `returnValue`

```
Update-ScriptFileInfo
    [-Author <string>]
    [-CompanyName <string>]
    [-Confirm <switch>]
    [-Copyright <string>]
    [-Description <string>]
    [-ExternalModuleDependencies <string[]>]
    [-ExternalScriptDependencies <string[]>]
    [-Force <switch>]
    [-Guid <guid>]
    [-IconUri <uri>]
    [-LicenseUri <uri>]
    -LiteralPath <string>
    [-PassThru <switch>]
    -Path <string>
    [-PrivateData <string>]
    [-ProjectUri <uri>]
    [-ReleaseNotes <string[]>]
    [-RequiredModules <Object[]>]
    [-RequiredScripts <string[]>]
    [-Tags <string[]>]
    [-Version <string>]
    [-WhatIf <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Author` | `string` | No |  |
| `-CompanyName` | `string` | No |  |
| `-Confirm` | `switch` | No |  |
| `-Copyright` | `string` | No |  |
| `-Description` | `string` | No |  |
| `-ExternalModuleDependencies` | `string[]` | No |  |
| `-ExternalScriptDependencies` | `string[]` | No |  |
| `-Force` | `switch` | No |  |
| `-Guid` | `guid` | No |  |
| `-IconUri` | `uri` | No |  |
| `-LicenseUri` | `uri` | No |  |
| `-LiteralPath` | `string` | Yes |  |
| `-PassThru` | `switch` | No |  |
| `-Path` | `string` | Yes |  |
| `-PrivateData` | `string` | No |  |
| `-ProjectUri` | `uri` | No |  |
| `-ReleaseNotes` | `string[]` | No |  |
| `-RequiredModules` | `Object[]` | No |  |
| `-RequiredScripts` | `string[]` | No |  |
| `-Tags` | `string[]` | No |  |
| `-Version` | `string` | No |  |
| `-WhatIf` | `switch` | No |  |

---

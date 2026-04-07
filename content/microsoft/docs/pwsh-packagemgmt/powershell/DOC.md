---
name: pwsh-packagemgmt
description: "PowerShell 7.5 PackageManagement cmdlets — Find, Install, Get, Uninstall packages across providers (NuGet, Chocolatey, etc.)"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Find-Package,Find-PackageProvider,Get-Package,Get-PackageProvider,Get-PackageSource,Import-PackageProvider,Install-Package,Install-PackageProvider,Register-PackageSource,Save-Package,Set-PackageSource,Uninstall-Package,Unregister-PackageSource"
---

# PowerShell 7.5 — Find

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Find-Package` | Finds software packages in available package sources. |
| `Find-PackageProvider` | Returns a list of Package Management package providers available for installation. |
| `Get-Package` | Returns a list of all software packages that were installed with PackageManagement . |
| `Get-PackageProvider` | Returns a list of package providers that are connected to Package Management. |
| `Get-PackageSource` | Gets a list of package sources that are registered for a package provider. |
| `Import-PackageProvider` | Adds Package Management package providers to the current session. |
| `Install-Package` | Installs one or more software packages. |
| `Install-PackageProvider` | Installs one or more Package Management package providers. |
| `Register-PackageSource` | Adds a package source for a specified package provider. |
| `Save-Package` | Saves packages to the local computer without installing them. |
| `Set-PackageSource` | Replaces a package source for a specified package provider. |
| `Uninstall-Package` | Uninstalls one or more software packages. |
| `Unregister-PackageSource` | Removes a registered package source. |

---

### Find-Package

Finds software packages in available package sources.

`Find-Package` finds software packages that are available in package sources. `Get-PackageProvider` and `Get-PackageSource` display details about your providers. !INCLUDE [nuget-module (../../includes/nuget-module.md)]

**Returns**: `SoftwareIdentify[]`

```
Find-Package
    [-AcceptLicense <System.Management.Automation.SwitchParameter>]
    [-AllowPrereleaseVersions <System.Management.Automation.SwitchParameter>]
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Command <System.String[]>]
    [-ConfigFile <System.String>]
    [-Contains <System.String>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-DscResource <System.String[]>]
    [-Filter <System.String>]
    [-FilterOnTag <System.String[]>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-Headers <System.String[]>]
    [-IncludeDependencies <System.Management.Automation.SwitchParameter>]
    [-Includes <System.String[]>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    [-Name <System.String[]>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String[]>]
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-PublishLocation <System.String>]
    [-RequiredVersion <System.String>]
    [-RoleCapability <System.String[]>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
    [-Source <System.String[]>]
    [-Tag <System.String[]>]
    [-Type <System.String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `System.Management.Automation.SwitchParameter` | No | Automatically accepts a license agreement if the package requires it. |
| `-AllowPrereleaseVersions` | `System.Management.Automation.SwitchParameter` | No | Includes packages marked as a prerelease in the results. |
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Find-Package` returns all available versions of the package. By default, `Find-Package` only returns the newest available version. |
| `-Command` | `System.String[]` | No | Specifies an array of commands searched by `Find-Package`. |
| `-ConfigFile` | `System.String` | No | Specifies a configuration file. |
| `-Contains` | `System.String` | No | `Find-Package` gets objects if any item in the object's property values are an exact match for the specified value. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to search for packages. |
| `-DscResource` | `System.String[]` | No | Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches. |
| `-Filter` | `System.String` | No | Specifies terms to search for within the Name and Description properties. |
| `-FilterOnTag` | `System.String[]` | No | Specifies the tag that filters the results. Results that don't contain the specified tag are excluded. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Find-Package` forces PackageManagement to automatically install the package provider. |
| `-Headers` | `System.String[]` | No | Specifies the headers for the package. |
| `-IncludeDependencies` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet includes package dependencies in the results. |
| `-Includes` | `System.String[]` | No | Specifies whether `Find-Package` should find all packages within a category.   The accepted values are as follows:   - Cmdlet   - DscResource   - Function   - RoleCapability   - Workflow |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum package version that you want to find. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum package version that you want to find. If a higher version is available, that version is returned. |
| `-Name` | `System.String[]` | No | Specifies one or more package names, or package names with wildcard characters. Separate multiple package names with commas. |
| `-PackageManagementProvider` | `System.String` | No | Specifies the name of a package management provider. |
| `-ProviderName` | `System.String[]` | No | Specifies one or more package provider names. Separate multiple package provider names with commas. Use `Get-PackageProvider` to get a list of available package providers. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than a direct connection to the internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server that is specified by the Proxy parameter. |
| `-PublishLocation` | `System.String` | No | Specifies a location for publishing the package. |
| `-RequiredVersion` | `System.String` | No | Specifies an exact package version that you want to find. |
| `-RoleCapability` | `System.String[]` | No | Specifies an array of role capabilities. |
| `-ScriptPublishLocation` | `System.String` | No | Specifies a script publishing location for the package. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies a script source location. |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips package credential validation. |
| `-Source` | `System.String[]` | No | Specifies one or more package sources. Use `Get-PackageSource` to get a list of available package sources. A file system directory can be used as a source for download packages. |
| `-Tag` | `System.String[]` | No | Specifies one or more strings to search for in the package metadata. |
| `-Type` | `System.String` | No | Specifies whether to search for packages with a module, a script, or either. |

---

### Find-PackageProvider

Returns a list of Package Management package providers available for installation.

The `Find-PackageProvider` cmdlet finds matching PackageManagement providers that are available in package sources registered with PowerShellGet. These are package providers available for installation with the Install-PackageProvider cmdlet. By default, this includes modules available in the PowerShell Gallery with the PackageManagement and Provider tags.

**Returns**: `Microsoft.PackageManagement.Packaging.SoftwareIdentity`

```
Find-PackageProvider
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-IncludeDependencies <System.Management.Automation.SwitchParameter>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    [-Name <System.String[]>]
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-RequiredVersion <System.String>]
    [-Source <System.String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet returns all available versions of the package provider. By default, `Find-PackageProvider` only returns the newest available version. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to search for package providers. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. Currently, this is equivalent to the ForceBootstrap parameter. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet forces Package Management to automatically install the package provider. |
| `-IncludeDependencies` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet includes dependencies. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum allowed version of the package provider that you want to find. If you do not add this parameter, `Find-PackageProvider` finds the highest available version of the provider. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum allowed version of the package provider that you want to find. If you do not add this parameter, `Find-PackageProvider` finds the highest available version of the package that... |
| `-Name` | `System.String[]` | No | Specifies one or more package provider module names, or provider names with wildcard characters. Separate multiple package names with commas. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than connecting directly to the Internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server that is specified by the Proxy parameter. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact allowed version of the package provider that you want to find. If you do not add this parameter, `Find-PackageProvider` finds the highest available version of the provider that ... |
| `-Source` | `System.String[]` | No | Specifies one or more package sources. You can get a list of available package sources by using the `Get-PackageSource` cmdlet. |

---

### Get-Package

Returns a list of all software packages that were installed with PackageManagement .

The `Get-Package` cmdlet returns a list of all software packages on the local computer that were installed with PackageManagement . You can run `Get-Package` on remote computers by running it as part of an `Invoke-Command` or `Enter-PSSession` command or script. !INCLUDE [nuget-module (../../includes/nuget-module.md)]

**Returns**: `Microsoft.PackageManagement.Packaging.SoftwareIdentity`

```
Get-Package
    [-AllowClobber <System.Management.Automation.SwitchParameter>]
    [-AllowPrereleaseVersions <System.Management.Automation.SwitchParameter>]
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Destination <System.String>]
    [-ExcludeVersion <System.Management.Automation.SwitchParameter>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-InstallUpdate <System.Management.Automation.SwitchParameter>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    [-Name <System.String[]>]
    [-NoPathUpdate <System.Management.Automation.SwitchParameter>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String[]>]
    [-RequiredVersion <System.String>]
    [-Scope <System.String>]
    [-SkipDependencies <System.Management.Automation.SwitchParameter>]
    [-SkipPublisherCheck <System.Management.Automation.SwitchParameter>]
    [-Type <System.String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowClobber` | `System.Management.Automation.SwitchParameter` | No | Overrides warning messages about conflicts with existing commands. Overwrites existing commands that have the same name as commands being installed by a module. |
| `-AllowPrereleaseVersions` | `System.Management.Automation.SwitchParameter` | No | Includes packages marked as a prerelease in the results. |
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Get-Package` returns all available versions of the package. By default, `Get-Package` only returns the newest available version. |
| `-Destination` | `System.String` | No | Specifies the path to a directory that contains extracted package files. |
| `-ExcludeVersion` | `System.Management.Automation.SwitchParameter` | No | Switch to exclude the version number in the folder path. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Get-Package` forces PackageManagement to automatically install the package provider. |
| `-InstallUpdate` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet installs updates. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum package version that you want to find. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum package version that you want to find. If a higher version is available, that version is returned. |
| `-Name` | `System.String[]` | No | Specifies one or more package names, or package names with wildcard characters. Separate multiple package names with commas. |
| `-NoPathUpdate` | `System.Management.Automation.SwitchParameter` | No | NoPathUpdate only applies to the `Install-Script` cmdlet. NoPathUpdate is a dynamic parameter added by the provider and isn't supported by `Get-Package`. |
| `-PackageManagementProvider` | `System.String` | No | Specifies the name of a package management provider. |
| `-ProviderName` | `System.String[]` | No | Specifies one or more package provider names. Separate multiple package provider names with commas. Use `Get-PackageProvider` to get a list of available package providers. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact version of the package to find. |
| `-Scope` | `System.String` | No | Specifies the search scope for the package. |
| `-SkipDependencies` | `System.Management.Automation.SwitchParameter` | No | Switch that specifies to skip finding any package dependencies. |
| `-SkipPublisherCheck` | `System.Management.Automation.SwitchParameter` | No | Allows you to get a package version that is newer than your installed version. For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally si... |
| `-Type` | `System.String` | No | Specifies whether to search for packages with a module, a script, or either. |

---

### Get-PackageProvider

Returns a list of package providers that are connected to Package Management.

The `Get-PackageProvider` cmdlet returns a list of package providers that are connected to Package Management. Examples of these providers include PSModule, NuGet, and Chocolatey. You can filter the results based on all or part of one or more provider names.

**Returns**: `Microsoft.PackageManagement.Implementation.PackageProvider`

```
Get-PackageProvider
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-ListAvailable <System.Management.Automation.SwitchParameter>]
    [-Name <System.String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet forces all other actions with this cmdlet that can be forced. In `Get-PackageProvider`, this means the Force parameter acts the same as the ForceBootstrap parameter. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet forces Package Management to automatically install the package provider. |
| `-ListAvailable` | `System.Management.Automation.SwitchParameter` | No | Gets all installed providers. `Get-PackageProvider` gets provider in paths listed in the PSModulePath environment variable as well as the package provider assembly folders:   - `$env:ProgramFiles\P... |
| `-Name` | `System.String[]` | No | Specifies one or more provider names, or partial provider names. Separate multiple provider names with commas. Valid values for this parameter include names of providers that you have installed wit... |

---

### Get-PackageSource

Gets a list of package sources that are registered for a package provider.

The `Get-PackageSource` cmdlet gets a list of package sources that are registered with PackageManagement on the local computer. If you specify a package provider, `Get-PackageSource` gets only those sources that are associated with the specified provider. Otherwise, the command returns all package sources that are registered with PackageManagement .

**Returns**: `Microsoft.PackageManagement.Packaging.PackageSource`

```
Get-PackageSource
    [-ConfigFile <System.String>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-Location <System.String>]
    [-Name <System.String>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String[]>]
    [-PublishLocation <System.String>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ConfigFile` | `System.String` | No | Specifies a configuration file. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet forces PackageManagement to automatically install a package provider. |
| `-Location` | `System.String` | No | Specifies the location of a package management source or repository. |
| `-Name` | `System.String` | No | Specifies the name of a package management source. |
| `-PackageManagementProvider` | `System.String` | No | Specifies a package management provider. |
| `-ProviderName` | `System.String[]` | No | Specifies one or more package provider names. Separate multiple package provider names with commas. Use `Get-PackageProvider` to get a list of available package providers. |
| `-PublishLocation` | `System.String` | No | Specifies the publish location for the package source. |
| `-ScriptPublishLocation` | `System.String` | No | Specifies the script publish location. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies the script source location. |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips validating the credentials of a package source. |

---

### Import-PackageProvider

Adds Package Management package providers to the current session.

The `Import-PackageProvider` cmdlet adds one or more package providers to the current session. The provider that you import must be installed on the local computer.

**Returns**: `None documented`

```
Import-PackageProvider
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    -Name <System.String[]>
    [-RequiredVersion <System.String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. Re-imports a package provider. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet forces Package Management to automatically install the package provider. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum allowed version of the package provider that you want to import. If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum allowed version of the package provider that you want to import. If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the packag... |
| `-Name` | `System.String[]` | Yes | Specifies one or more package provider names. Wildcards are not permitted. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact version of the package provider that you want to import. If you do not add this parameter, `Import-PackageProvider` imports the highest available version of the provider that al... |

---

### Install-Package

Installs one or more software packages.

The `Install-Package` cmdlet installs one or more software packages on the local computer. If you have multiple software sources, use `Get-PackageProvider` and `Get-PackageSource` to display details about your providers. !INCLUDE [nuget-module (../../includes/nuget-module.md)]

**Returns**: `Microsoft.PackageManagement.Packaging.SoftwareIdentity`

```
Install-Package
    [-AcceptLicense <System.Management.Automation.SwitchParameter>]
    [-AllowClobber <System.Management.Automation.SwitchParameter>]
    [-AllowPrereleaseVersions <System.Management.Automation.SwitchParameter>]
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Command <System.String[]>]
    [-ConfigFile <System.String>]
    [-Contains <System.String>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-Destination <System.String>]
    [-DscResource <System.String[]>]
    [-ExcludeVersion <System.Management.Automation.SwitchParameter>]
    [-Filter <System.String>]
    [-FilterOnTag <System.String[]>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-Headers <System.String[]>]
    [-Includes <System.String[]>]
    -InputObject <Microsoft.PackageManagement.Packaging.SoftwareIdentity[]>
    [-InstallUpdate <System.Management.Automation.SwitchParameter>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    -Name <System.String[]>
    [-NoPathUpdate <System.Management.Automation.SwitchParameter>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String[]>]
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-PublishLocation <System.String>]
    [-RequiredVersion <System.String>]
    [-RoleCapability <System.String[]>]
    [-Scope <System.String>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipDependencies <System.Management.Automation.SwitchParameter>]
    [-SkipPublisherCheck <System.Management.Automation.SwitchParameter>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
    [-Source <System.String[]>]
    [-Tag <System.String[]>]
    [-Type <System.String>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `System.Management.Automation.SwitchParameter` | No | AcceptLicense automatically accepts the license agreement during installation. |
| `-AllowClobber` | `System.Management.Automation.SwitchParameter` | No | Overrides warning messages about conflicts with existing commands. Overwrites existing commands that have the same name as commands being installed. |
| `-AllowPrereleaseVersions` | `System.Management.Automation.SwitchParameter` | No | Allows the installation of packages marked as prerelease. |
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | `Install-Package` installs all available versions of the package. By default, only the newest version is installed. |
| `-Command` | `System.String[]` | No | Specifies one or more commands that `Install-Package` searches. |
| `-ConfigFile` | `System.String` | No | Specifies a path that contains a configuration file. |
| `-Contains` | `System.String` | No | `Install-Package` gets objects if the Contains parameter specifies a value that matches any of the object's property values. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to access the computer and run commands. Type a user name, such as User01 , Domain01\User01 , or enter a PSCredential object, generated by the `Get-Cred... |
| `-Destination` | `System.String` | No | Specifies a path to an input object. |
| `-DscResource` | `System.String[]` | No | Specifies one or more Desired State Configuration (DSC) resources that are searched by `Install-Package`. Use the `Find-DscResource` cmdlet to find DSC resources. |
| `-ExcludeVersion` | `System.Management.Automation.SwitchParameter` | No | Switch to exclude the version number in the folder path. |
| `-Filter` | `System.String` | No | Specifies terms to search for within the Name and Description properties. |
| `-FilterOnTag` | `System.String[]` | No | Specifies a tag that filters results and excludes results that don't contain the specified tag. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. Overrides restrictions that prevent `Install-Package` from succeeding, with the exception of security. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Forces PackageManagement to automatically install the package provider for the specified package. |
| `-Headers` | `System.String[]` | No | Specifies the package headers. |
| `-Includes` | `System.String[]` | No | Specifies whether `Install-Package` should find all package types. The acceptable values for this parameter are as follows:   - Cmdlet   - DscResource   - Function   - RoleCapability   - Workflow |
| `-InputObject` | `Microsoft.PackageManagement.Packaging.SoftwareIdentity[]` | Yes | Accepts pipeline input. Specifies a package by using the package's SoftwareIdentity type. `Find-Package` outputs a SoftwareIdentity object. |
| `-InstallUpdate` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Install-Package` installs updates. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum allowed package version that you want to install. If you don't specify this parameter, `Install-Package` installs the package's newest version. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum allowed package version that you want to install. If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version specified... |
| `-Name` | `System.String[]` | Yes | Specifies one or more package names. Multiple package names must be separated by commas. |
| `-NoPathUpdate` | `System.Management.Automation.SwitchParameter` | No | NoPathUpdate only applies to the `Install-Script` cmdlet. NoPathUpdate is a dynamic parameter added by the provider and isn't supported by `Install-Package`. |
| `-PackageManagementProvider` | `System.String` | No | Specifies the name of the PackageManagement provider. |
| `-ProviderName` | `System.String[]` | No | Specifies one or more package provider names to which to scope your package search. You can get package provider names by running the `Get-PackageProvider` cmdlet. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than connecting directly to an internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server specified by the Proxy parameter. |
| `-PublishLocation` | `System.String` | No | Specifies the path to a package's published location. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact allowed version of the package that you want to install. If you don't add this parameter, `Install-Package` installs the package's newest version that satisfies any version spec... |
| `-RoleCapability` | `System.String[]` | No | Specifies an array of role capabilities. |
| `-Scope` | `System.String` | No | Specifies the scope for which to install the package. The acceptable values for this parameter are as follows:   - CurrentUser   - AllUsers |
| `-ScriptPublishLocation` | `System.String` | No | Specifies the path to a script's published location. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies the script source location. |
| `-SkipDependencies` | `System.Management.Automation.SwitchParameter` | No | Skips the installation of software dependencies. |
| `-SkipPublisherCheck` | `System.Management.Automation.SwitchParameter` | No | Allows you to get a package version that is newer than your installed version. For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally si... |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips validating the credentials of a package. |
| `-Source` | `System.String[]` | No | Specifies one or more package sources. Multiple package source names must be separated by commas. You can get package source names by running the `Get-PackageSource` cmdlet. |
| `-Tag` | `System.String[]` | No | Specifies one or more strings to search for in the package metadata. |
| `-Type` | `System.String` | No | Specifies whether to search for packages with a module, a script, or both. The acceptable values for this parameter are as follows:   - Module   - Script   - All |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if `Install-Package` cmdlet is run. The cmdlet is not run. |

---

### Install-PackageProvider

Installs one or more Package Management package providers.

The `Install-PackageProvider` cmdlet installs matching Package Management providers that are available in package sources registered with PowerShellGet . By default, this includes modules available in the Windows PowerShell Gallery with the PackageManagement tag. The PowerShellGet Package Management provider is used for finding providers in these repositories.

**Returns**: `None documented`

```
Install-PackageProvider
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    -InputObject <Microsoft.PackageManagement.Packaging.SoftwareIdentity[]>
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    -Name <System.String[]>
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-RequiredVersion <System.String>]
    [-Scope <System.String>]
    [-Source <System.String[]>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet installs all available versions of the package provider. By default, `Install-PackageProvider` only returns the highest available version. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to install package providers. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet forces all actions with this cmdlet that can be forced. Currently, this means the Force parameter acts the same as the ForceBootstrap parameter. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet automatically installs the package provider. |
| `-InputObject` | `Microsoft.PackageManagement.Packaging.SoftwareIdentity[]` | Yes | Specifies a SoftwareIdentity object. Use the `Find-PackageProvider` cmdlet to obtain a SoftwareIdentity object to pipe into `Install-PackageProvider`. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum allowed version of the package provider that you want to install. If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the pro... |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum allowed version of the package provider that you want to install. If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the pac... |
| `-Name` | `System.String[]` | Yes | Specifies one or more package provider module names. Separate multiple package names with commas. Wildcard characters are not supported. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than connecting directly to the Internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server that is specified by the Proxy parameter. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact allowed version of the package provider that you want to install. If you do not add this parameter, `Install-PackageProvider` installs the highest available version of the provi... |
| `-Scope` | `System.String` | No | Specifies the installation scope of the provider. The acceptable values for this parameter are:   - AllUsers - installs providers in a location that is accessible to all users of the computer.   By... |
| `-Source` | `System.String[]` | No | Specifies one or more package sources. Use the `Get-PackageSource` cmdlet to get a list of available package sources. |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Register-PackageSource

Adds a package source for a specified package provider.

The `Register-PackageSource` cmdlet adds a package source for a specified package provider. Package sources are always managed by a package provider. If the package provider cannot add or replace a package source, the provider generates an error message.

**Returns**: `None documented`

```
Register-PackageSource
    [-ConfigFile <System.String>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-Location <System.String>]
    [-Name <System.String>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String>]
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-PublishLocation <System.String>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
    [-Trusted <System.Management.Automation.SwitchParameter>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ConfigFile` | `System.String` | No | Specifies a configuration file. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to access the authenticated location. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet automatically installs the package provider. |
| `-Location` | `System.String` | No | Specifies the package source location. |
| `-Name` | `System.String` | No | Specifies the name of the package source to register. |
| `-PackageManagementProvider` | `System.String` | No | Specifies the Package Management provider. |
| `-ProviderName` | `System.String` | No | Specifies the package provider's name. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than a direct connection to the internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server that is specified by the Proxy parameter. |
| `-PublishLocation` | `System.String` | No | Specifies the publish location. |
| `-ScriptPublishLocation` | `System.String` | No | Specifies the script publish location. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies the script source location. |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips validating the credentials of a package source. |
| `-Trusted` | `System.Management.Automation.SwitchParameter` | No | Indicates that the package source is trusted. |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Save-Package

Saves packages to the local computer without installing them.

The `Save-Package` cmdlet saves packages to the local computer but doesn't install the packages. This cmdlet saves the newest version of a package unless you specify a RequiredVerion . The Path and LiteralPath parameters are mutually exclusive, and cannot be added to the same command.

**Returns**: `None`

```
Save-Package
    [-AcceptLicense <System.Management.Automation.SwitchParameter>]
    [-AllowPrereleaseVersions <System.Management.Automation.SwitchParameter>]
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Command <System.String[]>]
    [-ConfigFile <System.String>]
    [-Contains <System.String>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-DscResource <System.String[]>]
    [-Filter <System.String>]
    [-FilterOnTag <System.String[]>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    [-Headers <System.String[]>]
    [-Includes <System.String[]>]
    -InputObject <Microsoft.PackageManagement.Packaging.SoftwareIdentity>
    [-LiteralPath <System.String>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    -Name <System.String[]>
    [-PackageManagementProvider <System.String>]
    [-Path <System.String>]
    [-ProviderName <System.String[]>]
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-PublishLocation <System.String>]
    [-RequiredVersion <System.String>]
    [-RoleCapability <System.String[]>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
    [-Source <System.String[]>]
    [-Tag <System.String[]>]
    [-Type <System.String>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `System.Management.Automation.SwitchParameter` | No | Automatically accept the license agreement during installation if the package requires it. |
| `-AllowPrereleaseVersions` | `System.Management.Automation.SwitchParameter` | No | Allows packages marked as Prerelease to be saved. |
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet saves all available versions of the package. |
| `-Command` | `System.String[]` | No | Specifies one or more commands included in the package. |
| `-ConfigFile` | `System.String` | No | Specifies a configuration File. |
| `-Contains` | `System.String` | No | `Save-Package` gets objects if any item in the object's property values are an exact match for the specified value. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to save a package from a specified package provider or source. |
| `-DscResource` | `System.String[]` | No | Specifies one or more Desired State Configuration (DSC) resources for the package. |
| `-Filter` | `System.String` | No | Specifies a filter for the package. |
| `-FilterOnTag` | `System.String[]` | No | Specifies the tag that filters the results. Results that don't contain the specified tag are excluded. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Save-Package` forces PackageManagement to automatically install the package provider for the specified package. |
| `-Headers` | `System.String[]` | No | Specifies the headers for the package. |
| `-Includes` | `System.String[]` | No | Indicates the resources that the package includes. |
| `-InputObject` | `Microsoft.PackageManagement.Packaging.SoftwareIdentity` | Yes | A software ID object that represents the package that you want to save. Software IDs are part of the results of the `Find-Package` cmdlet. |
| `-LiteralPath` | `System.String` | No | Specifies the literal path to which you want to save the package. You cannot add both this parameter and the Path parameter to the same command. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum version of the package that you want to save. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum version of the package that you want to find. |
| `-Name` | `System.String[]` | Yes | Specifies one or more package names. |
| `-PackageManagementProvider` | `System.String` | No | Specifies a package management provider. |
| `-Path` | `System.String` | No | Specifies the location on the local computer to store the package. |
| `-ProviderName` | `System.String[]` | No | Specifies one or more provider names. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than a direct connection to the internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server that is specified by the Proxy parameter. |
| `-PublishLocation` | `System.String` | No | Specifies the publish location. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact version of the package to save. |
| `-RoleCapability` | `System.String[]` | No | Specifies an array of role capabilities. |
| `-ScriptPublishLocation` | `System.String` | No | Specifies the script publish location. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies the script source location. |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips validating the credentials of a package. |
| `-Source` | `System.String[]` | No | Specifies one or more package sources. |
| `-Tag` | `System.String[]` | No | Specifies a tag to search for within the package metadata. |
| `-Type` | `System.String` | No | Specifies whether to search for packages with a module, a script, or either. |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Set-PackageSource

Replaces a package source for a specified package provider.

The `Set-PackageSource` replaces a package source for a specified package provider. Package sources are always managed by a package provider.

**Returns**: `None`

```
Set-PackageSource
    [-ConfigFile <System.String>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    -InputObject <Microsoft.PackageManagement.Packaging.PackageSource>
    [-Location <System.String>]
    [-Name <System.String>]
    [-NewLocation <System.String>]
    [-NewName <System.String>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String>]
    [-Proxy <System.Uri>]
    [-ProxyCredential <System.Management.Automation.PSCredential>]
    [-PublishLocation <System.String>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
    [-Trusted <System.Management.Automation.SwitchParameter>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ConfigFile` | `System.String` | No | Specifies a configuration file. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to install package providers. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Set-PackageSource` forces PackageManagement to automatically install the package provider. |
| `-InputObject` | `Microsoft.PackageManagement.Packaging.PackageSource` | Yes | Specifies a package source ID object that represents the package that you want to change. Package source IDs are part of the results of the `Get-PackageSource` cmdlet. |
| `-Location` | `System.String` | No | Specifies the current package source location. The value can be a URI, a file path, or any other destination format supported by the package provider. |
| `-Name` | `System.String` | No | Specifies a package source's name. |
| `-NewLocation` | `System.String` | No | Specifies the new location for a package source. The value can be a URI, a file path, or any other destination format supported by the package provider. |
| `-NewName` | `System.String` | No | Specifies the new name you assign to a package source. |
| `-PackageManagementProvider` | `System.String` | No | Specifies a package management provider. |
| `-ProviderName` | `System.String` | No | Specifies a provider name. |
| `-Proxy` | `System.Uri` | No | Specifies a proxy server for the request, rather than connecting directly to the Internet resource. |
| `-ProxyCredential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to use the proxy server that is specified by the Proxy parameter. |
| `-PublishLocation` | `System.String` | No | Specifies the publish location. |
| `-ScriptPublishLocation` | `System.String` | No | Specifies the script publish location. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies the script source location. |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips validating the credentials of a package source. |
| `-Trusted` | `System.Management.Automation.SwitchParameter` | No | Indicates that the source is a trusted package provider. Trusted sources don't prompt for verification to install packages. |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Uninstall-Package

Uninstalls one or more software packages.

The `Uninstall-Package` cmdlet uninstalls one or more software packages from the local computer. To find installed packages, use the `Get-Package` cmdlet. !INCLUDE [nuget-module (../../includes/nuget-module.md)]

**Returns**: `Microsoft.PackageManagement.Packaging.SoftwareIdentity`

```
Uninstall-Package
    [-AllowClobber <System.Management.Automation.SwitchParameter>]
    [-AllowPrereleaseVersions <System.Management.Automation.SwitchParameter>]
    [-AllVersions <System.Management.Automation.SwitchParameter>]
    [-Destination <System.String>]
    [-ExcludeVersion <System.Management.Automation.SwitchParameter>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    -InputObject <Microsoft.PackageManagement.Packaging.SoftwareIdentity[]>
    [-InstallUpdate <System.Management.Automation.SwitchParameter>]
    [-MaximumVersion <System.String>]
    [-MinimumVersion <System.String>]
    -Name <System.String[]>
    [-NoPathUpdate <System.Management.Automation.SwitchParameter>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String[]>]
    [-RequiredVersion <System.String>]
    [-Scope <System.String>]
    [-SkipDependencies <System.Management.Automation.SwitchParameter>]
    [-SkipPublisherCheck <System.Management.Automation.SwitchParameter>]
    [-Type <System.String>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowClobber` | `System.Management.Automation.SwitchParameter` | No | Overrides warning messages about conflicts with existing commands. Overwrites existing commands that have the same name as commands being installed. |
| `-AllowPrereleaseVersions` | `System.Management.Automation.SwitchParameter` | No | Allows packages marked as prerelease to be uninstalled. |
| `-AllVersions` | `System.Management.Automation.SwitchParameter` | No | Indicates that this cmdlet uninstalls all versions of the package. |
| `-Destination` | `System.String` | No | Specifies a string of the path to the input object. |
| `-ExcludeVersion` | `System.Management.Automation.SwitchParameter` | No | Switch to exclude the version number in the folder path. |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Forces PackageManagement to automatically install the package provider for the specified package. |
| `-InputObject` | `Microsoft.PackageManagement.Packaging.SoftwareIdentity[]` | Yes | Accepts pipeline input that specifies the package's SoftwareIdentity object from the `Get-Package` cmdlet. InputObject accepts the SoftwareIdentity object as a `Get-Package` value or a variable tha... |
| `-InstallUpdate` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Uninstall-Package` uninstalls updates. |
| `-MaximumVersion` | `System.String` | No | Specifies the maximum allowed package version that you want to uninstall. If you don't specify this parameter, `Uninstall-Package` uninstalls the package's newest version. |
| `-MinimumVersion` | `System.String` | No | Specifies the minimum allowed package version that you want to uninstall. If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any version spe... |
| `-Name` | `System.String[]` | Yes | Specifies one or more package names. Multiple package names must be separated by commas. |
| `-NoPathUpdate` | `System.Management.Automation.SwitchParameter` | No | NoPathUpdate only applies to the `Install-Script` cmdlet. NoPathUpdate is a dynamic parameter added by the provider and isn't supported by `Uninstall-Package`. |
| `-PackageManagementProvider` | `System.String` | No | Specifies the PackageManagement provider. |
| `-ProviderName` | `System.String[]` | No | Specifies one or more package provider names to search for packages. You can get package provider names by running the `Get-PackageProvider` cmdlet. |
| `-RequiredVersion` | `System.String` | No | Specifies the exact allowed version of the package that you want to uninstall. If you don't add this parameter, `Uninstall-Package` uninstalls the package's newest version that satisfies any versio... |
| `-Scope` | `System.String` | No | Specifies the scope for which to uninstall the package. The acceptable values for this parameter are as follows:   - CurrentUser   - AllUsers |
| `-SkipDependencies` | `System.Management.Automation.SwitchParameter` | No | Skips the uninstallation of software dependencies. |
| `-SkipPublisherCheck` | `System.Management.Automation.SwitchParameter` | No | Allows you to get a package version that is newer than your installed version. For example, an installed package that is digitally signed by a trusted publisher but a new version isn't digitally si... |
| `-Type` | `System.String` | No | Specifies whether to search for packages with a module, a script, or both. The acceptable values for this parameter are as follows:   - Module   - Script   - All |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if `Uninstall-Package` cmdlet is run. The cmdlet isn't run. |

---

### Unregister-PackageSource

Removes a registered package source.

The `Unregister-PackageSource` cmdlet removes a registered package source. Package sources are always managed by a package provider. To find package sources, use the `Get-PackageSource` cmdlet.

**Returns**: `None`

```
Unregister-PackageSource
    [-ConfigFile <System.String>]
    [-Credential <System.Management.Automation.PSCredential>]
    [-Force <System.Management.Automation.SwitchParameter>]
    [-ForceBootstrap <System.Management.Automation.SwitchParameter>]
    -InputObject <Microsoft.PackageManagement.Packaging.PackageSource[]>
    [-Location <System.String>]
    [-PackageManagementProvider <System.String>]
    [-ProviderName <System.String>]
    [-PublishLocation <System.String>]
    [-ScriptPublishLocation <System.String>]
    [-ScriptSourceLocation <System.String>]
    [-SkipValidate <System.Management.Automation.SwitchParameter>]
    [-Source <System.String>]
    [-Confirm <System.Management.Automation.SwitchParameter>]
    [-WhatIf <System.Management.Automation.SwitchParameter>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ConfigFile` | `System.String` | No | Specifies a configuration file. |
| `-Credential` | `System.Management.Automation.PSCredential` | No | Specifies a user account that has permission to access the computer and run commands. Type a user name, such as User01 , Domain01\User01 , or enter a PSCredential object, generated by the `Get-Cred... |
| `-Force` | `System.Management.Automation.SwitchParameter` | No | Forces the command to run without asking for user confirmation. Overrides restrictions that prevent `Unregister-PackageSource` from succeeding, with the exception of security. |
| `-ForceBootstrap` | `System.Management.Automation.SwitchParameter` | No | Indicates that `Unregister-PackageSource` forces PackageManagement to automatically uninstall the package provider for the specified package source. |
| `-InputObject` | `Microsoft.PackageManagement.Packaging.PackageSource[]` | Yes | Accepts pipeline input that specifies the PackageSource object from the `Get-PackageSource` cmdlet. InputObject accepts the PackageSource object as a `Get-PackageSource` value or a variable that co... |
| `-Location` | `System.String` | No | Specifies the location to which a package source points. The value of this parameter can be a URI, a file path, or any other destination format that is supported by the package provider. |
| `-PackageManagementProvider` | `System.String` | No | Specifies the PackageManagement provider. |
| `-ProviderName` | `System.String` | No | Specifies the provider name. |
| `-PublishLocation` | `System.String` | No | Specifies the publish location. |
| `-ScriptPublishLocation` | `System.String` | No | Specifies the script publish location. |
| `-ScriptSourceLocation` | `System.String` | No | Specifies the script source location. |
| `-SkipValidate` | `System.Management.Automation.SwitchParameter` | No | Switch that skips validating the credentials of a package source. |
| `-Source` | `System.String` | No | Specifies the friendly name of the package source. |
| `-Confirm` | `System.Management.Automation.SwitchParameter` | No | Prompts you for confirmation before `Unregister-PackageSource` is run. |
| `-WhatIf` | `System.Management.Automation.SwitchParameter` | No | Shows what would happen if `Unregister-PackageSource` cmdlet is run. The cmdlet isn't run. |

---

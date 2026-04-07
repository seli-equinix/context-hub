---
name: pwsh-psresourceget-cmdlets
description: "PowerShell 7.5 PSResourceGet cmdlets — Find, Install, Save, Update, Uninstall, Publish PSResource (replaces PowerShellGet)"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Compress-PSResource,Find-PSResource,Get-InstalledPSResource,Get-PSResource,Get-PSResourceRepository,Get-PSScriptFileInfo,Import-PSGetRepository,Install-PSResource,New-PSScriptFileInfo,Publish-PSResource,Register-PSResourceRepository,Reset-PSResourceRepository,Save-PSResource,Set-PSResourceRepository,Test-PSScriptFileInfo,Uninstall-PSResource,Unregister-PSResourceRepository,Update-PSModuleManifest,Update-PSResource,Update-PSScriptFileInfo"
---

# PowerShell 7.5 — Find

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Compress-PSResource` | Compresses a specified folder containing module or script resources into a `.nupkg` file. |
| `Find-PSResource` | Searches for packages from a repository (local or remote), based on a name or other package prope... |
| `Get-InstalledPSResource` | Returns modules and scripts installed on the machine via **PowerShellGet**. |
| `Get-PSResource` | Returns modules and scripts installed on the machine via **PowerShellGet**. |
| `Get-PSResourceRepository` | Finds and returns registered repository information. |
| `Get-PSScriptFileInfo` | Returns the metadata for a script. |
| `Import-PSGetRepository` | Finds the repositories registered with PowerShellGet and registers them for PSResourceGet. |
| `Install-PSResource` | Installs resources from a registered repository. |
| `New-PSScriptFileInfo` | The cmdlet creates a new script file, including metadata about the script. |
| `Publish-PSResource` | Publishes a specified module from the local computer to PSResource repository. |
| `Register-PSResourceRepository` | Registers a repository for PowerShell resources. |
| `Reset-PSResourceRepository` | Creates a new default `PSRepositories.xml` file with PSGallery registered. |
| `Save-PSResource` | Saves resources (modules and scripts) from a registered repository onto the machine. |
| `Set-PSResourceRepository` | Sets information for a registered repository. |
| `Test-PSScriptFileInfo` | Tests the comment-based metadata in a `.ps1` file to ensure it's valid for publication. |
| `Uninstall-PSResource` | Uninstalls a resource that was installed using **PowerShellGet**. |
| `Unregister-PSResourceRepository` | Removes a registered repository from the local machine. |
| `Update-PSModuleManifest` | Updates a module manifest file. |
| `Update-PSResource` | Downloads and installs the newest version of a package already installed on the local machine. |
| `Update-PSScriptFileInfo` | This cmdlet updates the comment-based metadata in an existing script `.ps1` file. |

---

### Compress-PSResource

Compresses a specified folder containing module or script resources into a `.nupkg` file.

This cmdlet compresses a specified folder containing module or script resources into a `.nupkg` file. isolates the pack feature in the `Publish-PSResource` cmdlet. This allows you to sign the `.nupkg` file before publishing it to a repository. You can publish the final `.nupkg` file using the **NupkgPath** parameter of `Publish-PSResource`.

**Returns**: `System.IO.FileInfo`

```
Compress-PSResource
    [-Confirm <Object>]
    -DestinationPath <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-SkipModuleManifestValidate <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-DestinationPath` | `Object` | Yes | Path to save the compressed resource. |
| `-PassThru` | `Object` | No | Pass the full path of the nupkg through the pipeline. |
| `-Path` | `Object` | Yes | Path to the resource to be compressed. |
| `-SkipModuleManifestValidate` | `Object` | No | Skips validating the module manifest before creating the `.nupkg` file. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Find-PSResource

Searches for packages from a repository (local or remote), based on a name or other package
properties.

The `Find-PSResource` cmdlet searches for a package from a repository (local or remote) based on a name or other package properties.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSResourceInfo`

```
Find-PSResource
    -CommandName <Object>
    [-Credential <Object>]
    -DscResourceName <Object>
    [-IncludeDependencies <Object>]
    [-Name <Object>]
    [-Prerelease <Object>]
    [-Repository <Object>]
    [-Tag <Object>]
    [-Type <Object>]
    [-Version <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CommandName` | `Object` | Yes | The name of the command to search for. |
| `-Credential` | `Object` | No | Optional credentials to be used when accessing a repository. |
| `-DscResourceName` | `Object` | Yes | The name of the DSC Resource to search for. |
| `-IncludeDependencies` | `Object` | No | When specified, search returns all matching resources their dependencies. Dependencies are deduplicated. |
| `-Name` | `Object` | No | Name of a resource to find. Wildcards are supported but NuGet only accepts the `*` character. NuGet doesn't support wildcard searches of local (file-based) repositories. |
| `-Prerelease` | `Object` | No | When specified, includes prerelease versions in search results returned. |
| `-Repository` | `Object` | No | Specifies one or more repository names to search. If not specified, search includes all registered repositories, in priority order (highest first), until a repository is found that contains the pac... |
| `-Tag` | `Object` | No | Filters search results for resources that include the specified tags. If multiple tags are specified, the cmdlet only returns resources that include all the tags provided. |
| `-Type` | `Object` | No | Specifies one or more resource types to find. Resource types supported are:   - `None` - `Module` - `Script` |
| `-Version` | `Object` | No | Specifies the version of the resource to be returned. The value can be an exact version or a version range using the NuGet versioning syntax.   Wildcards are supported but NuGet only accepts wildca... |

---

### Get-InstalledPSResource

Returns modules and scripts installed on the machine via **PowerShellGet**.

This cmdlet searches the module and script installation paths and returns **PSResourceInfo** objects that describes each resource item found. This is equivalent to the combined output of the `Get-InstalledModule` and `Get-InstalledScript` cmdlets from **PowerShellGet** v2.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSResourceInfo`

```
Get-InstalledPSResource
    [-Name <Object>]
    [-Path <Object>]
    [-Scope <Object>]
    [-Version <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `Object` | No | Name of a resource to find. Wildcards are supported but NuGet only accepts the `*` character. NuGet doesn't support wildcard searches of local (file-based) repositories. |
| `-Path` | `Object` | No | Specifies the path to search in. |
| `-Scope` | `Object` | No | Specifies the scope of the resource. |
| `-Version` | `Object` | No | Specifies the version of the resource to be returned. The value can be an exact version or a version range using the NuGet versioning syntax.   For more information about NuGet version ranges, see ... |

---

### Get-PSResource

Returns modules and scripts installed on the machine via **PowerShellGet**.

This cmdlet searches the module and script installation paths and returns **PSResourceInfo** objects that describes each resource item found. This is equivalent to the combined output of the `Get-InstalledModule` and `Get-InstalledScript` cmdlets from **PowerShellGet** v2.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSResourceInfo`

```
Get-PSResource
    [-Name <Object>]
    [-Path <Object>]
    [-Scope <Object>]
    [-Version <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `Object` | No | Name of a resource to find. Wildcards are supported but NuGet only accepts the `*` character. NuGet doesn't support wildcard searches of local (file-based) repositories. |
| `-Path` | `Object` | No | Specifies the path to search in. |
| `-Scope` | `Object` | No | Specifies the scope of the resource. |
| `-Version` | `Object` | No | Specifies the version of the resource to be returned. The value can be an exact version or a version range using the NuGet versioning syntax.   For more information about NuGet version ranges, see ... |

---

### Get-PSResourceRepository

Finds and returns registered repository information.

This cmdlet searches for PowerShell resource repositories that are registered on the machine. By default, it returns all registered repositories.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSRepositoryInfo`

```
Get-PSResourceRepository
    [-Name <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `Object` | No | The name of the repository to search for. Wildcards are supported. Tab completion for this parameter cycles through the registered repository names. |

---

### Get-PSScriptFileInfo

Returns the metadata for a script.

This cmdlet searches for a PowerShell script located on the machine and returns the script metadata information.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSScriptFileInfo`

```
Get-PSScriptFileInfo
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Path` | `Object` | Yes | Specifies the path to the resource. |

---

### Import-PSGetRepository

Finds the repositories registered with PowerShellGet and registers them for PSResourceGet.

**Returns**: `None documented`

```
Import-PSGetRepository
    [-Force]
    [-WhatIf]
    [-Confirm]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `SwitchParameter` | No | Use the -Force switch to overwrite existing repositories. |
| `-WhatIf` | `SwitchParameter` | No |  |
| `-Confirm` | `SwitchParameter` | No |  |

---

### Install-PSResource

Installs resources from a registered repository.

This cmdlet installs resources from a registered repository to an installation path on a machine. By default, the cmdlet doesn't return any object. Other parameters allow you to specify the repository, scope, and version for a resource, and suppress license prompts.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSResourceInfo`

```
Install-PSResource
    [-AcceptLicense <Object>]
    [-AuthenticodeCheck <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    -InputObject <Object>
    -Name <Object>
    [-NoClobber <Object>]
    [-PassThru <Object>]
    [-Prerelease <Object>]
    [-Quiet <Object>]
    [-Reinstall <Object>]
    [-Repository <Object>]
    -RequiredResource <Object>
    -RequiredResourceFile <Object>
    [-Scope <Object>]
    [-SkipDependencyCheck <Object>]
    [-TemporaryPath <Object>]
    [-TrustRepository <Object>]
    [-Version <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `Object` | No | Specifies that the resource should accept any request to accept the license agreement. This suppresses prompting if the module mandates that a user accept the license agreement. |
| `-AuthenticodeCheck` | `Object` | No | Validates Authenticode signatures and catalog files on Windows. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Optional credentials used when accessing a repository. |
| `-InputObject` | `Object` | Yes | Used for pipeline input. |
| `-Name` | `Object` | Yes | The name of one or more resources to install. |
| `-NoClobber` | `Object` | No | Prevents installing a package that contains cmdlets that already exist on the machine. |
| `-PassThru` | `Object` | No | When specified, outputs a **PSResourceInfo** object for the saved resource. |
| `-Prerelease` | `Object` | No | When specified, includes prerelease versions in search results returned. |
| `-Quiet` | `Object` | No | Suppresses installation progress bar. |
| `-Reinstall` | `Object` | No | Installs the latest version of a module even if the latest version is already installed. The installed version is overwritten. This allows you to repair a damaged installation of the module.   If a... |
| `-Repository` | `Object` | No | Specifies one or more repository names to search. If not specified, search includes all registered repositories, in priority order (highest first), until a repository is found that contains the pac... |
| `-RequiredResource` | `Object` | Yes | A hashtable or JSON string that specifies resources to install. Wildcard characters aren't allowed. See the [NOTES](#notes) section for a description of the file formats. |
| `-RequiredResourceFile` | `Object` | Yes | Path to a `.psd1` or `.json` that specifies resources to install. Wildcard characters aren't allowed. See the [NOTES](#notes) section for a description of the file formats. |
| `-Scope` | `Object` | No | Specifies the installation scope. Accepted values are:   - `CurrentUser` - `AllUsers`   The default scope is `CurrentUser`, which doesn't require elevation for install.   The `AllUsers` scope insta... |
| `-SkipDependencyCheck` | `Object` | No | Skips the check for resource dependencies. Only found resources are installed. No resources of the found resource are installed. |
| `-TemporaryPath` | `Object` | No | Specifies the path to temporarily install the resource before actual installation. If no temporary path is provided, the resource is temporarily installed in the current user's temporary folder. |
| `-TrustRepository` | `Object` | No | Suppress prompts to trust repository. The prompt to trust repository only occurs if the repository isn't configured as trusted. |
| `-Version` | `Object` | No | Specifies the version of the resource to be returned. The value can be an exact version or a version range using the NuGet versioning syntax.   For more information about NuGet version ranges, see ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### New-PSScriptFileInfo

The cmdlet creates a new script file, including metadata about the script.

The cmdlet creates a new script file containing the required metadata needed to publish a script package.

**Returns**: `System.Object`

```
New-PSScriptFileInfo
    [-Author <Object>]
    [-CompanyName <Object>]
    [-Copyright <Object>]
    -Description <Object>
    [-ExternalModuleDependencies <Object>]
    [-ExternalScriptDependencies <Object>]
    [-Force <Object>]
    [-Guid <Object>]
    [-IconUri <Object>]
    [-LicenseUri <Object>]
    -Path <Object>
    [-PrivateData <Object>]
    [-ProjectUri <Object>]
    [-ReleaseNotes <Object>]
    [-RequiredModules <Object>]
    [-RequiredScripts <Object>]
    [-Tags <Object>]
    [-Version <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Author` | `Object` | No | The name of the author of the script. |
| `-CompanyName` | `Object` | No | The name of the company owning the script. |
| `-Copyright` | `Object` | No | The copyright information for the script. |
| `-Description` | `Object` | Yes | The description of the script. |
| `-ExternalModuleDependencies` | `Object` | No | The list of external module dependencies taken by this script. |
| `-ExternalScriptDependencies` | `Object` | No | The list of external script dependencies taken by this script. |
| `-Force` | `Object` | No | Forces the cmdlet to overwrite any existing file. |
| `-Guid` | `Object` | No | The unique identifier for the script in GUID format. If you don't provide a GUID, the cmdlet creates a new one automatically. |
| `-IconUri` | `Object` | No | A Uniform Resource Identifier (URI) pointing to the icon associated with the script. |
| `-LicenseUri` | `Object` | No | The URI pointing to the license agreement file associated with the script. |
| `-Path` | `Object` | Yes | The filename and location where the script is created. |
| `-PrivateData` | `Object` | No | The private data associated with the script. |
| `-ProjectUri` | `Object` | No | The URI pointing to the project site associated with the script. |
| `-ReleaseNotes` | `Object` | No | The release notes for the script. |
| `-RequiredModules` | `Object` | No | The parameter takes an array of module specification hashtables. A module specification is a hashtable that has the following keys.   - `ModuleName` - **Required** Specifies the module name. - `GUI... |
| `-RequiredScripts` | `Object` | No | The list of scripts required by the script. |
| `-Tags` | `Object` | No | The tags associated with the script. Tag values are strings that shouldn't contain spaces. For more information, see [Tag details](/powershell/scripting/gallery/concepts/package-manifest-affecting-... |
| `-Version` | `Object` | No | The version of the script. If no value is provided **Version** defaults to `1.0.0.0`. |

---

### Publish-PSResource

Publishes a specified module from the local computer to PSResource repository.

This cmdlet combines the functions of the `Publish-Module` and `Publish-Script` cmdlets from **PowerShellGet** v2. `Publish-PSResource` publishes a resource from the local computer to an online NuGet-based repository. You can specify the resource by a path containing the module or script resource files or by pointing a prepackaged `.nupkg` file.

**Returns**: `System.Object`

```
Publish-PSResource
    [-ApiKey <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-DestinationPath <Object>]
    [-ModulePrefix <Object>]
    -NupkgPath <Object>
    -Path <Object>
    [-Proxy <Object>]
    [-ProxyCredential <Object>]
    [-Repository <Object>]
    [-SkipDependenciesCheck <Object>]
    [-SkipModuleManifestValidate <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApiKey` | `Object` | No | Specifies the API key that you want to use to publish a resource to the online gallery. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies a user account that has rights to a specific repository. |
| `-DestinationPath` | `Object` | No | Specifies the path where the NuGet package `.nupkg` file should be saved. This parameter can be used in conjunction with the **Repository** parameter to publish to a repository and also save the ex... |
| `-ModulePrefix` | `Object` | No | The value of the parameter is pre-pended to the package name. This information is only used for publishing and isn't included in the package metadata. The module prefix controls the visibility of t... |
| `-NupkgPath` | `Object` | Yes | Path to the `.nupkg` file to be published. The `.nupkg` file could have been created by a previous run of `Publish-PSResource` with the **DestinationPath** parameter. Or, you can create the `.nupkg... |
| `-Path` | `Object` | Yes | The path to the module or script file or the path to a folder containing the module or script file to be published. The cmdlet packages all files in the folder into a `.nupkg` file before publishin... |
| `-Proxy` | `Object` | No | The URL to a proxy server used to access repositories outside of your network. |
| `-ProxyCredential` | `Object` | No | The credentials required to use the proxy server. |
| `-Repository` | `Object` | No | Specifies the repository to publish to. |
| `-SkipDependenciesCheck` | `Object` | No | Bypasses the default check that all dependencies are present in the target repository. |
| `-SkipModuleManifestValidate` | `Object` | No | Skips validating the module manifest before publishing. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Register-PSResourceRepository

Registers a repository for PowerShell resources.

The cmdlet registers a NuGet repository containing PowerShell resources.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSRepositoryInfo`

```
Register-PSResourceRepository
    [-ApiVersion <Object>]
    [-Confirm <Object>]
    [-CredentialInfo <Object>]
    [-CredentialProvider <Object>]
    [-Force <Object>]
    -Name <Object>
    [-PassThru <Object>]
    [-Priority <Object>]
    -PSGallery <Object>
    -Repository <Object>
    [-Trusted <Object>]
    -Uri <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApiVersion` | `Object` | No | Specifies the API version used by the repository. Valid values are:   - `V2` - uses the NuGet V2 API - `V3` - uses the NuGet V3 API - `ContainerRegistry` - used for Azure Container Registry - `Loca... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-CredentialInfo` | `Object` | No | A **PSCredentialInfo** object that includes the name of a vault and a secret that's stored in a **Microsoft.PowerShell.SecretManagement** store. |
| `-CredentialProvider` | `Object` | No | This is a dynamic parameter that specifies the credential provider to use for the repository. This parameter is only available when the repository being registered is an Azure Artifacts feed. Valid... |
| `-Force` | `Object` | No | Overwrites a repository if it already exists. |
| `-Name` | `Object` | Yes | Name of the repository to be registered. Can't be `PSGallery`. |
| `-PassThru` | `Object` | No | When specified, displays the successfully registered repository and its information. |
| `-Priority` | `Object` | No | Specifies the priority ranking of the repository. Valid priority values range from 0 to 100. Lower values have a higher priority ranking. The default value is `50`.   Repositories are sorted by pri... |
| `-PSGallery` | `Object` | Yes | When specified, registers **PSGallery** repository. |
| `-Repository` | `Object` | Yes | Specifies an array of hashtables that contain repository information. Use this parameter to register multiple repositories at once. Each hashtable can only have keys associated with parameters for ... |
| `-Trusted` | `Object` | No | Specifies whether the repository should be trusted. |
| `-Uri` | `Object` | Yes | Specifies the location of the repository to be registered. The value must use one of the following URI schemas:   - `https://` - `http://` - `ftp://` - `file://` |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Reset-PSResourceRepository

Creates a new default `PSRepositories.xml` file with PSGallery registered.

This command resets the repository store by creating a store file with PSGallery registered. First it creates a new temporary file and only replaces the old file if creation succeeds. If creation fails, the old file is restored.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSRepositoryInfo`

```
Reset-PSResourceRepository
    [-Confirm <Object>]
    [-PassThru <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-PassThru` | `Object` | No | By default, the command does not generate any output. When specified, the command displays the results of the reset operation. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Save-PSResource

Saves resources (modules and scripts) from a registered repository onto the machine.

This cmdlet combines the functionality of the `Save-Module` and `Save-Script` cmdlets from **PowerShellGet** v2. `Save-PSResource` downloads a resource from a registered repository to a specific path on the local machine. By default, the resource is saved in the unpacked or installed format. The scripts or modules could be run from the saved location. There is also an option to download the resource in `.nupkg` format.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSResourceInfo`

```
Save-PSResource
    [-AcceptLicense <Object>]
    [-AsNupkg <Object>]
    [-AuthenticodeCheck <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-IncludeXml <Object>]
    -InputObject <Object>
    -Name <Object>
    [-PassThru <Object>]
    [-Path <Object>]
    [-Prerelease <Object>]
    [-Quiet <Object>]
    [-Repository <Object>]
    [-SkipDependencyCheck <Object>]
    [-TemporaryPath <Object>]
    [-TrustRepository <Object>]
    [-Version <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `Object` | No | For modules that require a license, automatically accepts the license agreement during installation.   This parameter was added in PSResourceGet 1.1.0-rc1. |
| `-AsNupkg` | `Object` | No | Saves the resource as a `.nupkg` file. |
| `-AuthenticodeCheck` | `Object` | No | Validates the resource's signed files and catalog files on Windows. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Optional credentials used when accessing a repository. |
| `-IncludeXml` | `Object` | No | Includes the PowerShellGet metadata XML used to verify that PowerShellGet has installed a module. |
| `-InputObject` | `Object` | Yes | Used for pipeline input. |
| `-Name` | `Object` | Yes | The name of one or more resources to install. |
| `-PassThru` | `Object` | No | When specified, outputs a **PSResourceInfo** object for the saved resource. |
| `-Path` | `Object` | No | Specifies the path to save the resource to. If no path is provided, the resource is saved in the current directory. |
| `-Prerelease` | `Object` | No | When specified, includes prerelease versions in search results returned. |
| `-Quiet` | `Object` | No | Suppresses the progress bar output.   This parameter was added in PSResourceGet 1.1.0-rc1. |
| `-Repository` | `Object` | No | Specifies one or more repository names to search. If not specified, search includes all registered repositories, in priority order (highest first), until a repository is found that contains the pac... |
| `-SkipDependencyCheck` | `Object` | No | Skips the check for resource dependencies. Only found resources are installed. No resources of the found resource are installed. |
| `-TemporaryPath` | `Object` | No | Specifies the path to temporarily install the resource before saving. If no temporary path is provided, the resource is temporarily installed in the current user's temporary folder. |
| `-TrustRepository` | `Object` | No | Suppress prompts to trust repository. The prompt to trust repository only occurs if the repository isn't configured as trusted. |
| `-Version` | `Object` | No | Specifies the version of the resource to be returned. The value can be an exact version or a version range using the NuGet versioning syntax.   For more information about NuGet version ranges, see ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Set-PSResourceRepository

Sets information for a registered repository.

The `Set-PSResourceRepository` cmdlet sets information for a registered repository.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSRepositoryInfo`

```
Set-PSResourceRepository
    [-ApiVersion <Object>]
    [-Confirm <Object>]
    [-CredentialInfo <Object>]
    [-CredentialProvider <Object>]
    -Name <Object>
    [-PassThru <Object>]
    [-Priority <Object>]
    -Repository <Object>
    [-Trusted <Object>]
    [-Uri <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApiVersion` | `Object` | No | Specifies the API version used by the repository. Valid values are:   - `v2` - uses the NuGet V2 API - `v3` - uses the NuGet V3 API - `ContainerRegistry` - used for Azure Container Registry - `loca... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-CredentialInfo` | `Object` | No | A **PSCredentialInfo** object that includes the name of a vault and a secret that's stored in a **Microsoft.PowerShell.SecretManagement** store. |
| `-CredentialProvider` | `Object` | No | This is a dynamic parameter that specifies the credential provider to use for the repository. This parameter is only available when the named repository is an Azure Artifacts feed. Valid values are... |
| `-Name` | `Object` | Yes | Specifies the name of the repository to be modified.   > [!NOTE] > The **Uri** value of the default **PSGallery** repository can't be changed. |
| `-PassThru` | `Object` | No | When specified, displays the successfully registered repository and its information. |
| `-Priority` | `Object` | No | Specifies the priority ranking of the repository. Valid priority values range from 0 to 100. Lower values have a higher priority ranking. The default value is `50`.   Repositories are sorted by pri... |
| `-Repository` | `Object` | Yes | Specifies an array of hashtables that contain repository information. Use this parameter to register multiple repositories at once. Each hashtable can only have keys associated with parameters for ... |
| `-Trusted` | `Object` | No | Specifies whether the repository should be trusted. |
| `-Uri` | `Object` | No | Specifies the location of the repository to be registered. The value must use one of the following URI schemas:   - `https://` - `http://` - `ftp://` - `file://` |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Test-PSScriptFileInfo

Tests the comment-based metadata in a `.ps1` file to ensure it's valid for publication.

This cmdlet tests the comment-based metadata in a `.ps1` file to ensure it's valid for publication to a repository.

**Returns**: `System.Boolean`

```
Test-PSScriptFileInfo
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Path` | `Object` | Yes | The path to `.ps1` script file. |

---

### Uninstall-PSResource

Uninstalls a resource that was installed using **PowerShellGet**.

This cmdlet combines the functionality of the `Uninstall-Module` and `Uninstall-Script` cmdlets from **PowerShellGet** v2. The cmdlet searches the package installation paths for resources that have the **PowerShellGet** XML metadata file. Matching resources are uninstalled from the system.

**Returns**: `System.Object`

```
Uninstall-PSResource
    [-Confirm <Object>]
    -InputObject <Object>
    -Name <Object>
    [-Prerelease <Object>]
    [-Scope <Object>]
    [-SkipDependencyCheck <Object>]
    [-Version <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-InputObject` | `Object` | Yes | Used for pipeline input. |
| `-Name` | `Object` | Yes | Name of a resource or resources to remove. Wildcards are supported but NuGet only accepts the `*` character. |
| `-Prerelease` | `Object` | No | Indicates that only prerelease version resources should be removed. |
| `-Scope` | `Object` | No | Specifies the scope of the resource to uninstall. |
| `-SkipDependencyCheck` | `Object` | No | By default, the cmdlet checks to see whether the resource being removed is a dependency for another resource. Using this parameter skips the dependency test. |
| `-Version` | `Object` | No | Specifies the version of the resource to be removed. The value can be an exact version or a version range using the NuGet versioning syntax.   For more information about NuGet version ranges, see [... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Unregister-PSResourceRepository

Removes a registered repository from the local machine.

The cmdlet removes a registered repository from the the local machine.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSRepositoryInfo`

```
Unregister-PSResourceRepository
    [-Confirm <Object>]
    -Name <Object>
    [-PassThru <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Name` | `Object` | Yes | The name of one or more repositories to remove. |
| `-PassThru` | `Object` | No | When specified, outputs a **PSRepositoryInfo** object for each repository that's removed. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Update-PSModuleManifest

Updates a module manifest file.

This cmdlet updates the data stored in a module manifest file. The parameters allow you to specify which properties get updated. `Update-PSModuleManifest` overwrites any existing values in the module manifest.

**Returns**: `System.Object`

```
Update-PSModuleManifest
    [-AliasesToExport <Object>]
    [-Author <Object>]
    [-ClrVersion <Object>]
    [-CmdletsToExport <Object>]
    [-CompanyName <Object>]
    [-CompatiblePSEditions <Object>]
    [-Copyright <Object>]
    [-DefaultCommandPrefix <Object>]
    [-Description <Object>]
    [-DotNetFrameworkVersion <Object>]
    [-DscResourcesToExport <Object>]
    [-ExternalModuleDependencies <Object>]
    [-FileList <Object>]
    [-FormatsToProcess <Object>]
    [-FunctionsToExport <Object>]
    [-Guid <Object>]
    [-HelpInfoUri <Object>]
    [-IconUri <Object>]
    [-LicenseUri <Object>]
    [-ModuleList <Object>]
    [-ModuleVersion <Object>]
    [-NestedModules <Object>]
    -Path <Object>
    [-PowerShellHostName <Object>]
    [-PowerShellHostVersion <Object>]
    [-PowerShellVersion <Object>]
    [-Prerelease <Object>]
    [-PrivateData <Object>]
    [-ProcessorArchitecture <Object>]
    [-ProjectUri <Object>]
    [-ReleaseNotes <Object>]
    [-RequiredAssemblies <Object>]
    [-RequiredModules <Object>]
    [-RequireLicenseAcceptance <Object>]
    [-RootModule <Object>]
    [-ScriptsToProcess <Object>]
    [-Tags <Object>]
    [-TypesToProcess <Object>]
    [-VariablesToExport <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AliasesToExport` | `Object` | No | Specifies the aliases that the module exports. Wildcards are permitted. |
| `-Author` | `Object` | No | Specifies the module author. |
| `-ClrVersion` | `Object` | No | Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework required by the module. |
| `-CmdletsToExport` | `Object` | No | Specifies the cmdlets that the module exports. Wildcards are permitted. |
| `-CompanyName` | `Object` | No | Specifies the company or vendor who created the module. |
| `-CompatiblePSEditions` | `Object` | No | Specifies the compatible **PSEditions** of the module. For information about **PSEdition**, see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition... |
| `-Copyright` | `Object` | No | Specifies a copyright statement for the module. |
| `-DefaultCommandPrefix` | `Object` | No | Specifies the default command prefix. |
| `-Description` | `Object` | No | Specifies a description of the module. |
| `-DotNetFrameworkVersion` | `Object` | No | Specifies the minimum version of the Microsoft .NET Framework required by the module. |
| `-DscResourcesToExport` | `Object` | No | Specifies the Desired State Configuration (DSC) resources that the module exports. Wildcards are permitted. |
| `-ExternalModuleDependencies` | `Object` | No | Specifies an array of external module dependencies. |
| `-FileList` | `Object` | No | Specifies all items that are included in the module. |
| `-FormatsToProcess` | `Object` | No | Specifies the formatting files (`.ps1xml`) that are processed when the module is imported.   When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files. Becau... |
| `-FunctionsToExport` | `Object` | No | Specifies the functions that the module exports. Wildcards are permitted. |
| `-Guid` | `Object` | No | Specifies a unique identifier for the module. The **GUID** is used to distinguish between modules with the same name. |
| `-HelpInfoUri` | `Object` | No | Specifies the internet address of the module's HelpInfo XML file. Enter a Uniform Resource Identifier (URI) that begins with `http:` or `https:`.   For more information, see [Updatable Help](/power... |
| `-IconUri` | `Object` | No | Specifies the URI of an icon for the module. The specified icon is displayed on the gallery web page for the module. |
| `-LicenseUri` | `Object` | No | Specifies the URL of licensing terms for the module. |
| `-ModuleList` | `Object` | No | Specifies an array of modules that are included in the module.   Enter each module name as a string or as a hashtable with **ModuleName** and **ModuleVersion** keys. The hashtable can also have an ... |
| `-ModuleVersion` | `Object` | No | Specifies the version of the module. |
| `-NestedModules` | `Object` | No | Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state. The files in the **NestedModules** key run in the order in which they're listed.   ... |
| `-Path` | `Object` | Yes | Specifies the path and filename of the module manifest. Enter filename with a `.psd1` file extension. |
| `-PowerShellHostName` | `Object` | No | Specifies the name of the PowerShell host program that the module requires. Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost. Wildcards aren't permitted.   The name of... |
| `-PowerShellHostVersion` | `Object` | No | Specifies the minimum version of the PowerShell host program that works with the module. Enter a version number, such as 1.1. |
| `-PowerShellVersion` | `Object` | No | Specifies the minimum version of PowerShell that works with this module. For example, you can specify versions such as `5.1` or `7.2`. |
| `-Prerelease` | `Object` | No | Specifies the prerelease value that's appended to the module version. For example, if **Prerelease** is `preview` and the **ModuleVersion** is `1.0.0`, the version of the module is `1.0.0-preview`. |
| `-PrivateData` | `Object` | No | Specifies data that's passed to the module when it's imported. This can be any arbitrary values stored in a hashtable. |
| `-ProcessorArchitecture` | `Object` | No | Specifies the processor architecture that the module requires.   The acceptable values for this parameter are:   - `Amd64` - `Arm` - `IA64` - `MSIL` - `None` (unknown or unspecified) - `X86` |
| `-ProjectUri` | `Object` | No | Specifies the URI of a web page about this project. |
| `-ReleaseNotes` | `Object` | No | Specifies a string that contains release notes or comments for the module. |
| `-RequiredAssemblies` | `Object` | No | Specifies the assembly (`.dll`) files required by the module. PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file spec... |
| `-RequiredModules` | `Object` | No | Specifies modules that must be in the global session state. If the required modules aren't in the global session state, PowerShell imports them. If the required modules aren't available, the `Impor... |
| `-RequireLicenseAcceptance` | `Object` | No | Specifies that a license acceptance is required for the module. |
| `-RootModule` | `Object` | No | Specifies the primary or root file of the module. Enter the filename of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), or a cmdlet definition XML f... |
| `-ScriptsToProcess` | `Object` | No | Specifies script (`.ps1`) files that run in the caller's session state when the module is imported. You can use these scripts to prepare an environment, just as you might use a login script.   To s... |
| `-Tags` | `Object` | No | Specifies an array of tags. |
| `-TypesToProcess` | `Object` | No | Specifies the type files (`.ps1xml`) that run when the module is imported.   When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files. Because type files ar... |
| `-VariablesToExport` | `Object` | No | Specifies the variables that the module exports. Wildcards are permitted.   Use this parameter to restrict which variables that are exported by the module. |

---

### Update-PSResource

Downloads and installs the newest version of a package already installed on the local machine.

`Update-PSResource` downloads and installs the newest version of a package already installed on the local machine. This cmdlet replaces the `Update-Module` and `Update-Script` cmdlets from **PowerShellGet** v2. The new version of the resource is installed side-by-side with previous versions in a new versioned folder.

**Returns**: `Microsoft.PowerShell.PSResourceGet.UtilClasses.PSResourceInfo`

```
Update-PSResource
    [-AcceptLicense <Object>]
    [-AuthenticodeCheck <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Force <Object>]
    [-Name <Object>]
    [-PassThru <Object>]
    [-Prerelease <Object>]
    [-Quiet <Object>]
    [-Repository <Object>]
    [-Scope <Object>]
    [-SkipDependencyCheck <Object>]
    [-TemporaryPath <Object>]
    [-TrustRepository <Object>]
    [-Version <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AcceptLicense` | `Object` | No | For resources that require a license, **AcceptLicense** automatically accepts the license agreement during the update. |
| `-AuthenticodeCheck` | `Object` | No | Validates signed files and catalog files on Windows. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies optional credentials used when accessing a private repository. |
| `-Force` | `Object` | No | When specified, bypasses checks for **TrustRepository** and **AcceptLicense** and updates the package. |
| `-Name` | `Object` | No | Specifies the name of one or more resources to update. Wildcards are supported but NuGet only accepts the `*` character. NuGet doesn't support wildcard searches of local (file-based) repositories. |
| `-PassThru` | `Object` | No | When specified, outputs a **PSResourceInfo** object for the saved resource. |
| `-Prerelease` | `Object` | No | When specified, allows updating to a prerelease version. |
| `-Quiet` | `Object` | No | Suppresses progress information. |
| `-Repository` | `Object` | No | Specifies one or more repository names to search. If not specified, search includes all registered repositories, in priority order (highest first), until a repository is found that contains the pac... |
| `-Scope` | `Object` | No | Specifies the installation scope. Accepted values are:   - `CurrentUser` - `AllUsers`   The default scope is `CurrentUser`, which doesn't require elevation. |
| `-SkipDependencyCheck` | `Object` | No | Skips the check for resource dependencies. This means that only named resources are updated. |
| `-TemporaryPath` | `Object` | No | Specifies the path to temporarily install the resource before actual installatoin. If no temporary path is provided, the resource is temporarily installed in the current user's temporary folder. |
| `-TrustRepository` | `Object` | No | Suppress prompts to trust repository. The prompt to trust repository only occurs if the repository isn't configured as trusted. |
| `-Version` | `Object` | No | Specifies the version of the resource to be returned. The value can be an exact version or a version range using the NuGet versioning syntax.   For more information about NuGet version ranges, see ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Update-PSScriptFileInfo

This cmdlet updates the comment-based metadata in an existing script `.ps1` file.

This cmdlet updates the comment-based metadata in an existing script `.ps1` file. This is similar to `Update-ModuleManifest`.

**Returns**: `System.Object`

```
Update-PSScriptFileInfo
    [-Author <Object>]
    [-CompanyName <Object>]
    [-Copyright <Object>]
    [-Description <Object>]
    [-ExternalModuleDependencies <Object>]
    [-ExternalScriptDependencies <Object>]
    [-Guid <Object>]
    [-IconUri <Object>]
    [-LicenseUri <Object>]
    -Path <Object>
    [-PrivateData <Object>]
    [-ProjectUri <Object>]
    [-ReleaseNotes <Object>]
    [-RemoveSignature <Object>]
    [-RequiredModules <Object>]
    [-RequiredScripts <Object>]
    [-Tags <Object>]
    [-Version <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Author` | `Object` | No | The name of the author of the script. |
| `-CompanyName` | `Object` | No | The name of the company owning the script. |
| `-Copyright` | `Object` | No | The copyright information for the script. |
| `-Description` | `Object` | No | The description of the script. |
| `-ExternalModuleDependencies` | `Object` | No | The list of external module dependencies taken by this script. |
| `-ExternalScriptDependencies` | `Object` | No | The list of external script dependencies taken by this script. |
| `-Guid` | `Object` | No | The unique identifier for the script in GUID format. |
| `-IconUri` | `Object` | No | A Uniform Resource Identifier (URI) pointing to the icon associated with the script. |
| `-LicenseUri` | `Object` | No | The URI pointing to the license agreement file associated with the script. |
| `-Path` | `Object` | Yes | The filename and location of the script. |
| `-PrivateData` | `Object` | No | The private data associated with the script. |
| `-ProjectUri` | `Object` | No | The URI pointing to the project site associated with the script. |
| `-ReleaseNotes` | `Object` | No | The release notes for the script. |
| `-RemoveSignature` | `Object` | No | Removes the signature from a signed `.ps1` file, allowing you to update the script. You should re-sign the after updating the file. |
| `-RequiredModules` | `Object` | No | The parameter takes an array of module specification hashtables. A module specification is a hashtable that has the following keys.   - `ModuleName` - **Required** Specifies the module name. - `GUI... |
| `-RequiredScripts` | `Object` | No | The list of scripts required by the script. |
| `-Tags` | `Object` | No | The tags associated with the script. Tag values are strings that shouldn't contain spaces. For more information, see [Tag details](/powershell/scripting/gallery/concepts/package-manifest-affecting-... |
| `-Version` | `Object` | No | The version of the script. |

---

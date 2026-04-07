---
name: pwsh-core-cmdlets
description: "PowerShell 7.5 Core cmdlets — modules, sessions, remoting, jobs, history, providers, errors, events, PSSession, Invoke-Command"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Add-History,Clear-History,Debug-Job,Disable-ExperimentalFeature,Enable-ExperimentalFeature,Enter-PSHostProcess,Enter-PSSession,Exit-PSHostProcess,Exit-PSSession,Export-ModuleMember,ForEach-Object,Get-Command,Get-ExperimentalFeature,Get-Help,Get-History,Get-Job,Get-Module,Get-PSHostProcessInfo,Get-PSSession,Get-PSSubsystem,Import-Module,Invoke-Command,Invoke-History,New-Module,New-ModuleManifest,New-PSRoleCapabilityFile,New-PSSession,New-PSSessionConfigurationFile,New-PSSessionOption,New-PSTransportOption,Out-Default,Out-Host,Out-Null,Receive-Job,Register-ArgumentCompleter,Remove-Job,Remove-Module,Remove-PSSession,Save-Help,Set-PSDebug,Set-StrictMode,Start-Job,Stop-Job,Switch-Process,Test-ModuleManifest,Update-Help,Wait-Job,Where-Object"
---

# PowerShell 7.5 — modules

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-History` | Appends entries to the session history. |
| `Clear-History` | Deletes entries from the PowerShell session command history. |
| `Debug-Job` | Debugs a running background or remote job. |
| `Disable-ExperimentalFeature` | Disable an experimental feature on startup of new instance of PowerShell. |
| `Enable-ExperimentalFeature` | Enable an experimental feature on startup of new instance of PowerShell. |
| `Enter-PSHostProcess` | Connects to and enters into an interactive session with a local process. |
| `Enter-PSSession` | Starts an interactive session with a remote computer. |
| `Exit-PSHostProcess` | Closes an interactive session with a local process. |
| `Exit-PSSession` | Ends an interactive session with a remote computer. |
| `Export-ModuleMember` | Specifies the module members that are exported. |
| `ForEach-Object` | Performs an operation against each item in a collection of input objects. |
| `Get-Command` | Gets all commands. |
| `Get-ExperimentalFeature` | Gets experimental features. |
| `Get-Help` | Displays information about PowerShell commands and concepts. |
| `Get-History` | Gets a list of the commands entered during the current session. |
| `Get-Job` | Gets PowerShell background jobs that are running in the current session. |
| `Get-Module` | List the modules imported in the current session or that can be imported from the PSModulePath. |
| `Get-PSHostProcessInfo` | Gets process information about the PowerShell host. |
| `Get-PSSession` | Gets the PowerShell sessions on local and remote computers. |
| `Get-PSSubsystem` | Retrieves information about the subsystems registered in PowerShell. |
| `Import-Module` | Adds modules to the current session. |
| `Invoke-Command` | Runs commands on local and remote computers. |
| `Invoke-History` | Runs commands from the session history. |
| `New-Module` | Creates a new dynamic module that exists only in memory. |
| `New-ModuleManifest` | Creates a new module manifest. |
| `New-PSRoleCapabilityFile` | Creates a file that defines a set of capabilities to be exposed through a session configuration. |
| `New-PSSession` | Creates a persistent connection to a local or remote computer. |
| `New-PSSessionConfigurationFile` | Creates a file that defines a session configuration. |
| `New-PSSessionOption` | Creates an object that contains advanced options for a PSSession. |
| `New-PSTransportOption` | Creates an object that contains advanced options for a session configuration. |
| `Out-Default` | Sends the output to the default formatter and to the default output cmdlet. |
| `Out-Host` | Sends output to the command line. |
| `Out-Null` | Hides the output instead of sending it down the pipeline or displaying it. |
| `Receive-Job` | Gets the results of the PowerShell background jobs in the current session. |
| `Register-ArgumentCompleter` | Registers a custom argument completer. |
| `Remove-Job` | Deletes a PowerShell background job. |
| `Remove-Module` | Removes modules from the current session. |
| `Remove-PSSession` | Closes one or more PowerShell sessions (PSSessions). |
| `Save-Help` | Downloads and saves the newest help files to a file system directory. |
| `Set-PSDebug` | Turns script debugging features on and off, sets the trace level, and toggles strict mode. |
| `Set-StrictMode` | Establishes and enforces coding rules in expressions, scripts, and scriptblocks. |
| `Start-Job` | Starts a PowerShell background job. |
| `Stop-Job` | Stops a PowerShell background job. |
| `Switch-Process` | On Linux and macOS, the cmdlet calls the `execv()` function to provide similar behavior as POSIX ... |
| `Test-ModuleManifest` | Verifies that a module manifest file accurately describes the contents of a module. |
| `Update-Help` | Downloads and installs the newest help files on your computer. |
| `Wait-Job` | Waits until one or all of the PowerShell jobs running in the session are in a terminating state. |
| `Where-Object` | Selects objects from a collection based on their property values. |

---

## Patterns & Common Usage

## Golden Rule

PowerShell classes are NOT C# classes:

- **No partial classes** — one class definition per type, in one file
- **Types must be defined before use** — parse order matters; referenced class must appear BEFORE the referencing class
- **Single inheritance only** — one base class, multiple interfaces (PS 7.4+)
- **No constructor chaining** like C# `this()` — use `$this.Init()` helper methods instead
- **Classes in .psm1 only** for cross-file use — `using module` does not work with `.ps1`
- **Return semantics differ** — methods emit ALL uncaptured output to the pipeline

## Class Declaration

```powershell
class ServerInfo {
    [string]$Name
    [string]$IPAddress
    [int]$Port = 443
}

$server = [ServerInfo]::new()
$server.Name = 'web01'

$server = [ServerInfo]@{ Name = 'web01'; IPAddress = '10.0.0.1'; Port = 8080 }
```

## Properties

Typed with optional defaults. Validation attributes work on properties.

```powershell
class User {
    [string]$Name = 'Unknown'

    [ValidateRange(1, 65535)]
    [int]$Port

    [ValidateNotNullOrEmpty()]
    [string]$Email

    [ValidateSet('Admin', 'User', 'Guest')]
    [string]$Role = 'User'

    [Nullable[datetime]]$LastLogin
}
```

No `readonly` keyword exists. Use hidden backing field + getter method as a workaround.

## Methods

Methods MUST declare a return type. Use `[void]` for no return. Every non-void method MUST have a `return` statement.

```powershell
class Calculator {
    [int]$Value = 0
    [void] Add([int]$n) { $this.Value += $n }
    [int] GetValue() { return $this.Value }

    # Method overloading
    [string] Format() { return "Value: $($this.Value)" }
    [string] Format([string]$prefix) { return "${prefix}: $($this.Value)" }
}
```

### Critical: Suppress Pipeline Output in Methods

```powershell
[string] CreateFile([string]$path) {
    New-Item -Path $path -ItemType File    # leaks FileInfo into return!
    return 'Done'
}

[string] CreateFile([string]$path) {
    $null = New-Item -Path $path -ItemType File
    return 'Done'
}
```

## Constructors

```powershell
class DatabaseConnection {
    [string]$Server
    [string]$Database
    [int]$Port

    DatabaseConnection() {
        $this.Server = 'localhost'; $this.Database = 'master'; $this.Port = 1433
    }
    DatabaseConnection([string]$server, [string]$database) {
        $this.Server = $server; $this.Database = $database; $this.Port = 1433
    }
    DatabaseConnection([string]$server, [string]$database, [int]$port) {
        $this.Server = $server; $this.Database = $database; $this.Port = $port
    }
}

$db = [DatabaseConnection]::new('sql01', 'AppDB', 5432)
```

### No Constructor Chaining — Use Init Helper

```powershell
class Service {
    [string]$Name; [int]$Port; [bool]$UseTls

    hidden [void] Init([string]$name, [int]$port, [bool]$tls) {
        $this.Name = $name; $this.Port = $port; $this.UseTls = $tls
    }

    Service() { $this.Init('default', 80, $false) }
    Service([string]$name) { $this.Init($name, 443, $true) }
    Service([string]$name, [int]$port) { $this.Init($name, $port, $true) }
}
```

### Static Factory Methods

```powershell
class Endpoint {
    [string]$Uri
    Endpoint([string]$uri) { $this.Uri = $uri }

    static [Endpoint] FromParts([string]$host, [int]$port) {
        return [Endpoint]::new("https://${host}:${port}")
    }
}
```


### Add-History

Appends entries to the session history.

The `Add-History` cmdlet adds entries to the end of the session history, that is, the list of commands entered during the current session.

**Returns**: `None`

```
Add-History
    [-InputObject <Object>]
    [-PassThru <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | No | Specifies an array of entries to add to the history as **HistoryInfo** object to the session history. You can use this parameter to submit a **HistoryInfo** object, such as the ones that are return... |
| `-PassThru` | `Object` | No | Indicates that this cmdlet returns a **HistoryInfo** object for each history entry. By default, this cmdlet does not generate any output. |

---

### Clear-History

Deletes entries from the PowerShell session command history.

`Clear-History` deletes the command history from a PowerShell session. Each PowerShell session has its own command history. To display the command history, use the `Get-History` cmdlet.

**Returns**: `None`

```
Clear-History
    [-CommandLine <Object>]
    [-Confirm <Object>]
    [-Count <Object>]
    [-Id <Object>]
    [-Newest <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CommandLine` | `Object` | No | Deletes command history from a PowerShell session. The string must be an exact match or use wildcards to match commands in the PowerShell session history displayed by `Get-History`. If you enter mo... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the `Clear-History` cmdlet. |
| `-Count` | `Object` | No | Specifies the number of history entries that `Clear-History` deletes. Commands are deleted in order, beginning with the oldest entry in the history.   The **Count** and **Id** parameters can be use... |
| `-Id` | `Object` | No | Specifies the command history **Id** that `Clear-History` deletes. To display **Id** numbers, use the `Get-History` cmdlet. The **Id** numbers are sequential and commands keep their **Id** number t... |
| `-Newest` | `Object` | No | When the **Newest** parameter is used, `Clear-History` deletes the newest entries in the history. By default, `Clear-History` deletes the oldest entries in the history.   The **Newest** parameter c... |
| `-WhatIf` | `Object` | No | Shows what would happen if the `Clear-History` cmdlet runs. The cmdlet is not run. |

---

### Debug-Job

Debugs a running background or remote job.

The `Debug-Job` cmdlet lets you debug scripts that are running within jobs. The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions. `Debug-Job` accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running. The debugger `quit` command stops the job and running script. The `exit` command detaches the debugger, and allows the job to continue to run.

**Returns**: `None documented`

```
Debug-Job
    [-BreakAll <Object>]
    [-Confirm <Object>]
    -Id <Object>
    -InstanceId <Object>
    -Job <Object>
    -Name <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BreakAll` | `Object` | No | Allows you to break immediately in the current location when the debugger attaches.   This parameter was added in PowerShell 7.2. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | Yes | Specifies the ID number of a running job. To get the ID number of a job, run the `Get-Job` cmdlet. |
| `-InstanceId` | `Object` | Yes | Specifies the instance ID GUID of a running job. |
| `-Job` | `Object` | Yes | Specifies a running job object. The simplest way to use this parameter is to save the results of a `Get-Job` command that returns the running job that you want to debug in a variable, and then spec... |
| `-Name` | `Object` | Yes | Specifies a job by the friendly name of the job. When you start a job, you can specify a job name by adding the **JobName** parameter, in cmdlets such as `Invoke-Command` and `Start-Job`. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Disable-ExperimentalFeature

Disable an experimental feature on startup of new instance of PowerShell.

The `Disable-ExperimentalFeature` cmdlet disables experimental features by removing the named experimental features from the `powershell.config.json` settings file read on PowerShell startup.

**Returns**: `None`

```
Disable-ExperimentalFeature
    [-Confirm <Object>]
    -Name <Object>
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Name` | `Object` | Yes | The name or names of the experimental features to disable. |
| `-Scope` | `Object` | No | Determines which `powershell.config.json` to update whether it affects all users or just the current user. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Enable-ExperimentalFeature

Enable an experimental feature on startup of new instance of PowerShell.

The `Enable-ExperimentalFeature` cmdlet enables experimental features by adding the named experimental features to the `powershell.config.json` settings file read on PowerShell startup.

**Returns**: `None`

```
Enable-ExperimentalFeature
    [-Confirm <Object>]
    -Name <Object>
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Name` | `Object` | Yes | The name or names of the experimental features to enable. |
| `-Scope` | `Object` | No | Determines which `powershell.config.json` to update whether it affects all users or just the current user. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Enter-PSHostProcess

Connects to and enters into an interactive session with a local process.

The `Enter-PSHostProcess` cmdlet connects to and enters into an interactive session with a local process. Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.

**Returns**: `None documented`

```
Enter-PSHostProcess
    [-AppDomainName <Object>]
    -CustomPipeName <Object>
    -HostProcessInfo <Object>
    -Id <Object>
    -Name <Object>
    -Process <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AppDomainName` | `Object` | No | Specifies an application domain name to connect to if omitted, uses **DefaultAppDomain**. Use `Get-PSHostProcessInfo` to display the application domain names. |
| `-CustomPipeName` | `Object` | Yes | Gets or sets the custom named pipe name to connect to. This is usually used in conjunction with `pwsh -CustomPipeName`.   This parameter was introduced in PowerShell 6.2. |
| `-HostProcessInfo` | `Object` | Yes | Specifies a **PSHostProcessInfo** object that can be connected to with PowerShell. Use `Get-PSHostProcessInfo` to get the object. |
| `-Id` | `Object` | Yes | Specifies a process by the process ID. To get a process ID, run the `Get-Process` cmdlet. |
| `-Name` | `Object` | Yes | Specifies a process by the process name. To get a process name, run the `Get-Process` cmdlet. You can also get process names from the Properties dialog box of a process in Task Manager. |
| `-Process` | `Object` | Yes | Specifies a process by the process object. The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and th... |

---

### Enter-PSSession

Starts an interactive session with a remote computer.

The `Enter-PSSession` cmdlet starts an interactive session with a single remote computer. During the session, the commands that you type run on the remote computer, just as if you were typing directly on the remote computer. You can have only one interactive session at a time.

**Returns**: `None`

```
Enter-PSSession
    [-AllowRedirection <Object>]
    [-ApplicationName <Object>]
    [-Authentication <Object>]
    [-CertificateThumbprint <Object>]
    -ComputerName <Object>
    [-ConfigurationName <Object>]
    [-ConnectingTimeout <Object>]
    [-ConnectionUri <Object>]
    -ContainerId <Object>
    -Credential <Object>
    [-EnableNetworkAccess <Object>]
    -HostName <Object>
    [-Id <Object>]
    [-InstanceId <Object>]
    [-KeyFilePath <Object>]
    [-Name <Object>]
    [-Options <Object>]
    [-Port <Object>]
    [-RunAsAdministrator <Object>]
    [-Session <Object>]
    [-SessionOption <Object>]
    [-SSHTransport <Object>]
    [-Subsystem <Object>]
    [-UserName <Object>]
    [-UseSSL <Object>]
    -VMId <Object>
    -VMName <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowRedirection` | `Object` | No | Allows redirection of this connection to an alternate Uniform Resource Identifier (URI). By default, redirection isn't allowed.   When you use the **ConnectionURI** parameter, the remote destinatio... |
| `-ApplicationName` | `Object` | No | Specifies the application name segment of the connection URI. Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.   The default ... |
| `-Authentication` | `Object` | No | Specifies the mechanism that's used to authenticate the user's credentials. The acceptable values for this parameter are:   - Default - Basic - Credssp - Digest - Kerberos - Negotiate - NegotiateWi... |
| `-CertificateThumbprint` | `Object` | No | Specifies the digital public key certificate (X509) of a user account that has permission to perform this action. Enter the certificate thumbprint of the certificate.   Certificates are used in cli... |
| `-ComputerName` | `Object` | Yes | Specifies a computer name. This cmdlet starts an interactive session with the specified remote computer. Enter only one computer name. The default is the local computer.   Type the NetBIOS name, th... |
| `-ConfigurationName` | `Object` | No | Specifies the session configuration that's used for the interactive session.   Enter a configuration name or the fully qualified resource URI for a session configuration. If you specify only the co... |
| `-ConnectingTimeout` | `Object` | No | Specifies the amount of time in milliseconds allowed for the initial SSH connection to complete. If the connection doesn't complete within the specified time, an error is returned.   This parameter... |
| `-ConnectionUri` | `Object` | No | Specifies a URI that defines the connection endpoint for the session. The URI must be fully qualified. The format of this string is as follows:   `<Transport>://<ComputerName>:<Port>/<ApplicationNa... |
| `-ContainerId` | `Object` | Yes | Specifies the ID of a container. |
| `-Credential` | `Object` | Yes | Specifies a user account that has permission to perform this action. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** obje... |
| `-EnableNetworkAccess` | `Object` | No | Indicates that this cmdlet adds an interactive security token to loopback sessions. The interactive token lets you run commands in the loopback session that get data from other computers. For examp... |
| `-HostName` | `Object` | Yes | Specifies a computer name for a Secure Shell (SSH) based connection. This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH rather tha... |
| `-Id` | `Object` | No | Specifies the ID of an existing session. `Enter-PSSession` uses the specified session for the interactive session.   To find the ID of a session, use the `Get-PSSession` cmdlet. |
| `-InstanceId` | `Object` | No | Specifies the instance ID of an existing session. `Enter-PSSession` uses the specified session for the interactive session.   The instance ID is a GUID. To find the instance ID of a session, use th... |
| `-KeyFilePath` | `Object` | No | Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.   SSH allows user authentication to be performed via private/public keys as an alternative to basic... |
| `-Name` | `Object` | No | Specifies the friendly name of an existing session. `Enter-PSSession` uses the specified session for the interactive session.   If the name that you specify matches more than one session, the comma... |
| `-Options` | `Object` | No | Specifies a hashtable of SSH options used when connecting to a remote SSH-based session. The possible options are any values supported by the Unix-based version of the [ssh](https://man.openbsd.org... |
| `-Port` | `Object` | No | Specifies the network port on the remote computer that's used for this command.   In PowerShell 6.0 this parameter was included in the **HostName** parameter set which supports Secure Shell (SSH) c... |
| `-RunAsAdministrator` | `Object` | No | Indicates that the **PSSession** runs as administrator. |
| `-Session` | `Object` | No | Specifies a PowerShell session (**PSSession**) to use for the interactive session. This parameter takes a session object. You can also use the **Name**, **InstanceId**, or **Id** parameters to spec... |
| `-SessionOption` | `Object` | No | Sets advanced options for the session. Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option ... |
| `-SSHTransport` | `Object` | No | Indicates that the remote connection is established using Secure Shell (SSH).   By default PowerShell uses Windows WinRM to connect to a remote computer. This switch forces PowerShell to use the Ho... |
| `-Subsystem` | `Object` | No | Specifies the SSH subsystem used for the new **PSSession**.   This specifies the subsystem to use on the target as defined in sshd_config. The subsystem starts a specific version of PowerShell with... |
| `-UserName` | `Object` | No | Specifies the user name for the account used to create a session on the remote computer. If the **UserName** parameter isn't specified then the current logged on username is used. User authenticati... |
| `-UseSSL` | `Object` | No | Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer. By default, SSL isn't used.   WS-Management encrypts all PowerShell content... |
| `-VMId` | `Object` | Yes | Specifies the ID of a virtual machine. |
| `-VMName` | `Object` | Yes | Specifies the name of a virtual machine. |

---

### Exit-PSHostProcess

Closes an interactive session with a local process.

The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet. You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process. Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.

**Returns**: `None documented`

```
Exit-PSHostProcess
```

---

### Exit-PSSession

Ends an interactive session with a remote computer.

The `Exit-PSSession` cmdlet ends interactive sessions that you started by using the `Enter-PSSession` cmdlet.

**Returns**: `None`

```
Exit-PSSession
```

---

### Export-ModuleMember

Specifies the module members that are exported.

The `Export-ModuleMember` cmdlet specifies the module members that are exported from a script module (`.psm1`) file, or from a dynamic module created by using the `New-Module` cmdlet. Module members include cmdlets, functions, variables, and aliases. This cmdlet can be used only in a script module file or a dynamic module.

**Returns**: `None`

```
Export-ModuleMember
    [-Alias <Object>]
    [-Cmdlet <Object>]
    [-Function <Object>]
    [-Variable <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Alias` | `Object` | No | Specifies the aliases that are exported from the script module file. Enter the alias names. Wildcard characters are permitted. |
| `-Cmdlet` | `Object` | No | Specifies the cmdlets that are exported from the script module file. Enter the cmdlet names. Wildcard characters are permitted.   You cannot create cmdlets in a script module file, but you can impo... |
| `-Function` | `Object` | No | Specifies the functions that are exported from the script module file. Enter the function names. Wildcard characters are permitted. You can also pipe function name strings to `Export-ModuleMember`. |
| `-Variable` | `Object` | No | Specifies the variables that are exported from the script module file. Enter the variable names, without a dollar sign character (`$`). Wildcard characters are permitted. |

**Patterns & Best Practices:**

**The module manifest (.psd1) is the contract.** It controls what a module exports — not `Export-ModuleMember`. When a manifest with explicit `FunctionsToExport`, `CmdletsToExport`, `VariablesToExport`, and `AliasesToExport` entries exists, those fields determine visibility and override `Export-ModuleMember`.


**Patterns & Best Practices:**

Used inside .psm1 to control exports. **The manifest overrides it** when both exist.

When `Export-ModuleMember` matters:
1. **No manifest** — it is the only export control.
2. **Manifest with `'*'` wildcards** — acts as secondary filter.

Without `Export-ModuleMember` and no manifest: all functions export, no variables or aliases export.

```powershell
function Get-Widget { "public" }
function Set-Widget { param($Name) }
function Initialize-Internal { }  # Helper
$ModuleVersion = '1.0.0'

Export-ModuleMember -Function 'Get-Widget', 'Set-Widget' -Variable 'ModuleVersion'
```


---

### ForEach-Object

Performs an operation against each item in a collection of input objects.

The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects. The input objects can be piped to the cmdlet or specified using the **InputObject** parameter.

**Returns**: `System.Management.Automation.PSObject`

```
ForEach-Object
    [-ArgumentList <Object>]
    [-AsJob <Object>]
    [-Begin <Object>]
    [-Confirm <Object>]
    [-End <Object>]
    [-InputObject <Object>]
    -MemberName <Object>
    -Parallel <Object>
    -Process <Object>
    [-RemainingScripts <Object>]
    [-ThrottleLimit <Object>]
    [-TimeoutSeconds <Object>]
    [-UseNewRunspace <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object` | No | Specifies an array of arguments to a method call. For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).   This paramete... |
| `-AsJob` | `Object` | No | Causes the parallel invocation to run as a PowerShell job. A single job object is returned instead of output from the running scriptblocks. The job object contains child jobs for each parallel scri... |
| `-Begin` | `Object` | No | Specifies a scriptblock that runs before this cmdlet processes any input objects. This scriptblock is only run once for the entire pipeline. For more information about the `begin` block, see [about... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-End` | `Object` | No | Specifies a scriptblock that runs after this cmdlet processes all input objects. This scriptblock is only run once for the entire pipeline. For more information about the `end` block, see [about_Fu... |
| `-InputObject` | `Object` | No | Specifies the input objects. `ForEach-Object` runs the scriptblock or operation statement on each input object. Enter a variable that contains the objects, or type a command or expression that gets... |
| `-MemberName` | `Object` | Yes | Specifies the name of the member property to get or the member method to call. The members must be instance members, not static members.   Wildcard characters are permitted, but work only if the re... |
| `-Parallel` | `Object` | Yes | Specifies the scriptblock to be used for parallel processing of input objects. Enter a scriptblock that describes the operation.   This parameter was introduced in PowerShell 7.0. |
| `-Process` | `Object` | Yes | Specifies the operation that's performed on each input object. This scriptblock is run for every object in the pipeline. For more information about the `process` block, see [about_Functions](about/... |
| `-RemainingScripts` | `Object` | No | Specifies all scriptblocks that aren't taken by the **Process** parameter.   This parameter was introduced in Windows PowerShell 3.0. |
| `-ThrottleLimit` | `Object` | No | Specifies the number of scriptblocks that run in parallel. Input objects are blocked until the running scriptblock count falls below the **ThrottleLimit**. The default value is `5`.   The ThrottleL... |
| `-TimeoutSeconds` | `Object` | No | Specifies the number of seconds to wait for all input to be processed in parallel. After the specified timeout time, all running scripts are stopped. And any remaining input objects to be processed... |
| `-UseNewRunspace` | `Object` | No | Causes the parallel invocation to create a new runspace for every loop iteration instead of reusing runspaces from the runspace pool.   This parameter was introduced in PowerShell 7.1 |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Get-Command

Gets all commands.

The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications. `Get-Command` gets the commands from PowerShell modules and commands available on your system. To get only commands that have been imported into the current session, use the **ListImported** parameter.

**Returns**: `System.Management.Automation.CommandInfo`

```
Get-Command
    [-All <Object>]
    [-ArgumentList <Object>]
    [-CommandType <Object>]
    [-FullyQualifiedModule <Object>]
    [-FuzzyMinimumDistance <Object>]
    [-ListImported <Object>]
    [-Module <Object>]
    [-Name <Object>]
    [-Noun <Object>]
    [-ParameterName <Object>]
    [-ParameterType <Object>]
    [-ShowCommandInfo <Object>]
    [-Syntax <Object>]
    [-TotalCount <Object>]
    [-UseAbbreviationExpansion <Object>]
    [-UseFuzzyMatching <Object>]
    [-Verb <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-All` | `Object` | No | Indicates that this cmdlet gets all commands, including commands of the same type that have the same name. By default, `Get-Command` gets only the commands that run when you type the command name. ... |
| `-ArgumentList` | `Object` | No | Specifies an array of arguments. This cmdlet gets information about a cmdlet or function when it's used with the specified parameters ("arguments"). The alias for **ArgumentList** is **Args**.   To... |
| `-CommandType` | `Object` | No | Specifies the types of commands that this cmdlet gets. Enter one or more command types. Use **CommandType** or its alias, **Type**. By default, `Get-Command` gets all cmdlets, functions, and aliase... |
| `-FullyQualifiedModule` | `Object` | No | The value can be a module name or a full module specification. PowerShell searches the **PSModulePath** for the specified module.   A module specification is a hashtable that has the following keys... |
| `-FuzzyMinimumDistance` | `Object` | No | This parameter allows filtering fuzzy results to be more or less accurate. The distance is calculated using the Damerau Levenshtein Distance algorithm, which indicates how many steps is the match f... |
| `-ListImported` | `Object` | No | Indicates that this cmdlet gets only commands in the current session.   Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the command... |
| `-Module` | `Object` | No | Specifies an array of modules. This cmdlet gets the commands that came from the specified modules. Enter the names of modules or module objects.   This parameter takes string values, but the value ... |
| `-Name` | `Object` | No | Specifies an array of names. This cmdlet gets only commands that have the specified name. Enter a name or name pattern. Wildcard characters are permitted.   To get commands that have the same name,... |
| `-Noun` | `Object` | No | Specifies an array of command nouns. This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun. Enter one or more nouns or noun patte... |
| `-ParameterName` | `Object` | No | Specifies an array of parameter names. This cmdlet gets commands in the session that have the specified parameters. Enter parameter names or parameter aliases. Wildcard characters are supported.   ... |
| `-ParameterType` | `Object` | No | Specifies an array of parameter names. This cmdlet gets commands in the session that have parameters of the specified type. Enter the full name or partial name of a parameter type. Wildcard charact... |
| `-ShowCommandInfo` | `Object` | No | Indicates that this cmdlet displays command information.   This parameter was introduced in Windows PowerShell 5.0. |
| `-Syntax` | `Object` | No | Indicates that this cmdlet gets only the following specified data about the command:   - Aliases. Gets the standard name. - Cmdlets. Gets the syntax. - Functions and filters. Gets the function defi... |
| `-TotalCount` | `Object` | No | Specifies the number of commands to get. You can use this parameter to limit the output of a command. |
| `-UseAbbreviationExpansion` | `Object` | No | Indicates using matching of the characters in the command to find with uppercase characters in a command. For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to ... |
| `-UseFuzzyMatching` | `Object` | No | Indicates using a fuzzy matching algorithm when finding commands. The order of the output is from closest match to least likely match. Wildcards shouldn't be used with fuzzy matching as it will att... |
| `-Verb` | `Object` | No | Specifies an array of command verbs. This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb. Enter one or more verbs or verb patte... |

**Patterns & Best Practices:**

Alias > Function > Cmdlet > External Application.

```powershell
function ping { Write-Host 'Custom' }
ping          # Runs function, NOT ping.exe
& (Get-Command ping.exe).Source 8.8.8.8
Microsoft.PowerShell.Management\Get-ChildItem
```


---

### Get-ExperimentalFeature

Gets experimental features.

The `Get-ExperimentalFeature` cmdlet returns all experimental features discovered by PowerShell. Experimental features can come from modules or the PowerShell engine. Experimental features allow users to safely test new features and provide feedback (typically via GitHub) before the design is considered complete and any changes can become a breaking change.

**Returns**: `System.Management.Automation.ExperimentalFeature`

```
Get-ExperimentalFeature
    [-Name <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `Object` | No | Name or names of specific experimental features to return. |

---

### Get-Help

Displays information about PowerShell commands and concepts.

The `Get-Help` cmdlet displays information about PowerShell concepts and commands, including cmdlets, functions, Common Information Model (CIM) commands, workflows, providers, aliases, and scripts.

**Returns**: `ExtendedCmdletHelpInfo`

```
Get-Help
    [-Category <Object>]
    [-Component <Object>]
    -Detailed <Object>
    -Examples <Object>
    [-Full <Object>]
    [-Functionality <Object>]
    [-Name <Object>]
    -Online <Object>
    -Parameter <Object>
    [-Path <Object>]
    [-Role <Object>]
    -ShowWindow <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `Object` | No | Displays help only for items in the specified category and their aliases. Conceptual articles are in the **HelpFile** category.   The acceptable values for this parameter are as follows:   - Alias ... |
| `-Component` | `Object` | No | Displays commands with the specified component value, such as **Exchange**. Enter a component name. Wildcard characters are permitted. This parameter has no effect on displays of conceptual (**Abou... |
| `-Detailed` | `Object` | Yes | Adds parameter descriptions and examples to the basic help display. This parameter is effective only when the help files are installed on the computer. It has no effect on displays of conceptual (*... |
| `-Examples` | `Object` | Yes | Displays only the name, synopsis, and examples. This parameter is effective only when the help files are installed on the computer. It has no effect on displays of conceptual (**About_**) help. |
| `-Full` | `Object` | No | Displays the entire help article for a cmdlet. **Full** includes parameter descriptions and attributes, examples, input and output object types, and additional notes.   This parameter is effective ... |
| `-Functionality` | `Object` | No | Displays help for items with the specified functionality. Enter the functionality. Wildcard characters are permitted. This parameter has no effect on displays of conceptual (**About_**) help. |
| `-Name` | `Object` | No | Gets help about the specified command or concept. Enter the name of a cmdlet, function, provider, script, or workflow, such as `Get-Member`, a conceptual article name, such as `about_Objects`, or a... |
| `-Online` | `Object` | Yes | Displays the online version of a help article in the default browser. This parameter is valid only for cmdlet, function, workflow, and script help articles. You can't use the **Online** parameter w... |
| `-Parameter` | `Object` | Yes | Displays only the detailed descriptions of the specified parameters. Wildcards are permitted. This parameter has no effect on displays of conceptual (**About_**) help. |
| `-Path` | `Object` | No | Gets help that explains how the cmdlet works in the specified provider path. Enter a PowerShell provider path.   This parameter gets a customized version of a cmdlet help article that explains how ... |
| `-Role` | `Object` | No | Displays help customized for the specified user role. Enter a role. Wildcard characters are permitted.   Enter the role that the user plays in an organization. Some cmdlets display different text i... |
| `-ShowWindow` | `Object` | Yes | Displays the help topic in a window for easier reading. The window includes a **Find** search feature and a **Settings** box that lets you set options for the display, including options to display ... |

---

### Get-History

Gets a list of the commands entered during the current session.

The `Get-History` cmdlet gets the session history, that is, the list of commands entered during the current session.

**Returns**: `Microsoft.PowerShell.Commands.HistoryInfo`

```
Get-History
    [-Count <Object>]
    [-Id <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Count` | `Object` | No | Specifies the number of the most recent history entries that this cmdlet gets. By, default, `Get-History` gets all entries in the session history. If you use both the **Count** and **Id** parameter... |
| `-Id` | `Object` | No | Specifies an array of the IDs of entries in the session history. `Get-History` gets only specified entries. If you use both the **Id** and **Count** parameters in a command, `Get-History` gets the ... |

---

### Get-Job

Gets PowerShell background jobs that are running in the current session.

The `Get-Job` cmdlet gets objects that represent the background jobs that were started in the current session. You can use `Get-Job` to get jobs that were started by using the `Start-Job` cmdlet, or by using the **AsJob** parameter of any cmdlet.

**Returns**: `System.Management.Automation.RemotingJob`

```
Get-Job
    [-After <Object>]
    [-Before <Object>]
    [-ChildJobState <Object>]
    [-Command <Object>]
    -Filter <Object>
    [-HasMoreData <Object>]
    [-Id <Object>]
    [-IncludeChildJob <Object>]
    -InstanceId <Object>
    -Name <Object>
    [-Newest <Object>]
    -State <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-After` | `Object` | No | Gets completed jobs that ended after the specified date and time. Enter a **DateTime** object, such as one returned by the `Get-Date` cmdlet or a string that can be converted to a **DateTime** obje... |
| `-Before` | `Object` | No | Gets completed jobs that ended before the specified date and time. Enter a **DateTime** object.   This parameter works only on custom job types, such as workflow jobs and scheduled jobs, that have ... |
| `-ChildJobState` | `Object` | No | Gets only the child jobs that have the specified state. The acceptable values for this parameter are:   - NotStarted - Running - Completed - Failed - Stopped - Blocked - Suspended - Disconnected - ... |
| `-Command` | `Object` | No | Specifies an array of commands as strings. This cmdlet gets the jobs that include the specified commands. The default is all jobs. You can use wildcard characters to specify a command pattern. |
| `-Filter` | `Object` | Yes | Specifies a hash table of conditions. This cmdlet gets jobs that satisfy all of the conditions. Enter a hash table where the keys are job properties and the values are job property values.   This p... |
| `-HasMoreData` | `Object` | No | Indicates whether this cmdlet gets only jobs that have the specified **HasMoreData** property value. The **HasMoreData** property indicates whether all job results have been received in the current... |
| `-Id` | `Object` | No | Specifies an array of IDs of jobs that this cmdlet gets.   The ID is an integer that uniquely identifies the job in the current session. It is easier to remember and to type than the instance ID, b... |
| `-IncludeChildJob` | `Object` | No | Indicates that this cmdlet returns child jobs, in addition to parent jobs.   This parameter is especially useful for investigating workflow jobs, for which `Get-Job` returns a container parent job,... |
| `-InstanceId` | `Object` | Yes | Specifies an array of instance IDs of jobs that this cmdlet gets. The default is all jobs.   An instance ID is a GUID that uniquely identifies the job on the computer. To find the instance ID of a ... |
| `-Name` | `Object` | Yes | Specifies an array of instance friendly names of jobs that this cmdlet gets. Enter a job name, or use wildcard characters to enter a job name pattern. By default, `Get-Job` gets all jobs in the cur... |
| `-Newest` | `Object` | No | Specifies a number of jobs to get. This cmdlet gets the jobs that ended most recently.   The **Newest** parameter does not sort or return the newest jobs in end-time order. To sort the output, use ... |
| `-State` | `Object` | Yes | Specifies a job state. This cmdlet gets only jobs in the specified state. The acceptable values for this parameter are:   - NotStarted - Running - Completed - Failed - Stopped - Blocked - Suspended... |

---

### Get-Module

List the modules imported in the current session or that can be imported from the PSModulePath.

The `Get-Module` cmdlet lists the PowerShell modules that have been imported, or that can be imported, into a PowerShell session. Without parameters, `Get-Module` gets modules that have been imported into the current session. The **ListAvailable** parameter is used to list the modules that are available to be imported from the paths specified in the **PSModulePath** environment variable (`$Env:PSModulePath`).

**Returns**: `System.Management.Automation.PSModuleInfo`

```
Get-Module
    [-All <Object>]
    [-CimNamespace <Object>]
    [-CimResourceUri <Object>]
    -CimSession <Object>
    [-FullyQualifiedName <Object>]
    -ListAvailable <Object>
    [-Name <Object>]
    [-PSEdition <Object>]
    -PSSession <Object>
    [-Refresh <Object>]
    [-SkipEditionCheck <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-All` | `Object` | No | Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (`.psd1`) files, script module (`.psm1`) files, and binary module (`.dll`) files. Without this ... |
| `-CimNamespace` | `Object` | No | Specifies the namespace of an alternate CIM provider that exposes CIM modules. The default value is the namespace of the Module Discovery WMI provider.   Use this parameter to get CIM modules from ... |
| `-CimResourceUri` | `Object` | No | Specifies an alternate location for CIM modules. The default value is the resource URI of the Module Discovery WMI provider on the remote computer.   Use this parameter to get CIM modules from comp... |
| `-CimSession` | `Object` | Yes | Specifies a CIM session on the remote computer. Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-c... |
| `-FullyQualifiedName` | `Object` | No | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-ListAvailable` | `Object` | Yes | By default, `Get-Module` only returns the modules that have been imported into the current session. With this parameter the command lists modules installed in any path included in the `$env:PSModul... |
| `-Name` | `Object` | No | Specifies names or name patterns of modules that this cmdlet gets. Wildcard characters are permitted. You can also pipe the names to `Get-Module`. You cannot specify the **FullyQualifiedName** para... |
| `-PSEdition` | `Object` | No | Gets the modules that support specified edition of PowerShell.   The acceptable values for this parameter are:   - `Desktop` - `Core`   The `Get-Module` cmdlet checks **CompatiblePSEditions** prope... |
| `-PSSession` | `Object` | Yes | Gets the modules in the specified user-managed PowerShell session (**PSSession**). Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or... |
| `-Refresh` | `Object` | No | Indicates that this cmdlet refreshes the cache of installed commands. The command cache is created when the session starts. It enables the `Get-Command` cmdlet to get commands from modules that are... |
| `-SkipEditionCheck` | `Object` | No | Skips the check of the **CompatiblePSEditions** field.   By default, `Get-Module` omits modules in the `%windir%\System32\WindowsPowerShell\v1.0\Modules` directory that do not specify `Core` in the... |

**Patterns & Best Practices:**

| Task | Command |
|------|---------|
| Create manifest | `New-ModuleManifest -Path ./M/M.psd1 -RootModule M.psm1` |
| Import module | `Import-Module MyModule` |
| Import version | `Import-Module MyModule -RequiredVersion 2.0.0` |
| Reimport (dev) | `Import-Module MyModule -Force` |
| List loaded | `Get-Module` |
| List installed | `Get-Module -ListAvailable` |
| Find on gallery | `Find-Module -Name 'ModName'` |
| Install | `Install-Module ModName -Scope CurrentUser` |
| Validate manifest | `Test-ModuleManifest ./M/M.psd1` |
| Module paths | `$env:PSModulePath -split [IO.Path]::PathSeparator` |
| Require in script | `#Requires -Modules ModName` |


---

### Get-PSHostProcessInfo

Gets process information about the PowerShell host.

The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.

**Returns**: `Microsoft.PowerShell.Commands.PSHostProcessInfo`

```
Get-PSHostProcessInfo
    -Id <Object>
    [-Name <Object>]
    -Process <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `Object` | Yes | Specifies a process by the process ID. To get a process ID, run the `Get-Process` cmdlet. |
| `-Name` | `Object` | No | Specifies a process by the process name. To get a process name, run the `Get-Process` cmdlet. |
| `-Process` | `Object` | Yes | Specifies a process by the process object. The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and th... |

---

### Get-PSSession

Gets the PowerShell sessions on local and remote computers.

The `Get-PSSession` cmdlet gets the user-managed PowerShell sessions (**PSSessions**) on local and remote computers.

**Returns**: `System.Management.Automation.Runspaces.PSSession`

```
Get-PSSession
    [-AllowRedirection <Object>]
    [-ApplicationName <Object>]
    [-Authentication <Object>]
    [-CertificateThumbprint <Object>]
    -ComputerName <Object>
    [-ConfigurationName <Object>]
    -ConnectionUri <Object>
    -ContainerId <Object>
    [-Credential <Object>]
    -Id <Object>
    -InstanceId <Object>
    [-Name <Object>]
    [-Port <Object>]
    [-SessionOption <Object>]
    [-State <Object>]
    [-ThrottleLimit <Object>]
    [-UseSSL <Object>]
    -VMId <Object>
    -VMName <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowRedirection` | `Object` | No | Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI). By default, PowerShell does not redirect connections.   This parameter configures... |
| `-ApplicationName` | `Object` | No | Specifies the name of an application. This cmdlet connects only to sessions that use the specified application.   Enter the application name segment of the connection URI. For example, in the follo... |
| `-Authentication` | `Object` | No | Specifies the mechanism that is used to authenticate credentials for the session in which the `Get-PSSession` command runs.   This parameter configures the temporary connection that is created to r... |
| `-CertificateThumbprint` | `Object` | No | Specifies the digital public key certificate (X509) of a user account that has permission to create the session in which the `Get-PSSession` command runs. Enter the certificate thumbprint of the ce... |
| `-ComputerName` | `Object` | Yes | Specifies an array of names of computers. Gets the sessions that connect to the specified computers. Wildcard characters are not permitted. There is no default value.   Beginning in Windows PowerSh... |
| `-ConfigurationName` | `Object` | No | Specifies the name of a configuration. This cmdlet gets only to sessions that use the specified session configuration.   Enter a configuration name or the fully qualified resource URI for a session... |
| `-ConnectionUri` | `Object` | Yes | Specifies a URI that defines the connection endpoint for the temporary session in which the `Get-PSSession` command runs. The URI must be fully qualified.   This parameter configures the temporary ... |
| `-ContainerId` | `Object` | Yes | Specifies an array of IDs of containers. This cmdlet starts an interactive session with each of the specified containers. Use the `docker ps` command to get a list of container IDs. For more inform... |
| `-Credential` | `Object` | No | Specifies a user credential. This cmdlet runs the command with the permissions of the specified user. Specify a user account that has permission to connect to the remote computer and run a `Get-PSS... |
| `-Id` | `Object` | Yes | Specifies an array of session IDs. This cmdlet gets only the sessions with the specified IDs. Type one or more IDs, separated by commas, or use the range operator (`..`) to specify a range of IDs. ... |
| `-InstanceId` | `Object` | Yes | Specifies an array of instance IDs of sessions. This cmdlet gets only the sessions with the specified instance IDs.   The instance ID is a GUID that uniquely identifies a session on a local or remo... |
| `-Name` | `Object` | No | Specifies an array of session names. This cmdlet gets only the sessions that have the specified friendly names. Wildcard characters are permitted.   The friendly name of a session is stored in the ... |
| `-Port` | `Object` | No | Specifies the specified network port that is used for the temporary connection in which the `Get-PSSession` command runs. To connect to a remote computer, the remote computer must be listening on t... |
| `-SessionOption` | `Object` | No | Specifies advanced options for the session. Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session op... |
| `-State` | `Object` | No | Specifies a session state. This cmdlet gets only sessions in the specified state. The acceptable values for this parameter are: `All`, `Opened`, `Disconnected`, `Closed`, and `Broken`. The default ... |
| `-ThrottleLimit` | `Object` | No | Specifies the maximum number of concurrent connections that can be established to run the `Get-PSSession` command. If you omit this parameter or enter a value of `0` (zero), the default value, `32`... |
| `-UseSSL` | `Object` | No | Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish the connection in which the `Get-PSSession` command runs. By default, SSL is not used. If you use this parameter... |
| `-VMId` | `Object` | Yes | Specifies an array of ID of virtual machines. This cmdlet starts an interactive session with each of the specified virtual machines. To see the virtual machines that are available to you, use the f... |
| `-VMName` | `Object` | Yes | Specifies an array of names of virtual machines. This cmdlet starts an interactive session with each of the specified virtual machines. To see the virtual machines that are available to you, use th... |

---

### Get-PSSubsystem

Retrieves information about the subsystems registered in PowerShell.

**Returns**: `System.Management.Automation.Subsystem.SubsystemInfo`

```
Get-PSSubsystem
    -Kind <Object>
    -SubsystemType <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Kind` | `Object` | Yes | Specifies the kind of subsystem to be returned. Valid values are: `CommandPredictor`. |
| `-SubsystemType` | `Object` | Yes | Specifies the type of subsystem to be returned. |

---

### Import-Module

Adds modules to the current session.

The `Import-Module` cmdlet adds one or more modules to the current session. Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module. However, you can still use the `Import-Module` command to import a module. You can disable automatic module importing using the `$PSModuleAutoLoadingPreference` preference variable. For more information about the `$PSModuleAutoLoadingPreference` variable, see [about_Preference_V...

**Returns**: `None`

```
Import-Module
    [-Alias <Object>]
    [-ArgumentList <Object>]
    [-AsCustomObject <Object>]
    -Assembly <Object>
    [-CimNamespace <Object>]
    [-CimResourceUri <Object>]
    -CimSession <Object>
    [-Cmdlet <Object>]
    [-DisableNameChecking <Object>]
    [-Force <Object>]
    -FullyQualifiedName <Object>
    [-Function <Object>]
    [-Global <Object>]
    [-MaximumVersion <Object>]
    [-MinimumVersion <Object>]
    -ModuleInfo <Object>
    -Name <Object>
    [-NoClobber <Object>]
    [-PassThru <Object>]
    [-Prefix <Object>]
    -PSSession <Object>
    [-RequiredVersion <Object>]
    [-Scope <Object>]
    [-SkipEditionCheck <Object>]
    -UseWindowsPowerShell <Object>
    [-Variable <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Alias` | `Object` | No | Specifies the aliases that this cmdlet imports from the module into the current session. Enter a comma-separated list of aliases. Wildcard characters are permitted.   Some modules automatically exp... |
| `-ArgumentList` | `Object` | No | Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command. This parameter is valid only when you're importing a script module.   Yo... |
| `-AsCustomObject` | `Object` | No | Indicates that this cmdlet returns a custom object with members that represent the imported module members. This parameter is valid only for script modules.   When you use the **AsCustomObject** pa... |
| `-Assembly` | `Object` | Yes | Specifies an array of assembly objects. This cmdlet imports the cmdlets and providers implemented in the specified assembly objects. Enter a variable that contains assembly objects or a command tha... |
| `-CimNamespace` | `Object` | No | Specifies the namespace of an alternate CIM provider that exposes CIM modules. The default value is the namespace of the Module Discovery WMI provider.   Use this parameter to import CIM modules fr... |
| `-CimResourceUri` | `Object` | No | Specifies an alternate location for CIM modules. The default value is the resource URI of the Module Discovery WMI provider on the remote computer.   Use this parameter to import CIM modules from c... |
| `-CimSession` | `Object` | Yes | Specifies a CIM session on the remote computer. Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) co... |
| `-Cmdlet` | `Object` | No | Specifies an array of cmdlets that this cmdlet imports from the module into the current session. Wildcard characters are permitted.   Some modules automatically export selected cmdlets into your se... |
| `-DisableNameChecking` | `Object` | No | Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.   By default, when a module t... |
| `-Force` | `Object` | No | This parameter causes a module to be loaded, or reloaded, over top of the current one. Some modules load external assemblies. The import fails if you are importing a module that loads a newer versi... |
| `-FullyQualifiedName` | `Object` | Yes | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-Function` | `Object` | No | Specifies an array of functions that this cmdlet imports from the module into the current session. Wildcard characters are permitted. Some modules automatically export selected functions into your ... |
| `-Global` | `Object` | No | Indicates that this cmdlet imports modules into the global session state so they're available to all commands in the session.   By default, when `Import-Module` cmdlet is called from the command pr... |
| `-MaximumVersion` | `Object` | No | Specifies a maximum version. This cmdlet imports only a version of the module that's less than or equal to the specified value. If no version qualifies, `Import-Module` returns an error. |
| `-MinimumVersion` | `Object` | No | Specifies a minimum version. This cmdlet imports only a version of the module that's greater than or equal to the specified value. Use the **MinimumVersion** parameter name or its alias, **Version*... |
| `-ModuleInfo` | `Object` | Yes | Specifies an array of module objects to import. Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailab... |
| `-Name` | `Object` | Yes | Specifies the names of the modules to import. Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file. File paths are optional. Wildcard... |
| `-NoClobber` | `Object` | No | Prevents importing commands that have the same names as existing commands in the current session. By default, `Import-Module` imports all exported module commands.   Commands that have the same nam... |
| `-PassThru` | `Object` | No | Returns an object representing the imported module. By default, this cmdlet doesn't generate any output. |
| `-Prefix` | `Object` | No | Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.   Use this parameter to avoid name conflicts that might occur when different members in the session ha... |
| `-PSSession` | `Object` | Yes | Specifies a PowerShell user-managed session (**PSSession**) from which this cmdlet imports modules into the current session. Enter a variable that contains a **PSSession** or a command that gets a ... |
| `-RequiredVersion` | `Object` | No | Specifies a version of the module that this cmdlet imports. If the version isn't installed, `Import-Module` generates an error.   By default, `Import-Module` imports the module without checking the... |
| `-Scope` | `Object` | No | Specifies a scope to import the module in.   The acceptable values for this parameter are:   - **Global**. Available to all commands in the session. Equivalent to the **Global** parameter. - **Loca... |
| `-SkipEditionCheck` | `Object` | No | Skips the check on the `CompatiblePSEditions` field.   Allows loading a module from the `"$($Env:windir)\System32\WindowsPowerShell\v1.0\Modules"` module directory into PowerShell Core when that mo... |
| `-UseWindowsPowerShell` | `Object` | Yes | Loads module using Windows PowerShell Compatibility functionality. See [about_Windows_PowerShell_Compatibility](About/about_Windows_PowerShell_Compatibility.md) for more information. |
| `-Variable` | `Object` | No | Specifies an array of variables that this cmdlet imports from the module into the current session. Enter a list of variables. Wildcard characters are permitted.   Some modules automatically export ... |

**Patterns & Best Practices:**

**Patterns & Best Practices:**

Since PS 3.0, modules are auto-imported when you call an exported command. No `Import-Module` needed if:
1. The module is in `$PSModulePath`.
2. The manifest has **explicit** `FunctionsToExport` (not `'*'`).

```powershell
Get-Widget  # PS finds this in MyModule, auto-imports, runs it
```


**Patterns & Best Practices:**

```powershell
Install-Module 'Pester' -RequiredVersion 4.10.1 -Scope CurrentUser
Install-Module 'Pester' -RequiredVersion 5.6.1 -Scope CurrentUser

Import-Module 'Pester' -RequiredVersion 5.6.1

Import-Module 'Pester'
```


**Patterns & Best Practices:**

```powershell
Import-Module MyModule -Force     # Reimport (removes and reloads; useful in dev)
Import-Module MyModule -PassThru  # Returns module info object
Import-Module MyModule -DisableNameChecking  # Suppress non-standard verb warnings
```


**Patterns & Best Practices:**

```powershell
. ./helpers.ps1
Invoke-HelperFunction   # Available directly

./helpers.ps1

Import-Module ./MyModule.psm1
Remove-Module MyModule; Import-Module ./MyModule.psm1 -Force  # Reload
```

| Aspect | Dot-Source | Module Import |
|--------|-----------|---------------|
| Scope | Caller's scope | Isolated module scope |
| Variables | Leak into caller | Encapsulated |
| Functions | All visible | Only exported |
| Use case | Script helpers | Reusable libraries |


### Case-Sensitive Filesystem

```powershell
Test-Path ./README.md      # True
Test-Path ./readme.md      # FALSE on Linux — different file!

Import-Module ./MyModule.psm1     # Works
Import-Module ./mymodule.psm1     # FAILS if file is MyModule.psm1

$ht = @{}; $ht['Key'] = 1; $ht['key']   # Returns 1
```

### File Permissions

```powershell
if (-not $IsWindows) {
    & chmod 755 ./script.sh
    & chmod 600 ./secrets.conf
    & chown 'user:group' ./file.txt
}
```

### Configuration File Locations

```powershell
$PROFILE

$env:PSModulePath -split [IO.Path]::PathSeparator
```

### Systemd Integration

```powershell
if ($IsLinux) {
    & systemctl is-active --quiet nginx
    if ($LASTEXITCODE -eq 0) { Write-Host "nginx is running" }
}
```

---


---

### Invoke-Command

Runs commands on local and remote computers.

The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors. Using a single `Invoke-Command` command, you can run commands on multiple computers.

**Returns**: `System.Management.Automation.PSRemotingJob`

```
Invoke-Command
    [-AllowRedirection <Object>]
    [-ApplicationName <Object>]
    [-ArgumentList <Object>]
    [-AsJob <Object>]
    [-Authentication <Object>]
    [-CertificateThumbprint <Object>]
    [-ComputerName <Object>]
    [-ConfigurationName <Object>]
    [-ConnectingTimeout <Object>]
    [-ConnectionUri <Object>]
    -ContainerId <Object>
    -Credential <Object>
    [-EnableNetworkAccess <Object>]
    -FilePath <Object>
    [-HideComputerName <Object>]
    -HostName <Object>
    [-InDisconnectedSession <Object>]
    [-InputObject <Object>]
    [-JobName <Object>]
    [-KeyFilePath <Object>]
    [-NoNewScope <Object>]
    [-Options <Object>]
    [-Port <Object>]
    [-RemoteDebug <Object>]
    [-RunAsAdministrator <Object>]
    -ScriptBlock <Object>
    [-Session <Object>]
    [-SessionName <Object>]
    [-SessionOption <Object>]
    -SSHConnection <Object>
    [-SSHTransport <Object>]
    [-Subsystem <Object>]
    [-ThrottleLimit <Object>]
    [-UserName <Object>]
    [-UseSSL <Object>]
    -VMId <Object>
    -VMName <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowRedirection` | `Object` | No | Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).   When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect... |
| `-ApplicationName` | `Object` | No | Specifies the application name segment of the connection URI. Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.   The default ... |
| `-ArgumentList` | `Object` | No | Supplies the values of parameters for the scriptblock. The parameters in the scriptblock are passed by position from the array value supplied to **ArgumentList**. This is known as array splatting. ... |
| `-AsJob` | `Object` | No | Indicates that this cmdlet runs the command as a background job on a remote computer. Use this parameter to run commands that take an extensive time to finish.   When you use the **AsJob** paramete... |
| `-Authentication` | `Object` | No | Specifies the mechanism that's used to authenticate the user's credentials. CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operati... |
| `-CertificateThumbprint` | `Object` | No | Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session. Enter the certificate thumbprint of the certificate.   Certificates... |
| `-ComputerName` | `Object` | No | Specifies the computers on which the command runs. The default is the local computer.   When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to ru... |
| `-ConfigurationName` | `Object` | No | Specifies the session configuration that is used for the new **PSSession**.   Enter a configuration name or the fully qualified resource URI for a session configuration. If you specify only the con... |
| `-ConnectingTimeout` | `Object` | No | Specifies the amount of time in milliseconds allowed for the initial SSH connection to complete. If the connection doesn't complete within the specified time, an error is returned.   This parameter... |
| `-ConnectionUri` | `Object` | No | Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session. The URI must be fully qualified.   The format of this string is as follows:   `<Transport>://<Comp... |
| `-ContainerId` | `Object` | Yes | Specifies an array of container IDs. |
| `-Credential` | `Object` | Yes | Specifies a user account that has permission to perform this action. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** obje... |
| `-EnableNetworkAccess` | `Object` | No | Indicates that this cmdlet adds an interactive security token to loopback sessions. The interactive token lets you run commands in the loopback session that get data from other computers. For examp... |
| `-FilePath` | `Object` | Yes | Specifies a local script that this cmdlet runs on one or more remote computers. Enter the path and filename of the script, or pipe a script path to `Invoke-Command`. The script must exist on the lo... |
| `-HideComputerName` | `Object` | No | Indicates that this cmdlet omits the computer name of each object from the output display. By default, the name of the computer that generated the object appears in the display.   This parameter af... |
| `-HostName` | `Object` | Yes | Specifies an array of computer names for a Secure Shell (SSH) based connection. This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH... |
| `-InDisconnectedSession` | `Object` | No | Indicates that this cmdlet runs a command or script in a disconnected session.   When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote c... |
| `-InputObject` | `Object` | No | Specifies input to the command. Enter a variable that contains the objects or type a command or expression that gets the objects.   When using the **InputObject** parameter, use the `$input` automa... |
| `-JobName` | `Object` | No | Specifies a friendly name for the background job. By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.   If you use the **JobName** parameter in a command, the command is run as a... |
| `-KeyFilePath` | `Object` | No | Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.   SSH allows user authentication to be performed via private and public keys as an alternative to b... |
| `-NoNewScope` | `Object` | No | Indicates that this cmdlet runs the specified command in the current scope. By default, `Invoke-Command` runs commands in their own scope.   This parameter is valid only in commands that are run in... |
| `-Options` | `Object` | No | Specifies a hashtable of SSH options used when connecting to a remote SSH-based session. The possible options are any values supported by the Unix-based version of the [ssh](https://man.openbsd.org... |
| `-Port` | `Object` | No | Specifies the network port on the remote computer that is used for this command. To connect to a remote computer, the remote computer must be listening on the port that the connection uses. The def... |
| `-RemoteDebug` | `Object` | No | Used to run the invoked command in debug mode in the remote PowerShell session. |
| `-RunAsAdministrator` | `Object` | No | Indicates that this cmdlet invokes a command as an Administrator. |
| `-ScriptBlock` | `Object` | Yes | Specifies the commands to run. Enclose the commands in braces (`{}`) to create a scriptblock. When using `Invoke-Command` to run a command remotely, any variables in the command are evaluated on th... |
| `-Session` | `Object` | No | Specifies an array of sessions in which this cmdlet runs the command. Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `Ne... |
| `-SessionName` | `Object` | No | Specifies a friendly name for a disconnected session. You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command. This parameter is valid only with the *... |
| `-SessionOption` | `Object` | No | Specifies advanced options for the session. Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session optio... |
| `-SSHConnection` | `Object` | Yes | This parameter takes an array of hash tables where each hash table contains one or more connection parameters needed to establish a Secure Shell (SSH) connection. The **SSHConnection** parameter is... |
| `-SSHTransport` | `Object` | No | Indicates that the remote connection is established using Secure Shell (SSH).   By default PowerShell uses Windows WinRM to connect to a remote computer. This switch forces PowerShell to use the **... |
| `-Subsystem` | `Object` | No | Specifies the SSH subsystem used for the new **PSSession**.   This specifies the subsystem to use on the target as defined in sshd_config. The subsystem starts a specific version of PowerShell with... |
| `-ThrottleLimit` | `Object` | No | Specifies the maximum number of concurrent connections that can be established to run this command. If you omit this parameter or enter a value of 0, the default value, 32, is used.   The throttle ... |
| `-UserName` | `Object` | No | Specifies the username for the account used to run a command on the remote computer. The user authentication method depends on how Secure Shell (SSH) is configured on the remote computer.   If SSH ... |
| `-UseSSL` | `Object` | No | Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer. By default, SSL isn't used.   WS-Management encrypts all PowerShell content... |
| `-VMId` | `Object` | Yes | Specifies an array of IDs of virtual machines. |
| `-VMName` | `Object` | Yes | Specifies an array of names of virtual machines. |

**Patterns & Best Practices:**

**Patterns & Best Practices:**

**Patterns & Best Practices:**

Runs in the **same process** in a separate runspace. Bundled with PS 7.5.

```powershell
$job = Start-ThreadJob -ScriptBlock {
    param($Path, $Filter)
    Get-ChildItem -Path $Path -Filter $Filter -Recurse
} -ArgumentList '/var/log', '*.log'

$results = Receive-Job $job -Wait -AutoRemoveJob
```

Both `-ArgumentList` with `param()` and `$using:` work with `Start-ThreadJob`.

**Patterns & Best Practices:**

**Remote objects are deserialized snapshots.** Objects crossing a remoting boundary are serialized to CLIXML and deserialized on the other side. The result is a property bag — **all methods are gone**, only properties survive. The type gains a `Deserialized.` prefix (e.g., `Deserialized.System.Diagnostics.Process`).

```powershell
$svc = Invoke-Command -HostName server1 -ScriptBlock { Get-Service wuauserv }
$svc.Stop()  # ERROR: Method invocation failed

Invoke-Command -HostName server1 -ScriptBlock { Stop-Service wuauserv }
```


**Patterns & Best Practices:**

```powershell
Invoke-Command -ComputerName server1 -ScriptBlock { Get-Process | Where-Object CPU -gt 100 }

Invoke-Command -HostName server1 -ScriptBlock { Get-Process | Where-Object CPU -gt 100 }
```

`-ComputerName` = WinRM (port 5985/5986). `-HostName` = SSH (port 22). **Mutually exclusive.**

**Patterns & Best Practices:**

Default depth is **2**. Nested objects beyond that become `.ToString()` strings.

**Types that survive:** `[string]`, `[int]`, `[long]`, `[double]`, `[decimal]`, `[bool]`, `[DateTime]`, `[TimeSpan]`, `[Guid]`, `[Uri]`, `[Version]`, `[byte[]]`, `[PSCustomObject]`, `[hashtable]`, `[array]` (becomes `[object[]]`).

**Types that do NOT survive:** Any .NET object with methods (becomes `Deserialized.*`), `[ScriptBlock]`, `[SecureString]` (only WinRM+CredSSP), file handles, connections.

```powershell
$remote_proc = Invoke-Command -HostName server1 -ScriptBlock { Get-Process pwsh }
$remote_proc.GetType().FullName  # System.Management.Automation.PSObject (NOT Process)
```


**Patterns & Best Practices:**

| Task | Command |
|------|---------|
| Remote command (SSH) | `Invoke-Command -HostName host -ScriptBlock { ... }` |
| Remote command (WinRM) | `Invoke-Command -ComputerName host -ScriptBlock { ... }` |
| Persistent session | `New-PSSession -HostName host` |
| Interactive session | `Enter-PSSession -HostName host` |
| Import remote cmds | `Import-PSSession -Session $s -Module Mod` |
| Fan-out | `Invoke-Command -HostName h1,h2,h3 -ScriptBlock { ... }` |
| Background job | `Invoke-Command -HostName host -ScriptBlock { ... } -AsJob` |
| Pass local variable | `$using:varName` inside ScriptBlock |
| Limit concurrency | `-ThrottleLimit 5` |


### Passing Arguments

```powershell
Invoke-Command -HostName server1 -ScriptBlock {
    param($Name, $Threshold)
    Get-Process -Name $Name | Where-Object CPU -gt $Threshold
} -ArgumentList 'pwsh', 50

$processName = 'pwsh'
$threshold = 50
Invoke-Command -HostName server1 -ScriptBlock {
    Get-Process -Name $using:processName | Where-Object CPU -gt $using:threshold
}
```

### Fan-Out and Throttling

```powershell
$servers = 'web01', 'web02', 'web03', 'db01'

Invoke-Command -HostName $servers -ScriptBlock {
    [PSCustomObject]@{ Host = $env:COMPUTERNAME; Uptime = (Get-Uptime).TotalHours }
}

Invoke-Command -HostName $servers -ThrottleLimit 5 -ScriptBlock { }
```

Results include `PSComputerName` so you know which host returned what.

### Credentials

```powershell
Invoke-Command -ComputerName server1 -Credential (Get-Credential) -ScriptBlock { whoami }

Invoke-Command -HostName server1 -UserName admin -KeyFilePath ~/.ssh/id_ed25519 -ScriptBlock { whoami }
```


### Multiple ThreadJobs

```powershell
$jobs = foreach ($server in 'web01', 'web02', 'db01') {
    Start-ThreadJob -ScriptBlock {
        Invoke-Command -HostName $using:server -ScriptBlock { Get-Uptime }
    }
}
$results = $jobs | Receive-Job -Wait -AutoRemoveJob
```


### 1. Using `==` instead of `-eq`
```powershell
if ($name == 'admin') { }   # WRONG — not valid PowerShell
if ($name -eq 'admin') { }  # CORRECT
```

### 2. Forgetting `-eq` is case-insensitive
```powershell
'Hello' -eq 'hello'    # $true (surprise!)
'Hello' -ceq 'hello'   # $false (case-sensitive)
```

### 3. All uncaptured output goes to pipeline
```powershell
function Broken {
    'leaked'                           # Output 1
    $list = [System.Collections.ArrayList]::new()
    $list.Add(42)                      # .Add() returns index 0 — Output 2!
    return 'done'                      # Output 3
}
function Fixed {
    [void]$list.Add(42)   # Suppressed
    return 'done'         # Only output
}
```

### 4. `-contains` is not substring check
```powershell
'hello world' -contains 'hello'        # $false! (not a collection)
@('hello', 'world') -contains 'hello'  # $true (collection membership)
'hello world' -match 'hello'           # $true (substring/regex)
```

### 5. Missing `$using:` in remote/parallel
```powershell
$name = 'svchost'
Invoke-Command -ComputerName S1 -ScriptBlock { Get-Process $name }         # $name is $null!
Invoke-Command -ComputerName S1 -ScriptBlock { Get-Process $using:name }   # CORRECT
```

### 6. Backtick line continuation (fragile)
```powershell
Get-Process | `
    Where-Object CPU -gt 100
Get-Process |
    Where-Object CPU -gt 100
```

### 7. Array `+=` is O(n) per append
```powershell
$arr = @(); foreach ($i in 1..10000) { $arr += $i }
$list = [System.Collections.Generic.List[object]]::new()
foreach ($i in 1..10000) { $list.Add($i) }
$arr = foreach ($i in 1..10000) { $i }
```

### 8. Single-element array unwrapping
```powershell
$r = @('only-one')
$r.GetType().Name        # String — unwrapped!
$r = @(Get-ChildItem *.log)   # Force array with @()
[array]$r = Get-ChildItem *.log  # Or type-constrain
```

### 9. Hashtable key order in [pscustomobject]
```powershell
[pscustomobject]@{ Z = 1; A = 2; M = 3 }
[pscustomobject][ordered]@{ Z = 1; A = 2; M = 3 }
```


### Scope Modifiers

| Modifier | Description |
|---|---|
| `$local:var` | Current scope only (default for new variables) |
| `$script:var` | Visible to entire .ps1 file |
| `$global:var` | Visible to entire session |
| `$private:var` | Current scope, invisible to child scopes |
| `$using:var` | Pass local variable into remote/parallel scope |

**Key rule**: Child scopes READ parent variables, but WRITING creates a local copy unless you use a scope modifier.

```powershell
$script:counter = 0
function Increment { $script:counter++ }

$threshold = 100
Invoke-Command -ComputerName Server1 -ScriptBlock {
    Get-Process | Where-Object { $_.WorkingSet64 -gt $using:threshold }
}
$prefix = 'LOG'
1..10 | ForEach-Object -Parallel { "$($using:prefix): Processing $_" }
```


---

### Invoke-History

Runs commands from the session history.

The `Invoke-History` cmdlet runs commands from the session history. You can pass objects representing the commands from Get-History to `Invoke-History`, or you can identify commands in the current history by using their **Id** number. To find the identification number of a command, use the `Get-History` cmdlet.

**Returns**: `None`

```
Invoke-History
    [-Confirm <Object>]
    [-Id <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | No | Specifies the **Id** of a command in the history. You can type the **Id** number of the command or the first few characters of the command.   If you type characters, `Invoke-History` matches the mo... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### New-Module

Creates a new dynamic module that exists only in memory.

The `New-Module` cmdlet creates a dynamic module from a scriptblock. The members of the dynamic module, such as functions and variables, are immediately available in the session and remain available until you close the session.

**Returns**: `System.Management.Automation.PSModuleInfo`

```
New-Module
    [-ArgumentList <Object>]
    [-AsCustomObject <Object>]
    [-Cmdlet <Object>]
    [-Function <Object>]
    -Name <Object>
    [-ReturnResult <Object>]
    -ScriptBlock <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object` | No | Specifies an array of arguments which are parameter values that are passed to the scriptblock. For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatti... |
| `-AsCustomObject` | `Object` | No | Indicates that this cmdlet returns a custom object that represents the dynamic module. The module members are implemented as script methods of the custom object, but they are not imported into the ... |
| `-Cmdlet` | `Object` | No | Specifies an array of cmdlets that this cmdlet exports from the module into the current session. Enter a comma-separated list of cmdlets. Wildcard characters are permitted. By default, all cmdlets ... |
| `-Function` | `Object` | No | Specifies an array of functions that this cmdlet exports from the module into the current session. Enter a comma-separated list of functions. Wildcard characters are permitted. By default, all func... |
| `-Name` | `Object` | Yes | Specifies a name for the new module. You can also pipe a module name to New-Module.   The default value is an autogenerated name that starts with `__DynamicModule_` and is followed by a GUID that s... |
| `-ReturnResult` | `Object` | No | Indicates that this cmdlet runs the scriptblock and returns the scriptblock results instead of returning a module object. |
| `-ScriptBlock` | `Object` | Yes | Specifies the contents of the dynamic module. Enclose the contents in braces (`{}`) to create a scriptblock. This parameter is required. |

**Patterns & Best Practices:**

| Type | Extension | Description |
|------|-----------|-------------|
| Script module | `.psm1` | PowerShell code; most common |
| Module manifest | `.psd1` | Metadata controlling exports; points to RootModule |
| Binary module | `.dll` | Compiled C# cmdlets |
| Dynamic module | (none) | Created at runtime with `New-Module`; not on disk |

A typical module ships as a manifest + script module pair: `MyModule.psd1` + `MyModule.psm1`.


---

### New-ModuleManifest

Creates a new module manifest.

The `New-ModuleManifest` cmdlet creates a new module manifest (`.psd1`) file, populates its values, and saves the manifest file in the specified path.

**Returns**: `None`

```
New-ModuleManifest
    [-AliasesToExport <Object>]
    [-Author <Object>]
    [-ClrVersion <Object>]
    [-CmdletsToExport <Object>]
    [-CompanyName <Object>]
    [-CompatiblePSEditions <Object>]
    [-Confirm <Object>]
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
    [-PassThru <Object>]
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
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AliasesToExport` | `Object` | No | Specifies the aliases that the module exports. Wildcards are permitted.   You can use this parameter to restrict the aliases that are exported by the module. It can remove aliases from the list of ... |
| `-Author` | `Object` | No | Specifies the module author.   If you omit this parameter, `New-ModuleManifest` creates an **Author** key with the name of the current user. |
| `-ClrVersion` | `Object` | No | Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.   > [!NOTE] > This setting is valid for the PowerShell Desktop edition o... |
| `-CmdletsToExport` | `Object` | No | Specifies the cmdlets that the module exports. Wildcards are permitted.   You can use this parameter to restrict the cmdlets that are exported by the module. It can remove cmdlets from the list of ... |
| `-CompanyName` | `Object` | No | Identifies the company or vendor who created the module.   If you omit this parameter, `New-ModuleManifest` creates a **CompanyName** key with a value of "Unknown". |
| `-CompatiblePSEditions` | `Object` | No | Specifies the module's compatible PSEditions. For information about PSEdition, see [Modules with compatible PowerShell Editions](/powershell/gallery/concepts/module-psedition-support). |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Copyright` | `Object` | No | Specifies a copyright statement for the module.   If you omit this parameter, `New-ModuleManifest` creates a **Copyright** key with a value of `(c) <year> <username>. All rights reserved.` where `<... |
| `-DefaultCommandPrefix` | `Object` | No | Specifies a prefix that is prepended to the nouns of all commands in the module when they're imported into a session. Enter a prefix string. Prefixes prevent command name conflicts in a user's sess... |
| `-Description` | `Object` | No | Describes the contents of the module. |
| `-DotNetFrameworkVersion` | `Object` | No | Specifies the minimum version of the Microsoft .NET Framework that the module requires.   > [!NOTE] > This setting is valid for the PowerShell Desktop edition only, such as Windows PowerShell 5.1, ... |
| `-DscResourcesToExport` | `Object` | No | Specifies the Desired State Configuration (DSC) resources that the module exports. Wildcards are permitted. |
| `-ExternalModuleDependencies` | `Object` | No | A list of external modules that this module is depends on. This list is only used to document the module's dependencies and is not enforced by PowerShell. It's not used by the PowerShellGet or PSRe... |
| `-FileList` | `Object` | No | Specifies all items that are included in the module.   This key is designed to act as a module inventory. The files listed in the key are included when the module is published, but any functions ar... |
| `-FormatsToProcess` | `Object` | No | Specifies the formatting files (`.ps1xml`) that run when the module is imported.   When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files. Because formatt... |
| `-FunctionsToExport` | `Object` | No | Specifies the functions that the module exports. Wildcards are permitted.   You can use this parameter to restrict the functions that are exported by the module. It can remove functions from the li... |
| `-Guid` | `Object` | No | Specifies a unique identifier for the module. The **GUID** can be used to distinguish among modules with the same name.   If you omit this parameter, `New-ModuleManifest` creates a **GUID** key in ... |
| `-HelpInfoUri` | `Object` | No | Specifies the internet address of the HelpInfo XML file for the module. Enter a Uniform Resource Identifier (URI) that begins with **http** or **https**.   The HelpInfo XML file supports the Updata... |
| `-IconUri` | `Object` | No | Specifies the URL of an icon for the module. The specified icon is displayed on the gallery web page for the module. |
| `-LicenseUri` | `Object` | No | Specifies the URL of licensing terms for the module. |
| `-ModuleList` | `Object` | No | Lists all modules that are included in this module.   Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys. The hash table can also have an optional ... |
| `-ModuleVersion` | `Object` | No | Specifies the module's version.   This parameter isn't required, but a **ModuleVersion** key is required in the manifest. If you omit this parameter, `New-ModuleManifest` creates a **ModuleVersion*... |
| `-NestedModules` | `Object` | No | Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state. The files in the **NestedModules** key run in the order in which they're listed in ... |
| `-PassThru` | `Object` | No | Writes the resulting module manifest to the console and creates a `.psd1` file. By default, this cmdlet doesn't generate any output. |
| `-Path` | `Object` | Yes | Specifies the path and file name of the new module manifest. Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`. The **Path** parameter ... |
| `-PowerShellHostName` | `Object` | No | Specifies the name of the PowerShell host program that the module requires. Enter the name of the host program, such as **Windows PowerShell ISE Host** or **ConsoleHost**. Wildcards aren't permitte... |
| `-PowerShellHostVersion` | `Object` | No | Specifies the minimum version of the PowerShell host program that works with the module. Enter a version number, such as 1.1. |
| `-PowerShellVersion` | `Object` | No | Specifies the minimum version of PowerShell that works with this module. For example, you can enter 1.0, 2.0, or 3.0 as the parameter's value. It must be in an X.X format. For example, if you submi... |
| `-Prerelease` | `Object` | No | Prerelease string of this module. Adding a Prerelease string identifies the module as a prerelease version. When the module is published to the PowerShell Gallery, this data is used to identify pre... |
| `-PrivateData` | `Object` | No | Specifies data that is passed to the module when it's imported. |
| `-ProcessorArchitecture` | `Object` | No | Specifies the processor architecture that the module requires. Valid values are x86, AMD64, IA64, MSIL, and None (unknown or unspecified). |
| `-ProjectUri` | `Object` | No | Specifies the URL of a web page about this project. |
| `-ReleaseNotes` | `Object` | No | Specifies release notes. |
| `-RequiredAssemblies` | `Object` | No | Specifies the assembly (`.dll`) files that the module requires. Enter the assembly file names. PowerShell loads the specified assemblies before updating types or formats, importing nested modules, ... |
| `-RequiredModules` | `Object` | No | Specifies modules that must be in the global session state. If the required modules aren't in the global session state, PowerShell imports them. If the required modules aren't available, the `Impor... |
| `-RequireLicenseAcceptance` | `Object` | No | Flag to indicate whether the module requires explicit user acceptance for install, update, or save. |
| `-RootModule` | `Object` | No | Specifies the primary or root file of the module. Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest(`.psd1`), an assembly (`.dll`), a cmdlet definition XML file... |
| `-ScriptsToProcess` | `Object` | No | Specifies script (`.ps1`) files that run in the caller's session state when the module is imported. You can use these scripts to prepare an environment, just as you might use a login script.   To s... |
| `-Tags` | `Object` | No | Specifies an array of tags. |
| `-TypesToProcess` | `Object` | No | Specifies the type files (`.ps1xml`) that run when the module is imported.   When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files. Because type files ar... |
| `-VariablesToExport` | `Object` | No | Specifies the variables that the module exports. Wildcards are permitted.   You can use this parameter to restrict the variables that are exported by the module. It can remove variables from the li... |
| `-WhatIf` | `Object` | No | Shows what would happen if `New-ModuleManifest` runs. The cmdlet isn't run. |

**Patterns & Best Practices:**

```powershell
New-ModuleManifest -Path ./MyModule/MyModule.psd1 `
    -RootModule 'MyModule.psm1' `
    -ModuleVersion '1.0.0' `
    -Author 'Your Name' `
    -Description 'What this module does' `
    -FunctionsToExport @('Get-Widget', 'Set-Widget', 'Remove-Widget') `
    -CmdletsToExport @() `
    -VariablesToExport @() `
    -AliasesToExport @()
```

### Critical Manifest Fields

| Field | Purpose | Rule |
|-------|---------|------|
| `RootModule` | .psm1 or .dll to load | Required for code modules |
| `ModuleVersion` | Semantic version | Required for PSGallery |
| `FunctionsToExport` | Visible functions | **Explicit list, never `'*'`** |
| `CmdletsToExport` | Visible cmdlets | `@()` if none |
| `VariablesToExport` | Visible variables | `@()` — almost never export |
| `AliasesToExport` | Visible aliases | Explicit list or `@()` |
| `RequiredModules` | Dependencies loaded first | Array of names or specs |
| `NestedModules` | Sub-modules loaded into module scope | Different from RequiredModules |
| `PrivateData.PSData` | PSGallery metadata | Tags, LicenseUri, ProjectUri |

**Why explicit lists matter:** With `FunctionsToExport = '*'`, PowerShell must **load the entire module** to discover commands. With an explicit list, it reads only the manifest, making tab completion and autoloading dramatically faster.


---

### New-PSRoleCapabilityFile

Creates a file that defines a set of capabilities to be exposed through a session configuration.

The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files. This includes determining which cmdlets, functions, and scripts are available to users. The capability file is a human-readable text file that contains a hash table of session configuration properties and values. The file has a `.psrc` file name extension, and can be used by more than one session configuration.

**Returns**: `None documented`

```
New-PSRoleCapabilityFile
    [-AliasDefinitions <Object>]
    [-AssembliesToLoad <Object>]
    [-Author <Object>]
    [-CompanyName <Object>]
    [-Copyright <Object>]
    [-Description <Object>]
    [-EnvironmentVariables <Object>]
    [-FormatsToProcess <Object>]
    [-FunctionDefinitions <Object>]
    [-Guid <Object>]
    [-ModulesToImport <Object>]
    -Path <Object>
    [-ScriptsToProcess <Object>]
    [-TypesToProcess <Object>]
    [-VariableDefinitions <Object>]
    [-VisibleAliases <Object>]
    [-VisibleCmdlets <Object>]
    [-VisibleExternalCommands <Object>]
    [-VisibleFunctions <Object>]
    [-VisibleProviders <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AliasDefinitions` | `Object` | No | Adds the specified aliases to sessions that use the role capability file. Enter a hash table with the following keys:   - Name. Name of the alias. This key is required. - Value. The command that th... |
| `-AssembliesToLoad` | `Object` | No | Specifies the assemblies to load into the sessions that use the role capability file. |
| `-Author` | `Object` | No | Specifies the user that created the role capability file. |
| `-CompanyName` | `Object` | No | Identifies the company that created the role capability file. The default value is Unknown. |
| `-Copyright` | `Object` | No | Specifies a copyright for the role capability file. If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement using the value of the **Author** parameter. |
| `-Description` | `Object` | No | Specifies a description for the role capability file. |
| `-EnvironmentVariables` | `Object` | No | Specifies the environment variables for sessions that expose this role capability file. Enter a hash table in which the keys are the environment variable names and the values are the environment va... |
| `-FormatsToProcess` | `Object` | No | Specifies the formatting files (`.ps1xml`) that run in sessions that use the role capability file. The value of this parameter must be a full or absolute path of the formatting files. |
| `-FunctionDefinitions` | `Object` | No | Adds the specified functions to sessions that expose the role capability. Enter a hash table with the following keys:   - Name. Name of the function. This key is required. - ScriptBlock. Function b... |
| `-Guid` | `Object` | No | Specifies a unique identifier for the role capability file. If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file. To create a new GUID in PowerShell, type `[guid]::N... |
| `-ModulesToImport` | `Object` | No | Specifies the modules that are automatically imported into sessions that use the role capability file. By default, all the commands in listed modules are visible. When used with **VisibleCmdlets** ... |
| `-Path` | `Object` | Yes | Specifies the path and filename of the role capability file. The file must have a `.psrc` filename extension. |
| `-ScriptsToProcess` | `Object` | No | Specifies scripts to add to sessions that use the role capability file. Enter the path and file names of the scripts. The value of this parameter must be a full or absolute path of the script file ... |
| `-TypesToProcess` | `Object` | No | Specifies type files (`.ps1xml`) to add to sessions that use the role capability file. Enter the type filenames. The value of this parameter must be a full or absolute path of the type filenames. |
| `-VariableDefinitions` | `Object` | No | Specifies variables to add to sessions that use the role capability file. Enter a hash table with the following keys:   - Name. Name of the variable. This key is required. - Value. Variable value. ... |
| `-VisibleAliases` | `Object` | No | Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter. Wildcard characters are supported... |
| `-VisibleCmdlets` | `Object` | No | Limits the cmdlets in the session to those specified in the value of this parameter. Wildcard characters and Module Qualified Names are supported.   By default, all cmdlets that the modules in the ... |
| `-VisibleExternalCommands` | `Object` | No | Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.   By default, no external commands are visible in this sess... |
| `-VisibleFunctions` | `Object` | No | Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter. Wildcard characters are supported... |
| `-VisibleProviders` | `Object` | No | Limits the PowerShell providers in the session to those specified in the value of this parameter. Wildcard characters are supported.   By default, all providers exported by a module in the session ... |

---

### New-PSSession

Creates a persistent connection to a local or remote computer.

The `New-PSSession` cmdlet creates a PowerShell session (**PSSession**) on a local or remote computer. When you create a **PSSession**, PowerShell establishes a persistent connection to the remote computer.

**Returns**: `System.Management.Automation.Runspaces.PSSession`

```
New-PSSession
    [-AllowRedirection <Object>]
    [-ApplicationName <Object>]
    [-Authentication <Object>]
    [-CertificateThumbprint <Object>]
    [-ComputerName <Object>]
    [-ConfigurationName <Object>]
    [-ConnectingTimeout <Object>]
    -ConnectionUri <Object>
    -ContainerId <Object>
    -Credential <Object>
    [-EnableNetworkAccess <Object>]
    -HostName <Object>
    [-KeyFilePath <Object>]
    [-Name <Object>]
    [-Options <Object>]
    [-Port <Object>]
    [-RunAsAdministrator <Object>]
    [-Session <Object>]
    [-SessionOption <Object>]
    -SSHConnection <Object>
    [-SSHTransport <Object>]
    [-Subsystem <Object>]
    [-ThrottleLimit <Object>]
    [-UserName <Object>]
    [-UseSSL <Object>]
    -UseWindowsPowerShell <Object>
    -VMId <Object>
    -VMName <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowRedirection` | `Object` | No | Indicates that this cmdlet allows redirection of this connection to an alternate Uniform Resource Identifier (URI).   When you use the **ConnectionURI** parameter, the remote destination can return... |
| `-ApplicationName` | `Object` | No | Specifies the application name segment of the connection URI. Use this parameter to specify the application name when you are not using the **ConnectionURI** parameter in the command.   The default... |
| `-Authentication` | `Object` | No | Specifies the mechanism that is used to authenticate the user's credentials. The acceptable values for this parameter are:   - `Default` - `Basic` - `Credssp` - `Digest` - `Kerberos` - `Negotiate` ... |
| `-CertificateThumbprint` | `Object` | No | Specifies the digital public key certificate (X509) of a user account that has permission to perform this action. Enter the certificate thumbprint of the certificate.   Certificates are used in cli... |
| `-ComputerName` | `Object` | No | Specifies an array of names of computers. This cmdlet creates a persistent connection (**PSSession**) to the specified computer. If you enter multiple computer names, `New-PSSession` creates multip... |
| `-ConfigurationName` | `Object` | No | Specifies the session configuration that is used for the new **PSSession**.   Enter a configuration name or the fully qualified resource URI for a session configuration. If you specify only the con... |
| `-ConnectingTimeout` | `Object` | No | Specifies the amount of time in milliseconds allowed for the initial SSH connection to complete. If the connection doesn't complete within the specified time, an error is returned.   This parameter... |
| `-ConnectionUri` | `Object` | Yes | Specifies a URI that defines the connection endpoint for the session. The URI must be fully qualified. The format of this string is as follows:   `<Transport>://<ComputerName>:<Port>/<ApplicationNa... |
| `-ContainerId` | `Object` | Yes | Specifies an array of IDs of containers. This cmdlet starts an interactive session with each of the specified containers. Use the `docker ps` command to get a list of container IDs. For more inform... |
| `-Credential` | `Object` | Yes | Specifies a user account that has permission to do this action. The default is the current user.   Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object genera... |
| `-EnableNetworkAccess` | `Object` | No | Indicates that this cmdlet adds an interactive security token to loopback sessions. The interactive token lets you run commands in the loopback session that get data from other computers. For examp... |
| `-HostName` | `Object` | Yes | Specifies an array of computer names for a Secure Shell (SSH) based connection. This is similar to the **ComputerName** parameter except that the connection to the remote computer is made using SSH... |
| `-KeyFilePath` | `Object` | No | Specifies a key file path used by Secure Shell (SSH) to authenticate a user on a remote computer.   SSH allows user authentication to be performed via private/public keys as an alternative to basic... |
| `-Name` | `Object` | No | Specifies a friendly name for the **PSSession**.   You can use the name to refer to the **PSSession** when you use other cmdlets, such as `Get-PSSession` and `Enter-PSSession`. The name is not requ... |
| `-Options` | `Object` | No | Specifies a hashtable of SSH options used when connecting to a remote SSH-based session. The possible options are any values supported by the Unix-based version of the [ssh](https://man.openbsd.org... |
| `-Port` | `Object` | No | Specifies the network port on the remote computer that is used for this connection. To connect to a remote computer, the remote computer must be listening on the port that the connection uses. The ... |
| `-RunAsAdministrator` | `Object` | No | Indicates that the **PSSession** runs as administrator. |
| `-Session` | `Object` | No | Specifies an array of **PSSession** objects that this cmdlet uses as a model for the new **PSSession**. This parameter creates new **PSSession** objects that have the same properties as the specifi... |
| `-SessionOption` | `Object` | No | Specifies advanced options for the session. Enter a **SessionOption** object, such as one that you create by using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session op... |
| `-SSHConnection` | `Object` | Yes | This parameter takes an array of hashtables where each hashtable contains one or more connection parameters needed to establish a Secure Shell (SSH) connection (**HostName**, **Port**, **UserName**... |
| `-SSHTransport` | `Object` | No | Indicates that the remote connection is established using Secure Shell (SSH).   By default PowerShell uses Windows WinRM to connect to a remote computer. This switch forces PowerShell to use the Ho... |
| `-Subsystem` | `Object` | No | Specifies the SSH subsystem used for the new **PSSession**.   This specifies the subsystem to use on the target as defined in `sshd_config`. The subsystem starts a specific version of PowerShell wi... |
| `-ThrottleLimit` | `Object` | No | Specifies the maximum number of concurrent connections that can be established to run this command. If you omit this parameter or enter a value of `0` (zero), the default value, `32`, is used.   Th... |
| `-UserName` | `Object` | No | Specifies the user name for the account used to create a session on the remote computer. If the **UserName** parameter isn't specified then the current logged on username is used. User authenticati... |
| `-UseSSL` | `Object` | No | Indicates that this cmdlet uses the SSL protocol to establish a connection to the remote computer. By default, SSL is not used.   WS-Management encrypts all PowerShell content transmitted over the ... |
| `-UseWindowsPowerShell` | `Object` | Yes | Creates a remote connection to a new Windows PowerShell runspace on the local system. |
| `-VMId` | `Object` | Yes | Specifies an array of virtual machine IDs. This cmdlet starts a PowerShell Direct interactive session with each of the specified virtual machines. For more information, see [Virtual Machine automat... |
| `-VMName` | `Object` | Yes | Specifies an array of names of virtual machines. This cmdlet starts a PowerShell Direct interactive session with each of the specified virtual machines. For more information, see [Virtual Machine a... |

**Patterns & Best Practices:**

Proxy remote commands locally via `Import-PSSession`:

```powershell
$s = New-PSSession -HostName exchange-server
Import-PSSession -Session $s -Module ExchangeOnlineManagement -Prefix Remote
Get-RemoteMailbox -Identity user@domain.com  # Runs on remote, looks local
```


---

### New-PSSessionConfigurationFile

Creates a file that defines a session configuration.

The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration. To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.

**Returns**: `None`

```
New-PSSessionConfigurationFile
    [-AliasDefinitions <Object>]
    [-AssembliesToLoad <Object>]
    [-Author <Object>]
    [-CompanyName <Object>]
    [-Copyright <Object>]
    [-Description <Object>]
    [-EnvironmentVariables <Object>]
    [-ExecutionPolicy <Object>]
    [-FormatsToProcess <Object>]
    [-Full <Object>]
    [-FunctionDefinitions <Object>]
    [-GroupManagedServiceAccount <Object>]
    [-Guid <Object>]
    [-LanguageMode <Object>]
    [-ModulesToImport <Object>]
    [-MountUserDrive <Object>]
    -Path <Object>
    [-PowerShellVersion <Object>]
    [-RequiredGroups <Object>]
    [-RoleDefinitions <Object>]
    [-RunAsVirtualAccount <Object>]
    [-RunAsVirtualAccountGroups <Object>]
    [-SchemaVersion <Object>]
    [-ScriptsToProcess <Object>]
    [-SessionType <Object>]
    [-TranscriptDirectory <Object>]
    [-TypesToProcess <Object>]
    [-UserDriveMaximumSize <Object>]
    [-VariableDefinitions <Object>]
    [-VisibleAliases <Object>]
    [-VisibleCmdlets <Object>]
    [-VisibleExternalCommands <Object>]
    [-VisibleFunctions <Object>]
    [-VisibleProviders <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AliasDefinitions` | `Object` | No | Adds the specified aliases to sessions that use the session configuration. Enter a hash table with the following keys:   - Name - Name of the alias. This key is required. - Value - The command that... |
| `-AssembliesToLoad` | `Object` | No | Specifies the assemblies to load into the sessions that use the session configuration. |
| `-Author` | `Object` | No | Specifies the author of the session configuration or the configuration file. The default is the current user. The value of this parameter is visible in the session configuration file, but it is not... |
| `-CompanyName` | `Object` | No | Specifies the company that created the session configuration or the configuration file. The default value is **Unknown**. The value of this parameter is visible in the session configuration file, b... |
| `-Copyright` | `Object` | No | Specifies a copyright the session configuration file. The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.   If yo... |
| `-Description` | `Object` | No | Specifies a description of the session configuration or the session configuration file. The value of this parameter is visible in the session configuration file, but it is not a property of the ses... |
| `-EnvironmentVariables` | `Object` | No | Adds environment variables to the session. Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.   For example: `EnvironmentVar... |
| `-ExecutionPolicy` | `Object` | No | Specifies the execution policy of sessions that use the session configuration. If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted... |
| `-FormatsToProcess` | `Object` | No | Specifies the formatting files (`.ps1xml`) that run in sessions that use the session configuration. The value of this parameter must be a full or absolute path of the formatting files. |
| `-Full` | `Object` | No | Indicates that this operation includes all possible configuration properties in the session configuration file. |
| `-FunctionDefinitions` | `Object` | No | Adds the specified functions to sessions that use the session configuration. Enter a hash table with the following keys:   - Name - Name of the function. This key is required. - ScriptBlock - Funct... |
| `-GroupManagedServiceAccount` | `Object` | No | Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account. The machine where this session configuration is registered must have pe... |
| `-Guid` | `Object` | No | Specifies a unique identifier for the session configuration file. If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file. To create a new GUID in PowerShell, typ... |
| `-LanguageMode` | `Object` | No | Determines which elements of the PowerShell language are permitted in sessions that use this session configuration. You can use this parameter to restrict the commands that particular users can run... |
| `-ModulesToImport` | `Object` | No | Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.   By default, only the **Microsoft.PowerShell.Core** snap-in is imported into re... |
| `-MountUserDrive` | `Object` | No | Configures sessions that use this session configuration to expose the `User:` PSDrive. User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints ... |
| `-Path` | `Object` | Yes | Specifies the path and filename of the session configuration file. The file must have a `.pssc` file name extension. |
| `-PowerShellVersion` | `Object` | No | Specifies the version of the PowerShell engine in sessions that use the session configuration. The acceptable values for this parameter are: 2.0 and 3.0. If you omit this parameter, the **PowerShel... |
| `-RequiredGroups` | `Object` | No | Specifies conditional access rules for users connecting to sessions that use this session configuration.   Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or '... |
| `-RoleDefinitions` | `Object` | No | Specifies the mapping between security groups (or users) and role capabilities. Users will be granted access to all role capabilities which apply to their group membership at the time the session i... |
| `-RunAsVirtualAccount` | `Object` | No | Configures sessions using this session configuration to be run as the computer's (virtual) administrator account. This field cannot be used with the **GroupManagedServiceAccount** parameter. |
| `-RunAsVirtualAccountGroups` | `Object` | No | Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account. If omitted, the virtual account belongs to Do... |
| `-SchemaVersion` | `Object` | No | Specifies the version of the session configuration file schema. The default value is "1.0.0.0". |
| `-ScriptsToProcess` | `Object` | No | Adds the specified scripts to sessions that use the session configuration. Enter the path and file names of the scripts. The value of this parameter must be a full or absolute path of script file n... |
| `-SessionType` | `Object` | No | Specifies the type of session that is created by using the session configuration. The default value is Default. The acceptable values for this parameter are:   - Empty - No modules are added to ses... |
| `-TranscriptDirectory` | `Object` | No | Specifies the directory to place session transcripts for sessions using this session configuration. |
| `-TypesToProcess` | `Object` | No | Adds the specified `.ps1xml` type files to sessions that use the session configuration. Enter the type filenames. The value of this parameter must be a full or absolute path to type filenames. |
| `-UserDriveMaximumSize` | `Object` | No | Specifies the maximum size for user drives exposed in sessions that use this session configuration. When omitted, the default size of each `User:` drive root is 50MB.   This parameter should be use... |
| `-VariableDefinitions` | `Object` | No | Adds the specified variables to sessions that use the session configuration. Enter a hash table with the following keys:   - Name - Name of the variable. This key is required. - Value - Variable va... |
| `-VisibleAliases` | `Object` | No | Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter. Wildcard characters are supported. By def... |
| `-VisibleCmdlets` | `Object` | No | Limits the cmdlets in the session to those specified in the value of this parameter. Wildcard characters and Module Qualified Names are supported.   By default, all cmdlets that modules in the sess... |
| `-VisibleExternalCommands` | `Object` | No | Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter. Wildcard characters are supported.   By default, no extern... |
| `-VisibleFunctions` | `Object` | No | Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter. Wildcard characters are supported.... |
| `-VisibleProviders` | `Object` | No | Limits the PowerShell providers in the session to those specified in the value of this parameter. Wildcard characters are supported.   By default, all providers that modules in the session export a... |

---

### New-PSSessionOption

Creates an object that contains advanced options for a PSSession.

The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session (**PSSession**). You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession**, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.

**Returns**: `System.Management.Automation.Remoting.PSSessionOption`

```
New-PSSessionOption
    [-ApplicationArguments <Object>]
    [-CancelTimeout <Object>]
    [-Culture <Object>]
    [-IdleTimeout <Object>]
    [-IncludePortInSPN <Object>]
    [-MaxConnectionRetryCount <Object>]
    [-MaximumReceivedDataSizePerCommand <Object>]
    [-MaximumReceivedObjectSize <Object>]
    [-MaximumRedirection <Object>]
    [-NoCompression <Object>]
    [-NoEncryption <Object>]
    [-NoMachineProfile <Object>]
    [-OpenTimeout <Object>]
    [-OperationTimeout <Object>]
    [-OutputBufferingMode <Object>]
    [-ProxyAccessType <Object>]
    [-ProxyAuthentication <Object>]
    [-ProxyCredential <Object>]
    [-SkipCACheck <Object>]
    [-SkipCNCheck <Object>]
    [-SkipRevocationCheck <Object>]
    [-UICulture <Object>]
    [-UseUTF16 <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApplicationArguments` | `Object` | No | Specifies a **PrimitiveDictionary** that's sent to the remote session. Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary i... |
| `-CancelTimeout` | `Object` | No | Determines how long PowerShell waits for a cancel operation (<kbd>CTRL</kbd>+<kbd>C</kbd>) to finish before ending it. Enter a value in milliseconds.   The default value is `60000` (one minute). A ... |
| `-Culture` | `Object` | No | Specifies the culture to use for the session. Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command ... |
| `-IdleTimeout` | `Object` | No | Determines how long the session stays open if the remote computer does not receive any communication from the local computer. This includes the heartbeat signal. When the interval expires, the sess... |
| `-IncludePortInSPN` | `Object` | No | Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`. This option allows a client that uses a non-default SPN to ... |
| `-MaxConnectionRetryCount` | `Object` | No | Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues. The default value is `5`.   This parameter was ad... |
| `-MaximumReceivedDataSizePerCommand` | `Object` | No | Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command. Enter a value in bytes. By default, there is no data size limit.   This optio... |
| `-MaximumReceivedObjectSize` | `Object` | No | Specifies the maximum size of an object that the local computer can receive from the remote computer. This option is designed to protect the resources on the client computer. Enter a value in bytes... |
| `-MaximumRedirection` | `Object` | No | Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails. The default value is `5`. A value of `0` (zero) prevents a... |
| `-NoCompression` | `Object` | No | Turns off packet compression in the session. Compression uses more processor cycles, but it makes transmission faster. |
| `-NoEncryption` | `Object` | No | Turns off data encryption. |
| `-NoMachineProfile` | `Object` | No | Prevents loading the user's Windows user profile. As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are no... |
| `-OpenTimeout` | `Object` | No | Determines how long the client computer waits for the session connection to be established. When the interval expires, the command to establish the connection fails. Enter a value in milliseconds. ... |
| `-OperationTimeout` | `Object` | No | Determines the maximum time **WinRM** waits for positive connection tests from a live connection before initiating a connection time-out. For more information on WinRM, see the [Windows Remote Mana... |
| `-OutputBufferingMode` | `Object` | No | Determines how command output is managed in disconnected sessions when the output buffer becomes full.   If the output buffering mode is not set in the session or in the session configuration, the ... |
| `-ProxyAccessType` | `Object` | No | Determines which mechanism is used to resolve the hostname. The acceptable values for this parameter are:   - `IEConfig` - `WinHttpConfig` - `AutoDetect` - `NoProxyServer` - `None`   The default va... |
| `-ProxyAuthentication` | `Object` | No | Specifies the authentication method that is used for proxy resolution. The acceptable values for this parameter are:   - `Basic` - `Digest` - `Negotiate`   The default value is `Negotiate`.   For m... |
| `-ProxyCredential` | `Object` | No | Specifies the credentials to use for proxy authentication. Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` comm... |
| `-SkipCACheck` | `Object` | No | Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).   Use this option only when the remote comp... |
| `-SkipCNCheck` | `Object` | No | Specifies that the certificate common name (CN) of the server does not have to match the hostname of the server. This option is used only in remote operations that use the HTTPS protocol.   Use thi... |
| `-SkipRevocationCheck` | `Object` | No | Does not validate the revocation status of the server certificate. |
| `-UICulture` | `Object` | No | Specifies the UI culture to use for the session.   Valid values include:   - A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP` - A variable that contains a **Culture... |
| `-UseUTF16` | `Object` | No | Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format. |

---

### New-PSTransportOption

Creates an object that contains advanced options for a session configuration.

The `New-PSTransportOption` cmdlet creates an object that contains transport options for session configurations. You can use the object as the value of the **TransportOption** parameter of cmdlets that create or change a session configuration, such as the `Register-PSSessionConfiguration` and `Set-PSSessionConfiguration` cmdlets.

**Returns**: `Microsoft.PowerShell.Commands.WSManConfigurationOption`

```
New-PSTransportOption
    [-IdleTimeoutSec <Object>]
    [-MaxConcurrentCommandsPerSession <Object>]
    [-MaxConcurrentUsers <Object>]
    [-MaxIdleTimeoutSec <Object>]
    [-MaxMemoryPerSessionMB <Object>]
    [-MaxProcessesPerSession <Object>]
    [-MaxSessions <Object>]
    [-MaxSessionsPerUser <Object>]
    [-OutputBufferingMode <Object>]
    [-ProcessIdleTimeoutSec <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-IdleTimeoutSec` | `Object` | No | Determines how long each session stays open if the remote computer does not receive any communication from the local computer. This includes the heartbeat signal. When the interval expires, the ses... |
| `-MaxConcurrentCommandsPerSession` | `Object` | No | Limits the number of commands that can run at the same time in each session to the specified value. The default value is 1000.   The **MaxConcurrentCommandsPerSession** parameter corresponds to the... |
| `-MaxConcurrentUsers` | `Object` | No | Limits the number of users who can run commands at the same time in each session to the specified value. The default value is 5. |
| `-MaxIdleTimeoutSec` | `Object` | No | Limits the idle time-out set for each session to the specified value. The default value is `[int]::MaxValue` (~25 days).   The idle time-out value is of significant importance when the user intends... |
| `-MaxMemoryPerSessionMB` | `Object` | No | Limits the memory used by each session to the specified value. Enter a value in megabytes. The default value is 1024 megabytes (1 GB).   The **MaxMemoryPerSessionMB** parameter corresponds to the *... |
| `-MaxProcessesPerSession` | `Object` | No | Limits the number of processes running in each session to the specified value. The default value is 15.   The **MaxProcessesPerSession** parameter corresponds to the **MaxProcessesPerShell** proper... |
| `-MaxSessions` | `Object` | No | Limits the number of sessions that use the session configuration. The default value is 25.   The **MaxSessions** parameter corresponds to the **MaxShells** property of a session configuration. |
| `-MaxSessionsPerUser` | `Object` | No | Limits the number of sessions that use the session configuration and run with the credentials of a given user to the specified value. The default value is 25.   When you specify this value, conside... |
| `-OutputBufferingMode` | `Object` | No | Determines how command output is managed in disconnected sessions when the output buffer becomes full. The acceptable values for this parameter are:   - `Block`   When the output buffer is full, ex... |
| `-ProcessIdleTimeoutSec` | `Object` | No | Limits the time-out for each host process to the specified value. The default value, 0, means that there is no time-out value for the process.   Other session configurations have per-process time-o... |

---

### Out-Default

Sends the output to the default formatter and to the default output cmdlet.

PowerShell automatically adds `Out-Default` to the end of every top-level interactive pipeline. `Out-Default` passes the objects it receives to the PowerShell format system. Then, it writes the formatted output to the console. This cmdlet isn't intended to be used by the end user.

**Returns**: `None documented`

```
Out-Default
    [-InputObject <Object>]
    [-Transcript <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | No | Accepts input to the cmdlet. |
| `-Transcript` | `Object` | No | When you use this parameter, the output is only sent to the PowerShell transcript. |

---

### Out-Host

Sends output to the command line.

The `Out-Host` cmdlet sends output to the PowerShell host for display. The host displays the output at the command line. Because `Out-Host` is the default, you don't have to specify it unless you want to use its parameters.

**Returns**: `None`

```
Out-Host
    [-InputObject <Object>]
    [-Paging <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | No | Specifies the objects that are written to the console. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-Paging` | `Object` | No | Indicates that `Out-Host` displays one page of output at a time. The page size is determined by the characteristics of the host.   After outputting the first page, the command waits for user input ... |

---

### Out-Null

Hides the output instead of sending it down the pipeline or displaying it.

The `Out-Null` cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output from being displayed on screen.

**Returns**: `None`

```
Out-Null
    [-InputObject <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | No | Specifies the object to be sent to NULL (removed from pipeline). Enter a variable that contains the objects, or type a command or expression that gets the objects. |

**Patterns & Best Practices:**

```text
TYPES:        [string] [int] [bool] [array] [hashtable] [pscustomobject] [datetime]
COMPARE:      -eq -ne -gt -lt -ge -le -like -match -contains -in  (case-insensitive!)
CASE-SENS:    -ceq -cne -cgt -clt -cge -cle -clike -cmatch
LOGIC:        -and -or -not -xor !
NULL:         $null -eq $var (LEFT side!)  ??  ??=  ${x}?.Prop
TERNARY:      $cond ? $ifTrue : $ifFalse
CHAIN:        cmd1 && cmd2 (on success)    cmd1 || cmd2 (on failure)
SCOPE:        $local: $script: $global: $private: $using:
SUCCESS:      $? (last PS cmd)    $LASTEXITCODE (last native exe)
IDENTITY:     $PSVersionTable  $IsLinux  $IsWindows  $IsMacOS
CONTEXT:      $PSScriptRoot  $PSCommandPath  $MyInvocation
PIPELINE:     $_ ($PSItem)  $input  $Matches
PRECEDENCE:   alias > function > cmdlet > external application
SUPPRESS:     [void]$x.Method()  or  $null = expr  or  | Out-Null
FORCE ARRAY:  @(expression)  or  [array]$var = expression
```


**Patterns & Best Practices:**

When parallel iterations write to a shared collection, use `System.Collections.Concurrent`:

```powershell
$bag = [System.Collections.Concurrent.ConcurrentBag[object]]::new()
1..100 | ForEach-Object -Parallel {
    ($using:bag).Add([PSCustomObject]@{ Id = $_; Squared = $_ * $_ })
} -ThrottleLimit 10
$bag.Count  # 100

$dict = [System.Collections.Concurrent.ConcurrentDictionary[string, int]]::new()
Get-ChildItem *.log | ForEach-Object -Parallel {
    $lines = (Get-Content $_.FullName | Measure-Object -Line).Lines
    ($using:dict).TryAdd($_.Name, $lines) | Out-Null
}
```

**Regular collections (ArrayList, List\<T\>) are NOT thread-safe** and will corrupt data or throw in parallel scenarios.


**Patterns & Best Practices:**

### Mistake 1: Forgetting $using: in -Parallel Blocks
```powershell
$path = '/var/log'
Get-ChildItem $path | ForEach-Object -Parallel { Get-Content "$path/$($_.Name)" }
Get-ChildItem $path | ForEach-Object -Parallel { Get-Content "$($using:path)/$($_.Name)" }
```

### Mistake 2: Trying to Modify $using: Variables
```powershell
$counter = 0
1..10 | ForEach-Object -Parallel { $using:counter++ }  # ERROR
$bag = [System.Collections.Concurrent.ConcurrentBag[int]]::new()
1..10 | ForEach-Object -Parallel { ($using:bag).Add($_) }
```

### Mistake 3: Using Start-Job When -Parallel or ThreadJob Suffices
```powershell
$jobs = 1..50 | ForEach-Object { Start-Job { param($n) $n * 2 } -ArgumentList $_ }
$results = 1..50 | ForEach-Object -Parallel { $_ * 2 } -ThrottleLimit 10
```

### Mistake 4: Expecting Ordered Output from -Parallel
```powershell
$out = 1..10 | ForEach-Object -Parallel { Start-Sleep (Get-Random -Max 3); $_ }
$out = 1..10 | ForEach-Object -Parallel {
    [PSCustomObject]@{ Order = $_; Value = $_ * 2 }
} | Sort-Object Order
```

### Mistake 5: Using Non-Thread-Safe Collections
```powershell
$list = [System.Collections.ArrayList]::new()
1..1000 | ForEach-Object -Parallel { ($using:list).Add($_) | Out-Null }  # Race condition!
$bag = [System.Collections.Concurrent.ConcurrentBag[int]]::new()
1..1000 | ForEach-Object -Parallel { ($using:bag).Add($_) }
```

### Mistake 6: Not Understanding -ThrottleLimit Default
The default is **5**, not unlimited. Set it explicitly for your workload:
```powershell
1..1000 | ForEach-Object -Parallel { Invoke-RestMethod "https://api.example.com/$_" } -ThrottleLimit 20
```

### Mistake 7: Wrong $using: Capture in Loops
```powershell
$items = 1..5
$items | ForEach-Object { Start-ThreadJob { "Processing $using:_" } }  # $_ ambiguous
$items | ForEach-Object {
    $item = $_
    Start-ThreadJob { "Processing $using:item" }
}
```

### Mistake 8: Forgetting -Wait on Receive-Job
```powershell
$job = Start-ThreadJob { Start-Sleep 5; "Done" }
$result = Receive-Job $job  # Empty!
$result = Receive-Job $job -Wait
```

### Mistake 9: Not Cleaning Up Jobs
```powershell
foreach ($i in 1..100) {
    $job = Start-ThreadJob { "work" }
    Receive-Job $job -Wait  # Job still exists!
}
Get-Job | Measure-Object  # 100 stale jobs
Receive-Job $job -Wait -AutoRemoveJob
```

### Mistake 10: Using -Parallel for Trivial or Sequential Work
```powershell
1..5 | ForEach-Object -Parallel { $_ * 2 }
1..5 | ForEach-Object { $_ * 2 }
```


---

### Receive-Job

Gets the results of the PowerShell background jobs in the current session.

The `Receive-Job` cmdlet gets the results of PowerShell background jobs, such as those started by using the `Start-Job` cmdlet or the **AsJob** parameter of any cmdlet. You can get the results of all jobs or identify jobs by their name, ID, instance ID, computer name, location, or session, or by submitting a job object.

**Returns**: `System.Management.Automation.PSObject`

```
Receive-Job
    [-AutoRemoveJob <Object>]
    [-ComputerName <Object>]
    [-Force <Object>]
    -Id <Object>
    -InstanceId <Object>
    -Job <Object>
    [-Keep <Object>]
    [-Location <Object>]
    -Name <Object>
    [-NoRecurse <Object>]
    [-Session <Object>]
    [-Wait <Object>]
    [-WriteEvents <Object>]
    [-WriteJobInResults <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutoRemoveJob` | `Object` | No | Indicates that this cmdlet deletes the job after it returns the job results. If the job has more results, the job is still deleted, but `Receive-Job` displays a message.   This parameter works only... |
| `-ComputerName` | `Object` | No | Specifies an array of names of computers.   This parameter selects from among the job results that are stored on the local computer. It doesn't get data for jobs run on remote computers. To get job... |
| `-Force` | `Object` | No | Indicates that this cmdlet continues waiting if jobs are in the **Suspended** or **Disconnected** state. By default, the **Wait** parameter of `Receive-Job` returns, or terminates the wait, when jo... |
| `-Id` | `Object` | Yes | Specifies an array of IDs. This cmdlet gets the results of jobs with the specified IDs.   The ID is an integer that uniquely identifies the job in the current session. it's easier to remember and t... |
| `-InstanceId` | `Object` | Yes | Specifies an array of instance IDs. This cmdlet gets the results of jobs with the specified instance IDs.   An instance ID is a GUID that uniquely identifies the job on the computer. To find the in... |
| `-Job` | `Object` | Yes | Specifies the job for which results are being retrieved.   Enter a variable that contains the job or a command that gets the job. You can also pipe a job object to `Receive-Job`. |
| `-Keep` | `Object` | No | Indicates that this cmdlet saves the aggregated stream data in the system, even after you have received them. By default, aggregated stream data is erased after viewed with `Receive-Job`.   Closing... |
| `-Location` | `Object` | No | Specifies an array of locations. This cmdlet gets only the results of jobs in the specified locations. |
| `-Name` | `Object` | Yes | Specifies an array of friendly names. This cmdlet gets the results of jobs that have the specified names. Wildcard characters are supported. |
| `-NoRecurse` | `Object` | No | Indicates that this cmdlet gets results only from the specified job. By default, `Receive-Job` also gets the results of all child jobs of the specified job. |
| `-Session` | `Object` | No | Specifies an array of sessions. This cmdlet gets the results of jobs that were run in the specified PowerShell session (**PSSession**). Enter a variable that contains the **PSSession** or a command... |
| `-Wait` | `Object` | No | Indicates that this cmdlet suppresses the command prompt until all job results are received. By default, `Receive-Job` immediately returns the available results.   By default, the **Wait** paramete... |
| `-WriteEvents` | `Object` | No | Indicates that this cmdlet reports changes in the job state while it waits for the job to finish.   This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** ... |
| `-WriteJobInResults` | `Object` | No | Indicates that this cmdlet returns the job object followed by the results.   This parameter is valid only when the **Wait** parameter is used in the command and the **Keep** parameter is omitted.  ... |

**Patterns & Best Practices:**

Runs in a **separate process** — full isolation but serialization overhead and high memory.

```powershell
$job = Start-Job -ScriptBlock { param($Dir) Get-ChildItem $Dir -Recurse | Measure-Object } -ArgumentList '/var/log'
$result = Receive-Job $job -Wait -AutoRemoveJob
```

`$using:` works in PS7 Start-Job, but values are serialized across process boundaries (same deserialization rules as remoting).

**Use Start-Job only when you need:** process isolation, crash protection, or assembly conflict avoidance. Otherwise prefer ThreadJob or -Parallel.


---

### Register-ArgumentCompleter

Registers a custom argument completer.

The `Register-ArgumentCompleter` cmdlet registers a custom argument completer. An argument completer allows you to provide dynamic tab completion, at run time for any command that you specify.

**Returns**: `None`

```
Register-ArgumentCompleter
    -CommandName <Object>
    [-Native <Object>]
    -ParameterName <Object>
    -ScriptBlock <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CommandName` | `Object` | Yes | Specifies the name of one or more commands to register the argument completer for. This parameter is mandatory for native commands.   When you specify this parameter without the **ParameterName** o... |
| `-Native` | `Object` | No | Indicates that the argument completer is for a native command where PowerShell can't complete parameter names. |
| `-ParameterName` | `Object` | Yes | Specifies the name of the parameter the argument completer applies to. The type for specified parameters can't be an enumeration, such as the **ForegroundColor** parameter of the `Write-Host` cmdle... |
| `-ScriptBlock` | `Object` | Yes | Specifies the commands to run to perform tab completion. The scriptblock you provide should return the values that complete the input. The scriptblock must unroll the values using the pipeline (`Fo... |

---

### Remove-Job

Deletes a PowerShell background job.

The `Remove-Job` cmdlet deletes PowerShell background jobs that were started by the `Start-Job` cmdlet or by cmdlets such as `Invoke-Command` that support the **AsJob** parameter.

**Returns**: `None`

```
Remove-Job
    [-Command <Object>]
    [-Confirm <Object>]
    -Filter <Object>
    [-Force <Object>]
    -Id <Object>
    -InstanceId <Object>
    -Job <Object>
    -Name <Object>
    -State <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Command` | `Object` | No | Deletes jobs that include the specified words in the command. You can enter a comma-separated array. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before `Remove-Job` is run. |
| `-Filter` | `Object` | Yes | Deletes jobs that satisfy all the conditions established in the associated hash table. Enter a hash table where the keys are job properties and the values are job property values.   This parameter ... |
| `-Force` | `Object` | No | Deletes a job even if the job's state is **Running**. If the **Force** parameter isn't specified, `Remove-Job` doesn't delete running jobs. |
| `-Id` | `Object` | Yes | Deletes background jobs with the specified **Id**. You can enter a comma-separated array. The job's **Id** is a unique integer that identifies a job within the current session.   To find a job's **... |
| `-InstanceId` | `Object` | Yes | Deletes jobs with the specified **InstanceId**. You can enter a comma-separated array. An **InstanceId** is a unique GUID that identifies a job.   To find a job's **InstanceId**, use `Get-Job`. |
| `-Job` | `Object` | Yes | Specifies the jobs to be deleted. Enter a variable that contains the jobs or a command that gets the jobs. You can enter a comma-separated array.   You can send job objects down the pipeline to `Re... |
| `-Name` | `Object` | Yes | Only deletes jobs with the specified friendly name. Wildcards are permitted. You can enter a comma-separated array.   Friendly names for jobs aren't guaranteed to be unique, even within a PowerShel... |
| `-State` | `Object` | Yes | Only deletes jobs with the specified state. To delete jobs with a state of **Running**, use the **Force** parameter.   Accepted values:   - AtBreakpoint - Blocked - Completed - Disconnected - Faile... |
| `-WhatIf` | `Object` | No | Shows what would happen if `Remove-Job` runs. The cmdlet isn't run. |

**Patterns & Best Practices:**

```powershell
1..10 | ForEach-Object -Parallel {
    "Processing $_ on thread $([Threading.Thread]::CurrentThread.ManagedThreadId)"
    Start-Sleep 1
} -ThrottleLimit 5
```

- Pipeline input available as `$_` / `$PSItem`.
- `-ThrottleLimit` controls max concurrent runspaces (**default: 5**).
- Each iteration runs in its own runspace — **separate scope, no shared state**.
- Output order is **non-deterministic**.

**Patterns & Best Practices:**

```powershell
$job = Start-ThreadJob { long-running-work }
Get-Job                              # List all jobs
$job.State                           # Running, Completed, Failed
Receive-Job $job                     # Get available output (non-blocking)
Receive-Job $job -Wait               # Block until complete
Receive-Job $job -Wait -AutoRemoveJob  # Wait + get output + cleanup
Stop-Job $job                        # Signal stop
Remove-Job $job                      # Remove (must be stopped/completed)
Remove-Job $job -Force               # Force-remove even if running
```

**Patterns & Best Practices:**

**Patterns & Best Practices:**

| Task | Command |
|------|---------|
| Parallel iteration | `items \| ForEach-Object -Parallel { ... } -ThrottleLimit N` |
| Async parallel | `items \| ForEach-Object -Parallel { ... } -AsJob` |
| Lightweight job | `Start-ThreadJob -ScriptBlock { ... }` |
| Isolated job | `Start-Job -ScriptBlock { ... }` |
| Wait + collect | `Receive-Job $job -Wait -AutoRemoveJob` |
| Check all jobs | `Get-Job` |
| Clean completed | `Get-Job -State Completed \| Remove-Job` |
| Pass variable | `$using:varName` |
| Thread-safe add | `[Concurrent.ConcurrentBag[T]]::new()` |


**Patterns & Best Practices:**

```powershell
$job = Invoke-Command -HostName server1, server2 -ScriptBlock { Start-Sleep 30; Get-Process } -AsJob
$job.ChildJobs | Format-Table State, Location  # Per-host child jobs
$results = Receive-Job $job -Wait
Remove-Job $job
```


### In ForEach-Object -Parallel

Errors from one iteration do NOT stop others. Capture via the output stream:

```powershell
$results = 1..5 | ForEach-Object -Parallel {
    if ($_ -eq 3) { throw "Item 3 failed" }
    "OK: $_"
} 2>&1

$results | ForEach-Object {
    if ($_ -is [System.Management.Automation.ErrorRecord]) { "ERROR: $($_.Exception.Message)" }
    else { $_ }
}
```

### In Jobs

```powershell
$job = Start-ThreadJob { throw "Something went wrong" }
Wait-Job $job
$job.State  # Failed
try { Receive-Job $job -Wait -ErrorAction Stop }
catch { "Job failed: $_" }
Remove-Job $job
```


### Collecting from Multiple Jobs

```powershell
$jobs = 1..5 | ForEach-Object {
    $num = $_
    Start-ThreadJob { Start-Sleep 2; "Result from $using:num" }
}
$results = $jobs | Receive-Job -Wait -AutoRemoveJob
```


### $using: for Local Variables

Variables from the calling scope are NOT visible inside `-Parallel`. Use `$using:`.

```powershell
$logPath = '/var/log/app'
$threshold = 100
Get-ChildItem $logPath -Filter '*.log' | ForEach-Object -Parallel {
    $errors = (Get-Content "$($using:logPath)/$($_.Name)" | Select-String 'ERROR').Count
    if ($errors -gt $using:threshold) { [PSCustomObject]@{ File = $_.Name; Errors = $errors } }
} -ThrottleLimit 4
```

`$using:` values are **read-only copies**. You cannot write back to the caller's scope.

### -AsJob for Async

```powershell
$job = 1..20 | ForEach-Object -Parallel {
    Start-Sleep (Get-Random -Minimum 1 -Maximum 5); "Done: $_"
} -ThrottleLimit 5 -AsJob

$results = Receive-Job $job -Wait
Remove-Job $job
```

### No Pipeline Blocks Inside -Parallel

```powershell
1..5 | ForEach-Object -Parallel {
    begin { $total = 0 }      # ERROR
    process { $total += $_ }
}
$results = 1..5 | ForEach-Object -Parallel { $_ * 2 }
```


---

### Remove-Module

Removes modules from the current session.

The `Remove-Module` cmdlet removes the members of a module, such as cmdlets and functions, from the current session.

**Returns**: `None`

```
Remove-Module
    [-Confirm <Object>]
    [-Force <Object>]
    -FullyQualifiedName <Object>
    -ModuleInfo <Object>
    -Name <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Force` | `Object` | No | Indicates that this cmdlet removes read-only modules. By default, `Remove-Module` removes only read-write modules.   The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property ... |
| `-FullyQualifiedName` | `Object` | Yes | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-ModuleInfo` | `Object` | Yes | Specifies the module objects to remove. Enter a variable that contains a **PSModuleInfo** object or a command that gets a module object, such as a `Get-Module` command. You can also pipe module obj... |
| `-Name` | `Object` | Yes | Specifies the names of modules to remove. Wildcard characters are permitted. You can also pipe name strings to `Remove-Module`. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

**Patterns & Best Practices:**

### Mistake 1: Using Export-ModuleMember When a Manifest Controls Exports
```powershell
Export-ModuleMember -Function 'Get-Widget', 'Set-Widget'  # Set-Widget still NOT exported!
```

### Mistake 2: Using FunctionsToExport = '*'
```powershell
@{ FunctionsToExport = '*' }
@{ FunctionsToExport = @('Get-Widget', 'Set-Widget', 'Remove-Widget') }
```

### Mistake 3: Confusing Module Scope with Script/Global Scope
```powershell
$script:cache = @{}  # Correct: module-level state

$global:cache = @{}  # Don't do this for module state
```

### Mistake 4: Forgetting to Update FunctionsToExport After Adding Functions
```powershell
@{ FunctionsToExport = @('Get-Widget', 'Set-Widget') }  # New-Widget invisible!
```

### Mistake 5: Redundant Import-Module with #Requires
```powershell
#Requires -Modules Az.Accounts
Import-Module Az.Accounts  # Unnecessary

#Requires -Modules Az.Accounts
Get-AzContext
```

### Mistake 6: Not Specifying Install-Module Scope
```powershell
Install-Module Pester  # CurrentUser on Linux, AllUsers if elevated on Windows
Install-Module Pester -Scope CurrentUser
```

### Mistake 7: Confusing RequiredModules and NestedModules
```powershell
@{
    RequiredModules = @('Az.Accounts')    # Dependency loaded INDEPENDENTLY, before your module
    NestedModules = @('Helper.psm1')      # Loaded INTO your module's scope
}
```

### Mistake 8: Assuming Remove-Module Unloads .NET Assemblies
```powershell
Remove-Module MyBinaryModule
```

### Mistake 9: Using $PSScriptRoot Wrong in Dot-Sourced Files
```powershell

$script:ModuleRoot = $PSScriptRoot
$configPath = Join-Path $script:ModuleRoot 'config.json'
```

### Mistake 10: Publishing Without Checking the Manifest
```powershell
Test-ModuleManifest ./MyModule/MyModule.psd1
```


---

### Remove-PSSession

Closes one or more PowerShell sessions (PSSessions).

The `Remove-PSSession` cmdlet closes PowerShell sessions (**PSSessions**) in the current session. It stops any commands that are running in the **PSSessions**, ends the **PSSession**, and releases the resources that the **PSSession** was using. If the **PSSession** is connected to a remote computer, this cmdlet also closes the connection between the local and remote computers.

**Returns**: `None`

```
Remove-PSSession
    -ComputerName <Object>
    [-Confirm <Object>]
    -ContainerId <Object>
    -Id <Object>
    -InstanceId <Object>
    -Name <Object>
    -Session <Object>
    -VMId <Object>
    -VMName <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ComputerName` | `Object` | Yes | Specifies an array of names of computers. This cmdlet closes the **PSSessions** that are connected to the specified computers. Wildcard characters are permitted.   Type the NetBIOS name, an IP addr... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-ContainerId` | `Object` | Yes | Specifies an array of IDs of containers. This cmdlet removes sessions for each of the specified containers. Use the `docker ps` command to get a list of container IDs. For more information, see the... |
| `-Id` | `Object` | Yes | Specifies an array of IDs of sessions. This cmdlet closes the **PSSessions** with the specified IDs. Type one or more IDs, separated by commas, or use the range operator (`..`) to specify a range o... |
| `-InstanceId` | `Object` | Yes | Specifies an array of instance IDs. This cmdlet closes the **PSSessions** that have the specified instance IDs.   The instance ID is a GUID that uniquely identifies a **PSSession** in the current s... |
| `-Name` | `Object` | Yes | Specifies an array of friendly names of sessions. This cmdlet closes the **PSSessions** that have the specified friendly names. Wildcard characters are permitted.   Because the friendly name of a *... |
| `-Session` | `Object` | Yes | Specifies the session objects of the **PSSessions** to close. Enter a variable that contains the **PSSessions** or a command that creates or gets the **PSSessions**, such as a `New-PSSession` or `G... |
| `-VMId` | `Object` | Yes | Specifies an array of ID of virtual machines. This cmdlet starts an interactive session with each of the specified virtual machines. To see the virtual machines that are available to you, use the f... |
| `-VMName` | `Object` | Yes | Specifies an array of names of virtual machines. This cmdlet starts an interactive session with each of the specified virtual machines. To see the virtual machines that are available to you, use th... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

**Patterns & Best Practices:**

Sessions maintain state — variables, functions, and modules persist between calls.

```powershell
$s = New-PSSession -HostName server1
Invoke-Command -Session $s -ScriptBlock { $counter = 0 }
Invoke-Command -Session $s -ScriptBlock { $counter++; $counter }  # Returns 1

$sessions = New-PSSession -HostName web01, web02, web03
Invoke-Command -Session $sessions -ScriptBlock { Get-Service nginx }
$sessions | Remove-PSSession

Enter-PSSession -Session $s
Exit-PSSession
Remove-PSSession $s
```

**Disconnected sessions** (WinRM only, not SSH):
```powershell
$s = New-PSSession -ComputerName server1
Disconnect-PSSession $s
```


**Patterns & Best Practices:**

### Mistake 1: Forgetting $using: in Remote ScriptBlocks
```powershell
$name = 'nginx'
Invoke-Command -HostName server1 -ScriptBlock { Get-Service $name }
Invoke-Command -HostName server1 -ScriptBlock { Get-Service $using:name }
```
Local variables do NOT exist in the remote scope without `$using:`.

### Mistake 2: Mixing -ComputerName and -HostName Parameters
```powershell
Invoke-Command -ComputerName server1 -KeyFilePath ~/.ssh/id_ed25519 -ScriptBlock { }
Invoke-Command -HostName server1 -KeyFilePath ~/.ssh/id_ed25519 -ScriptBlock { }
```

### Mistake 3: Calling Methods on Deserialized Objects
```powershell
$proc = Invoke-Command -HostName server1 -ScriptBlock { Get-Process -Id 1234 }
$proc.Kill()  # Method does not exist
Invoke-Command -HostName server1 -ScriptBlock { Stop-Process -Id 1234 -Force }
```

### Mistake 4: Passing ScriptBlocks to Remote Sessions
```powershell
$filter = { $_.CPU -gt 100 }
Invoke-Command -HostName server1 -ScriptBlock { Get-Process | Where-Object $using:filter }
Invoke-Command -HostName server1 -ScriptBlock { Get-Process | Where-Object CPU -gt 100 }
```

### Mistake 5: Using -Credential with SSH Remoting
```powershell
Invoke-Command -HostName server1 -Credential $cred -ScriptBlock { whoami }
Invoke-Command -HostName server1 -UserName admin -KeyFilePath ~/.ssh/id_ed25519 -ScriptBlock { whoami }
```

### Mistake 6: Assuming Fan-Out Is Sequential
```powershell
Invoke-Command -HostName server1, server2, server3 -ScriptBlock { Restart-Service nginx }
```

### Mistake 7: Using Disconnect-PSSession with SSH
```powershell
$s = New-PSSession -HostName linux-box
Disconnect-PSSession $s  # ERROR
```

### Mistake 8: Not Flattening Objects for Serialization
```powershell
$r = Invoke-Command -HostName s1 -ScriptBlock { Get-ChildItem -Recurse | Select-Object * }
$r = Invoke-Command -HostName s1 -ScriptBlock {
    Get-ChildItem -Recurse | ForEach-Object {
        [PSCustomObject]@{ FullName = $_.FullName; Length = $_.Length }
    }
}
```

### Mistake 9: Leaking PSSessions
```powershell
foreach ($server in $servers) {
    $s = New-PSSession -HostName $server
    Invoke-Command -Session $s -ScriptBlock { Get-Service }  # Never removed!
}
$sessions = New-PSSession -HostName $servers
try { Invoke-Command -Session $sessions -ScriptBlock { Get-Service } }
finally { $sessions | Remove-PSSession }
```

### Mistake 10: Using Enter-PSSession in Scripts
```powershell
Enter-PSSession -HostName server1
Get-Service nginx  # Runs LOCALLY, not on server1!
Exit-PSSession
Invoke-Command -HostName server1 -ScriptBlock { Get-Service nginx }
```


---

### Save-Help

Downloads and saves the newest help files to a file system directory.

The `Save-Help` cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify. This feature lets you update the help files on computers that don't have access to the internet, and makes it easier to update the help files on multiple computers. This cmdlet was introduced in Windows PowerShell 3.0.

**Returns**: `None`

```
Save-Help
    [-Credential <Object>]
    -DestinationPath <Object>
    [-Force <Object>]
    [-FullyQualifiedModule <Object>]
    -LiteralPath <Object>
    [-Module <Object>]
    [-Scope <Object>]
    [-UICulture <Object>]
    [-UseDefaultCredentials <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | Specifies a user credential. This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter. This p... |
| `-DestinationPath` | `Object` | Yes | Specifies the path of the folder in which the help files are saved. Don't specify a filename or filename extension. |
| `-Force` | `Object` | No | Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.   Without this parameter, only one `Save-Help` command... |
| `-FullyQualifiedModule` | `Object` | No | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-LiteralPath` | `Object` | Yes | Specifies a path of the destination folder. Unlike the value of the **DestinationPath** parameter, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interp... |
| `-Module` | `Object` | No | Specifies modules for which this cmdlet downloads help. Enter one or more module names or name patterns in a comma-separated list or in a file that has one module name on each line. Wildcard charac... |
| `-Scope` | `Object` | No | This parameter does nothing in this cmdlet. |
| `-UICulture` | `Object` | No | Specifies UI culture values for which this cmdlet gets updated help files. Enter one or more language codes, such as `es-ES`, a variable that contains culture objects, or a command that gets cultur... |
| `-UseDefaultCredentials` | `Object` | No | Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user. By default, the command runs without explicit credentials.   This parameter is eff... |

---

### Set-PSDebug

Turns script debugging features on and off, sets the trace level, and toggles strict mode.

The `Set-PSDebug` cmdlet turns script debugging features on and off, sets the trace level, and toggles strict mode. By default, the PowerShell debug features are off.

**Returns**: `None`

```
Set-PSDebug
    [-Off <Object>]
    [-Step <Object>]
    [-Strict <Object>]
    [-Trace <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Off` | `Object` | No | Turns off all script debugging features. |
| `-Step` | `Object` | No | Turns on script stepping. Before each line runs, PowerShell prompts you to stop, continue, or enter a new interpreter level to inspect the state of the script.   Specifying the **Step** parameter a... |
| `-Strict` | `Object` | No | Specifies that variables must be assigned a value before being referenced in a script. If a variable is referenced before a value is assigned, PowerShell returns an exception error. This is equival... |
| `-Trace` | `Object` | No | Specifies the trace level for each line in a script. Each line is traced as it's run.   The acceptable values for this parameter are as follows:   - 0: Turn script tracing off. - 1: Trace script li... |

---

### Set-StrictMode

Establishes and enforces coding rules in expressions, scripts, and scriptblocks.

The `Set-StrictMode` cmdlet configures strict mode for the current scope and all child scopes, and turns it on and off. When strict mode is on, PowerShell generates a terminating error when the content of an expression, script, or scriptblock violates basic best-practice coding rules.

**Returns**: `None`

```
Set-StrictMode
    -Off <Object>
    -Version <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Off` | `Object` | Yes | Indicates that this cmdlet turns strict mode off for the current scope and all child scopes. |
| `-Version` | `Object` | Yes | Specifies the conditions that cause an error in strict mode. This parameter accepts any valid PowerShell version number. Any number higher than `3` is treated as `Latest`. The value supplied must b... |

**Patterns & Best Practices:**

```powershell
#!/usr/bin/env pwsh
#Requires -Version 7.4

<#
.SYNOPSIS
    Brief one-line description.
.PARAMETER Name
    Description of the Name parameter.
.EXAMPLE
    ./Deploy-Service.ps1 -Name 'web-api' -Environment Production
#>

[CmdletBinding(SupportsShouldProcess)]
param(
    [Parameter(Mandatory)]
    [ValidateNotNullOrEmpty()]
    [string]$Name,

    [ValidateSet('Development', 'Staging', 'Production')]
    [string]$Environment = 'Development'
)

Set-StrictMode -Version Latest
$ErrorActionPreference = 'Stop'

Write-Verbose "Deploying $Name to $Environment"
```

**Patterns & Best Practices:**

`Set-StrictMode -Version Latest` catches common bugs at runtime:

| Behavior | Without StrictMode | With StrictMode |
|----------|-------------------|-----------------|
| Undefined variable | Returns `$null` | Throws error |
| Nonexistent property | Returns `$null` | Throws error |
| Function called as method `f()` | Calls function | Throws error |

```powershell
Set-StrictMode -Version Latest

$config = Import-Csv './config.csv'
$config[0].Naem   # Typo caught immediately!

function Test-Thing {
    $undefined.Property   # No error! Must set StrictMode inside function too
}
```

**Patterns & Best Practices:**

### 1: Missing [CmdletBinding()] param()
Without it, `-Verbose`, `-Debug`, and `-ErrorAction` are not available to callers.

### 2: Wrong shebang
`#!/usr/bin/pwsh` (not portable), `#!/usr/bin/env powershell` (invokes PS 5.1), or shebang not on line 1.

### 3: Set-StrictMode before param()
```powershell
Set-StrictMode -Version Latest   [CmdletBinding()]
[CmdletBinding()]                param()
param()                          Set-StrictMode -Version Latest
```

### 4: Using exit in functions
`exit` terminates the entire PowerShell process. In functions, use `throw` or `return`.

### 5: Not saving $? immediately
`$?` is reset by every statement including assignments. Save it on the very next line.

### 6: Assuming $LASTEXITCODE resets after cmdlets
Cmdlets do NOT reset `$LASTEXITCODE`. Check it immediately after native commands or reset manually.

### 7: Dot-sourcing when you want isolation
`. ./setup.ps1` leaks all variables into your scope. Use `./setup.ps1` or `Import-Module` for isolation.

### 8: Expecting StrictMode to inherit into child scopes
StrictMode is scoped. Functions do NOT inherit it. Set `Set-StrictMode -Version Latest` inside each function.

### 9: Using Write-Host for output data
```powershell
function Get-Name { Write-Host "server-01" }
$name = Get-Name   # $null! Write-Host is display-only

function Get-Name { "server-01" }   # Implicit Write-Output
$name = Get-Name   # "server-01"
```

### 10: #Requires inside a function
`#Requires` is silently ignored inside functions. It only works at script level.


### StrictMode Gotcha: Property Existence Checks

```powershell
Set-StrictMode -Version Latest

if ($obj.Optional) { ... }

if ($null -ne $obj.PSObject.Properties['Optional']) { ... }
$value = $obj?.Optional   # PS7.1+ null-conditional — returns $null safely
```


### Why This Order Matters

1. **Shebang** must be the very first line (Linux/macOS execution)
2. **#Requires** directives are checked before ANY code runs
3. **Comment-based help** must immediately precede `param()`
4. **`[CmdletBinding()]` and `param()`** must be the first non-comment code
5. **`Set-StrictMode`** and **`$ErrorActionPreference`** go in the body, after param


---

### Start-Job

Starts a PowerShell background job.

The `Start-Job` cmdlet starts a PowerShell background job on the local computer.

**Returns**: `System.Management.Automation.PSRemotingJob`

```
Start-Job
    [-ArgumentList <Object>]
    [-Authentication <Object>]
    [-Credential <Object>]
    -DefinitionName <Object>
    [-DefinitionPath <Object>]
    -FilePath <Object>
    [-InitializationScript <Object>]
    [-InputObject <Object>]
    -LiteralPath <Object>
    [-Name <Object>]
    [-PSVersion <Object>]
    [-RunAs32 <Object>]
    -ScriptBlock <Object>
    [-Type <Object>]
    [-WorkingDirectory <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object` | No | Specifies an array of arguments, or parameter values, for the script that is specified by the **FilePath** parameter or a command specified with the **ScriptBlock** parameter.   Arguments must be p... |
| `-Authentication` | `Object` | No | Specifies the mechanism that is used to authenticate user credentials.   The acceptable values for this parameter are as follows:   - `Default` - `Basic` - `Credssp` - `Digest` - `Kerberos` - `Nego... |
| `-Credential` | `Object` | No | Specifies a user account that has permission to perform this action. If the **Credential** parameter isn't specified, the command uses the current user's credentials.   Type a user name, such as **... |
| `-DefinitionName` | `Object` | Yes | Specifies the definition name of the job that this cmdlet starts. Use this parameter to start custom job types that have a definition name, such as scheduled jobs.   When you use `Start-Job` to sta... |
| `-DefinitionPath` | `Object` | No | Specifies path of the definition for the job that this cmdlet starts. Enter the definition path. The concatenation of the values of the **DefinitionPath** and **DefinitionName** parameters is the f... |
| `-FilePath` | `Object` | Yes | Specifies a local script that `Start-Job` runs as a background job. Enter the path and file name of the script or use the pipeline to send a script path to `Start-Job`. The script must be on the lo... |
| `-InitializationScript` | `Object` | No | Specifies commands that run before the job starts. To create a scriptblock, enclose the commands in curly braces (`{}`).   Use this parameter to prepare the session in which the job runs. For examp... |
| `-InputObject` | `Object` | No | Specifies input to the command. Enter a variable that contains the objects, or type a command or expression that generates the objects.   In the value of the **ScriptBlock** parameter, use the `$in... |
| `-LiteralPath` | `Object` | Yes | Specifies a local script that this cmdlet runs as a background job. Enter the path of a script on the local computer.   `Start-Job` uses the value of the **LiteralPath** parameter exactly as it's t... |
| `-Name` | `Object` | No | Specifies a friendly name for the new job. You can use the name to identify the job to other job cmdlets, such as the `Stop-Job` cmdlet.   The default friendly name is `Job#`, where `#` is an ordin... |
| `-PSVersion` | `Object` | No | Specifies a version of PowerShell to use for running the job. When the value of **PSVersion** is **5.1** The job is run in a Windows PowerShell 5.1 session. For any other value, the job is run usin... |
| `-RunAs32` | `Object` | No | Beginning with PowerShell 7, the **RunAs32** parameter doesn't work on 64-bit PowerShell (`pwsh`). If **RunAs32** is specified in 64-bit PowerShell, `Start-Job` throws a terminating exception error... |
| `-ScriptBlock` | `Object` | Yes | Specifies the commands to run in the background job. To create a scriptblock, enclose the commands in curly braces (`{}`). Use the `$input` automatic variable to access the value of the **InputObje... |
| `-Type` | `Object` | No | Specifies the custom type for jobs started by `Start-Job`. Enter a custom job type name, such as PSScheduledJob for scheduled jobs or PSWorkflowJob for workflows jobs. This parameter isn't valid fo... |
| `-WorkingDirectory` | `Object` | No | Specifies the initial working directory of the background job. If the parameter isn't specified, the job runs from the default location. The default location is the current working directory of the... |

**Patterns & Best Practices:**

**`ForEach-Object -Parallel` is the PS7 way.** It uses runspaces, is far lighter than `Start-Job`, and is the default choice for parallel iteration. Use `Start-ThreadJob` when you need a job object without process isolation. Reserve `Start-Job` only when you need full process isolation.


**Patterns & Best Practices:**

| Feature | `ForEach-Object -Parallel` | `Start-ThreadJob` | `Start-Job` |
|---------|---------------------------|-------------------|-------------|
| Execution | Runspace pool | Single runspace | Separate process |
| Overhead | Low | Low | High |
| Serialization | No (same process) | No (same process) | Yes (cross-process) |
| `$using:` | Yes (read-only) | Yes | Yes (serialized) |
| Pipeline input | Yes (`$_`) | No | No |
| Job object | Only with `-AsJob` | Always | Always |
| Default throttle | 5 | Manual | Manual |
| Memory per unit | ~2-5 MB | ~2-5 MB | ~30-80 MB |
| Startup time | Milliseconds | Milliseconds | Seconds |


---

### Stop-Job

Stops a PowerShell background job.

The `Stop-Job` cmdlet stops PowerShell background jobs that are in progress. You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to `Stop-Job`.

**Returns**: `None`

```
Stop-Job
    [-Confirm <Object>]
    -Filter <Object>
    -Id <Object>
    -InstanceId <Object>
    -Job <Object>
    -Name <Object>
    [-PassThru <Object>]
    -State <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Filter` | `Object` | Yes | Specifies a hash table of conditions. This cmdlet stops jobs that satisfy every condition. Enter a hash table where the keys are job properties and the values are job property values.   This parame... |
| `-Id` | `Object` | Yes | Specifies the IDs of jobs that this cmdlet stops. The default is all jobs in the current session.   The ID is an integer that uniquely identifies the job in the current session. It is easier to rem... |
| `-InstanceId` | `Object` | Yes | Specifies the instance IDs of jobs that this cmdlet stops. The default is all jobs.   An instance ID is a GUID that uniquely identifies the job on the computer. To find the instance ID of a job, us... |
| `-Job` | `Object` | Yes | Specifies the jobs that this cmdlet stops. Enter a variable that contains the jobs or a command that gets the jobs. You can also use a pipeline operator to submit jobs to the `Stop-Job` cmdlet. By ... |
| `-Name` | `Object` | Yes | Specifies friendly names of jobs that this cmdlet stops. Enter the job names in a comma-separated list or use wildcard characters (`*`) to enter a job name pattern. By default, `Stop-Job` stops all... |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-State` | `Object` | Yes | Specifies a job state. This cmdlet stops only jobs in the specified state. The acceptable values for this parameter are:   - `NotStarted` - `Running` - `Completed` - `Failed` - `Stopped` - `Blocked... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Switch-Process

On Linux and macOS, the cmdlet calls the `execv()` function to provide similar behavior as POSIX
shells.

Some native Unix commands shell out to run something (like ssh) and use the `bash` built-in command `exec` to spawn a new process that replaces the current one. By default, `exec` isn't a valid command in PowerShell. This is affecting some known scripts like `copy-ssh-id` and some subcommands of AzCLI.

**Returns**: `System.Object`

```
Switch-Process
    [-WithCommand <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-WithCommand` | `Object` | No | Specifies the native executable (and any parameters) to be run. All additional values passed as arguments are passed as an array of strings to be executed with the first command.   The target comma... |

---

### Test-ModuleManifest

Verifies that a module manifest file accurately describes the contents of a module.

The `Test-ModuleManifest` cmdlet verifies that the files that are listed in the module manifest (`.psd1`) file are actually in the specified paths.

**Returns**: `System.Management.Automation.PSModuleInfo`

```
Test-ModuleManifest
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Path` | `Object` | Yes | Specifies a path and file name for the manifest file. Enter an optional path and name of the module manifest file that has the `.psd1` file name extension. The default location is the current direc... |

---

### Update-Help

Downloads and installs the newest help files on your computer.

The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer. You need not restart PowerShell to make the change effective. You can use the `Get-Help` cmdlet to view the new help files immediately.

**Returns**: `None`

```
Update-Help
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Force <Object>]
    [-FullyQualifiedModule <Object>]
    [-LiteralPath <Object>]
    [-Module <Object>]
    [-Recurse <Object>]
    [-Scope <Object>]
    [-SourcePath <Object>]
    [-UICulture <Object>]
    [-UseDefaultCredentials <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies credentials of a user who has permission to access the file system location specified by **SourcePath**. This parameter is valid only when the **SourcePath** or **LiteralPath** parameter ... |
| `-Force` | `Object` | No | Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.   Without this parameter, `Update-Help` runs only once... |
| `-FullyQualifiedModule` | `Object` | No | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-LiteralPath` | `Object` | No | Specifies the folder for updated help files instead of downloading them from the internet. Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a dir... |
| `-Module` | `Object` | No | Updates help for the specified modules. Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line. Wildcard characters are... |
| `-Recurse` | `Object` | No | Performs a recursive search for help files in the specified directory. This parameter is valid only when the command uses the **SourcePath** parameter. |
| `-Scope` | `Object` | No | Specifies the system scope where help is updated. Updates at the **AllUsers** scope require administrative privileges on Windows systems. The `-Scope` parameter was introduced in PowerShell Core ve... |
| `-SourcePath` | `Object` | No | Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet. Enter the path of a folder. Don't specify a file name or file name extensi... |
| `-UICulture` | `Object` | No | Specifies UI culture values for which this cmdlet gets updated help files. Enter one or more language codes, such as `es-ES`, a variable that contains culture objects, or a command that gets cultur... |
| `-UseDefaultCredentials` | `Object` | No | Indicates that `Update-Help` runs the command, including the internet download, using the credentials of the current user. By default, the command runs without explicit credentials.   This paramete... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Wait-Job

Waits until one or all of the PowerShell jobs running in the session are in a terminating state.

The `Wait-Job` cmdlet waits for a job to be in a terminating state before continuing execution. The terminating states are:

**Returns**: `System.Management.Automation.PSRemotingJob`

```
Wait-Job
    [-Any <Object>]
    -Filter <Object>
    [-Force <Object>]
    -Id <Object>
    -InstanceId <Object>
    -Job <Object>
    -Name <Object>
    -State <Object>
    [-Timeout <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Any` | `Object` | No | Indicates that this cmdlet returns the job object and continues execution when any job finishes. By default, `Wait-Job` waits until all of the specified jobs are complete before it displays the pro... |
| `-Filter` | `Object` | Yes | Specifies a hash table of conditions. This cmdlet waits for jobs that satisfy all of the conditions in the hash table. Enter a hash table where the keys are job properties and the values are job pr... |
| `-Force` | `Object` | No | Indicates that this cmdlet continues to wait for jobs in the Suspended or Disconnected state. By default, `Wait-Job` returns, or ends the wait, when jobs are in one of the following states:   - Com... |
| `-Id` | `Object` | Yes | Specifies an array of IDs of jobs for which this cmdlet waits.   The ID is an integer that uniquely identifies the job in the current session. It is easier to remember and type than the instance ID... |
| `-InstanceId` | `Object` | Yes | Specifies an array of instance IDs of jobs for which this cmdlet waits. The default is all jobs.   An instance ID is a GUID that uniquely identifies the job on the computer. To find the instance ID... |
| `-Job` | `Object` | Yes | Specifies the jobs for which this cmdlet waits. Enter a variable that contains the job objects or a command that gets the job objects. You can also use a pipeline operator to send job objects to th... |
| `-Name` | `Object` | Yes | Specifies friendly names of jobs for which this cmdlet waits. |
| `-State` | `Object` | Yes | Specifies a job state. This cmdlet waits only for jobs in the specified state. The acceptable values for this parameter are:   - NotStarted - Running - Completed - Failed - Stopped - Blocked - Susp... |
| `-Timeout` | `Object` | No | Specifies the maximum wait time for each job, in seconds. The default value, -1, indicates that the cmdlet waits until the job finishes. The timing starts when you submit the `Wait-Job` command, no... |

---

### Where-Object

Selects objects from a collection based on their property values.

The `Where-Object` cmdlet selects objects that have particular property values from the collection of objects that are passed to it. For example, you can use the `Where-Object` cmdlet to select files that were created after a certain date, events with a particular ID, or computers that use a particular version of Windows.

**Returns**: `System.Object`

```
Where-Object
    -CContains <Object>
    -CEQ <Object>
    -CGE <Object>
    -CGT <Object>
    -CIn <Object>
    -CLE <Object>
    -CLike <Object>
    -CLT <Object>
    -CMatch <Object>
    -CNE <Object>
    -CNotContains <Object>
    -CNotIn <Object>
    -CNotLike <Object>
    -CNotMatch <Object>
    -Contains <Object>
    [-EQ <Object>]
    -FilterScript <Object>
    -GE <Object>
    -GT <Object>
    -In <Object>
    [-InputObject <Object>]
    -Is <Object>
    -IsNot <Object>
    -LE <Object>
    -Like <Object>
    -LT <Object>
    -Match <Object>
    -NE <Object>
    -Not <Object>
    -NotContains <Object>
    -NotIn <Object>
    -NotLike <Object>
    -NotMatch <Object>
    -Property <Object>
    [-Value <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CContains` | `Object` | Yes | Indicates that this cmdlet gets objects from a collection if the property value of the object is an exact match for the specified value. This operation is case-sensitive.   For example: `Get-Proces... |
| `-CEQ` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is the same as the specified value. This operation is case-sensitive.   This parameter was introduced in Windows PowerShell 3.0. |
| `-CGE` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value. This operation is case-sensitive.   This parameter was introduced in Windows PowerShel... |
| `-CGT` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is greater than the specified value. This operation is case-sensitive.   This parameter was introduced in Windows PowerShell 3.0. |
| `-CIn` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value includes the specified value. This operation is case-sensitive.   For example: `Get-Process | Where-Object -Value "svchost" -CIn Proces... |
| `-CLE` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is less-than or equal to the specified value. This operation is case-sensitive.   This parameter was introduced in Windows PowerShell 3.0. |
| `-CLike` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters (`*`). This operation is case-sensitive.   For example: `Get-Process | Where-Object P... |
| `-CLT` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is less-than the specified value. This operation is case-sensitive.   This parameter was introduced in Windows PowerShell 3.0. |
| `-CMatch` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value matches the specified regular expression. This operation is case-sensitive. When the input is a single object, the matched value is sav... |
| `-CNE` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is different than the specified value. This operation is case-sensitive.   This parameter was introduced in Windows PowerShell 3.0. |
| `-CNotContains` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value of the object isn't an exact match for the specified value. This operation is case-sensitive.   For example: `Get-Process | Where-Objec... |
| `-CNotIn` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value isn't an exact match for the specified value. This operation is case-sensitive.   For example: `Get-Process | Where-Object -Value "svch... |
| `-CNotLike` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value doesn't match a value that includes wildcard characters. This operation is case-sensitive.   For example: `Get-Process | Where-Object P... |
| `-CNotMatch` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value doesn't match the specified regular expression. This operation is case-sensitive. When the input is a single object, the matched value ... |
| `-Contains` | `Object` | Yes | Indicates that this cmdlet gets objects if any item in the property value of the object is an exact match for the specified value.   For example: `Get-Process | Where-Object ProcessName -Contains "... |
| `-EQ` | `Object` | No | Indicates that this cmdlet gets objects if the property value is the same as the specified value.   This parameter was introduced in Windows PowerShell 3.0. |
| `-FilterScript` | `Object` | Yes | Specifies the scriptblock that's used to filter the objects. Enclose the scriptblock in braces (`{}`).   The parameter name, **FilterScript**, is optional. |
| `-GE` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is greater than or equal to the specified value.   This parameter was introduced in Windows PowerShell 3.0. |
| `-GT` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is greater than the specified value.   This parameter was introduced in Windows PowerShell 3.0. |
| `-In` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value matches any of the specified values. For example:   `Get-Process | Where-Object -Property ProcessName -In -Value "Svchost", "TaskHost",... |
| `-InputObject` | `Object` | No | Specifies the objects to filter. You can also pipe the objects to `Where-Object`.   When you use the **InputObject** parameter with `Where-Object`, instead of piping command results to `Where-Objec... |
| `-Is` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is an instance of the specified .NET type. Enclose the type name in square brackets.   For example, `Get-Process | Where-Object StartTi... |
| `-IsNot` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value isn't an instance of the specified .NET type.   For example, `Get-Process | where StartTime -IsNot [datetime]`   This parameter was int... |
| `-LE` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is less than or equal to the specified value.   This parameter was introduced in Windows PowerShell 3.0. |
| `-Like` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value matches a value that includes wildcard characters (`*`).   For example: `Get-Process | Where-Object ProcessName -Like "*host"`   This p... |
| `-LT` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is less than the specified value.   This parameter was introduced in Windows PowerShell 3.0. |
| `-Match` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value matches the specified regular expression. When the input is a single object, the matched value is saved in the `$Matches` automatic var... |
| `-NE` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value is different than the specified value.   This parameter was introduced in Windows PowerShell 3.0. |
| `-Not` | `Object` | Yes | Indicates that this cmdlet gets objects if the property doesn't exist or has a value of `$null` or `$false`.   For example: `Get-Service | Where-Object -Not "DependentServices"`   This parameter wa... |
| `-NotContains` | `Object` | Yes | Indicates that this cmdlet gets objects if none of the items in the property value is an exact match for the specified value.   For example: `Get-Process | Where-Object ProcessName -NotContains "Sv... |
| `-NotIn` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value isn't an exact match for any of the specified values.   For example: `Get-Process | Where-Object -Value "svchost" -NotIn -Property Proc... |
| `-NotLike` | `Object` | Yes | Indicates that this cmdlet gets objects if the property value doesn't match a value that includes wildcard characters (`*`).   For example: `Get-Process | Where-Object ProcessName -NotLike "*host"`... |
| `-NotMatch` | `Object` | Yes | Indicates that this cmdlet gets objects when the property value doesn't match the specified regular expression. When the input is a single object, the matched value is saved in the `$Matches` autom... |
| `-Property` | `Object` | Yes | Specifies the name of a property of the input object. The property must be an instance property, not a static property. This is a positional parameter, so the name, **Property**, is optional.   Thi... |
| `-Value` | `Object` | No | Specifies a property value. The parameter name, **Value**, is optional. This parameter accepts wildcard characters when used with the following comparison parameters:   - **CLike** - **CNotLike** -... |

**Patterns & Best Practices:**

**PowerShell passes .NET objects through the pipeline, not strings.** Every command emits objects with typed properties and methods. Never parse text when you can access object properties directly.

```powershell
Get-Process | grep "chrome"
Get-Process | Where-Object ProcessName -eq 'chrome'
(Get-Process -Name chrome).WorkingSet64   # Returns [long], not a string
```


**Patterns & Best Practices:**

**Patterns & Best Practices:**

Any function that modifies state should support `-WhatIf` and `-Confirm`:

```powershell
function Remove-OldLogs {
    [CmdletBinding(SupportsShouldProcess)]
    param(
        [Parameter(Mandatory)]
        [string]$Path,
        [int]$DaysOld = 30
    )

    $cutoff = (Get-Date).AddDays(-$DaysOld)
    $files = Get-ChildItem $Path -Filter '*.log' | Where-Object { $_.LastWriteTime -lt $cutoff }

    foreach ($file in $files) {
        if ($PSCmdlet.ShouldProcess($file.FullName, 'Delete')) {
            Remove-Item $file.FullName
        }
    }
}

Remove-OldLogs -Path 'C:\Logs' -WhatIf     # Preview only
Remove-OldLogs -Path 'C:\Logs' -Confirm     # Prompt per item
```

**ShouldProcess signatures**: `ShouldProcess($target)`, `ShouldProcess($target, $action)`, `ShouldProcess($verboseDesc, $warning, $caption)`.

**ConfirmImpact** controls auto-prompting: `High` prompts when `$ConfirmPreference` is `High` or `Medium` (default). `Low` never auto-prompts.

**ShouldContinue** is for additional confirmation beyond `-Confirm` (always prompts):

```powershell
if ($PSCmdlet.ShouldProcess($target, 'Delete')) {
    if ($Force -or $PSCmdlet.ShouldContinue("Permanently delete '$target'?", 'Confirm')) {
        Remove-Item $target -Force
    }
}
```


### 1. Hardcoding backslash path separators
```powershell
$path = "$HOME\Documents\file.txt"    # WRONG — \ is literal on Linux
$path = Join-Path $HOME 'Documents' 'file.txt'  # RIGHT
```

### 2. Using $env:USERPROFILE on Linux (it's null)
```powershell
Join-Path $env:USERPROFILE '.config'   # WRONG — null on Linux
Join-Path $HOME '.config'              # RIGHT — works everywhere
```

### 3. Using CIM/WMI in cross-platform scripts
```powershell
$os = Get-CimInstance Win32_OperatingSystem   # CRASHES on Linux
```

### 4. Assuming $IsWindows exists in PS 5.1
```powershell
if ($IsWindows) { ... }   # NEVER TRUE in PS 5.1 ($IsWindows is undefined/null)
```

### 5. Hardcoding PATH separator
```powershell
$env:PATH += ";/usr/local/bin"                            # WRONG
$env:PATH += [IO.Path]::PathSeparator + '/usr/local/bin'  # RIGHT
```

### 6. Using .exe extension in cross-platform scripts
```powershell
& git.exe status       # WRONG on Linux
& git status           # RIGHT — PS resolves .exe on Windows automatically
```

### 7. Assuming case-insensitive filesystem
```powershell
Test-Path './Config.JSON'    # FALSE on Linux if file is config.json
Get-ChildItem . | Where-Object { $_.Name -like 'config.json' }
```

### 8. Using Windows-specific paths without guards
```powershell
$logPath = 'C:\Logs\app.log'    # WRONG — C:\ doesn't exist on Linux
$logPath = if ($IsWindows) {
    Join-Path $env:ProgramData 'MyApp' 'Logs' 'app.log'
} else {
    Join-Path '/var/log' 'myapp' 'app.log'
}
```

### 9. Relying on Windows line endings
```powershell
$lines = $text -split "`r`n"    # WRONG — misses LF-only on Linux
$lines = $text -split '\r?\n'   # RIGHT — handles both
```

### 10. Using Registry provider in cross-platform modules
```powershell
Get-ItemProperty 'HKCU:\Software\MyApp' -Name 'Setting'

if ($IsWindows) {
    (Get-ItemProperty 'HKCU:\Software\MyApp' -Name 'Setting').Setting
} else {
    $f = Join-Path $HOME '.config' 'myapp' 'settings.json'
    if (Test-Path $f) { (Get-Content $f -Raw | ConvertFrom-Json).Setting }
}
```


---

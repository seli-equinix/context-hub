---
name: pwsh-management
description: "PowerShell 7.5 Management cmdlets — files, paths, processes, services, registry, environment, clipboard, PSDrives, event logs"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Add-Content,Clear-Content,Clear-Item,Clear-ItemProperty,Convert-Path,Copy-Item,Copy-ItemProperty,Debug-Process,Get-ChildItem,Get-Clipboard,Get-Content,Get-Item,Get-ItemProperty,Get-ItemPropertyValue,Get-Location,Get-PSDrive,Get-PSProvider,Get-Process,Get-TimeZone,Invoke-Item,Join-Path,Move-Item,Move-ItemProperty,New-Item,New-ItemProperty,New-PSDrive,Pop-Location,Push-Location,Remove-Item,Remove-ItemProperty,Remove-PSDrive,Rename-Item,Rename-ItemProperty,Resolve-Path,Restart-Computer,Set-Clipboard,Set-Content,Set-Item,Set-ItemProperty,Set-Location,Split-Path,Start-Process,Stop-Computer,Stop-Process,Test-Connection,Test-Path,Wait-Process"
---

# PowerShell 7.5 — files

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-Content` | Adds content to the specified items, such as adding words to a file. |
| `Clear-Content` | Deletes the contents of an item, but does not delete the item. |
| `Clear-Item` | Clears the contents of an item, but does not delete the item. |
| `Clear-ItemProperty` | Clears the value of a property but does not delete the property. |
| `Convert-Path` | Converts a path from a PowerShell path to a PowerShell provider path. |
| `Copy-Item` | Copies an item from one location to another. |
| `Copy-ItemProperty` | Copies a property and value from a specified location to another location. |
| `Debug-Process` | Debugs one or more processes running on the local computer. |
| `Get-ChildItem` | Gets the items and child items in one or more specified locations. |
| `Get-Clipboard` | Gets the contents of the clipboard. |
| `Get-Content` | Gets the content of the item at the specified location. |
| `Get-Item` | Gets the item at the specified location. |
| `Get-ItemProperty` | Gets the properties of a specified item. |
| `Get-ItemPropertyValue` | Gets the value for one or more properties of a specified item. |
| `Get-Location` | Gets information about the current working location or a location stack. |
| `Get-PSDrive` | Gets drives in the current session. |
| `Get-PSProvider` | Gets information about the specified PowerShell provider. |
| `Get-Process` | Gets the processes that are running on the local computer. |
| `Get-TimeZone` | Gets the current time zone or a list of available time zones. |
| `Invoke-Item` | Performs the default action on the specified item. |
| `Join-Path` | Combines a path and a child path into a single path. |
| `Move-Item` | Moves an item from one location to another. |
| `Move-ItemProperty` | Moves a property from one location to another. |
| `New-Item` | Creates a new item. |
| `New-ItemProperty` | Creates a new property for an item and sets its value. |
| `New-PSDrive` | Creates temporary and persistent drives that are associated with a location in an item data store. |
| `Pop-Location` | Changes the current location to the location most recently pushed onto the stack. |
| `Push-Location` | Adds the current location to the top of a location stack. |
| `Remove-Item` | Deletes the specified items. |
| `Remove-ItemProperty` | Deletes the property and its value from an item. |
| `Remove-PSDrive` | Deletes temporary PowerShell drives and disconnects mapped network drives. |
| `Rename-Item` | Renames an item in a PowerShell provider namespace. |
| `Rename-ItemProperty` | Renames a property of an item. |
| `Resolve-Path` | Resolves the wildcard characters in a path, and displays the path contents. |
| `Restart-Computer` | Restarts the operating system on local and remote computers. |
| `Set-Clipboard` | Sets the contents of the clipboard. |
| `Set-Content` | Writes new content or replaces existing content in a file. |
| `Set-Item` | Changes the value of an item to the value specified in the command. |
| `Set-ItemProperty` | Creates or changes the value of a property of an item. |
| `Set-Location` | Sets the current working location to a specified location. |
| `Split-Path` | Returns the specified part of a path. |
| `Start-Process` | Starts one or more processes on the local computer. |
| `Stop-Computer` | Stops (shuts down) local and remote computers. |
| `Stop-Process` | Stops one or more running processes. |
| `Test-Connection` | Sends ICMP echo request packets, or pings, to one or more computers. |
| `Test-Path` | Determines whether all elements of a path exist. |
| `Wait-Process` | Waits for the processes to be stopped before accepting more input. |

---

### Add-Content

Adds content to the specified items, such as adding words to a file.

The `Add-Content` cmdlet appends content to a specified item or file. Content can be passed in from the pipeline or specified by using the **Value** parameter.

**Returns**: `None`

```
Add-Content
    [-AsByteStream <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Encoding <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-NoNewline <Object>]
    [-PassThru <Object>]
    -Path <Object>
    [-Stream <Object>]
    -Value <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsByteStream` | `Object` | No | Specifies that the content should be read as a stream of bytes. This parameter was introduced in PowerShell 6.0.   A warning occurs when you use the **AsByteStream** parameter with the **Encoding**... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](..... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   Encoding is a dynamic parameter that the FileSystem provider adds to the `Add-Content` cmdlet. This parameter... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Overrides the read-only attribute, allowing you to add content to a read-only file. For example, **Force** overrides the read-only attribute but it doesn't change file permissions. |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-NoNewline` | `Object` | No | Indicates that this cmdlet doesn't add a new line or carriage return to the content.   The string representations of the input objects are concatenated to form the output. No spaces or newlines are... |
| `-PassThru` | `Object` | No | Returns an object representing the added content. By default, this cmdlet doesn't generate any output. |
| `-Path` | `Object` | Yes | Specifies the path to the items that receive the additional content. Wildcard characters are permitted. The paths must be paths to items, not to containers. For example, you must specify a path to ... |
| `-Stream` | `Object` | No | > [!NOTE] > This Parameter is only available on Windows.   Specifies an alternative data stream for content. If the stream doesn't exist, this cmdlet creates it. Wildcard characters aren't supporte... |
| `-Value` | `Object` | Yes | Specifies the content to be added. Type a quoted string, such as **This data is for internal use only**, or specify an object that contains content, such as the **DateTime** object that `Get-Date` ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Clear-Content

Deletes the contents of an item, but does not delete the item.

The `Clear-Content` cmdlet deletes the contents of an item, such as deleting the text from a file, but it does not delete the item. As a result, the item exists, but it is empty. `Clear-Content` is similar to `Clear-Item`, but it works on items with contents, instead of items with values.

**Returns**: `None`

```
Clear-Content
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-Stream <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use `Invoke-Command`. |
| `-Exclude` | `Object` | No | Specifies, as a string array, strings that this cmdlet omits from the path to the content. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter in the provider's format or language. The value of this parameter qualifies the **Path** parameter. The syntax of the filter, including the use of wildcards, depends on the provi... |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation. |
| `-Include` | `Object` | No | Specifies, as a string array, content that this cmdlet clears. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.txt`. Wildcards are permitted. |
| `-LiteralPath` | `Object` | Yes | Specifies the paths to the items from which content is deleted. Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcard... |
| `-Path` | `Object` | Yes | Specifies the paths to the items from which content is deleted. Wildcards are permitted. The paths must be paths to items, not to containers. For example, you must specify a path to one or more fil... |
| `-Stream` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. This parameter is only available on Windows.   Specifies an alternative data stream for content. If the stream does not ex... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Clear-Item

Clears the contents of an item, but does not delete the item.

The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item. For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable. The value that used to represent a cleared item is defined by each PowerShell provider. This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.

**Returns**: `None`

```
Clear-Item
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases. The cmdlet cannot clear constants. Implementation varies from provider to provider. For more inf... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Path` | `Object` | Yes | Specifies the path to the items being cleared. Wildcard characters are permitted. This parameter is required, but the parameter name **Path** is optional. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Clear-ItemProperty

Clears the value of a property but does not delete the property.

The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property. You can use this cmdlet to delete the data from a registry value.

**Returns**: `None`

```
Clear-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user. Implementation varies from provider to provider. For more information, see [about_Providers](... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies the name of the property to be cleared, such as the name of a registry value. Wildcard characters are permitted. |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path to the property being cleared. Wildcard characters are permitted. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Convert-Path

Converts a path from a PowerShell path to a PowerShell provider path.

The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.

**Returns**: `System.String`

```
Convert-Path
    [-Force <Object>]
    -LiteralPath <Object>
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `Object` | No | Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files. The **Force** parameter doesn't override security restrictions. Implementation varies am... |
| `-LiteralPath` | `Object` | Yes | Specifies, as a string array, the path to be converted. The value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes es... |
| `-Path` | `Object` | Yes | Specifies the PowerShell path to be converted. |

---

### Copy-Item

Copies an item from one location to another.

The `Copy-Item` cmdlet copies an item from one location to another location in the same namespace. For instance, it can copy a file to a folder, but it can't copy a file to a certificate drive.

**Returns**: `None`

```
Copy-Item
    [-Confirm <Object>]
    [-Container <Object>]
    [-Credential <Object>]
    [-Destination <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-FromSession <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-Recurse <Object>]
    [-ToSession <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Container` | `Object` | No | Indicates that this cmdlet preserves container objects during the copy operation. By default, the **Container** parameter is set to **True**. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](..... |
| `-Destination` | `Object` | No | Specifies the path to the new location. The default is the current directory.   To rename the item being copied, specify a new name in the value of the **Destination** parameter. |
| `-Exclude` | `Object` | No | Specifies one or more path elements or patterns, such as `"*.txt"`, to limit this cmdlet's operation. The value of this parameter filters against the wildcard-matching result of the **Path** parame... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Indicates that this cmdlet copies items that can't otherwise be changed, such as copying over a read-only file or alias. |
| `-FromSession` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider.   Specify the **PSSession** object from which a remote file is being copied. When you use this parameter, the **Path** and... |
| `-Include` | `Object` | No | Specifies one or more path elements or patterns, such as `"*.txt"`, to limit this cmdlet's operation. The value of this parameter filters against the wildcard-matching result of the **Path** parame... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-PassThru` | `Object` | No | Returns an object that represents the item with which you're working. By default, this cmdlet doesn't generate any output. |
| `-Path` | `Object` | Yes | Specifies, as a string array, the path to the items to copy. Wildcard characters are permitted. |
| `-Recurse` | `Object` | No | Indicates that this cmdlet does a recursive copy. |
| `-ToSession` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider.   Specify the **PSSession** object to which a remote file is being copied. When you use this parameter, the **Destination*... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Copy-ItemProperty

Copies a property and value from a specified location to another location.

The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location. For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.

**Returns**: `None`

```
Copy-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    -Destination <Object>
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Destination` | `Object` | Yes | Specifies the path to the destination location. |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation. Implementation varies from provider to provider.   For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/abo... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies the name of the property to be copied. |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies, as a string array, the path to the property to be copied. Wildcard characters are permitted. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Debug-Process

Debugs one or more processes running on the local computer.

The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer. You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.

**Returns**: `None`

```
Debug-Process
    [-Confirm <Object>]
    -Id <Object>
    -InputObject <Object>
    -Name <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | Yes | Specifies the process IDs of the processes to be debugged. The **Id** parameter name is optional.   To find the process ID of a process, type `Get-Process`. |
| `-InputObject` | `Object` | Yes | Specifies the process objects that represent processes to be debugged. Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdle... |
| `-Name` | `Object` | Yes | Specifies the names of the processes to be debugged. If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name. The **Name** parameter is... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Get-ChildItem

Gets the items and child items in one or more specified locations.

The `Get-ChildItem` cmdlet gets the items in one or more specified locations. If the item is a container, it gets the items inside the container, known as child items. You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.

**Returns**: `System.Management.Automation.AliasInfo`

```
Get-ChildItem
    [-Attributes <Object>]
    [-CodeSigningCert <Object>]
    [-Depth <Object>]
    [-Directory <Object>]
    [-DnsName <Object>]
    [-DocumentEncryptionCert <Object>]
    [-Eku <Object>]
    [-Exclude <Object>]
    [-ExpiringInDays <Object>]
    [-File <Object>]
    [-Filter <Object>]
    [-FollowSymlink <Object>]
    [-Force <Object>]
    [-Hidden <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-Name <Object>]
    [-Path <Object>]
    [-ReadOnly <Object>]
    [-Recurse <Object>]
    [-SSLServerAuthentication <Object>]
    [-System <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Attributes` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   Gets files and folders with the specified attributes.... |
| `-CodeSigningCert` | `Object` | No | > [!NOTE] > This parameter is only available in the > [Certificate](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md) provider.   To get a list of certificates that have `Code S... |
| `-Depth` | `Object` | No | This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion. By default, `Get-ChildItem` displays the contents of the parent directory. The **Depth** parameter dete... |
| `-Directory` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   To get a list of directories, use the **Directory** p... |
| `-DnsName` | `Object` | No | > [!NOTE] > This parameter is only available in the > [Certificate](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md) provider.   Specifies a domain name or name pattern to matc... |
| `-DocumentEncryptionCert` | `Object` | No | > [!NOTE] > This parameter is only available in the > [Certificate](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md) provider.   To get a list of certificates that have `Docume... |
| `-Eku` | `Object` | No | > [!NOTE] > This parameter is only available in the > [Certificate](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md) provider.   Specifies text or a text pattern to match with ... |
| `-Exclude` | `Object` | No | Specifies an array of one or more string patterns to be matched as the cmdlet gets child items. Any matching item is excluded from the output. Enter a path element or pattern, such as `*.txt` or `A... |
| `-ExpiringInDays` | `Object` | No | > [!NOTE] > This parameter is only available in the > [Certificate](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md) provider.   Specifies that the cmdlet should only return ce... |
| `-File` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   To get a list of files, use the **File** parameter. Y... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-FollowSymlink` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   By default, the `Get-ChildItem` cmdlet displays symbo... |
| `-Force` | `Object` | No | Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files. The **Force** parameter doesn't override security restrictions. Implementation varies by... |
| `-Hidden` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   To get only hidden items, use the **Hidden** paramete... |
| `-Include` | `Object` | No | Specifies an array of one or more string patterns to be matched as the cmdlet gets child items. Any matching item is included in the output. Enter a path element or pattern, such as `"*.txt"`. Wild... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-Name` | `Object` | No | Gets only the names of the items in the location. The output is a string object that can be sent down the pipeline to other commands. The names returned are relative to the value of the **Path** pa... |
| `-Path` | `Object` | No | Specifies a path to one or more locations. If not specified, the default location is the current directory (`.`). Wildcards are accepted. Use care when using the **Path** parameter with the **Recur... |
| `-ReadOnly` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   To get only read-only items, use the **ReadOnly** par... |
| `-Recurse` | `Object` | No | Gets the items in the specified locations and in all child items of the locations. |
| `-SSLServerAuthentication` | `Object` | No | > [!NOTE] > This parameter is only available in the > [Certificate](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md) provider.   To get a list of certificates that have `Server... |
| `-System` | `Object` | No | > [!NOTE] > This parameter is only available in the > [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider.   Gets only system files and directories. To get only s... |

---

### Get-Clipboard

Gets the contents of the clipboard.

The `Get-Clipboard` cmdlet gets the contents of the clipboard as text. Multiple lines of text are returned as an array of strings similar to `Get-Content`.

**Returns**: `System.String`

```
Get-Clipboard
    [-Raw <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Raw` | `Object` | No | Gets the entire contents of the clipboard. Multiline text is returned as a single multiline string rather than an array of strings. |

---

### Get-Content

Gets the content of the item at the specified location.

The `Get-Content` cmdlet gets the content of the item at the location specified by the path, such as the text in a file or the content of a function. For files, the content is read one line at a time and returns a collection of objects, each representing a line of content.

**Returns**: `System.Byte`

```
Get-Content
    [-AsByteStream <Object>]
    [-Credential <Object>]
    [-Delimiter <Object>]
    [-Encoding <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-Raw <Object>]
    [-ReadCount <Object>]
    [-Stream <Object>]
    [-Tail <Object>]
    [-TotalCount <Object>]
    [-Wait <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsByteStream` | `Object` | No | Specifies that the content should be read as a stream of bytes. The **AsByteStream** parameter was introduced in Windows PowerShell 6.0.   A warning occurs when you use the **AsByteStream** paramet... |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use > [Invoke-Command](..... |
| `-Delimiter` | `Object` | No | Specifies the delimiter that `Get-Content` uses to divide the file into objects while it reads. The default is `\n`, the end-of-line character. When reading a text file, `Get-Content` returns a col... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter.   Enter a path element or pattern, such as `... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | **Force** can override a read-only attribute or create directories to complete a file path. The **Force** parameter doesn't attempt to change file permissions or override security restrictions. |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-Path` | `Object` | Yes | Specifies the path to an item where `Get-Content` gets the content. Wildcard characters are permitted. The paths must be paths to items, not to containers. For example, you must specify a path to o... |
| `-Raw` | `Object` | No | Ignores newline characters and returns the entire contents of a file in one string with the newlines preserved. By default, newline characters in a file are used as delimiters to separate the input... |
| `-ReadCount` | `Object` | No | Specifies how many lines of content are sent through the pipeline at a time. The default value is 1. A value of 0 (zero) or negative numbers sends all the content at one time.   This parameter does... |
| `-Stream` | `Object` | No | > [!NOTE] > This Parameter is only available on Windows.   Gets the contents of the specified alternate NTFS file stream from the file. Enter the stream name. Wildcards aren't supported.   **Stream... |
| `-Tail` | `Object` | No | Specifies the number of lines from the end of a file or other item. You can use the **Tail** parameter name or its alias, **Last**. A value of `0` returns no lines. Negative values cause an error. ... |
| `-TotalCount` | `Object` | No | Specifies the number of lines from the beginning of a file or other item. A value of `0` returns no lines. Negative values cause an error.   You can use the **TotalCount** parameter name or its ali... |
| `-Wait` | `Object` | No | Causes the cmdlet to wait indefinitely, keeping the file open, until interrupted. While waiting, `Get-Content` checks the file once per second and outputs new lines if present. When used with the *... |

---

### Get-Item

Gets the item at the specified location.

The `Get-Item` cmdlet gets the item at the specified location. It doesn't get the contents of the item at the location unless you use a wildcard character (`*`) to request all the contents of the item.

**Returns**: `System.Management.Automation.AliasInfo`

```
Get-Item
    [-CodeSigningCert <Object>]
    [-Credential <Object>]
    [-DnsName <Object>]
    [-DocumentEncryptionCert <Object>]
    [-Eku <Object>]
    [-Exclude <Object>]
    [-ExpiringInDays <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-SSLServerAuthentication <Object>]
    [-Stream <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CodeSigningCert` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. This parameter and the **Certificate** provider are only available on Windows.   To get certificates that have `Code Sign... |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](..... |
| `-DnsName` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. This parameter and the **Certificate** provider are only available on Windows.   Specifies a domain name or name pattern ... |
| `-DocumentEncryptionCert` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. This parameter and the **Certificate** provider are only available on Windows.   To get certificates that have `Document ... |
| `-Eku` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. This parameter and the **Certificate** provider are only available on Windows.   Specifies text or a text pattern to matc... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-ExpiringInDays` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. This parameter and the **Certificate** provider are only available on Windows.   Specifies that the cmdlet should only re... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Indicates that this cmdlet gets items that can't otherwise be accessed, such as hidden items. Implementation varies from provider to provider. For more information, see [about_Providers](../Microso... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-Path` | `Object` | Yes | Specifies the path to an item. This cmdlet gets the item at the specified location. Wildcard characters are permitted. This parameter is required, but the parameter name **Path** is optional.   Use... |
| `-SSLServerAuthentication` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. This parameter and the **Certificate** provider are only available on Windows.   To get certificates that have `Server Au... |
| `-Stream` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. This parameter is only available on Windows.   Gets the specified alternative data stream from the file. Enter the stream ... |

---

### Get-ItemProperty

Gets the properties of a specified item.

The `Get-ItemProperty` cmdlet gets the properties of the specified items. For example, you can use this cmdlet to get the value of the **LastAccessTime** property of a file object. You can also use this cmdlet to view registry entries and their values.

**Returns**: `System.Boolean`

```
Get-ItemProperty
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-Name <Object>]
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use > [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | No | Specifies the name of the property or properties to retrieve. Wildcard characters are permitted. |
| `-Path` | `Object` | Yes | Specifies the path to the item or items. Wildcard characters are permitted. |

---

### Get-ItemPropertyValue

Gets the value for one or more properties of a specified item.

The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the **Name** parameter, located in a path that you specify with either the **Path** or **LiteralPath** parameters.

**Returns**: `System.Management.Automation.PSObject`

```
Get-ItemPropertyValue
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    [-Path <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies the name of the property or properties to retrieve. |
| `-Path` | `Object` | No | Specifies the path to the item or items. Wildcard characters are permitted. |

---

### Get-Location

Gets information about the current working location or a location stack.

The `Get-Location` cmdlet gets an object that represents the current directory, much like the print working directory (pwd) command.

**Returns**: `System.Management.Automation.PathInfo`

```
Get-Location
    [-PSDrive <Object>]
    [-PSProvider <Object>]
    [-Stack <Object>]
    [-StackName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PSDrive` | `Object` | No | Gets the current location in the specified PowerShell drive.   For instance, if you are in the `Cert:` drive, you can use this parameter to find your current location in the `C:` drive. |
| `-PSProvider` | `Object` | No | Gets the current location in the drive supported by the specified PowerShell provider. If the specified provider supports more than one drive, this cmdlet returns the location on the most recently ... |
| `-Stack` | `Object` | No | Indicates that this cmdlet displays the locations added to the current location stack. You can add locations to stacks by using the `Push-Location` cmdlet.   To display the locations in a different... |
| `-StackName` | `Object` | No | Specifies, as a string array, the named location stacks. Enter one or more location stack names.   To display the locations in the current location stack, use the **Stack** parameter. To make a loc... |

---

### Get-PSDrive

Gets drives in the current session.

The `Get-PSDrive` cmdlet gets the drives in the current session. You can get a particular drive or all drives in the session.

**Returns**: `System.Management.Automation.PSDriveInfo`

```
Get-PSDrive
    -LiteralName <Object>
    [-Name <Object>]
    [-PSProvider <Object>]
    [-Scope <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-LiteralName` | `Object` | Yes | Specifies the name of the drive.   The value of **LiteralName** is used exactly as it is typed. No characters are interpreted as wildcards. If the name includes escape characters, enclose it in sin... |
| `-Name` | `Object` | No | Specifies, as a string array, the name or name of drives that this cmdlet gets in the operation. Type the drive name or letter without a colon (`:`). |
| `-PSProvider` | `Object` | No | Specifies, as a string array, the Windows PowerShell provider. This cmdlet gets only the drives supported by this provider. Type the name of a provider, such as FileSystem, Registry, or Certificate. |
| `-Scope` | `Object` | No | Specifies the scope in which this cmdlet gets the drives.   The acceptable values for this parameter are:   - Global - Local - Script - a number relative to the current scope (0 through the number ... |

---

### Get-PSProvider

Gets information about the specified PowerShell provider.

The `Get-PSProvider` cmdlet gets the PowerShell providers in the current session. You can get a particular drive or all drives in the session.

**Returns**: `System.Management.Automation.ProviderInfo`

```
Get-PSProvider
    [-PSProvider <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PSProvider` | `Object` | No | Specifies the name or names of the PowerShell providers about which this cmdlet gets information. |

---

### Get-Process

Gets the processes that are running on the local computer.

The `Get-Process` cmdlet gets the processes on a local computer.

**Returns**: `System.Diagnostics.Process`

```
Get-Process
    [-FileVersionInfo <Object>]
    -Id <Object>
    -IncludeUserName <Object>
    -InputObject <Object>
    [-Module <Object>]
    [-Name <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-FileVersionInfo` | `Object` | No | Indicates that this cmdlet gets the file version information for the program that runs in the process.   On Windows Vista and later versions of Windows, you must run PowerShell with elevated user r... |
| `-Id` | `Object` | Yes | Specifies one or more processes by process ID (PID). You can specify multiple IDs separated by commas. To get the PID of a process, use `Get-Process`. To get the PID of the current PowerShell sessi... |
| `-IncludeUserName` | `Object` | Yes | Indicates that this command adds a **UserName** property to each returned **Process** object. |
| `-InputObject` | `Object` | Yes | Specifies one or more **Process** objects. Use a variable that contains the objects, or a command or expression that gets the objects. |
| `-Module` | `Object` | No | Indicates that this cmdlet gets the modules that the process has loaded.   On Windows Vista and later versions of Windows, you must run PowerShell with elevated user rights (**Run as administrator*... |
| `-Name` | `Object` | No | Specifies one or more processes by process name. You can specify multiple process names separated by commas and use wildcard characters. Using the `-Name` parameter is optional. |

---

### Get-TimeZone

Gets the current time zone or a list of available time zones.

> **This cmdlet is only available on the Windows platform.**

**Returns**: `System.TimeZoneInfo`

```
Get-TimeZone
    -Id <Object>
    -ListAvailable <Object>
    [-Name <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `Object` | Yes | Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets. |
| `-ListAvailable` | `Object` | Yes | Indicates that this cmdlet gets all available time zones. |
| `-Name` | `Object` | No | Specifies, as a string array, the name or names of the time zones that this cmdlet gets. |

---

### Invoke-Item

Performs the default action on the specified item.

The `Invoke-Item` cmdlet performs the default action on the specified item. For example, it runs an executable file or opens a document file in the application associated with the document file type. The default action depends on the type of item and is determined by the PowerShell provider that provides access to the data.

**Returns**: `None`

```
Invoke-Item
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-Path` | `Object` | Yes | Specifies the path to the selected item. Wildcard characters are permitted.   > [!IMPORTANT] > Using this parameter with untrusted data is a security risk. Only use trusted data with this > paramet... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Join-Path

Combines a path and a child path into a single path.

The `Join-Path` cmdlet combines a path and child-path into a single path. The provider supplies the path delimiters.

**Returns**: `System.String`

```
Join-Path
    [-AdditionalChildPath <Object>]
    -ChildPath <Object>
    [-Credential <Object>]
    -Path <Object>
    [-Resolve <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AdditionalChildPath` | `Object` | No | Specifies additional elements to append to the value of the **Path** parameter. The **ChildPath** parameter is still mandatory and must be specified as well. This parameter is specified with the `V... |
| `-ChildPath` | `Object` | Yes | Specifies the elements to append to the value of the `Path` parameter. Wildcards are permitted. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use > [Invoke-Command](..... |
| `-Path` | `Object` | Yes | Specifies the main path (or paths) to which the child-path is appended. The value of **Path** determines which provider joins the paths and adds the path delimiters. Wildcards are permitted. |
| `-Resolve` | `Object` | No | Indicates that this cmdlet should attempt to resolve the joined path from the current provider.   - If you use wildcards, the cmdlet returns all paths that match the joined path. - If you don't use... |

---

### Move-Item

Moves an item from one location to another.

The `Move-Item` cmdlet moves an item, including its properties, contents, and child items, from one location to another location. The locations must be supported by the same provider.

**Returns**: `None`

```
Move-Item
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Destination <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Destination` | `Object` | No | Specifies the path to the location where the items are being moved. The default is the current directory. Wildcards aren't permitted.   To rename the item being moved, specify a new name in the val... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation. Implementation varies from provider to provider. For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-PassThru` | `Object` | No | Returns an object representing the moved item. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path to the current location of the items. The default is the current directory. Wildcard characters are permitted. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Move-ItemProperty

Moves a property from one location to another.

The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item. For instance, it can move a registry entry from one registry key to another registry key. When you move an item property, it is added to the new location and deleted from its original location.

**Returns**: `None`

```
Move-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    -Destination <Object>
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Destination` | `Object` | Yes | Specifies the path to the destination location. |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation. Implementation varies from provider to provider. For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies the name of the property to be moved. |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path to the current location of the property. Wildcard characters are permitted. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### New-Item

Creates a new item.

The `New-Item` cmdlet creates a new item and sets its value. The types of items that can be created depend on the location of the item. For example, in the file system, `New-Item` creates files and folders. In the registry, `New-Item` creates registry keys and entries.

**Returns**: `System.Collections.DictionaryEntry`

```
New-Item
    [-ApplicationName <Object>]
    [-Authentication <Object>]
    [-CertificateThumbprint <Object>]
    [-Confirm <Object>]
    -ConnectionURI <Object>
    [-Credential <Object>]
    [-Force <Object>]
    [-ItemType <Object>]
    -Name <Object>
    [-Options <Object>]
    [-OptionSet <Object>]
    -Path <Object>
    -Port <Object>
    [-SessionOption <Object>]
    [-UseSSL <Object>]
    [-Value <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ApplicationName` | `Object` | No | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Specifies the application name in the connection. Th... |
| `-Authentication` | `Object` | No | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Specifies the authentication mechanism to be used at... |
| `-CertificateThumbprint` | `Object` | No | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Specifies the digital public key certificate (X509) ... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-ConnectionURI` | `Object` | Yes | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Specifies the connection endpoint for WSMan.   For m... |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. To impersonate another > user or elevate your credentials when running this cmdlet, use `Invoke-Command`. |
| `-Force` | `Object` | No | Forces this cmdlet to create an item that writes over an existing read-only item. Implementation varies from provider to provider. Even using the **Force** parameter, the cmdlet can't override secu... |
| `-ItemType` | `Object` | No | Specifies the provider-specified type of the new item. The available values of this parameter depend on the current provider you are using.   If your location is in a `FileSystem` drive, the follow... |
| `-Name` | `Object` | Yes | Specifies the name of the new item. You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.... |
| `-Options` | `Object` | No | This is a dynamic parameter made available by the **Alias** provider. For more information, see [New-Alias](../Microsoft.PowerShell.Utility/New-Alias.md).   Specifies the value of the **Options** p... |
| `-OptionSet` | `Object` | No | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Passes a set of switches to a service to modify or r... |
| `-Path` | `Object` | Yes | Specifies the path of the location of the new item. The default is the current location when **Path** is omitted. You can specify the name of the new item in **Name**, or include it in **Path**. It... |
| `-Port` | `Object` | Yes | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Specifies the port to use when the client connects t... |
| `-SessionOption` | `Object` | No | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Defines a set of extended options for the WS-Managem... |
| `-UseSSL` | `Object` | No | This is a dynamic parameter made available by the **WSMan** provider. The **WSMan** provider and this parameter are only available on Windows.   Specifies that the Secure Sockets Layer (SSL) protoc... |
| `-Value` | `Object` | No | Specifies the value of the new item. You can also pipe a value to `New-Item`. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### New-ItemProperty

Creates a new property for an item and sets its value.

The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value. Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.

**Returns**: `System.Management.Automation.PSCustomObject`

```
New-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    -Path <Object>
    [-PropertyType <Object>]
    [-Value <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies a user account that has permission to perform this action. The default is the current user.   Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, ... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user. Implementation varies from provider to provider. For more information, see [about_Providers](../Mi... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies a name for the new property. If the property is a registry entry, this parameter specifies the name of the entry. |
| `-Path` | `Object` | Yes | Specifies the path of the item. Wildcard characters are permitted. This parameter identifies the item to which this cmdlet adds the new property. |
| `-PropertyType` | `Object` | No | Specifies the type of property that this cmdlet adds. The acceptable values for this parameter are:   - `String`: Specifies a null-terminated string. Used for **REG_SZ** values. - `ExpandString`: S... |
| `-Value` | `Object` | No | Specifies the property value. If the property is a registry entry, this parameter specifies the value of the entry. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### New-PSDrive

Creates temporary and persistent drives that are associated with a location in an item data store.

The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.

**Returns**: `System.Management.Automation.PSDriveInfo`

```
New-PSDrive
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Description <Object>]
    -Name <Object>
    [-Persist <Object>]
    -PSProvider <Object>
    -Root <Object>
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies a user account that has permission to do this action. The default is the current user.   Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credenti... |
| `-Description` | `Object` | No | Specifies a brief text description of the drive. Type any string.   To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.   To see the description of ... |
| `-Name` | `Object` | Yes | Specifies a name for the new drive. For persistent mapped network drives, use a drive letter. For temporary PowerShell drives, you aren't limited to drive letters, use any valid string. |
| `-Persist` | `Object` | No | Indicates that this cmdlet creates a Windows mapped network drive. The **Persist** parameter is only available on Windows.   Mapped network drives are saved in Windows on the local computer. They'r... |
| `-PSProvider` | `Object` | Yes | Specifies the PowerShell provider that supports drives of this kind.   For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`... |
| `-Root` | `Object` | Yes | Specifies the data store location to which a PowerShell drive is mapped.   For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a reg... |
| `-Scope` | `Object` | No | Specifies a scope for the drive. The acceptable values for this parameter are: **Global**, **Local**, and **Script**, or a number relative to the current scope. Scopes number 0 through the number o... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Pop-Location

Changes the current location to the location most recently pushed onto the stack.

The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet. You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.

**Returns**: `None`

```
Pop-Location
    [-PassThru <Object>]
    [-StackName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PassThru` | `Object` | No | Passes an object that represents the location to the pipeline. By default, this cmdlet does not generate any output. |
| `-StackName` | `Object` | No | Specifies the location stack from which the location is popped. Enter a location stack name.   Without this parameter, `Pop-Location` pops a location from the current location stack. By default, th... |

---

### Push-Location

Adds the current location to the top of a location stack.

The `Push-Location` cmdlet adds ("pushes") the current location onto a location stack. If you specify a path, `Push-Location` pushes the current location onto a location stack and then changes the current location to the location specified by the path. You can use the `Pop-Location` cmdlet to get locations from the location stack.

**Returns**: `None`

```
Push-Location
    [-LiteralPath <Object>]
    [-PassThru <Object>]
    [-Path <Object>]
    [-StackName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-LiteralPath` | `Object` | No | Specifies the path to the new location. Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards. If the ... |
| `-PassThru` | `Object` | No | Passes an object representing the location to the pipeline. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | No | Changes your location to the location specified by this path after it adds (pushes) the current location onto the top of the stack. Enter a path to any location whose provider supports this cmdlet.... |
| `-StackName` | `Object` | No | Specifies the location stack to which the current location is added. Enter a location stack name. If the stack does not exist, `Push-Location` creates it.   Without this parameter, `Push-Location` ... |

---

### Remove-Item

Deletes the specified items.

The `Remove-Item` cmdlet deletes one or more items. Because it's supported by many providers, it can delete many different types of items, including files, folders, registry keys, variables, aliases, and functions.

**Returns**: `None`

```
Remove-Item
    [-Confirm <Object>]
    [-Credential <Object>]
    [-DeleteKey <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-Recurse <Object>]
    [-Stream <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. For more information, see the following articles:   - [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variab... |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](..... |
| `-DeleteKey` | `Object` | No | This is a dynamic parameter made available by the **Certificate** provider. The **Certificate** provider and this parameter are only available on Windows platforms.   When provided, the cmdlet dele... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to remove items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables. The cmdlet can't remove constant aliases or variables. Implem... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it... |
| `-Path` | `Object` | Yes | Specifies a path of the items being removed. Wildcard characters are permitted. |
| `-Recurse` | `Object` | No | Indicates that this cmdlet deletes the items in the specified locations and in all child items of the locations.   The **Recurse** parameter might not delete all subfolders or all child items. This... |
| `-Stream` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. This parameter is only available on Windows. This parameter can't be used in combination with the **Recurse** parameter.  ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Remove-ItemProperty

Deletes the property and its value from an item.

The `Remove-ItemProperty` cmdlet deletes a property and its value from an item. You can use it to delete registry values and the data that they store.

**Returns**: `None`

```
Remove-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user. Implementation varies from provider to provider. For more information, see [about_Providers](../Mi... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies the names of the properties to remove. Wildcard characters are permitted. |
| `-Path` | `Object` | Yes | Specifies the path of the item whose properties are being removed. Wildcard characters are permitted. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Remove-PSDrive

Deletes temporary PowerShell drives and disconnects mapped network drives.

The `Remove-PSDrive` cmdlet deletes temporary PowerShell drives that were created by using the `New-PSDrive` cmdlet.

**Returns**: `None`

```
Remove-PSDrive
    [-Confirm <Object>]
    [-Force <Object>]
    -LiteralName <Object>
    -Name <Object>
    [-PSProvider <Object>]
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Force` | `Object` | No | Removes the current PowerShell drive. |
| `-LiteralName` | `Object` | Yes | Specifies the name of the drive.   The value of **LiteralName** is used exactly as typed. No characters are interpreted as wildcards. If the name includes escape characters, enclose it in single qu... |
| `-Name` | `Object` | Yes | Specifies the names of the drives to remove. Do not type a colon (`:`) after the drive name. |
| `-PSProvider` | `Object` | No | Specifies an array of **PSProvider** objects. This cmdlet removes and disconnects all of the drives associated with the specified PowerShell provider. |
| `-Scope` | `Object` | No | Specifies a scope for the drive. The acceptable values for this parameter are: `Global`, `Local`, and `Script`, or a number relative to the current scope. Scopes number `0` through the number of sc... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Rename-Item

Renames an item in a PowerShell provider namespace.

The `Rename-Item` cmdlet changes the name of a specified item. This cmdlet does not affect the content of the item being renamed.

**Returns**: `None`

```
Rename-Item
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Force <Object>]
    -LiteralPath <Object>
    -NewName <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use > [Invoke-Command](.... |
| `-Force` | `Object` | No | Forces the cmdlet to rename items that can't otherwise be changed, such as hidden or read-only files or read-only aliases or variables. The cmdlet can't change constant aliases or variables. Implem... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-NewName` | `Object` | Yes | Specifies the new name of the item. Enter only a name, not a path and name. If you enter a path that differs from the path that is specified in the **Path** parameter, `Rename-Item` generates an er... |
| `-PassThru` | `Object` | No | Returns an object that represents the item to the pipeline. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path of the item to rename. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Rename-ItemProperty

Renames a property of an item.

The `Rename-ItemProperty` cmdlet changes the name of a specified item property. The value of the property is not changed. For example, you can use `Rename-ItemProperty` to change the name of a registry entry.

**Returns**: `None`

```
Rename-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    -Name <Object>
    -NewName <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user. Implementation varies from provider to provider. For more information, see [about_Providers](../Mi... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to the item. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it in single q... |
| `-Name` | `Object` | Yes | Specifies the current name of the property to rename. |
| `-NewName` | `Object` | Yes | Specifies the new name for the property. |
| `-PassThru` | `Object` | No | Returns an object that represents the item property. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies a path to the item. Wildcard characters are permitted. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Resolve-Path

Resolves the wildcard characters in a path, and displays the path contents.

The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified. The match can include files, folders, registry keys, or any other object accessible from a **PSDrive** provider.

**Returns**: `System.Management.Automation.PathInfo`

```
Resolve-Path
    [-Credential <Object>]
    [-Force <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-Relative <Object>]
    [-RelativeBasePath <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | Specifies a user account that has permission to perform this action. The default is the current user.   Type a user name, such as `User01` or `Domain01\User01`, or pass a **PSCredential** object. Y... |
| `-Force` | `Object` | No | Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files. The **Force** parameter doesn't override security restrictions. Implementation varies am... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to be resolved. The value of the **LiteralPath** parameter is used exactly as typed. No characters are interpreted as wildcard characters. If the path includes escape characters,... |
| `-Path` | `Object` | Yes | Specifies the PowerShell path to resolve. This parameter is required. You can also pipe a path string to `Resolve-Path`. Wildcard characters are permitted. |
| `-Relative` | `Object` | No | Indicates that this cmdlet returns a relative path. |
| `-RelativeBasePath` | `Object` | No | Specifies a path to resolve the relative path from. When you use this parameter, the cmdlet returns the **System.Management.Automation.PathInfo** object for the resolved path.   When you use this p... |

---

### Restart-Computer

Restarts the operating system on local and remote computers.

The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.

**Returns**: `None`

```
Restart-Computer
    [-ComputerName <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Delay <Object>]
    [-For <Object>]
    [-Force <Object>]
    [-Timeout <Object>]
    [-Wait <Object>]
    [-WhatIf <Object>]
    [-WsmanAuthentication <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ComputerName` | `Object` | No | Specifies one computer name or a comma-separated array of computer names. `Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.   Type the NetBIOS name, an IP address,... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running `Restart-Computer`. |
| `-Credential` | `Object` | No | Specifies a user account that has permission to do this action. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object ge... |
| `-Delay` | `Object` | No | Specifies the frequency of queries, in seconds. PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.   Th... |
| `-For` | `Object` | No | Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts. This parameter is only valid with the **Wait** parameter.   Th... |
| `-Force` | `Object` | No | Forces an immediate restart of the computer.   This parameter is only available on Windows platforms. |
| `-Timeout` | `Object` | No | Specifies the duration of the wait, in seconds. When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.   The **Timeout** parameter is on... |
| `-Wait` | `Object` | No | `Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted. You can use this parameter in a script to restart computers and then continue to proc... |
| `-WhatIf` | `Object` | No | Shows what would happen if the `Restart-Computer` runs. The `Restart-Computer` cmdlet isn't run. |
| `-WsmanAuthentication` | `Object` | No | Specifies the mechanism that is used to authenticate the user credentials. This parameter was introduced in Windows PowerShell 3.0.   The acceptable values for this parameter are: **Basic**, **Cred... |

---

### Set-Clipboard

Sets the contents of the clipboard.

The `Set-Clipboard` cmdlet sets the contents of the clipboard.

**Returns**: `None`

```
Set-Clipboard
    [-Append <Object>]
    [-AsOSC52 <Object>]
    [-Confirm <Object>]
    [-PassThru <Object>]
    -Value <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Append` | `Object` | No | Indicates that the cmdlet should add to the clipboard instead of replacing it. By default, the cmdlet clears the current content from the clipboard and sets it to the new content. When this paramet... |
| `-AsOSC52` | `Object` | No | When connected to a remote session over SSH, `Set-Clipboard` sets the clipboard of the remote machine, not the local host. When you use this parameter, `Set-Clipboard` uses the OSC52 ANSI escape se... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you're working. By default, this cmdlet does not generate any output. |
| `-Value` | `Object` | Yes | The string values to be added to the clipboard. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Set-Content

Writes new content or replaces existing content in a file.

`Set-Content` is a string-processing cmdlet that writes new content or replaces the content in a file. `Set-Content` replaces the existing content and differs from the `Add-Content` cmdlet that appends content to a file. To send content to `Set-Content` you can use the **Value** parameter on the command line or send content through the pipeline.

**Returns**: `None`

```
Set-Content
    [-AsByteStream <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Encoding <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-NoNewline <Object>]
    [-PassThru <Object>]
    -Path <Object>
    [-Stream <Object>]
    -Value <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsByteStream` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. For more information, see [about_FileSystem_Provider](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md).   ... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Encoding` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. For more information, see [about_FileSystem_Provider](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md).   ... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to set the contents of a file, even if the file is read-only. Implementation varies from provider to provider. For more information, see [about_Providers](../Microsoft.PowerShell.... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-NoNewline` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. For more information, see [about_FileSystem_Provider](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md).   ... |
| `-PassThru` | `Object` | No | Returns an object that represents the content. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path of the item that receives the content. Wildcard characters are permitted. |
| `-Stream` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider. This Parameter is only available on Windows. For more information, see [about_FileSystem_Provider](../Microsoft.PowerShell... |
| `-Value` | `Object` | Yes | Specifies the new content for the item. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Set-Item

Changes the value of an item to the value specified in the command.

The `Set-Item` cmdlet changes the value of an item, such as a variable or registry key, to the value specified in the command.

**Returns**: `None`

```
Set-Item
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -LiteralPath <Object>
    [-Options <Object>]
    [-PassThru <Object>]
    -Path <Object>
    [-Type <Object>]
    [-Value <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to set items that cannot otherwise be changed, such as read-only alias or variables. The cmdlet cannot change constant aliases or variables. Implementation varies from provider to... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Options` | `Object` | No | This is a dynamic parameter made available by the **Alias** and **Function** providers. For more information, see [about_Alias_Provider](../Microsoft.PowerShell.Core/About/about_Alias_Provider.md) ... |
| `-PassThru` | `Object` | No | Passes an object that represents the item to the pipeline. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies a path of the location of the items. Wildcard characters are permitted. |
| `-Type` | `Object` | No | This is a dynamic parameter made available by the **Registry** provider. The **Registry** provider and this parameter are only available on Windows.   Specifies the type of property that this cmdle... |
| `-Value` | `Object` | No | Specifies a new value for the item. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Set-ItemProperty

Creates or changes the value of a property of an item.

The `Set-ItemProperty` cmdlet changes the value of the property of the specified item. You can use the cmdlet to establish or change the properties of items. For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$true`.

**Returns**: `None`

```
Set-ItemProperty
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -InputObject <Object>
    -LiteralPath <Object>
    -Name <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-Type <Object>]
    -Value <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | > [!NOTE] > This parameter is not supported by any providers installed with PowerShell. > To impersonate another user, or elevate your credentials when running this cmdlet, > use [Invoke-Command](.... |
| `-Exclude` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet excludes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.... |
| `-Filter` | `Object` | No | Specifies a filter to qualify the **Path** parameter. The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that suppo... |
| `-Force` | `Object` | No | Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user. Implementation varies by provider. For more information, see [about_Providers](../Microsoft.PowerShell.Co... |
| `-Include` | `Object` | No | Specifies, as a string array, an item or items that this cmdlet includes in the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `"*... |
| `-InputObject` | `Object` | Yes | Specifies the object that has the properties that this cmdlet changes. Enter a variable that contains the object or a command that gets the object. |
| `-LiteralPath` | `Object` | Yes | Specifies a path to one or more locations. The value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose i... |
| `-Name` | `Object` | Yes | Specifies the name of the property. |
| `-PassThru` | `Object` | No | Returns an object that represents the item property. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path of the items with the property to modify. Wildcard characters are permitted. |
| `-Type` | `Object` | No | This is a dynamic parameter made available by the **Registry** provider. The **Registry** provider and this parameter are only available on Windows.   Specifies the type of property that this cmdle... |
| `-Value` | `Object` | Yes | Specifies the value of the property. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Set-Location

Sets the current working location to a specified location.

The `Set-Location` cmdlet sets the working location to a specified location. That location could be a directory, a subdirectory, a registry location, or any provider path.

**Returns**: `None`

```
Set-Location
    -LiteralPath <Object>
    [-PassThru <Object>]
    [-Path <Object>]
    [-StackName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-LiteralPath` | `Object` | Yes | Specifies a path of the location. The value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcard characters. If the path includes escape charac... |
| `-PassThru` | `Object` | No | Returns a **PathInfo** object that represents the location. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | No | Specify the path of a new working location. If no path is provided, `Set-Location` defaults to the current user's home directory. When wildcards are used, the cmdlet chooses the container (director... |
| `-StackName` | `Object` | No | Specifies an existing location stack name that this cmdlet makes the current location stack. Enter a location stack name. To indicate the unnamed default location stack, type `$null` or an empty st... |

---

### Split-Path

Returns the specified part of a path.

The `Split-Path` cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a filename. It can also get items that are referenced by the split path and tell whether the path is relative or absolute. If you split a path without specifying any other parameters, `Split-Path` returns the parent part of the path provided.

**Returns**: `System.String`

```
Split-Path
    [-Credential <Object>]
    -Extension <Object>
    -IsAbsolute <Object>
    -Leaf <Object>
    -LeafBase <Object>
    -LiteralPath <Object>
    -NoQualifier <Object>
    [-Parent <Object>]
    -Path <Object>
    -Qualifier <Object>
    [-Resolve <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use > [Invoke-Command](..... |
| `-Extension` | `Object` | Yes | Indicates that this cmdlet returns only the extension of the leaf. For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.   This parameter was introduced in PowerShell 6.0. |
| `-IsAbsolute` | `Object` | Yes | Indicates that this cmdlet returns `$true` if the path is absolute and `$false` if it's relative. On Windows, an absolute path string must start with a provider drive specifier, like `C:` or `HKCU:... |
| `-Leaf` | `Object` | Yes | When using the **Leaf** parameter, `Split-Path` returns only the last item in the path string supplied, regardless whether that item is a file or a directory. |
| `-LeafBase` | `Object` | Yes | Indicates that this cmdlet returns only base name of the leaf. For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.   This parameter was introduced in PowerShell 6.0. |
| `-LiteralPath` | `Object` | Yes | Specifies the paths to be split. Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcard characters. If the path includes escape char... |
| `-NoQualifier` | `Object` | Yes | Indicates that this cmdlet returns the path without the qualifier. For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`. For example, i... |
| `-Parent` | `Object` | No | `Split-Path` returns only the parent container portion of the path string supplied. If the **Path** string doesn't contain a parent container, `Split-Path` returns an empty string. |
| `-Path` | `Object` | Yes | Specifies the paths to be split. Wildcard characters are permitted. If the path includes spaces, enclose it in quotation marks. You can also pipe a path to this cmdlet. |
| `-Qualifier` | `Object` | Yes | Indicates that this cmdlet returns only the qualifier of the specified path. For the FileSystem or Registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`. |
| `-Resolve` | `Object` | No | Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements. |

---

### Start-Process

Starts one or more processes on the local computer.

The `Start-Process` cmdlet starts one or more processes on the local computer. By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.

**Returns**: `None`

```
Start-Process
    [-ArgumentList <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Environment <Object>]
    -FilePath <Object>
    [-LoadUserProfile <Object>]
    [-NoNewWindow <Object>]
    [-PassThru <Object>]
    [-RedirectStandardError <Object>]
    [-RedirectStandardInput <Object>]
    [-RedirectStandardOutput <Object>]
    [-UseNewEnvironment <Object>]
    [-Verb <Object>]
    [-Wait <Object>]
    [-WhatIf <Object>]
    [-WindowStyle <Object>]
    [-WorkingDirectory <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object` | No | Specifies parameters or parameter values to use when this cmdlet starts the process. Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings s... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies a user account that has permission to perform this action. By default, the cmdlet uses the credentials of the current user.   Type a user name, such as **User01** or **Domain01\User01**, ... |
| `-Environment` | `Object` | No | Specifies one or more environment variables to override for the process as a hash table. Specify the name of an environment variable as a key in the hash table and the desired value. To unset an en... |
| `-FilePath` | `Object` | Yes | Specifies the optional path and filename of the program that runs in the process. Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that's associated with a pr... |
| `-LoadUserProfile` | `Object` | No | Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user. The parameter doesn't apply to non-Windows systems.   This parameter doesn't ... |
| `-NoNewWindow` | `Object` | No | Start the new process in the current console window. By default on Windows, PowerShell opens a new window. On non-Windows systems, you never get a new window.   You can't use the **NoNewWindow** an... |
| `-PassThru` | `Object` | No | Returns a process object for each process that the cmdlet started. By default, this cmdlet doesn't generate any output. |
| `-RedirectStandardError` | `Object` | No | Specifies a file. This cmdlet sends any errors generated by the process to a file that you specify. Enter the path and filename. By default, the errors are displayed in the console. |
| `-RedirectStandardInput` | `Object` | No | Specifies a file. This cmdlet reads input from the specified file. Enter the path and filename of the input file. By default, the process gets its input from the keyboard. |
| `-RedirectStandardOutput` | `Object` | No | Specifies a file. This cmdlet sends the output generated by the process to a file that you specify. Enter the path and filename. By default, the output is displayed in the console. |
| `-UseNewEnvironment` | `Object` | No | Indicates that this cmdlet uses new environment variables specified for the process. By default, the started process runs with the environment variables inherited from the parent process.   On Wind... |
| `-Verb` | `Object` | No | Specifies a verb to use when this cmdlet starts the process. The verbs that are available are determined by the filename extension of the file that runs in the process.   The following table shows ... |
| `-Wait` | `Object` | No | Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input. This parameter suppresses the command prompt or retains the window until the ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run.   This parameter was introduced in PowerShell 6.0. |
| `-WindowStyle` | `Object` | No | Specifies the state of the window that's used for the new process. The default value is `Normal`. The acceptable values for this parameter are:   - `Normal` - `Hidden` - `Minimized` - `Maximized`  ... |
| `-WorkingDirectory` | `Object` | No | Specifies the location that the new process should start in.   When not specified, the cmdlet defaults to the fully-qualified location specified in the **FilePath** parameter. If the value of the *... |

---

### Stop-Computer

Stops (shuts down) local and remote computers.

The `Stop-Computer` cmdlet shuts down the local computer and remote computers.

**Returns**: `None`

```
Stop-Computer
    [-ComputerName <Object>]
    [-Confirm <Object>]
    [-Credential <Object>]
    [-Force <Object>]
    [-WhatIf <Object>]
    [-WsmanAuthentication <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ComputerName` | `Object` | No | Specifies the computers to stop. The default is the local computer.   Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list. To specif... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Credential` | `Object` | No | Specifies a user account that has permission to do this action. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object ge... |
| `-Force` | `Object` | No | Forces an immediate shut down of the computer.   This parameter is only available on Windows platforms. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |
| `-WsmanAuthentication` | `Object` | No | Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol. The default value is **Default**.   The acceptable values for this parameter are:... |

---

### Stop-Process

Stops one or more running processes.

The `Stop-Process` cmdlet stops one or more running processes. You can specify a process by process name or process ID (PID), or pass a process object to `Stop-Process`. `Stop-Process` works only on processes running on the local computer.

**Returns**: `None`

```
Stop-Process
    [-Confirm <Object>]
    [-Force <Object>]
    -Id <Object>
    -InputObject <Object>
    -Name <Object>
    [-PassThru <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Force` | `Object` | No | Stops the specified processes without prompting for confirmation. By default, `Stop-Process` prompts for confirmation before stopping any process that is not owned by the current user.   To find th... |
| `-Id` | `Object` | Yes | Specifies the process IDs of the processes to stop. To specify multiple IDs, use commas to separate the IDs. To find the PID of a process, type `Get-Process`. |
| `-InputObject` | `Object` | Yes | Specifies the process objects to stop. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-Name` | `Object` | Yes | Specifies the process names of the processes to stop. You can type multiple process names, separated by commas, or use wildcard characters. |
| `-PassThru` | `Object` | No | Returns an object that represents the process. By default, this cmdlet does not generate any output. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Test-Connection

Sends ICMP echo request packets, or pings, to one or more computers.

The `Test-Connection` cmdlet sends Internet Control Message Protocol (ICMP) echo request packets, or pings, to one or more remote computers and returns the echo response replies. You can use this cmdlet to determine whether a particular computer can be contacted across an IP network.

**Returns**: `Microsoft.PowerShell.Commands.TestConnectionCommand+PingStatus`

```
Test-Connection
    [-BufferSize <Object>]
    [-Count <Object>]
    [-Delay <Object>]
    [-Detailed <Object>]
    [-DontFragment <Object>]
    [-IPv4 <Object>]
    [-IPv6 <Object>]
    [-MaxHops <Object>]
    -MtuSize <Object>
    [-Ping <Object>]
    [-Quiet <Object>]
    -Repeat <Object>
    [-ResolveDestination <Object>]
    [-Source <Object>]
    -TargetName <Object>
    -TcpPort <Object>
    [-TimeoutSeconds <Object>]
    -Traceroute <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BufferSize` | `Object` | No | Specifies the size, in bytes, of the buffer sent with this command. The default value is 32. |
| `-Count` | `Object` | No | Specifies the number of echo requests to send. The default value is 4. |
| `-Delay` | `Object` | No | Specifies the interval between pings, in seconds. |
| `-Detailed` | `Object` | No | When you use the **Detailed** parameter, this cmdlet returns a detailed information about the status of the TCP connection attempts.   This parameter was added in PowerShell 7.4. |
| `-DontFragment` | `Object` | No | This parameter sets the **Don't Fragment** flag in the IP header. You can use this parameter with the **BufferSize** parameter to test the Path MTU size. For more information about Path MTU, see th... |
| `-IPv4` | `Object` | No | Forces the cmdlet to use the IPv4 protocol for the test. |
| `-IPv6` | `Object` | No | Forces the cmdlet to use the IPv6 protocol for the test. |
| `-MaxHops` | `Object` | No | Sets the maximum number of hops that an ICMP request message can be sent. The default value is controlled by the operating system. The default value for Windows 10 and higher is 128 hops. |
| `-MtuSize` | `Object` | Yes | This parameter is used to discover the Path MTU size. The cmdlet returns a **PingReply#MTUSize** object that contains the Path MTU size to the target. For more information about Path MTU, see the [... |
| `-Ping` | `Object` | No | Causes the cmdlet to do a ping test. This is the default mode for the `Test-Connection` cmdlet. |
| `-Quiet` | `Object` | No | The **Quiet** parameter returns a **Boolean** value. Using this parameter suppresses all errors.   Each connection that's tested returns a **Boolean** value. If the **TargetName** parameter specifi... |
| `-Repeat` | `Object` | Yes | Causes the cmdlet to send ping requests continuously. When the value of **TargetName** is an array of targets, the cmdlet repeats the ping requests for the first target only. It ignores the remaini... |
| `-ResolveDestination` | `Object` | No | Causes the cmdlet to attempt to resolve the DNS name of the target. When used in conjunction with the **Traceroute** parameter, the DNS names of all intermediate hosts will also be retrieved, if po... |
| `-Source` | `Object` | No | Specifies the names of the computers where the ping originates. Enter a comma-separated list of computer names. The default is the local computer.   > [!NOTE] > This parameter is not supported in P... |
| `-TargetName` | `Object` | Yes | Specifies the computer(s) to test. Type the computer names or type IP addresses in IPv4 or IPv6 format. |
| `-TcpPort` | `Object` | Yes | Specifies the TCP port number on the target to be used in the TCP connection test.   The cmdlet attempts to make a TCP connection to the specified port on the target.   - The cmdlet returns `$true`... |
| `-TimeoutSeconds` | `Object` | No | Sets the timeout value for the test. The test fails if a response isn't received before the timeout expires. The default is five seconds.   This parameter was introduced in PowerShell 6.0. |
| `-Traceroute` | `Object` | Yes | Causes the cmdlet to do a traceroute test. When this parameter is used, the cmdlet returns a `TestConnectionCommand+TraceStatus` object. |

---

### Test-Path

Determines whether all elements of a path exist.

The `Test-Path` cmdlet determines whether all elements of the path exist. It returns `$true` if all elements exist and `$false` if any are missing. It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element. If the **Path** is a whitespace or empty string, then the cmdlet returns `$false`. If the **Path** is `$null`, an array of `$null` or an empty array, the cmdlet returns a non-terminating error.

**Returns**: `System.Boolean`

```
Test-Path
    [-Credential <Object>]
    [-Exclude <Object>]
    [-Filter <Object>]
    [-Include <Object>]
    [-IsValid <Object>]
    -LiteralPath <Object>
    [-NewerThan <Object>]
    [-OlderThan <Object>]
    -Path <Object>
    [-PathType <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | > [!NOTE] > This parameter isn't supported by any providers installed with PowerShell. To impersonate another > user, or elevate your credentials when running this cmdlet, use > [Invoke-Command](..... |
| `-Exclude` | `Object` | No | Specifies items that this cmdlet omits. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.txt`. Wildcard characters are permitted. |
| `-Filter` | `Object` | No | Specifies a filter in the format or language of the provider. The value of this parameter qualifies the **Path** parameter. The syntax of the filter, including the use of wildcard characters, depen... |
| `-Include` | `Object` | No | Specifies paths that this cmdlet tests. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.txt`. Wildcard characters are permitted. |
| `-IsValid` | `Object` | No | Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist. This cmdlet returns `$true` if the path syntax is valid and `$false` if it's not. If t... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to be tested. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interpreted as wildcard characters. If the path includes ... |
| `-NewerThan` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider.   Specify a time as a **DateTime** object.   Before PowerShell 7.5, the cmdlet ignores:   - This parameter when you specif... |
| `-OlderThan` | `Object` | No | This is a dynamic parameter made available by the **FileSystem** provider.   Specify a time as a **DateTime** object.   Before PowerShell 7.5, the cmdlet ignores:   - This parameter when you specif... |
| `-Path` | `Object` | Yes | Specifies a path to be tested. Wildcard characters are permitted. If the path includes spaces, enclose it in quotation marks. |
| `-PathType` | `Object` | No | Specifies the type of the final element in the path. This cmdlet returns `$true` if the element is of the specified type and `$false` if it's not. The acceptable values for this parameter are:   - ... |

---

### Wait-Process

Waits for the processes to be stopped before accepting more input.

> **This cmdlet doesn't work on Linux or macOS.**

**Returns**: `None`

```
Wait-Process
    [-Any <Object>]
    -Id <Object>
    -InputObject <Object>
    -Name <Object>
    [-PassThru <Object>]
    [-Timeout <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Any` | `Object` | No | When multiple processes are passed into `Wait-Process`, the cmdlet waits for all processes to exit before returning. With this parameter, the cmdlet returns when any of the processes exits. The rem... |
| `-Id` | `Object` | Yes | Specifies the process IDs of the processes. To specify multiple IDs, use commas to separate the IDs. To find the PID of a process, type `Get-Process`. |
| `-InputObject` | `Object` | Yes | Specifies the processes by submitting process objects. Enter a variable that contains the process objects, or type a command or expression that gets the process objects, such as the `Get-Process` c... |
| `-Name` | `Object` | Yes | Specifies the process names of the processes. To specify multiple names, use commas to separate the names. Wildcard characters are not supported. |
| `-PassThru` | `Object` | No | By default, this cmdlet doesn't output anything. With this parameter, the cmdlet returns objects representing the processes that were waited on.   This parameter was added in PowerShell 7.4. |
| `-Timeout` | `Object` | No | Specifies the maximum time, in seconds, that this cmdlet waits for the specified processes to stop. When this interval expires, the command displays a non-terminating error that lists the processes... |

---

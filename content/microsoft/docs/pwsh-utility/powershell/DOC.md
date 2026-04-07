---
name: pwsh-utility
description: "PowerShell 7.5 Utility cmdlets — output formatting, JSON/CSV/XML, strings, dates, random, variables, aliases, culture, debugging output, type data"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Add-Member,Add-Type,Clear-Variable,Compare-Object,ConvertFrom-CliXml,ConvertFrom-Csv,ConvertFrom-Json,ConvertFrom-Markdown,ConvertFrom-StringData,ConvertTo-CliXml,ConvertTo-Csv,ConvertTo-Html,ConvertTo-Json,ConvertTo-Xml,Debug-Runspace,Disable-PSBreakpoint,Disable-RunspaceDebug,Enable-PSBreakpoint,Enable-RunspaceDebug,Export-Alias,Export-Clixml,Export-Csv,Export-FormatData,Export-PSSession,Format-Custom,Format-Hex,Format-List,Format-Table,Format-Wide,Get-Alias,Get-Culture,Get-Date,Get-Error,Get-Event,Get-EventSubscriber,Get-FileHash,Get-FormatData,Get-Host,Get-MarkdownOption,Get-Member,Get-PSBreakpoint,Get-PSCallStack,Get-Random,Get-Runspace,Get-RunspaceDebug,Get-SecureRandom,Get-TraceSource,Get-TypeData,Get-UICulture,Get-Unique,Get-Uptime,Get-Variable,Get-Verb,Group-Object,Import-Alias,Import-Clixml,Import-Csv,Import-LocalizedData,Import-PSSession,Import-PowerShellDataFile,Invoke-Expression,Invoke-RestMethod,Invoke-WebRequest,Join-String,Measure-Command,Measure-Object,New-Alias,New-Event,New-Guid,New-Object,New-TemporaryFile,New-TimeSpan,New-Variable,Out-File,Out-String,Read-Host,Register-EngineEvent,Register-ObjectEvent,Remove-Alias,Remove-Event,Remove-PSBreakpoint,Remove-TypeData,Remove-Variable,Select-Object,Select-String,Select-Xml,Send-MailMessage,Set-Alias,Set-Date,Set-MarkdownOption,Set-PSBreakpoint,Set-TraceSource,Set-Variable,Show-Markdown,Sort-Object,Start-Sleep,Tee-Object,Test-Json,Trace-Command,Unblock-File,Unregister-Event,Update-FormatData,Update-List,Update-TypeData,Wait-Debugger,Wait-Event,Write-Debug,Write-Error,Write-Host,Write-Information,Write-Output,Write-Progress,Write-Verbose,Write-Warning"
---

# PowerShell 7.5 — output formatting

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-Member` | Adds custom properties and methods to an instance of a PowerShell object. |
| `Add-Type` | Adds a Microsoft .NET class to a PowerShell session. |
| `Clear-Variable` | Deletes the value of a variable. |
| `Compare-Object` | Compares two sets of objects. |
| `ConvertFrom-CliXml` | Converts a CliXml-formatted string to a custom **PSObject**. |
| `ConvertFrom-Csv` | Converts object properties in character-separated value (CSV) format into CSV versions of the ori... |
| `ConvertFrom-Json` | Converts a JSON-formatted string to a custom object or a hash table. |
| `ConvertFrom-Markdown` | Convert the contents of a string or a file to a **MarkdownInfo** object. |
| `ConvertFrom-StringData` | Converts a string containing one or more key and value pairs to a hash table. |
| `ConvertTo-CliXml` | Converts an object to a CliXml-formatted string. |
| `ConvertTo-Csv` | Converts .NET objects into a series of character-separated value (CSV) strings. |
| `ConvertTo-Html` | Converts .NET objects into HTML that can be displayed in a Web browser. |
| `ConvertTo-Json` | Converts an object to a JSON-formatted string. |
| `ConvertTo-Xml` | Creates an XML-based representation of an object. |
| `Debug-Runspace` | Starts an interactive debugging session with a runspace. |
| `Disable-PSBreakpoint` | Disables the breakpoints in the current console. |
| `Disable-RunspaceDebug` | Disables debugging on one or more runspaces, and releases any pending debugger stop. |
| `Enable-PSBreakpoint` | Enables the breakpoints in the current console. |
| `Enable-RunspaceDebug` | Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached. |
| `Export-Alias` | Exports information about currently defined aliases to a file. |
| `Export-Clixml` | Creates an XML-based representation of an object or objects and stores it in a file. |
| `Export-Csv` | Converts objects into a series of character-separated value (CSV) strings and saves the strings t... |
| `Export-FormatData` | Saves formatting data from the current session in a formatting file. |
| `Export-PSSession` | Exports commands from another session and saves them in a PowerShell module. |
| `Format-Custom` | Uses a customized view to format the output. |
| `Format-Hex` | Displays a file or other input as hexadecimal. |
| `Format-List` | Formats the output as a list of properties in which each property appears on a new line. |
| `Format-Table` | Formats the output as a table. |
| `Format-Wide` | Formats objects as a wide table that displays only one property of each object. |
| `Get-Alias` | Gets the aliases for the current session. |
| `Get-Culture` | Gets the current culture set in the operating system. |
| `Get-Date` | Gets the current date and time. |
| `Get-Error` | Gets and displays the most recent error messages from the current session. |
| `Get-Event` | Gets the events in the event queue. |
| `Get-EventSubscriber` | Gets the event subscribers in the current session. |
| `Get-FileHash` | Computes the hash value for a file by using a specified hash algorithm. |
| `Get-FormatData` | Gets the formatting data in the current session. |
| `Get-Host` | Gets an object that represents the current host program. |
| `Get-MarkdownOption` | Returns the current colors and styles used for rendering Markdown content in the console. |
| `Get-Member` | Gets the properties and methods of objects. |
| `Get-PSBreakpoint` | Gets the breakpoints that are set in the current session. |
| `Get-PSCallStack` | Displays the current call stack. |
| `Get-Random` | Gets a random number, or selects objects randomly from a collection. |
| `Get-Runspace` | Gets active runspaces within a PowerShell host process. |
| `Get-RunspaceDebug` | Shows runspace debugging options. |
| `Get-SecureRandom` | Gets a random number, or selects objects randomly from a collection. |
| `Get-TraceSource` | Gets PowerShell components that are instrumented for tracing. |
| `Get-TypeData` | Gets the extended type data in the current session. |
| `Get-UICulture` | Gets the current UI culture settings in the operating system. |
| `Get-Unique` | Returns unique items from a sorted list. |
| `Get-Uptime` | Get the **TimeSpan** since last boot. |
| `Get-Variable` | Gets the variables in the current console. |
| `Get-Verb` | Gets approved PowerShell verbs. |
| `Group-Object` | Groups objects that contain the same value for specified properties. |
| `Import-Alias` | Imports an alias list from a file. |
| `Import-Clixml` | Imports a CLIXML file and creates corresponding objects in PowerShell. |
| `Import-Csv` | Creates table-like custom objects from the items in a character-separated value (CSV) file. |
| `Import-LocalizedData` | Imports language-specific data into scripts and functions based on the UI culture that's selected... |
| `Import-PSSession` | Imports commands from another session into the current session. |
| `Import-PowerShellDataFile` | Imports values from a `.psd1` file without invoking its contents. |
| `Invoke-Expression` | Runs commands or expressions on the local computer. |
| `Invoke-RestMethod` | Sends an HTTP or HTTPS request to a RESTful web service. |
| `Invoke-WebRequest` | Gets content from a web page on the internet. |
| `Join-String` | Combines objects from the pipeline into a single string. |
| `Measure-Command` | Measures the time it takes to run scriptblocks and cmdlets. |
| `Measure-Object` | Calculates the numeric properties of objects, and the characters, words, and lines in string obje... |
| `New-Alias` | Creates a new alias. |
| `New-Event` | Creates a new event. |
| `New-Guid` | Creates a GUID. |
| `New-Object` | Creates an instance of a Microsoft .NET Framework or COM object. |
| `New-TemporaryFile` | Creates a temporary file. |
| `New-TimeSpan` | Creates a TimeSpan object. |
| `New-Variable` | Creates a new variable. |
| `Out-File` | Sends output to a file. |
| `Out-String` | Outputs input objects as a string. |
| `Read-Host` | Reads a line of input from the console. |
| `Register-EngineEvent` | Subscribes to events that are generated by the PowerShell engine and by the `New-Event` cmdlet. |
| `Register-ObjectEvent` | Subscribes to the events that are generated by a Microsoft .NET Framework object. |
| `Remove-Alias` | Remove an alias from the current session. |
| `Remove-Event` | Deletes events from the event queue. |
| `Remove-PSBreakpoint` | Deletes breakpoints from the current console. |
| `Remove-TypeData` | Deletes extended types from the current session. |
| `Remove-Variable` | Deletes a variable and its value. |
| `Select-Object` | Selects objects or object properties. |
| `Select-String` | Finds text in strings and files. |
| `Select-Xml` | Finds text in an XML string or document. |
| `Send-MailMessage` | Sends an email message. |
| `Set-Alias` | Creates or changes an alias for a cmdlet or other command in the current PowerShell session. |
| `Set-Date` | Changes the system time on the computer to a time that you specify. |
| `Set-MarkdownOption` | Sets the colors and styles used for rendering Markdown content in the console. |
| `Set-PSBreakpoint` | Sets a breakpoint on a line, command, or variable. |
| `Set-TraceSource` | Configures, starts, and stops a trace of PowerShell components. |
| `Set-Variable` | Sets the value of a variable. Creates the variable if one with the requested name does not exist. |
| `Show-Markdown` | Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or ... |
| `Sort-Object` | Sorts objects by property values. |
| `Start-Sleep` | Suspends the activity in a script or session for the specified period of time. |
| `Tee-Object` | Saves command output in a file or variable and also sends it down the pipeline. |
| `Test-Json` | Tests whether a string is a valid JSON document |
| `Trace-Command` | Configures and starts a trace of the specified expression or command. |
| `Unblock-File` | Unblocks files that were downloaded from the internet. |
| `Unregister-Event` | Cancels an event subscription. |
| `Update-FormatData` | Updates the formatting data in the current session. |
| `Update-List` | Adds items to and removes items from a property value that contains a collection of objects. |
| `Update-TypeData` | Updates the extended type data in the session. |
| `Wait-Debugger` | Stops a script in the debugger before running the next statement in the script. |
| `Wait-Event` | Waits until a particular event is raised before continuing to run. |
| `Write-Debug` | Writes a debug message to the console. |
| `Write-Error` | Writes an object to the error stream. |
| `Write-Host` | Writes customized output to a host. |
| `Write-Information` | Specifies how PowerShell handles information stream data for a command. |
| `Write-Output` | Writes the specified objects to the pipeline. |
| `Write-Progress` | Displays a progress bar within a PowerShell command window. |
| `Write-Verbose` | Writes text to the verbose message stream. |
| `Write-Warning` | Writes a warning message. |

---

### Add-Member

Adds custom properties and methods to an instance of a PowerShell object.

The `Add-Member` cmdlet lets you add members (properties and methods) to an instance of a PowerShell object. For instance, you can add a **NoteProperty** member that contains a description of the object or a **ScriptMethod** member that runs a script to change the object.

**Returns**: `None`

```
Add-Member
    [-Force <Object>]
    -InputObject <Object>
    -MemberType <Object>
    -Name <Object>
    -NotePropertyMembers <Object>
    -NotePropertyName <Object>
    -NotePropertyValue <Object>
    [-PassThru <Object>]
    [-SecondValue <Object>]
    -TypeName <Object>
    [-Value <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `Object` | No | By default, `Add-Member` can't add a new member if the object already has a member with the same. When you use the **Force** parameter, `Add-Member` replaces the existing member with the new member... |
| `-InputObject` | `Object` | Yes | Specifies the object to which the new member is added. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-MemberType` | `Object` | Yes | Specifies the type of the member to add. This parameter is required. The acceptable values for this parameter are:   - AliasProperty - CodeMethod - CodeProperty - NoteProperty - ScriptMethod - Scri... |
| `-Name` | `Object` | Yes | Specifies the name of the member that this cmdlet adds. |
| `-NotePropertyMembers` | `Object` | Yes | Specifies a hashtable or ordered dictionary that contains key-value pair representing **NoteProperty** names and their values. For more information about hash tables and ordered dictionaries in Pow... |
| `-NotePropertyName` | `Object` | Yes | Specifies the note property name.   Use this parameter with the **NotePropertyValue** parameter. This parameter is optional.   This parameter was introduced in Windows PowerShell 3.0. |
| `-NotePropertyValue` | `Object` | Yes | Specifies the note property value.   Use this parameter with the **NotePropertyName** parameter. This parameter is optional.   This parameter was introduced in Windows PowerShell 3.0. |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet doesn't generate any output.   For most objects, `Add-Member` adds the new members to the input object. H... |
| `-SecondValue` | `Object` | No | Specifies optional additional information about **AliasProperty**, **ScriptProperty**, or **CodeProperty** members.   If used when adding an **AliasProperty**, this parameter must be a data type. A... |
| `-TypeName` | `Object` | Yes | Specifies a name for the type.   When the type is a class in the **System** namespace or a type that has a type accelerator, you can enter the short name of the type. Otherwise, the full type name ... |
| `-Value` | `Object` | No | Specifies the initial value of the added member. If you add an **AliasProperty**, **CodeProperty**, or **ScriptProperty** member, you can supply additional information using the **SecondValue** par... |

---

### Add-Type

Adds a Microsoft .NET class to a PowerShell session.

The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session. You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object. If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.

**Returns**: `None`

```
Add-Type
    -AssemblyName <Object>
    [-CompilerOptions <Object>]
    [-IgnoreWarnings <Object>]
    [-Language <Object>]
    -LiteralPath <Object>
    -MemberDefinition <Object>
    -Name <Object>
    [-Namespace <Object>]
    [-OutputAssembly <Object>]
    [-OutputType <Object>]
    [-PassThru <Object>]
    -Path <Object>
    [-ReferencedAssemblies <Object>]
    -TypeDefinition <Object>
    [-UsingNamespace <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AssemblyName` | `Object` | Yes | Specifies the name of an assembly that includes the types. `Add-Type` takes the types from the specified assembly. This parameter is required when you're creating types based on an assembly name.  ... |
| `-CompilerOptions` | `Object` | No | Specifies the options for the source code compiler. These options are sent to the compiler without revision.   This parameter allows you to direct the compiler to generate an executable file, embed... |
| `-IgnoreWarnings` | `Object` | No | Ignores compiler warnings. Use this parameter to prevent `Add-Type` from handling compiler warnings as errors. |
| `-Language` | `Object` | No | Specifies the language that's used in the source code. The acceptable value for this parameter is `CSharp`. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to source code files or assembly DLL files that contain the types. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters are in... |
| `-MemberDefinition` | `Object` | Yes | Specifies new properties or methods for the class. `Add-Type` generates the template code that's required to support the properties or methods.   On Windows, you can use this feature to make Platfo... |
| `-Name` | `Object` | Yes | Specifies the name of the class to create. This parameter is required when generating a type from a member definition.   The type name and namespace must be unique within a session. You can't unloa... |
| `-Namespace` | `Object` | No | By default, this command creates the type in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace. When you use this parameter, the type is created in the specified namespace.... |
| `-OutputAssembly` | `Object` | No | Generates a DLL file for the assembly with the specified name in the location. Enter an optional path and filename. Wildcard characters are permitted. By default, `Add-Type` generates the assembly ... |
| `-OutputType` | `Object` | No | Specifies the output type of the output assembly. By default, no output type is specified. This parameter is valid only when an output assembly is specified in the command. For more information abo... |
| `-PassThru` | `Object` | No | Returns a **System.Runtime** object that represents the types that were added. By default, this cmdlet doesn't generate any output. Use this parameter if you used **OutputAssembly** to create a DLL... |
| `-Path` | `Object` | Yes | Specifies the path to source code files or assembly DLL files that contain the types.   If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly ... |
| `-ReferencedAssemblies` | `Object` | No | Specifies the assemblies upon which the type depends. By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`. Beginning in PowerShell 6, **ReferencedAssemblies** does... |
| `-TypeDefinition` | `Object` | Yes | Specifies the source code that contains the type definitions. Enter the source code in a string or here-string, or enter a variable that contains the source code. For more information about here-st... |
| `-UsingNamespace` | `Object` | No | Specifies other namespaces that are required for the class. This is much like the C# keyword, `Using`.   By default, `Add-Type` references the **System** namespace. When the **MemberDefinition** pa... |

---

### Clear-Variable

Deletes the value of a variable.

The `Clear-Variable` cmdlet deletes the data stored in a variable, but it does not delete the variable. As a result, the value of the variable is NULL (empty). If the variable has a specified data or object type, this cmdlet preserves the type of the object stored in the variable.

**Returns**: `None`

```
Clear-Variable
    [-Confirm <Object>]
    [-Exclude <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -Name <Object>
    [-PassThru <Object>]
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Exclude` | `Object` | No | Specifies an array of items that this cmdlet omits in the operation. The value of this parameter qualifies the **Name** parameter. Enter a name element or pattern, such as "s*". Wildcards are permi... |
| `-Force` | `Object` | No | Allows the cmdlet to clear a variable even if it is read-only. Even using the Force parameter, the cmdlet cannot clear constants. |
| `-Include` | `Object` | No | Specifies an array of items that this cmdlet includes in the operation. The value of this parameter qualifies the **Name** parameter. Enter a name element or pattern, such as "s*". Wildcards are pe... |
| `-Name` | `Object` | Yes | Specifies the name of the variable to be cleared. Wildcards are permitted. This parameter is required, but the parameter name **Name** is optional. |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Scope` | `Object` | No | Specifies the scope in which this alias is valid.   The acceptable values for this parameter are:   - `Global` - `Local` - `Script`   You can also use a number relative to the current scope (0 thro... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Compare-Object

Compares two sets of objects.

The `Compare-Object` cmdlet compares two sets of objects. One set of objects is the **reference**, and the other set of objects is the **difference**.

**Returns**: `None`

```
Compare-Object
    [-CaseSensitive <Object>]
    [-Culture <Object>]
    -DifferenceObject <Object>
    [-ExcludeDifferent <Object>]
    [-IncludeEqual <Object>]
    [-PassThru <Object>]
    [-Property <Object>]
    -ReferenceObject <Object>
    [-SyncWindow <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CaseSensitive` | `Object` | No | Indicates that comparisons should be case-sensitive. |
| `-Culture` | `Object` | No | Specifies the culture to use for comparisons. |
| `-DifferenceObject` | `Object` | Yes | Specifies the objects that are compared to the **reference** objects. |
| `-ExcludeDifferent` | `Object` | No | Indicates that this cmdlet displays only the characteristics of compared objects that are equal. The differences between the objects are discarded.   Use **ExcludeDifferent** with **IncludeEqual** ... |
| `-IncludeEqual` | `Object` | No | **IncludeEqual** displays the matches between the **reference** and **difference** objects.   By default, the output also includes the differences between the **reference** and **difference** objects. |
| `-PassThru` | `Object` | No | When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged. |
| `-Property` | `Object` | No | Specifies an array of properties of the **reference** and **difference** objects to compare.   The value of the **Property** parameter can be a new calculated property. The calculated property can ... |
| `-ReferenceObject` | `Object` | Yes | Specifies an array of objects used as a reference for comparison. |
| `-SyncWindow` | `Object` | No | Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects. `Compare-Object` examines adjacent objects when it doesn't find the obj... |

---

### ConvertFrom-CliXml

Converts a CliXml-formatted string to a custom **PSObject**.

The `ConvertFrom-CliXml` cmdlet converts strings that are formatted as Common Language Infrastructure (CLI) XML to a custom **PSObject**. This command is similar to `Import-Clixml`, but it doesn't read from a file. Instead, it takes a string as input.

**Returns**: `System.Object`

```
ConvertFrom-CliXml
    -InputObject <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | Yes | The object containing a CliXml-formatted string to be converted. |

---

### ConvertFrom-Csv

Converts object properties in character-separated value (CSV) format into CSV versions of the
original objects.

The `ConvertFrom-Csv` cmdlet converts character-separated value (CSV) data to **PSObject** type objects for each line of CSV data. The new objects are written to the pipeline in the order they are read from the CSV data. The values in column header row of the CSV become the names of the properties added to each new **PSObject**.

**Returns**: `System.Management.Automation.PSObject`

```
ConvertFrom-Csv
    [-Delimiter <Object>]
    [-Header <Object>]
    -InputObject <Object>
    -UseCulture <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Delimiter` | `Object` | No | Specifies the delimiter that separates the property values in the CSV data. The default is a comma (`,`).   Enter a character, such as a colon (`:`). To specify a semicolon (`;`), enclose it in sin... |
| `-Header` | `Object` | No | Specifies an alternate column header row for the imported string. The column header determines the property names of the objects created by `ConvertFrom-Csv`.   Enter column headers as a character-... |
| `-InputObject` | `Object` | Yes | Specifies the CSV strings to be converted to objects. Enter a variable that contains the CSV strings or type a command or expression that gets the CSV strings. You can also pipe the CSV strings to ... |
| `-UseCulture` | `Object` | Yes | Uses the list separator for the current culture as the item delimiter. To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`. |

---

### ConvertFrom-Json

Converts a JSON-formatted string to a custom object or a hash table.

The `ConvertFrom-Json` cmdlet converts a JavaScript Object Notation (JSON) formatted string to a custom **PSObject** or **Hashtable** object that has a property for each field in the JSON string. JSON is commonly used by web sites to provide a textual representation of objects. The cmdlet adds the properties to the new object as it processes each line of the JSON string.

**Returns**: `PSCustomObject`

```
ConvertFrom-Json
    [-AsHashtable <Object>]
    [-DateKind <Object>]
    [-Depth <Object>]
    -InputObject <Object>
    [-NoEnumerate <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsHashtable` | `Object` | No | Converts the JSON to a hash table object. This switch was introduced in PowerShell 6.0. Starting with PowerShell 7.3, the object is an **OrderedHashtable** and preserves the ordering of the keys fr... |
| `-DateKind` | `Object` | No | Specifies the method used when parsing date time values in the JSON string. The acceptable values for this parameter are:   - `Default` - `Local` - `Utc` - `Offset` - `String`   For information abo... |
| `-Depth` | `Object` | No | Gets or sets the maximum depth the JSON input is allowed to have. The default is 1024.   This parameter was introduced in PowerShell 6.2. |
| `-InputObject` | `Object` | Yes | Specifies the JSON strings to convert to JSON objects. Enter a variable that contains the string, or type a command or expression that gets the string. You can also pipe a string to `ConvertFrom-Js... |
| `-NoEnumerate` | `Object` | No | Specifies that output isn't enumerated.   Setting this parameter causes arrays to be sent as a single object instead of sending every element separately. This guarantees that JSON can be round-trip... |

---

### ConvertFrom-Markdown

Convert the contents of a string or a file to a **MarkdownInfo** object.

This cmdlet converts the specified content into a **MarkdownInfo**. When a file path is specified for the **Path** parameter, the contents on the file are converted. The output object has three properties:

**Returns**: `Microsoft.PowerShell.MarkdownRender.MarkdownInfo`

```
ConvertFrom-Markdown
    [-AsVT100EncodedString <Object>]
    -InputObject <Object>
    -LiteralPath <Object>
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsVT100EncodedString` | `Object` | No | Specifies if the output should be encoded as a string with VT100 escape codes. |
| `-InputObject` | `Object` | Yes | Specifies the object to be converted. When an object of type **System.String** is specified, the string is converted. When an object of type **System.IO.FileInfo** is specified, the contents of the... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to the file to be converted. |
| `-Path` | `Object` | Yes | Specifies a path to the file to be converted. |

---

### ConvertFrom-StringData

Converts a string containing one or more key and value pairs to a hash table.

The `ConvertFrom-StringData` cmdlet converts a string that contains one or more key and value pairs into a hash table. Because each key-value pair must be on a separate line, here-strings are often used as the input format. By default, the **key** must be separated from the **value** by an equals sign (`=`) character.

**Returns**: `System.Collections.Hashtable`

```
ConvertFrom-StringData
    [-Delimiter <Object>]
    -StringData <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Delimiter` | `Object` | No | The character used to separate the **key** from the **value** data in the string being converted. The default delimiter is the equals sign (`=`) character. This parameter was added in PowerShell 7. |
| `-StringData` | `Object` | Yes | Specifies the string to be converted. You can use this parameter or pipe a string to `ConvertFrom-StringData`. The parameter name is optional.   The value of this parameter must be a string that co... |

---

### ConvertTo-CliXml

Converts an object to a CliXml-formatted string.

The `ConvertTo-CliXml` cmdlet converts objects to strings that are formatted as Common Language Infrastructure (CLI) XML. This command is similar to `Export-Clixml`, but it doesn't write to a file. Instead, it outputs a string.

**Returns**: `System.String`

```
ConvertTo-CliXml
    [-Depth <Object>]
    -InputObject <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Depth` | `Object` | No | Specifies how many levels of contained objects are included in the XML representation. The default values is 2. |
| `-InputObject` | `Object` | Yes | The object to be converted to a CliXml-formatted string. |

---

### ConvertTo-Csv

Converts .NET objects into a series of character-separated value (CSV) strings.

The `ConvertTo-Csv` cmdlet returns a series of character-separated value (CSV) strings that represent the objects that you submit. You can then use the `ConvertFrom-Csv` cmdlet to recreate objects from the CSV strings. The objects converted from CSV are string values of the original objects that contain property values and no methods.

**Returns**: `System.String`

```
ConvertTo-Csv
    [-Delimiter <Object>]
    [-IncludeTypeInformation <Object>]
    -InputObject <Object>
    [-NoHeader <Object>]
    [-NoTypeInformation <Object>]
    [-QuoteFields <Object>]
    [-UseCulture <Object>]
    [-UseQuotes <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Delimiter` | `Object` | No | Specifies the delimiter to separate the property values in CSV strings. The default is a comma (`,`).   Enter a character, such as a colon (`:`). To specify a semicolon (`;`), enclose it in single ... |
| `-IncludeTypeInformation` | `Object` | No | When this parameter is used the first line of the output contains `#TYPE` followed by the fully qualified name of the object type. For example, `#TYPE System.Diagnostics.Process`.   This parameter ... |
| `-InputObject` | `Object` | Yes | Specifies the objects that are converted to CSV strings. Enter a variable that contains the objects or type a command or expression that gets the objects. You can also pipe objects to `ConvertTo-Csv`. |
| `-NoHeader` | `Object` | No | When this parameter is used, the cmdlet doesn't write a header row containing the column names to the output.   This parameter was added in PowerShell 7.4. |
| `-NoTypeInformation` | `Object` | No | Removes the `#TYPE` information header from the output. This parameter became the default in PowerShell 6.0 and is included for backwards compatibility. |
| `-QuoteFields` | `Object` | No | Specifies the names of the columns that should be quoted. When this parameter is used only the specified columns are quoted. This parameter was added in PowerShell 7.0. |
| `-UseCulture` | `Object` | No | Uses the list separator for the current culture as the item delimiter. To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`. |
| `-UseQuotes` | `Object` | No | Specifies when quotes are used in the CSV files. Possible values are:   - Never - don't quote anything - Always - quote everything (default behavior) - AsNeeded - only quote fields that contain a d... |

---

### ConvertTo-Html

Converts .NET objects into HTML that can be displayed in a Web browser.

The `ConvertTo-Html` cmdlet converts .NET objects into HTML that can be displayed in a Web browser. You can use this cmdlet to display the output of a command in a Web page.

**Returns**: `System.String`

```
ConvertTo-Html
    [-As <Object>]
    [-Body <Object>]
    [-Charset <Object>]
    [-CssUri <Object>]
    [-Fragment <Object>]
    [-Head <Object>]
    [-InputObject <Object>]
    [-Meta <Object>]
    [-PostContent <Object>]
    [-PreContent <Object>]
    [-Property <Object>]
    [-Title <Object>]
    [-Transitional <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-As` | `Object` | No | Determines whether the object is formatted as a table or a list. Valid values are **Table** and **List**. The default value is **Table**.   The **Table** value generates an HTML table that resemble... |
| `-Body` | `Object` | No | Specifies the text to add after the opening `<BODY>` tag. By default, there is no text in that position. |
| `-Charset` | `Object` | No | Specifies text to add to the opening `<charset>` tag. By default, there is no text in that position.   This parameter was introduced in PowerShell 6.0. |
| `-CssUri` | `Object` | No | Specifies the Uniform Resource Identifier (URI) of the cascading style sheet (CSS) that is applied to the HTML file. The URI is included in a style sheet link in the output. |
| `-Fragment` | `Object` | No | Generates only an HTML table. The `<HTML>`, `<HEAD>`, `<TITLE>`, and `<BODY>` tags are omitted. |
| `-Head` | `Object` | No | Specifies the content of the `<HEAD>` tag. The default is `<title\>HTML TABLE</title>`. If you use the **Head** parameter, the **Title** parameter is ignored. |
| `-InputObject` | `Object` | No | Specifies the objects to be represented in HTML. Enter a variable that contains the objects or type a command or expression that gets the objects.   If you use this parameter to submit multiple obj... |
| `-Meta` | `Object` | No | Specifies text to add to the opening `<meta>` tag. By default, there is no text in that position.   This parameter was introduced in PowerShell 6.0. |
| `-PostContent` | `Object` | No | Specifies text to add after the closing `</TABLE>` tag. By default, there is no text in that position. |
| `-PreContent` | `Object` | No | Specifies text to add before the opening `<TABLE>` tag. By default, there is no text in that position. |
| `-Property` | `Object` | No | Includes the specified properties of the objects in the HTML. The value of the **Property** parameter can be a new calculated property. The calculated property can be a scriptblock or a hash table.... |
| `-Title` | `Object` | No | Specifies a title for the HTML file, that is, the text that appears between the `<TITLE>` tags. |
| `-Transitional` | `Object` | No | Changes the `DOCTYPE` to **XHTML Transitional DTD**, Default `DOCTYPE` is **XHTML Strict DTD**.   This parameter was introduced in PowerShell 6.0. |

---

### ConvertTo-Json

Converts an object to a JSON-formatted string.

The `ConvertTo-Json` cmdlet converts any .NET object to a string in JavaScript Object Notation (JSON) format. The properties are converted to field names, the field values are converted to property values, and the methods are removed.

**Returns**: `System.String`

```
ConvertTo-Json
    [-AsArray <Object>]
    [-Compress <Object>]
    [-Depth <Object>]
    [-EnumsAsStrings <Object>]
    [-EscapeHandling <Object>]
    -InputObject <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsArray` | `Object` | No | Outputs the object in array brackets, even if the input is a single object. |
| `-Compress` | `Object` | No | Omits white space and indented formatting in the output string. |
| `-Depth` | `Object` | No | Specifies how many levels of contained objects are included in the JSON representation. The value can be any number from `0` to `100`. The default value is `2`. `ConvertTo-Json` emits a warning if ... |
| `-EnumsAsStrings` | `Object` | No | Provides an alternative serialization option that converts all enumerations to their string representation. |
| `-EscapeHandling` | `Object` | No | Controls how certain characters are escaped in the resulting JSON output. By default, only control characters (like newline) are escaped.   Acceptable values are:   - Default - Only control charact... |
| `-InputObject` | `Object` | Yes | Specifies the objects to convert to JSON format. Enter a variable that contains the objects, or type a command or expression that gets the objects. You can also pipe an object to `ConvertTo-Json`. ... |

---

### ConvertTo-Xml

Creates an XML-based representation of an object.

The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more .NET objects. To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.

**Returns**: `System.String`

```
ConvertTo-Xml
    [-As <Object>]
    [-Depth <Object>]
    -InputObject <Object>
    [-NoTypeInformation <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-As` | `Object` | No | Determines the output format. The acceptable values for this parameter are:   - `String` - Returns a single string. - `Stream` - Returns an array of strings. - `Document` - Returns an **XmlDocument... |
| `-Depth` | `Object` | No | Specifies how many levels of contained objects are included in the XML representation. The default value is 1.   For example, if the object's properties also contain objects, to save an XML represe... |
| `-InputObject` | `Object` | Yes | Specifies the object to be converted. Enter a variable that contains the objects, or type a command or expression that gets the objects. You can also pipe objects to `ConvertTo-Xml`. |
| `-NoTypeInformation` | `Object` | No | Omits the Type attribute from the object nodes. |

---

### Debug-Runspace

Starts an interactive debugging session with a runspace.

The `Debug-Runspace` cmdlet starts an interactive debugging session with a local or remote active runspace. You can find a runspace that you want to debug by first running `Get-Process` to find processes associated with PowerShell, then `Enter-PSHostProcess` with the process ID specified in the **Id** parameter to attach to the process, and then `Get-Runspace` to list runspaces within the PowerShell host process.

**Returns**: `None documented`

```
Debug-Runspace
    [-BreakAll <Object>]
    [-Confirm <Object>]
    -Id <Object>
    -InstanceId <Object>
    -Name <Object>
    -Runspace <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BreakAll` | `Object` | No | Allows you to break immediately in the current location when the debugger attaches.   This parameter was added in PowerShell 7.2. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | Yes | Specifies the ID number of a runspace. You can run `Get-Runspace` to show runspace IDs. |
| `-InstanceId` | `Object` | Yes | Specifies a runspace by its instance ID, a GUID that you can show by running `Get-Runspace`. |
| `-Name` | `Object` | Yes | Specifies a runspace by its name. You can run `Get-Runspace` to show the names of runspaces. |
| `-Runspace` | `Object` | Yes | Specifies a runspace object. The simplest way to provide a value for this parameter is to specify a variable that contains the results of a filtered `Get-Runspace` command. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Disable-PSBreakpoint

Disables the breakpoints in the current console.

The `Disable-PSBreakpoint` cmdlet disables breakpoints, which assures that they are not hit when the script runs. You can use it to disable all breakpoints, or you can specify breakpoints by submitting breakpoint objects or breakpoint IDs.

**Returns**: `None`

```
Disable-PSBreakpoint
    -Breakpoint <Object>
    [-Confirm <Object>]
    -Id <Object>
    [-PassThru <Object>]
    [-Runspace <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Breakpoint` | `Object` | Yes | Specifies the breakpoints to disable. Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a `Get-PSBreakpoint` command. You can also pipe breakpoint... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | Yes | Disables the breakpoints with the specified breakpoint IDs. Enter the IDs or a variable that contains the IDs. You cannot pipe IDs to `Disable-PSBreakpoint`. |
| `-PassThru` | `Object` | No | Returns an object representing the enabled breakpoints. By default, this cmdlet does not generate any output. |
| `-Runspace` | `Object` | No | Specifies the Id of a **Runspace** object so you can interact with breakpoints in the specified runspace.   This parameter was added in PowerShell 7.2. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Disable-RunspaceDebug

Disables debugging on one or more runspaces, and releases any pending debugger stop.

The `Disable-RunspaceDebug` cmdlet disables debugging on one or more runspaces, and releases any pending debugger stop.

**Returns**: `None documented`

```
Disable-RunspaceDebug
    [-AppDomainName <Object>]
    [-ProcessName <Object>]
    -Runspace <Object>
    -RunspaceId <Object>
    -RunspaceInstanceId <Object>
    [-RunspaceName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AppDomainName` | `Object` | No | The name of the application domain that hosts the PowerShell runspace. |
| `-ProcessName` | `Object` | No | The name of the process that hosts the PowerShell runspace. |
| `-Runspace` | `Object` | Yes | One or more **Runspace** objects to be disabled. |
| `-RunspaceId` | `Object` | Yes | One or more **Runspace** Id numbers to be disabled. |
| `-RunspaceInstanceId` | `Object` | Yes | One or more **Runspace** GUIDs to be disabled. |
| `-RunspaceName` | `Object` | No | One or more **Runspace** names to be disabled. |

---

### Enable-PSBreakpoint

Enables the breakpoints in the current console.

The `Enable-PSBreakpoint` cmdlet re-enables disabled breakpoints. You can use it to enable all breakpoints, or specific breakpoints by providing breakpoint objects or IDs.

**Returns**: `None`

```
Enable-PSBreakpoint
    -Breakpoint <Object>
    [-Confirm <Object>]
    -Id <Object>
    [-PassThru <Object>]
    [-Runspace <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Breakpoint` | `Object` | Yes | Specifies the breakpoints to enable. Provide a variable containing breakpoints or a command that gets breakpoint objects, such as `Get-PSBreakpoint`. You can also pipe breakpoint objects to `Enable... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | Yes | Specifies the **Id** numbers of the breakpoints to enable. The default value is all breakpoints. Provide the **Id** by number or in a variable. You can't pipe **Id** numbers to `Enable-PSBreakpoint... |
| `-PassThru` | `Object` | No | Returns an object representing the breakpoint being enabled. By default, this cmdlet doesn't generate any output. |
| `-Runspace` | `Object` | No | Specifies the Id of a **Runspace** object so you can interact with breakpoints in the specified runspace.   This parameter was added in PowerShell 7.2. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Enable-RunspaceDebug

Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.

The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.

**Returns**: `None documented`

```
Enable-RunspaceDebug
    [-AppDomainName <Object>]
    [-BreakAll <Object>]
    [-ProcessName <Object>]
    -Runspace <Object>
    -RunspaceId <Object>
    -RunspaceInstanceId <Object>
    [-RunspaceName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AppDomainName` | `Object` | No | The name of the application domain that hosts the PowerShell runspace. |
| `-BreakAll` | `Object` | No | Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached. The script or command will remain stopped until a debugger is atta... |
| `-ProcessName` | `Object` | No | The name of the process that hosts the PowerShell runspace. |
| `-Runspace` | `Object` | Yes | One or more **Runspace** objects to be disabled. |
| `-RunspaceId` | `Object` | Yes | One or more **Runspace** Id numbers to be disabled. |
| `-RunspaceInstanceId` | `Object` | Yes | One or more **Runspace** GUIDs to be disabled. |
| `-RunspaceName` | `Object` | No | One or more **Runspace** names to be disabled. |

---

### Export-Alias

Exports information about currently defined aliases to a file.

The `Export-Alias` cmdlet exports the aliases in the current session to a file. If the output file does not exist, the cmdlet will create it.

**Returns**: `None`

```
Export-Alias
    [-Append <Object>]
    [-As <Object>]
    [-Confirm <Object>]
    [-Description <Object>]
    [-Force <Object>]
    -LiteralPath <Object>
    [-Name <Object>]
    [-NoClobber <Object>]
    [-PassThru <Object>]
    -Path <Object>
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Append` | `Object` | No | Indicates that this cmdlet appends the output to the specified file, rather than overwriting the existing contents of that file. |
| `-As` | `Object` | No | Specifies the output format. CSV is the default. The acceptable values for this parameter are:   - CSV. Comma-separated value (CSV) format. - Script. Creates a `Set-Alias` command for each exported... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Description` | `Object` | No | Specifies the description of the exported file. The description appears as a comment at the top of the file, following the header information. |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation.   Overwrites the output file, even if the read-only attribute is set on the file.   By default, `Export-Alias` overwrites files witho... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to the output file. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes e... |
| `-Name` | `Object` | No | Specifies the names as an array of the aliases to export. Wildcards are permitted.   By default, `Export-Alias` exports all aliases in the session or scope. |
| `-NoClobber` | `Object` | No | Indicates that this cmdlet prevents `Export-Alias` from overwriting any files, even if the **Force** parameter is used in the command.   If the **NoClobber** parameter is omitted, `Export-Alias` wi... |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path to the output file. Wildcards are permitted, but the resulting path value must resolve to a single file name. |
| `-Scope` | `Object` | No | Specifies the scope from which the aliases should be exported. The acceptable values for this parameter are:   - `Global` - `Local` - `Script` - A number relative to the current scope (0 through th... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Export-Clixml

Creates an XML-based representation of an object or objects and stores it in a file.

The `Export-Clixml` cmdlet serializes an object into a Common Language Infrastructure (CLI) XML-based representation and stores it in a file. You can then use the `Import-Clixml` cmdlet to recreate the saved object based on the contents of that file. For more information about CLI, see [Language independence](/dotnet/standard/language-independence).

**Returns**: `System.IO.FileInfo`

```
Export-Clixml
    [-Confirm <Object>]
    [-Depth <Object>]
    [-Encoding <Object>]
    [-Force <Object>]
    -InputObject <Object>
    -LiteralPath <Object>
    [-NoClobber <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Depth` | `Object` | No | Specifies how many levels of contained objects are included in the XML representation. The default value is `2`.   The default value can be overridden for the object type in the `Types.ps1xml` file... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation.   Causes the cmdlet to clear the read-only attribute of the output file if necessary. The cmdlet will attempt to reset the read-only ... |
| `-InputObject` | `Object` | Yes | Specifies the object to be converted. Enter a variable that contains the objects, or type a command or expression that gets the objects. You can also pipe objects to `Export-Clixml`. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to the file where the XML representation of the object will be stored. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters ar... |
| `-NoClobber` | `Object` | No | Indicates that the cmdlet doesn't overwrite the contents of an existing file. By default, if a file exists in the specified path, `Export-Clixml` overwrites the file without warning. |
| `-Path` | `Object` | Yes | Specifies the path to the file where the XML representation of the object will be stored. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Export-Csv

Converts objects into a series of character-separated value (CSV) strings and saves the strings to a
file.

The `Export-Csv` cmdlet creates a CSV file of the objects that you submit. Each object is a row that includes a character-separated list of the object's property values. You can use the `Export-Csv` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.

**Returns**: `None`

```
Export-Csv
    [-Append <Object>]
    [-Confirm <Object>]
    [-Delimiter <Object>]
    [-Encoding <Object>]
    [-Force <Object>]
    [-IncludeTypeInformation <Object>]
    -InputObject <Object>
    [-LiteralPath <Object>]
    [-NoClobber <Object>]
    [-NoHeader <Object>]
    [-NoTypeInformation <Object>]
    [-Path <Object>]
    [-QuoteFields <Object>]
    [-UseCulture <Object>]
    [-UseQuotes <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Append` | `Object` | No | Use this parameter so that `Export-Csv` adds CSV output to the end of the specified file. Without this parameter, `Export-Csv` replaces the file contents without warning.   This parameter was intro... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Delimiter` | `Object` | No | Specifies a delimiter to separate the property values. The default is a comma (`,`).   Enter a character, such as a colon (`:`). To specify a semicolon (`;`), enclose it in single quotation marks. ... |
| `-Encoding` | `Object` | No | Specifies the encoding for the exported CSV file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit) c... |
| `-Force` | `Object` | No | This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.   When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be wr... |
| `-IncludeTypeInformation` | `Object` | No | When this parameter is used the first line of the CSV output contains `#TYPE` followed by the fully qualified name of the object type. For example, `#TYPE System.Diagnostics.Process`.   This parame... |
| `-InputObject` | `Object` | Yes | Specifies the objects to export as CSV strings. Enter a variable that contains the objects or type a command or expression that gets the objects. You can also pipe objects to `Export-Csv`. |
| `-LiteralPath` | `Object` | No | Specifies the path to the CSV output file. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards. If the path includ... |
| `-NoClobber` | `Object` | No | Use this parameter so that `Export-Csv` does not overwrite an existing file. By default, if the file exists in the specified path, `Export-Csv` overwrites the file without warning. |
| `-NoHeader` | `Object` | No | When this parameter is used, the cmdlet doesn't write a header row containing the column names to the output.   This parameter was added in PowerShell 7.4. |
| `-NoTypeInformation` | `Object` | No | Removes the `#TYPE` information header from the output. This parameter became the default in PowerShell 6.0 and is included for backwards compatibility. |
| `-Path` | `Object` | No | A required parameter that specifies the location to save the CSV output file. |
| `-QuoteFields` | `Object` | No | Specifies the names of the columns that should be quoted. When this parameter is used, only the specified columns are quoted. This parameter was added in PowerShell 7.0. |
| `-UseCulture` | `Object` | No | Uses the list separator for the current culture as the item delimiter. To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`. |
| `-UseQuotes` | `Object` | No | Specifies when quotes are used in the CSV files. Possible values are:   - Never - don't quote anything - Always - quote everything (default behavior) - AsNeeded - only quote fields that contain a d... |
| `-WhatIf` | `Object` | No | Prevents the cmdlet from being processed or making changes. The output shows what would happen if the cmdlet were run. |

---

### Export-FormatData

Saves formatting data from the current session in a formatting file.

The `Export-FormatData` cmdlet creates PowerShell formatting files (`format.ps1xml`) from the formatting objects in the current session. It takes the **ExtendedTypeDefinition** objects that `Get-FormatData` returns and saves them in a file in XML format.

**Returns**: `None`

```
Export-FormatData
    [-Force <Object>]
    [-IncludeScriptBlock <Object>]
    -InputObject <Object>
    -LiteralPath <Object>
    [-NoClobber <Object>]
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation. |
| `-IncludeScriptBlock` | `Object` | No | Indicates whether scriptblocks in the format data are exported.   Because scriptblocks contain code and can be used maliciously, they are not exported by default. |
| `-InputObject` | `Object` | Yes | Specifies the format data objects to be exported. Enter a variable that contains the objects or a command that gets the objects, such as a `Get-FormatData` command. You can also pipe the objects fr... |
| `-LiteralPath` | `Object` | Yes | Specifies a location for the output file. Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path include... |
| `-NoClobber` | `Object` | No | Indicates that the cmdlet does not overwrite existing files. By default, `Export-FormatData` overwrites files without warning unless the file has the read-only attribute.   To direct `Export-Format... |
| `-Path` | `Object` | Yes | Specifies a location for the output file. Enter a path (optional) and file name with a `format.ps1xml` file name extension. If you omit the path, `Export-FormatData` creates the file in the current... |

---

### Export-PSSession

Exports commands from another session and saves them in a PowerShell module.

The `Export-PSSession` cmdlet gets cmdlets, functions, aliases, and other command types from another PowerShell session (PSSession) on a local or remote computer and saves them in a PowerShell module. To add the commands from the module to the current session, use the `Import-Module` cmdlet.

**Returns**: `System.IO.FileInfo`

```
Export-PSSession
    [-AllowClobber <Object>]
    [-ArgumentList <Object>]
    [-Certificate <Object>]
    [-CommandName <Object>]
    [-CommandType <Object>]
    [-Encoding <Object>]
    [-Force <Object>]
    [-FormatTypeName <Object>]
    [-FullyQualifiedModule <Object>]
    [-Module <Object>]
    -OutputModule <Object>
    -Session <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowClobber` | `Object` | No | Exports the specified commands, even if they have the same names as commands in the current session.   If you export a command with the same name as a command in the current session, the exported c... |
| `-ArgumentList` | `Object` | No | Exports the variant of the command that results from using the specified arguments (parameter values).   For example, to export the variant of the `Get-Item` command in the certificate (Cert:) driv... |
| `-Certificate` | `Object` | No | Specifies the client certificate that is used to sign the format files (*.Format.ps1xml) or script module files (`.psm1`) in the module that `Export-PSSession` creates. Enter a variable that contai... |
| `-CommandName` | `Object` | No | Exports only the commands with the specified names or name patterns. Wildcards are permitted. Use **CommandName** or its alias, **Name**.   By default, `Export-PSSession` exports all commands from ... |
| `-CommandType` | `Object` | No | Exports only the specified types of command objects. Use **CommandType** or its alias, **Type**.   The acceptable values for this parameter are as follows:   - `Alias`: All PowerShell aliases in th... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-Force` | `Object` | No | Overwrites one or more existing output files, even if the file has the read-only attribute. |
| `-FormatTypeName` | `Object` | No | Exports formatting instructions only for the specified Microsoft .NET Framework types. Enter the type names. By default, `Export-PSSession` exports formatting instructions for all .NET Framework ty... |
| `-FullyQualifiedModule` | `Object` | No | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-Module` | `Object` | No | Exports only the commands in the specified PowerShell snap-ins and modules. Enter the snap-in and module names. Wildcards are not permitted.   For more information, see `Import-Module` and [about_P... |
| `-OutputModule` | `Object` | Yes | Specifies an optional path and name for the module created by `Export-PSSession`. The default path is `$HOME\Documents\WindowsPowerShell\Modules`. This parameter is required.   If the module subdir... |
| `-Session` | `Object` | Yes | Specifies the PSSession from which the commands are exported. Enter a variable that contains a session object or a command that gets a session object, such as a `Get-PSSession` command. This parame... |

---

### Format-Custom

Uses a customized view to format the output.

The `Format-Custom` cmdlet formats the output of a command as defined in an alternate view. `Format-Custom` is designed to display views that are not just tables or just lists. You can use the views defined in PowerShell, or you can create your own views in a new `format.ps1xml` file and use the `Update-FormatData` cmdlet to add them to PowerShell.

**Returns**: `Microsoft.PowerShell.Commands.Internal.Format`

```
Format-Custom
    [-Depth <Object>]
    [-DisplayError <Object>]
    [-Expand <Object>]
    [-Force <Object>]
    [-GroupBy <Object>]
    [-InputObject <Object>]
    [-Property <Object>]
    [-ShowError <Object>]
    [-View <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Depth` | `Object` | No | Specifies the number of columns in the display. |
| `-DisplayError` | `Object` | No | Displays errors at the command line. This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not a... |
| `-Expand` | `Object` | No | Formats the collection object, as well as the objects in the collection. This parameter is designed to format objects that support the **System.Collections.ICollection** interface. The default valu... |
| `-Force` | `Object` | No | Directs the cmdlet to display all of the error information. Use with the **DisplayError** or **ShowError** parameters. By default, when an error object is written to the error or display streams, o... |
| `-GroupBy` | `Object` | No | Formats the output in groups based on a shared property or value. Enter an expression or a property of the output. The **GroupBy** parameter expects that the objects are sorted. Use the `Sort-Objec... |
| `-InputObject` | `Object` | No | Specifies the objects to be formatted. Enter a variable that contains the objects or type a command or expression that gets the objects. |
| `-Property` | `Object` | No | Specifies the object properties that appear in the display and the order in which they appear. Wildcards are permitted.   If you omit this parameter, the properties that appear in the display depen... |
| `-ShowError` | `Object` | No | Sends errors through the pipeline. This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Custom` command, and the expressions do not app... |
| `-View` | `Object` | No | Specifies the name of an alternate format or view. If you omit this parameter, `Format-Custom` uses a default custom view. You cannot use the **Property** and **View** parameters in the same command. |

---

### Format-Hex

Displays a file or other input as hexadecimal.

The `Format-Hex` cmdlet displays a file or other input as hexadecimal values. To determine the offset of a character from the output, add the number at the leftmost of the row to the number at the top of the column for that character.

**Returns**: `Microsoft.PowerShell.Commands.ByteCollection`

```
Format-Hex
    [-Count <Object>]
    [-Encoding <Object>]
    -InputObject <Object>
    -LiteralPath <Object>
    [-Offset <Object>]
    -Path <Object>
    [-Raw <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Count` | `Object` | No | This represents the number of bytes to include in the hex output.   This parameter was introduced in PowerShell 6.2. |
| `-Encoding` | `Object` | No | Specifies the encoding of the input strings. This only applies to `[string]` input. The parameter has no effect on numeric types. The output value is always `utf8NoBOM`.   The acceptable values for... |
| `-InputObject` | `Object` | Yes | Specifies the objects to be formatted. Enter a variable that contains the objects or type a command or expression that gets the objects.   Only certain [scalar](/powershell/scripting/learn/glossary... |
| `-LiteralPath` | `Object` | Yes | Specifies the complete path to a file. The value of **LiteralPath** is used exactly as it is typed. This parameter does not accept wildcard characters. To specify multiple paths to files, separate ... |
| `-Offset` | `Object` | No | This represents the number of bytes to skip from being part of the hex output.   This parameter was introduced in PowerShell 6.2. |
| `-Path` | `Object` | Yes | Specifies the path to files. Use a dot (`.`) to specify the current location. The wildcard character (`*`) is accepted and can be used to specify all the items in a location. If the **Path** parame... |
| `-Raw` | `Object` | No | This parameter no longer does anything. It is retained for script compatibility. |

---

### Format-List

Formats the output as a list of properties in which each property appears on a new line.

The `Format-List` cmdlet formats the output of a command as a list of properties in which each property is displayed on a separate line. You can use `Format-List` to format and display all or selected properties of an object as a list (`Format-List -Property *`).

**Returns**: `Microsoft.PowerShell.Commands.Internal.Format`

```
Format-List
    [-DisplayError <Object>]
    [-Expand <Object>]
    [-Force <Object>]
    [-GroupBy <Object>]
    [-InputObject <Object>]
    [-Property <Object>]
    [-ShowError <Object>]
    [-View <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DisplayError` | `Object` | No | Indicates that this cmdlet displays errors at the command line. This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and... |
| `-Expand` | `Object` | No | Specifies the formatted collection object, as well as the objects in the collection. This parameter is designed to format objects that support the **System.Collections.ICollection** interface. The ... |
| `-Force` | `Object` | No | Indicates that this cmdlet displays all the error information. Use with the **DisplayError** or **ShowError** parameter. By default, when an error object is written to the error or display streams,... |
| `-GroupBy` | `Object` | No | Specifies the output in groups based on a shared property or value. Enter an expression or a property of the output. The **GroupBy** parameter expects that the objects are sorted. Use the `Sort-Obj... |
| `-InputObject` | `Object` | No | Specifies the objects to be formatted. Enter a variable that contains the objects or type a command or expression that gets the objects. |
| `-Property` | `Object` | No | Specifies the object properties that appear in the display and the order in which they appear. Wildcards are permitted.   If you omit this parameter, the properties that appear in the display depen... |
| `-ShowError` | `Object` | No | Indicates that the cmdlet sends errors through the pipeline. This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-List` command, and th... |
| `-View` | `Object` | No | Specifies the name of an alternate list format or view. You cannot use the **Property** and **View** parameters in the same command. |

---

### Format-Table

Formats the output as a table.

The `Format-Table` cmdlet formats the output of a command as a table with the selected properties of the object in each column. The object type determines the default layout and properties that are displayed in each column. You can use the **Property** parameter to select the properties that you want to display.

**Returns**: `Microsoft.PowerShell.Commands.Internal.Format`

```
Format-Table
    [-AutoSize <Object>]
    [-DisplayError <Object>]
    [-Expand <Object>]
    [-Force <Object>]
    [-GroupBy <Object>]
    [-HideTableHeaders <Object>]
    [-InputObject <Object>]
    [-Property <Object>]
    [-RepeatHeader <Object>]
    [-ShowError <Object>]
    [-View <Object>]
    [-Wrap <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutoSize` | `Object` | No | Indicates that the cmdlet adjusts the column size and number of columns based on the width of the data. By default, the column size and number are determined by the view. |
| `-DisplayError` | `Object` | No | Indicates that the cmdlet displays errors on the command line. This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot ... |
| `-Expand` | `Object` | No | Specifies the format of the collection object and the objects in the collection. This parameter is designed to format objects that support the [ICollection](xref:System.Collections.ICollection)([Sy... |
| `-Force` | `Object` | No | Indicates that the cmdlet directs the cmdlet to display all the error information. Use with the **DisplayError** or **ShowError** parameter. By default, when an error object is written to the error... |
| `-GroupBy` | `Object` | No | Specifies sorted output in separate tables based on a property value. For example, you can use **GroupBy** to list services in separate tables based on their status.   Enter an expression or a prop... |
| `-HideTableHeaders` | `Object` | No | Omits the column headings from the table. |
| `-InputObject` | `Object` | No | Specifies the objects to format. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-Property` | `Object` | No | Specifies the object properties that appear in the display and the order in which they appear. Type one or more property names, separated by commas, or use a hash table to display a calculated prop... |
| `-RepeatHeader` | `Object` | No | Repeats displaying the header of a table after every screen full. The repeated header is useful when the output is piped to a pager such as `less` or `more` or paging with a screen reader. |
| `-ShowError` | `Object` | No | This parameter sends errors through the pipeline. This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions. |
| `-View` | `Object` | No | Beginning in PowerShell 6, the default views are defined in PowerShell `C#` source code. The `*.format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later v... |
| `-Wrap` | `Object` | No | Displays text that exceeds the column width on the next line. By default, text that exceeds the column width is truncated. |

---

### Format-Wide

Formats objects as a wide table that displays only one property of each object.

The `Format-Wide` cmdlet formats objects as a wide table that displays only one property of each object. You can use the **Property** parameter to determine which property is displayed.

**Returns**: `Microsoft.PowerShell.Commands.Internal.Format`

```
Format-Wide
    [-AutoSize <Object>]
    [-Column <Object>]
    [-DisplayError <Object>]
    [-Expand <Object>]
    [-Force <Object>]
    [-GroupBy <Object>]
    [-InputObject <Object>]
    [-Property <Object>]
    [-ShowError <Object>]
    [-View <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AutoSize` | `Object` | No | Adjusts the column size and number of columns based on the width of the data. By default, the column size and number are determined by the view. You cannot use the **AutoSize** and **Column** param... |
| `-Column` | `Object` | No | Specifies the number of columns in the display. You cannot use the **AutoSize** and **Column** parameters in the same command. |
| `-DisplayError` | `Object` | No | Displays errors at the command line. This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not app... |
| `-Expand` | `Object` | No | Formats the collection object, as well as the objects in the collection. This parameter is designed to format objects that support the **System.Collections.ICollection** interface. The default valu... |
| `-Force` | `Object` | No | Indicates that this cmdlet overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security. For example, **Force** will override the read-only attrib... |
| `-GroupBy` | `Object` | No | Formats the output in groups based on a shared property or value. Enter an expression or a property of the output. The **GroupBy** parameter expects that the objects are sorted. Use the `Sort-Objec... |
| `-InputObject` | `Object` | No | Specifies the objects to format. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-Property` | `Object` | No | Specifies the object property that appears in the display. Wildcards are permitted.   If you omit this parameter, the properties that appear in the display depend on the object being displayed. The... |
| `-ShowError` | `Object` | No | Sends errors through the pipeline. This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appea... |
| `-View` | `Object` | No | Specifies the name of an alternate table format or view. You cannot use the **Property** and **View** parameters in the same command. |

---

### Get-Alias

Gets the aliases for the current session.

The `Get-Alias` cmdlet gets the aliases in the current session. This includes built-in aliases, aliases that you have set or imported, and aliases that you have added to your PowerShell profile.

**Returns**: `System.Management.Automation.AliasInfo`

```
Get-Alias
    [-Definition <Object>]
    [-Exclude <Object>]
    [-Name <Object>]
    [-Scope <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Definition` | `Object` | No | Gets the aliases for the specified item. Enter the name of a cmdlet, function, script, file, or executable file.   This parameter is called **Definition**, because it searches for the item name in ... |
| `-Exclude` | `Object` | No | Omits the specified items. The value of this parameter qualifies the **Name** and **Definition** parameters. Enter a name, a definition, or a pattern, such as "s*". Wildcards are permitted. |
| `-Name` | `Object` | No | Specifies the aliases that this cmdlet gets. Wildcards are permitted. By default, `Get-Alias` retrieves all aliases defined for the current session. The parameter name **Name** is optional. You can... |
| `-Scope` | `Object` | No | Specifies the scope for which this cmdlet gets aliases. The acceptable values for this parameter are:   - `Global` - `Local` - `Script` - A number relative to the current scope (0 through the numbe... |

---

### Get-Culture

Gets the current culture set in the operating system.

The `Get-Culture` cmdlet gets information about the current culture settings. This includes information about the current language settings on the system, such as the keyboard layout, and the display format of items such as numbers, currency, and dates.

**Returns**: `System.Globalization.CultureInfo`

```
Get-Culture
    [-ListAvailable <Object>]
    [-Name <Object>]
    [-NoUserOverrides <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ListAvailable` | `Object` | No | Retrieves all cultures supported by the current operating system.   This parameter was introduced in PowerShell 6.2. |
| `-Name` | `Object` | No | Retrieve a specific culture based on the name.   This parameter was introduced in PowerShell 6.2. |
| `-NoUserOverrides` | `Object` | No | Ignore user changes for current culture.   This parameter was introduced in PowerShell 6.2. |

---

### Get-Date

Gets the current date and time.

The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify. `Get-Date` can format the date and time in several .NET and Unix formats. You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.

**Returns**: `System.DateTime`

```
Get-Date
    [-AsUTC <Object>]
    [-Date <Object>]
    [-Day <Object>]
    [-DisplayHint <Object>]
    [-Format <Object>]
    [-Hour <Object>]
    [-Millisecond <Object>]
    [-Minute <Object>]
    [-Month <Object>]
    [-Second <Object>]
    [-UFormat <Object>]
    -UnixTimeSeconds <Object>
    [-Year <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsUTC` | `Object` | No | Converts the date value to the equivalent time in UTC.   This parameter was introduced in PowerShell 7.1. |
| `-Date` | `Object` | No | Specifies a date and time. Time is optional and if not specified, returns 00:00:00. Enter the date and time in a format that is standard for the currently selected locale. You can change the curren... |
| `-Day` | `Object` | No | Specifies the day of the month that is displayed. Enter a value from 1 to 31.   If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month... |
| `-DisplayHint` | `Object` | No | Determines which elements of the date and time are displayed.   The accepted values are as follows:   - **Date**: displays only the date - **Time**: displays only the time - **DateTime**: displays ... |
| `-Format` | `Object` | No | Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier. The **Format** parameter outputs a **String** object.   For a list of available .NET format spec... |
| `-Hour` | `Object` | No | Specifies the hour that is displayed. Enter a value from 0 to 23. |
| `-Millisecond` | `Object` | No | Specifies the milliseconds in the date. Enter a value from 0 to 999.   This parameter was introduced in PowerShell 3.0. |
| `-Minute` | `Object` | No | Specifies the minute that is displayed. Enter a value from 0 to 59. |
| `-Month` | `Object` | No | Specifies the month that is displayed. Enter a value from 1 to 12. |
| `-Second` | `Object` | No | Specifies the second that is displayed. Enter a value from 0 to 59. |
| `-UFormat` | `Object` | No | Displays the date and time in Unix format. The **UFormat** parameter outputs a string object.   **UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`. The [... |
| `-UnixTimeSeconds` | `Object` | Yes | Date and time represented in seconds since January 1, 1970, 0:00:00.   This parameter was introduced in PowerShell 7.1. |
| `-Year` | `Object` | No | Specifies the year that is displayed. Enter a value from 1 to 9999. |

---

### Get-Error

Gets and displays the most recent error messages from the current session.

The `Get-Error` cmdlet gets a **PSExtendedError** object that represents the current error details from the last error that occurred in the session.

**Returns**: `System.Management.Automation.ErrorRecord#PSExtendedError`

```
Get-Error
    [-InputObject <Object>]
    [-Newest <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | No | This parameter is used for pipeline input. |
| `-Newest` | `Object` | No | Specifies the number of errors to display that have occurred in the current session. |

---

### Get-Event

Gets the events in the event queue.

The `Get-Event` cmdlet gets events in the PowerShell event queue for the current session. You can get all events or use the **EventIdentifier** or **SourceIdentifier** parameter to specify the events.

**Returns**: `System.Management.Automation.PSEventArgs`

```
Get-Event
    -EventIdentifier <Object>
    [-SourceIdentifier <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-EventIdentifier` | `Object` | Yes | Specifies the event identifiers for which this cmdlet gets events. |
| `-SourceIdentifier` | `Object` | No | Specifies source identifiers for which this cmdlet gets events. The default is all events in the event queue. Wildcards are not permitted. |

---

### Get-EventSubscriber

Gets the event subscribers in the current session.

The `Get-EventSubscriber` cmdlet gets the event subscribers in the current session.

**Returns**: `System.Management.Automation.PSEventSubscriber`

```
Get-EventSubscriber
    [-Force <Object>]
    [-SourceIdentifier <Object>]
    -SubscriptionId <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `Object` | No | Indicates that this cmdlet gets all event subscribers, including subscribers for events that are hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `... |
| `-SourceIdentifier` | `Object` | No | Specifies the **SourceIdentifier** property value that gets only the event subscribers. By default, `Get-EventSubscriber` gets all event subscribers in the session. Wildcards are not permitted. Thi... |
| `-SubscriptionId` | `Object` | Yes | Specifies the subscription identifier that this cmdlet gets. By default, `Get-EventSubscriber` gets all event subscribers in the session. |

---

### Get-FileHash

Computes the hash value for a file by using a specified hash algorithm.

The `Get-FileHash` cmdlet computes the hash value for a file by using a specified hash algorithm. A hash value is a unique value that corresponds to the content of the file. Rather than identifying the contents of a file by its file name, extension, or other designation, a hash assigns a unique value to the contents of a file. File names and extensions can be changed without altering the content of the file, and without changing the hash value. Similarly, the file's content can be changed wit...

**Returns**: `Microsoft.PowerShell.Utility.FileHash`

```
Get-FileHash
    [-Algorithm <Object>]
    -InputStream <Object>
    -LiteralPath <Object>
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Algorithm` | `Object` | No | Specifies the cryptographic hash function to use for computing the hash value of the contents of the specified file or stream. A cryptographic hash function has the property that it is infeasible t... |
| `-InputStream` | `Object` | Yes | Specifies the input stream. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to a file. Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcard characters. If the ... |
| `-Path` | `Object` | Yes | Specifies the path to one or more files as an array. Wildcard characters are permitted. |

---

### Get-FormatData

Gets the formatting data in the current session.

The `Get-FormatData` cmdlet gets the formatting data in the current session.

**Returns**: `System.Management.Automation.ExtendedTypeDefinition`

```
Get-FormatData
    [-PowerShellVersion <Object>]
    [-TypeName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PowerShellVersion` | `Object` | No | Specify the version of PowerShell this cmdlet gets for the formatting data. Enter a two digit number separated by a period.   This parameter was added in PowerShell 5.1 to improve compatibility whe... |
| `-TypeName` | `Object` | No | Specifies the type names that this cmdlet gets for the formatting data. Enter the type names. Wildcards are permitted. |

---

### Get-Host

Gets an object that represents the current host program.

The `Get-Host` cmdlet gets an object that represents the program that is hosting Windows PowerShell.

**Returns**: `System.Management.Automation.Internal.Host.InternalHost`

```
Get-Host
```

---

### Get-MarkdownOption

Returns the current colors and styles used for rendering Markdown content in the console.

Returns the current colors and styles used for rendering Markdown content in the console. The strings displayed in the output of this cmdlet contain the ANSI escape codes used to change the color and style of the Markdown text being rendered.

**Returns**: `Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo`

```
Get-MarkdownOption
```

---

### Get-Member

Gets the properties and methods of objects.

The `Get-Member` cmdlet gets the members, the properties and methods, of objects.

**Returns**: `Microsoft.PowerShell.Commands.MemberDefinition`

```
Get-Member
    [-Force <Object>]
    [-InputObject <Object>]
    [-MemberType <Object>]
    [-Name <Object>]
    [-Static <Object>]
    [-View <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `Object` | No | Adds the intrinsic members and the compiler-generated **get_** and **set_** methods to the display. The following list describes the properties that are added when you use the **Force** parameter: ... |
| `-InputObject` | `Object` | No | Specifies the object whose members are retrieved.   Using the **InputObject** parameter isn't the same as piping an object to `Get-Member`. The differences are as follows:   - When you pipe a colle... |
| `-MemberType` | `Object` | No | Specifies the member type that this cmdlet gets. The default is `All`.   The acceptable values for this parameter are:   - `AliasProperty` - `CodeProperty` - `Property` - `NoteProperty` - `ScriptPr... |
| `-Name` | `Object` | No | Specifies the names of one or more properties or methods of the object. `Get-Member` gets only the specified properties and methods.   If you use the **Name** parameter with the **MemberType**, **V... |
| `-Static` | `Object` | No | Indicates that this cmdlet gets only the static properties and methods of the object. Static properties and methods are defined on the class of objects, not on any particular instance of the class.... |
| `-View` | `Object` | No | Specifies that this cmdlet gets only particular types properties and methods. Specify one or more of the values. The default is **Adapted**, **Extended**.   The acceptable values for this parameter... |

---

### Get-PSBreakpoint

Gets the breakpoints that are set in the current session.

The `Get-PSBreakpoint` cmdlet gets the breakpoints that are set in the current session. You can use the cmdlet parameters to get particular breakpoints.

**Returns**: `System.Management.Automation.CommandBreakpoint`

```
Get-PSBreakpoint
    -Command <Object>
    -Id <Object>
    [-Runspace <Object>]
    [-Script <Object>]
    -Type <Object>
    -Variable <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Command` | `Object` | Yes | Specifies an array of command breakpoints that are set on the specified command names. Enter the command names, such as the name of a cmdlet or function. |
| `-Id` | `Object` | Yes | Specifies the breakpoint IDs that this cmdlet gets. Enter the IDs in a comma-separated list. You can also pipe breakpoint IDs to `Get-PSBreakpoint`. |
| `-Runspace` | `Object` | No | Specifies the Id of a **Runspace** object so you can interact with breakpoints in the specified runspace.   This parameter was added in PowerShell 7.2. |
| `-Script` | `Object` | No | Specifies an array of scripts that contain the breakpoints. Enter the path (optional) and names of one or more script files. If you omit the path, the default location is the current directory. |
| `-Type` | `Object` | Yes | Specifies an array of breakpoint types that this cmdlet gets. Enter one or more types. The acceptable values for this parameter are:   - Line - Command - Variable   You can also pipe breakpoint typ... |
| `-Variable` | `Object` | Yes | Specifies an array of variable breakpoints that are set on the specified variable names. Enter the variable names without dollar signs. |

---

### Get-PSCallStack

Displays the current call stack.

The `Get-PSCallStack` cmdlet displays the current call stack.

**Returns**: `System.Management.Automation.CallStackFrame`

```
Get-PSCallStack
```

---

### Get-Random

Gets a random number, or selects objects randomly from a collection.

The `Get-Random` cmdlet gets a randomly selected number. If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.

**Returns**: `System.Int32`

```
Get-Random
    [-Count <Object>]
    -InputObject <Object>
    [-Maximum <Object>]
    [-Minimum <Object>]
    [-SetSeed <Object>]
    -Shuffle <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Count` | `Object` | No | Specifies the number of random objects to return. The default is 1.   When used with `InputObject` containing a collection:   - Each randomly selected item is returned only once. - If the value of ... |
| `-InputObject` | `Object` | Yes | Specifies a collection of objects. `Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count**. Enter the objects, a variable that contai... |
| `-Maximum` | `Object` | No | Specifies a maximum value for the random number. `Get-Random` returns a value that's less than the maximum (not equal). Enter an integer, a double-precision floating-point number, or an object that... |
| `-Minimum` | `Object` | No | Specifies a minimum value for the random number. Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("1... |
| `-SetSeed` | `Object` | No | Specifies a seed value for the random number generator. When you use **SetSeed**, the cmdlet generates pseudorandom numbers, which isn't cryptographically secure.   > [!CAUTION] > Setting the seed ... |
| `-Shuffle` | `Object` | Yes | Returns the entire collection in a randomized order. |

---

### Get-Runspace

Gets active runspaces within a PowerShell host process.

The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.

**Returns**: `System.Management.Automation.Runspaces.Runspace`

```
Get-Runspace
    -Id <Object>
    -InstanceId <Object>
    [-Name <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Id` | `Object` | Yes | Specifies the Id of a runspace |
| `-InstanceId` | `Object` | Yes | Specifies the instance ID GUID of a running job. |
| `-Name` | `Object` | No | Specifies the Name of a runspace |

---

### Get-RunspaceDebug

Shows runspace debugging options.

The `Get-RunspaceDebug` cmdlet shows runspace debugging options.

**Returns**: `None documented`

```
Get-RunspaceDebug
    [-AppDomainName <Object>]
    [-ProcessName <Object>]
    -Runspace <Object>
    -RunspaceId <Object>
    -RunspaceInstanceId <Object>
    [-RunspaceName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AppDomainName` | `Object` | No | The name of the application domain that hosts the PowerShell runspace. |
| `-ProcessName` | `Object` | No | The name of the process that hosts the PowerShell runspace. |
| `-Runspace` | `Object` | Yes | One or more **Runspace** objects to be disabled. |
| `-RunspaceId` | `Object` | Yes | One or more **Runspace** Id numbers to be disabled. |
| `-RunspaceInstanceId` | `Object` | Yes | One or more **Runspace** GUIDs to be disabled. |
| `-RunspaceName` | `Object` | No | One or more **Runspace** names to be disabled. |

---

### Get-SecureRandom

Gets a random number, or selects objects randomly from a collection.

The `Get-SecureRandom` cmdlet gets a randomly selected number. If you submit a collection of objects to `Get-SecureRandom`, it gets one or more randomly selected objects from the collection.

**Returns**: `System.Int32`

```
Get-SecureRandom
    [-Count <Object>]
    -InputObject <Object>
    [-Maximum <Object>]
    [-Minimum <Object>]
    -Shuffle <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Count` | `Object` | No | Specifies the number of random objects to return. The default is 1.   When used with `InputObject` containing a collection:   - Each randomly selected item is returned only once. - If the value of ... |
| `-InputObject` | `Object` | Yes | Specifies a collection of objects. `Get-SecureRandom` gets randomly selected objects in random order from the collection up to the number specified by **Count**. Enter the objects, a variable that ... |
| `-Maximum` | `Object` | No | Specifies a maximum value for the random number. `Get-SecureRandom` returns a value that's less than the maximum (not equal). Enter an integer, a double-precision floating-point number, or an objec... |
| `-Minimum` | `Object` | No | Specifies a minimum value for the random number. Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("1... |
| `-Shuffle` | `Object` | Yes | Returns the entire collection in a randomized order. |

---

### Get-TraceSource

Gets PowerShell components that are instrumented for tracing.

The `Get-TraceSource` cmdlet gets the trace sources for PowerShell components that are currently in use. You can use the data to determine which PowerShell components you can trace. When tracing, the component generates detailed messages about each step in its internal processing. Developers use the trace data to monitor data flow, program execution, and errors.

**Returns**: `System.Management.Automation.PSTraceSource`

```
Get-TraceSource
    [-Name <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `Object` | No | Specifies the trace sources to get. Wildcards are permitted. The parameter name **Name** is optional. |

---

### Get-TypeData

Gets the extended type data in the current session.

The `Get-TypeData` cmdlet gets the extended type data in the current session. This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.

**Returns**: `System.Management.Automation.Runspaces.TypeData`

```
Get-TypeData
    [-TypeName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-TypeName` | `Object` | No | Specifies type data as an array only for the types with the specified names. By default, `Get-TypeData` gets all types in the session.   Enter type names or a name patterns. Full names, or name pat... |

---

### Get-UICulture

Gets the current UI culture settings in the operating system.

The `Get-UICulture` cmdlet gets information about the current user interface (UI) culture settings for Windows. The UI culture determines which text strings are used for user interface elements, such as menus and messages.

**Returns**: `System.Globalization.CultureInfo`

```
Get-UICulture
```

---

### Get-Unique

Returns unique items from a sorted list.

The `Get-Unique` cmdlet compares each item in a sorted list to the next item, eliminates duplicates, and returns only one instance of each item. The list must be sorted for the cmdlet to work properly.

**Returns**: `System.Management.Automation.PSObject`

```
Get-Unique
    [-AsString <Object>]
    [-CaseInsensitive <Object>]
    [-InputObject <Object>]
    [-OnType <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsString` | `Object` | No | Indicates that this cmdlet uses the data as a string. Without this parameter, data is treated as an object, so when you submit a collection of objects of the same type to `Get-Unique`, such as a co... |
| `-CaseInsensitive` | `Object` | No | By default, `Get-Unique` is case-sensitive. When you use this parameter, the cmdlet uses case-insensitive comparisons.   This parameter was added in PowerShell 7.4. |
| `-InputObject` | `Object` | No | Specifies input for `Get-Unique`. Enter a variable that contains the objects or type a command or expression that gets the objects.   This cmdlet treats the input submitted using **InputObject** as... |
| `-OnType` | `Object` | No | Indicates that this cmdlet returns only one object of each type. |

---

### Get-Uptime

Get the **TimeSpan** since last boot.

This cmdlet returns the time elapsed since the last boot of the operating system.

**Returns**: `System.TimeSpan`

```
Get-Uptime
    [-Since <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Since` | `Object` | No | Cause the cmdlet to return a **DateTime** object representing the last time that the operating system was booted. |

---

### Get-Variable

Gets the variables in the current console.

The `Get-Variable` cmdlet gets the PowerShell variables in the current console. You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.

**Returns**: `System.Management.Automation.PSVariable`

```
Get-Variable
    [-Exclude <Object>]
    [-Include <Object>]
    [-Name <Object>]
    [-Scope <Object>]
    [-ValueOnly <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Exclude` | `Object` | No | Specifies an array of items that this cmdlet excludes from the operation. Wildcards are permitted. |
| `-Include` | `Object` | No | Specifies an array of items upon which the cmdlet will act, excluding all others. Wildcards are permitted. |
| `-Name` | `Object` | No | Specifies the name of the variable. Wildcards are permitted. You can also pipe a variable name to `Get-Variable`. |
| `-Scope` | `Object` | No | Specifies the variables in the scope.The acceptable values for this parameter are:   - **Global** - **Local** - **Script** - A number relative to the current scope (0 through the number of scopes, ... |
| `-ValueOnly` | `Object` | No | Indicates that this cmdlet gets only the value of the variable. |

---

### Get-Verb

Gets approved PowerShell verbs.

The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.

**Returns**: `System.Management.Automation.VerbInfo`

```
Get-Verb
    [-Group <Object>]
    [-Verb <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Group` | `Object` | No | Gets only the specified groups. Enter the name of a group. Wildcards aren't allowed.   This parameter was introduced in PowerShell 6.0. |
| `-Verb` | `Object` | No | Gets only the specified verbs. Enter the name of a verb or a name pattern. Wildcards are allowed. |

---

### Group-Object

Groups objects that contain the same value for specified properties.

The `Group-Object` cmdlet displays objects in groups based on the value of a specified property. `Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.

**Returns**: `Microsoft.PowerShell.Commands.GroupInfo`

```
Group-Object
    [-AsHashTable <Object>]
    [-AsString <Object>]
    [-CaseSensitive <Object>]
    [-Culture <Object>]
    [-InputObject <Object>]
    [-NoElement <Object>]
    [-Property <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsHashTable` | `Object` | No | Indicates that this cmdlet returns the group as a hash table. The keys of the hash table are the property values by which the objects are grouped. The values of the hash table are the objects that ... |
| `-AsString` | `Object` | No | Indicates that this cmdlet converts the hash table keys to strings. By default, the hash table keys are instances of the grouped object. This parameter is valid only when used with the **AsHashTabl... |
| `-CaseSensitive` | `Object` | No | Indicates that this cmdlet makes the grouping case-sensitive. Without this parameter, the property values of objects in a group might have different cases.   Beginning in PowerShell 7, to create ca... |
| `-Culture` | `Object` | No | Specifies the culture to use when comparing strings. |
| `-InputObject` | `Object` | No | Specifies the objects to group. Enter a variable that contains the objects, or type a command or expression that gets the objects.   When you use the **InputObject** parameter to submit a collectio... |
| `-NoElement` | `Object` | No | Indicates that this cmdlet omits the members of a group from the results. |
| `-Property` | `Object` | No | Specifies the properties for grouping. The objects are arranged into named groups based on the value of the specified properties. When no property is specified, objects are grouped by their value o... |

---

### Import-Alias

Imports an alias list from a file.

The `Import-Alias` cmdlet imports an alias list from a file.

**Returns**: `None`

```
Import-Alias
    [-Confirm <Object>]
    [-Force <Object>]
    -LiteralPath <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Force` | `Object` | No | Allows the cmdlet to import an alias that is already defined or is read only. You can use the following command to display information about the currently-defined aliases:   `Get-Alias | Select-Obj... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to a file that includes exported alias information. Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are in... |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Path` | `Object` | Yes | Specifies the path to a file that includes exported alias information. Wildcards are allowed but they must resolve to a single name. |
| `-Scope` | `Object` | No | Specifies the scope into which the aliases are imported. The acceptable values for this parameter are:   - Global - Local - Script - A number relative to the current scope (0 through the number of ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Import-Clixml

Imports a CLIXML file and creates corresponding objects in PowerShell.

The `Import-Clixml` cmdlet imports objects that have been serialized into a Common Language Infrastructure (CLI) XML file. A valuable use of `Import-Clixml` on Windows computers is to import credentials and secure strings that were exported as secure XML using `Export-Clixml`. [Example #2](#example-2-import-a-secure-credential-object) shows how to use `Import-Clixml` to import a secure credential object.

**Returns**: `System.Management.Automation.PSObject`

```
Import-Clixml
    [-First <Object>]
    [-IncludeTotalCount <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-Skip <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-First` | `Object` | No | Gets only the specified number of objects. Enter the number of objects to get. |
| `-IncludeTotalCount` | `Object` | No | Reports the total number of objects in the data set followed by the selected objects. If the cmdlet can't determine the total count, it displays **Unknown total count**. The integer has an **Accura... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to the XML files. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes esca... |
| `-Path` | `Object` | Yes | Specifies the path to the XML files. |
| `-Skip` | `Object` | No | Ignores the specified number of objects and then gets the remaining objects. Enter the number of objects to skip. |

---

### Import-Csv

Creates table-like custom objects from the items in a character-separated value (CSV) file.

The `Import-Csv` cmdlet creates table-like custom objects from the items in CSV files. Each column in the CSV file becomes a property of the custom object and the items in rows become the property values. `Import-Csv` works on any CSV file, including files that are generated by the `Export-Csv` cmdlet.

**Returns**: `System.Object`

```
Import-Csv
    [-Delimiter <Object>]
    [-Encoding <Object>]
    [-Header <Object>]
    -LiteralPath <Object>
    -Path <Object>
    -UseCulture <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Delimiter` | `Object` | No | Specifies the delimiter that separates the property values in the CSV file. The default is a comma (`,`).   Enter a character, such as a colon (`:`). To specify a semicolon (`;`), enclose it in sin... |
| `-Encoding` | `Object` | No | Specifies the encoding for the imported CSV file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit) c... |
| `-Header` | `Object` | No | Specifies an alternate column header row for the imported file. The column header determines the property names of the objects created by `Import-Csv`.   Enter column headers as a character-separat... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to the CSV file to import. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interpreted as wildcards. If the path incl... |
| `-Path` | `Object` | Yes | Specifies the path to the CSV file to import. You can also pipe a path to `Import-Csv`. |
| `-UseCulture` | `Object` | Yes | Uses the list separator for the current culture as the item delimiter. To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`. |

---

### Import-LocalizedData

Imports language-specific data into scripts and functions based on the UI culture that's selected
for the operating system.

The `Import-LocalizedData` cmdlet dynamically retrieves strings from a subdirectory whose name matches the UI language set for the current user of the operating system. It's designed to enable scripts to display user messages in the UI language selected by the current user.

**Returns**: `System.Collections.Hashtable`

```
Import-LocalizedData
    [-BaseDirectory <Object>]
    [-BindingVariable <Object>]
    [-FileName <Object>]
    [-SupportedCommand <Object>]
    [-UICulture <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BaseDirectory` | `Object` | No | Specifies the base directory where the `.psd1` files are located. The default is the directory where the script is located. `Import-LocalizedData` searches for the `.psd1` file for the script in a ... |
| `-BindingVariable` | `Object` | No | Specifies the variable into which the text strings are imported. Enter a variable name without a dollar sign (`$`).   In Windows PowerShell 2.0, this parameter is required. In Windows PowerShell 3.... |
| `-FileName` | `Object` | No | Specifies the name of the data file (`.psd1`) to be imported. Enter a filename. You can specify a filename that doesn't include its `.psd1` filename extension, or you can specify the filename inclu... |
| `-SupportedCommand` | `Object` | No | Specifies cmdlets and functions that generate only data.   Use this parameter to include cmdlets and functions that you have written or tested. For more information, see [about_Script_International... |
| `-UICulture` | `Object` | No | Specifies an alternate UI culture. The default is the value of the `$PSUICulture` automatic variable. Enter a UI culture in `<language>-<region>` format, such as `en-US`, `de-DE`, or `ar-SA`.   The... |

---

### Import-PSSession

Imports commands from another session into the current session.

The `Import-PSSession` cmdlet imports commands , such as cmdlets, functions, and aliases, from a PSSession on a local or remote computer into the current session. You can import any command that the `Get-Command` cmdlet can find in the PSSession.

**Returns**: `System.Management.Automation.PSModuleInfo`

```
Import-PSSession
    [-AllowClobber <Object>]
    [-ArgumentList <Object>]
    [-Certificate <Object>]
    [-CommandName <Object>]
    [-CommandType <Object>]
    [-DisableNameChecking <Object>]
    [-FormatTypeName <Object>]
    [-FullyQualifiedModule <Object>]
    [-Module <Object>]
    [-Prefix <Object>]
    -Session <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowClobber` | `Object` | No | Indicates that this cmdlet imports the specified commands, even if they have the same names as commands in the current session.   If you import a command with the same name as a command in the curr... |
| `-ArgumentList` | `Object` | No | Specifies an array of commands that results from using the specified arguments (parameter values).   For instance, to import the variant of the `Get-Item` command in the certificate (Cert:) drive i... |
| `-Certificate` | `Object` | No | Specifies the client certificate that is used to sign the format files (*.Format.ps1xml) or script module files (`.psm1`) in the temporary module that `Import-PSSession` creates.   Enter a variable... |
| `-CommandName` | `Object` | No | Specifies commands with the specified names or name patterns. Wildcards are permitted. Use **CommandName** or its alias, **Name**.   By default, `Import-PSSession` imports all commands from the ses... |
| `-CommandType` | `Object` | No | Specifies the type of command objects. The default value is Cmdlet. Use **CommandType** or its alias, **Type**. The acceptable values for this parameter are:   - `Alias`: The Windows PowerShell ali... |
| `-DisableNameChecking` | `Object` | No | Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.   By default, when a module t... |
| `-FormatTypeName` | `Object` | No | Specifies formatting instructions for the specified Microsoft .NET Framework types. Enter the type names. Wildcards are permitted.   The value of this parameter must be the name of a type that is r... |
| `-FullyQualifiedModule` | `Object` | No | The value can be a module name, a full module specification, or a path to a module file.   When the value is a path, the path can be fully qualified or relative. A relative path is resolved relativ... |
| `-Module` | `Object` | No | Specifies and array of commands in the Windows PowerShell snap-ins and modules. Enter the snap-in and module names. Wildcards are not permitted.   `Import-PSSession` cannot import providers from a ... |
| `-Prefix` | `Object` | No | Specifies a prefix to the nouns in the names of imported commands.   Use this parameter to avoid name conflicts that might occur when different commands in the session have the same name.   For ins... |
| `-Session` | `Object` | Yes | Specifies the **PSSession** from which the cmdlets are imported. Enter a variable that contains a session object or a command that gets a session object, such as a `New-PSSession` or `Get-PSSession... |

---

### Import-PowerShellDataFile

Imports values from a `.psd1` file without invoking its contents.

The `Import-PowerShellDataFile` cmdlet safely imports key-value pairs from hashtables defined in a `.psd1` file. The values could be imported using `Invoke-Expression` on the contents of the file. However, `Invoke-Expression` runs any code contained in the file. This could produce unwanted results or execute unsafe code. `Import-PowerShellDataFile` imports the data without invoking the code. By default there is a 500 key limit, but this can be bypassed with the **SkipLimitCheck** switch.

**Returns**: `System.Collections.Hashtable`

```
Import-PowerShellDataFile
    -LiteralPath <Object>
    -Path <Object>
    [-SkipLimitCheck <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-LiteralPath` | `Object` | Yes | The path to the file being imported. All characters in the path are treated as literal values. Wildcard characters aren't processed. |
| `-Path` | `Object` | Yes | The path to the file being imported. Wildcards are allowed but only the first matching file is imported. |
| `-SkipLimitCheck` | `Object` | No | By default `Import-PowerShellDataFile` imports only 500 keys from a `.psd1` file. Use **SkipLimitCheck** to import more than 500 keys. |

---

### Invoke-Expression

Runs commands or expressions on the local computer.

The `Invoke-Expression` cmdlet evaluates or runs a specified string as a command and returns the results of the expression or command. Without `Invoke-Expression`, a string submitted at the command line is returned (echoed) unchanged.

**Returns**: `None`

```
Invoke-Expression
    -Command <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Command` | `Object` | Yes | Specifies the command or expression to run. Type the command or expression or enter a variable that contains the command or expression. The **Command** parameter is required. |

---

### Invoke-RestMethod

Sends an HTTP or HTTPS request to a RESTful web service.

The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.

**Returns**: `System.Int64`

```
Invoke-RestMethod
    [-AllowInsecureRedirect <Object>]
    [-AllowUnencryptedAuthentication <Object>]
    [-Authentication <Object>]
    [-Body <Object>]
    [-Certificate <Object>]
    [-CertificateThumbprint <Object>]
    [-ConnectionTimeoutSeconds <Object>]
    [-ContentType <Object>]
    [-Credential <Object>]
    -CustomMethod <Object>
    [-DisableKeepAlive <Object>]
    [-FollowRelLink <Object>]
    [-Form <Object>]
    [-Headers <Object>]
    [-HttpVersion <Object>]
    [-InFile <Object>]
    [-MaximumFollowRelLink <Object>]
    [-MaximumRedirection <Object>]
    [-MaximumRetryCount <Object>]
    [-Method <Object>]
    -NoProxy <Object>
    [-OperationTimeoutSeconds <Object>]
    [-OutFile <Object>]
    [-PassThru <Object>]
    [-PreserveAuthorizationOnRedirect <Object>]
    [-PreserveHttpMethodOnRedirect <Object>]
    [-Proxy <Object>]
    [-ProxyCredential <Object>]
    [-ProxyUseDefaultCredentials <Object>]
    [-ResponseHeadersVariable <Object>]
    [-Resume <Object>]
    [-RetryIntervalSec <Object>]
    [-SessionVariable <Object>]
    [-SkipCertificateCheck <Object>]
    [-SkipHeaderValidation <Object>]
    [-SkipHttpErrorCheck <Object>]
    [-SslProtocol <Object>]
    [-StatusCodeVariable <Object>]
    [-Token <Object>]
    [-TransferEncoding <Object>]
    [-UnixSocket <Object>]
    -Uri <Object>
    [-UseBasicParsing <Object>]
    [-UseDefaultCredentials <Object>]
    [-UserAgent <Object>]
    [-WebSession <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowInsecureRedirect` | `Object` | No | Allows redirecting from HTTPS to HTTP. By default, any request that's redirected from HTTPS to HTTP results in an error and the request is aborted to prevent unintentionally communicating in plain ... |
| `-AllowUnencryptedAuthentication` | `Object` | No | Allows sending of credentials and secrets over unencrypted connections. By default, supplying **Credential** or any **Authentication** option with a **Uri** that doesn't begin with `https://` resul... |
| `-Authentication` | `Object` | No | Specifies the explicit authentication type to use for the request. The default is **None**. The **Authentication** parameter can't be used with the **UseDefaultCredentials** parameter.   Available ... |
| `-Body` | `Object` | No | Specifies the body of the request. The body is the content of the request that follows the headers. You can also pipe a body value to `Invoke-RestMethod`.   The **Body** parameter can be used to sp... |
| `-Certificate` | `Object` | No | Specifies the client certificate that's used for a secure web request. Enter a variable that contains a certificate or a command or expression that gets the certificate.   To find a certificate, us... |
| `-CertificateThumbprint` | `Object` | No | Specifies the digital public key certificate (X509) of a user account that has permission to send the request. Enter the certificate thumbprint of the certificate.   Certificates are used in client... |
| `-ConnectionTimeoutSeconds` | `Object` | No | Specifies how long the request can be pending before it times out. Enter a value in seconds. The default value, 0, specifies an indefinite time-out.   A Domain Name System (DNS) query can take up t... |
| `-ContentType` | `Object` | No | Specifies the content type of the web request.   If the value for **ContentType** contains the encoding format (as `charset`), the cmdlet uses that format to encode the body of the web request. If ... |
| `-Credential` | `Object` | No | Specifies a user account that has permission to send the request. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object ... |
| `-CustomMethod` | `Object` | Yes | Specifies custom method used for the web request. This can be used with the Request Method required by the endpoint isn't an available option on the **Method**. **Method** and **CustomMethod** can'... |
| `-DisableKeepAlive` | `Object` | No | Sets the **KeepAlive** value in the HTTP header to False. By default, **KeepAlive** is True. **KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests. |
| `-FollowRelLink` | `Object` | No | Indicates the cmdlet should follow relation links.   Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#section-5). Instead of parsing the header... |
| `-Form` | `Object` | No | Converts a dictionary to a `multipart/form-data` submission. **Form** may not be used with **Body**. The **ContentType** is ignored.   The keys of the dictionary are used as the form field names. B... |
| `-Headers` | `Object` | No | Specifies the headers of the web request. Enter a hash table or dictionary.   Content related headers, such as `Content-Type` are overridden when a `MultipartFormDataContent` object is supplied for... |
| `-HttpVersion` | `Object` | No | Specifies the HTTP version used for the request. The default is `1.1`.   Valid values are:   - 1.0 - 1.1 - 2.0 - 3.0 |
| `-InFile` | `Object` | No | Gets the content of the web request body from a file. Enter a path and filename. If you omit the path, the default is the current location.   You also need to set the content type of the request. F... |
| `-MaximumFollowRelLink` | `Object` | No | Specifies how many times to follow relation links if **FollowRelLink** is used. A smaller value may be needed if the REST api throttles due to too many requests. The default value is `[int32]::MaxV... |
| `-MaximumRedirection` | `Object` | No | Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails. The default value is 5. A value of 0 (zero) prevents all re... |
| `-MaximumRetryCount` | `Object` | No | Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received. Also see **RetryIntervalSec** parameter for specifying the interval b... |
| `-Method` | `Object` | No | Specifies the method used for the web request. The acceptable values for this parameter are:   - `Default` - `Delete` - `Get` - `Head` - `Merge` - `Options` - `Patch` - `Post` - `Put` - `Trace`   T... |
| `-NoProxy` | `Object` | Yes | Indicates that the cmdlet won't use a proxy to reach the destination. Use this to bypass the proxy configured in your internet settings or specified in the environment.   This parameter was introdu... |
| `-OperationTimeoutSeconds` | `Object` | No | This timeout applies to data reads within a stream, not to the stream time as a whole. The default value, 0, specifies an indefinite timeout.   Setting the value to 30 seconds means that any delay ... |
| `-OutFile` | `Object` | No | By default, `Invoke-RestMethod` returns the results to the pipeline. When you use the **OutFile** parameter, the results are saved to the specified file and not returned to the pipeline. Enter a pa... |
| `-PassThru` | `Object` | No | This parameter is valid only when the **OutFile** parameter is also used in the command. The intent is to have the results written to the file and to the pipeline. |
| `-PreserveAuthorizationOnRedirect` | `Object` | No | Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.   By default, the cmdlet strips the `Authorization` header before redirecting. Specifying this pa... |
| `-PreserveHttpMethodOnRedirect` | `Object` | No | Indicates the cmdlet should preserve the method of the request across redirections.   By default, the cmdlet changes the method to `GET` when redirected. Specifying this parameter disables this log... |
| `-Proxy` | `Object` | No | Uses a proxy server for the request, rather than connecting directly to the internet resource. Enter the Uniform Resource Identifier (URI) of a network proxy server.   This feature was added in Pow... |
| `-ProxyCredential` | `Object` | No | Specifies a user account that has permission to use the proxy server that's specified by the **Proxy** parameter. The default is the current user.   Type a user name, such as "User01" or "Domain01\... |
| `-ProxyUseDefaultCredentials` | `Object` | No | Uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.   This parameter is valid only when the **Proxy** parameter is also used in the com... |
| `-ResponseHeadersVariable` | `Object` | No | Creates a variable containing a Response Headers Dictionary. Enter a variable name without the dollar sign (`$`) symbol. The keys of the dictionary contain the field names and values of the Respons... |
| `-Resume` | `Object` | No | Performs a best effort attempt to resume downloading a partial file. The **Resume** parameter requires the **OutFile** parameter.   **Resume** only operates on the size of the local file and remote... |
| `-RetryIntervalSec` | `Object` | No | Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received. The value must be between `1` and `[int]::MaxValue`. When the failur... |
| `-SessionVariable` | `Object` | No | Creates a variable containing the web request session. Enter a variable name without the dollar sign (`$`) symbol.   When you specify a session variable, `Invoke-RestMethod` creates a web request s... |
| `-SkipCertificateCheck` | `Object` | No | Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.   > [!WARNING] > Using this parameter isn't secure and isn't recommende... |
| `-SkipHeaderValidation` | `Object` | No | Indicates the cmdlet should add headers to the request without validation.   This switch should be used for sites that require header values that don't conform to standards. Specifying this switch ... |
| `-SkipHttpErrorCheck` | `Object` | No | This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses. The error responses are written to the pipeline just as if they were successful.   This parameter w... |
| `-SslProtocol` | `Object` | No | Sets the SSL/TLS protocols that are permissible for the web request. By default all, SSL/TLS protocols supported by the system are allowed. **SslProtocol** allows for limiting to specific protocols... |
| `-StatusCodeVariable` | `Object` | No | Creates a variable containing a HTTP status code result of the request. Enter a variable name without the dollar sign (`$`) symbol.   The parameter can identify success messages or failure messages... |
| `-Token` | `Object` | No | The OAuth or Bearer token to include in the request. **Token** is required by certain **Authentication** options. It can't be used independently.   **Token** takes a `SecureString` that contains th... |
| `-TransferEncoding` | `Object` | No | Specifies a value for the transfer-encoding HTTP response header. The acceptable values for this parameter are:   - Chunked - Compress - Deflate - GZip - Identity |
| `-UnixSocket` | `Object` | No | Specifies the name of the Unix socket to connect to. This parameter is supported on Unix-based systems and Windows version 1803 and later. For more information about Windows support of Unix sockets... |
| `-Uri` | `Object` | Yes | Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent. This parameter supports HTTP, HTTPS, FTP, and FILE values.   This parameter is required. T... |
| `-UseBasicParsing` | `Object` | No | This parameter has been deprecated. Beginning with PowerShell 6.0.0, all Web requests use basic parsing only. This parameter is included for backwards compatibility only. When used, it has no effec... |
| `-UseDefaultCredentials` | `Object` | No | Indicates that the cmdlet uses the credentials of the current user to send the web request. This can't be used with **Authentication** or **Credential** and may not be supported on all platforms. |
| `-UserAgent` | `Object` | No | Specifies a user agent string for the web request.   The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variation... |
| `-WebSession` | `Object` | No | Specifies a web request session. Enter the variable name, including the dollar sign (`$`).   To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Crede... |

---

### Invoke-WebRequest

Gets content from a web page on the internet.

The `Invoke-WebRequest` cmdlet sends HTTP and HTTPS requests to a web page or web service. It parses the response and returns collections of links, images, and other significant HTML elements.

**Returns**: `Microsoft.PowerShell.Commands.BasicHtmlWebResponseObject`

```
Invoke-WebRequest
    [-AllowInsecureRedirect <Object>]
    [-AllowUnencryptedAuthentication <Object>]
    [-Authentication <Object>]
    [-Body <Object>]
    [-Certificate <Object>]
    [-CertificateThumbprint <Object>]
    [-ConnectionTimeoutSeconds <Object>]
    [-ContentType <Object>]
    [-Credential <Object>]
    -CustomMethod <Object>
    [-DisableKeepAlive <Object>]
    [-Form <Object>]
    [-Headers <Object>]
    [-HttpVersion <Object>]
    [-InFile <Object>]
    [-MaximumRedirection <Object>]
    [-MaximumRetryCount <Object>]
    [-Method <Object>]
    -NoProxy <Object>
    [-OperationTimeoutSeconds <Object>]
    [-OutFile <Object>]
    [-PassThru <Object>]
    [-PreserveAuthorizationOnRedirect <Object>]
    [-PreserveHttpMethodOnRedirect <Object>]
    [-Proxy <Object>]
    [-ProxyCredential <Object>]
    [-ProxyUseDefaultCredentials <Object>]
    [-Resume <Object>]
    [-RetryIntervalSec <Object>]
    [-SessionVariable <Object>]
    [-SkipCertificateCheck <Object>]
    [-SkipHeaderValidation <Object>]
    [-SkipHttpErrorCheck <Object>]
    [-SslProtocol <Object>]
    [-Token <Object>]
    [-TransferEncoding <Object>]
    [-UnixSocket <Object>]
    -Uri <Object>
    [-UseBasicParsing <Object>]
    [-UseDefaultCredentials <Object>]
    [-UserAgent <Object>]
    [-WebSession <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllowInsecureRedirect` | `Object` | No | Allows redirecting from HTTPS to HTTP. By default, any request that's redirected from HTTPS to HTTP results in an error and the request is aborted to prevent unintentionally communicating in plain ... |
| `-AllowUnencryptedAuthentication` | `Object` | No | Allows sending of credentials and secrets over unencrypted connections. By default, supplying **Credential** or any **Authentication** option with a **Uri** that doesn't begin with `https://` resul... |
| `-Authentication` | `Object` | No | Specifies the explicit authentication type to use for the request. The default is **None**. The **Authentication** parameter can't be used with the **UseDefaultCredentials** parameter.   Available ... |
| `-Body` | `Object` | No | Specifies the body of the request. The body is the content of the request that follows the headers. You can also pipe a body value to `Invoke-WebRequest`.   The **Body** parameter can be used to sp... |
| `-Certificate` | `Object` | No | Specifies the client certificate that's used for a secure web request. Enter a variable that contains a certificate or a command or expression that gets the certificate.   To find a certificate, us... |
| `-CertificateThumbprint` | `Object` | No | Specifies the digital public key certificate (X509) of a user account that has permission to send the request. Enter the certificate thumbprint of the certificate.   Certificates are used in client... |
| `-ConnectionTimeoutSeconds` | `Object` | No | Specifies how long the request can be pending before it times out. Enter a value in seconds. The default value, 0, specifies an indefinite time-out.   A Domain Name System (DNS) query can take up t... |
| `-ContentType` | `Object` | No | Specifies the content type of the web request.   If the value for **ContentType** contains the encoding format (as `charset`), the cmdlet uses that format to encode the body of the web request. If ... |
| `-Credential` | `Object` | No | Specifies a user account that has permission to send the request. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object ... |
| `-CustomMethod` | `Object` | Yes | Specifies a custom method used for the web request. This can be used if the Request Method required by the endpoint isn't an available option on the **Method**. **Method** and **CustomMethod** can'... |
| `-DisableKeepAlive` | `Object` | No | Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to **False**. By default, **KeepAlive** is **True**. **KeepAlive** establishes a persistent connection to the server to fac... |
| `-Form` | `Object` | No | Converts a dictionary to a `multipart/form-data` submission. **Form** may not be used with **Body**. If **ContentType** is used, it's ignored.   The keys of the dictionary are used as the form fiel... |
| `-Headers` | `Object` | No | Specifies the headers of the web request. Enter a hash table or dictionary.   Content related headers, such as `Content-Type` are overridden when a **MultipartFormDataContent** object is supplied f... |
| `-HttpVersion` | `Object` | No | Specifies the HTTP version used for the request. The default is `1.1`.   Valid values are:   - 1.0 - 1.1 - 2.0 - 3.0 |
| `-InFile` | `Object` | No | Gets the content of the web request body from a file. Enter a path and filename. If you omit the path, the default is the current location.   You also need to set the content type of the request. F... |
| `-MaximumRedirection` | `Object` | No | Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails. The default value is 5. A value of 0 (zero) prevents all re... |
| `-MaximumRetryCount` | `Object` | No | Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received. Also see **RetryIntervalSec** parameter for specifying the interval b... |
| `-Method` | `Object` | No | Specifies the method used for the web request. The acceptable values for this parameter are:   - `Default` - `Delete` - `Get` - `Head` - `Merge` - `Options` - `Patch` - `Post` - `Put` - `Trace`   T... |
| `-NoProxy` | `Object` | Yes | Indicates that the cmdlet shouldn't use a proxy to reach the destination. When you need to bypass the proxy configured in the environment, use this switch. This feature was added in PowerShell 6.0.0. |
| `-OperationTimeoutSeconds` | `Object` | No | This timeout applies to data reads within a stream, not to the stream time as a whole. The default value, 0, specifies an indefinite timeout.   Setting the value to 30 seconds means that any delay ... |
| `-OutFile` | `Object` | No | By default, `Invoke-WebRequest` returns the results to the pipeline. When you use the **OutFile** parameter, the results are saved to the specified file and not returned to the pipeline. Enter a pa... |
| `-PassThru` | `Object` | No | Indicates that the cmdlet returns the results, in addition to writing them to a file. This parameter is valid only when the **OutFile** parameter is also used in the command. |
| `-PreserveAuthorizationOnRedirect` | `Object` | No | Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.   By default, the cmdlet strips the `Authorization` header before redirecting. Specifying this pa... |
| `-PreserveHttpMethodOnRedirect` | `Object` | No | Indicates the cmdlet should preserve the method of the request across redirections.   By default, the cmdlet changes the method to `GET` when redirected. Specifying this parameter disables this log... |
| `-Proxy` | `Object` | No | Specifies a proxy server for the request, rather than connecting directly to the internet resource. Enter the URI of a network proxy server. |
| `-ProxyCredential` | `Object` | No | Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter. The default is the current user.   Type a user name, such as `User01` or `Domain01\User01`... |
| `-ProxyUseDefaultCredentials` | `Object` | No | Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.   This parameter is valid only when the **Proxy** paramet... |
| `-Resume` | `Object` | No | Performs a best effort attempt to resume downloading a partial file. **Resume** requires **OutFile**.   **Resume** only operates on the size of the local file and remote file and performs no other ... |
| `-RetryIntervalSec` | `Object` | No | Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received. Also see **MaximumRetryCount** parameter for specifying number of re... |
| `-SessionVariable` | `Object` | No | Specifies a variable for which this cmdlet creates a web request session and saves it in the value. Enter a variable name without the dollar sign (`$`) symbol.   When you specify a session variable... |
| `-SkipCertificateCheck` | `Object` | No | Skips certificate validation checks. This includes all validations such as expiration, revocation, trusted root authority, etc.   > [!WARNING] > Using this parameter isn't secure and isn't recommen... |
| `-SkipHeaderValidation` | `Object` | No | Indicates the cmdlet should add headers to the request without validation.   This switch should be used for sites that require header values that don't conform to standards. Specifying this switch ... |
| `-SkipHttpErrorCheck` | `Object` | No | This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses. The error responses are written to the pipeline just as if they were successful.   This parameter w... |
| `-SslProtocol` | `Object` | No | Sets the SSL/TLS protocols that are permissible for the web request. By default all, SSL/TLS protocols supported by the system are allowed. **SslProtocol** allows for limiting to specific protocols... |
| `-Token` | `Object` | No | The OAuth or Bearer token to include in the request. **Token** is required by certain **Authentication** options. It can't be used independently.   **Token** takes a `SecureString` containing the t... |
| `-TransferEncoding` | `Object` | No | Specifies a value for the transfer-encoding HTTP response header. The acceptable values for this parameter are:   - `Chunked` - `Compress` - `Deflate` - `GZip` - `Identity` |
| `-UnixSocket` | `Object` | No | Specifies the name of the Unix socket to connect to. This parameter is supported on Unix-based systems and Windows version 1803 and later. For more information about Windows support of Unix sockets... |
| `-Uri` | `Object` | Yes | Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent. Enter a URI. This parameter supports HTTP or HTTPS only.   This parameter is required. The... |
| `-UseBasicParsing` | `Object` | No | This parameter has been deprecated. Beginning with PowerShell 6.0.0, all Web requests use basic parsing only. This parameter is included for backwards compatibility only and any use of it has no ef... |
| `-UseDefaultCredentials` | `Object` | No | Indicates that the cmdlet uses the credentials of the current user to send the web request. This can't be used with **Authentication** or **Credential** and may not be supported on all platforms. |
| `-UserAgent` | `Object` | No | Specifies a user agent string for the web request.   The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variation... |
| `-WebSession` | `Object` | No | Specifies a web request session. Enter the variable name, including the dollar sign (`$`).   To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Crede... |

---

### Join-String

Combines objects from the pipeline into a single string.

The `Join-String` cmdlet joins, or combines, text from pipeline objects into a single string.

**Returns**: `System.String`

```
Join-String
    [-DoubleQuote <Object>]
    [-FormatString <Object>]
    [-InputObject <Object>]
    [-OutputPrefix <Object>]
    [-OutputSuffix <Object>]
    [-Property <Object>]
    [-Separator <Object>]
    [-SingleQuote <Object>]
    [-UseCulture <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-DoubleQuote` | `Object` | No | Wraps the string value of each pipeline object in double-quotes. |
| `-FormatString` | `Object` | No | Specifies a format string that specifies how each pipeline object should be formatted before joining them. Use the `{0}` placeholder to represent the current object. If you need to keep the curly b... |
| `-InputObject` | `Object` | No | Specifies the text to be joined. Enter a variable that contains the text, or type a command or expression that gets the objects to join into strings. |
| `-OutputPrefix` | `Object` | No | Text that's inserted before the output string. The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``). |
| `-OutputSuffix` | `Object` | No | Text that's appended to the output string. The string can contain special characters such as carriage return (`` `r ``), newline (`` `n ``), and tab (`` `t ``). |
| `-Property` | `Object` | No | The name of a property, or a property expression, to be converted to text. |
| `-Separator` | `Object` | No | Text or characters such as a comma or semicolon that's inserted between the text for each pipeline object.   By default, the pipeline objects are joined without a separator. If the [Output Field Se... |
| `-SingleQuote` | `Object` | No | Wraps the string value of each pipeline object in single quotes. |
| `-UseCulture` | `Object` | No | Uses the list separator for the current culture as the item delimiter. To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`. |

---

### Measure-Command

Measures the time it takes to run scriptblocks and cmdlets.

The `Measure-Command` cmdlet runs a scriptblock or cmdlet internally, times the execution of the operation, and returns the execution time.

**Returns**: `System.TimeSpan`

```
Measure-Command
    -Expression <Object>
    [-InputObject <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Expression` | `Object` | Yes | Specifies the expression that is being timed. Enclose the expression in braces (`{}`). |
| `-InputObject` | `Object` | No | Objects bound to the **InputObject** parameter are optional input for the scriptblock passed to the **Expression** parameter. Inside the scriptblock, `$_` can be used to reference the current objec... |

---

### Measure-Object

Calculates the numeric properties of objects, and the characters, words, and lines in string
objects, such as files of text.

The `Measure-Object` cmdlet calculates the property values of certain types of object. `Measure-Object` performs three types of measurements, depending on the parameters in the command.

**Returns**: `Microsoft.PowerShell.Commands.GenericMeasureInfo`

```
Measure-Object
    [-AllStats <Object>]
    [-Average <Object>]
    [-Character <Object>]
    [-IgnoreWhiteSpace <Object>]
    [-InputObject <Object>]
    [-Line <Object>]
    [-Maximum <Object>]
    [-Minimum <Object>]
    [-Property <Object>]
    [-StandardDeviation <Object>]
    [-Sum <Object>]
    [-Word <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllStats` | `Object` | No | Indicates that the cmdlet displays all the statistics of the specified properties. |
| `-Average` | `Object` | No | Indicates that the cmdlet displays the average value of the specified properties. |
| `-Character` | `Object` | No | Indicates that the cmdlet counts the number of characters in the input objects.   > [!NOTE] > The **Word**, **Char** and **Line** switches count _inside_ each input object, as well as _across_ > in... |
| `-IgnoreWhiteSpace` | `Object` | No | Indicates that the cmdlet ignores white space in character counts. By default, white space is not ignored. |
| `-InputObject` | `Object` | No | Specifies the objects to be measured. Enter a variable that contains the objects, or type a command or expression that gets the objects.   When you use the **InputObject** parameter with `Measure-O... |
| `-Line` | `Object` | No | Indicates that the cmdlet counts the number of lines in the input objects.   > [!NOTE] > The **Word**, **Char** and **Line** switches count _inside_ each input object, as well as _across_ > input o... |
| `-Maximum` | `Object` | No | Indicates that the cmdlet displays the maximum value of the specified properties. |
| `-Minimum` | `Object` | No | Indicates that the cmdlet displays the minimum value of the specified properties. |
| `-Property` | `Object` | No | Specifies one or more properties to measure. If you do not specify any other measures, `Measure-Object` counts the objects that have the properties you specify.   The value of the **Property** para... |
| `-StandardDeviation` | `Object` | No | Indicates that the cmdlet displays the standard deviation of the values of the specified properties. |
| `-Sum` | `Object` | No | Indicates that the cmdlet displays the sum of the values of the specified properties. |
| `-Word` | `Object` | No | Indicates that the cmdlet counts the number of words in the input objects.   > [!NOTE] > The **Word**, **Char** and **Line** switches count _inside_ each input object, as well as _across_ > input o... |

---

### New-Alias

Creates a new alias.

The `New-Alias` cmdlet creates a new alias in the current PowerShell session. Aliases created by using `New-Alias` are not saved after you exit the session or close PowerShell. You can use the `Export-Alias` cmdlet to save your alias information to a file. You can later use `Import-Alias` to retrieve that saved alias information.

**Returns**: `None`

```
New-Alias
    [-Confirm <Object>]
    [-Description <Object>]
    [-Force <Object>]
    -Name <Object>
    [-Option <Object>]
    [-PassThru <Object>]
    [-Scope <Object>]
    -Value <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Description` | `Object` | No | Specifies a description of the alias. You can type any string. If the description includes spaces, enclose it in quotation marks. |
| `-Force` | `Object` | No | Indicates that the cmdlet acts like `Set-Alias` if the alias named already exists. |
| `-Name` | `Object` | Yes | Specifies the new alias. You can use any alphanumeric characters in an alias, but the first character cannot be a number. |
| `-Option` | `Object` | No | Specifies the value of the **Options** property of the alias. Valid values are:   - `None`: The alias has no constraints (default value) - `ReadOnly`: The alias can be deleted but cannot be changed... |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Scope` | `Object` | No | Specifies the scope of the new alias. The acceptable values for this parameter are:   - `Global` - `Local` - `Script` - A number relative to the current scope (0 through the number of scopes, where... |
| `-Value` | `Object` | Yes | Specifies the name of the cmdlet or command element that is being aliased. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### New-Event

Creates a new event.

The `New-Event` cmdlet creates a new custom event.

**Returns**: `System.Management.Automation.PSEventArgs`

```
New-Event
    [-EventArguments <Object>]
    [-MessageData <Object>]
    [-Sender <Object>]
    -SourceIdentifier <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-EventArguments` | `Object` | No | Specifies an object that contains options for the event. |
| `-MessageData` | `Object` | No | Specifies additional data associated with the event. The value of this parameter appears in the **MessageData** property of the event object. |
| `-Sender` | `Object` | No | Specifies the object that raises the event. The default is the PowerShell engine. |
| `-SourceIdentifier` | `Object` | Yes | Specifies a name for the new event. This parameter is required, and it must be unique in the session.   The value of this parameter appears in the **SourceIdentifier** property of the events. |

---

### New-Guid

Creates a GUID.

The `New-Guid` cmdlet creates a random globally unique identifier (GUID). If you need a unique ID in a script, you can create a GUID, as needed.

**Returns**: `System.Guid`

```
New-Guid
    [-Empty <Object>]
    [-InputObject <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Empty` | `Object` | No | Indicates that this cmdlet creates an empty GUID. An empty GUID has all zeros in its string. |
| `-InputObject` | `Object` | No | This parameter accepts a string representing a GUID and converts it to a GUID object. |

---

### New-Object

Creates an instance of a Microsoft .NET Framework or COM object.

The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.

**Returns**: `System.Object`

```
New-Object
    [-ArgumentList <Object>]
    -ComObject <Object>
    [-Property <Object>]
    [-Strict <Object>]
    -TypeName <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object` | No | Specifies an array of arguments to pass to the constructor of the .NET Framework class. If the constructor takes a single parameter that is an array, you must wrap that parameter inside another arr... |
| `-ComObject` | `Object` | Yes | Specifies the programmatic identifier (ProgID) of the COM object. |
| `-Property` | `Object` | No | Sets property values and invokes methods of the new object.   Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments. `Ne... |
| `-Strict` | `Object` | No | Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly. This feature distinguishes actual COM objects from .NET Framework ... |
| `-TypeName` | `Object` | Yes | Specifies the fully qualified name of the .NET Framework class. You cannot specify both the **TypeName** parameter and the **ComObject** parameter. |

---

### New-TemporaryFile

Creates a temporary file.

This cmdlet creates temporary files that you can use in scripts.

**Returns**: `System.IO.FileInfo`

```
New-TemporaryFile
    [-Confirm <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### New-TimeSpan

Creates a TimeSpan object.

The `New-TimeSpan` cmdlet creates a **TimeSpan** object that represents a time interval. You can use a **TimeSpan** object to add or subtract time from **DateTime** objects.

**Returns**: `System.TimeSpan`

```
New-TimeSpan
    [-Days <Object>]
    [-End <Object>]
    [-Hours <Object>]
    [-Milliseconds <Object>]
    [-Minutes <Object>]
    [-Seconds <Object>]
    [-Start <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Days` | `Object` | No | Specifies the days in the time span. The default value is 0. |
| `-End` | `Object` | No | Specifies the end of a time span. The default value is the current date and time. |
| `-Hours` | `Object` | No | Specifies the hours in the time span. The default value is 0. |
| `-Milliseconds` | `Object` | No | Specifies the length of the time span in milliseconds. The default value is 0. |
| `-Minutes` | `Object` | No | Specifies the minutes in the time span. The default value is 0. |
| `-Seconds` | `Object` | No | Specifies the length of the time span in seconds. The default value is 0. |
| `-Start` | `Object` | No | Specifies the start of a time span. Enter a string that represents the date and time, such as "3/15/09" or a **DateTime** object, such as one from a `Get-Date` command. The default value is the cur... |

---

### New-Variable

Creates a new variable.

The `New-Variable` cmdlet creates a new variable in PowerShell. You can assign a value to the variable while creating it or assign or change the value after it is created.

**Returns**: `None`

```
New-Variable
    [-Confirm <Object>]
    [-Description <Object>]
    [-Force <Object>]
    -Name <Object>
    [-Option <Object>]
    [-PassThru <Object>]
    [-Scope <Object>]
    [-Value <Object>]
    [-Visibility <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Description` | `Object` | No | Specifies a description of the variable. |
| `-Force` | `Object` | No | Indicates that the cmdlet creates a variable with the same name as an existing read-only variable.   By default, you can overwrite a variable unless the variable has an option value of `ReadOnly` o... |
| `-Name` | `Object` | Yes | Specifies a name for the new variable. |
| `-Option` | `Object` | No | Specifies the value of the **Options** property of the variable. The acceptable values for this parameter are:   - `None` - Sets no options. `None` is the default. - `ReadOnly` - Can be deleted. Ca... |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-Scope` | `Object` | No | Specifies the scope of the new variable. The acceptable values for this parameter are:   - `Global` - Variables created in the global scope are accessible everywhere in a PowerShell   process. - `L... |
| `-Value` | `Object` | No | Specifies the initial value of the variable. |
| `-Visibility` | `Object` | No | Determines whether the variable is visible outside of the session in which it was created. This parameter is designed for use in scripts and commands that will be delivered to other users. The acce... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Out-File

Sends output to a file.

The `Out-File` cmdlet sends output to a file. It implicitly uses PowerShell's formatting system to write to the file. The file receives the same display representation as the terminal. This means that the output may not be ideal for programmatic processing unless all input objects are strings.

**Returns**: `None`

```
Out-File
    [-Append <Object>]
    [-Confirm <Object>]
    [-Encoding <Object>]
    -FilePath <Object>
    [-Force <Object>]
    [-InputObject <Object>]
    -LiteralPath <Object>
    [-NoClobber <Object>]
    [-NoNewline <Object>]
    [-WhatIf <Object>]
    [-Width <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Append` | `Object` | No | Adds the output to the end of an existing file. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-FilePath` | `Object` | Yes | Specifies the path to the output file. |
| `-Force` | `Object` | No | Overrides the read-only attribute and overwrites an existing read-only file. The **Force** parameter doesn't override security restrictions. |
| `-InputObject` | `Object` | No | Specifies the objects to be written to the file. Enter a variable that contains the objects or type a command or expression that gets the objects. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to the output file. The **LiteralPath** parameter is used exactly as it's typed. Wildcard characters aren't accepted. If the path includes escape characters, enclose it in single... |
| `-NoClobber` | `Object` | No | **NoClobber** prevents an existing file from being overwritten and displays a message that the file already exists. By default, if a file exists in the specified path, `Out-File` overwrites the fil... |
| `-NoNewline` | `Object` | No | Specifies that the content written to the file doesn't end with a newline character. The string representations of the input objects are concatenated to form the output. No spaces or newlines are i... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |
| `-Width` | `Object` | No | Specifies the maximum number of characters in each line of output. Any additional characters are truncated, not wrapped. If this parameter isn't used, the width is determined by the characteristics... |

---

### Out-String

Outputs input objects as a string.

The `Out-String` cmdlet converts input objects into strings. By default, `Out-String` accumulates the strings and returns them as a single string, but you can use the **Stream** parameter to direct `Out-String` to return one line at a time or create an array of strings. This cmdlet lets you search and manipulate string output as you would in traditional shells when object manipulation is less convenient.

**Returns**: `System.String`

```
Out-String
    [-InputObject <Object>]
    [-NoNewline <Object>]
    [-Stream <Object>]
    [-Width <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | No | Specifies the objects to be written to a string. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-NoNewline` | `Object` | No | Removes all newlines from output generated by the PowerShell formatter. Newlines that are part of the string objects are preserved.   This parameter was introduced in PowerShell 6.0. |
| `-Stream` | `Object` | No | By default, `Out-String` outputs a single string formatted as you would see it in the console including any blank headers or trailing newlines. The **Stream** parameter enables `Out-String` to outp... |
| `-Width` | `Object` | No | Specifies the number of characters in each line of output. Any additional characters are wrapped to the next line or truncated depending on the formatter cmdlet used. The **Width** parameter applie... |

---

### Read-Host

Reads a line of input from the console.

The `Read-Host` cmdlet reads a line of input from the console (stdin). You can use it to prompt a user for input. Because you can save the input as a secure string, you can use this cmdlet to prompt users for secure data, such as passwords.

**Returns**: `System.String`

```
Read-Host
    [-AsSecureString <Object>]
    [-MaskInput <Object>]
    [-Prompt <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsSecureString` | `Object` | No | Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input. When you use this parameter, the output of the `Read-Host` cmdlet is a **SecureString** o... |
| `-MaskInput` | `Object` | No | Indicates that the cmdlet displays asterisks (`*`) in place of the characters that the user types as input. When you use this parameter, the output of the `Read-Host` cmdlet is a **String** object.... |
| `-Prompt` | `Object` | No | Specifies the text of the prompt. Type a string. If the string includes spaces, enclose it in quotation marks. PowerShell appends a colon (`:`) to the text that you enter. |

---

### Register-EngineEvent

Subscribes to events that are generated by the PowerShell engine and by the `New-Event` cmdlet.

The `Register-EngineEvent` cmdlet subscribes to events that are generated by the PowerShell engine and the `New-Event` cmdlet. Use the **SourceIdentifier** parameter to specify the event.

**Returns**: `None`

```
Register-EngineEvent
    [-Action <Object>]
    [-Forward <Object>]
    [-MaxTriggerCount <Object>]
    [-MessageData <Object>]
    -SourceIdentifier <Object>
    [-SupportEvent <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Action` | `Object` | No | Specifies commands to handle the events. The commands in the **Action** run when an event is raised, instead of sending the event to the event queue. Enclose the commands in braces (`{}`) to create... |
| `-Forward` | `Object` | No | Indicates that the cmdlet sends events for this subscription to the session on the local computer. Use this parameter when you are registering for events on a remote computer or in a remote session. |
| `-MaxTriggerCount` | `Object` | No | Specifies the maximum number of times that the action is executed for the event subscription. |
| `-MessageData` | `Object` | No | This parameter is part of the base class for all Event cmdlets. The `Register-EngineEvent` doesn't use this parameter. Any data passed to this parameter is ignored. |
| `-SourceIdentifier` | `Object` | Yes | Specifies the source identifier of the event to which you are subscribing. The source identifier must be unique in the current session. This parameter is required.   The value of this parameter app... |
| `-SupportEvent` | `Object` | No | Indicates that the cmdlet hides the event subscription. Add this parameter when the current subscription is part of a more complex event registration mechanism and it should not be discovered indep... |

---

### Register-ObjectEvent

Subscribes to the events that are generated by a Microsoft .NET Framework object.

The `Register-ObjectEvent` cmdlet subscribes to events that are generated by .NET objects on the local computer or on a remote computer.

**Returns**: `None`

```
Register-ObjectEvent
    [-Action <Object>]
    -EventName <Object>
    [-Forward <Object>]
    -InputObject <Object>
    [-MaxTriggerCount <Object>]
    [-MessageData <Object>]
    [-SourceIdentifier <Object>]
    [-SupportEvent <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Action` | `Object` | No | Specifies the commands to handle the event. The commands in the **Action** run when an event is raised, instead of sending the event to the event queue. Enclose the commands in braces (`{}`) to cre... |
| `-EventName` | `Object` | Yes | Specifies the event to which you are subscribing.   The value of this parameter must be the name of the event that the .NET object exposes. For example, the **ManagementEventWatcher** class has eve... |
| `-Forward` | `Object` | No | Indicates that the cmdlet sends events for this subscription to a remote session. Use this parameter when you are registering for events on a remote computer or in a remote session. |
| `-InputObject` | `Object` | Yes | Specifies the .NET object that generates the events. Enter a variable that contains the object, or type a command or expression that gets the object. |
| `-MaxTriggerCount` | `Object` | No | Specifies the maximum number of times an event can be triggered. |
| `-MessageData` | `Object` | No | Specifies any additional data to be associated with this event subscription. The value of this parameter appears in the MessageData property of all events associated with this subscription. |
| `-SourceIdentifier` | `Object` | No | Specifies a name that you select for the subscription. The name that you select must be unique in the current session. The default value is the GUID that PowerShell assigns.   The value of this par... |
| `-SupportEvent` | `Object` | No | Indicates that the cmdlet hides the event subscription. Use this parameter when the current subscription is part of a more complex event registration mechanism and should not be discovered independ... |

---

### Remove-Alias

Remove an alias from the current session.

The `Remove-Alias` cmdlet removes an alias from the current PowerShell session. To remove an alias with the **Option** property set to **ReadOnly**, use the **Force** parameter.

**Returns**: `None`

```
Remove-Alias
    [-Force <Object>]
    -Name <Object>
    [-Scope <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Force` | `Object` | No | Indicates that the cmdlet removes an alias, including aliases with the **Option** property set to **ReadOnly**. The **Force** parameter can't remove an alias with an **Option** property set to **Co... |
| `-Name` | `Object` | Yes | Specifies the name of the alias to remove. |
| `-Scope` | `Object` | No | Affects only the aliases in the specified scope. The default scope is **Local**. For more information, see [about_Scopes](../microsoft.powershell.core/about/about_scopes.md).   The acceptable value... |

---

### Remove-Event

Deletes events from the event queue.

The `Remove-Event` cmdlet deletes events from the event queue in the current session.

**Returns**: `None`

```
Remove-Event
    [-Confirm <Object>]
    -EventIdentifier <Object>
    -SourceIdentifier <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-EventIdentifier` | `Object` | Yes | Specifies the event identifier for which the cmdlet deletes. An **EventIdentifier** or **SourceIdentifier** parameter is required in every command. |
| `-SourceIdentifier` | `Object` | Yes | Specifies the source identifier for which this cmdlet deletes events from. Wildcards are not permitted. An **EventIdentifier** or **SourceIdentifier** parameter is required in every command. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Remove-PSBreakpoint

Deletes breakpoints from the current console.

The `Remove-PSBreakpoint` cmdlet deletes a breakpoint. Enter a breakpoint object or a breakpoint ID.

**Returns**: `None`

```
Remove-PSBreakpoint
    -Breakpoint <Object>
    [-Confirm <Object>]
    -Id <Object>
    [-Runspace <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Breakpoint` | `Object` | Yes | Specifies the breakpoints to delete. Enter a variable that contains breakpoint objects or a command that gets breakpoint objects, such as a `Get-PSBreakpoint` command. You can also pipe breakpoint ... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Id` | `Object` | Yes | Specifies breakpoint IDs for which this cmdlet deletes breakpoints. |
| `-Runspace` | `Object` | No | Specifies the Id of a **Runspace** object so you can interact with breakpoints in the specified runspace.   This parameter was added in PowerShell 7.2. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Remove-TypeData

Deletes extended types from the current session.

The `Remove-TypeData` cmdlet deletes extended type data from the current session. This cmdlet affects only the current session and sessions that are created in the current session.

**Returns**: `None`

```
Remove-TypeData
    [-Confirm <Object>]
    -Path <Object>
    -TypeData <Object>
    -TypeName <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Path` | `Object` | Yes | Specifies an array of files that this cmdlet deletes from the session extended type data. This parameter is required.   Enter the paths and file names of one or more `Types.ps1xml` files. Wildcards... |
| `-TypeData` | `Object` | Yes | Specifies the type data that this cmdlet deletes from the session. This parameter is required. Enter a variable that contains **TypeData** objects (**System.Management.Automation.Runspaces.TypeData... |
| `-TypeName` | `Object` | Yes | Specifies the types that this cmdlet deletes all extended type data for. For types in the System namespace, enter the short name. Otherwise, the full type name is required. Wildcards are not suppor... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Remove-Variable

Deletes a variable and its value.

The `Remove-Variable` cmdlet deletes a variable and its value from the scope in which it is defined, such as the current session. You cannot use this cmdlet to delete variables that are set as constants or those that are owned by the system.

**Returns**: `None`

```
Remove-Variable
    [-Confirm <Object>]
    [-Exclude <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -Name <Object>
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Exclude` | `Object` | No | Specifies an array of items that this cmdlet omits from the operation. The value of this parameter qualifies the **Name** parameter. Enter a name element or pattern, such as "s*". Wildcards are per... |
| `-Force` | `Object` | No | Indicates that the cmdlet removes a variable even if it is read-only. Even using the **Force** parameter, the cmdlet cannot remove a constant. |
| `-Include` | `Object` | No | Specifies an array of items that this cmdlet deletes in the operation. The value of this parameter qualifies the **Name** parameter. Enter a name element or pattern, such as s*. Wildcards are permi... |
| `-Name` | `Object` | Yes | Specifies the name of the variable to be removed. The parameter name (**Name**) is optional. Wildcards are permitted |
| `-Scope` | `Object` | No | Gets only the variables in the specified scope. The acceptable values for this parameter are:   - Global - Local - Script - A number relative to the current scope (0 through the number of scopes, w... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Select-Object

Selects objects or object properties.

The `Select-Object` cmdlet selects specified properties of an object or set of objects. It can also select unique objects, a specified number of objects, or objects in a specified position in an array.

**Returns**: `System.Management.Automation.PSObject`

```
Select-Object
    [-CaseInsensitive <Object>]
    [-ExcludeProperty <Object>]
    [-ExpandProperty <Object>]
    [-First <Object>]
    [-Index <Object>]
    [-InputObject <Object>]
    [-Last <Object>]
    [-Property <Object>]
    [-Skip <Object>]
    [-SkipIndex <Object>]
    [-SkipLast <Object>]
    [-Unique <Object>]
    [-Wait <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CaseInsensitive` | `Object` | No | By default, when you use the **Unique** parameter the cmdlet uses case-sensitive comparisons. When you use this parameter, the cmdlet uses case-insensitive comparisons.   This parameter was added i... |
| `-ExcludeProperty` | `Object` | No | Specifies the properties that this cmdlet excludes from the operation. Wildcards are permitted.   Beginning in PowerShell 6, it's no longer required to include the **Property** parameter for **Excl... |
| `-ExpandProperty` | `Object` | No | Specifies a property to select, and indicates that an attempt should be made to expand that property. If the input object pipeline doesn't have the property named, `Select-Object` returns an error.... |
| `-First` | `Object` | No | Specifies the number of objects to select from the beginning of an array of input objects. |
| `-Index` | `Object` | No | Selects objects from an array based on their index values. Enter the indexes in a comma-separated list. Indexes in an array begin with 0, where 0 represents the first value and (n-1) represents the... |
| `-InputObject` | `Object` | No | Specifies objects to send to the cmdlet through the pipeline. This parameter enables you to pipe objects to `Select-Object`.   When you pass objects to the **InputObject** parameter, instead of usi... |
| `-Last` | `Object` | No | Specifies the number of objects to select from the end of an array of input objects. |
| `-Property` | `Object` | No | Specifies the properties to select. These properties are added as **NoteProperty** members to the output objects. Wildcards are permitted. If the input object doesn't have the property named, the v... |
| `-Skip` | `Object` | No | Skips (doesn't select) the specified number of items. By default, the **Skip** parameter counts from the beginning of the collection of objects. If the command uses the **Last** parameter, it count... |
| `-SkipIndex` | `Object` | No | Skips (doesn't select) the objects from an array based on their index values. Enter the indexes in a comma-separated list. Indexes in an array begin with 0, where 0 represents the first value and (... |
| `-SkipLast` | `Object` | No | Skips (doesn't select) the specified number of items from the end of the list or array. Works in the same way as using **Skip** together with **Last** parameter.   Unlike the **Index** parameter, w... |
| `-Unique` | `Object` | No | Specifies that if a subset of the input objects has identical properties and values, only a single member of the subset should be selected.   **Unique** selects values _after_ other filtering param... |
| `-Wait` | `Object` | No | Indicates that the cmdlet turns off optimization. PowerShell runs commands in the order that they appear in the command pipeline and lets them generate all objects. By default, if you include a `Se... |

---

### Select-String

Finds text in strings and files.

The `Select-String` cmdlet uses regular expression matching to search for text patterns in input strings and files. You can use `Select-String` similar to `grep` in Unix or `findstr.exe` in Windows.

**Returns**: `Microsoft.PowerShell.Commands.MatchInfo`

```
Select-String
    [-AllMatches <Object>]
    [-CaseSensitive <Object>]
    [-Context <Object>]
    [-Culture <Object>]
    [-Encoding <Object>]
    [-Exclude <Object>]
    [-Include <Object>]
    -InputObject <Object>
    [-List <Object>]
    -LiteralPath <Object>
    [-NoEmphasis <Object>]
    [-NotMatch <Object>]
    -Path <Object>
    -Pattern <Object>
    [-Quiet <Object>]
    -Raw <Object>
    [-SimpleMatch <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AllMatches` | `Object` | No | Indicates that the cmdlet searches for more than one match in each line of text. Without this parameter, `Select-String` finds only the first match in each line of text.   When `Select-String` find... |
| `-CaseSensitive` | `Object` | No | Indicates that the cmdlet matches are case-sensitive. By default, matches aren't case-sensitive. |
| `-Context` | `Object` | No | Captures the specified number of lines before and after the line that matches the pattern.   If you enter one number as the value of this parameter, that number determines the number of lines captu... |
| `-Culture` | `Object` | No | Specifies a culture name to match the specified pattern. The **Culture** parameter must be used with the **SimpleMatch** parameter. The default behavior uses the culture of the current PowerShell r... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-Exclude` | `Object` | No | Exclude the specified items. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.txt`. Wildcards are permitted. |
| `-Include` | `Object` | No | Includes the specified items. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.txt`. Wildcards are permitted. |
| `-InputObject` | `Object` | Yes | Specifies the text to be searched. Enter a variable that contains the text, or type a command or expression that gets the text.   Using the **InputObject** parameter isn't the same as sending strin... |
| `-List` | `Object` | No | Only the first instance of matching text is returned from each input file. This is the most efficient way to retrieve a list of files that have contents matching the regular expression.   By defaul... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to the files to be searched. The value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape cha... |
| `-NoEmphasis` | `Object` | No | By default, `Select-String` highlights the string that matches the pattern you searched for with the **Pattern** parameter. The **NoEmphasis** parameter disables the highlighting.   The emphasis us... |
| `-NotMatch` | `Object` | No | The **NotMatch** parameter finds text that doesn't match the specified pattern. |
| `-Path` | `Object` | Yes | Specifies the path to the files to search. Wildcards are permitted. The default location is the local directory.   Specify files in the directory, such as `log1.txt`, `*.doc`, or `*.*`. If you spec... |
| `-Pattern` | `Object` | Yes | Specifies the text to find on each line. The pattern value is treated as a regular expression. The parameter accepts multiple patterns in an array. If you specify more than one pattern, `Select-Str... |
| `-Quiet` | `Object` | No | Indicates that the cmdlet returns a simple response instead of a **MatchInfo** object. The returned value is `$true` if the pattern is found or `$null` if the pattern is not found. |
| `-Raw` | `Object` | Yes | Causes the cmdlet to output only the matching strings, rather than **MatchInfo** objects. This behavior is most similar to the Unix `grep` or Windows `findstr.exe` commands.   This parameter was in... |
| `-SimpleMatch` | `Object` | No | Indicates that the cmdlet uses a simple match rather than a regular expression match. In a simple match, `Select-String` searches the input for the text in the **Pattern** parameter. It doesn't int... |

---

### Select-Xml

Finds text in an XML string or document.

The `Select-Xml` cmdlet lets you use XPath queries to search for text in XML strings and documents. Enter an XPath query, and use the **Content**, **Path**, or **Xml** parameter to specify the XML to be searched.

**Returns**: `Microsoft.PowerShell.Commands.SelectXmlInfo`

```
Select-Xml
    -Content <Object>
    -LiteralPath <Object>
    [-Namespace <Object>]
    -Path <Object>
    -Xml <Object>
    -XPath <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Content` | `Object` | Yes | Specifies a string that contains the XML to search. You can also pipe strings to `Select-Xml`. |
| `-LiteralPath` | `Object` | Yes | Specifies the paths and file names of the XML files to search. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards... |
| `-Namespace` | `Object` | No | Specifies a hash table of the namespaces used in the XML. Use the format`@{<namespaceName> = <namespaceValue>}`.   When the XML uses the default namespace, which begins with xmlns, use an arbitrary... |
| `-Path` | `Object` | Yes | Specifies the path and file names of the XML files to search. Wildcard characters are permitted. |
| `-Xml` | `Object` | Yes | Specifies one or more XML nodes.   An XML document will be processed as a collection of XML nodes. If you pipe an XML document to `Select-Xml`, each document node will be searched separately as it ... |
| `-XPath` | `Object` | Yes | Specifies an XPath search query. The query language is case-sensitive. This parameter is required. |

---

### Send-MailMessage

Sends an email message.

The `Send-MailMessage` cmdlet sends an email message from within PowerShell.

**Returns**: `None`

```
Send-MailMessage
    [-Attachments <Object>]
    [-Bcc <Object>]
    [-Body <Object>]
    [-BodyAsHtml <Object>]
    [-Cc <Object>]
    [-Credential <Object>]
    [-DeliveryNotificationOption <Object>]
    [-Encoding <Object>]
    -From <Object>
    [-Port <Object>]
    [-Priority <Object>]
    [-ReplyTo <Object>]
    [-SmtpServer <Object>]
    [-Subject <Object>]
    -To <Object>
    [-UseSsl <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Attachments` | `Object` | No | Specifies the path and file names of files to be attached to the email message. You can use this parameter or pipe the paths and file names to `Send-MailMessage`. |
| `-Bcc` | `Object` | No | Specifies the email addresses that receive a copy of the mail but aren't listed as recipients of the message. Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`. |
| `-Body` | `Object` | No | Specifies the content of the email message. |
| `-BodyAsHtml` | `Object` | No | Specifies that the value of the **Body** parameter contains HTML. |
| `-Cc` | `Object` | No | Specifies the email addresses to which a carbon copy (CC) of the email message is sent. Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`. |
| `-Credential` | `Object` | No | Specifies a user account that has permission to perform this action. The default is the current user.   Type a user name, such as **User01** or **Domain01\User01**. Or, enter a **PSCredential** obj... |
| `-DeliveryNotificationOption` | `Object` | No | Specifies the delivery notification options for the email message. You can specify multiple values. None is the default value. The alias for this parameter is **DNO**.   The delivery notifications ... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-From` | `Object` | Yes | The **From** parameter is required. This parameter specifies the sender's email address. Enter a name (optional) and email address, such as `Name <someone@fabrikam.com>`. |
| `-Port` | `Object` | No | Specifies an alternate port on the SMTP server. The default value is 25, which is the default SMTP port. |
| `-Priority` | `Object` | No | Specifies the priority of the email message. Normal is the default. The acceptable values for this parameter are Normal, High, and Low. |
| `-ReplyTo` | `Object` | No | Specifies additional email addresses (other than the From address) to use to reply to this message. Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`.   This param... |
| `-SmtpServer` | `Object` | No | Specifies the name of the SMTP server that sends the email message.   The default value is the value of the `$PSEmailServer` preference variable. If the preference variable isn't set and this param... |
| `-Subject` | `Object` | No | The **Subject** parameter isn't required. This parameter specifies the subject of the email message. |
| `-To` | `Object` | Yes | The **To** parameter is required. This parameter specifies the recipient's email address. Enter names (optional) and the email address, such as `Name <someone@fabrikam.com>`. |
| `-UseSsl` | `Object` | No | The Secure Sockets Layer (SSL) protocol is used to establish a secure connection to the remote computer to send mail. By default, SSL isn't used. |

---

### Set-Alias

Creates or changes an alias for a cmdlet or other command in the current PowerShell session.

The `Set-Alias` cmdlet creates or changes an alias for a cmdlet or a command, such as a function, script, file, or other executable. An alias is an alternate name that refers to a cmdlet or command. For example, `sal` is the alias for the `Set-Alias` cmdlet. For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).

**Returns**: `None`

```
Set-Alias
    [-Confirm <Object>]
    [-Description <Object>]
    [-Force <Object>]
    -Name <Object>
    [-Option <Object>]
    [-PassThru <Object>]
    [-Scope <Object>]
    -Value <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Description` | `Object` | No | Specifies a description of the alias. You can type any string. If the description includes spaces, enclose it in single quotation marks. |
| `-Force` | `Object` | No | Use the **Force** parameter to change or delete an alias that has the **Option** parameter set to **ReadOnly**.   The **Force** parameter can't change or delete an alias with the **Option** paramet... |
| `-Name` | `Object` | Yes | Specifies the name of a new alias. An alias name can contain alphanumeric characters and hyphens. Alias names can't be numeric, such as 123. |
| `-Option` | `Object` | No | Sets the **Option** property value of the alias. Values such as `ReadOnly` and `Constant` protect an alias from unintended changes. To see the **Option** property of all aliases in the session, typ... |
| `-PassThru` | `Object` | No | Returns an object that represents the alias. Use a format cmdlet such as `Format-List` to display the object. By default, `Set-Alias` doesn't generate any output. |
| `-Scope` | `Object` | No | Specifies the scope this alias is valid in. The default value is **Local**. For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).   The acceptable values are... |
| `-Value` | `Object` | Yes | Specifies the name of the cmdlet or command that the alias runs. The **Value** parameter is the alias's **Definition** property. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Set-Date

Changes the system time on the computer to a time that you specify.

The `Set-Date` cmdlet changes the system date and time on the computer to a date and time that you specify.

**Returns**: `System.DateTime`

```
Set-Date
    -Adjust <Object>
    [-Confirm <Object>]
    -Date <Object>
    [-DisplayHint <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Adjust` | `Object` | Yes | Specifies the value for which this cmdlet adds or subtracts from the current date and time. You can type an adjustment in standard date and time format for your locale or use the **Adjust** paramet... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Date` | `Object` | Yes | Changes the date and time to the specified values. You can type a new date in the short date format and a time in the standard time format for your locale. Or, you can pass a **DateTime** object fr... |
| `-DisplayHint` | `Object` | No | Specifies which elements of the date and time are displayed. The acceptable values for this parameter are:   - `Date` - displays only the date. - `Time` - displays only the time. - `DateTime` - dis... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Set-MarkdownOption

Sets the colors and styles used for rendering Markdown content in the console.

Sets the colors and styles used for rendering Markdown content in the console. These styles are defined using ANSI escape codes that change the color and style of the Markdown text being rendered.

**Returns**: `Microsoft.PowerShell.MarkdownRender.PSMarkdownOptionInfo`

```
Set-MarkdownOption
    [-BoldForegroundColor <Object>]
    [-Code <Object>]
    [-Header1Color <Object>]
    [-Header2Color <Object>]
    [-Header3Color <Object>]
    [-Header4Color <Object>]
    [-Header5Color <Object>]
    [-Header6Color <Object>]
    [-ImageAltTextForegroundColor <Object>]
    -InputObject <Object>
    [-ItalicsForegroundColor <Object>]
    [-LinkForegroundColor <Object>]
    [-PassThru <Object>]
    -Theme <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BoldForegroundColor` | `Object` | No | Sets the foreground color for rendering bold Markdown text. |
| `-Code` | `Object` | No | Sets the color for rendering code blocks and spans in Markdown text. |
| `-Header1Color` | `Object` | No | Sets the color for rendering Header1 blocks in Markdown text. |
| `-Header2Color` | `Object` | No | Sets the color for rendering Header2 blocks in Markdown text. |
| `-Header3Color` | `Object` | No | Sets the color for rendering Header3 blocks in Markdown text. |
| `-Header4Color` | `Object` | No | Sets the color for rendering Header4 blocks in Markdown text. |
| `-Header5Color` | `Object` | No | Sets the color for rendering Header5 blocks in Markdown text. |
| `-Header6Color` | `Object` | No | Sets the color for rendering Header6 blocks in Markdown text. |
| `-ImageAltTextForegroundColor` | `Object` | No | Sets the foreground color for rendering the alternate text of an image element in Markdown text. |
| `-InputObject` | `Object` | Yes | A **PSMarkdownOptionInfo** object containing the configuration to be set. |
| `-ItalicsForegroundColor` | `Object` | No | Sets the foreground color for rendering the italics in Markdown text. |
| `-LinkForegroundColor` | `Object` | No | Sets the foreground color for rendering hyperlinks in Markdown text. |
| `-PassThru` | `Object` | No | Causes the cmdlet to output a **PSMarkdownOptionInfo** object containing the new configuration. |
| `-Theme` | `Object` | Yes | Selects a theme containing predefined color settings. The possible values are **Dark** and **Light**. |

---

### Set-PSBreakpoint

Sets a breakpoint on a line, command, or variable.

The `Set-PSBreakpoint` cmdlet sets a breakpoint in a script or in any command run in the current session. You can use `Set-PSBreakpoint` to set a breakpoint before executing a script or running a command, or during debugging, when stopped at another breakpoint.

**Returns**: `System.Management.Automation.CommandBreakpoint`

```
Set-PSBreakpoint
    [-Action <Object>]
    [-Column <Object>]
    -Command <Object>
    -Line <Object>
    [-Mode <Object>]
    [-Runspace <Object>]
    -Script <Object>
    -Variable <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Action` | `Object` | No | Specifies commands that run at each breakpoint instead of breaking. Enter a scriptblock that contains the commands. You can use this parameter to set conditional breakpoints or to perform other tas... |
| `-Column` | `Object` | No | Specifies the column number of the column in the script file on which execution stops. Enter only one column number. The default is column 1.   The Column value is used with the value of the **Line... |
| `-Command` | `Object` | Yes | Sets a command breakpoint. Enter cmdlet names, such as `Get-Process`, or function names. Wildcards are permitted.   Execution stops just before each instance of each command is executed. If the com... |
| `-Line` | `Object` | Yes | Sets a line breakpoint in a script. Enter one or more line numbers, separated by commas. PowerShell stops immediately before executing the statement that begins on each of the specified lines.   Li... |
| `-Mode` | `Object` | No | Specifies the mode of access that triggers variable breakpoints. The default is **Write**.   This parameter is valid only when the **Variable** parameter is used in the command. The mode applies to... |
| `-Runspace` | `Object` | No | Specifies the Id of a **Runspace** object so you can interact with breakpoints in the specified runspace.   This parameter was added in PowerShell 7.2. |
| `-Script` | `Object` | Yes | Specifies an array of script files that this cmdlet sets a breakpoint in. Enter the paths and file names of one or more script files. If the files are in the current directory, you can omit the pat... |
| `-Variable` | `Object` | Yes | Specifies an array of variables that this cmdlet sets breakpoints on. Enter a comma-separated list of variables without dollar signs (`$`).   Use the **Mode** parameter to determine the mode of acc... |

---

### Set-TraceSource

Configures, starts, and stops a trace of PowerShell components.

The `Set-TraceSource` cmdlet configures, starts, and stops a trace of a PowerShell component. You can use it to specify which components will be traced and where the tracing output is sent.

**Returns**: `None`

```
Set-TraceSource
    [-Debugger <Object>]
    [-FilePath <Object>]
    [-Force <Object>]
    [-ListenerOption <Object>]
    -Name <Object>
    [-Option <Object>]
    [-PassThru <Object>]
    [-PSHost <Object>]
    [-RemoveFileListener <Object>]
    [-RemoveListener <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Debugger` | `Object` | No | Indicates that the cmdlet sends the trace output to the debugger. You can view the output in any user-mode or kernel mode debugger or in Microsoft Visual Studio. This parameter also selects the def... |
| `-FilePath` | `Object` | No | Specifies a file that this cmdlet sends the trace output to. This parameter also selects the file trace listener. If you use this parameter to start the trace, use the **RemoveFileListener** parame... |
| `-Force` | `Object` | No | Indicates that the cmdlet overwrites a read-only file. Use with the **FilePath** parameter. |
| `-ListenerOption` | `Object` | No | Specifies optional data to the prefix of each trace message in the output. The acceptable values for this parameter are:   - `None` - `LogicalOperationStack` - `DateTime` - `Timestamp` - `ProcessId... |
| `-Name` | `Object` | Yes | Specifies which components are traced. Enter the name of the trace source of each component. Wildcards are permitted. |
| `-Option` | `Object` | No | Specifies the type of events that are traced. The acceptable values for this parameter are:   - `None` - `Constructor` - `Dispose` - `Finalizer` - `Method` - `Property` - `Delegates` - `Events` - `... |
| `-PassThru` | `Object` | No | Returns an object representing the item with which you are working. By default, this cmdlet does not generate any output. |
| `-PSHost` | `Object` | No | Indicates that this cmdlet sends the trace output to the PowerShell host. This parameter also selects the PSHost trace listener. |
| `-RemoveFileListener` | `Object` | No | Stops the trace by removing the file trace listener associated with the specified file. Enter the path and file name of the trace output file. |
| `-RemoveListener` | `Object` | No | Stops the trace by removing the trace listener.   Use the following values with **RemoveListener**:   - To remove PSHost (console), type `Host`. - To remove Debugger, type `Debug`. - To remove all ... |

---

### Set-Variable

Sets the value of a variable. Creates the variable if one with the requested name does not exist.

The `Set-Variable` cmdlet assigns a value to a specified variable or changes the current value. If the variable does not exist, the cmdlet creates it.

**Returns**: `None`

```
Set-Variable
    [-Confirm <Object>]
    [-Description <Object>]
    [-Exclude <Object>]
    [-Force <Object>]
    [-Include <Object>]
    -Name <Object>
    [-Option <Object>]
    [-PassThru <Object>]
    [-Scope <Object>]
    [-Value <Object>]
    [-Visibility <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Description` | `Object` | No | Specifies the description of the variable. |
| `-Exclude` | `Object` | No | Specifies an array of items that this cmdlet excludes from the operation. The value of this parameter qualifies the **Path** parameter. Enter a path element or pattern, such as `*.txt`. Wildcards a... |
| `-Force` | `Object` | No | Allows you to create a variable with the same name as an existing read-only variable, or to change the value of a read-only variable.   By default, you can overwrite a variable, unless the variable... |
| `-Include` | `Object` | No | Specifies an array of items that this cmdlet includes in the operation. The value of this parameter qualifies the **Name** parameter. Enter a name or name pattern, such as `c*`. Wildcards are permi... |
| `-Name` | `Object` | Yes | Specifies the variable name. |
| `-Option` | `Object` | No | Specifies the value of the **Options** property of the variable.   Valid values are:   - `None`: Sets no options. (`None` is the default.) - `ReadOnly`: Can be deleted. Cannot be changed, except by... |
| `-PassThru` | `Object` | No | Returns an object representing the new variable. By default, this cmdlet does not generate any output. |
| `-Scope` | `Object` | No | Specifies the scope of the variable.The acceptable values for this parameter are:   - `Global` - `Local` - `Script` - `Private` - A number relative to the current scope (0 through the number of sco... |
| `-Value` | `Object` | No | Specifies the value of the variable. |
| `-Visibility` | `Object` | No | Determines whether the variable is visible outside of the session in which it was created. This parameter is designed for use in scripts and commands that will be delivered to other users.   Valid ... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Show-Markdown

Shows a Markdown file or string in the console in a friendly way using VT100 escape sequences or in
a browser using HTML.

The `Show-Markdown` cmdlet is used to render Markdown in a human readable format either in a terminal or in a browser.

**Returns**: `System.String`

```
Show-Markdown
    -InputObject <Object>
    -LiteralPath <Object>
    -Path <Object>
    [-UseBrowser <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | Yes | A Markdown string that will be shown in the terminal. If you do not pass in a supported format, `Show-Markdown` will emit an error. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to a Markdown file. Unlike the Path parameter, the value of LiteralPath is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape ch... |
| `-Path` | `Object` | Yes | Specifies the path to a Markdown file to be rendered. |
| `-UseBrowser` | `Object` | No | Compiles the Markdown input as HTML and opens it in your default browser. |

---

### Sort-Object

Sorts objects by property values.

The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values. If sort properties aren't included in a command, PowerShell uses default sort properties of the first input object. If the input object's type has no default sort properties, PowerShell attempts to compare the objects themselves. For more information, see the [Notes](#notes) section.

**Returns**: `System.Management.Automation.PSObject`

```
Sort-Object
    -Bottom <Object>
    [-CaseSensitive <Object>]
    [-Culture <Object>]
    [-Descending <Object>]
    [-InputObject <Object>]
    [-Property <Object>]
    [-Stable <Object>]
    -Top <Object>
    [-Unique <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Bottom` | `Object` | Yes | Specifies the number of objects to get from the end of a sorted object array. This results in a stable sort.   This parameter was introduced in PowerShell 6.0. |
| `-CaseSensitive` | `Object` | No | Indicates that the sort is case-sensitive. By default, sorts aren't case-sensitive. |
| `-Culture` | `Object` | No | Specifies the cultural configuration to use for sorts. Use `Get-Culture` to display the system's culture configuration. |
| `-Descending` | `Object` | No | Indicates that `Sort-Object` sorts the objects in descending order. The default is ascending order.   To sort multiple properties with different sort orders, use a hash table. For example, with a h... |
| `-InputObject` | `Object` | No | To sort objects, send them down the pipeline to `Sort-Object`. If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collec... |
| `-Property` | `Object` | No | Specifies the property names that `Sort-Object` uses to sort the objects. Wildcards are permitted. Objects are sorted based on the property values. If you don't specify a property, `Sort-Object` so... |
| `-Stable` | `Object` | No | The sorted objects are delivered in the order they were received when the sort criteria are equal.   This parameter was added in PowerShell v6.2.0. |
| `-Top` | `Object` | Yes | Specifies the number of objects to get from the start of a sorted object array. This results in a stable sort.   This parameter was introduced in PowerShell 6.0. |
| `-Unique` | `Object` | No | Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection. The first instance of a unique value is included in the sorted output.   **Unique** is case... |

---

### Start-Sleep

Suspends the activity in a script or session for the specified period of time.

The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time. You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.

**Returns**: `None`

```
Start-Sleep
    -Duration <Object>
    -Milliseconds <Object>
    -Seconds <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Duration` | `Object` | Yes | Uses a **TimeSpan** object to specify how long the resource sleeps in milliseconds. The value must not be a negative **TimeSpan** and must not exceed `[int]::MaxValue` milliseconds.   This paramete... |
| `-Milliseconds` | `Object` | Yes | Specifies how long the resource sleeps in milliseconds. The parameter can be abbreviated as **m**. |
| `-Seconds` | `Object` | Yes | Specifies how long the resource sleeps in seconds. You can omit the parameter name or you can abbreviate it as **s**. Beginning in PowerShell 6.2.0, this parameter now accepts fractional values. |

---

### Tee-Object

Saves command output in a file or variable and also sends it down the pipeline.

The `Tee-Object` cmdlet write output in two directions. It stores the output in a file or variable and also sends it down the pipeline. If `Tee-Object` is the last command in the pipeline, the command output is displayed in the console.

**Returns**: `System.Management.Automation.PSObject`

```
Tee-Object
    [-Append <Object>]
    [-Encoding <Object>]
    -FilePath <Object>
    [-InputObject <Object>]
    -LiteralPath <Object>
    -Variable <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Append` | `Object` | No | Indicates that the cmdlet appends the output to the specified file. Without this parameter, the new content replaces any existing content in the file without warning.   This parameter was introduce... |
| `-Encoding` | `Object` | No | Specifies the type of encoding for the target file. The default value is `utf8NoBOM`.   The acceptable values for this parameter are as follows:   - `ascii`: Uses the encoding for the ASCII (7-bit)... |
| `-FilePath` | `Object` | Yes | Specifies a file that this cmdlet saves the object to Wildcard characters are permitted, but must resolve to a single file.   Starting in PowerShell 7, when you specify the **FilePath** as `\\.\CON... |
| `-InputObject` | `Object` | No | Specifies the object to be saved and displayed. Enter a variable that contains the objects or type a command or expression that gets the objects. You can also pipe an object to `Tee-Object`.   When... |
| `-LiteralPath` | `Object` | Yes | Specifies a file that this cmdlet saves the object to. Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards. If... |
| `-Variable` | `Object` | Yes | Specifies a variable that the cmdlet saves the object to. Enter a variable name without the preceding dollar sign (`$`). |

---

### Test-Json

Tests whether a string is a valid JSON document

The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.

**Returns**: `Boolean`

```
Test-Json
    -Json <Object>
    -LiteralPath <Object>
    [-Options <Object>]
    -Path <Object>
    -Schema <Object>
    -SchemaFile <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Json` | `Object` | Yes | Specifies the JSON string to test for validity. Enter a variable that contains the string, or type a command or expression that gets the string. You can also pipe a string to `Test-Json`.   The **J... |
| `-LiteralPath` | `Object` | Yes | Specifies a path to a JSON file. The value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcards. If the path includes escape characters, enclose it in single... |
| `-Options` | `Object` | No | By default, `Test-Json` doesn't support JSON containing comments or trailing commas. This parameter allows you to specify options to change the default behavior. The following options are available... |
| `-Path` | `Object` | Yes | Specifies the path to a JSON file. This cmdlet gets the item at the specified location. Wildcard characters are permitted but the pattern must resolve to a single file.   This parameter was added i... |
| `-Schema` | `Object` | Yes | Specifies a schema to validate the JSON input against. If passed, `Test-Json` validates that the JSON input conforms to the spec specified by the **Schema** parameter and return `$true` only if the... |
| `-SchemaFile` | `Object` | Yes | Specifies a schema file used to validate the JSON input. When used, the `Test-Json` returns `$true` only if the JSON input conforms to the schema defined in the file specified by the **SchemaFile**... |

---

### Trace-Command

Configures and starts a trace of the specified expression or command.

The `Trace-Command` cmdlet configures and starts a trace of the specified expression or command. It works like Set-TraceSource, except that it applies only to the specified command.

**Returns**: `System.Management.Automation.PSObject`

```
Trace-Command
    [-ArgumentList <Object>]
    -Command <Object>
    [-Debugger <Object>]
    -Expression <Object>
    [-FilePath <Object>]
    [-Force <Object>]
    [-InputObject <Object>]
    [-ListenerOption <Object>]
    -Name <Object>
    [-Option <Object>]
    [-PSHost <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object` | No | Specifies the parameters and parameter values for the command being traced. The alias for **ArgumentList** is **Args**. This feature is useful for debugging dynamic parameters.   For more informati... |
| `-Command` | `Object` | Yes | Specifies a command that's being processed during the trace.   When you use this parameter, PowerShell processes the command just as it would be processed in a pipeline. For example, command discov... |
| `-Debugger` | `Object` | No | Indicates that the cmdlet sends the trace output to the debugger. You can view the output in any user-mode or kernel mode debugger or in Visual Studio. This parameter also selects the default trace... |
| `-Expression` | `Object` | Yes | Specifies the expression that's being processed during the trace. Enclose the expression in braces (`{}`). |
| `-FilePath` | `Object` | No | Specifies a file that the cmdlet sends the trace output to. This parameter also selects the file trace listener. |
| `-Force` | `Object` | No | Forces the command to run without asking for user confirmation. Used with the **FilePath** parameter. Even using the **Force** parameter, the cmdlet can't override security restrictions. |
| `-InputObject` | `Object` | No | Specifies input to the expression that's being processed during the trace. You can enter a variable that represents the input that the expression accepts, or pass an object through the pipeline. |
| `-ListenerOption` | `Object` | No | Specifies optional data to the prefix of each trace message in the output. The acceptable values for this parameter are:   - `None` - `LogicalOperationStack` - `DateTime` - `Timestamp` - `ProcessId... |
| `-Name` | `Object` | Yes | Specifies an array of PowerShell components that are traced. Enter the name of the trace source of each component. Wildcards are permitted. To find the trace sources on your computer, type `Get-Tra... |
| `-Option` | `Object` | No | Determines the type of events that are traced. The acceptable values for this parameter are:   - `None` - `Constructor` - `Dispose` - `Finalizer` - `Method` - `Property` - `Delegates` - `Events` - ... |
| `-PSHost` | `Object` | No | Indicates that the cmdlet sends the trace output to the PowerShell host. This parameter also selects the PSHost trace listener. |

---

### Unblock-File

Unblocks files that were downloaded from the internet.

> **This cmdlet only works on the Windows and macOS platforms.**

**Returns**: `None`

```
Unblock-File
    [-Confirm <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-LiteralPath` | `Object` | Yes | Specifies the files to unblock. Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards. If the path includes escape c... |
| `-Path` | `Object` | Yes | Specifies the files to unblock. Wildcard characters are supported. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Unregister-Event

Cancels an event subscription.

The `Unregister-Event` cmdlet cancels an event subscription that was created by using the `Register-EngineEvent`, `Register-ObjectEvent`, or `Register-WmiEvent` cmdlet.

**Returns**: `None`

```
Unregister-Event
    [-Confirm <Object>]
    [-Force <Object>]
    -SourceIdentifier <Object>
    -SubscriptionId <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Force` | `Object` | No | Cancels all event subscriptions, including subscriptions that were hidden by using the **SupportEvent** parameter of `Register-ObjectEvent`, `Register-WmiEvent`, and `Register-EngineEvent`. |
| `-SourceIdentifier` | `Object` | Yes | Specifies a source identifier that this cmdlet cancels event subscriptions.   A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command. |
| `-SubscriptionId` | `Object` | Yes | Specifies a source identifier ID that this cmdlet cancels event subscriptions.   A **SourceIdentifier** or **SubscriptionId** parameter must be included in every command. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Update-FormatData

Updates the formatting data in the current session.

The `Update-FormatData` cmdlet reloads the formatting data from formatting files into the current session. This cmdlet lets you update the formatting data without restarting PowerShell.

**Returns**: `None`

```
Update-FormatData
    [-AppendPath <Object>]
    [-Confirm <Object>]
    [-PrependPath <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AppendPath` | `Object` | No | Specifies formatting files that this cmdlet adds to the session. The files are loaded after PowerShell loads the built-in formatting files.   When formatting .NET objects, PowerShell uses the first... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-PrependPath` | `Object` | No | Specifies formatting files that this cmdlet adds to the session. The files are loaded before PowerShell loads the built-in formatting files.   When formatting .NET objects, PowerShell uses the firs... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Update-List

Adds items to and removes items from a property value that contains a collection of objects.

The `Update-List` cmdlet adds, removes, or replaces items in a property value of an object and returns the updated object. This cmdlet is designed for properties that contain collections of objects.

**Returns**: `System.Collections.Hashtable`

```
Update-List
    [-Add <Object>]
    [-InputObject <Object>]
    [-Property <Object>]
    [-Remove <Object>]
    -Replace <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Add` | `Object` | No | Specifies the property values to be added to the collection. Enter the values in the order that they should appear in the collection. |
| `-InputObject` | `Object` | No | Specifies the objects to be updated. You can also pipe the object to be updated to `Update-List`. |
| `-Property` | `Object` | No | Specifies the property that contains the collection that's being updated. If you omit this parameter, `Update-List` returns an object that represents the change instead of changing the object. |
| `-Remove` | `Object` | No | Specifies the property values to be removed from the collection. |
| `-Replace` | `Object` | Yes | Specifies a new collection. This parameter replaces all items in the original collection with the items specified by this parameter. |

---

### Update-TypeData

Updates the extended type data in the session.

The `Update-TypeData` cmdlet updates the extended type data in the session by reloading the `Types.ps1xml` files into memory and adding new extended type data.

**Returns**: `None`

```
Update-TypeData
    [-AppendPath <Object>]
    [-Confirm <Object>]
    [-DefaultDisplayProperty <Object>]
    [-DefaultDisplayPropertySet <Object>]
    [-DefaultKeyPropertySet <Object>]
    [-Force <Object>]
    [-InheritPropertySerializationSet <Object>]
    [-MemberName <Object>]
    [-MemberType <Object>]
    [-PrependPath <Object>]
    [-PropertySerializationSet <Object>]
    [-SecondValue <Object>]
    [-SerializationDepth <Object>]
    [-SerializationMethod <Object>]
    [-StringSerializationSource <Object>]
    [-TargetTypeForDeserialization <Object>]
    [-TypeAdapter <Object>]
    [-TypeConverter <Object>]
    -TypeData <Object>
    -TypeName <Object>
    [-Value <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AppendPath` | `Object` | No | Specifies the path to optional `.ps1xml` files. The specified files are loaded in the order that they are listed after the built-in files are loaded. You can also pipe an **AppendPath** value to `U... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-DefaultDisplayProperty` | `Object` | No | Specifies the property of the type that is displayed by the `Format-Wide` cmdlet when no other properties are specified.   Type the name of a standard or extended property of the type. The value of... |
| `-DefaultDisplayPropertySet` | `Object` | No | Specifies one or more properties of the type. These properties are displayed by the `Format-List`, `Format-Table`, and `Format-Custom` cmdlets when no other properties are specified.   Type the nam... |
| `-DefaultKeyPropertySet` | `Object` | No | Specifies one or more properties of the type. These properties are used by the `Group-Object` and `Sort-Object` cmdlets when no other properties are specified.   Type the names of standard or exten... |
| `-Force` | `Object` | No | Indicates that the cmdlet uses the specified type data, even if type data has already been specified for that type.   This parameter was introduced in Windows PowerShell 3.0. |
| `-InheritPropertySerializationSet` | `Object` | No | Indicates whether the set of properties that are serialized is inherited. The default value is `$null`. The acceptable values for this parameter are:   - `$true`. The property set is inherited. - `... |
| `-MemberName` | `Object` | No | Specifies the name of a property or method.   Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.   T... |
| `-MemberType` | `Object` | No | Specifies the type of the member to add or change.   Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a ty... |
| `-PrependPath` | `Object` | No | Specifies the path to the optional `.ps1xml` files. The specified files are loaded in the order that they are listed before the built-in files are loaded. |
| `-PropertySerializationSet` | `Object` | No | Specifies the names of properties that are serialized. Use this parameter when the value of the **SerializationMethod** parameter is **SpecificProperties**. |
| `-SecondValue` | `Object` | No | Specifies additional values for **AliasProperty**, **ScriptProperty**, **CodeProperty**, or **CodeMethod** members.   Use this parameter with the **TypeName**, **MemberType**, **Value**, and **Seco... |
| `-SerializationDepth` | `Object` | No | Specifies how many levels of type objects are serialized as strings. The default value `1` serializes the object and its properties. A value of `0` serializes the object, but not its properties. A ... |
| `-SerializationMethod` | `Object` | No | Specifies a serialization method for the type. A serialization method determines which properties of the type are serialized and the technique that is used to serialize them. The acceptable values ... |
| `-StringSerializationSource` | `Object` | No | Specifies the name of a property of the type. The value of specified property is used as the serialization result. This parameter is valid only when the value of the **SerializationMethod** paramet... |
| `-TargetTypeForDeserialization` | `Object` | No | Specifies the type to which object of this type are converted when they are deserialized.   This parameter was introduced in Windows PowerShell 3.0. |
| `-TypeAdapter` | `Object` | No | Specifies the type of a type adapter, such as **Microsoft.PowerShell.Cim.CimInstanceAdapter**. A type adapter enables PowerShell to get the members of a type.   This parameter was introduced in Win... |
| `-TypeConverter` | `Object` | No | Specifies a type converter to convert values between different types. If a type converter is defined for a type, an instance of the type converter is used for the conversion.   Enter a **System.Typ... |
| `-TypeData` | `Object` | Yes | Specifies an array of type data that this cmdlet adds to the session. Enter a variable that contains a **TypeData** object or a command that gets a **TypeData** object, such as a `Get-TypeData` com... |
| `-TypeName` | `Object` | Yes | Specifies the name of the type to extend.   For types in the **System** namespace, enter the short name. Otherwise, the full type name is required. Wildcards are not supported.   You can pipe type ... |
| `-Value` | `Object` | No | Specifies the value of the property or method.   If you add an `AliasProperty`, `CodeProperty`, `ScriptProperty`, or `CodeMethod` member, you can use the **SecondValue** parameter to add additional... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Wait-Debugger

Stops a script in the debugger before running the next statement in the script.

Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.

**Returns**: `None`

```
Wait-Debugger
```

---

### Wait-Event

Waits until a particular event is raised before continuing to run.

The `Wait-Event` cmdlet suspends execution of a script or function until a particular event is raised. Execution resumes when the event is detected. To cancel the wait, press <kbd>CTRL</kbd>+<kbd>C</kbd>.

**Returns**: `System.Management.Automation.PSEventArgs`

```
Wait-Event
    [-SourceIdentifier <Object>]
    [-Timeout <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-SourceIdentifier` | `Object` | No | Specifies the source identifier that this cmdlet waits for events. By default, `Wait-Event` waits for any event. |
| `-Timeout` | `Object` | No | Specifies the maximum time, in seconds, that `Wait-Event` waits for the event to occur. The default, -1, waits indefinitely. The timing starts when you submit the `Wait-Event` command.   If the spe... |

---

### Write-Debug

Writes a debug message to the console.

The `Write-Debug` cmdlet writes debug messages to the host from a script or command.

**Returns**: `None`

```
Write-Debug
    -Message <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Message` | `Object` | Yes | Specifies the debug message to send to the console. |

---

### Write-Error

Writes an object to the error stream.

The `Write-Error` cmdlet declares a non-terminating error. By default, errors are sent in the error stream to the host program to be displayed, along with output.

**Returns**: `None`

```
Write-Error
    [-Category <Object>]
    [-CategoryActivity <Object>]
    [-CategoryReason <Object>]
    [-CategoryTargetName <Object>]
    [-CategoryTargetType <Object>]
    [-ErrorId <Object>]
    -ErrorRecord <Object>
    -Exception <Object>
    -Message <Object>
    [-RecommendedAction <Object>]
    [-TargetObject <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Category` | `Object` | No | Specifies the category of the error. The default value is **NotSpecified**. The acceptable values for this parameter are:   - NotSpecified - OpenError - CloseError - DeviceError - DeadlockDetected ... |
| `-CategoryActivity` | `Object` | No | Specifies the action that caused the error. |
| `-CategoryReason` | `Object` | No | Specifies how or why the activity caused the error. |
| `-CategoryTargetName` | `Object` | No | Specifies the name of the object that was being processed when the error occurred. |
| `-CategoryTargetType` | `Object` | No | Specifies the type of the object that was being processed when the error occurred. |
| `-ErrorId` | `Object` | No | Specifies an ID string to identify the error. The string should be unique to the error. |
| `-ErrorRecord` | `Object` | Yes | Specifies an error record object that represents the error. Use the properties of the object to describe the error.   To create an error record object, use the `New-Object` cmdlet or get an error r... |
| `-Exception` | `Object` | Yes | Specifies an exception object that represents the error. Use the properties of the object to describe the error.   To create an exception object, use a hash table or use the `New-Object` cmdlet. |
| `-Message` | `Object` | Yes | Specifies the message text of the error. If the text includes spaces or special characters, enclose it in quotation marks. You can also pipe a message string to `Write-Error`. |
| `-RecommendedAction` | `Object` | No | Specifies the action that the user should take to resolve or prevent the error. |
| `-TargetObject` | `Object` | No | Specifies the object that was being processed when the error occurred. Enter the object, a variable that contains the object, or a command that gets the object. |

---

### Write-Host

Writes customized output to a host.

The `Write-Host` cmdlet's primary purpose is to produce for-(host)-display-only output, such as printing colored text like when prompting the user for input in conjunction with [Read-Host](Read-Host.md). `Write-Host` uses the [ToString()](/dotnet/api/system.object.tostring) method to write the output. By contrast, to output data to the pipeline, use [Write-Output](Write-Output.md) or implicit output.

**Returns**: `None`

```
Write-Host
    [-BackgroundColor <Object>]
    [-ForegroundColor <Object>]
    [-NoNewline <Object>]
    [-Object <Object>]
    [-Separator <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BackgroundColor` | `Object` | No | Specifies the background color. There is no default. The acceptable values for this parameter are:   - `Black` - `DarkBlue` - `DarkGreen` - `DarkCyan` - `DarkRed` - `DarkMagenta` - `DarkYellow` - `... |
| `-ForegroundColor` | `Object` | No | Specifies the text color. There is no default. The acceptable values for this parameter are:   - `Black` - `DarkBlue` - `DarkGreen` - `DarkCyan` - `DarkRed` - `DarkMagenta` - `DarkYellow` - `Gray` ... |
| `-NoNewline` | `Object` | No | The string representations of the input objects are concatenated to form the output. No spaces or newlines are inserted between the output strings. No newline is added after the last output string. |
| `-Object` | `Object` | No | Objects to display in the host. |
| `-Separator` | `Object` | No | Specifies a separator string to insert between objects displayed by the host. |

---

### Write-Information

Specifies how PowerShell handles information stream data for a command.

The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.

**Returns**: `None`

```
Write-Information
    -MessageData <Object>
    [-Tags <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-MessageData` | `Object` | Yes | Specifies an informational message that you want to display to users as they run a script or command. For best results, enclose the informational message in quotation marks. |
| `-Tags` | `Object` | No | One or more strings that you can use to sort and filter messages that you have added to the information stream with `Write-Information`. This parameter works similarly to the **Tags** parameter in ... |

---

### Write-Output

Writes the specified objects to the pipeline.

Writes the specified objects to the pipeline. If `Write-Output` is the last command in the pipeline, the objects are displayed in the console.

**Returns**: `System.Management.Automation.PSObject`

```
Write-Output
    -InputObject <Object>
    [-NoEnumerate <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-InputObject` | `Object` | Yes | Specifies the objects to send down the pipeline. Enter a variable that contains the objects, or type a command or expression that gets the objects. |
| `-NoEnumerate` | `Object` | No | By default, the `Write-Output` cmdlet always enumerates its output. The **NoEnumerate** parameter suppresses the default behavior, and prevents `Write-Output` from enumerating output. The **NoEnume... |

---

### Write-Progress

Displays a progress bar within a PowerShell command window.

The `Write-Progress` cmdlet displays a progress bar in a PowerShell command window that depicts the status of a running command or script. You can select the indicators that the bar reflects and the text that appears above and below the progress bar.

**Returns**: `None`

```
Write-Progress
    [-Activity <Object>]
    [-Completed <Object>]
    [-CurrentOperation <Object>]
    [-Id <Object>]
    [-ParentId <Object>]
    [-PercentComplete <Object>]
    [-SecondsRemaining <Object>]
    [-SourceId <Object>]
    [-Status <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Activity` | `Object` | No | Specifies the first line of text in the heading above the status bar. This text describes the activity whose progress is being reported. |
| `-Completed` | `Object` | No | Indicates whether the progress bar is visible. If this parameter is omitted, `Write-Progress` displays progress information. |
| `-CurrentOperation` | `Object` | No | Specifies the line of text below the progress bar in the `Classic` progress view. This text describes the operation that's currently taking place. This parameter has no effect when the progress vie... |
| `-Id` | `Object` | No | Specifies an ID that distinguishes each progress bar from the others. Use this parameter when you are creating more than one progress bar in a single command. If the progress bars don't have differ... |
| `-ParentId` | `Object` | No | Specifies the parent activity of the current activity. Use the value `-1` if the current activity has no parent activity. |
| `-PercentComplete` | `Object` | No | Specifies the percentage of the activity that's completed. Use the value `-1` if the percentage complete is unknown or not applicable. |
| `-SecondsRemaining` | `Object` | No | Specifies the projected number of seconds remaining until the activity is completed. Use the value `-1` if the number of seconds remaining is unknown or not applicable. |
| `-SourceId` | `Object` | No | Specifies the source of the record. You can use this in place of **Id** but can't be used with other parameters like **ParentId**. |
| `-Status` | `Object` | No | Specifies the second line of text in the heading above the status bar. This text describes current state of the activity. |

---

### Write-Verbose

Writes text to the verbose message stream.

The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell. Typically, the verbose message stream is used to deliver more in depth information about command processing.

**Returns**: `None`

```
Write-Verbose
    -Message <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Message` | `Object` | Yes | Specifies the message to display. This parameter is required. You can also pipe a message string to `Write-Verbose`. |

---

### Write-Warning

Writes a warning message.

The `Write-Warning` cmdlet writes a warning message to the PowerShell host. The response to the warning depends on the value of the user's `$WarningPreference` variable and the use of the **WarningAction** common parameter.

**Returns**: `None`

```
Write-Warning
    -Message <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Message` | `Object` | Yes | Specifies the warning message. |

---

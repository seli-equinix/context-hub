---
name: pwsh-host
description: "PowerShell 7.5 Host cmdlets — console host interaction"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Start-Transcript,Stop-Transcript"
---

# PowerShell 7.5 — console host interaction

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Start-Transcript` | Creates a record of all or part of a PowerShell session to a text file. |
| `Stop-Transcript` | Stops a transcript. |

---

### Start-Transcript

Creates a record of all or part of a PowerShell session to a text file.

The `Start-Transcript` cmdlet creates a record of all or part of a PowerShell session to a text file. The transcript includes all command that the user types and all output that appears on the console.

**Returns**: `System.String`

```
Start-Transcript
    [-Append <Object>]
    [-Confirm <Object>]
    [-Force <Object>]
    [-IncludeInvocationHeader <Object>]
    [-LiteralPath <Object>]
    [-NoClobber <Object>]
    [-OutputDirectory <Object>]
    [-Path <Object>]
    [-UseMinimalHeader <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Append` | `Object` | No | Indicates that this cmdlet adds the new transcript to the end of an existing file. Use the **Path** parameter to specify the file. |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-Force` | `Object` | No | Allows the cmdlet to append the transcript to an existing read-only file. When used on a read-only file, the cmdlet changes the file permission to read-write. The cmdlet can't override security res... |
| `-IncludeInvocationHeader` | `Object` | No | Indicates that this cmdlet logs the time stamp when commands are run. |
| `-LiteralPath` | `Object` | No | Specifies a location to the transcript file. Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as it's typed. No characters are interpreted as wildcards. If ... |
| `-NoClobber` | `Object` | No | Indicates that this cmdlet doesn't overwrite an existing file. By default, if a transcript file exists in the specified path, `Start-Transcript` overwrites the file without warning. |
| `-OutputDirectory` | `Object` | No | Specifies a specific path and folder in which to save a transcript. PowerShell automatically assigns the transcript name. If you use a relative path, the path is relative to your `Documents` direct... |
| `-Path` | `Object` | No | Specifies a location to the transcript file. Enter a path to a `.txt` file. Wildcards aren't permitted. If any of the directories in the path don't exist, the command fails.   If you don't specify ... |
| `-UseMinimalHeader` | `Object` | No | Prepend a short header to the transcript, instead of the detailed header included by default. This parameter was added in PowerShell 6.2. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Stop-Transcript

Stops a transcript.

The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet. Alternatively, you can end a session to stop a transcript.

**Returns**: `System.String`

```
Stop-Transcript
    [-Confirm <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet.   This parameter was added in PowerShell 7.4. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run.   This parameter was added in PowerShell 7.4. |

---

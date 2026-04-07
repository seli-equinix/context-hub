---
name: pwsh-psreadline
description: "PowerShell 7.5 PSReadLine cmdlets — command-line editing, key handlers, prediction, history"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Get-PSReadLineKeyHandler,Get-PSReadLineOption,PSConsoleHostReadLine,Remove-PSReadLineKeyHandler,Set-PSReadLineKeyHandler,Set-PSReadLineOption"
---

# PowerShell 7.5 — command-line editing

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Get-PSReadLineKeyHandler` | Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]  Get-PSReadLineKeyHandler [-Cho... |
| `Get-PSReadLineOption` | Get-PSReadLineOption [<CommonParameters>] |
| `PSConsoleHostReadLine` | This function is the main entry point for PSReadLine. |
| `Remove-PSReadLineKeyHandler` | Remove-PSReadLineKeyHandler [-Chord] <string[]> [-ViMode <ViMode>] [<CommonParameters>] |
| `Set-PSReadLineKeyHandler` | Set-PSReadLineKeyHandler [-Chord] <string[]> [-ScriptBlock] <scriptblock> [-BriefDescription <str... |
| `Set-PSReadLineOption` | Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <string>] [-HistoryNoDuplicates]... |

---

### Get-PSReadLineKeyHandler

Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]

Get-PSReadLineKeyHandler [-Chord] <string[]> [<CommonParameters>]

**Returns**: `returnValue`

```
Get-PSReadLineKeyHandler
    [-Bound <switch>]
    -Chord <string[]>
    [-Unbound <switch>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Bound` | `switch` | No |  |
| `-Chord` | `string[]` | Yes |  |
| `-Unbound` | `switch` | No |  |

---

### Get-PSReadLineOption

Get-PSReadLineOption [<CommonParameters>]

**Returns**: `returnValue`

```
Get-PSReadLineOption
```

---

### PSConsoleHostReadLine

This function is the main entry point for PSReadLine.

`PSConsoleHostReadLine` is the main entry point for the PSReadLine module. The PowerShell console host automatically loads the PSReadLine module and calls this function. Under normal operating conditions, this function isn't intended to be used from the command line.

**Returns**: `None`

```
PSConsoleHostReadLine
```

---

### Remove-PSReadLineKeyHandler

Remove-PSReadLineKeyHandler [-Chord] <string[]> [-ViMode <ViMode>] [<CommonParameters>]

**Returns**: `returnValue`

```
Remove-PSReadLineKeyHandler
    -Chord <string[]>
    [-ViMode <ViMode>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Chord` | `string[]` | Yes |  |
| `-ViMode` | `ViMode` | No |  |

---

### Set-PSReadLineKeyHandler

Set-PSReadLineKeyHandler [-Chord] <string[]> [-ScriptBlock] <scriptblock> [-BriefDescription <string>] [-Description <string>] [-ViMode <ViMode>] [<CommonParameters>]

Set-PSReadLineKeyHandler [-Chord] <string[]> [-Function] <string> [-ViMode <ViMode>] [<CommonParameters>]

**Returns**: `returnValue`

```
Set-PSReadLineKeyHandler
    [-BriefDescription <string>]
    -Chord <string[]>
    [-Description <string>]
    -Function <string>
    -ScriptBlock <scriptblock>
    [-ViMode <ViMode>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-BriefDescription` | `string` | No |  |
| `-Chord` | `string[]` | Yes |  |
| `-Description` | `string` | No |  |
| `-Function` | `string` | Yes |  |
| `-ScriptBlock` | `scriptblock` | Yes |  |
| `-ViMode` | `ViMode` | No |  |

---

### Set-PSReadLineOption

Set-PSReadLineOption [-EditMode <EditMode>] [-ContinuationPrompt <string>] [-HistoryNoDuplicates] [-AddToHistoryHandler <Func[string,Object]>] [-CommandValidationHandler <Action[CommandAst]>] [-HistorySearchCursorMovesToEnd] [-MaximumHistoryCount <int>] [-MaximumKillRingCount <int>] [-ShowToolTips] [-ExtraPromptLineCount <int>] [-DingTone <int>] [-DingDuration <int>] [-BellStyle <BellStyle>] [-CompletionQueryItems <int>] [-WordDelimiters <string>] [-HistorySearchCaseSensitive] [-HistorySaveStyle <HistorySaveStyle>] [-HistorySavePath <string>] [-AnsiEscapeTimeout <int>] [-PromptText <string[]>] [-ViModeIndicator <ViModeStyle>] [-ViModeChangeHandler <scriptblock>] [-PredictionSource <PredictionSource>] [-PredictionViewStyle <PredictionViewStyle>] [-Colors <hashtable>] [-TerminateOrphanedConsoleApps] [-EnableScreenReaderMode] [<CommonParameters>]

**Returns**: `returnValue`

```
Set-PSReadLineOption
    [-AddToHistoryHandler <Func[string,Object]>]
    [-AnsiEscapeTimeout <int>]
    [-BellStyle <BellStyle>]
    [-Colors <hashtable>]
    [-CommandValidationHandler <Action[CommandAst]>]
    [-CompletionQueryItems <int>]
    [-ContinuationPrompt <string>]
    [-DingDuration <int>]
    [-DingTone <int>]
    [-EditMode <EditMode>]
    [-EnableScreenReaderMode <switch>]
    [-ExtraPromptLineCount <int>]
    [-HistoryNoDuplicates <switch>]
    [-HistorySavePath <string>]
    [-HistorySaveStyle <HistorySaveStyle>]
    [-HistorySearchCaseSensitive <switch>]
    [-HistorySearchCursorMovesToEnd <switch>]
    [-MaximumHistoryCount <int>]
    [-MaximumKillRingCount <int>]
    [-PredictionSource <PredictionSource>]
    [-PredictionViewStyle <PredictionViewStyle>]
    [-PromptText <string[]>]
    [-ShowToolTips <switch>]
    [-TerminateOrphanedConsoleApps <switch>]
    [-ViModeChangeHandler <scriptblock>]
    [-ViModeIndicator <ViModeStyle>]
    [-WordDelimiters <string>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AddToHistoryHandler` | `Func[string,Object]` | No |  |
| `-AnsiEscapeTimeout` | `int` | No |  |
| `-BellStyle` | `BellStyle` | No |  |
| `-Colors` | `hashtable` | No |  |
| `-CommandValidationHandler` | `Action[CommandAst]` | No |  |
| `-CompletionQueryItems` | `int` | No |  |
| `-ContinuationPrompt` | `string` | No |  |
| `-DingDuration` | `int` | No |  |
| `-DingTone` | `int` | No |  |
| `-EditMode` | `EditMode` | No |  |
| `-EnableScreenReaderMode` | `switch` | No |  |
| `-ExtraPromptLineCount` | `int` | No |  |
| `-HistoryNoDuplicates` | `switch` | No |  |
| `-HistorySavePath` | `string` | No |  |
| `-HistorySaveStyle` | `HistorySaveStyle` | No |  |
| `-HistorySearchCaseSensitive` | `switch` | No |  |
| `-HistorySearchCursorMovesToEnd` | `switch` | No |  |
| `-MaximumHistoryCount` | `int` | No |  |
| `-MaximumKillRingCount` | `int` | No |  |
| `-PredictionSource` | `PredictionSource` | No |  |
| `-PredictionViewStyle` | `PredictionViewStyle` | No |  |
| `-PromptText` | `string[]` | No |  |
| `-ShowToolTips` | `switch` | No |  |
| `-TerminateOrphanedConsoleApps` | `switch` | No |  |
| `-ViModeChangeHandler` | `scriptblock` | No |  |
| `-ViModeIndicator` | `ViModeStyle` | No |  |
| `-WordDelimiters` | `string` | No |  |

---

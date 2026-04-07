---
name: pwsh-threadjob
description: "PowerShell 7.5 ThreadJob — Start-ThreadJob for lightweight parallel execution"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Start-ThreadJob"
---

# PowerShell 7.5 — Start-ThreadJob for lightweight parallel execution

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Start-ThreadJob` | Start-ThreadJob [-ScriptBlock] <scriptblock> [-Name <string>] [-InitializationScript <scriptblock... |

---

### Start-ThreadJob

Start-ThreadJob [-ScriptBlock] <scriptblock> [-Name <string>] [-InitializationScript <scriptblock>] [-InputObject <psobject>] [-ArgumentList <Object[]>] [-ThrottleLimit <int>] [-StreamingHost <PSHost>] [<CommonParameters>]

Start-ThreadJob [-FilePath] <string> [-Name <string>] [-InitializationScript <scriptblock>] [-InputObject <psobject>] [-ArgumentList <Object[]>] [-ThrottleLimit <int>] [-StreamingHost <PSHost>] [<CommonParameters>]

**Returns**: `returnValue`

```
Start-ThreadJob
    [-ArgumentList <Object[]>]
    -FilePath <string>
    [-InitializationScript <scriptblock>]
    [-InputObject <psobject>]
    [-Name <string>]
    -ScriptBlock <scriptblock>
    [-StreamingHost <PSHost>]
    [-ThrottleLimit <int>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ArgumentList` | `Object[]` | No |  |
| `-FilePath` | `string` | Yes |  |
| `-InitializationScript` | `scriptblock` | No |  |
| `-InputObject` | `psobject` | No |  |
| `-Name` | `string` | No |  |
| `-ScriptBlock` | `scriptblock` | Yes |  |
| `-StreamingHost` | `PSHost` | No |  |
| `-ThrottleLimit` | `int` | No |  |

---

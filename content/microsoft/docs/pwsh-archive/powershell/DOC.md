---
name: pwsh-archive
description: "PowerShell 7.5 Archive cmdlets — Compress-Archive, Expand-Archive"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Compress-Archive,Expand-Archive"
---

# PowerShell 7.5 — Compress-Archive

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Compress-Archive` | Creates a compressed archive, or zipped file, from specified files and directories. |
| `Expand-Archive` | Extracts files from a specified ZIP archive file. |

---

### Compress-Archive

Creates a compressed archive, or zipped file, from specified files and directories.

The `Compress-Archive` cmdlet creates a compressed, or zipped, archive file from one or more specified files or directories. An archive packages multiple files, with optional compression, into a single zipped file for easier distribution and storage. An archive file can be compressed using the compression algorithm specified by the **CompressionLevel** parameter.

**Returns**: `None`

```
Compress-Archive
    [-CompressionLevel <Object>]
    [-Confirm <Object>]
    -DestinationPath <Object>
    -Force <Object>
    -LiteralPath <Object>
    [-PassThru <Object>]
    -Path <Object>
    -Update <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CompressionLevel` | `Object` | No | Specifies how much compression to apply when you're creating the archive file. Faster compression requires less time to create the file, but can result in larger file sizes.   If this parameter isn... |
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-DestinationPath` | `Object` | Yes | This parameter is required and specifies the path to the archive output file. The **DestinationPath** should include the name of the zipped file, and either the absolute or relative path to the zip... |
| `-Force` | `Object` | Yes | Use this parameter to overwrite an existing archive file. |
| `-LiteralPath` | `Object` | Yes | Specifies the path or paths to the files that you want to add to the archive zipped file. Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed. No characters ar... |
| `-PassThru` | `Object` | No | Causes the cmdlet to output a file object representing the archive file created.   This parameter was introduced in PowerShell 6.0. |
| `-Path` | `Object` | Yes | Specifies the path or paths to the files that you want to add to the archive zipped file. To specify multiple paths, and include files in multiple locations, use commas to separate the paths.   Thi... |
| `-Update` | `Object` | Yes | Updates the specified archive by replacing older file versions in the archive with newer file versions that have the same names. You can also add this parameter to add files to an existing archive. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

### Expand-Archive

Extracts files from a specified ZIP archive file.

The `Expand-Archive` cmdlet extracts files from a specified zipped archive file to a specified destination folder. An archive file allows multiple files to be packaged, and optionally compressed, into a single zipped file for easier distribution and storage.

**Returns**: `None`

```
Expand-Archive
    [-Confirm <Object>]
    [-DestinationPath <Object>]
    [-Force <Object>]
    -LiteralPath <Object>
    [-PassThru <Object>]
    -Path <Object>
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-DestinationPath` | `Object` | No | By default, `Expand-Archive` creates a folder in the current location that's the same name as the ZIP file. The parameter allows you to specify the path to a different folder. The target folder is ... |
| `-Force` | `Object` | No | Use this parameter to overwrite existing files. By default, `Expand-Archive` doesn't overwrite. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to an archive file. Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it's typed. Wildcard characters aren't supported. If the path includes escape c... |
| `-PassThru` | `Object` | No | Causes the cmdlet to output a list of the files expanded from the archive. |
| `-Path` | `Object` | Yes | Specifies the path to the archive file. |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet isn't run. |

---

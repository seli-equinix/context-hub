---
name: pwsh-security
description: "PowerShell 7.5 Security cmdlets — credentials, certificates, execution policy, CMS encryption, secure strings"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,ConvertFrom-SecureString,ConvertTo-SecureString,Get-CmsMessage,Get-Credential,Get-ExecutionPolicy,Get-PfxCertificate,Protect-CmsMessage,Set-ExecutionPolicy,Unprotect-CmsMessage"
---

# PowerShell 7.5 — credentials

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `ConvertFrom-SecureString` | Converts a secure string to an encrypted standard string. |
| `ConvertTo-SecureString` | Converts plain text or encrypted strings to secure strings. |
| `Get-CmsMessage` | Gets content that has been encrypted by using the Cryptographic Message Syntax format. |
| `Get-Credential` | Gets a credential object based on a user name and password. |
| `Get-ExecutionPolicy` | Gets the execution policies for the current session. |
| `Get-PfxCertificate` | Gets information about PFX certificate files on the computer. |
| `Protect-CmsMessage` | Encrypts content by using the Cryptographic Message Syntax format. |
| `Set-ExecutionPolicy` | Sets the PowerShell execution policies for Windows computers. |
| `Unprotect-CmsMessage` | Decrypts content that has been encrypted by using the Cryptographic Message Syntax format. |

---

### ConvertFrom-SecureString

Converts a secure string to an encrypted standard string.

The `ConvertFrom-SecureString` cmdlet converts a secure string (**System.Security.SecureString**) into an encrypted standard string (**System.String**). Unlike a secure string, an encrypted standard string can be saved in a file for later use. The encrypted standard string can be converted back to its secure string format by using the `ConvertTo-SecureString` cmdlet.

**Returns**: `System.String`

```
ConvertFrom-SecureString
    [-AsPlainText <Object>]
    [-Key <Object>]
    [-SecureKey <Object>]
    -SecureString <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsPlainText` | `Object` | No | When set, `ConvertFrom-SecureString` will convert secure strings to the decrypted plaintext string as output.   This parameter was added in PowerShell 7.0. |
| `-Key` | `Object` | No | Specifies the encryption key as a byte array. |
| `-SecureKey` | `Object` | No | Specifies the encryption key as a secure string. The secure string value is converted to a byte array before being used as the key. |
| `-SecureString` | `Object` | Yes | Specifies the secure string to convert to an encrypted standard string. |

---

### ConvertTo-SecureString

Converts plain text or encrypted strings to secure strings.

The `ConvertTo-SecureString` cmdlet converts encrypted standard strings into secure strings. It can also convert plain text to secure strings. It is used with `ConvertFrom-SecureString` and `Read-Host`. The secure string created by the cmdlet can be used with cmdlets or functions that require a parameter of type **SecureString**. The secure string can be converted back to an encrypted, standard string using the `ConvertFrom-SecureString` cmdlet. This enables it to be stored in a file for late...

**Returns**: `System.Security.SecureString`

```
ConvertTo-SecureString
    [-AsPlainText <Object>]
    [-Force <Object>]
    [-Key <Object>]
    [-SecureKey <Object>]
    -String <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AsPlainText` | `Object` | No | Specifies a plain text string to convert to a secure string. The secure string cmdlets help protect confidential text. The text is encrypted for privacy and is deleted from computer memory after it... |
| `-Force` | `Object` | No | Beginning in PowerShell 7, The **Force** parameter is no longer required when using the **AsPlainText** parameter. While the parameter is not used, it was not removed to provide compatibility with ... |
| `-Key` | `Object` | No | Specifies the encryption key used to convert the original secure string into the encrypted standard string. Valid key lengths are 16, 24 and 32 bytes. |
| `-SecureKey` | `Object` | No | Specifies the encryption key used to convert the original secure string into the encrypted standard string. The key must be provided in the format of a secure string. The secure string will be conv... |
| `-String` | `Object` | Yes | Specifies the string to convert to a secure string. |

---

### Get-CmsMessage

Gets content that has been encrypted by using the Cryptographic Message Syntax format.

The `Get-CmsMessage` cmdlet gets content that has been encrypted using the Cryptographic Message Syntax (CMS) format.

**Returns**: `None documented`

```
Get-CmsMessage
    -Content <Object>
    -LiteralPath <Object>
    -Path <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Content` | `Object` | Yes | Specifies an encrypted string, or a variable containing an encrypted string. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to encrypted content that you want to get. Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcard characters. If ... |
| `-Path` | `Object` | Yes | Specifies the path to encrypted content that you want to decrypt. |

---

### Get-Credential

Gets a credential object based on a user name and password.

The `Get-Credential` cmdlet creates a credential object for a specified user name and password. You can use the credential object in security operations.

**Returns**: `System.Management.Automation.PSCredential`

```
Get-Credential
    [-Credential <Object>]
    [-Message <Object>]
    [-Title <Object>]
    [-UserName <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Credential` | `Object` | No | Specifies a user name for the credential, such as **User01** or **Domain01\User01**. The parameter name, `-Credential`, is optional.   When you submit the command and specify a user name, you're pr... |
| `-Message` | `Object` | No | Specifies a message that appears in the authentication prompt. This parameter is designed for use in a function or script. You can use the message to explain to the user why you are requesting cred... |
| `-Title` | `Object` | No | Sets the text of the title line for the authentication prompt in the console.   This parameter was introduced in PowerShell 6.0. |
| `-UserName` | `Object` | No | Specifies a user name. The authentication prompt requests a password for the user name. By default, the user name is blank and the authentication prompt requests both a user name and password.   Th... |

---

### Get-ExecutionPolicy

Gets the execution policies for the current session.

To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`. To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.

**Returns**: `Microsoft.PowerShell.ExecutionPolicy`

```
Get-ExecutionPolicy
    [-List <Object>]
    [-Scope <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-List` | `Object` | No | Gets all execution policy values for the session. By default, `Get-ExecutionPolicy` gets only the effective execution policy. |
| `-Scope` | `Object` | No | Specifies the scope that is affected by an execution policy.   The effective execution policy is determined by the order of precedence as follows:   - `MachinePolicy`. Set by a Group Policy for all... |

---

### Get-PfxCertificate

Gets information about PFX certificate files on the computer.

The `Get-PfxCertificate` cmdlet gets an object representing each specified PFX certificate file. A PFX file includes both the certificate and a private key.

**Returns**: `System.Security.Cryptography.X509Certificates.X509Certificate2`

```
Get-PfxCertificate
    -FilePath <Object>
    -LiteralPath <Object>
    [-NoPromptForPassword <Object>]
    [-Password <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-FilePath` | `Object` | Yes | Specifies the full path to the PFX file of the secured file. If you specify a value for this parameter, it is not necessary to type `-FilePath` at the command line. |
| `-LiteralPath` | `Object` | Yes | The full path to the PFX file of the secured file. Unlike **FilePath**, the value of the **LiteralPath** parameter is used exactly as it is typed. No characters are interpreted as wildcards. If the... |
| `-NoPromptForPassword` | `Object` | No | Suppresses prompting for a password. |
| `-Password` | `Object` | No | Specifies a password required to access a `.pfx` certificate file.   This parameter was introduced in PowerShell 6.1.   > [!NOTE] > For more information about **SecureString** data protection, see ... |

---

### Protect-CmsMessage

Encrypts content by using the Cryptographic Message Syntax format.

The `Protect-CmsMessage` cmdlet encrypts content by using the Cryptographic Message Syntax (CMS) format.

**Returns**: `None documented`

```
Protect-CmsMessage
    -Content <Object>
    -LiteralPath <Object>
    [-OutFile <Object>]
    -Path <Object>
    -To <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Content` | `Object` | Yes | Specifies a **PSObject** that contains content that you want to encrypt. For example, you can encrypt the content of an event message, and then use the variable containing the message (`$Event`, in... |
| `-LiteralPath` | `Object` | Yes | Specifies the path to content that you want to encrypt. Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed. No characters are interpreted as wildcards. If the path include... |
| `-OutFile` | `Object` | No | Specifies the path and file name of a file to which you want to send the encrypted content. |
| `-Path` | `Object` | Yes | Specifies the path to content that you want to encrypt. |
| `-To` | `Object` | Yes | Specifies one or more CMS message recipients, identified in any of the following formats:   - An actual certificate (as retrieved from the Certificate provider). - Path to the file containing the c... |

---

### Set-ExecutionPolicy

Sets the PowerShell execution policies for Windows computers.

The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers. For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).

**Returns**: `None`

```
Set-ExecutionPolicy
    [-Confirm <Object>]
    -ExecutionPolicy <Object>
    [-Force <Object>]
    [-Scope <Object>]
    [-WhatIf <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Confirm` | `Object` | No | Prompts you for confirmation before running the cmdlet. |
| `-ExecutionPolicy` | `Object` | Yes | Specifies the execution policy. If there are no Group Policies and each scope's execution policy is set to `Undefined`, then `Restricted` becomes the effective policy for all users.   The acceptabl... |
| `-Force` | `Object` | No | Suppresses all the confirmation prompts. Use caution with this parameter to avoid unexpected results. |
| `-Scope` | `Object` | No | Specifies the scope that is affected by an execution policy. The default scope is `LocalMachine`.   The effective execution policy is determined by the order of precedence as follows:   - `MachineP... |
| `-WhatIf` | `Object` | No | Shows what would happen if the cmdlet runs. The cmdlet is not run. |

---

### Unprotect-CmsMessage

Decrypts content that has been encrypted by using the Cryptographic Message Syntax format.

The `Unprotect-CmsMessage` cmdlet decrypts content that has been encrypted using the Cryptographic Message Syntax (CMS) format.

**Returns**: `System.String`

```
Unprotect-CmsMessage
    -Content <Object>
    -EventLogRecord <Object>
    [-IncludeContext <Object>]
    -LiteralPath <Object>
    -Path <Object>
    [-To <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Content` | `Object` | Yes | Specifies an encrypted string, or a variable containing an encrypted string. |
| `-EventLogRecord` | `Object` | Yes | Specifies an event log record that contains a CMS encrypted message. |
| `-IncludeContext` | `Object` | No | Determines whether to include the decrypted content in its original context, rather than output the decrypted content only. |
| `-LiteralPath` | `Object` | Yes | Specifies the path to encrypted content that you want to decrypt. Unlike **Path**, the value of **LiteralPath** is used exactly as it's typed. No characters are interpreted as wildcard characters. ... |
| `-Path` | `Object` | Yes | Specifies the path to encrypted content that you want to decrypt. |
| `-To` | `Object` | No | Specifies one or more CMS message recipients, identified in any of the following formats:   - An actual certificate (as retrieved from the Certificate provider). - Path to the a file containing the... |

---

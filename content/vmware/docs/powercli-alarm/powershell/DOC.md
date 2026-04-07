---
name: powercli-alarm
description: "VMware PowerCLI 13.3 — alarm management: definitions, actions, triggers"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Get-AlarmAction,Get-AlarmActionTrigger,Get-AlarmDefinition,Get-AlarmTrigger,Get-AlarmTriggerArgumentAttributeName,New-AlarmAction,New-AlarmActionTrigger,New-AlarmDefinition,New-AlarmTrigger,New-AlarmTriggerArgument,Remove-AlarmAction,Remove-AlarmActionTrigger,Remove-AlarmDefinition,Set-AlarmDefinition"
---

# VMware PowerCLI — alarm management

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Get-AlarmAction` | This cmdlet retrieves the actions of the specified alarm definitions. |
| `Get-AlarmActionTrigger` | This cmdlet retrieves the actions that trigger the specified alarm actions. |
| `Get-AlarmDefinition` | This cmdlet retrieves the available alarm definitions. |
| `Get-AlarmTrigger` | This cmdlet retrieves alarms triggers. |
| `Get-AlarmTriggerArgumentAttributeName` | This cmdlet fetches a list of attribute names of the alarm trigger argument for the "vsan.health.... |
| `New-AlarmAction` | This cmdlet creates an alarm action and attaches it to the specified alarm. |
| `New-AlarmActionTrigger` | This cmdlet creates a new action trigger for the specified alarm action. |
| `New-AlarmDefinition` | This cmdlet creates a new alarm definition. |
| `New-AlarmTrigger` | This cmdlet adds ? new alarm trigger to the existing alarm or creates ? new alarm trigger. |
| `New-AlarmTriggerArgument` | This cmdlet creates a new AlarmTriggerArgument local object that defines the condition comparison... |
| `Remove-AlarmAction` | This cmdlet removes an alarm action. |
| `Remove-AlarmActionTrigger` | This cmdlet removes the alarm action triggers. |
| `Remove-AlarmDefinition` | This cmdlet removes alarm definitions from the vSphere environment. |
| `Set-AlarmDefinition` | This cmdlet modifies the specified alarm definitions. |

---

### Get-AlarmAction

This cmdlet retrieves the actions of the specified alarm definitions.

**Returns**: `AlarmAction`

```
Get-AlarmAction
    [-ActionType <ActionType[]>]
    [-AlarmDefinition <AlarmDefinition[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ActionType` | `ActionType[]` | No | Specifies the type of the alarm actions you want to retrieve. The valid values are SendEmail, ExecuteScript, and Send SNMP. |
| `-AlarmDefinition` | `AlarmDefinition[]` | No | Specifies the alarm definitions for which you want to retrieve the configured actions. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-AlarmActionTrigger

This cmdlet retrieves the actions that trigger the specified alarm actions.

**Returns**: `AlarmActionTrigger`

```
Get-AlarmActionTrigger
    [-AlarmAction <AlarmAction[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmAction` | `AlarmAction[]` | No | Filters the trigger actions by the alarm actions they trigger. |

---

### Get-AlarmDefinition

This cmdlet retrieves the available alarm definitions.

**Returns**: `AlarmDefinition`

```
Get-AlarmDefinition
    [-Enabled <Boolean>]
    [-Entity <VIObject[]>]
    [-Id <String[]>]
    [-Name <String[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Enabled` | `Boolean` | No | Indicates that you want to retrieve only the enabled alarm definitions. |
| `-Entity` | `VIObject[]` | No | Filters the alarm definitions by the entities to which they are defined. This parameter accepts InventoryItem, Datastore, and DatastoreCluster objects. |
| `-Id` | `String[]` | No | Specifies the IDs of the alarms you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string v... |
| `-Name` | `String[]` | No | Specifies the names of the alarms you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-AlarmTrigger

This cmdlet retrieves alarms triggers.

This cmdlet retrieves alarms triggers. The cmdlet returns a set of triggers that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Alarm.AlarmTrigger`

```
Get-AlarmTrigger
    -AlarmDefinition <AlarmDefinition[]>
    [-TriggerType <TriggerType>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmDefinition` | `AlarmDefinition[]` | Yes | Specifies the alarm definitions for which you want to retrieve the triggers. The alarm name could be passed. |
| `-TriggerType` | `TriggerType` | No | Specifies the type of the trigger that you want to retrieve. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-AlarmTriggerArgumentAttributeName

This cmdlet fetches a list of attribute names of the alarm trigger argument for the "vsan.health.ssd.endurance" event type. (The most of attribute names for alarm trigger argument can be fetched by Get-EventType)

**Returns**: `A list of attribute names.`

```
Get-AlarmTriggerArgumentAttributeName
```

---

### New-AlarmAction

This cmdlet creates an alarm action and attaches it to the specified alarm.

This cmdlet creates an alarm action or attaches an alarm action to the specified alarm.

**Returns**: `AlarmAction`

```
New-AlarmAction
    [-AlarmDefinition <AlarmDefinition>]
    [-AlarmActionTrigger <AlarmActionTrigger>]
    [-Body <String>]
    [-Cc <String[]>]
    -Email
    -Script
    -ScriptPath <String>
    [-Server <VIServer[]>]
    -Snmp
    [-Subject <String>]
    -To <String[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmDefinition` | `AlarmDefinition` | No | Specifies the alarm definition for which you want to configure actions. |
| `-AlarmActionTrigger` | `AlarmActionTrigger` | No | Specifies the alarm action trigger. If it is not specified, a default action trigger is created with a Yellow start value and a Red end value. |
| `-Body` | `String` | No | Specifies the text of the email message. |
| `-Cc` | `String[]` | No | Specifies the email addresses you want to add to the CC field of the email message. |
| `-Email` | `SwitchParameter` | Yes | Indicates that when the alarm is activated, the system sends an email message to the specified address. Use the Subject, To, CC, and Body parameters to customize the alarm message. |
| `-Script` | `SwitchParameter` | Yes | Indicates that a script is run when the alarm is activated. |
| `-ScriptPath` | `String` | Yes | Specifies the path to a batch file, located on a vCenter Server system, that will run when the alarm is activated. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Snmp` | `SwitchParameter` | Yes | Indicates that a SNMP message is sent when the alarm is activated. |
| `-Subject` | `String` | No | Specifies a subject for the email message you want to send. |
| `-To` | `String[]` | Yes | Specifies the email address to which you want to send a message. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-AlarmActionTrigger

This cmdlet creates a new action trigger for the specified alarm action.

This cmdlet creates a new action trigger or adds a new action trigger to the specified alarm action.

**Returns**: `AlarmActionTrigger`

```
New-AlarmActionTrigger
    [-AlarmAction <AlarmAction>]
    -EndStatus <InventoryItemStatus>
    [-Repeat]
    -StartStatus <InventoryItemStatus>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmAction` | `AlarmAction` | No | Specifies the alarm action for which you want to create an action trigger. |
| `-EndStatus` | `InventoryItemStatus` | Yes | Specifies the end status for the alarm action. The valid values are Green, Yellow, and Red. |
| `-Repeat` | `SwitchParameter` | No | Indicates whether you want the alarm action to repeat until the alarm is acknowledged. |
| `-StartStatus` | `InventoryItemStatus` | Yes | Specifies the start status for the alarm action. The valid values are Green, Yellow, and Red. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-AlarmDefinition

This cmdlet creates a new alarm definition.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Alarm.AlarmDefinition`

```
New-AlarmDefinition
    [-ActionRepeatMinutes <Int32>]
    [-AlarmAction <AlarmAction[]>]
    -AlarmTrigger <AlarmTrigger[]>
    [-Description <String>]
    [-Disabled]
    -Entity <VIObject>
    -Name <String>
    [-ReportingFrequencyMinutes <Int32>]
    [-ReportingTolerancePercentage <Int32>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ActionRepeatMinutes` | `Int32` | No | Specifies the frequency in minutes. This indicates how often appropriate actions should be repeated when an alarm does not change its state. |
| `-AlarmAction` | `AlarmAction[]` | No | Specifies the alarm actions which you want to be executed when the alarm triggers. |
| `-AlarmTrigger` | `AlarmTrigger[]` | Yes | Specifies the alarm triggers which you can use to activate the alarm. |
| `-Description` | `String` | No | Specifies the alarm description. |
| `-Disabled` | `SwitchParameter` | No | Specifies if the alarm is deactivated. By default, the alarm is activated. |
| `-Entity` | `VIObject` | Yes | Specifies the entity to which you want to attach the alarm. If you want to specify the root, use the data centers. |
| `-Name` | `String` | Yes | Specifies the alarm name. |
| `-ReportingFrequencyMinutes` | `Int32` | No | Indicates how often you want to trigger the alarm. It is measured in minutes. |
| `-ReportingTolerancePercentage` | `Int32` | No | Indicates the tolerance range for the metric triggers. It is measured in percentage. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### New-AlarmTrigger

This cmdlet adds ? new alarm trigger to the existing alarm or creates ? new alarm trigger.

This cmdlet adds an alarm trigger to the existing alarm or creates a new alarm trigger. The newly added or created triggers could be Event, Metric, and State. The cmdlet returns the added or created trigger. To specify a server that is different from the default one, use the Server parameter.

**Returns**: `VMware.VimAutomation.ViCore.Types.V1.Alarm.AlarmTrigger`

```
New-AlarmTrigger
    -AlarmDefinition <AlarmDefinition[]>
    [-Confirm]
    [-EntityStatus <EntityStatus>]
    -EntityType <String>
    [-Argument <AlarmTriggerArgument[]>]
    -EventType <EventType>
    -Metric <Metric>
    -MetricAlarmOperator <MetricAlarmOperator>
    [-Red <Int32>]
    [-RedIntervalSeconds <Int32>]
    [-Server <VIServer[]>]
    -StateAlarmOperator <StateAlarmOperator>
    -StatePath <String>
    -Value <String>
    [-WhatIf]
    [-Yellow <Int32>]
    [-YellowIntervalSeconds <Int32>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmDefinition` | `AlarmDefinition[]` | Yes | Specifies the existing alarm to which you want to add the trigger. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-EntityStatus` | `EntityStatus` | No | Specifies the trigger status. The allowed values for the Metric and State triggers are Red and Yellow. |
| `-EntityType` | `String` | Yes | Specifies the type of object on which the event occurs, its containing state or metric. ?he valid PowerCLI type names are Cluster, Datacenter, Datastore, DistributedSwitch, VMHost, VirtualPortGroup... |
| `-Argument` | `AlarmTriggerArgument[]` | No | Specifies the arguments on which the event occurs, including condition comparisons. ?he valid values are fetched by New-AlarmTriggerArgument. |
| `-EventType` | `EventType` | Yes | Specifies the event to trigger. You can find the event types by using the Get-EventType cmdlet. |
| `-Metric` | `Metric` | Yes | Specifies the metric to trigger on. You can find the metrics by using the Get-Metric cmdlet. |
| `-MetricAlarmOperator` | `MetricAlarmOperator` | Yes | Specifies the operation of the target metric. |
| `-Red` | `Int32` | No | Specifies the threshold value that triggers a red status. |
| `-RedIntervalSeconds` | `Int32` | No | Specifies the time interval for which the red condition must be true before the red status is triggered. If unset, the red status is triggered immediately when the red condition becomes true. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StateAlarmOperator` | `StateAlarmOperator` | Yes | Specifies the operation of the target state. |
| `-StatePath` | `String` | Yes | Specifies the path of the state property. Supported values for the VirtualMachine type: runtime.powerState, summary.quickStats.guestHeartbeatStatus. Supported values for the VMHost type: runtime.co... |
| `-Value` | `String` | Yes | Specifies the condition of the state path. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |
| `-Yellow` | `Int32` | No | Specifies the threshold value that triggers a yellow status. |
| `-YellowIntervalSeconds` | `Int32` | No | Specifies the time interval for which the yellow condition must be true before the yellow status is triggered. If unset, the yellow status is triggered immediately when the yellow condition becomes... |

---

### New-AlarmTriggerArgument

This cmdlet creates a new AlarmTriggerArgument local object that defines the condition comparison under which an alarm is triggered. The AlarmTriggerArgument object is used as the Arguments parameter in the New-AlarmTrigger cmdlet.

**Returns**: `AlarmTriggerArgument`

```
New-AlarmTriggerArgument
    -AttributeName <String>
    -Operator <AlarmTriggerArgumentOperatorType>
    -Value <String>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AttributeName` | `String` | Yes | Specifies the attribute name in the expression comparison. You can fetch the valid attribute names for the "vsan.health.ssd.endurance" event type by using the New-AlarmTriggerArgumentAttributeName ... |
| `-Operator` | `AlarmTriggerArgumentOperatorType` | Yes | Specifies the operator in the comparison expression. The valid values are equals, notEqualTo, startsWith, doesNotStartWith, endsWith, doesNotEndWith. |
| `-Value` | `String` | Yes | Specifies the value in the comparison expression. |

---

### Remove-AlarmAction

This cmdlet removes an alarm action.

**Returns**: `None`

```
Remove-AlarmAction
    -AlarmAction <AlarmAction[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmAction` | `AlarmAction[]` | Yes | Specifies the alarm actions you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-AlarmActionTrigger

This cmdlet removes the alarm action triggers.

This cmdlet removes the selected alarm action triggers.

**Returns**: `None`

```
Remove-AlarmActionTrigger
    -AlarmActionTrigger <AlarmActionTrigger[]>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmActionTrigger` | `AlarmActionTrigger[]` | Yes | Specifies the alarm action triggers you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-AlarmDefinition

This cmdlet removes alarm definitions from the vSphere environment.

**Returns**: `None`

```
Remove-AlarmDefinition
    -AlarmDefinition <AlarmDefinition[]>
    [-Confirm]
    [-Server <VIServer[]>]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-AlarmDefinition` | `AlarmDefinition[]` | Yes | Specifies the alarm definitions that you want to remove. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-AlarmDefinition

This cmdlet modifies the specified alarm definitions.

**Returns**: `AlarmDefinition`

```
Set-AlarmDefinition
    [-ActionRepeatMinutes <Int32>]
    -AlarmDefinition <AlarmDefinition[]>
    [-Description <String>]
    [-Enabled <Boolean>]
    [-Name <String>]
    [-AlarmAction <AlarmAction[]>]
    [-AlarmTrigger <AlarmTrigger[]>]
    [-ReportingFrequencyMinutes <Int32>]
    [-ReportingTolerancePercentage <Int32>]
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ActionRepeatMinutes` | `Int32` | No | Specifies a time period in minutes to define how often the alarm action repeats if the alarm is active. |
| `-AlarmDefinition` | `AlarmDefinition[]` | Yes | Specifies the alarm definition you want to modify. |
| `-Description` | `String` | No | Specifies a new description for the alarm definition. |
| `-Enabled` | `Boolean` | No | Indicates that the alarm definition is enabled. |
| `-Name` | `String` | No | Specifies a new name for the alarm definition. |
| `-AlarmAction` | `AlarmAction[]` | No | Specifies the alarm actions which you want to be executed when the alarm triggers. |
| `-AlarmTrigger` | `AlarmTrigger[]` | No | Specifies the alarm triggers which you can use to activate the alarm. |
| `-ReportingFrequencyMinutes` | `Int32` | No | Indicates how often you want to trigger the alarm. It is measured in minutes. |
| `-ReportingTolerancePercentage` | `Int32` | No | Indicates the tolerance range for the metric triggers. It is measured in percentage. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

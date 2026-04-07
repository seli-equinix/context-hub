---
name: powercli-alarms
description: "VMware PowerCLI 13.3 — Alarm definitions, triggers, actions for vCenter monitoring"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,alarms,Get-AlarmAction, Get-AlarmActionTrigger, Get-AlarmDefinition, Get-AlarmTrigger, Get-AlarmTriggerArgumentAttributeName, New-AlarmAction, New-AlarmActionTrigger, New-AlarmDefinition, New-AlarmTrigger, New-AlarmTriggerArgument, Remove-AlarmAction, Remove-AlarmActionTrigger, Remove-AlarmDefinition, Set-AlarmDefinition"
---

# VMware PowerCLI — Alarms

Alarm definitions, triggers, actions for vCenter monitoring. Module: VMware.VimAutomation (14 cmdlets).

## Get

### `Get-AlarmAction`

**This cmdlet retrieves the actions of the specified alarm definitions.**

**Parameters:**

- -ActionType [ActionType[]] (Optional) Specifies the type of the alarm actions you want to retrieve. The valid values are SendEmail, ExecuteScript, and Send SNMP.
- -AlarmDefinition [AlarmDefinition[]] (Optional) Specifies the alarm definitions for which you want to retrieve the configured actions.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-AlarmDefinition -Name "Host processor status" | Get-AlarmAction -ActionType "ExecuteScript", "SendSNMP", "SendEmail"
```
_Extract all PowerCLI supported alarm actions for the default alarm "Host processor status"._

```powershell
Get-AlarmAction -AlarmDefinition "Host processor status" -ActionType "SendSNMP" -Server 'server IP'
```
_Extract the alarm actions for the default alarm "Host processor status" by specifying the alarm by name._

### `Get-AlarmActionTrigger`

**This cmdlet retrieves the actions that trigger the specified alarm actions.**

**Parameters:**

- -AlarmAction [AlarmAction[]] (Optional) Filters the trigger actions by the alarm actions they trigger.

**Examples:**

```powershell
Get-AlarmAction -AlarmDefinition (Get-AlarmDefinition | select -First 1) | Get-AlarmActionTrigger
```
_Retrieves the action triggers for the actions of the first returned alarm._

### `Get-AlarmDefinition`

**This cmdlet retrieves the available alarm definitions.**

**Parameters:**

- -Enabled [Boolean] (Optional) Indicates that you want to retrieve only the enabled alarm definitions.
- -Entity [VIObject[]] (Optional) Filters the alarm definitions by the entities to which they are defined. This parameter accepts InventoryItem, Datastore, and DatastoreCluster objects.
- -Id [String[]] (Optional) Specifies the IDs of the alarms you want to retrieve.   Note: When a list of values is specified for the Id parameter, the returned objects would have an ID that matches exactly one of the string values in that list.
- -Name [String[]] (Optional) Specifies the names of the alarms you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-AlarmDefinition -Entity (Get-Folder -NoRecursion) -Name "Host connection and power state" -Enabled:$true
```
_Retrieve the enabled alarms named "Host connection and power state" for the available folders._

```powershell
Get-AlarmDefinition -Server Server1, Server2
```
_Retrieves the alarms for the specified servers._

### `Get-AlarmTrigger`

**This cmdlet retrieves alarms triggers.**

This cmdlet retrieves alarms triggers. The cmdlet returns a set of triggers that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -AlarmDefinition [AlarmDefinition[]] (Required) Specifies the alarm definitions for which you want to retrieve the triggers. The alarm name could be passed.
- -TriggerType [TriggerType] (Optional) Specifies the type of the trigger that you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-AlarmTrigger -AlarmDefinition $alarm
```
_Retrieves all alarm triggers._

```powershell
Get-AlarmTrigger -AlarmDefinition $alarm -TriggerType Event
```
_Retrieves alarm triggers of type Event._

### `Get-AlarmTriggerArgumentAttributeName`

**This cmdlet fetches a list of attribute names of the alarm trigger argument for the "vsan.health.ssd.endurance" event type. (The most of attribute names for alarm trigger argument can be fetched by Get-EventType)**

**Examples:**

```powershell
Get-AlarmTriggerArgumentAttributeName
Disk Name
Disk Percentage Used
Disk Percentage Threshold
Cluster Name
Disk Vendor Name
```
_Fetches the list of attribute names of the alarm trigger argument for the "vsan.health.ssd.endurance" event type._

## New

### `New-AlarmAction`

**This cmdlet creates an alarm action and attaches it to the specified alarm.**

This cmdlet creates an alarm action or attaches an alarm action to the specified alarm.

**Parameters:**

- -AlarmDefinition [AlarmDefinition] (Optional) Specifies the alarm definition for which you want to configure actions.
- -AlarmActionTrigger [AlarmActionTrigger] (Optional) Specifies the alarm action trigger. If it is not specified, a default action trigger is created with a Yellow start value and a Red end value.
- -Body [String] (Optional) Specifies the text of the email message.
- -Cc [String[]] (Optional) Specifies the email addresses you want to add to the CC field of the email message.
- -Email [SwitchParameter] (Required) Indicates that when the alarm is activated, the system sends an email message to the specified address. Use the Subject, To, CC, and Body parameters to customize the alarm message.
- -Script [SwitchParameter] (Required) Indicates that a script is run when the alarm is activated.
- -ScriptPath [String] (Required) Specifies the path to a batch file, located on a vCenter Server system, that will run when the alarm is activated.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -Snmp [SwitchParameter] (Required) Indicates that a SNMP message is sent when the alarm is activated.
- -Subject [String] (Optional) Specifies a subject for the email message you want to send.
- -To [String[]] (Required) Specifies the email address to which you want to send a message.

**Examples:**

```powershell
Get-AlarmDefinition -Name "Alarm1" | New-AlarmAction -Snmp
```
_Creates an alarm action SNMP and attaches it to the specified alarm._

```powershell
New-AlarmAction -Snmp
```
_Creates an alarm action SNMP._

```powershell
Get-AlarmDefinition -Name "Alarm1" | New-AlarmAction -Script -ScriptPath 'c:\test.bat'
```
_Creates an alarm action script and attaches it to the specified alarm._

### `New-AlarmActionTrigger`

**This cmdlet creates a new action trigger for the specified alarm action.**

This cmdlet creates a new action trigger or adds a new action trigger to the specified alarm action.

**Parameters:**

- -AlarmAction [AlarmAction] (Optional) Specifies the alarm action for which you want to create an action trigger.
- -EndStatus [InventoryItemStatus] (Required) Specifies the end status for the alarm action. The valid values are Green, Yellow, and Red.
- -Repeat [SwitchParameter] (Optional) Indicates whether you want the alarm action to repeat until the alarm is acknowledged.
- -StartStatus [InventoryItemStatus] (Required) Specifies the start status for the alarm action. The valid values are Green, Yellow, and Red.

**Examples:**

```powershell
Get-AlarmDefinition -Name "Alarm1" | Get-AlarmAction | New-AlarmActionTrigger -StartStatus 'Red' -EndStatus 'Yellow' -Repeat
```
_Creates an action trigger for all actions for the specified alarm definition._

```powershell
New-AlarmActionTrigger -StartStatus 'Red' -EndStatus 'Yellow' -Repeat
```
_Creates an action trigger._

### `New-AlarmDefinition`

**This cmdlet creates a new alarm definition.**

**Parameters:**

- -ActionRepeatMinutes [Int32] (Optional) Specifies the frequency in minutes. This indicates how often appropriate actions should be repeated when an alarm does not change its state.
- -AlarmAction [AlarmAction[]] (Optional) Specifies the alarm actions which you want to be executed when the alarm triggers.
- -AlarmTrigger [AlarmTrigger[]] (Required) Specifies the alarm triggers which you can use to activate the alarm.
- -Description [String] (Optional) Specifies the alarm description.
- -Disabled [SwitchParameter] (Optional) Specifies if the alarm is deactivated. By default, the alarm is activated.
- -Entity [VIObject] (Required) Specifies the entity to which you want to attach the alarm. If you want to specify the root, use the data centers.
- -Name [String] (Required) Specifies the alarm name.
- -ReportingFrequencyMinutes [Int32] (Optional) Indicates how often you want to trigger the alarm. It is measured in minutes.
- -ReportingTolerancePercentage [Int32] (Optional) Indicates the tolerance range for the metric triggers. It is measured in percentage.

**Examples:**

```powershell
New-AlarmDefinition -Name "AlarmName" -AlarmTrigger $alarmTriggers -Entity $entity
```
_Creates an enabled alarm definition with the "AlarmName" name and a collection of $alarmTriggers triggers for the $entity._

```powershell
New-AlarmDefinition -Name "AlarmName" - AlarmTrigger $alarmTriggers -AlarmAction $alarmAction -Entity $entity -Description "alarm definition description" -ActionRepeatMinutes 20 -ReportingFrequencyMinutes 30 -ReportingTolerancePercentage 10 -Disabled
```
_Creates a deactivated alarm definition with the "AlarmName" name, an "alarm definition description" description, and a collection of $alarmTriggers triggers for the $entity. The newly created alarm definition has alarm actions: $alarm Action.  The alarm action repeat minutes are 20, the reporting frequency minutes are 30, and the reporting tolerance range is 10._

### `New-AlarmTrigger`

**This cmdlet adds ? new alarm trigger to the existing alarm or creates ? new alarm trigger.**

This cmdlet adds an alarm trigger to the existing alarm or creates a new alarm trigger. The newly added or created triggers could be Event, Metric, and State. The cmdlet returns the added or created trigger. To specify a server that is different from the default one, use the Server parameter.

**Parameters:**

- -AlarmDefinition [AlarmDefinition[]] (Required) Specifies the existing alarm to which you want to add the trigger.
- -EntityStatus [EntityStatus] (Optional) Specifies the trigger status. The allowed values for the Metric and State triggers are Red and Yellow.
- -EntityType [String] (Required) Specifies the type of object on which the event occurs, its containing state or metric. ?he valid PowerCLI type names are Cluster, Datacenter, Datastore, DistributedSwitch, VMHost, VirtualPortGroup, ResourcePool, VirtualMachine, and so on.
- -Argument [AlarmTriggerArgument[]] (Optional) Specifies the arguments on which the event occurs, including condition comparisons. ?he valid values are fetched by New-AlarmTriggerArgument.
- -EventType [EventType] (Required) Specifies the event to trigger. You can find the event types by using the Get-EventType cmdlet.
- -Metric [Metric] (Required) Specifies the metric to trigger on. You can find the metrics by using the Get-Metric cmdlet.
- -MetricAlarmOperator [MetricAlarmOperator] (Required) Specifies the operation of the target metric.
- -Red [Int32] (Optional) Specifies the threshold value that triggers a red status.
- -RedIntervalSeconds [Int32] (Optional) Specifies the time interval for which the red condition must be true before the red status is triggered. If unset, the red status is triggered immediately when the red condition becomes true.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.
- -StateAlarmOperator [StateAlarmOperator] (Required) Specifies the operation of the target state.
- -StatePath [String] (Required) Specifies the path of the state property. Supported values for the VirtualMachine type: runtime.powerState, summary.quickStats.guestHeartbeatStatus. Supported values for the VMHost type: runtime.connectionState. And so on.
- -Value [String] (Required) Specifies the condition of the state path.
- -Yellow [Int32] (Optional) Specifies the threshold value that triggers a yellow status.
- -YellowIntervalSeconds [Int32] (Optional) Specifies the time interval for which the yellow condition must be true before the yellow status is triggered. If unset, the yellow status is triggered immediately when the yellow condition becomes true.

**Examples:**

```powershell
New-AlarmTrigger  -EventType $eventType -EntityStatus Red -AlarmDefinition $alarm -EntityType "VirtualMachine"
```
_Adds a new event trigger from the $eventType event type to the existing $alarm alarm with status Red to the VirtualMachine entity._

```powershell
New-AlarmTrigger  -EventType $eventType -EntityStatus Red  -EntityType "VirtualMachine"
```
_Creates a new event trigger from the $eventType event type with status Red with the VirtualMachine entity._

```powershell
New-AlarmTrigger  -AlarmDefinition $alarm -Metric $metric -MetricAlarmOperator Above -Red 3200 -RedIntervalSeconds 900 -EntityType "VirtualMachine"
```
_Adds a new metric trigger with a $metric metric and an Above operator for the VirtualMachine entity to the $alarm alarm. The threshold value that triggers a red status is 3200. The time interval for which the red condition must be true before the red status is triggered is 900._

### `New-AlarmTriggerArgument`

**This cmdlet creates a new AlarmTriggerArgument local object that defines the condition comparison under which an alarm is triggered. The AlarmTriggerArgument object is used as the Arguments parameter in the New-AlarmTrigger cmdlet.**

**Parameters:**

- -AttributeName [String] (Required) Specifies the attribute name in the expression comparison. You can fetch the valid attribute names for the "vsan.health.ssd.endurance" event type by using the New-AlarmTriggerArgumentAttributeName cmdlet.
- -Operator [AlarmTriggerArgumentOperatorType] (Required) Specifies the operator in the comparison expression. The valid values are equals, notEqualTo, startsWith, doesNotStartWith, endsWith, doesNotEndWith.
- -Value [String] (Required) Specifies the value in the comparison expression.

**Examples:**

```powershell
$argument = New-AlarmTriggerArgument -AttributeName "Cluster Name" -Operator "equals" -Value "vSAN-ESA-Cluster"
```
_Creates a local AlarmTriggerArgument object with the Cluster Name attribute equal to "vSAN-ESA-Cluster"._

```powershell
New-AlarmTriggerArgument

cmdlet New-AlarmTriggerArgument at command pipeline position 1
Supply values for the following parameters:
AttributeName: host.name
Operator: equals
Value: "host-123"
```
_Creates a local AlarmTriggerArgument object with a host name equal to "host-123"._

## Remove

### `Remove-AlarmAction`

**This cmdlet removes an alarm action.**

**Parameters:**

- -AlarmAction [AlarmAction[]] (Required) Specifies the alarm actions you want to remove.

**Examples:**

```powershell
Get-AlarmDefinition -Name "Alarm1" | Get-AlarmAction | Remove-AlarmAction -Confirm:$false
```
_Removes all actions for an alarm definition._

### `Remove-AlarmActionTrigger`

**This cmdlet removes the alarm action triggers.**

This cmdlet removes the selected alarm action triggers.

**Parameters:**

- -AlarmActionTrigger [AlarmActionTrigger[]] (Required) Specifies the alarm action triggers you want to remove.

**Examples:**

```powershell
Get-AlarmDefinition -Name "Alarm1" | Get-AlarmAction | Get-AlarmActionTrigger | select -First 1 | Remove-AlarmActionTrigger -Confirm:$false
```
_Removes the first action trigger found for an alarm definition._

### `Remove-AlarmDefinition`

**This cmdlet removes alarm definitions from the vSphere environment.**

**Parameters:**

- -AlarmDefinition [AlarmDefinition[]] (Required) Specifies the alarm definitions that you want to remove.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-AlarmDefinition -Name "MyAlarm" | Remove-AlarmDefinition
```
_Removes the alarm with a name "MyAlarm"._

```powershell
Remove-AlarmDefinition -AlarmDefinition "MyAlarm*"
```
_Removes all alarms that match the pattern._

## Set

### `Set-AlarmDefinition`

**This cmdlet modifies the specified alarm definitions.**

**Parameters:**

- -ActionRepeatMinutes [Int32] (Optional) Specifies a time period in minutes to define how often the alarm action repeats if the alarm is active.
- -AlarmDefinition [AlarmDefinition[]] (Required) Specifies the alarm definition you want to modify.
- -Description [String] (Optional) Specifies a new description for the alarm definition.
- -Enabled [Boolean] (Optional) Indicates that the alarm definition is enabled.
- -Name [String] (Optional) Specifies a new name for the alarm definition.
- -AlarmAction [AlarmAction[]] (Optional) Specifies the alarm actions which you want to be executed when the alarm triggers.
- -AlarmTrigger [AlarmTrigger[]] (Optional) Specifies the alarm triggers which you can use to activate the alarm.
- -ReportingFrequencyMinutes [Int32] (Optional) Indicates how often you want to trigger the alarm. It is measured in minutes.
- -ReportingTolerancePercentage [Int32] (Optional) Indicates the tolerance range for the metric triggers. It is measured in percentage.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-AlarmDefinition -Name 'alarms' | Set-AlarmDefinition -ActionRepeatMinutes ($_.ActionRepeatMinutes + 1)
```
_Increases all selected alarms action repeat minutes._

```powershell
Get-AlarmDefinition -Name 'alarm' | foreach {$_ | Set-AlarmDefinition -Name 'alarm new name' -Description 'new description' -Enabled:$true}
```
_Changes the name, description, and the Enabled flag of the selected alarms._

```powershell
$trigger = New-AlarmTrigger -StatePath "runtime.powerState" -Value "poweredOff" -EntityStatus Red -EntityType "VirtualMachine" -StateAlarmOperator Equal

$action = New-AlarmAction -Snmp

Get-AlarmDefinition -Name 'alarm' | Set-AlarmDefinition -Trigger $trigger -Action $action -ReportingFrequencyMinutes 20 -ReportingTolerancePercentage 10
```
_Changes the triggers, actions, reporting frequency minutes, and reporting tolerance percentage of the selected alarm._

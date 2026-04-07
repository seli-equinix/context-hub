---
name: powercli-alarms
description: "VMware PowerCLI 13.3 — Alarm definitions, triggers, actions for vCenter monitoring"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,alarms,Get-AlarmAction, Get-AlarmActionTrigger, Get-AlarmDefinition, Get-AlarmTrigger, Get-AlarmTriggerArgumentAttributeName, New-AlarmAction, New-AlarmActionTrigger, New-AlarmDefinition, New-AlarmTrigger, New-AlarmTriggerArgument, Remove-AlarmAction, Remove-AlarmActionTrigger, Remove-AlarmDefinition, Set-AlarmDefinition"
---

# VMware PowerCLI — Alarms

Alarm definitions, triggers, actions for vCenter monitoring. Module: VMware.VimAutomation (14 cmdlets).

## Cmdlet Reference (14 cmdlets)

### Get

#### `Get-AlarmAction`

This cmdlet retrieves the actions of the specified alarm definitions.

**Parameters**: `AlarmDefinition, ActionType, Server`

#### `Get-AlarmActionTrigger`

This cmdlet retrieves the actions that trigger the specified alarm actions.

**Parameters**: `AlarmAction`

#### `Get-AlarmDefinition`

This cmdlet retrieves the available alarm definitions.

**Parameters**: `Id, Name, Entity, Enabled, Server`

#### `Get-AlarmTrigger`

This cmdlet retrieves alarms triggers.

**Parameters**: `TriggerType, AlarmDefinition, Server`

#### `Get-AlarmTriggerArgumentAttributeName`

This cmdlet fetches a list of attribute names of the alarm trigger argument for the "vsan.health.ssd.endurance" event type. (The most of attribute names for alarm trigger argument can be fetched by Get-EventType)

**Parameters**: None

### New

#### `New-AlarmAction`

This cmdlet creates an alarm action and attaches it to the specified alarm.

**Parameters**: `AlarmDefinition, Email, Subject, To, Cc, Body, Script, ScriptPath, Snmp, AlarmActionTrigger, Server`

#### `New-AlarmActionTrigger`

This cmdlet creates a new action trigger for the specified alarm action.

**Parameters**: `StartStatus, EndStatus, AlarmAction, Repeat`

#### `New-AlarmDefinition`

This cmdlet creates a new alarm definition.

**Parameters**: `Description, Name, Disabled, AlarmTrigger, ReportingFrequencyMinutes, ReportingTolerancePercentage, ActionRepeatMinutes, Entity, AlarmAction`

#### `New-AlarmTrigger`

This cmdlet adds ? new alarm trigger to the existing alarm or creates ? new alarm trigger.

**Parameters**: `StatePath, Value, EntityStatus, Argument, RedIntervalSeconds, Red, Yellow, YellowIntervalSeconds, EventType, Metric, AlarmDefinition, EntityType` (+3 more)

#### `New-AlarmTriggerArgument`

This cmdlet creates a new AlarmTriggerArgument local object that defines the condition comparison under which an alarm is triggered. The AlarmTriggerArgument object is used as the Arguments parameter in the New-AlarmTrigger cmdlet.

**Parameters**: `AttributeName, Operator, Value`

### Remove

#### `Remove-AlarmAction`

This cmdlet removes an alarm action.

**Parameters**: `AlarmAction`

#### `Remove-AlarmActionTrigger`

This cmdlet removes the alarm action triggers.

**Parameters**: `AlarmActionTrigger`

#### `Remove-AlarmDefinition`

This cmdlet removes alarm definitions from the vSphere environment.

**Parameters**: `AlarmDefinition, Server`

### Set

#### `Set-AlarmDefinition`

This cmdlet modifies the specified alarm definitions.

**Parameters**: `AlarmDefinition, ActionRepeatMinutes, Description, Enabled, Name, ReportingFrequencyMinutes, ReportingTolerancePercentage, AlarmTrigger, AlarmAction, Server`

---
name: powercli-alarms
description: "VMware PowerCLI 13.3 — Alarm definitions, metric/state/event triggers, email/SNMP/script actions for vCenter monitoring"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,alarms,monitoring,triggers,actions,Get-AlarmDefinition,New-AlarmDefinition,Set-AlarmDefinition,Remove-AlarmDefinition,Get-AlarmAction,New-AlarmAction,Remove-AlarmAction,Get-AlarmActionTrigger,New-AlarmActionTrigger,Remove-AlarmActionTrigger,Get-AlarmTrigger,New-AlarmTrigger,New-AlarmTriggerArgument,Get-AlarmTriggerArgumentAttributeName"
---

# VMware PowerCLI — Alarms

## Golden Rule

**Alarms are built from three layers: Definition (the alarm itself), Triggers (what activates it), and Actions (what happens when it fires). You must configure all three layers for an alarm to do anything useful.**

```
AlarmDefinition (name, entity scope, enabled)
  -> AlarmTrigger (metric threshold, state change, or event match)
    -> AlarmAction (email, SNMP, or script)
      -> AlarmActionTrigger (on which state transitions the action fires)
```

| Layer | Cmdlet | Purpose |
|-------|--------|---------|
| Definition | `New-AlarmDefinition` | Creates the alarm and attaches it to an entity |
| Trigger | `New-AlarmTrigger` | Defines WHAT condition activates the alarm (metric, state, event) |
| Action | `New-AlarmAction` | Defines WHAT HAPPENS when triggered (email, SNMP, script) |
| Action Trigger | `New-AlarmActionTrigger` | Defines WHICH state transitions fire the action (Green->Yellow, Yellow->Red) |

## Scenario: Create a CPU Alarm with Email Notification

```powershell
$entity = Get-Cluster "Production" -Server $vcenter

# Create a metric trigger: CPU > 90% for 5 minutes = Red, > 75% = Yellow
$cpuMetric = Get-Metric -Name "cpu.usage.average" -Server $vcenter
$trigger = New-AlarmTrigger -Metric $cpuMetric -MetricAlarmOperator Above `
    -Yellow 75 -Red 90 -RedIntervalSeconds 300 `
    -EntityType "VirtualMachine"

# Create an email action
$action = New-AlarmAction -Email -To "ops@company.com" `
    -Subject "VM CPU Alert" -Body "VM CPU usage exceeded threshold"

# Create the alarm definition, attaching trigger and action
$alarm = New-AlarmDefinition -Name "VM-High-CPU" -Entity $entity `
    -AlarmTrigger $trigger -AlarmAction $action `
    -Description "Alerts when VM CPU exceeds 75% (warning) or 90% (critical)" `
    -ActionRepeatMinutes 30

# Add action trigger: only fire email on transition to Red (not Yellow)
$emailAction = Get-AlarmAction -AlarmDefinition $alarm -ActionType SendEmail
New-AlarmActionTrigger -AlarmAction $emailAction `
    -StartStatus Yellow -EndStatus Red
```

## Scenario: Audit and Manage Existing Alarms

```powershell
# List all alarm definitions with their current state
Get-AlarmDefinition -Server $vcenter |
    Select-Object Name, Enabled,
        @{N='Entity';E={$_.Entity.Name}},
        @{N='EntityType';E={$_.Entity.GetType().Name}} |
    Sort-Object Entity | Format-Table -AutoSize

# Find disabled alarms (potential monitoring gaps)
Get-AlarmDefinition -Enabled:$false -Server $vcenter |
    Select-Object Name, Entity | Format-Table

# Inspect triggers and actions for a specific alarm
$alarm = Get-AlarmDefinition -Name "Host connection and power state" -Server $vcenter
Get-AlarmTrigger -AlarmDefinition $alarm | Format-List
Get-AlarmAction -AlarmDefinition $alarm | Format-List
Get-AlarmAction -AlarmDefinition $alarm | Get-AlarmActionTrigger | Format-List

# Bulk enable all alarms for a cluster
Get-AlarmDefinition -Entity (Get-Cluster "Production") -Enabled:$false |
    Set-AlarmDefinition -Enabled $true

# Remove a custom alarm
Get-AlarmDefinition -Name "VM-High-CPU" -Server $vcenter | Remove-AlarmDefinition -Confirm:$false
```

## Scenario: State-Based Alarm for VM Power State

```powershell
$entity = Get-Folder -NoRecursion -Server $vcenter  # Root = applies everywhere

# Trigger when a VM powers off unexpectedly
$trigger = New-AlarmTrigger -StatePath "runtime.powerState" `
    -Value "poweredOff" -EntityStatus Red `
    -EntityType "VirtualMachine" -StateAlarmOperator Equal

$action = New-AlarmAction -Snmp

New-AlarmDefinition -Name "VM-Unexpected-PowerOff" -Entity $entity `
    -AlarmTrigger $trigger -AlarmAction $action `
    -Description "Fires when any VM powers off"
```

## Common Mistakes

### Mistake 1: Creating Alarm Definition Without Actions

```powershell
# WRONG -- Alarm triggers but nobody is notified
New-AlarmDefinition -Name "High-CPU" -Entity $cluster `
    -AlarmTrigger $trigger
# Alarm appears in vCenter UI but does nothing visible

# CORRECT -- Always attach at least one action
$action = New-AlarmAction -Email -To "ops@company.com" -Subject "High CPU"
New-AlarmDefinition -Name "High-CPU" -Entity $cluster `
    -AlarmTrigger $trigger -AlarmAction $action
```

### Mistake 2: Alarm Fires on Every State Transition

```powershell
# WRONG -- Action fires on Green->Yellow, Yellow->Red, Red->Yellow, Yellow->Green
# You get flooded with emails during flapping conditions

# CORRECT -- Restrict action triggers to only the transitions you care about
$action = Get-AlarmAction -AlarmDefinition $alarm
New-AlarmActionTrigger -AlarmAction $action `
    -StartStatus Yellow -EndStatus Red  # Only notify on escalation to Red
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-AlarmDefinition` | List alarms | `-Name`, `-Entity`, `-Enabled`, `-Server` |
| `New-AlarmDefinition` | Create alarm | `-Name`, `-Entity`, `-AlarmTrigger`, `-AlarmAction`, `-Description`, `-ActionRepeatMinutes` |
| `Set-AlarmDefinition` | Modify alarm | `-Name`, `-Enabled`, `-AlarmTrigger`, `-AlarmAction`, `-Description` |
| `Remove-AlarmDefinition` | Delete alarm | `-AlarmDefinition` |
| `Get-AlarmTrigger` | List triggers | `-AlarmDefinition`, `-TriggerType` (Metric/State/Event) |
| `New-AlarmTrigger` | Create trigger | `-Metric`, `-MetricAlarmOperator`, `-Yellow`, `-Red`, `-RedIntervalSeconds` (metric); `-StatePath`, `-Value`, `-StateAlarmOperator` (state); `-EventType`, `-EntityStatus` (event) |
| `Get-AlarmAction` | List actions | `-AlarmDefinition`, `-ActionType` (SendEmail/ExecuteScript/SendSNMP) |
| `New-AlarmAction` | Create action | `-Email -To -Subject -Body` (email); `-Snmp` (SNMP); `-Script -ScriptPath` (script) |
| `Remove-AlarmAction` | Delete action | `-AlarmAction` |
| `Get-AlarmActionTrigger` | List action triggers | `-AlarmAction` |
| `New-AlarmActionTrigger` | Create action trigger | `-AlarmAction`, `-StartStatus`, `-EndStatus` (Green/Yellow/Red), `-Repeat` |
| `Remove-AlarmActionTrigger` | Delete action trigger | `-AlarmActionTrigger` |
| `New-AlarmTriggerArgument` | Create trigger filter | `-AttributeName`, `-Operator`, `-Value` |
| `Get-AlarmTriggerArgumentAttributeName` | List filter attributes | (no parameters) |

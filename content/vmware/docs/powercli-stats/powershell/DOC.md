---
name: powercli-stats
description: "VMware PowerCLI 13.3 — performance statistics, events, tasks"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,vcenter,esxi,Get-Stat,Get-StatInterval,Get-StatType,Get-VIEvent,New-StatInterval,Remove-StatInterval,Set-StatInterval"
---

# VMware PowerCLI — performance statistics, events, tasks

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Get-Stat` | This cmdlet retrieves the statistical information available on a vCenter Server system. |
| `Get-StatInterval` | This cmdlet retrieves the available statistics intervals and filters them using the provided para... |
| `Get-StatType` | This cmdlet retrieves the available statistics types for a inventory object. |
| `Get-VIEvent` | This cmdlet retrieves information about the events on a vCenter Server system. |
| `New-StatInterval` | This cmdlet creates a statistics interval with the specified parameters. |
| `Remove-StatInterval` | This cmdlet removes the statistics interval specified by the provided sampling period or name. |
| `Set-StatInterval` | This cmdlet changes the statistics interval that is specified by the provided parameters. |

---

### Get-Stat

This cmdlet retrieves the statistical information available on a vCenter Server system.

This cmdlet retrieves the statistical information available on a vCenter Server system for each provided entity. For example, if the CPU parameter is set to $true, collects the average CPU usage and the average CPU usagemhz counters as appropriate for each entity. If the Stat parameter is specified, collects all provided named stats counters. Counters are provided using a dotted notation of the form "counter group"."counter name"."rollup type". For example: "cpu.usage.min". The cmdlet uses th...

**Returns**: `LongSample`

```
Get-Stat
    [-Common]
    [-Cpu]
    [-Disk]
    -Entity <VIObject[]>
    [-Finish <DateTime>]
    [-Instance <String[]>]
    [-IntervalMins <Int32[]>]
    [-IntervalSecs <Int32[]>]
    [-MaxSamples <Int32>]
    [-Memory]
    [-Network]
    [-Realtime]
    [-Server <VIServer[]>]
    [-Start <DateTime>]
    [-Stat <String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Common` | `SwitchParameter` | No | Indicates whether the command collects common CPU, disk, memory and network statistics. |
| `-Cpu` | `SwitchParameter` | No | Indicates whether the command collects common CPU statistics, such as the average CPU usage and average CPU usagemhz counters as appropriate for each entity. |
| `-Disk` | `SwitchParameter` | No | Indicates whether the command collects common disk statistics, such as the average disk usage, average disk read and average disk write counters as appropriate for each entity. |
| `-Entity` | `VIObject[]` | Yes | Specifies the objects (such as virtual machine, virtual machine host, resource pool, and so on) whose statistics you want to retrieve. |
| `-Finish` | `DateTime` | No | Specifies the end of the time range for which you want to collect statistics. The valid format is dd/mm/yyyy. |
| `-Instance` | `String[]` | No | Specifies the Instance property of the statistics you want to retrieve. |
| `-IntervalMins` | `Int32[]` | No | Specifies one or more intervals in minutes of the statistics samples you want to retrieve. The closest available statistics interval is taken. To retrieve statistics samples for all available inter... |
| `-IntervalSecs` | `Int32[]` | No | Specifies one or more intervals in seconds of the statistics samples you want to retrieve. The closest available statistics interval is taken. To retrieve statistics samples for all available inter... |
| `-MaxSamples` | `Int32` | No | Specifies the maximum number of samples for each statistic. |
| `-Memory` | `SwitchParameter` | No | Indicates whether the command collects common memory statistics, such as the mem usage, mem vmmemctl, mem active and mem granted counters as appropriate for each entity. |
| `-Network` | `SwitchParameter` | No | Indicates whether the command collects common network statistics, such as the average network usage, average network transmitted and average network received counters as appropriate for each entity. |
| `-Realtime` | `SwitchParameter` | No | Indicates whether the command collects real time statistics. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Start` | `DateTime` | No | Specifies the beginning of the time range for which you want to collect statistics. The valid format is dd/mm/yyyy. |
| `-Stat` | `String[]` | No | Specifies the identifiers of the statistics you want to retrieve. Counters are provided using a dotted notation of the form "counter group"."counter name"."rollup type". For example, "cpu.usage.min". |

---

### Get-StatInterval

This cmdlet retrieves the available statistics intervals and filters them using the provided parameters.

**Returns**: `StatInterval`

```
Get-StatInterval
    [-Name <String[]>]
    [-SamplingPeriodSecs <Int32[]>]
    [-Server <VIServer[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String[]` | No | Specifies the names of the statistics intervals you want to retrieve. |
| `-SamplingPeriodSecs` | `Int32[]` | No | Specifies the sampling period of the statistics intervals you want to retrieve. The sampling period is an integer that defines (in seconds) the interval of the statistics sample. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |

---

### Get-StatType

This cmdlet retrieves the available statistics types for a inventory object.

This cmdlet retrieves the available statistics types for a virtual machine, virtual machine host, cluster, or resource pool. Performance statistics types can be filtered by their names, start and finish times,  and collection intervals. If the Realtime parameter is set, the Start and Finish parameters are ignored.

**Returns**: `System`

```
Get-StatType
    -Entity <VIObject[]>
    [-Finish <DateTime>]
    [-Interval <StatInterval[]>]
    [-Name <String[]>]
    [-Realtime]
    [-Server <VIServer[]>]
    [-Start <DateTime>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObject[]` | Yes | Specifies clusters, virtual machine hosts, resource pools, or virtual machines, for which you want to retrieve the available statistics types. |
| `-Finish` | `DateTime` | No | Specifies the end of the time range for which the statistics types you want to retrieve are collected. The valid format is dd/mm/yyyy. This value corresponds to the server time. When the finish tim... |
| `-Interval` | `StatInterval[]` | No | Specifies the interval at which the statistics types you want to retrieve are gathered. The interval can be specified by its name or by its sampling period in seconds. |
| `-Name` | `String[]` | No | Specifies the names of the statistics types you want to retrieve. |
| `-Realtime` | `SwitchParameter` | No | Indicates that you want to retrieve realtime statistics type as well. If this parameter is set, the Start and Finish parameters are ignored. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Start` | `DateTime` | No | Specifies the beginning of the time range for which the statistics types you want to retrieve are collected. The valid format is dd/mm/yyyy. This value corresponds to the server time. When the star... |

---

### Get-VIEvent

This cmdlet retrieves information about the events on a vCenter Server system.

This cmdlet retrieves information about the events on a vCenter Server system. An event is any action in the vCenter Server system or ESX/ESXi host. You can filter retrieved events by specifying arguments for the cmdlet parameters. Filters are additive. For example, when you specify the Entity, Start, and Finish parameters, Get-VIEvent filters events both by the entity and the timestamp properties. To specify a server different from the default one, use the Server parameter.

**Returns**: `VimApi`

```
Get-VIEvent
    [-Entity <VIObject[]>]
    [-Finish <DateTime>]
    [-MaxSamples <Int32>]
    [-Server <VIServer[]>]
    [-Start <DateTime>]
    [-Types <EventCategory[]>]
    [-Username <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Entity` | `VIObject[]` | No | Specifies objects (such as virtual machine, virtual machine host, resource pool, and so on) for which you want to collect events. |
| `-Finish` | `DateTime` | No | Specifies the end date of the events you want to retrieve. The valid formats are dd/mm/yyyy and mm/dd/yyyy, depending on the local machine regional settings. |
| `-MaxSamples` | `Int32` | No | Specifies the maximum number of retrieved events. When you do not filter events by time period, the maximum number of retrieved events is set to 100 by default.   Note: This parameter is ignored wh... |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Start` | `DateTime` | No | Specifies the start date of the events you want to retrieve. The valid formats are dd/mm/yyyy and mm/dd/yyyy, depending on the local machine regional settings. |
| `-Types` | `EventCategory[]` | No | Specifies the type of the events you want to collect. The valid values are Error, Info, and Warning. |
| `-Username` | `String` | No | Specifies the user that has initiated the events you want to retrieve. |

---

### New-StatInterval

This cmdlet creates a statistics interval with the specified parameters.

**Returns**: `StatInterval`

```
New-StatInterval
    -Name <String>
    -SamplingPeriodSecs <Int32>
    [-Server <VIServer[]>]
    -StorageTimeSecs <Int32>
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | Specifies a name for the new statistics interval. |
| `-SamplingPeriodSecs` | `Int32` | Yes | Specifies a sampling period in seconds. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StorageTimeSecs` | `Int32` | Yes | Specifies the length of time (in seconds) that the statistics information is kept in the database. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Remove-StatInterval

This cmdlet removes the statistics interval specified by the provided sampling period or name.

**Returns**: `None`

```
Remove-StatInterval
    -Interval <StatInterval[]>
    [-Server <VIServer[]>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Interval` | `StatInterval[]` | Yes | Specifies the statistics intervals you want to remove. The values of this parameter can be statistics interval objects, names, or refresh periods in seconds. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

### Set-StatInterval

This cmdlet changes the statistics interval that is specified by the provided parameters.

**Returns**: `StatInterval`

```
Set-StatInterval
    -Interval <StatInterval[]>
    [-SamplingPeriodSecs <Int32>]
    [-Server <VIServer[]>]
    [-StorageTimeSecs <Int32>]
    [-Confirm]
    [-WhatIf]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Interval` | `StatInterval[]` | Yes | Specifies the statistics interval you want to change. |
| `-SamplingPeriodSecs` | `Int32` | No | Specifies a new sampling period in seconds. |
| `-Server` | `VIServer[]` | No | Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more infor... |
| `-StorageTimeSecs` | `Int32` | No | Specifies a new time period in seconds, for which the statistics information is kept. |
| `-Confirm` | `SwitchParameter` | No | If the value is $true, indicates that the cmdlet asks for confirmation before running. If the value is $false, the cmdlet runs without asking for user confirmation. |
| `-WhatIf` | `SwitchParameter` | No | Indicates that the cmdlet is run only to display the changes that would be made and actually no objects are modified. |

---

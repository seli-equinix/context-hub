---
name: powercli-monitoring
description: "VMware PowerCLI 13.3 — Performance stats, events, tasks, logs"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 1
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,monitoring,Get-EventType, Get-Log, Get-LogType, Get-Metric, Get-Stat, Get-StatInterval, Get-StatType, Get-VIEvent, New-StatInterval, Remove-StatInterval, Set-StatInterval"
---

# VMware PowerCLI — Monitoring & Events

Performance stats, events, tasks, logs. Module: VMware.VimAutomation (11 cmdlets).

## Cmdlet Reference (11 cmdlets)

### Get

#### `Get-EventType`

This cmdlet retrieves the available event types on a vCenter Server system.

**Parameters**: `Category, Server`

#### `Get-Log`

This cmdlet retrieves entries from vSphere logs.

**Parameters**: `Key, VMHost, StartLineNum, NumLines, Bundle, DestinationPath, Server, RunAsync`

#### `Get-LogType`

This cmdlet retrieves information about the log types available on a virtual machine host.

**Parameters**: `VMHost, Server`

#### `Get-Metric`

This cmdlet retrieves the available metrics on a vCenter Server system.

**Parameters**: `MetricGroup, Name, Server`

#### `Get-Stat`

This cmdlet retrieves the statistical information available on a vCenter Server system.

**Parameters**: `Entity, Common, Memory, Cpu, Disk, Network, Stat, Start, Finish, MaxSamples, IntervalMins, IntervalSecs` (+3 more)

```powershell
Get-Stat -Entity (Get-VM "my-vm") -Stat "cpu.usage.average" -Start (Get-Date).AddHours(-24) -IntervalMins 30
```

#### `Get-StatInterval`

This cmdlet retrieves the available statistics intervals and filters them using the provided parameters.

**Parameters**: `Name, SamplingPeriodSecs, Server`

#### `Get-StatType`

This cmdlet retrieves the available statistics types for a inventory object.

**Parameters**: `Name, Entity, Start, Finish, Interval, Realtime, Server`

#### `Get-VIEvent`

This cmdlet retrieves information about the events on a vCenter Server system.

**Parameters**: `Entity, Start, Finish, Username, MaxSamples, Types, Server`

### New

#### `New-StatInterval`

This cmdlet creates a statistics interval with the specified parameters.

**Parameters**: `Name, SamplingPeriodSecs, StorageTimeSecs, Server`

### Remove

#### `Remove-StatInterval`

This cmdlet removes the statistics interval specified by the provided sampling period or name.

**Parameters**: `Interval, Server`

### Set

#### `Set-StatInterval`

This cmdlet changes the statistics interval that is specified by the provided parameters.

**Parameters**: `SamplingPeriodSecs, StorageTimeSecs, Interval, Server`

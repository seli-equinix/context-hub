---
name: powercli-monitoring
description: "VMware PowerCLI 13.3 — Performance statistics, events, tasks, and log retrieval for vSphere monitoring and troubleshooting"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 4
  updated-on: "2026-04-07"
  source: community
  tags: "vmware,powercli,vsphere,monitoring,performance,stats,events,logs,Get-Stat,Get-StatType,Get-StatInterval,New-StatInterval,Set-StatInterval,Remove-StatInterval,Get-VIEvent,Get-EventType,Get-Log,Get-LogType,Get-Metric"
---

# VMware PowerCLI — Monitoring & Events

## Golden Rule

**`Get-Stat` is the single most important monitoring cmdlet. It retrieves historical performance data for ANY vSphere entity. Pair it with `Get-VIEvent` to correlate performance degradation with configuration changes.**

| Task | Cmdlet | Use When | Critical Notes |
|------|--------|----------|----------------|
| CPU/RAM/disk/net metrics | `Get-Stat` | Capacity planning, troubleshooting | Use `-Realtime` for 20s intervals, historical for trends |
| What metrics are available? | `Get-StatType` | Discovering which counters exist on an entity | Available counters differ between VMs, hosts, clusters |
| What happened? | `Get-VIEvent` | Investigating changes, migrations, failures | Default returns last 100 events -- use `-Start`/`-Finish` |
| Host logs | `Get-Log` | ESXi syslog retrieval, diagnostic bundles | Use `-Bundle` for full support log package |

**Key stat intervals (default vCenter retention):**

| Interval | Sampling | Retention | Use For |
|----------|----------|-----------|---------|
| Realtime | 20 sec | 1 hour | Active troubleshooting |
| Past Day | 5 min | 1 day | Recent performance |
| Past Week | 30 min | 1 week | Short-term trends |
| Past Month | 2 hours | 1 month | Capacity planning |
| Past Year | 1 day | 1 year | Long-term trends |

## Scenario: Performance Troubleshooting -- CPU and Memory

```powershell
# Get real-time CPU and memory for a VM (20-second samples, last hour)
$vm = Get-VM -Name "prod-db-01" -Server $vcenter
Get-Stat -Entity $vm -Stat "cpu.usage.average", "mem.usage.average" `
    -Realtime -Server $vcenter |
    Select-Object Timestamp, MetricId, Value, Unit |
    Sort-Object Timestamp -Descending | Select-Object -First 20 | Format-Table

# Historical CPU over the last 7 days for capacity planning
Get-Stat -Entity $vm -Stat "cpu.usage.average" `
    -Start (Get-Date).AddDays(-7) -Finish (Get-Date) `
    -IntervalMins 30 -Server $vcenter |
    Group-Object { $_.Timestamp.Date } | ForEach-Object {
        [PSCustomObject]@{
            Date   = $_.Name
            AvgCPU = [math]::Round(($_.Group | Measure-Object -Property Value -Average).Average, 1)
            MaxCPU = [math]::Round(($_.Group | Measure-Object -Property Value -Maximum).Maximum, 1)
        }
    } | Sort-Object Date | Format-Table

# Find VMs with sustained high CPU (>80% average over 24 hours)
Get-VM -Location (Get-Cluster "Production") -Server $vcenter | ForEach-Object {
    $stats = Get-Stat -Entity $_ -Stat "cpu.usage.average" `
        -Start (Get-Date).AddDays(-1) -IntervalMins 30 -Server $vcenter
    $avg = ($stats | Measure-Object -Property Value -Average).Average
    if ($avg -gt 80) {
        [PSCustomObject]@{
            VM     = $_.Name
            AvgCPU = [math]::Round($avg, 1)
            Host   = $_.VMHost.Name
        }
    }
} | Sort-Object AvgCPU -Descending | Format-Table
```

## Scenario: Event Investigation After an Incident

```powershell
# What happened to this VM in the last 24 hours?
$vm = Get-VM -Name "prod-web-01" -Server $vcenter
Get-VIEvent -Entity $vm -Start (Get-Date).AddDays(-1) -Server $vcenter |
    Select-Object CreatedTime, UserName, FullFormattedMessage |
    Sort-Object CreatedTime -Descending | Format-Table -Wrap

# Find all errors across the environment in the last 4 hours
Get-VIEvent -Start (Get-Date).AddHours(-4) -Types Error -Server $vcenter |
    Select-Object CreatedTime, @{N='Entity';E={$_.ObjectName}},
        UserName, FullFormattedMessage |
    Sort-Object CreatedTime -Descending | Format-Table -Wrap

# Who logged in during the outage window?
Get-VIEvent -Start "04/01/2026" -Finish "04/02/2026" -Server $vcenter |
    Where-Object { $_.FullFormattedMessage -match "logged in" } |
    Select-Object CreatedTime, UserName, FullFormattedMessage | Format-Table

# Correlate: get vMotion events (VM migrations)
Get-VIEvent -Start (Get-Date).AddDays(-1) -Server $vcenter |
    Where-Object { $_ -is [VMware.Vim.VmMigratedEvent] -or
                   $_ -is [VMware.Vim.DrsVmMigratedEvent] } |
    Select-Object CreatedTime, ObjectName,
        @{N='From';E={$_.Host.Name}},
        @{N='Msg';E={$_.FullFormattedMessage}} | Format-Table
```

## Scenario: Host Log Retrieval for Support

```powershell
# List available log types on a host
$vmhost = Get-VMHost "esxi01.example.com" -Server $vcenter
Get-LogType -VMHost $vmhost | Select-Object Key, Label

# Get the last 500 lines of syslog
$vmhost | Get-Log -Key "syslog" -NumLines 500

# Download full diagnostic bundle for VMware support
$vmhost | Get-Log -Bundle -DestinationPath "C:\Support\esxi01-logs"
```

## Common Mistakes

### Mistake 1: Pulling All Stats Without Filtering

```powershell
# WRONG -- Gets ALL stat types for ALL intervals, massive data volume
Get-Stat -Entity $vm -Common -Start (Get-Date).AddMonths(-6)
# Returns hundreds of thousands of data points, extremely slow

# CORRECT -- Specify exact counters and a reasonable time range
Get-Stat -Entity $vm -Stat "cpu.usage.average", "mem.usage.average" `
    -Start (Get-Date).AddDays(-7) -IntervalMins 30 -Server $vcenter
```

### Mistake 2: Using Get-VIEvent Without Time Bounds

```powershell
# WRONG -- No time filter, returns only last 100 events (default MaxSamples)
$events = Get-VIEvent -Entity $vm
# You think you got all events, but you only got the most recent 100

# CORRECT -- Always specify Start/Finish for complete data
$events = Get-VIEvent -Entity $vm `
    -Start (Get-Date).AddDays(-7) -Finish (Get-Date) -Server $vcenter
# With Start/Finish specified, MaxSamples is ignored and ALL events are returned
```

## Cmdlet Quick Reference

| Cmdlet | Purpose | Key Parameters |
|--------|---------|----------------|
| `Get-Stat` | Retrieve performance data | `-Entity`, `-Stat` (counter name), `-Start`, `-Finish`, `-Realtime`, `-IntervalMins`, `-MaxSamples`, `-Instance` |
| `Get-StatType` | List available counters | `-Entity`, `-Realtime`, `-Name`, `-Start`, `-Finish` |
| `Get-StatInterval` | List collection intervals | `-Name`, `-SamplingPeriodSecs` |
| `New-StatInterval` | Create custom interval | `-Name`, `-SamplingPeriodSecs`, `-StorageTimeSecs` |
| `Set-StatInterval` | Modify interval retention | `-Interval`, `-StorageTimeSecs` |
| `Remove-StatInterval` | Delete custom interval | `-Interval` |
| `Get-VIEvent` | Retrieve events | `-Entity`, `-Start`, `-Finish`, `-Types` (Error/Info/Warning), `-Username`, `-MaxSamples` |
| `Get-EventType` | List event types | `-Category` |
| `Get-Metric` | List available metrics | `-Name`, `-MetricGroup` (CPU/Disk/Memory/Network) |
| `Get-Log` | Retrieve host/vCenter logs | `-Key`, `-VMHost`, `-NumLines`, `-StartLineNum`, `-Bundle`, `-DestinationPath` |
| `Get-LogType` | List available log keys | `-VMHost` |

---
name: powercli-monitoring
description: "VMware PowerCLI 13.3 — Performance stats, events, tasks, logs"
metadata:
  languages: "powershell"
  versions: "13.3.0"
  revision: 3
  updated-on: "2026-04-06"
  source: community
  tags: "vmware,powercli,vsphere,monitoring,Get-EventType, Get-Log, Get-LogType, Get-Metric, Get-Stat, Get-StatInterval, Get-StatType, Get-VIEvent, New-StatInterval, Remove-StatInterval, Set-StatInterval"
---

# VMware PowerCLI — Monitoring & Events

Performance stats, events, tasks, logs. Module: VMware.VimAutomation (11 cmdlets).

## Get

### `Get-EventType`

**This cmdlet retrieves the available event types on a vCenter Server system.**

This cmdlet retrieves the available event types on a vCenter Server system. The cmdlet returns a set of event types that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Category [EventCategory] (Optional) Specifies the category of the event type that you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vSphere servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-EventType
```
_Retrieves all available event types._

```powershell
Get-EventType -Category Error
```
_Retrieves all available event types which have category Error._

### `Get-Log`

**This cmdlet retrieves entries from vSphere logs.**

This cmdlet retrieves entries from vSphere logs. Returns portions of the log files according to the criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Bundle [SwitchParameter] (Optional) Indicates whether to retrieve a diagnostic bundle of logs from vCenter Server.
- -DestinationPath [String] (Required) Specifies a local file path where you want to save the log bundle.
- -Key [String[]] (Required) Specifies the key identifier of the log file you want to retrieve. Passing values to this parameter through a pipeline is deprecated and will be deactivated in a future release.
- -NumLines [Int32] (Optional) Specifies the number of the lines you want to retrieve from the logs.
- -RunAsync [SwitchParameter] (Optional) Indicates that the command returns immediately without waiting for the task to complete. In this mode, the output of the cmdlet is a Task object. For more information about the RunAsync parameter run "help About_RunAsync" in the VMware PowerCLI console.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StartLineNum [Int32] (Optional) Specifies the start line number for reading from the logs.
- -VMHost [VMHost[]] (Optional) Specifies the hosts for which you want to retrieve logs. If no value is given to this parameter, the command returns logs only for the default vCenter Server system.

**Examples:**

```powershell
$keys = Get-LogType

Get-Log -Key $keys[0]
```
_Obtain the available keys. Obtains the first log file from the currently connected vCenter Server system._

```powershell
$vmhost = Get-VMHost Host

$keyList = Get-LogType -VMHost $vmhost

$vmhost | Get-Log -Key $keyList[0] -StartLineNum 1 -NumLines 100
```
_Retrieve the first one hundred log lines for the specified host and key._

```powershell
Get-VMHost Host | Get-Log -Bundle -DestinationPath "D:\VMHostBundeLog"
```
_Retrieve a bundle log for the specified host._

### `Get-LogType`

**This cmdlet retrieves information about the log types available on a virtual machine host.**

This cmdlet retrieves information about the log types available on a virtual machine host. If no virtual machine host is specified, the cmdlet retrieves the log types for the default vCenter Server system. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -VMHost [VMHost[]] (Optional) Specifies the hosts you want to search for log types. If no value is given to this parameter, the command searches for logs only on the default vCenter Server system.

**Examples:**

```powershell
$vmhost = Get-VMHost -State "Connected"

Get-Logtype -VMHost $vmhost
```
_Gets information about the available logs on the virtual machine hosts whose state is Connected._

### `Get-Metric`

**This cmdlet retrieves the available metrics on a vCenter Server system.**

This cmdlet retrieves the available metrics on a vCenter Server system. The cmdlet returns a set of metrics that correspond to the filter criteria provided by the cmdlet parameters. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -MetricGroup [String[]] (Optional) Specifies the metric groups of the metrics that you want to retrieve.
- -Name [String[]] (Optional) Specifies the names of the metrics that you want to retrieve.
- -Server [VIServer[]] (Optional) Specifies the vSphere servers on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of the Connect-VIServer cmdlet.

**Examples:**

```powershell
Get-Metric
```
_Retrieves all available metrics._

```powershell
Get-Metric -Name "Usage*"
```
_Retrieves metrics with the name Usage._

```powershell
Get-Metric -MetricGroup "CPU" $server
```
_Retrieves all available metrics on the server that match the pattern._

### `Get-Stat`

**This cmdlet retrieves the statistical information available on a vCenter Server system.**

This cmdlet retrieves the statistical information available on a vCenter Server system for each provided entity. For example, if the CPU parameter is set to $true, collects the average CPU usage and the average CPU usagemhz counters as appropriate for each entity. If the Stat parameter is specified, collects all provided named stats counters. Counters are provided using a dotted notation of the form "counter group"."counter name"."rollup type". For example: "cpu.usage.min". The cmdlet uses the Start time, if provided, and the Finish time, if provided, along with the MaxSamples, if provided, to bound the data collection. If intervalSecs is provided,  the closest matching available interval is used. For each statistics sample on the server, the cmdlet returns a Sample object. The Instance property of the Sample object shows the serial number of the device for which a statistics value is taken. If the Instance property is empty ("), this indicates that the statistics sample contains an average statistic value for all specified devices. If you are connected to a vCenter Server and Get-Stat is run for a host entity, the cmdlet returns only the statistics available on the vCenter Server.

**Parameters:**

- -Common [SwitchParameter] (Optional) Indicates whether the command collects common CPU, disk, memory and network statistics.
- -Cpu [SwitchParameter] (Optional) Indicates whether the command collects common CPU statistics, such as the average CPU usage and average CPU usagemhz counters as appropriate for each entity.
- -Disk [SwitchParameter] (Optional) Indicates whether the command collects common disk statistics, such as the average disk usage, average disk read and average disk write counters as appropriate for each entity.
- -Entity [VIObject[]] (Required) Specifies the objects (such as virtual machine, virtual machine host, resource pool, and so on) whose statistics you want to retrieve.
- -Finish [DateTime] (Optional) Specifies the end of the time range for which you want to collect statistics. The valid format is dd/mm/yyyy.
- -Instance [String[]] (Optional) Specifies the Instance property of the statistics you want to retrieve.
- -IntervalMins [Int32[]] (Optional) Specifies one or more intervals in minutes of the statistics samples you want to retrieve. The closest available statistics interval is taken. To retrieve statistics samples for all available intervals, pass *. If the IntervalMins parameter is not specified, the samples with the best sample rate are retrieved. A best sample rate is the highest sample rate, whose relevant period contains the relevant periods for all other sample rates. A relevant period is the period that starts no earlier than the oldest sample still retained, and is a subset of a query period specified by the user.
- -IntervalSecs [Int32[]] (Optional) Specifies one or more intervals in seconds of the statistics samples you want to retrieve. The closest available statistics interval is taken. To retrieve statistics samples for all available intervals, pass *.
- -MaxSamples [Int32] (Optional) Specifies the maximum number of samples for each statistic.
- -Memory [SwitchParameter] (Optional) Indicates whether the command collects common memory statistics, such as the mem usage, mem vmmemctl, mem active and mem granted counters as appropriate for each entity.
- -Network [SwitchParameter] (Optional) Indicates whether the command collects common network statistics, such as the average network usage, average network transmitted and average network received counters as appropriate for each entity.
- -Realtime [SwitchParameter] (Optional) Indicates whether the command collects real time statistics.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Start [DateTime] (Optional) Specifies the beginning of the time range for which you want to collect statistics. The valid format is dd/mm/yyyy.
- -Stat [String[]] (Optional) Specifies the identifiers of the statistics you want to retrieve. Counters are provided using a dotted notation of the form "counter group"."counter name"."rollup type". For example, "cpu.usage.min".

**Examples:**

```powershell
Get-Stat -Entity $VM -Start 5/5/2013 -Finish 7/10/2013 -Disk -IntervalSecs 300
```
_Prints the disk statistics for the specified time interval for the first virtual machine, retrieved by the Get-VM cmdlet._

```powershell
Get-Stat -Entity $MyVMHost -Cpu -Instance 0
```
_Retrieves the CPU statistics for the first processor of a multiprocessor host.   Note: This command can only work with a direct ESX connection._

```powershell
Get-VMHost -Name "MyVMHost" | Get-Stat -Network -IntervalSecs 20
```
_Retrieves the network usage statistics for the specified host for the specified time interval._

### `Get-StatInterval`

**This cmdlet retrieves the available statistics intervals and filters them using the provided parameters.**

**Parameters:**

- -Name [String[]] (Optional) Specifies the names of the statistics intervals you want to retrieve.
- -SamplingPeriodSecs [Int32[]] (Optional) Specifies the sampling period of the statistics intervals you want to retrieve. The sampling period is an integer that defines (in seconds) the interval of the statistics sample.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Get-StatInterval
```
_Retrieves the available statistics intervals._

### `Get-StatType`

**This cmdlet retrieves the available statistics types for a inventory object.**

This cmdlet retrieves the available statistics types for a virtual machine, virtual machine host, cluster, or resource pool. Performance statistics types can be filtered by their names, start and finish times,  and collection intervals. If the Realtime parameter is set, the Start and Finish parameters are ignored.

**Parameters:**

- -Entity [VIObject[]] (Required) Specifies clusters, virtual machine hosts, resource pools, or virtual machines, for which you want to retrieve the available statistics types.
- -Finish [DateTime] (Optional) Specifies the end of the time range for which the statistics types you want to retrieve are collected. The valid format is dd/mm/yyyy. This value corresponds to the server time. When the finish time is omitted, the returned result includes up to the most recent statistics type.
- -Interval [StatInterval[]] (Optional) Specifies the interval at which the statistics types you want to retrieve are gathered. The interval can be specified by its name or by its sampling period in seconds.
- -Name [String[]] (Optional) Specifies the names of the statistics types you want to retrieve.
- -Realtime [SwitchParameter] (Optional) Indicates that you want to retrieve realtime statistics type as well. If this parameter is set, the Start and Finish parameters are ignored.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Start [DateTime] (Optional) Specifies the beginning of the time range for which the statistics types you want to retrieve are collected. The valid format is dd/mm/yyyy. This value corresponds to the server time. When the start time is omitted, the returned statistics types start from the first available statistics type in the system.

**Examples:**

```powershell
Get-StatType -Entity "MyVM"
```
_Retrieves the statistics types collected for the specified virtual machine._

### `Get-VIEvent`

**This cmdlet retrieves information about the events on a vCenter Server system.**

This cmdlet retrieves information about the events on a vCenter Server system. An event is any action in the vCenter Server system or ESX/ESXi host. You can filter retrieved events by specifying arguments for the cmdlet parameters. Filters are additive. For example, when you specify the Entity, Start, and Finish parameters, Get-VIEvent filters events both by the entity and the timestamp properties. To specify a server different from the default one, use the Server parameter.

**Parameters:**

- -Entity [VIObject[]] (Optional) Specifies objects (such as virtual machine, virtual machine host, resource pool, and so on) for which you want to collect events.
- -Finish [DateTime] (Optional) Specifies the end date of the events you want to retrieve. The valid formats are dd/mm/yyyy and mm/dd/yyyy, depending on the local machine regional settings.
- -MaxSamples [Int32] (Optional) Specifies the maximum number of retrieved events. When you do not filter events by time period, the maximum number of retrieved events is set to 100 by default.   Note: This parameter is ignored when the Start and Finish parameters are specified and all events from the specified period are retrieved.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -Start [DateTime] (Optional) Specifies the start date of the events you want to retrieve. The valid formats are dd/mm/yyyy and mm/dd/yyyy, depending on the local machine regional settings.
- -Types [EventCategory[]] (Optional) Specifies the type of the events you want to collect. The valid values are Error, Info, and Warning.
- -Username [String] (Optional) Specifies the user that has initiated the events you want to retrieve.

**Examples:**

```powershell
Get-VIEvent -Entity MyVM1 -Username admin -Types error -MaxSamples 15
```
_Retrieves a list of the last fifteen error events on the MyVM1 virtual machine for the user admin._

```powershell
Connect-VIServer -Server 10.23.113.41

$events = Get-VIEvent -MaxSamples 100

foreach ($event in $events) {if  ($event.fullFormattedMessage -match "User (.*)@\b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b logged in") {Write-Host ("User " + $matches[1] + " logged in at:" + $event.createdTime)} }
```
_Gathers information for the users that have logged in._

## New

### `New-StatInterval`

**This cmdlet creates a statistics interval with the specified parameters.**

**Parameters:**

- -Name [String] (Required) Specifies a name for the new statistics interval.
- -SamplingPeriodSecs [Int32] (Required) Specifies a sampling period in seconds.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageTimeSecs [Int32] (Required) Specifies the length of time (in seconds) that the statistics information is kept in the database.

**Examples:**

```powershell
New-StatInterval -Name Minute -SamplingPeriodSecs 60 -StorageTimeSecs 600
```
_Creates a new statistics interval named Minute. Note that creating statistics intervals is allowed only on VirtualCenter 2.0._

## Remove

### `Remove-StatInterval`

**This cmdlet removes the statistics interval specified by the provided sampling period or name.**

**Parameters:**

- -Interval [StatInterval[]] (Required) Specifies the statistics intervals you want to remove. The values of this parameter can be statistics interval objects, names, or refresh periods in seconds.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.

**Examples:**

```powershell
Remove-StatInterval -Interval *
```
_Removes all the statistics intervals. Note that deleting statistics intervals is allowed only on VirtualCenter 2.0._

## Set

### `Set-StatInterval`

**This cmdlet changes the statistics interval that is specified by the provided parameters.**

**Parameters:**

- -Interval [StatInterval[]] (Required) Specifies the statistics interval you want to change.
- -SamplingPeriodSecs [Int32] (Optional) Specifies a new sampling period in seconds.
- -Server [VIServer[]] (Optional) Specifies the vCenter Server systems on which you want to run the cmdlet. If no value is provided or $null value is passed to this parameter, the command runs on the default servers. For more information about default servers, see the description of Connect-VIServer.
- -StorageTimeSecs [Int32] (Optional) Specifies a new time period in seconds, for which the statistics information is kept.

**Examples:**

```powershell
Set-StatInterval -Interval "past day" -StorageTimeSecs 700000
```
_Changes the storage time of the "past day" statistics interval._

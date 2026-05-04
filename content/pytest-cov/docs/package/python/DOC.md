---
name: package
description: "Practical pytest-cov 7.0.0 guide for pytest coverage runs, reports, xdist, and subprocess measurement"
metadata:
  languages: "python"
  versions: "7.0.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pytest-cov,python,pytest,coverage,testing,ci,toml,true,Opt-Out,CentralCovContextWarning,CovDisabledWarning,CovReportWarning,CoverageError,DistCovError,PytestCovWarning,BrokenCovConfigError,Central,ensure_topdir,finish,get_node_desc,get_width,pause,resume,sep,start,summary,CovController,DistMaster,configure_node,testnodedown,DistWorker,CovPlugin,pytest_configure_node,pytest_runtest_call,pytest_runtestloop,pytest_sessionstart,pytest_terminal_summary,pytest_testnodedown,write_heading,StoreReport,format_usage,TestContextPlugin,pytest_runtest_setup,pytest_runtest_teardown,switch_context,pytest_addoption,pytest_configure,pytest_load_initial_conftests,validate_context,validate_fail_under,validate_report"
---

# pytest-cov — package

pytest-cov: avoid already-imported warning: PYTEST_DONT_REWRITE.

## Install

```bash
pip install pytest-cov
```

## Imports

```python
import pytest_cov
```

## Symbols (76)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `CentralCovContextWarning` | Class | Indicates that dynamic_context was set to test_function instead of using the bu… |
| `CovDisabledWarning` | Class | Indicates that Coverage was manually disabled. |
| `CovReportWarning` | Class | Indicates that we failed to generate a report. |
| `CoverageError` | Class | Indicates that our coverage is too low |
| `DistCovError` | Class | Raised when dynamic_context is set to test_function and xdist is also used.  Se… |
| `PytestCovWarning` | Class | The base for all pytest-cov warnings, never raised directly. |
| `BrokenCovConfigError` | Class | Common base class for all non-exit exceptions. |
| `Central` | Class | Implementation for centralised operation. |
| `ensure_topdir` | Method |  |
| `finish` | Method | Stop coverage, save data to file and set the list of coverage objects to report… |
| `get_node_desc` | Method | Return a description of this node. |
| `get_width` | Method |  |
| `pause` | Method |  |
| `resume` | Method |  |
| `sep` | Method |  |
| `start` | Method |  |
| `summary` | Method | Produce coverage reports. |
| `CentralCovContextWarning` | Class | Indicates that dynamic_context was set to test_function instead of using the bu… |
| `CovController` | Class | Base class for different plugin implementations. |
| `ensure_topdir` | Method |  |
| `finish` | Method |  |
| `get_node_desc` | Method | Return a description of this node. |
| `get_width` | Method |  |
| `pause` | Method |  |
| `resume` | Method |  |
| `sep` | Method |  |
| `start` | Method |  |
| `summary` | Method | Produce coverage reports. |
| `DistCovError` | Class | Raised when dynamic_context is set to test_function and xdist is also used.  Se… |
| `DistMaster` | Class | Implementation for distributed master. |

_Plus 46 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `CentralCovContextWarning`

Indicates that dynamic_context was set to test_function instead of using the builtin --cov-context.

```python
pytest_cov.CentralCovContextWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CovDisabledWarning`

Indicates that Coverage was manually disabled.

```python
pytest_cov.CovDisabledWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CovReportWarning`

Indicates that we failed to generate a report.

```python
pytest_cov.CovReportWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CoverageError`

Indicates that our coverage is too low

```python
pytest_cov.CoverageError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DistCovError`

Raised when dynamic_context is set to test_function and xdist is also used.

See: https://github.com/pytest-dev/pytest-cov/issues/604

```python
pytest_cov.DistCovError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PytestCovWarning`

The base for all pytest-cov warnings, never raised directly.

```python
pytest_cov.PytestCovWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BrokenCovConfigError`

Common base class for all non-exit exceptions.

```python
pytest_cov.engine.BrokenCovConfigError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Central`

Implementation for centralised operation.

```python
pytest_cov.engine.Central(self, options: argparse.Namespace, config: Optional[object], nodeid: Optional[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `Namespace` | `—` | pos/kw |
| `config` | `Optional` | `—` | pos/kw |
| `nodeid` | `Optional` | `—` | pos/kw |

### `CentralCovContextWarning`

Indicates that dynamic_context was set to test_function instead of using the builtin --cov-context.

```python
pytest_cov.engine.CentralCovContextWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CovController`

Base class for different plugin implementations.

```python
pytest_cov.engine.CovController(self, options: argparse.Namespace, config: Optional[object], nodeid: Optional[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `Namespace` | `—` | pos/kw |
| `config` | `Optional` | `—` | pos/kw |
| `nodeid` | `Optional` | `—` | pos/kw |

### `DistCovError`

Raised when dynamic_context is set to test_function and xdist is also used.

See: https://github.com/pytest-dev/pytest-cov/issues/604

```python
pytest_cov.engine.DistCovError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DistMaster`

Implementation for distributed master.

```python
pytest_cov.engine.DistMaster(self, options: argparse.Namespace, config: Optional[object], nodeid: Optional[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `Namespace` | `—` | pos/kw |
| `config` | `Optional` | `—` | pos/kw |
| `nodeid` | `Optional` | `—` | pos/kw |

### `DistWorker`

Implementation for distributed workers.

```python
pytest_cov.engine.DistWorker(self, options: argparse.Namespace, config: Optional[object], nodeid: Optional[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `Namespace` | `—` | pos/kw |
| `config` | `Optional` | `—` | pos/kw |
| `nodeid` | `Optional` | `—` | pos/kw |

### `CovDisabledWarning`

Indicates that Coverage was manually disabled.

```python
pytest_cov.plugin.CovDisabledWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CovPlugin`

Use coverage package to produce code coverage reports.

Delegates all work to a particular implementation based on whether
this test process is centralised, a distributed master or a
distributed work…

```python
pytest_cov.plugin.CovPlugin(self, options: argparse.Namespace, pluginmanager, start=True, no_cov_should_warn=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `Namespace` | `—` | pos/kw |
| `pluginmanager` | `—` | `—` | pos/kw |
| `start` | `—` | `True` | pos/kw |
| `no_cov_should_warn` | `—` | `False` | pos/kw |

### `CovReportWarning`

Indicates that we failed to generate a report.

```python
pytest_cov.plugin.CovReportWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PytestCovWarning`

The base for all pytest-cov warnings, never raised directly.

```python
pytest_cov.plugin.PytestCovWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StoreReport`

Information about how to convert command line strings to Python objects.

Action objects are used by an ArgumentParser to represent the information
needed to parse a single argument from one or more…

```python
pytest_cov.plugin.StoreReport(self, option_strings, dest, nargs=None, const=None, default=None, type=None, choices=None, required=False, help=None, metavar=None, deprecated=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `option_strings` | `—` | `—` | pos/kw |
| `dest` | `—` | `—` | pos/kw |
| `nargs` | `—` | `None` | pos/kw |
| `const` | `—` | `None` | pos/kw |
| `default` | `—` | `None` | pos/kw |
| `type` | `—` | `None` | pos/kw |
| `choices` | `—` | `None` | pos/kw |
| `required` | `—` | `False` | pos/kw |
| `help` | `—` | `None` | pos/kw |
| `metavar` | `—` | `None` | pos/kw |
| `deprecated` | `—` | `False` | pos/kw |

### `TestContextPlugin`

```python
pytest_cov.plugin.TestContextPlugin(self, cov_controller)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cov_controller` | `—` | `—` | pos/kw |

## Functions

### `pytest_addoption`

Add options to control coverage.

```python
pytest_cov.plugin.pytest_addoption(parser)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `—` | `—` | pos/kw |

### `pytest_configure`

```python
pytest_cov.plugin.pytest_configure(config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `—` | `—` | pos/kw |

### `pytest_load_initial_conftests`

```python
pytest_cov.plugin.pytest_load_initial_conftests(early_config, parser, args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `early_config` | `—` | `—` | pos/kw |
| `parser` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | pos/kw |

### `validate_context`

```python
pytest_cov.plugin.validate_context(arg)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `arg` | `—` | `—` | pos/kw |

### `validate_fail_under`

```python
pytest_cov.plugin.validate_fail_under(num_str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `num_str` | `—` | `—` | pos/kw |

### `validate_report`

```python
pytest_cov.plugin.validate_report(arg)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `arg` | `—` | `—` | pos/kw |

## Methods

### `pytest_cov.engine.Central` methods

### `ensure_topdir`

```python
pytest_cov.engine.Central.ensure_topdir(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish`

Stop coverage, save data to file and set the list of coverage objects to report on.

```python
pytest_cov.engine.Central.finish(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_node_desc`

Return a description of this node.

```python
pytest_cov.engine.Central.get_node_desc(platform, version_info)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `platform` | `—` | `—` | pos/kw |
| `version_info` | `—` | `—` | pos/kw |

### `get_width`

```python
pytest_cov.engine.Central.get_width()
```

### `pause`

```python
pytest_cov.engine.Central.pause(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `resume`

```python
pytest_cov.engine.Central.resume(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `sep`

```python
pytest_cov.engine.Central.sep(self, stream, s, txt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |
| `s` | `—` | `—` | pos/kw |
| `txt` | `—` | `—` | pos/kw |

### `start`

```python
pytest_cov.engine.Central.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `summary`

Produce coverage reports.

```python
pytest_cov.engine.Central.summary(self, stream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |

### `pytest_cov.engine.CovController` methods

### `ensure_topdir`

```python
pytest_cov.engine.CovController.ensure_topdir(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish`

```python
pytest_cov.engine.CovController.finish(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_node_desc`

Return a description of this node.

```python
pytest_cov.engine.CovController.get_node_desc(platform, version_info)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `platform` | `—` | `—` | pos/kw |
| `version_info` | `—` | `—` | pos/kw |

### `get_width`

```python
pytest_cov.engine.CovController.get_width()
```

### `pause`

```python
pytest_cov.engine.CovController.pause(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `resume`

```python
pytest_cov.engine.CovController.resume(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `sep`

```python
pytest_cov.engine.CovController.sep(self, stream, s, txt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |
| `s` | `—` | `—` | pos/kw |
| `txt` | `—` | `—` | pos/kw |

### `start`

```python
pytest_cov.engine.CovController.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `summary`

Produce coverage reports.

```python
pytest_cov.engine.CovController.summary(self, stream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |

### `pytest_cov.engine.DistMaster` methods

### `configure_node`

Workers need to know if they are collocated and what files have moved.

```python
pytest_cov.engine.DistMaster.configure_node(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ensure_topdir`

```python
pytest_cov.engine.DistMaster.ensure_topdir(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish`

Combines coverage data and sets the list of coverage objects to report on.

```python
pytest_cov.engine.DistMaster.finish(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_node_desc`

Return a description of this node.

```python
pytest_cov.engine.DistMaster.get_node_desc(platform, version_info)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `platform` | `—` | `—` | pos/kw |
| `version_info` | `—` | `—` | pos/kw |

### `get_width`

```python
pytest_cov.engine.DistMaster.get_width()
```

### `pause`

```python
pytest_cov.engine.DistMaster.pause(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `resume`

```python
pytest_cov.engine.DistMaster.resume(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `sep`

```python
pytest_cov.engine.DistMaster.sep(self, stream, s, txt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |
| `s` | `—` | `—` | pos/kw |
| `txt` | `—` | `—` | pos/kw |

### `start`

```python
pytest_cov.engine.DistMaster.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `summary`

Produce coverage reports.

```python
pytest_cov.engine.DistMaster.summary(self, stream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |

### `testnodedown`

Collect data file name from worker.

```python
pytest_cov.engine.DistMaster.testnodedown(self, node, error)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |
| `error` | `—` | `—` | pos/kw |

### `pytest_cov.engine.DistWorker` methods

### `ensure_topdir`

```python
pytest_cov.engine.DistWorker.ensure_topdir(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish`

Stop coverage and send relevant info back to the master.

```python
pytest_cov.engine.DistWorker.finish(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_node_desc`

Return a description of this node.

```python
pytest_cov.engine.DistWorker.get_node_desc(platform, version_info)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `platform` | `—` | `—` | pos/kw |
| `version_info` | `—` | `—` | pos/kw |

### `get_width`

```python
pytest_cov.engine.DistWorker.get_width()
```

### `pause`

```python
pytest_cov.engine.DistWorker.pause(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `resume`

```python
pytest_cov.engine.DistWorker.resume(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `sep`

```python
pytest_cov.engine.DistWorker.sep(self, stream, s, txt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |
| `s` | `—` | `—` | pos/kw |
| `txt` | `—` | `—` | pos/kw |

### `start`

```python
pytest_cov.engine.DistWorker.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `summary`

Only the master reports so do nothing.

```python
pytest_cov.engine.DistWorker.summary(self, stream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |

### `pytest_cov.plugin.CovPlugin` methods

### `pytest_configure_node`

Delegate to our implementation.

Mark this hook as optional in case xdist is not installed.

```python
pytest_cov.plugin.CovPlugin.pytest_configure_node(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `pytest_runtest_call`

```python
pytest_cov.plugin.CovPlugin.pytest_runtest_call(self, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `—` | `—` | pos/kw |

### `pytest_runtestloop`

```python
pytest_cov.plugin.CovPlugin.pytest_runtestloop(self, session)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `session` | `—` | `—` | pos/kw |

### `pytest_sessionstart`

At session start determine our implementation and delegate to it.

```python
pytest_cov.plugin.CovPlugin.pytest_sessionstart(self, session)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `session` | `—` | `—` | pos/kw |

### `pytest_terminal_summary`

```python
pytest_cov.plugin.CovPlugin.pytest_terminal_summary(self, terminalreporter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `terminalreporter` | `—` | `—` | pos/kw |

### `pytest_testnodedown`

Delegate to our implementation.

Mark this hook as optional in case xdist is not installed.

```python
pytest_cov.plugin.CovPlugin.pytest_testnodedown(self, node, error)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |
| `error` | `—` | `—` | pos/kw |

### `start`

```python
pytest_cov.plugin.CovPlugin.start(self, controller_cls: type['CovController'], config=None, nodeid=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `controller_cls` | `type` | `—` | pos/kw |
| `config` | `—` | `None` | pos/kw |
| `nodeid` | `—` | `None` | pos/kw |

### `write_heading`

```python
pytest_cov.plugin.CovPlugin.write_heading(self, terminalreporter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `terminalreporter` | `—` | `—` | pos/kw |

### `pytest_cov.plugin.StoreReport` methods

### `format_usage`

```python
pytest_cov.plugin.StoreReport.format_usage(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pytest_cov.plugin.TestContextPlugin` methods

### `pytest_runtest_call`

```python
pytest_cov.plugin.TestContextPlugin.pytest_runtest_call(self, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `—` | `—` | pos/kw |

### `pytest_runtest_setup`

```python
pytest_cov.plugin.TestContextPlugin.pytest_runtest_setup(self, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `—` | `—` | pos/kw |

### `pytest_runtest_teardown`

```python
pytest_cov.plugin.TestContextPlugin.pytest_runtest_teardown(self, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `—` | `—` | pos/kw |

### `switch_context`

```python
pytest_cov.plugin.TestContextPlugin.switch_context(self, item, when)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `—` | `—` | pos/kw |
| `when` | `—` | `—` | pos/kw |


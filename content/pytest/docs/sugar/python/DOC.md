---
name: sugar
description: "pytest-sugar plugin guide for prettier pytest output, progress bars, and Playwright trace hints"
metadata:
  languages: "python"
  versions: "1.1.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pytest,python,testing,terminal,ci,playwright,ini,toml,Version-Sensitive,DeferredXdistPlugin,pytest_xdist_node_collection_finished,SugarTerminalReporter,begin_new_line,build_summary_stats_line,count,ensure_newline,flush,get_max_column_for_test_status,getreports,hasopt,insert_progress,line,overwrite,print_failure,print_teardown_sections,pytest_collection,pytest_collection_finish,pytest_collectreport,pytest_deselected,pytest_internalerror,pytest_keyboard_interrupt,pytest_plugin_registered,pytest_report_header,pytest_runtest_logfinish,pytest_runtest_logreport,pytest_runtest_logstart,pytest_runtestloop,pytest_sessionfinish,pytest_sessionstart,pytest_terminal_summary,pytest_unconfigure,pytest_warning_recorded,Theme,flatten,pytest_addoption,pytest_configure,pytest_report_teststatus,real_string_length,strip_colors,SugarReporter,ProgressBar,pytest_collection_modifyitems,pytest_runtest_protocol"
---

# pytest — sugar

pytest_sugar
~~~~~~~~~~~~

pytest-sugar is a plugin for pytest that changes the default look
and feel of pytest (e.g. progressbar, show tests that fail instantly).

:copyright: see LICENSE for details
:license: BSD, see LICENSE for more details.

## 1. Golden Rule

Use `pytest` for pytest-sugar plugin guide for prettier pytest output, progress bars, and playwright trace hints.

### Install

```bash
pip install pytest
```

### Imports

```python
import pytest
```

## 2. Core Operations

### 1. `Theme`

Theme(header: Optional[str] = 'magenta', skipped: Optional[str] = 'blue', success: Optional[str] = 'green', warning: Optional[str] = 'yellow', fail: Optional[str] = 'red', error: Optional[str] = 'red', xfailed: Optional[str] = 'green', xpassed: Optional[str] = 'red', progressbar: Optional[str] = 'g…

```python
pytest_sugar.Theme(self, header: Optional[str] = 'magenta', skipped: Optional[str] = 'blue', success: Optional[str] = 'green', warning: Optional[str] = 'yellow', fail: Optional[str] = 'red', error: Optional[str] = 'red', xfailed: Optional[str] = 'green', xpassed: Optional[str] = 'red', progressbar: Optional[str] = 'green', progressbar_fail: Optional[str] = 'red', progressbar_background: Optional[str] = 'grey', path: Optional[str] = 'cyan', symbol_passed: str = '✓', symbol_skipped: str = 's', symbol_failed: str = '⨯', symbol_failed_not_call: str = 'ₓ', symbol_xfailed_skipped: str = 'x', symbol_xfailed_failed: str = 'X', symbol_unknown: str = '?', unknown: Optional[str] = 'blue', symbol_rerun: Optional[str] = 'R', rerun: Optional[str] = 'blue') -> None
```

**Parameters:**

- `header`: `Optional` = `'magenta'`
- `skipped`: `Optional` = `'blue'`
- `success`: `Optional` = `'green'`
- `warning`: `Optional` = `'yellow'`
- `fail`: `Optional` = `'red'`
- `error`: `Optional` = `'red'`
- `xfailed`: `Optional` = `'green'`
- `xpassed`: `Optional` = `'red'`
- `progressbar`: `Optional` = `'green'`
- `progressbar_fail`: `Optional` = `'red'`
- `progressbar_background`: `Optional` = `'grey'`
- `path`: `Optional` = `'cyan'`
- `symbol_passed`: `str` = `'✓'`
- `symbol_skipped`: `str` = `'s'`
- `symbol_failed`: `str` = `'⨯'`
- `symbol_failed_not_call`: `str` = `'ₓ'`
- `symbol_xfailed_skipped`: `str` = `'x'`
- `symbol_xfailed_failed`: `str` = `'X'`
- `symbol_unknown`: `str` = `'?'`
- `unknown`: `Optional` = `'blue'`
- `symbol_rerun`: `Optional` = `'R'`
- `rerun`: `Optional` = `'blue'`

### 2. `pytest_deselected`

Update tests_count to not include deselected tests

```python
pytest_sugar.pytest_deselected(items: Sequence[_pytest.nodes.Item]) -> None
```

**Parameters:**

- `items`: `Sequence`

### 3. `DeferredXdistPlugin`

```python
pytest_sugar.DeferredXdistPlugin(self, /, *args, **kwargs)
```

**Parameters:**

- `args`
- `kwargs`

### 4. `SugarTerminalReporter`

```python
pytest_sugar.SugarTerminalReporter(self, config: _pytest.config.Config, file: Optional[TextIO] = None) -> None
```

**Parameters:**

- `config`: `Config`
- `file`: `Optional` = `None`

### 5. `flatten`

```python
pytest_sugar.flatten(seq) -> Generator[Any, NoneType, NoneType]
```

**Parameters:**

- `seq`

**Returns:** `typing.Generator[typing.Any, NoneType, NoneType]`

### 6. `pytest_addoption`

```python
pytest_sugar.pytest_addoption(parser: _pytest.config.argparsing.Parser) -> None
```

**Parameters:**

- `parser`: `Parser`

### 7. `pytest_collection_finish`

```python
pytest_sugar.pytest_collection_finish(session: _pytest.main.Session) -> None
```

**Parameters:**

- `session`: `Session`

### 8. `pytest_configure`

```python
pytest_sugar.pytest_configure(config) -> None
```

**Parameters:**

- `config`

### 9. `pytest_report_teststatus`

```python
pytest_sugar.pytest_report_teststatus(report: _pytest.reports.BaseReport) -> Optional[Tuple[str, str, str]]
```

**Parameters:**

- `report`: `BaseReport`

**Returns:** `typing.Optional[typing.Tuple[str, str, str]]`

### 10. `pytest_sessionstart`

```python
pytest_sugar.pytest_sessionstart(session: _pytest.main.Session) -> None
```

**Parameters:**

- `session`: `Session`

### 11. `real_string_length`

```python
pytest_sugar.real_string_length(string: str) -> int
```

**Parameters:**

- `string`: `str`

**Returns:** `<class 'int'>`

### 12. `strip_colors`

```python
pytest_sugar.strip_colors(text: str) -> str
```

**Parameters:**

- `text`: `str`

**Returns:** `<class 'str'>`

## API Classes Summary

| Class | Synopsis |
|-------|----------|
| `DeferredXdistPlugin` |  |
| `SugarTerminalReporter` |  |
| `Theme` | Theme(header: Optional[str] = 'magenta', skipped: Optional[str] = 'blue', success: Optional[str] =… |

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`pytest==1.1.1`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.
## API surface — pytest-sugar plugin internals

```python
from pytest_sugar import SugarTerminalReporter

class SugarReporter(SugarTerminalReporter):
    def pytest_collection_modifyitems(self, items): pass
    def pytest_runtest_logstart(self, nodeid, location): pass
    def pytest_runtest_logreport(self, report): pass
    def pytest_terminal_summary(self, terminalreporter, exitstatus, config): pass
    def pytest_sessionstart(self, session): pass
    def pytest_sessionfinish(self, session, exitstatus): pass
    def pytest_collectreport(self, report): pass
    def pytest_runtest_protocol(self, item, nextitem): pass

class ProgressBar:
    def __init__(self, total): pass
    def update(self, n=1): pass
    def render_line(self, status, name): pass
    def overwrite_line(self, message): pass
    def finalize(self): pass
```

---
name: package
description: "pytest-sugar package guide for prettier pytest output, progress bars, and Playwright trace hints"
metadata:
  languages: "python"
  versions: "1.1.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pytest-sugar,python,pytest,testing,terminal,ci,playwright,ini,toml,DeferredXdistPlugin,SugarTerminalReporter,count,flush,getreports,hasopt,line,overwrite,pytest_collection_finish,pytest_deselected,pytest_sessionstart,Theme,flatten,pytest_addoption,pytest_configure,pytest_report_teststatus,real_string_length,strip_colors"
---

# pytest-sugar — package

pytest_sugar
~~~~~~~~~~~~

pytest-sugar is a plugin for pytest that changes the default look
and feel of pytest (e.g. progressbar, show tests that fail instantly).

:copyright: see LICENSE for details
:license: BSD, see LICENSE for more details.

## 1. Golden Rule

Use `pytest-sugar` for pytest-sugar package guide for prettier pytest output, progress bars, and playwright trace hints.

### Install

```bash
pip install pytest-sugar
```

### Imports

```python
import pytest_sugar
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
- Pin the version (`pytest-sugar==1.1.1`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `pytest-sugar`

Each name below is a real top-level export of `pytest_sugar`, verified via `dir(__import__('pytest_sugar'))` against `pytest-sugar` installed from PyPI.

```python
import pytest_sugar

# Public classes
class DeferredXdistPlugin: pass
class SugarTerminalReporter: pass
class Theme: pass

# Public functions
def flatten(): pass
def pytest_addoption(): pass
def pytest_collection_finish(): pass
def pytest_configure(): pass
def pytest_deselected(): pass
def pytest_report_teststatus(): pass
def pytest_sessionstart(): pass
def real_string_length(): pass
def strip_colors(): pass
```

```python
# Verified call shapes — every name resolves in pytest_sugar.dir()
pytest_sugar.flatten()
pytest_sugar.pytest_addoption()
pytest_sugar.pytest_collection_finish()
pytest_sugar.pytest_configure()
pytest_sugar.pytest_deselected()
pytest_sugar.pytest_report_teststatus()
pytest_sugar.pytest_sessionstart()
pytest_sugar.real_string_length()
pytest_sugar.strip_colors()
```

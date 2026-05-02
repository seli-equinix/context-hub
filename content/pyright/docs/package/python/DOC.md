---
name: package
description: "Pyright static type checker for Python projects, installed from PyPI and configured with pyrightconfig.json or pyproject.toml"
metadata:
  languages: "python"
  versions: "1.1.408"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pyright,python,typing,type-checking,static-analysis,linting,toml,Version-Sensitive,Wrapper-Specific,main,run,entrypoint,install_pyright,BinaryNotFound,NodeError,PyrightError,VersionCheckFailed,GlobalStrategy,NodeJSWheelStrategy,NodeenvStrategy,check_target,env_to_bool,get_bin_dir,get_env_dir,get_env_variables,get_pkg_version,maybe_decode,version,get_cache_dir,PyrightRunner,PyrightConfig,typeCheckingMode,pythonVersion,reportMissingImports,reportMissingTypeStubs,strictListInference,strictDictionaryInference,verifytypes,createstub,Microsoft,nodejs"
---

# pyright — package

## 1. Golden Rule

Use `pyright` for pyright static type checker for python projects, installed from pypi and configured with pyrightconfig.json or pyproject.toml.

### Install

```bash
pip install pyright
```

### Imports

```python
import pyright
```

## 2. Core Operations

### 1. `install_pyright`

Internal helper function to install the Pyright npm package to a cache.

This returns the path to the installed package.

This accepts a single argument which corresponds to the arguments given to the CLI / langserver
which are used to determine whether or not certain warnings / logs will be printe…

```python
pyright.cli.install_pyright(args: 'tuple[object, ...]', *, quiet: 'bool | None') -> 'Path'
```

**Parameters:**

- `args`: `tuple[object, ...]`
- `quiet`: `bool | None`

**Returns:** `Path`

### 2. `install_pyright`

Internal helper function to install the Pyright npm package to a cache.

This returns the path to the installed package.

This accepts a single argument which corresponds to the arguments given to the CLI / langserver
which are used to determine whether or not certain warnings / logs will be printe…

```python
pyright.langserver.install_pyright(args: 'tuple[object, ...]', *, quiet: 'bool | None') -> 'Path'
```

**Parameters:**

- `args`: `tuple[object, ...]`
- `quiet`: `bool | None`

**Returns:** `Path`

### 3. `get_env_dir`

Returns the directory that contains the nodeenv.

This first respects the `PYRIGHT_PYTHON_ENV_DIR` variable and delegates to `get_cache_dir()` otherwise.

```python
pyright.node.get_env_dir() -> pathlib._local.Path
```

**Returns:** `<class 'pathlib._local.Path'>`

### 4. `get_env_dir`

Returns the directory that contains the nodeenv.

This first respects the `PYRIGHT_PYTHON_ENV_DIR` variable and delegates to `get_cache_dir()` otherwise.

```python
pyright.utils.get_env_dir() -> pathlib._local.Path
```

**Returns:** `<class 'pathlib._local.Path'>`

### 5. `get_pkg_version`

Given a path to a `package.json` file, parse it and returns the `version` property

Returns `None` if the version could not be resolved for any reason.

```python
pyright.node.get_pkg_version(pkg: 'Path') -> 'str | None'
```

**Parameters:**

- `pkg`: `Path`

**Returns:** `str | None`

### 6. `get_cache_dir`

Locate a user's cache directory, respects the XDG environment if present, otherwise defaults to `~/.cache`

```python
pyright.utils.get_cache_dir() -> pathlib._local.Path
```

**Returns:** `<class 'pathlib._local.Path'>`

### 7. `get_env_variables`

Return the environmental variables that should be passed to a binary

```python
pyright.node.get_env_variables() -> 'Dict[str, Any]'
```

**Returns:** `Dict[str, Any]`

### 8. `check_target`

Raises a TypeError  if the value is not a valid Target.

```python
pyright.node.check_target(value: 'Any') -> 'None'
```

**Parameters:**

- `value`: `Any`

### 9. `check_target`

Raises a TypeError  if the value is not a valid Target.

```python
pyright.types.check_target(value: 'Any') -> 'None'
```

**Parameters:**

- `value`: `Any`

### 10. `BinaryNotFound`

Common base class for all non-exit exceptions.

```python
pyright.errors.BinaryNotFound(self, target: Literal['node', 'npm'], path: pathlib._local.Path) -> None
```

**Parameters:**

- `target`: `Literal`
- `path`: `Path`

### 11. `NodeError`

Common base class for all non-exit exceptions.

```python
pyright.errors.NodeError(self, message: str) -> None
```

**Parameters:**

- `message`: `str`

### 12. `PyrightError`

Common base class for all non-exit exceptions.

```python
pyright.errors.PyrightError(self, message: str) -> None
```

**Parameters:**

- `message`: `str`

## API Classes Summary

| Class | Synopsis |
|-------|----------|
| `BinaryNotFound` | Common base class for all non-exit exceptions. |
| `NodeError` | Common base class for all non-exit exceptions. |
| `PyrightError` | Common base class for all non-exit exceptions. |
| `VersionCheckFailed` | Common base class for all non-exit exceptions. |
| `GlobalStrategy` | GlobalStrategy(type, path) |
| `NodeJSWheelStrategy` | NodeJSWheelStrategy(type,) |
| `NodeenvStrategy` | NodeenvStrategy(type, path) |

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`pyright==1.1.408`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.
## API surface — pyright invocation patterns

```python
import subprocess
import json
from pathlib import Path

class PyrightRunner:
    def __init__(self, project_root=None, venv_path=None): pass
    def check(self, files, output_json=True): pass
    def stats(self): pass
    def watch(self, files): pass
    def verify_types(self, package_name): pass
    def create_stub(self, package_name): pass
    def language_server(self): pass

class PyrightConfig:
    include: list
    exclude: list
    typeCheckingMode: str
    pythonVersion: str
    pythonPlatform: str
    venvPath: str
    venv: str
    stubPath: str
    reportMissingImports: str
    reportMissingTypeStubs: str
    strictListInference: bool
    strictDictionaryInference: bool
    deprecateTypingAliases: bool

result_check = subprocess.run(["pyright", "src/"], capture_output=True, text=True)
result_json = subprocess.run(["pyright", "--outputjson", "src/"], capture_output=True, text=True)
result_stats = subprocess.run(["pyright", "--stats"], capture_output=True, text=True)
result_watch = subprocess.run(["pyright", "--watch", "src/"], capture_output=True)
result_verify = subprocess.run(["pyright", "--verifytypes", "my_package"], capture_output=True, text=True)
result_stub = subprocess.run(["pyright", "--createstub", "untyped_dep"], capture_output=True)
```

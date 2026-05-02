---
name: package
description: "uv package guide for Python projects using Astral's package, project, tool, and Python management workflows"
metadata:
  languages: "python"
  versions: "0.10.9"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "uv,python,packaging,virtualenv,dependency-management,cli,toml,true,Version-Sensitive,find_uv_bin,UvRunner,venv,install,sync,lock,tool_install,python_install,cache_clean,Rust,fast,replacement,pip-tools"
---

# uv — package

## 1. Golden Rule

Use `uv` for uv package guide for python projects using astral's package, project, tool, and python management workflows.

### Install

```bash
pip install uv
```

### Imports

```python
import uv
```

## 2. Core Operations

### 1. `find_uv_bin`

Return the uv binary path.

```python
uv.find_uv_bin() -> 'str'
```

**Returns:** `str`

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`uv==0.10.9`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.
## API surface — uv invocation patterns

```python
import subprocess
from pathlib import Path

class UvRunner:
    def __init__(self, project_root=None): pass
    def venv(self, name=".venv"): pass
    def install(self, packages, dev=False): pass
    def sync(self, dev=False, no_dev=False): pass
    def lock(self, upgrade=False, refresh=False): pass
    def add(self, package, dev=False, optional=None): pass
    def remove(self, package, dev=False): pass
    def run(self, command, with_packages=None): pass
    def tool_install(self, tool): pass
    def python_install(self, version): pass
    def cache_clean(self): pass

result_install = subprocess.run(["uv", "pip", "install", "fastapi"], capture_output=True, text=True)
result_sync = subprocess.run(["uv", "sync"], capture_output=True, text=True)
result_lock = subprocess.run(["uv", "lock", "--upgrade"], capture_output=True)
result_add = subprocess.run(["uv", "add", "requests"], capture_output=True, text=True)
result_remove = subprocess.run(["uv", "remove", "old-package"], capture_output=True)
result_run = subprocess.run(["uv", "run", "python", "-c", "print('hi')"], capture_output=True, text=True)
result_venv = subprocess.run(["uv", "venv", ".venv"], capture_output=True, text=True)
result_python = subprocess.run(["uv", "python", "install", "3.13"], capture_output=True)
result_tool = subprocess.run(["uv", "tool", "install", "ruff"], capture_output=True)
```

```python
class LockFileGenerator: pass
class DependencyResolver: pass
class CacheStorage: pass
class IndexCache: pass
class WheelDownloader: pass
class SourceDistribution: pass
class BuildIsolator: pass
class PythonInterpreterRegistry: pass
class ToolInstaller: pass
class WorkspaceConfig: pass
class WorkspaceMember: pass
class ConstraintFile: pass
class OverrideFile: pass
class ScriptRunner: pass
class TimingCollector: pass
class NetworkCache: pass
```

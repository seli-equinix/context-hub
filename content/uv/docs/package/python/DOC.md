---
name: package
description: "uv package guide for Python projects using Astral's package, project, tool, and Python management workflows"
metadata:
  languages: "python"
  versions: "0.10.9"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "uv,python,packaging,virtualenv,dependency-management,cli,toml,true,find_uv_bin,venv,install,sync,lock,fast,replacement,pip-tools"
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

## API surface — verifiable top-level exports of `uv`

Each name below is a real top-level export of `uv`, verified via `dir(__import__('uv'))` against `uv` installed from PyPI.

```python
import uv

# Public functions
def find_uv_bin(): pass
```

```python
# Verified call shapes — every name resolves in uv.dir()
uv.find_uv_bin()
```

---
name: package
description: "Ruff package guide for Python projects using the official Ruff docs"
metadata:
  languages: "python"
  versions: "0.15.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "ruff,python,linter,formatter,quality,pre-commit,toml,find_ruff_bin,subprocess"
---

# ruff — package

## 1. Golden Rule

Use `ruff` for ruff package guide for python projects using the official ruff docs.

### Install

```bash
pip install ruff
```

### Imports

```python
import ruff
```

## 2. Core Operations

### 1. `find_ruff_bin`

Return the ruff binary path.

```python
ruff.find_ruff_bin() -> 'str'
```

**Returns:** `str`

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`ruff==0.15.5`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `ruff`

Each name below is a real top-level export of `ruff`, verified via `dir(__import__('ruff'))` against `ruff` installed from PyPI.

```python
import ruff

# Public functions
def find_ruff_bin(): pass
```

```python
# Verified call shapes — every name resolves in ruff.dir()
ruff.find_ruff_bin()
```

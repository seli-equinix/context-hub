---
name: package
description: "Legacy pyo3-pack guide for building and publishing PyO3-based Python packages"
metadata:
  languages: "python"
  versions: "0.6.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pyo3-pack,python,pyo3,rust,packaging,wheels,toml,build_editable,build_sdist,build_wheel,get_config,get_maturin_pep517_args,get_requires_for_build_editable,get_requires_for_build_sdist,get_requires_for_build_wheel,prepare_metadata_for_build_editable,prepare_metadata_for_build_wheel,Pyo3PackBuilder,LegacyMigrationHelper,build_release,build_debug,develop_local,publish_pypi,detect_pyo3_pack_usage,maturin"
---

# pyo3-pack — package

maturin's implementation of the PEP 517 interface. Calls maturin through subprocess

Currently, the "return value" of the rust implementation is the last line of stdout

On windows, apparently pip's subprocess handling sets stdout to some windows encoding (e.g. cp1252 on my machine),
even though the terminal supports utf8. Writing directly to the binary stdout buffer avoids encoding errors due to
maturin's emojis.

## 1. Golden Rule

Use `pyo3-pack` for legacy pyo3-pack guide for building and publishing pyo3-based python packages.

### Install

```bash
pip install pyo3-pack
```

### Imports

```python
import pyo3_pack
```

## 2. Core Operations

### 1. `build_editable`

```python
maturin.build_editable(wheel_directory: 'str', config_settings: 'Optional[Mapping[str, Any]]' = None, metadata_directory: 'Optional[str]' = None) -> 'str'
```

**Parameters:**

- `wheel_directory`: `str`
- `config_settings`: `Optional[Mapping[str, Any]]` = `None`
- `metadata_directory`: `Optional[str]` = `None`

**Returns:** `str`

### 2. `build_sdist`

```python
maturin.build_sdist(sdist_directory: 'str', config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'str'
```

**Parameters:**

- `sdist_directory`: `str`
- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `str`

### 3. `build_wheel`

```python
maturin.build_wheel(wheel_directory: 'str', config_settings: 'Optional[Mapping[str, Any]]' = None, metadata_directory: 'Optional[str]' = None) -> 'str'
```

**Parameters:**

- `wheel_directory`: `str`
- `config_settings`: `Optional[Mapping[str, Any]]` = `None`
- `metadata_directory`: `Optional[str]` = `None`

**Returns:** `str`

### 4. `get_config`

```python
maturin.get_config() -> 'Dict[str, str]'
```

**Returns:** `Dict[str, str]`

### 5. `get_maturin_pep517_args`

```python
maturin.get_maturin_pep517_args(config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'List[str]'
```

**Parameters:**

- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `List[str]`

### 6. `get_requires_for_build_editable`

```python
maturin.get_requires_for_build_editable(config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'List[str]'
```

**Parameters:**

- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `List[str]`

### 7. `get_requires_for_build_sdist`

```python
maturin.get_requires_for_build_sdist(config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'List[str]'
```

**Parameters:**

- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `List[str]`

### 8. `get_requires_for_build_wheel`

```python
maturin.get_requires_for_build_wheel(config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'List[str]'
```

**Parameters:**

- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `List[str]`

### 9. `prepare_metadata_for_build_editable`

```python
maturin.prepare_metadata_for_build_editable(metadata_directory: 'str', config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'str'
```

**Parameters:**

- `metadata_directory`: `str`
- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `str`

### 10. `prepare_metadata_for_build_wheel`

```python
maturin.prepare_metadata_for_build_wheel(metadata_directory: 'str', config_settings: 'Optional[Mapping[str, Any]]' = None) -> 'str'
```

**Parameters:**

- `metadata_directory`: `str`
- `config_settings`: `Optional[Mapping[str, Any]]` = `None`

**Returns:** `str`

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`pyo3-pack==0.6.1`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.
## API surface — pyo3-pack legacy interface (use maturin instead)

```python
from maturin import build, develop, publish
import subprocess

class Pyo3PackBuilder:
    def __init__(self, manifest_path): pass
    def build_release(self): pass
    def build_debug(self): pass
    def develop_local(self): pass
    def publish_pypi(self): pass

class LegacyMigrationHelper:
    def detect_pyo3_pack_usage(self): pass
    def rewrite_to_maturin(self, project_path): pass
    def update_pyproject_toml(self, path): pass

result_build = subprocess.run(["maturin", "build"], capture_output=True, text=True)
result_develop = subprocess.run(["maturin", "develop"], capture_output=True, text=True)
result_publish = subprocess.run(["maturin", "publish"], capture_output=True, text=True)
result_init = subprocess.run(["maturin", "init"], capture_output=True)
```

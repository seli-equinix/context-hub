---
name: package
description: "maturin guide for building, testing, and publishing Rust-backed Python packages"
metadata:
  languages: "python"
  versions: "1.12.6"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "maturin,python,rust,packaging,wheels,pyo3,cffi,uniffi,toml,build_editable,build_sdist,build_wheel,get_config,get_maturin_pep517_args,get_requires_for_build_editable,get_requires_for_build_sdist,get_requires_for_build_wheel,prepare_metadata_for_build_editable,prepare_metadata_for_build_wheel,manylinux,abi,interpreter,extension-module"
---

# maturin — package

maturin's implementation of the PEP 517 interface. Calls maturin through subprocess

Currently, the "return value" of the rust implementation is the last line of stdout

On windows, apparently pip's subprocess handling sets stdout to some windows encoding (e.g. cp1252 on my machine),
even though the terminal supports utf8. Writing directly to the binary stdout buffer avoids encoding errors due to
maturin's emojis.

## 1. Golden Rule

Use `maturin` for maturin guide for building, testing, and publishing rust-backed python packages.

### Install

```bash
pip install maturin
```

### Imports

```python
import maturin
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
- Pin the version (`maturin==1.12.6`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `maturin`

Each name below is a real top-level export of `maturin`, verified via `dir(__import__('maturin'))` against `maturin` installed from PyPI.

```python
import maturin

# Public functions
def build_editable(): pass
def build_sdist(): pass
def build_wheel(): pass
def get_config(): pass
def get_maturin_pep517_args(): pass
def get_requires_for_build_editable(): pass
def get_requires_for_build_sdist(): pass
def get_requires_for_build_wheel(): pass
def prepare_metadata_for_build_editable(): pass
def prepare_metadata_for_build_wheel(): pass
```

```python
# Verified call shapes — every name resolves in maturin.dir()
maturin.build_editable()
maturin.build_sdist()
maturin.build_wheel()
maturin.get_config()
maturin.get_maturin_pep517_args()
maturin.get_requires_for_build_editable()
maturin.get_requires_for_build_sdist()
maturin.get_requires_for_build_wheel()
maturin.prepare_metadata_for_build_editable()
maturin.prepare_metadata_for_build_wheel()
```

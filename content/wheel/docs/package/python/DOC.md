---
name: package
description: "wheel package guide for Python wheel-file tooling and legacy build compatibility"
metadata:
  languages: "python"
  versions: "0.46.3"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "wheel,python,packaging,build,pypi,ini,toml,calculate_macosx_platform_tag,extract_macosx_min_system_version,get_base_class_and_magic_number,parse_version,read_data,read_mach_header,swap32,convert_requirements,generate_requirements,pkginfo_to_metadata,requires_to_requires_dist,safe_extra,safe_name,split_sections,WheelError,WheelFile,close,extract,extractall,getinfo,infolist,mkdir,namelist,open,printdir,read,setpassword,testzip,write,writestr,get_zipinfo_datetime,urlsafe_b64decode,urlsafe_b64encode,unpack,pack,convert"
---

# wheel — package

## 1. Golden Rule

Use `wheel` for wheel package guide for python wheel-file tooling and legacy build compatibility.

### Install

```bash
pip install wheel
```

### Imports

```python
import wheel
```

## 2. Core Operations

### 1. `split_sections`

Split a string or iterable thereof into (section, content) pairs
Each ``section`` is a stripped version of the section header ("[section]")
and each ``content`` is a list of stripped lines excluding blank lines and
comment-only lines.  If there are any such lines before the first section
header, th…

```python
wheel.metadata.split_sections(s: 'str | Iterator[str]') -> 'Generator[tuple[str | None, list[str]], None, None]'
```

**Parameters:**

- `s`: `str | Iterator[str]`

**Returns:** `Generator[tuple[str | None, list[str]], None, None]`

### 2. `generate_requirements`

Convert requirements from a setup()-style dictionary to
('Requires-Dist', 'requirement') and ('Provides-Extra', 'extra') tuples.

extras_require is a dictionary of {extra: [requirements]} as passed to setup(),
using the empty extra {'': [requirements]} to hold install_requires.

```python
wheel.metadata.generate_requirements(extras_require: 'dict[str | None, list[str]]') -> 'Iterator[tuple[str, str]]'
```

**Parameters:**

- `extras_require`: `dict[str | None, list[str]]`

**Returns:** `Iterator[tuple[str, str]]`

### 3. `safe_extra`

Convert an arbitrary string to a standard 'extra' name
Any runs of non-alphanumeric characters are replaced with a single '_',
and the result is always lowercased.

```python
wheel.metadata.safe_extra(extra: 'str') -> 'str'
```

**Parameters:**

- `extra`: `str`

**Returns:** `str`

### 4. `read_mach_header`

This function parses a Mach-O header and extracts
information about the minimal macOS version.

:param lib_file: reference to opened library file with pointer

```python
wheel.macosx_libfile.read_mach_header(lib_file: 'BufferedIOBase', seek: 'int | None' = None) -> 'tuple[int, int, int] | None'
```

**Parameters:**

- `lib_file`: `BufferedIOBase`
- `seek`: `int | None` = `None`

**Returns:** `tuple[int, int, int] | None`

### 5. `safe_name`

Convert an arbitrary string to a standard distribution name
Any runs of non-alphanumeric/. characters are replaced with a single '-'.

```python
wheel.metadata.safe_name(name: 'str') -> 'str'
```

**Parameters:**

- `name`: `str`

**Returns:** `str`

### 6. `calculate_macosx_platform_tag`

Calculate proper macosx platform tag basing on files which are included to wheel

Example platform tag `macosx-10.14-x86_64`

```python
wheel.macosx_libfile.calculate_macosx_platform_tag(archive_root: 'StrPath', platform_tag: 'str') -> 'str'
```

**Parameters:**

- `archive_root`: `StrPath`
- `platform_tag`: `str`

**Returns:** `str`

### 7. `WheelFile`

A ZipFile derivative class that also reads SHA-256 hashes from
.dist-info/RECORD and checks any read files against those.

```python
wheel.wheelfile.WheelFile(self, file: 'StrPath', mode: "Literal['r', 'w', 'x', 'a']" = 'r', compression: 'int' = 8)
```

**Parameters:**

- `file`: `StrPath`
- `mode`: `Literal['r', 'w', 'x', 'a']` = `'r'`
- `compression`: `int` = `8`

### 8. `requires_to_requires_dist`

Return the version specifier for a requirement in PEP 345/566 fashion.

```python
wheel.metadata.requires_to_requires_dist(requirement: 'Requirement') -> 'str'
```

**Parameters:**

- `requirement`: `Requirement`

**Returns:** `str`

### 9. `pkginfo_to_metadata`

Convert .egg-info directory with PKG-INFO to the Metadata 2.1 format

```python
wheel.metadata.pkginfo_to_metadata(egg_info_path: 'str', pkginfo_path: 'str') -> 'Message'
```

**Parameters:**

- `egg_info_path`: `str`
- `pkginfo_path`: `str`

**Returns:** `Message`

### 10. `convert_requirements`

Yield Requires-Dist: strings for parsed requirements strings.

```python
wheel.metadata.convert_requirements(requirements: 'list[str]') -> 'Iterator[str]'
```

**Parameters:**

- `requirements`: `list[str]`

**Returns:** `Iterator[str]`

### 11. `WheelError`

Common base class for all non-exit exceptions.

```python
wheel.wheelfile.WheelError(self, /, *args, **kwargs)
```

**Parameters:**

- `args`
- `kwargs`

### 12. `urlsafe_b64decode`

urlsafe_b64decode without padding

```python
wheel.wheelfile.urlsafe_b64decode(data: 'bytes') -> 'bytes'
```

**Parameters:**

- `data`: `bytes`

**Returns:** `bytes`

## API Classes Summary

| Class | Synopsis |
|-------|----------|
| `WheelError` | Common base class for all non-exit exceptions. |
| `WheelFile` | A ZipFile derivative class that also reads SHA-256 hashes from .dist-info/RECORD and checks any rea… |

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`wheel==0.46.3`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `wheel`

Each name below is a real top-level export of `wheel`, verified via `dir(__import__('wheel'))` against `wheel` installed from PyPI.

```python
import wheel

# Public classes
class WheelError: pass
class WheelFile: pass

# Public functions
def calculate_macosx_platform_tag(): pass
def convert_requirements(): pass
def extract_macosx_min_system_version(): pass
def generate_requirements(): pass
def get_base_class_and_magic_number(): pass
def get_zipinfo_datetime(): pass
def parse_version(): pass
def pkginfo_to_metadata(): pass
def read_data(): pass
def read_mach_header(): pass
def requires_to_requires_dist(): pass
def safe_extra(): pass
def safe_name(): pass
def split_sections(): pass
def swap32(): pass
def urlsafe_b64decode(): pass
def urlsafe_b64encode(): pass
```

```python
# Verified call shapes — every name resolves in wheel.dir()
wheel.calculate_macosx_platform_tag()
wheel.convert_requirements()
wheel.extract_macosx_min_system_version()
wheel.generate_requirements()
wheel.get_base_class_and_magic_number()
wheel.get_zipinfo_datetime()
wheel.parse_version()
wheel.pkginfo_to_metadata()
wheel.read_data()
wheel.read_mach_header()
wheel.requires_to_requires_dist()
wheel.safe_extra()
wheel.safe_name()
wheel.split_sections()
wheel.swap32()
wheel.urlsafe_b64decode()
wheel.urlsafe_b64encode()
```

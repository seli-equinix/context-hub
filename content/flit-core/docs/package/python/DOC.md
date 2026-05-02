---
name: package
description: "flit-core Python build backend for packaging projects with pyproject.toml and PEP 517"
metadata:
  languages: "python"
  versions: "3.12.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "flit-core,python,packaging,pyproject,pep517,build-backend,pypi,toml,example.com,Version-Sensitive,Module,iter_files,SdistBuilder,add_setup_py,apply_includes_excludes,build,from_ini_path,prep_entry_points,select_files,build_editable,build_sdist,build_wheel,dist_info_name,get_docstring_and_version_via_ast,get_requires_for_build_editable,get_requires_for_build_sdist,get_requires_for_build_wheel,make_metadata,make_wheel_in,prepare_metadata_for_build_editable,prepare_metadata_for_build_wheel,read_flit_config,write_entry_points,InvalidVersion,Metadata,write_metadata_file,NoDocstringError,NoVersionError,ProblemInModule,VCSError,check_version,get_docstring_and_version_via_import,get_info_from_module,hash_file,is_version_str_assignment,normalise_core_metadata_name,normalise_version,normalize_dist_name,normalize_file_permissions,parse_entry_point,walk_data_dir,ConfigError,EntryPointsConflict,LoadedConfig,add_scripts,description_from_file,flatten_entrypoints,isabs_ish,name_is_valid,normalise_compound_license_expr,normalise_simple_license_expr,pep621_people,prep_toml_config,read_pep621_metadata,FilePatterns,match_dir,match_file,clean_tarinfo,load,loads,WheelBuilder,add_data_directory,add_pth,copy_module,write_metadata,write_record,main,zip_timestamp_from_env"
---

# flit-core — package

Flit's core machinery for building packages.

This package provides a standard PEP 517 API to build packages using Flit.
All the convenient development features live in the main 'flit' package.

## Install

```bash
pip install flit-core
```

## Imports

```python
import flit_core
```

## Symbols (88)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Module` | Class | This represents the module/package that we are going to distribute |
| `iter_files` | Method | Iterate over the files contained in this module.  Yields absolute paths - calle… |
| `SdistBuilder` | Class | Builds a minimal sdist  These minimal sdists should work for PEP 517. The class… |
| `add_setup_py` | Method | No-op here; overridden in flit to generate setup.py |
| `apply_includes_excludes` | Method |  |
| `build` | Method |  |
| `from_ini_path` | Method |  |
| `prep_entry_points` | Method |  |
| `select_files` | Method | Pick which files from the source tree will be included in the sdist  This is ov… |
| `build_editable` | Function | Builds an "editable" wheel, places it in wheel_directory |
| `build_sdist` | Function | Builds an sdist, places it in sdist_directory |
| `build_wheel` | Function | Builds a wheel, places it in wheel_directory |
| `dist_info_name` | Function | Get the correct name of the .dist-info folder |
| `get_docstring_and_version_via_ast` | Function | Return a tuple like (docstring, version) for the given module, extracted by par… |
| `get_requires_for_build_editable` | Function | Returns a list of requirements for building, as strings |
| `get_requires_for_build_sdist` | Function | Returns a list of requirements for building, as strings |
| `get_requires_for_build_wheel` | Function | Returns a list of requirements for building, as strings |
| `make_metadata` | Function |  |
| `make_wheel_in` | Function |  |
| `prepare_metadata_for_build_editable` | Function | Creates {metadata_directory}/foo-1.2.dist-info |
| `prepare_metadata_for_build_wheel` | Function | Creates {metadata_directory}/foo-1.2.dist-info |
| `read_flit_config` | Function | Read and check the `pyproject.toml` file with data about the package. |
| `write_entry_points` | Function | Write entry_points.txt from a two-level dict  Sorts on keys to ensure results a… |
| `InvalidVersion` | Class | Inappropriate argument value (of correct type). |
| `Metadata` | Class |  |
| `write_metadata_file` | Method | Write out metadata in the email headers format |
| `Module` | Class | This represents the module/package that we are going to distribute |
| `iter_files` | Method | Iterate over the files contained in this module.  Yields absolute paths - calle… |
| `NoDocstringError` | Class | Inappropriate argument value (of correct type). |
| `NoVersionError` | Class | Inappropriate argument value (of correct type). |
| `ProblemInModule` | Class | Inappropriate argument value (of correct type). |
| `VCSError` | Class | Common base class for all non-exit exceptions. |
| `check_version` | Function | Check whether a given version string match PEP 440, and do normalisation.  Rais… |
| `dist_info_name` | Function | Get the correct name of the .dist-info folder |
| `get_docstring_and_version_via_ast` | Function | Return a tuple like (docstring, version) for the given module, extracted by par… |
| `get_docstring_and_version_via_import` | Function | Return a tuple like (docstring, version) for the given module, extracted by imp… |
| `get_info_from_module` | Function | Load the module/package, get its docstring and __version__ |
| `hash_file` | Function |  |
| `is_version_str_assignment` | Function | Check if *node* is a simple string assignment to __version__ |
| `make_metadata` | Function |  |
| `normalise_core_metadata_name` | Function | Normalise a project or extra name (as in PEP 503, also PEP 685) |
| `normalise_version` | Function | Normalise version number according to rules in PEP 440  Raises InvalidVersion i… |
| `normalize_dist_name` | Function | Normalizes a name and a PEP 440 version  The resulting string is valid as dist-… |
| `normalize_file_permissions` | Function | Normalize the permission bits in the st_mode field from stat to 644/755  Popula… |
| `parse_entry_point` | Function | Check and parse a 'package.module:func' style entry point specification.  Retur… |
| `walk_data_dir` | Function | Iterate over the files in the given data directory.  Yields paths prefixed with… |
| `write_entry_points` | Function | Write entry_points.txt from a two-level dict  Sorts on keys to ensure results a… |
| `ConfigError` | Class | Inappropriate argument value (of correct type). |
| `EntryPointsConflict` | Class | Inappropriate argument value (of correct type). |
| `LoadedConfig` | Class |  |
| `add_scripts` | Method |  |
| `description_from_file` | Function |  |
| `flatten_entrypoints` | Function | Flatten nested entrypoints dicts.  Entry points group names can include dots. B… |
| `isabs_ish` | Function | Like os.path.isabs(), but Windows paths from a drive root count as absolute  is… |
| `name_is_valid` | Function |  |
| `normalise_compound_license_expr` | Function | Validate and normalise a compund SPDX license expression.  Per the specificatio… |
| `normalise_core_metadata_name` | Function | Normalise a project or extra name (as in PEP 503, also PEP 685) |
| `normalise_simple_license_expr` | Function | Normalise a simple SPDX license expression.  https://spdx.github.io/spdx-spec/v… |
| `normalise_version` | Function | Normalise version number according to rules in PEP 440  Raises InvalidVersion i… |
| `pep621_people` | Function | Convert authors/maintainers from PEP 621 to core metadata fields |
| `prep_toml_config` | Function | Validate config loaded from pyproject.toml and prepare common metadata  Returns… |
| `read_flit_config` | Function | Read and check the `pyproject.toml` file with data about the package. |
| `read_pep621_metadata` | Function |  |
| `FilePatterns` | Class | Manage a set of file inclusion/exclusion patterns relative to basedir |
| `match_dir` | Method |  |
| `match_file` | Method |  |
| `SdistBuilder` | Class | Builds a minimal sdist  These minimal sdists should work for PEP 517. The class… |
| `add_setup_py` | Method | No-op here; overridden in flit to generate setup.py |
| `apply_includes_excludes` | Method |  |
| `build` | Method |  |
| `from_ini_path` | Method |  |
| `prep_entry_points` | Method |  |
| `select_files` | Method | Pick which files from the source tree will be included in the sdist  This is ov… |
| `clean_tarinfo` | Function | Clean metadata from a TarInfo object to make it more reproducible.  - Set uid &… |
| `load` | Function | Parse TOML from a binary file object. |
| `loads` | Function | Parse TOML from a string. |
| `normalise_version` | Function | Normalise version number according to rules in PEP 440  Raises InvalidVersion i… |
| `WheelBuilder` | Class |  |
| `add_data_directory` | Method |  |
| `add_pth` | Method |  |
| `build` | Method |  |
| `copy_module` | Method |  |
| `from_ini_path` | Method |  |
| `write_metadata` | Method |  |
| `write_record` | Method |  |
| `main` | Function |  |
| `make_wheel_in` | Function |  |
| `zip_timestamp_from_env` | Function | Prepare a timestamp from $SOURCE_DATE_EPOCH, if set |

## Classes

### `Module`

This represents the module/package that we are going to distribute

```python
flit_core.buildapi.Module(self, name, directory=PosixPath('.'))
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `directory` | `—` | `PosixPath('.')` | pos/kw |

### `SdistBuilder`

Builds a minimal sdist

These minimal sdists should work for PEP 517.
The class is extended in flit.sdist to make a more 'full fat' sdist,
which is what should normally be published to PyPI.

```python
flit_core.buildapi.SdistBuilder(self, module, metadata, cfgdir, reqs_by_extra, entrypoints, extra_files, data_directory, include_patterns=(), exclude_patterns=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `—` | `—` | pos/kw |
| `metadata` | `—` | `—` | pos/kw |
| `cfgdir` | `—` | `—` | pos/kw |
| `reqs_by_extra` | `—` | `—` | pos/kw |
| `entrypoints` | `—` | `—` | pos/kw |
| `extra_files` | `—` | `—` | pos/kw |
| `data_directory` | `—` | `—` | pos/kw |
| `include_patterns` | `—` | `()` | pos/kw |
| `exclude_patterns` | `—` | `()` | pos/kw |

### `InvalidVersion`

Inappropriate argument value (of correct type).

```python
flit_core.common.InvalidVersion(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Metadata`

```python
flit_core.common.Metadata(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `Module`

This represents the module/package that we are going to distribute

```python
flit_core.common.Module(self, name, directory=PosixPath('.'))
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `directory` | `—` | `PosixPath('.')` | pos/kw |

### `NoDocstringError`

Inappropriate argument value (of correct type).

```python
flit_core.common.NoDocstringError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NoVersionError`

Inappropriate argument value (of correct type).

```python
flit_core.common.NoVersionError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ProblemInModule`

Inappropriate argument value (of correct type).

```python
flit_core.common.ProblemInModule(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `VCSError`

Common base class for all non-exit exceptions.

```python
flit_core.common.VCSError(self, msg, directory)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `msg` | `—` | `—` | pos/kw |
| `directory` | `—` | `—` | pos/kw |

### `ConfigError`

Inappropriate argument value (of correct type).

```python
flit_core.config.ConfigError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `EntryPointsConflict`

Inappropriate argument value (of correct type).

```python
flit_core.config.EntryPointsConflict(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LoadedConfig`

```python
flit_core.config.LoadedConfig(self)
```

### `FilePatterns`

Manage a set of file inclusion/exclusion patterns relative to basedir

```python
flit_core.sdist.FilePatterns(self, patterns, basedir)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `patterns` | `—` | `—` | pos/kw |
| `basedir` | `—` | `—` | pos/kw |

### `SdistBuilder`

Builds a minimal sdist

These minimal sdists should work for PEP 517.
The class is extended in flit.sdist to make a more 'full fat' sdist,
which is what should normally be published to PyPI.

```python
flit_core.sdist.SdistBuilder(self, module, metadata, cfgdir, reqs_by_extra, entrypoints, extra_files, data_directory, include_patterns=(), exclude_patterns=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `—` | `—` | pos/kw |
| `metadata` | `—` | `—` | pos/kw |
| `cfgdir` | `—` | `—` | pos/kw |
| `reqs_by_extra` | `—` | `—` | pos/kw |
| `entrypoints` | `—` | `—` | pos/kw |
| `extra_files` | `—` | `—` | pos/kw |
| `data_directory` | `—` | `—` | pos/kw |
| `include_patterns` | `—` | `()` | pos/kw |
| `exclude_patterns` | `—` | `()` | pos/kw |

### `WheelBuilder`

```python
flit_core.wheel.WheelBuilder(self, directory, module, metadata, entrypoints, target_fp, data_directory)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |
| `metadata` | `—` | `—` | pos/kw |
| `entrypoints` | `—` | `—` | pos/kw |
| `target_fp` | `—` | `—` | pos/kw |
| `data_directory` | `—` | `—` | pos/kw |

## Functions

### `build_editable`

Builds an "editable" wheel, places it in wheel_directory

```python
flit_core.buildapi.build_editable(wheel_directory, config_settings=None, metadata_directory=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `wheel_directory` | `—` | `—` | pos/kw |
| `config_settings` | `—` | `None` | pos/kw |
| `metadata_directory` | `—` | `None` | pos/kw |

### `build_sdist`

Builds an sdist, places it in sdist_directory

```python
flit_core.buildapi.build_sdist(sdist_directory, config_settings=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sdist_directory` | `—` | `—` | pos/kw |
| `config_settings` | `—` | `None` | pos/kw |

### `build_wheel`

Builds a wheel, places it in wheel_directory

```python
flit_core.buildapi.build_wheel(wheel_directory, config_settings=None, metadata_directory=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `wheel_directory` | `—` | `—` | pos/kw |
| `config_settings` | `—` | `None` | pos/kw |
| `metadata_directory` | `—` | `None` | pos/kw |

### `dist_info_name`

Get the correct name of the .dist-info folder

```python
flit_core.buildapi.dist_info_name(distribution, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `distribution` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `get_docstring_and_version_via_ast`

Return a tuple like (docstring, version) for the given module,
extracted by parsing its AST.

```python
flit_core.buildapi.get_docstring_and_version_via_ast(target)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target` | `—` | `—` | pos/kw |

### `get_requires_for_build_editable`

Returns a list of requirements for building, as strings

```python
flit_core.buildapi.get_requires_for_build_editable(config_settings=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_settings` | `—` | `None` | pos/kw |

### `get_requires_for_build_sdist`

Returns a list of requirements for building, as strings

```python
flit_core.buildapi.get_requires_for_build_sdist(config_settings=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_settings` | `—` | `None` | pos/kw |

### `get_requires_for_build_wheel`

Returns a list of requirements for building, as strings

```python
flit_core.buildapi.get_requires_for_build_wheel(config_settings=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_settings` | `—` | `None` | pos/kw |

### `make_metadata`

```python
flit_core.buildapi.make_metadata(module, ini_info)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `—` | `—` | pos/kw |
| `ini_info` | `—` | `—` | pos/kw |

### `make_wheel_in`

```python
flit_core.buildapi.make_wheel_in(ini_path, wheel_directory, editable=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ini_path` | `—` | `—` | pos/kw |
| `wheel_directory` | `—` | `—` | pos/kw |
| `editable` | `—` | `False` | pos/kw |

### `prepare_metadata_for_build_editable`

Creates {metadata_directory}/foo-1.2.dist-info

```python
flit_core.buildapi.prepare_metadata_for_build_editable(metadata_directory, config_settings=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata_directory` | `—` | `—` | pos/kw |
| `config_settings` | `—` | `None` | pos/kw |

### `prepare_metadata_for_build_wheel`

Creates {metadata_directory}/foo-1.2.dist-info

```python
flit_core.buildapi.prepare_metadata_for_build_wheel(metadata_directory, config_settings=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata_directory` | `—` | `—` | pos/kw |
| `config_settings` | `—` | `None` | pos/kw |

### `read_flit_config`

Read and check the `pyproject.toml` file with data about the package.

```python
flit_core.buildapi.read_flit_config(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `write_entry_points`

Write entry_points.txt from a two-level dict

Sorts on keys to ensure results are reproducible.

```python
flit_core.buildapi.write_entry_points(d, fp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `fp` | `—` | `—` | pos/kw |

### `check_version`

Check whether a given version string match PEP 440, and do normalisation.

Raise InvalidVersion/NoVersionError with relevant information if
version is invalid.

Log a warning if the version is not ca…

```python
flit_core.common.check_version(version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `—` | `—` | pos/kw |

### `dist_info_name`

Get the correct name of the .dist-info folder

```python
flit_core.common.dist_info_name(distribution, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `distribution` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `get_docstring_and_version_via_ast`

Return a tuple like (docstring, version) for the given module,
extracted by parsing its AST.

```python
flit_core.common.get_docstring_and_version_via_ast(target)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target` | `—` | `—` | pos/kw |

### `get_docstring_and_version_via_import`

Return a tuple like (docstring, version) for the given module,
extracted by importing the module and pulling __doc__ & __version__
from it.

```python
flit_core.common.get_docstring_and_version_via_import(target)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target` | `—` | `—` | pos/kw |

### `get_info_from_module`

Load the module/package, get its docstring and __version__

```python
flit_core.common.get_info_from_module(target, for_fields=('version', 'description'))
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target` | `—` | `—` | pos/kw |
| `for_fields` | `—` | `('version', 'description')` | pos/kw |

### `hash_file`

```python
flit_core.common.hash_file(path, algorithm='sha256')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `algorithm` | `—` | `'sha256'` | pos/kw |

### `is_version_str_assignment`

Check if *node* is a simple string assignment to __version__

```python
flit_core.common.is_version_str_assignment(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `make_metadata`

```python
flit_core.common.make_metadata(module, ini_info)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `—` | `—` | pos/kw |
| `ini_info` | `—` | `—` | pos/kw |

### `normalise_core_metadata_name`

Normalise a project or extra name (as in PEP 503, also PEP 685)

```python
flit_core.common.normalise_core_metadata_name(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `normalise_version`

Normalise version number according to rules in PEP 440

Raises InvalidVersion if the version does not match PEP 440. This can be
overridden with the FLIT_ALLOW_INVALID environment variable.

https://…

```python
flit_core.common.normalise_version(orig_version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `orig_version` | `—` | `—` | pos/kw |

### `normalize_dist_name`

Normalizes a name and a PEP 440 version

The resulting string is valid as dist-info folder name
and as first part of a wheel filename

See https://packaging.python.org/specifications/binary-distribut…

```python
flit_core.common.normalize_dist_name(name: str, version: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `normalize_file_permissions`

Normalize the permission bits in the st_mode field from stat to 644/755

Popular VCSs only track whether a file is executable or not. The exact
permissions can vary on systems with different umasks.…

```python
flit_core.common.normalize_file_permissions(st_mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `st_mode` | `—` | `—` | pos/kw |

### `parse_entry_point`

Check and parse a 'package.module:func' style entry point specification.

Returns (modulename, funcname)

```python
flit_core.common.parse_entry_point(ep)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ep` | `—` | `—` | pos/kw |

### `walk_data_dir`

Iterate over the files in the given data directory.

Yields paths prefixed with data_directory - caller may want to make them
relative to that. Excludes any __pycache__ subdirectories.

```python
flit_core.common.walk_data_dir(data_directory)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data_directory` | `—` | `—` | pos/kw |

### `write_entry_points`

Write entry_points.txt from a two-level dict

Sorts on keys to ensure results are reproducible.

```python
flit_core.common.write_entry_points(d, fp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `fp` | `—` | `—` | pos/kw |

### `description_from_file`

```python
flit_core.config.description_from_file(rel_path: str, proj_dir: pathlib._local.Path, guess_mimetype=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `rel_path` | `str` | `—` | pos/kw |
| `proj_dir` | `Path` | `—` | pos/kw |
| `guess_mimetype` | `—` | `True` | pos/kw |

### `flatten_entrypoints`

Flatten nested entrypoints dicts.

Entry points group names can include dots. But dots in TOML make nested
dictionaries:

[entrypoints.a.b]    # {'entrypoints': {'a': {'b': {}}}}

The proper way to a…

```python
flit_core.config.flatten_entrypoints(ep)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ep` | `—` | `—` | pos/kw |

### `isabs_ish`

Like os.path.isabs(), but Windows paths from a drive root count as absolute

isabs() worked this way up to Python 3.12 (inclusive), and where we reject
absolute paths, we also want to reject these od…

```python
flit_core.config.isabs_ish(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `name_is_valid`

```python
flit_core.config.name_is_valid(name) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `normalise_compound_license_expr`

Validate and normalise a compund SPDX license expression.

Per the specification, licence expression operators (AND, OR and WITH)
are matched case-sensitively. The WITH operator is not currently supp…

```python
flit_core.config.normalise_compound_license_expr(s: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `normalise_core_metadata_name`

Normalise a project or extra name (as in PEP 503, also PEP 685)

```python
flit_core.config.normalise_core_metadata_name(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `normalise_simple_license_expr`

Normalise a simple SPDX license expression.

https://spdx.github.io/spdx-spec/v2.2.2/SPDX-license-expressions/#d3-simple-license-expressions

```python
flit_core.config.normalise_simple_license_expr(s: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `normalise_version`

Normalise version number according to rules in PEP 440

Raises InvalidVersion if the version does not match PEP 440. This can be
overridden with the FLIT_ALLOW_INVALID environment variable.

https://…

```python
flit_core.config.normalise_version(orig_version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `orig_version` | `—` | `—` | pos/kw |

### `pep621_people`

Convert authors/maintainers from PEP 621 to core metadata fields

```python
flit_core.config.pep621_people(people, group_name='author') -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `people` | `—` | `—` | pos/kw |
| `group_name` | `—` | `'author'` | pos/kw |

**Returns:** `<class 'dict'>`

### `prep_toml_config`

Validate config loaded from pyproject.toml and prepare common metadata

Returns a LoadedConfig object.

```python
flit_core.config.prep_toml_config(d, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `read_flit_config`

Read and check the `pyproject.toml` file with data about the package.

```python
flit_core.config.read_flit_config(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `read_pep621_metadata`

```python
flit_core.config.read_pep621_metadata(proj, path) -> flit_core.config.LoadedConfig
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `proj` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

**Returns:** `<class 'flit_core.config.LoadedConfig'>`

### `clean_tarinfo`

Clean metadata from a TarInfo object to make it more reproducible.

- Set uid & gid to 0
- Set uname and gname to ""
- Normalise permissions to 644 or 755
- Set mtime if not None

```python
flit_core.sdist.clean_tarinfo(ti, mtime=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ti` | `—` | `—` | pos/kw |
| `mtime` | `—` | `None` | pos/kw |

### `load`

Parse TOML from a binary file object.

```python
flit_core.vendor.tomli.load(fp: <class 'BinaryIO'>, *, parse_float: Callable[[str], Any] = <class 'float'>) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fp` | `BinaryIO` | `—` | pos/kw |
| `parse_float` | `Callable` | `<class 'float'>` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `loads`

Parse TOML from a string.

```python
flit_core.vendor.tomli.loads(s: str, *, parse_float: Callable[[str], Any] = <class 'float'>) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `str` | `—` | pos/kw |
| `parse_float` | `Callable` | `<class 'float'>` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `normalise_version`

Normalise version number according to rules in PEP 440

Raises InvalidVersion if the version does not match PEP 440. This can be
overridden with the FLIT_ALLOW_INVALID environment variable.

https://…

```python
flit_core.versionno.normalise_version(orig_version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `orig_version` | `—` | `—` | pos/kw |

### `main`

```python
flit_core.wheel.main(argv=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `—` | `None` | pos/kw |

### `make_wheel_in`

```python
flit_core.wheel.make_wheel_in(ini_path, wheel_directory, editable=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ini_path` | `—` | `—` | pos/kw |
| `wheel_directory` | `—` | `—` | pos/kw |
| `editable` | `—` | `False` | pos/kw |

### `zip_timestamp_from_env`

Prepare a timestamp from $SOURCE_DATE_EPOCH, if set

```python
flit_core.wheel.zip_timestamp_from_env() -> Optional[tuple]
```

**Returns:** `typing.Optional[tuple]`

## Methods

### `flit_core.buildapi.Module` methods

### `iter_files`

Iterate over the files contained in this module.

Yields absolute paths - caller may want to make them relative.
Excludes any __pycache__ and *.pyc files.

```python
flit_core.buildapi.Module.iter_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `flit_core.buildapi.SdistBuilder` methods

### `add_setup_py`

No-op here; overridden in flit to generate setup.py

```python
flit_core.buildapi.SdistBuilder.add_setup_py(self, files_to_add, target_tarfile)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `files_to_add` | `—` | `—` | pos/kw |
| `target_tarfile` | `—` | `—` | pos/kw |

### `apply_includes_excludes`

```python
flit_core.buildapi.SdistBuilder.apply_includes_excludes(self, files)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `files` | `—` | `—` | pos/kw |

### `build`

```python
flit_core.buildapi.SdistBuilder.build(self, target_dir, gen_setup_py=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `target_dir` | `—` | `—` | pos/kw |
| `gen_setup_py` | `—` | `True` | pos/kw |

### `from_ini_path`

```python
flit_core.buildapi.SdistBuilder.from_ini_path(ini_path: pathlib._local.Path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ini_path` | `Path` | `—` | pos/kw |

### `prep_entry_points`

```python
flit_core.buildapi.SdistBuilder.prep_entry_points(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `select_files`

Pick which files from the source tree will be included in the sdist

This is overridden in flit itself to use information from a VCS to
include tests, docs, etc. for a 'gold standard' sdist.

```python
flit_core.buildapi.SdistBuilder.select_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `flit_core.common.Metadata` methods

### `write_metadata_file`

Write out metadata in the email headers format

```python
flit_core.common.Metadata.write_metadata_file(self, fp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `fp` | `—` | `—` | pos/kw |

### `flit_core.common.Module` methods

### `iter_files`

Iterate over the files contained in this module.

Yields absolute paths - caller may want to make them relative.
Excludes any __pycache__ and *.pyc files.

```python
flit_core.common.Module.iter_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `flit_core.config.LoadedConfig` methods

### `add_scripts`

```python
flit_core.config.LoadedConfig.add_scripts(self, scripts_dict)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scripts_dict` | `—` | `—` | pos/kw |

### `flit_core.sdist.FilePatterns` methods

### `match_dir`

```python
flit_core.sdist.FilePatterns.match_dir(self, rel_path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `rel_path` | `—` | `—` | pos/kw |

### `match_file`

```python
flit_core.sdist.FilePatterns.match_file(self, rel_path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `rel_path` | `—` | `—` | pos/kw |

### `flit_core.sdist.SdistBuilder` methods

### `add_setup_py`

No-op here; overridden in flit to generate setup.py

```python
flit_core.sdist.SdistBuilder.add_setup_py(self, files_to_add, target_tarfile)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `files_to_add` | `—` | `—` | pos/kw |
| `target_tarfile` | `—` | `—` | pos/kw |

### `apply_includes_excludes`

```python
flit_core.sdist.SdistBuilder.apply_includes_excludes(self, files)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `files` | `—` | `—` | pos/kw |

### `build`

```python
flit_core.sdist.SdistBuilder.build(self, target_dir, gen_setup_py=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `target_dir` | `—` | `—` | pos/kw |
| `gen_setup_py` | `—` | `True` | pos/kw |

### `from_ini_path`

```python
flit_core.sdist.SdistBuilder.from_ini_path(ini_path: pathlib._local.Path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ini_path` | `Path` | `—` | pos/kw |

### `prep_entry_points`

```python
flit_core.sdist.SdistBuilder.prep_entry_points(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `select_files`

Pick which files from the source tree will be included in the sdist

This is overridden in flit itself to use information from a VCS to
include tests, docs, etc. for a 'gold standard' sdist.

```python
flit_core.sdist.SdistBuilder.select_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `flit_core.wheel.WheelBuilder` methods

### `add_data_directory`

```python
flit_core.wheel.WheelBuilder.add_data_directory(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `add_pth`

```python
flit_core.wheel.WheelBuilder.add_pth(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `build`

```python
flit_core.wheel.WheelBuilder.build(self, editable=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `editable` | `—` | `False` | pos/kw |

### `copy_module`

```python
flit_core.wheel.WheelBuilder.copy_module(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_ini_path`

```python
flit_core.wheel.WheelBuilder.from_ini_path(ini_path, target_fp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ini_path` | `—` | `—` | pos/kw |
| `target_fp` | `—` | `—` | pos/kw |

### `write_metadata`

```python
flit_core.wheel.WheelBuilder.write_metadata(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `write_record`

```python
flit_core.wheel.WheelBuilder.write_record(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |


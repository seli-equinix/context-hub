---
name: package
description: "pip-tools package guide for Python projects using pip-compile and pip-sync to produce reproducible dependency locks"
metadata:
  languages: "python"
  versions: "7.5.3"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pip-tools,python,pip-compile,pip-sync,packaging,dependencies,toml,false,pypi.mycompany.example,Version-Sensitive,ProjectMetadata,StaticProjectMetadata,build_project_metadata,maybe_statically_parse_project_metadata,CorruptCacheError,DependencyCache,as_cache_key,clear,reverse_dependencies,write_cache,PipToolsError,as_tuple,key_from_req,lookup_table_from_tuples,read_cache_file,IncompatibleRequirements,NoCandidateFound,LogContext,debug,error,indentation,info,log,reset,warning,LocalRequirementsRepository,allow_all_wheels,clear_caches,find_best_match,get_dependencies,get_hashes,PyPIRepository,find_all_candidates,resolve_reqs,BaseRepository,ireq_satisfied_by_existing_pin,key_from_ireq,FileStream,candidate_version,create_wheel_cache,is_pinned_requirement,is_url_requirement,lookup_table,open_local_or_remote_file,BacktrackingResolver,resolve,resolve_hashes,BaseResolver,LegacyResolver,get_best_match,RequirementSummary,combine_install_requirements,format_requirement,format_specifier,omit_list_value,strip_extras,OutputWriter,write,write_find_links,write_flags,write_format_controls,write_header,write_index_options,write_trusted_hosts,dedup,drop_extras,filter_deprecated_pip_args,parse_requirements,override_defaults_from_config_file,Distribution,from_pip_distribution,flat_map,get_required_pip_specification,get_sys_path_for_python_executable,dependency_tree,diff,diff_key_from_ireq,diff_key_from_req"
---

# pip-tools — package

## Install

```bash
pip install pip-tools
```

## Imports

```python
import pip_tools
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `ProjectMetadata` | Class | ProjectMetadata(extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirem… |
| `StaticProjectMetadata` | Class | StaticProjectMetadata(extras: 'tuple[str, ...]', requirements: 'tuple[InstallRe… |
| `build_project_metadata` | Function | Return the metadata for a project.  First, optionally attempt to determine the… |
| `maybe_statically_parse_project_metadata` | Function | Return the metadata for a project, if it can be statically parsed from ``pyproj… |
| `CorruptCacheError` | Class | Common base class for all non-exit exceptions. |
| `DependencyCache` | Class | Create new persistent dependency cache for the current Python version.  The cac… |
| `as_cache_key` | Method | Given a requirement, return its cache key.  This behavior is a little weird in… |
| `clear` | Method |  |
| `reverse_dependencies` | Method | Return a lookup table of reverse dependencies for all the given ireqs.  Since t… |
| `write_cache` | Method | Write the cache to disk as JSON. |
| `PipToolsError` | Class | Common base class for all non-exit exceptions. |
| `as_tuple` | Function | Pull out the (name: str, version:str, extras:(str)) tuple from the pinned Insta… |
| `key_from_req` | Function | Get an all-lowercase version of the requirement's name.  **Note:** If the argum… |
| `lookup_table_from_tuples` | Function | Build a dict-based lookup table (index) elegantly. |
| `read_cache_file` | Function |  |
| `IncompatibleRequirements` | Class | Common base class for all non-exit exceptions. |
| `NoCandidateFound` | Class | Common base class for all non-exit exceptions. |
| `PipToolsError` | Class | Common base class for all non-exit exceptions. |
| `LogContext` | Class |  |
| `debug` | Method |  |
| `error` | Method |  |
| `indentation` | Method | Increase indentation. |
| `info` | Method |  |
| `log` | Method |  |
| `reset` | Method | Reset logger to initial state. |
| `warning` | Method |  |
| `LocalRequirementsRepository` | Class | The LocalRequirementsRepository proxied the _real_ repository by first checking… |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `PyPIRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions… |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_all_candidates` | Method |  |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given an InstallRequirement, return a set of hashes that represent all of the f… |
| `resolve_reqs` | Method |  |
| `BaseRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `BaseRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `LocalRequirementsRepository` | Class | The LocalRequirementsRepository proxied the _real_ repository by first checking… |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `PyPIRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions… |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_all_candidates` | Method |  |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given an InstallRequirement, return a set of hashes that represent all of the f… |
| `resolve_reqs` | Method |  |
| `as_tuple` | Function | Pull out the (name: str, version:str, extras:(str)) tuple from the pinned Insta… |
| `ireq_satisfied_by_existing_pin` | Function | Return :py:data:`True` if the given ``InstallRequirement`` is satisfied by the… |
| `key_from_ireq` | Function | Get a standardized key for an InstallRequirement. |
| `BaseRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `FileStream` | Class | FileStream(stream, size) |
| `NoCandidateFound` | Class | Common base class for all non-exit exceptions. |
| `PyPIRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions… |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_all_candidates` | Method |  |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given an InstallRequirement, return a set of hashes that represent all of the f… |
| `resolve_reqs` | Method |  |
| `as_tuple` | Function | Pull out the (name: str, version:str, extras:(str)) tuple from the pinned Insta… |
| `candidate_version` | Function |  |
| `create_wheel_cache` | Function |  |
| `is_pinned_requirement` | Function | Return whether an InstallRequirement is a "pinned" requirement.  An InstallRequ… |
| `is_url_requirement` | Function | Return :py:data:`True` if requirement was specified as a path or URL.  ``ireq.o… |
| `lookup_table` | Function | Build a dict-based lookup table (index) elegantly. |
| `open_local_or_remote_file` | Function | Open local or remote file for reading.  :type link: pip.index.Link :type sessio… |
| `BacktrackingResolver` | Class | A wrapper for the backtracking (or 2020) resolver. |
| `resolve` | Method | Resolve given ireqs.  Find concrete package versions for all the given InstallR… |
| `resolve_hashes` | Method | Find acceptable hashes for all of the given ``InstallRequirement``\ s. |
| `BaseRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `BaseResolver` | Class |  |
| `resolve` | Method | Find concrete package versions for all the given InstallRequirements and their… |
| `resolve_hashes` | Method | Find acceptable hashes for all of the given ``InstallRequirement``\ s. |
| `DependencyCache` | Class | Create new persistent dependency cache for the current Python version.  The cac… |
| `as_cache_key` | Method | Given a requirement, return its cache key.  This behavior is a little weird in… |
| `clear` | Method |  |
| `reverse_dependencies` | Method | Return a lookup table of reverse dependencies for all the given ireqs.  Since t… |
| `write_cache` | Method | Write the cache to disk as JSON. |
| `LegacyResolver` | Class | Wrapper for the (deprecated) legacy dependency resolver. |
| `get_best_match` | Method | Return a (pinned or editable) InstallRequirement.  This indicates the best matc… |
| `resolve` | Method | Find concrete package versions for all the given ``InstallRequirement``\ s and… |
| `resolve_hashes` | Method | Find acceptable hashes for all of the given ``InstallRequirement``\ s. |
| `PipToolsError` | Class | Common base class for all non-exit exceptions. |
| `RequirementSummary` | Class | Summary of a requirement's properties for comparison purposes. |
| `as_tuple` | Function | Pull out the (name: str, version:str, extras:(str)) tuple from the pinned Insta… |
| `combine_install_requirements` | Function | Return a single install requirement that reflects a combination of all the inpu… |
| `create_wheel_cache` | Function |  |
| `format_requirement` | Function | Generic formatter for pretty printing InstallRequirements to the terminal in a… |
| `format_specifier` | Function | Generic formatter for pretty printing the specifier part of InstallRequirements… |
| `is_pinned_requirement` | Function | Return whether an InstallRequirement is a "pinned" requirement.  An InstallRequ… |
| `is_url_requirement` | Function | Return :py:data:`True` if requirement was specified as a path or URL.  ``ireq.o… |
| `key_from_ireq` | Function | Get a standardized key for an InstallRequirement. |
| `key_from_req` | Function | Get an all-lowercase version of the requirement's name.  **Note:** If the argum… |
| `omit_list_value` | Function | Produce a new list with a given value skipped. |
| `strip_extras` | Function | Strip extras from package name, e.g. pytest[testing] -> pytest. |
| `BacktrackingResolver` | Class | A wrapper for the backtracking (or 2020) resolver. |
| `resolve` | Method | Resolve given ireqs.  Find concrete package versions for all the given InstallR… |
| `resolve_hashes` | Method | Find acceptable hashes for all of the given ``InstallRequirement``\ s. |
| `BaseRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `DependencyCache` | Class | Create new persistent dependency cache for the current Python version.  The cac… |
| `as_cache_key` | Method | Given a requirement, return its cache key.  This behavior is a little weird in… |
| `clear` | Method |  |
| `reverse_dependencies` | Method | Return a lookup table of reverse dependencies for all the given ireqs.  Since t… |
| `write_cache` | Method | Write the cache to disk as JSON. |
| `LegacyResolver` | Class | Wrapper for the (deprecated) legacy dependency resolver. |
| `get_best_match` | Method | Return a (pinned or editable) InstallRequirement.  This indicates the best matc… |
| `resolve` | Method | Find concrete package versions for all the given ``InstallRequirement``\ s and… |
| `resolve_hashes` | Method | Find acceptable hashes for all of the given ``InstallRequirement``\ s. |
| `LocalRequirementsRepository` | Class | The LocalRequirementsRepository proxied the _real_ repository by first checking… |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions. |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given a pinned InstallRequirement, returns a set of hashes that represent all o… |
| `NoCandidateFound` | Class | Common base class for all non-exit exceptions. |
| `OutputWriter` | Class |  |
| `write` | Method |  |
| `write_find_links` | Method |  |
| `write_flags` | Method |  |
| `write_format_controls` | Method |  |
| `write_header` | Method |  |
| `write_index_options` | Method |  |
| `write_trusted_hosts` | Method |  |
| `PipToolsError` | Class | Common base class for all non-exit exceptions. |
| `ProjectMetadata` | Class | ProjectMetadata(extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirem… |
| `PyPIRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions… |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_all_candidates` | Method |  |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given an InstallRequirement, return a set of hashes that represent all of the f… |
| `resolve_reqs` | Method |  |
| `build_project_metadata` | Function | Return the metadata for a project.  First, optionally attempt to determine the… |
| `dedup` | Function | Deduplicate an iterable object like ``iter(set(iterable))`` but order-preserved. |
| `drop_extras` | Function | Remove "extra" markers (PEP-508) from requirement. |
| `filter_deprecated_pip_args` | Function | Warn about and drop pip args that are no longer supported by pip.  Currently dr… |
| `is_pinned_requirement` | Function | Return whether an InstallRequirement is a "pinned" requirement.  An InstallRequ… |
| `key_from_ireq` | Function | Get a standardized key for an InstallRequirement. |
| `parse_requirements` | Function |  |
| `override_defaults_from_config_file` | Function | Override ``click.Command`` defaults based on specified or discovered config fil… |
| `Distribution` | Class | Distribution(key: 'str', version: 'str', requires: 'Iterable[Requirement]', dir… |
| `from_pip_distribution` | Method |  |
| `PipToolsError` | Class | Common base class for all non-exit exceptions. |
| `PyPIRepository` | Class |  |
| `allow_all_wheels` | Method | Monkey patches pip.Wheel to allow wheels from all platforms and Python versions… |
| `clear_caches` | Method | Should clear any caches used by the implementation. |
| `find_all_candidates` | Method |  |
| `find_best_match` | Method | Returns a pinned InstallRequirement object that indicates the best match for th… |
| `get_dependencies` | Method | Given a pinned, URL, or editable InstallRequirement, returns a set of dependenc… |
| `get_hashes` | Method | Given an InstallRequirement, return a set of hashes that represent all of the f… |
| `resolve_reqs` | Method |  |
| `filter_deprecated_pip_args` | Function | Warn about and drop pip args that are no longer supported by pip.  Currently dr… |
| `flat_map` | Function | Map a function over a collection and flatten the result by one-level |
| `get_required_pip_specification` | Function | Return pip version specifier requested by current pip-tools installation. |
| `get_sys_path_for_python_executable` | Function | Return sys.path list for the given python executable. |
| `parse_requirements` | Function |  |
| `Distribution` | Class | Distribution(key: 'str', version: 'str', requires: 'Iterable[Requirement]', dir… |
| `from_pip_distribution` | Method |  |
| `IncompatibleRequirements` | Class | Common base class for all non-exit exceptions. |
| `dependency_tree` | Function | Calculate the dependency tree for a package.  Return a collection of all of the… |
| `diff` | Function | Calculate which packages should be installed or uninstalled.  Compared are the… |
| `diff_key_from_ireq` | Function | Calculate key for comparing a compiled requirement with installed modules.  For… |
| `diff_key_from_req` | Function | Get a unique key for the requirement. |

## Classes

### `ProjectMetadata`

ProjectMetadata(extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirement, ...]', build_requirements: 'tuple[InstallRequirement, ...]')

```python
piptools.build.ProjectMetadata(self, extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirement, ...]', build_requirements: 'tuple[InstallRequirement, ...]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extras` | `tuple[str, ...]` | `—` | pos/kw |
| `requirements` | `tuple[InstallRequirement, ...]` | `—` | pos/kw |
| `build_requirements` | `tuple[InstallRequirement, ...]` | `—` | pos/kw |

### `StaticProjectMetadata`

StaticProjectMetadata(extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirement, ...]')

```python
piptools.build.StaticProjectMetadata(self, extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirement, ...]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extras` | `tuple[str, ...]` | `—` | pos/kw |
| `requirements` | `tuple[InstallRequirement, ...]` | `—` | pos/kw |

### `CorruptCacheError`

Common base class for all non-exit exceptions.

```python
piptools.cache.CorruptCacheError(self, path: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

### `DependencyCache`

Create new persistent dependency cache for the current Python version.

The cache file is written to the appropriate user cache dir for the
current platform, i.e.

    ~/.cache/pip-tools/depcache-pyX…

```python
piptools.cache.DependencyCache(self, cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cache_dir` | `str` | `—` | pos/kw |

### `PipToolsError`

Common base class for all non-exit exceptions.

```python
piptools.cache.PipToolsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `IncompatibleRequirements`

Common base class for all non-exit exceptions.

```python
piptools.exceptions.IncompatibleRequirements(self, ireq_a: 'InstallRequirement', ireq_b: 'InstallRequirement') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq_a` | `InstallRequirement` | `—` | pos/kw |
| `ireq_b` | `InstallRequirement` | `—` | pos/kw |

### `NoCandidateFound`

Common base class for all non-exit exceptions.

```python
piptools.exceptions.NoCandidateFound(self, ireq: 'InstallRequirement', candidates_tried: 'Iterable[InstallationCandidate]', finder: 'PackageFinder') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `candidates_tried` | `Iterable[InstallationCandidate]` | `—` | pos/kw |
| `finder` | `PackageFinder` | `—` | pos/kw |

### `PipToolsError`

Common base class for all non-exit exceptions.

```python
piptools.exceptions.PipToolsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LogContext`

```python
piptools.logging.LogContext(self, verbosity: 'int' = 0, indent_width: 'int' = 2)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `verbosity` | `int` | `0` | pos/kw |
| `indent_width` | `int` | `2` | pos/kw |

### `LocalRequirementsRepository`

The LocalRequirementsRepository proxied the _real_ repository by first
checking if a requirement can be satisfied by existing pins (i.e. the
result of a previous compile step).

In effect, if a requi…

```python
piptools.repositories.LocalRequirementsRepository(self, existing_pins: 'Mapping[str, InstallationCandidate]', proxied_repository: 'PyPIRepository', reuse_hashes: 'bool' = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `existing_pins` | `Mapping[str, InstallationCandidate]` | `—` | pos/kw |
| `proxied_repository` | `PyPIRepository` | `—` | pos/kw |
| `reuse_hashes` | `bool` | `True` | pos/kw |

### `PyPIRepository`

```python
piptools.repositories.PyPIRepository(self, pip_args: 'list[str]', cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pip_args` | `list[str]` | `—` | pos/kw |
| `cache_dir` | `str` | `—` | pos/kw |

### `BaseRepository`

```python
piptools.repositories.base.BaseRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BaseRepository`

```python
piptools.repositories.local.BaseRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LocalRequirementsRepository`

The LocalRequirementsRepository proxied the _real_ repository by first
checking if a requirement can be satisfied by existing pins (i.e. the
result of a previous compile step).

In effect, if a requi…

```python
piptools.repositories.local.LocalRequirementsRepository(self, existing_pins: 'Mapping[str, InstallationCandidate]', proxied_repository: 'PyPIRepository', reuse_hashes: 'bool' = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `existing_pins` | `Mapping[str, InstallationCandidate]` | `—` | pos/kw |
| `proxied_repository` | `PyPIRepository` | `—` | pos/kw |
| `reuse_hashes` | `bool` | `True` | pos/kw |

### `PyPIRepository`

```python
piptools.repositories.local.PyPIRepository(self, pip_args: 'list[str]', cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pip_args` | `list[str]` | `—` | pos/kw |
| `cache_dir` | `str` | `—` | pos/kw |

### `BaseRepository`

```python
piptools.repositories.pypi.BaseRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FileStream`

FileStream(stream, size)

```python
piptools.repositories.pypi.FileStream(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NoCandidateFound`

Common base class for all non-exit exceptions.

```python
piptools.repositories.pypi.NoCandidateFound(self, ireq: 'InstallRequirement', candidates_tried: 'Iterable[InstallationCandidate]', finder: 'PackageFinder') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `candidates_tried` | `Iterable[InstallationCandidate]` | `—` | pos/kw |
| `finder` | `PackageFinder` | `—` | pos/kw |

### `PyPIRepository`

```python
piptools.repositories.pypi.PyPIRepository(self, pip_args: 'list[str]', cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pip_args` | `list[str]` | `—` | pos/kw |
| `cache_dir` | `str` | `—` | pos/kw |

### `BacktrackingResolver`

A wrapper for the backtracking (or 2020) resolver.

```python
piptools.resolver.BacktrackingResolver(self, constraints: 'Iterable[InstallRequirement]', existing_constraints: 'dict[str, InstallRequirement]', repository: 'BaseRepository', allow_unsafe: 'bool' = False, unsafe_packages: 'set[str] | None' = None, **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `constraints` | `Iterable[InstallRequirement]` | `—` | pos/kw |
| `existing_constraints` | `dict[str, InstallRequirement]` | `—` | pos/kw |
| `repository` | `BaseRepository` | `—` | pos/kw |
| `allow_unsafe` | `bool` | `False` | pos/kw |
| `unsafe_packages` | `set[str] \| None` | `None` | pos/kw |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `BaseRepository`

```python
piptools.resolver.BaseRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BaseResolver`

```python
piptools.resolver.BaseResolver(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DependencyCache`

Create new persistent dependency cache for the current Python version.

The cache file is written to the appropriate user cache dir for the
current platform, i.e.

    ~/.cache/pip-tools/depcache-pyX…

```python
piptools.resolver.DependencyCache(self, cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cache_dir` | `str` | `—` | pos/kw |

### `LegacyResolver`

Wrapper for the (deprecated) legacy dependency resolver.

```python
piptools.resolver.LegacyResolver(self, constraints: 'Iterable[InstallRequirement]', existing_constraints: 'dict[str, InstallRequirement]', repository: 'BaseRepository', cache: 'DependencyCache', prereleases: 'bool | None' = False, clear_caches: 'bool' = False, allow_unsafe: 'bool' = False, unsafe_packages: 'set[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `constraints` | `Iterable[InstallRequirement]` | `—` | pos/kw |
| `existing_constraints` | `dict[str, InstallRequirement]` | `—` | pos/kw |
| `repository` | `BaseRepository` | `—` | pos/kw |
| `cache` | `DependencyCache` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `False` | pos/kw |
| `clear_caches` | `bool` | `False` | pos/kw |
| `allow_unsafe` | `bool` | `False` | pos/kw |
| `unsafe_packages` | `set[str] \| None` | `None` | pos/kw |

### `PipToolsError`

Common base class for all non-exit exceptions.

```python
piptools.resolver.PipToolsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RequirementSummary`

Summary of a requirement's properties for comparison purposes.

```python
piptools.resolver.RequirementSummary(self, ireq: 'InstallRequirement') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

### `BacktrackingResolver`

A wrapper for the backtracking (or 2020) resolver.

```python
piptools.scripts.compile.BacktrackingResolver(self, constraints: 'Iterable[InstallRequirement]', existing_constraints: 'dict[str, InstallRequirement]', repository: 'BaseRepository', allow_unsafe: 'bool' = False, unsafe_packages: 'set[str] | None' = None, **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `constraints` | `Iterable[InstallRequirement]` | `—` | pos/kw |
| `existing_constraints` | `dict[str, InstallRequirement]` | `—` | pos/kw |
| `repository` | `BaseRepository` | `—` | pos/kw |
| `allow_unsafe` | `bool` | `False` | pos/kw |
| `unsafe_packages` | `set[str] \| None` | `None` | pos/kw |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `BaseRepository`

```python
piptools.scripts.compile.BaseRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DependencyCache`

Create new persistent dependency cache for the current Python version.

The cache file is written to the appropriate user cache dir for the
current platform, i.e.

    ~/.cache/pip-tools/depcache-pyX…

```python
piptools.scripts.compile.DependencyCache(self, cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cache_dir` | `str` | `—` | pos/kw |

### `LegacyResolver`

Wrapper for the (deprecated) legacy dependency resolver.

```python
piptools.scripts.compile.LegacyResolver(self, constraints: 'Iterable[InstallRequirement]', existing_constraints: 'dict[str, InstallRequirement]', repository: 'BaseRepository', cache: 'DependencyCache', prereleases: 'bool | None' = False, clear_caches: 'bool' = False, allow_unsafe: 'bool' = False, unsafe_packages: 'set[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `constraints` | `Iterable[InstallRequirement]` | `—` | pos/kw |
| `existing_constraints` | `dict[str, InstallRequirement]` | `—` | pos/kw |
| `repository` | `BaseRepository` | `—` | pos/kw |
| `cache` | `DependencyCache` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `False` | pos/kw |
| `clear_caches` | `bool` | `False` | pos/kw |
| `allow_unsafe` | `bool` | `False` | pos/kw |
| `unsafe_packages` | `set[str] \| None` | `None` | pos/kw |

### `LocalRequirementsRepository`

The LocalRequirementsRepository proxied the _real_ repository by first
checking if a requirement can be satisfied by existing pins (i.e. the
result of a previous compile step).

In effect, if a requi…

```python
piptools.scripts.compile.LocalRequirementsRepository(self, existing_pins: 'Mapping[str, InstallationCandidate]', proxied_repository: 'PyPIRepository', reuse_hashes: 'bool' = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `existing_pins` | `Mapping[str, InstallationCandidate]` | `—` | pos/kw |
| `proxied_repository` | `PyPIRepository` | `—` | pos/kw |
| `reuse_hashes` | `bool` | `True` | pos/kw |

### `NoCandidateFound`

Common base class for all non-exit exceptions.

```python
piptools.scripts.compile.NoCandidateFound(self, ireq: 'InstallRequirement', candidates_tried: 'Iterable[InstallationCandidate]', finder: 'PackageFinder') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `candidates_tried` | `Iterable[InstallationCandidate]` | `—` | pos/kw |
| `finder` | `PackageFinder` | `—` | pos/kw |

### `OutputWriter`

```python
piptools.scripts.compile.OutputWriter(self, dst_file: '_t.BinaryIO', click_ctx: 'Context', dry_run: 'bool', emit_header: 'bool', emit_index_url: 'bool', emit_trusted_host: 'bool', annotate: 'bool', annotation_style: 'str', strip_extras: 'bool', generate_hashes: 'bool', default_index_url: 'str', index_urls: 'Iterable[str]', trusted_hosts: 'Iterable[str]', format_control: 'FormatControl', linesep: 'str', allow_unsafe: 'bool', find_links: 'list[str]', emit_find_links: 'bool', emit_options: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dst_file` | `_t.BinaryIO` | `—` | pos/kw |
| `click_ctx` | `Context` | `—` | pos/kw |
| `dry_run` | `bool` | `—` | pos/kw |
| `emit_header` | `bool` | `—` | pos/kw |
| `emit_index_url` | `bool` | `—` | pos/kw |
| `emit_trusted_host` | `bool` | `—` | pos/kw |
| `annotate` | `bool` | `—` | pos/kw |
| `annotation_style` | `str` | `—` | pos/kw |
| `strip_extras` | `bool` | `—` | pos/kw |
| `generate_hashes` | `bool` | `—` | pos/kw |
| `default_index_url` | `str` | `—` | pos/kw |
| `index_urls` | `Iterable[str]` | `—` | pos/kw |
| `trusted_hosts` | `Iterable[str]` | `—` | pos/kw |
| `format_control` | `FormatControl` | `—` | pos/kw |
| `linesep` | `str` | `—` | pos/kw |
| `allow_unsafe` | `bool` | `—` | pos/kw |
| `find_links` | `list[str]` | `—` | pos/kw |
| `emit_find_links` | `bool` | `—` | pos/kw |
| `emit_options` | `bool` | `—` | pos/kw |

### `PipToolsError`

Common base class for all non-exit exceptions.

```python
piptools.scripts.compile.PipToolsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ProjectMetadata`

ProjectMetadata(extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirement, ...]', build_requirements: 'tuple[InstallRequirement, ...]')

```python
piptools.scripts.compile.ProjectMetadata(self, extras: 'tuple[str, ...]', requirements: 'tuple[InstallRequirement, ...]', build_requirements: 'tuple[InstallRequirement, ...]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extras` | `tuple[str, ...]` | `—` | pos/kw |
| `requirements` | `tuple[InstallRequirement, ...]` | `—` | pos/kw |
| `build_requirements` | `tuple[InstallRequirement, ...]` | `—` | pos/kw |

### `PyPIRepository`

```python
piptools.scripts.compile.PyPIRepository(self, pip_args: 'list[str]', cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pip_args` | `list[str]` | `—` | pos/kw |
| `cache_dir` | `str` | `—` | pos/kw |

### `Distribution`

Distribution(key: 'str', version: 'str', requires: 'Iterable[Requirement]', direct_url: 'DirectUrl | None')

```python
piptools.scripts.sync.Distribution(self, key: 'str', version: 'str', requires: 'Iterable[Requirement]', direct_url: 'DirectUrl | None') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |
| `requires` | `Iterable[Requirement]` | `—` | pos/kw |
| `direct_url` | `DirectUrl \| None` | `—` | pos/kw |

### `PipToolsError`

Common base class for all non-exit exceptions.

```python
piptools.scripts.sync.PipToolsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PyPIRepository`

```python
piptools.scripts.sync.PyPIRepository(self, pip_args: 'list[str]', cache_dir: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pip_args` | `list[str]` | `—` | pos/kw |
| `cache_dir` | `str` | `—` | pos/kw |

### `Distribution`

Distribution(key: 'str', version: 'str', requires: 'Iterable[Requirement]', direct_url: 'DirectUrl | None')

```python
piptools.sync.Distribution(self, key: 'str', version: 'str', requires: 'Iterable[Requirement]', direct_url: 'DirectUrl | None') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |
| `requires` | `Iterable[Requirement]` | `—` | pos/kw |
| `direct_url` | `DirectUrl \| None` | `—` | pos/kw |

### `IncompatibleRequirements`

Common base class for all non-exit exceptions.

```python
piptools.sync.IncompatibleRequirements(self, ireq_a: 'InstallRequirement', ireq_b: 'InstallRequirement') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq_a` | `InstallRequirement` | `—` | pos/kw |
| `ireq_b` | `InstallRequirement` | `—` | pos/kw |

## Functions

### `build_project_metadata`

Return the metadata for a project.

First, optionally attempt to determine the metadata statically from the
``pyproject.toml`` file. This will not work if build_targets are specified,
since we cannot…

```python
piptools.build.build_project_metadata(src_file: 'pathlib.Path', build_targets: 'tuple[str, ...]', *, upgrade_packages: 'tuple[str, ...] | None' = None, attempt_static_parse: 'bool', isolated: 'bool', quiet: 'bool') -> 'ProjectMetadata | StaticProjectMetadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_file` | `pathlib.Path` | `—` | pos/kw |
| `build_targets` | `tuple[str, ...]` | `—` | pos/kw |
| `upgrade_packages` | `tuple[str, ...] \| None` | `None` | kw |
| `attempt_static_parse` | `bool` | `—` | kw |
| `isolated` | `bool` | `—` | kw |
| `quiet` | `bool` | `—` | kw |

**Returns:** `ProjectMetadata | StaticProjectMetadata`

### `maybe_statically_parse_project_metadata`

Return the metadata for a project, if it can be statically parsed from ``pyproject.toml``.

This function is typically significantly faster than invoking a build backend.
Returns None if the project…

```python
piptools.build.maybe_statically_parse_project_metadata(src_file: 'pathlib.Path') -> 'StaticProjectMetadata | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_file` | `pathlib.Path` | `—` | pos/kw |

**Returns:** `StaticProjectMetadata | None`

### `as_tuple`

Pull out the (name: str, version:str, extras:(str)) tuple from
the pinned InstallRequirement.

```python
piptools.cache.as_tuple(ireq: 'InstallRequirement') -> 'tuple[str, str, tuple[str, ...]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `tuple[str, str, tuple[str, ...]]`

### `key_from_req`

Get an all-lowercase version of the requirement's name.

**Note:** If the argument is an instance of
``pip._internal.resolution.resolvelib.base.Requirement`` (like
``pip._internal.resolution.resolvel…

```python
piptools.cache.key_from_req(req: 'InstallRequirement | Requirement | PipRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `req` | `InstallRequirement \| Requirement \| PipRequirement` | `—` | pos/kw |

**Returns:** `str`

### `lookup_table_from_tuples`

Build a dict-based lookup table (index) elegantly.

```python
piptools.cache.lookup_table_from_tuples(values: 'Iterable[tuple[_KT, _VT]]') -> 'dict[_KT, set[_VT]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `values` | `Iterable[tuple[_KT, _VT]]` | `—` | pos/kw |

**Returns:** `dict[_KT, set[_VT]]`

### `read_cache_file`

```python
piptools.cache.read_cache_file(cache_file_path: 'str') -> 'CacheDict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cache_file_path` | `str` | `—` | pos/kw |

**Returns:** `CacheDict`

### `as_tuple`

Pull out the (name: str, version:str, extras:(str)) tuple from
the pinned InstallRequirement.

```python
piptools.repositories.local.as_tuple(ireq: 'InstallRequirement') -> 'tuple[str, str, tuple[str, ...]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `tuple[str, str, tuple[str, ...]]`

### `ireq_satisfied_by_existing_pin`

Return :py:data:`True` if the given ``InstallRequirement`` is satisfied by the
previously encountered version pin.

```python
piptools.repositories.local.ireq_satisfied_by_existing_pin(ireq: 'InstallRequirement', existing_pin: 'InstallationCandidate') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `existing_pin` | `InstallationCandidate` | `—` | pos/kw |

**Returns:** `bool`

### `key_from_ireq`

Get a standardized key for an InstallRequirement.

```python
piptools.repositories.local.key_from_ireq(ireq: 'InstallRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `str`

### `as_tuple`

Pull out the (name: str, version:str, extras:(str)) tuple from
the pinned InstallRequirement.

```python
piptools.repositories.pypi.as_tuple(ireq: 'InstallRequirement') -> 'tuple[str, str, tuple[str, ...]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `tuple[str, str, tuple[str, ...]]`

### `candidate_version`

```python
piptools.repositories.pypi.candidate_version(candidate: 'InstallationCandidate') -> '_BaseVersion'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `candidate` | `InstallationCandidate` | `—` | pos/kw |

**Returns:** `_BaseVersion`

### `create_wheel_cache`

```python
piptools.repositories.pypi.create_wheel_cache(cache_dir: 'str', format_control: 'str | None' = None) -> 'WheelCache'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cache_dir` | `str` | `—` | pos/kw |
| `format_control` | `str \| None` | `None` | pos/kw |

**Returns:** `WheelCache`

### `is_pinned_requirement`

Return whether an InstallRequirement is a "pinned" requirement.

An InstallRequirement is considered pinned if:

- Is not editable
- It has exactly one specifier
- That specifier is "=="
- The versio…

```python
piptools.repositories.pypi.is_pinned_requirement(ireq: 'InstallRequirement') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `bool`

### `is_url_requirement`

Return :py:data:`True` if requirement was specified as a path or URL.

``ireq.original_link`` will have been set by ``InstallRequirement.__init__``

```python
piptools.repositories.pypi.is_url_requirement(ireq: 'InstallRequirement') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `bool`

### `lookup_table`

Build a dict-based lookup table (index) elegantly.

```python
piptools.repositories.pypi.lookup_table(values: 'Iterable[_VT]', key: '_t.Callable[[_VT], _KT]') -> 'dict[_KT, set[_VT]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `values` | `Iterable[_VT]` | `—` | pos/kw |
| `key` | `_t.Callable[[_VT], _KT]` | `—` | pos/kw |

**Returns:** `dict[_KT, set[_VT]]`

### `open_local_or_remote_file`

Open local or remote file for reading.

:type link: pip.index.Link
:type session: requests.Session
:raises ValueError: If link points to a local directory.
:return: a context manager to a FileStream…

```python
piptools.repositories.pypi.open_local_or_remote_file(link: 'Link', session: 'Session') -> 'Iterator[FileStream]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `link` | `Link` | `—` | pos/kw |
| `session` | `Session` | `—` | pos/kw |

**Returns:** `Iterator[FileStream]`

### `as_tuple`

Pull out the (name: str, version:str, extras:(str)) tuple from
the pinned InstallRequirement.

```python
piptools.resolver.as_tuple(ireq: 'InstallRequirement') -> 'tuple[str, str, tuple[str, ...]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `tuple[str, str, tuple[str, ...]]`

### `combine_install_requirements`

Return a single install requirement that reflects a combination of
all the inputs.

```python
piptools.resolver.combine_install_requirements(ireqs: 'Iterable[InstallRequirement]') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireqs` | `Iterable[InstallRequirement]` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `create_wheel_cache`

```python
piptools.resolver.create_wheel_cache(cache_dir: 'str', format_control: 'str | None' = None) -> 'WheelCache'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cache_dir` | `str` | `—` | pos/kw |
| `format_control` | `str \| None` | `None` | pos/kw |

**Returns:** `WheelCache`

### `format_requirement`

Generic formatter for pretty printing InstallRequirements to the terminal
in a less verbose way than using its ``__str__`` method.

```python
piptools.resolver.format_requirement(ireq: 'InstallRequirement', marker: 'Marker | None' = None, hashes: 'set[str] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `marker` | `Marker \| None` | `None` | pos/kw |
| `hashes` | `set[str] \| None` | `None` | pos/kw |

**Returns:** `str`

### `format_specifier`

Generic formatter for pretty printing the specifier part of
InstallRequirements to the terminal.

```python
piptools.resolver.format_specifier(ireq: 'InstallRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `str`

### `is_pinned_requirement`

Return whether an InstallRequirement is a "pinned" requirement.

An InstallRequirement is considered pinned if:

- Is not editable
- It has exactly one specifier
- That specifier is "=="
- The versio…

```python
piptools.resolver.is_pinned_requirement(ireq: 'InstallRequirement') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `bool`

### `is_url_requirement`

Return :py:data:`True` if requirement was specified as a path or URL.

``ireq.original_link`` will have been set by ``InstallRequirement.__init__``

```python
piptools.resolver.is_url_requirement(ireq: 'InstallRequirement') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `bool`

### `key_from_ireq`

Get a standardized key for an InstallRequirement.

```python
piptools.resolver.key_from_ireq(ireq: 'InstallRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `str`

### `key_from_req`

Get an all-lowercase version of the requirement's name.

**Note:** If the argument is an instance of
``pip._internal.resolution.resolvelib.base.Requirement`` (like
``pip._internal.resolution.resolvel…

```python
piptools.resolver.key_from_req(req: 'InstallRequirement | Requirement | PipRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `req` | `InstallRequirement \| Requirement \| PipRequirement` | `—` | pos/kw |

**Returns:** `str`

### `omit_list_value`

Produce a new list with a given value skipped.

```python
piptools.resolver.omit_list_value(lst: 'list[_T]', value: '_T') -> 'list[_T]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lst` | `list[_T]` | `—` | pos/kw |
| `value` | `_T` | `—` | pos/kw |

**Returns:** `list[_T]`

### `strip_extras`

Strip extras from package name, e.g. pytest[testing] -> pytest.

```python
piptools.resolver.strip_extras(name: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `str`

### `build_project_metadata`

Return the metadata for a project.

First, optionally attempt to determine the metadata statically from the
``pyproject.toml`` file. This will not work if build_targets are specified,
since we cannot…

```python
piptools.scripts.compile.build_project_metadata(src_file: 'pathlib.Path', build_targets: 'tuple[str, ...]', *, upgrade_packages: 'tuple[str, ...] | None' = None, attempt_static_parse: 'bool', isolated: 'bool', quiet: 'bool') -> 'ProjectMetadata | StaticProjectMetadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_file` | `pathlib.Path` | `—` | pos/kw |
| `build_targets` | `tuple[str, ...]` | `—` | pos/kw |
| `upgrade_packages` | `tuple[str, ...] \| None` | `None` | kw |
| `attempt_static_parse` | `bool` | `—` | kw |
| `isolated` | `bool` | `—` | kw |
| `quiet` | `bool` | `—` | kw |

**Returns:** `ProjectMetadata | StaticProjectMetadata`

### `dedup`

Deduplicate an iterable object like ``iter(set(iterable))`` but
order-preserved.

```python
piptools.scripts.compile.dedup(iterable: 'Iterable[_T]') -> 'Iterable[_T]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `Iterable[_T]` | `—` | pos/kw |

**Returns:** `Iterable[_T]`

### `drop_extras`

Remove "extra" markers (PEP-508) from requirement.

```python
piptools.scripts.compile.drop_extras(ireq: 'InstallRequirement') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

### `filter_deprecated_pip_args`

Warn about and drop pip args that are no longer supported by pip.

Currently drops:

- ``--use-pep517``
- ``--no-use-pep517``
- ``--global-option``
- ``--build-option``

```python
piptools.scripts.compile.filter_deprecated_pip_args(args: 'list[str]') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `list[str]` | `—` | pos/kw |

**Returns:** `list[str]`

### `is_pinned_requirement`

Return whether an InstallRequirement is a "pinned" requirement.

An InstallRequirement is considered pinned if:

- Is not editable
- It has exactly one specifier
- That specifier is "=="
- The versio…

```python
piptools.scripts.compile.is_pinned_requirement(ireq: 'InstallRequirement') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `bool`

### `key_from_ireq`

Get a standardized key for an InstallRequirement.

```python
piptools.scripts.compile.key_from_ireq(ireq: 'InstallRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `str`

### `parse_requirements`

```python
piptools.scripts.compile.parse_requirements(filename: 'str', session: 'PipSession', finder: 'PackageFinder | None' = None, options: 'optparse.Values | None' = None, constraint: 'bool' = False, isolated: 'bool' = False, comes_from_stdin: 'bool' = False) -> 'Iterator[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |
| `session` | `PipSession` | `—` | pos/kw |
| `finder` | `PackageFinder \| None` | `None` | pos/kw |
| `options` | `optparse.Values \| None` | `None` | pos/kw |
| `constraint` | `bool` | `False` | pos/kw |
| `isolated` | `bool` | `False` | pos/kw |
| `comes_from_stdin` | `bool` | `False` | pos/kw |

**Returns:** `Iterator[InstallRequirement]`

### `override_defaults_from_config_file`

Override ``click.Command`` defaults based on specified or discovered config
file, returning the ``pathlib.Path`` of that config file if specified or
discovered.

:returns: :py:data:`None` if no such…

```python
piptools.scripts.options.override_defaults_from_config_file(ctx: 'click.Context', param: 'click.Parameter', value: 'str | None') -> 'Path | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `click.Context` | `—` | pos/kw |
| `param` | `click.Parameter` | `—` | pos/kw |
| `value` | `str \| None` | `—` | pos/kw |

**Returns:** `Path | None`

### `filter_deprecated_pip_args`

Warn about and drop pip args that are no longer supported by pip.

Currently drops:

- ``--use-pep517``
- ``--no-use-pep517``
- ``--global-option``
- ``--build-option``

```python
piptools.scripts.sync.filter_deprecated_pip_args(args: 'list[str]') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `list[str]` | `—` | pos/kw |

**Returns:** `list[str]`

### `flat_map`

Map a function over a collection and flatten the result by one-level

```python
piptools.scripts.sync.flat_map(fn: '_t.Callable[[_T], Iterable[_S]]', collection: 'Iterable[_T]') -> 'Iterator[_S]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fn` | `_t.Callable[[_T], Iterable[_S]]` | `—` | pos/kw |
| `collection` | `Iterable[_T]` | `—` | pos/kw |

**Returns:** `Iterator[_S]`

### `get_required_pip_specification`

Return pip version specifier requested by current pip-tools installation.

```python
piptools.scripts.sync.get_required_pip_specification() -> 'SpecifierSet'
```

**Returns:** `SpecifierSet`

### `get_sys_path_for_python_executable`

Return sys.path list for the given python executable.

```python
piptools.scripts.sync.get_sys_path_for_python_executable(python_executable: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `python_executable` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

### `parse_requirements`

```python
piptools.scripts.sync.parse_requirements(filename: 'str', session: 'PipSession', finder: 'PackageFinder | None' = None, options: 'optparse.Values | None' = None, constraint: 'bool' = False, isolated: 'bool' = False, comes_from_stdin: 'bool' = False) -> 'Iterator[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |
| `session` | `PipSession` | `—` | pos/kw |
| `finder` | `PackageFinder \| None` | `None` | pos/kw |
| `options` | `optparse.Values \| None` | `None` | pos/kw |
| `constraint` | `bool` | `False` | pos/kw |
| `isolated` | `bool` | `False` | pos/kw |
| `comes_from_stdin` | `bool` | `False` | pos/kw |

**Returns:** `Iterator[InstallRequirement]`

### `dependency_tree`

Calculate the dependency tree for a package.

Return a collection of all of the package's dependencies.
Uses a DFS traversal algorithm.

``installed_keys`` should be a {key: requirement} mapping, e.g…

```python
piptools.sync.dependency_tree(installed_keys: 'Mapping[str, Distribution]', root_key: 'str') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `installed_keys` | `Mapping[str, Distribution]` | `—` | pos/kw |
| `root_key` | `str` | `—` | pos/kw |

**Returns:** `set[str]`

### `diff`

Calculate which packages should be installed or uninstalled.

Compared are the compiled requirements and a list of currently
installed modules.

```python
piptools.sync.diff(compiled_requirements: 'Iterable[InstallRequirement]', installed_dists: 'Iterable[Distribution]') -> 'tuple[set[InstallRequirement], set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `compiled_requirements` | `Iterable[InstallRequirement]` | `—` | pos/kw |
| `installed_dists` | `Iterable[Distribution]` | `—` | pos/kw |

**Returns:** `tuple[set[InstallRequirement], set[str]]`

### `diff_key_from_ireq`

Calculate key for comparing a compiled requirement with installed modules.

For URL requirements, only provide a useful key if the url includes
a hash, e.g. #sha1=..., in any of the supported hash al…

```python
piptools.sync.diff_key_from_ireq(ireq: 'InstallRequirement') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `str`

### `diff_key_from_req`

Get a unique key for the requirement.

```python
piptools.sync.diff_key_from_req(req: 'Distribution') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `req` | `Distribution` | `—` | pos/kw |

**Returns:** `str`

## Methods

### `piptools.cache.DependencyCache` methods

### `as_cache_key`

Given a requirement, return its cache key.

This behavior is a little weird
in order to allow backwards compatibility with cache files. For a requirement
without extras, this will return, for example…

```python
piptools.cache.DependencyCache.as_cache_key(self, ireq: 'InstallRequirement') -> 'CacheKey'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `CacheKey`

### `clear`

```python
piptools.cache.DependencyCache.clear(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reverse_dependencies`

Return a lookup table of reverse dependencies for all the given ireqs.

Since this is all static, it only works if the dependency cache
contains the complete data, otherwise you end up with a partial…

```python
piptools.cache.DependencyCache.reverse_dependencies(self, ireqs: 'Iterable[InstallRequirement]') -> 'dict[str, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `Iterable[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[str, set[str]]`

### `write_cache`

Write the cache to disk as JSON.

```python
piptools.cache.DependencyCache.write_cache(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `piptools.logging.LogContext` methods

### `debug`

```python
piptools.logging.LogContext.debug(self, message: 'str', *args: '_t.Any', **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `args` | `_t.Any` | `—` | *args |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `error`

```python
piptools.logging.LogContext.error(self, message: 'str', *args: '_t.Any', **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `args` | `_t.Any` | `—` | *args |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `indentation`

Increase indentation.

```python
piptools.logging.LogContext.indentation(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `info`

```python
piptools.logging.LogContext.info(self, message: 'str', *args: '_t.Any', **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `args` | `_t.Any` | `—` | *args |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `log`

```python
piptools.logging.LogContext.log(self, message: 'str', *args: '_t.Any', **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `args` | `_t.Any` | `—` | *args |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `reset`

Reset logger to initial state.

```python
piptools.logging.LogContext.reset(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `warning`

```python
piptools.logging.LogContext.warning(self, message: 'str', *args: '_t.Any', **kwargs: '_t.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `args` | `_t.Any` | `—` | *args |
| `kwargs` | `_t.Any` | `—` | **kwargs |

### `piptools.repositories.LocalRequirementsRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.repositories.LocalRequirementsRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.LocalRequirementsRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.LocalRequirementsRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallationCandidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallationCandidate`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.LocalRequirementsRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.repositories.LocalRequirementsRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.repositories.PyPIRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

This also saves the candidate cache and set a new one, or else the results from
the previous non-patched calls will i…

```python
piptools.repositories.PyPIRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.PyPIRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_all_candidates`

```python
piptools.repositories.PyPIRepository.find_all_candidates(self, req_name: 'str') -> 'list[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req_name` | `str` | `—` | pos/kw |

**Returns:** `list[InstallationCandidate]`

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.PyPIRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.PyPIRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given an InstallRequirement, return a set of hashes that represent all
of the files for a given requirement. Unhashable requirements return an
empty set. Unpinned requirements raise a TypeError.

```python
piptools.repositories.PyPIRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `resolve_reqs`

```python
piptools.repositories.PyPIRepository.resolve_reqs(self, download_dir: 'str | None', ireq: 'InstallRequirement', wheel_cache: 'WheelCache') -> 'set[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `download_dir` | `str \| None` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `wheel_cache` | `WheelCache` | `—` | pos/kw |

**Returns:** `set[InstallationCandidate]`

### `piptools.repositories.base.BaseRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.repositories.base.BaseRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.base.BaseRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.base.BaseRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.base.BaseRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.repositories.base.BaseRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.repositories.local.BaseRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.repositories.local.BaseRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.local.BaseRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.local.BaseRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.local.BaseRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.repositories.local.BaseRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.repositories.local.LocalRequirementsRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.repositories.local.LocalRequirementsRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.local.LocalRequirementsRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.local.LocalRequirementsRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallationCandidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallationCandidate`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.local.LocalRequirementsRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.repositories.local.LocalRequirementsRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.repositories.local.PyPIRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

This also saves the candidate cache and set a new one, or else the results from
the previous non-patched calls will i…

```python
piptools.repositories.local.PyPIRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.local.PyPIRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_all_candidates`

```python
piptools.repositories.local.PyPIRepository.find_all_candidates(self, req_name: 'str') -> 'list[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req_name` | `str` | `—` | pos/kw |

**Returns:** `list[InstallationCandidate]`

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.local.PyPIRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.local.PyPIRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given an InstallRequirement, return a set of hashes that represent all
of the files for a given requirement. Unhashable requirements return an
empty set. Unpinned requirements raise a TypeError.

```python
piptools.repositories.local.PyPIRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `resolve_reqs`

```python
piptools.repositories.local.PyPIRepository.resolve_reqs(self, download_dir: 'str | None', ireq: 'InstallRequirement', wheel_cache: 'WheelCache') -> 'set[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `download_dir` | `str \| None` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `wheel_cache` | `WheelCache` | `—` | pos/kw |

**Returns:** `set[InstallationCandidate]`

### `piptools.repositories.pypi.BaseRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.repositories.pypi.BaseRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.pypi.BaseRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.pypi.BaseRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.pypi.BaseRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.repositories.pypi.BaseRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.repositories.pypi.PyPIRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

This also saves the candidate cache and set a new one, or else the results from
the previous non-patched calls will i…

```python
piptools.repositories.pypi.PyPIRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.repositories.pypi.PyPIRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_all_candidates`

```python
piptools.repositories.pypi.PyPIRepository.find_all_candidates(self, req_name: 'str') -> 'list[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req_name` | `str` | `—` | pos/kw |

**Returns:** `list[InstallationCandidate]`

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.repositories.pypi.PyPIRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.repositories.pypi.PyPIRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given an InstallRequirement, return a set of hashes that represent all
of the files for a given requirement. Unhashable requirements return an
empty set. Unpinned requirements raise a TypeError.

```python
piptools.repositories.pypi.PyPIRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `resolve_reqs`

```python
piptools.repositories.pypi.PyPIRepository.resolve_reqs(self, download_dir: 'str | None', ireq: 'InstallRequirement', wheel_cache: 'WheelCache') -> 'set[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `download_dir` | `str \| None` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `wheel_cache` | `WheelCache` | `—` | pos/kw |

**Returns:** `set[InstallationCandidate]`

### `piptools.resolver.BacktrackingResolver` methods

### `resolve`

Resolve given ireqs.

Find concrete package versions for all the given InstallRequirements
and their recursive dependencies.

:returns: A set of pinned ``InstallRequirement``\ s.

```python
piptools.resolver.BacktrackingResolver.resolve(self, max_rounds: 'int' = 10) -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_rounds` | `int` | `10` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `resolve_hashes`

Find acceptable hashes for all of the given ``InstallRequirement``\ s.

```python
piptools.resolver.BacktrackingResolver.resolve_hashes(self, ireqs: 'set[InstallRequirement]') -> 'dict[InstallRequirement, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `set[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[InstallRequirement, set[str]]`

### `piptools.resolver.BaseRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.resolver.BaseRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.resolver.BaseRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.resolver.BaseRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.resolver.BaseRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.resolver.BaseRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.resolver.BaseResolver` methods

### `resolve`

Find concrete package versions for all the given InstallRequirements
and their recursive dependencies.
:returns: a set of pinned ``InstallRequirement``\ s.

```python
piptools.resolver.BaseResolver.resolve(self, max_rounds: 'int') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_rounds` | `int` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `resolve_hashes`

Find acceptable hashes for all of the given ``InstallRequirement``\ s.

```python
piptools.resolver.BaseResolver.resolve_hashes(self, ireqs: 'set[InstallRequirement]') -> 'dict[InstallRequirement, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `set[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[InstallRequirement, set[str]]`

### `piptools.resolver.DependencyCache` methods

### `as_cache_key`

Given a requirement, return its cache key.

This behavior is a little weird
in order to allow backwards compatibility with cache files. For a requirement
without extras, this will return, for example…

```python
piptools.resolver.DependencyCache.as_cache_key(self, ireq: 'InstallRequirement') -> 'CacheKey'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `CacheKey`

### `clear`

```python
piptools.resolver.DependencyCache.clear(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reverse_dependencies`

Return a lookup table of reverse dependencies for all the given ireqs.

Since this is all static, it only works if the dependency cache
contains the complete data, otherwise you end up with a partial…

```python
piptools.resolver.DependencyCache.reverse_dependencies(self, ireqs: 'Iterable[InstallRequirement]') -> 'dict[str, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `Iterable[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[str, set[str]]`

### `write_cache`

Write the cache to disk as JSON.

```python
piptools.resolver.DependencyCache.write_cache(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `piptools.resolver.LegacyResolver` methods

### `get_best_match`

Return a (pinned or editable) InstallRequirement.

This indicates the best match to use for the given
InstallRequirement (in the form of an InstallRequirement).

Example:
Given the constraint Flask>=…

```python
piptools.resolver.LegacyResolver.get_best_match(self, ireq: 'InstallRequirement') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `resolve`

Find concrete package versions for all the given ``InstallRequirement``\ s
and their recursive dependencies and return a set of pinned
``InstallRequirement``\ s.

Resolves constraints one round at a…

```python
piptools.resolver.LegacyResolver.resolve(self, max_rounds: 'int' = 10) -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_rounds` | `int` | `10` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `resolve_hashes`

Find acceptable hashes for all of the given ``InstallRequirement``\ s.

```python
piptools.resolver.LegacyResolver.resolve_hashes(self, ireqs: 'set[InstallRequirement]') -> 'dict[InstallRequirement, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `set[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[InstallRequirement, set[str]]`

### `piptools.scripts.compile.BacktrackingResolver` methods

### `resolve`

Resolve given ireqs.

Find concrete package versions for all the given InstallRequirements
and their recursive dependencies.

:returns: A set of pinned ``InstallRequirement``\ s.

```python
piptools.scripts.compile.BacktrackingResolver.resolve(self, max_rounds: 'int' = 10) -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_rounds` | `int` | `10` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `resolve_hashes`

Find acceptable hashes for all of the given ``InstallRequirement``\ s.

```python
piptools.scripts.compile.BacktrackingResolver.resolve_hashes(self, ireqs: 'set[InstallRequirement]') -> 'dict[InstallRequirement, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `set[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[InstallRequirement, set[str]]`

### `piptools.scripts.compile.BaseRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.scripts.compile.BaseRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.scripts.compile.BaseRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.scripts.compile.BaseRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.scripts.compile.BaseRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.scripts.compile.BaseRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.scripts.compile.DependencyCache` methods

### `as_cache_key`

Given a requirement, return its cache key.

This behavior is a little weird
in order to allow backwards compatibility with cache files. For a requirement
without extras, this will return, for example…

```python
piptools.scripts.compile.DependencyCache.as_cache_key(self, ireq: 'InstallRequirement') -> 'CacheKey'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `CacheKey`

### `clear`

```python
piptools.scripts.compile.DependencyCache.clear(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reverse_dependencies`

Return a lookup table of reverse dependencies for all the given ireqs.

Since this is all static, it only works if the dependency cache
contains the complete data, otherwise you end up with a partial…

```python
piptools.scripts.compile.DependencyCache.reverse_dependencies(self, ireqs: 'Iterable[InstallRequirement]') -> 'dict[str, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `Iterable[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[str, set[str]]`

### `write_cache`

Write the cache to disk as JSON.

```python
piptools.scripts.compile.DependencyCache.write_cache(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `piptools.scripts.compile.LegacyResolver` methods

### `get_best_match`

Return a (pinned or editable) InstallRequirement.

This indicates the best match to use for the given
InstallRequirement (in the form of an InstallRequirement).

Example:
Given the constraint Flask>=…

```python
piptools.scripts.compile.LegacyResolver.get_best_match(self, ireq: 'InstallRequirement') -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `InstallRequirement`

### `resolve`

Find concrete package versions for all the given ``InstallRequirement``\ s
and their recursive dependencies and return a set of pinned
``InstallRequirement``\ s.

Resolves constraints one round at a…

```python
piptools.scripts.compile.LegacyResolver.resolve(self, max_rounds: 'int' = 10) -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_rounds` | `int` | `10` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `resolve_hashes`

Find acceptable hashes for all of the given ``InstallRequirement``\ s.

```python
piptools.scripts.compile.LegacyResolver.resolve_hashes(self, ireqs: 'set[InstallRequirement]') -> 'dict[InstallRequirement, set[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireqs` | `set[InstallRequirement]` | `—` | pos/kw |

**Returns:** `dict[InstallRequirement, set[str]]`

### `piptools.scripts.compile.LocalRequirementsRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

```python
piptools.scripts.compile.LocalRequirementsRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.scripts.compile.LocalRequirementsRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.scripts.compile.LocalRequirementsRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallationCandidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallationCandidate`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.scripts.compile.LocalRequirementsRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given a pinned InstallRequirement, returns a set of hashes that represent
all of the files for a given requirement. It is not acceptable for an
editable or unpinned requirement to be passed to this f…

```python
piptools.scripts.compile.LocalRequirementsRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `piptools.scripts.compile.OutputWriter` methods

### `write`

```python
piptools.scripts.compile.OutputWriter.write(self, results: 'set[InstallRequirement]', unsafe_requirements: 'set[InstallRequirement]', unsafe_packages: 'set[str]', markers: 'dict[str, Marker]', hashes: 'dict[InstallRequirement, set[str]] | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `results` | `set[InstallRequirement]` | `—` | pos/kw |
| `unsafe_requirements` | `set[InstallRequirement]` | `—` | pos/kw |
| `unsafe_packages` | `set[str]` | `—` | pos/kw |
| `markers` | `dict[str, Marker]` | `—` | pos/kw |
| `hashes` | `dict[InstallRequirement, set[str]] \| None` | `—` | pos/kw |

### `write_find_links`

```python
piptools.scripts.compile.OutputWriter.write_find_links(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `write_flags`

```python
piptools.scripts.compile.OutputWriter.write_flags(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `write_format_controls`

```python
piptools.scripts.compile.OutputWriter.write_format_controls(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `write_header`

```python
piptools.scripts.compile.OutputWriter.write_header(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `write_index_options`

```python
piptools.scripts.compile.OutputWriter.write_index_options(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `write_trusted_hosts`

```python
piptools.scripts.compile.OutputWriter.write_trusted_hosts(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `piptools.scripts.compile.PyPIRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

This also saves the candidate cache and set a new one, or else the results from
the previous non-patched calls will i…

```python
piptools.scripts.compile.PyPIRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.scripts.compile.PyPIRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_all_candidates`

```python
piptools.scripts.compile.PyPIRepository.find_all_candidates(self, req_name: 'str') -> 'list[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req_name` | `str` | `—` | pos/kw |

**Returns:** `list[InstallationCandidate]`

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.scripts.compile.PyPIRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.scripts.compile.PyPIRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given an InstallRequirement, return a set of hashes that represent all
of the files for a given requirement. Unhashable requirements return an
empty set. Unpinned requirements raise a TypeError.

```python
piptools.scripts.compile.PyPIRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `resolve_reqs`

```python
piptools.scripts.compile.PyPIRepository.resolve_reqs(self, download_dir: 'str | None', ireq: 'InstallRequirement', wheel_cache: 'WheelCache') -> 'set[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `download_dir` | `str \| None` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `wheel_cache` | `WheelCache` | `—` | pos/kw |

**Returns:** `set[InstallationCandidate]`

### `piptools.scripts.sync.Distribution` methods

### `from_pip_distribution`

```python
piptools.scripts.sync.Distribution.from_pip_distribution(dist: 'BaseDistribution') -> 'Distribution'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `BaseDistribution` | `—` | pos/kw |

**Returns:** `Distribution`

### `piptools.scripts.sync.PyPIRepository` methods

### `allow_all_wheels`

Monkey patches pip.Wheel to allow wheels from all platforms and Python versions.

This also saves the candidate cache and set a new one, or else the results from
the previous non-patched calls will i…

```python
piptools.scripts.sync.PyPIRepository.allow_all_wheels(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `clear_caches`

Should clear any caches used by the implementation.

```python
piptools.scripts.sync.PyPIRepository.clear_caches(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_all_candidates`

```python
piptools.scripts.sync.PyPIRepository.find_all_candidates(self, req_name: 'str') -> 'list[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req_name` | `str` | `—` | pos/kw |

**Returns:** `list[InstallationCandidate]`

### `find_best_match`

Returns a pinned InstallRequirement object that indicates the best match
for the given InstallRequirement according to the external repository.

```python
piptools.scripts.sync.PyPIRepository.find_best_match(self, ireq: 'InstallRequirement', prereleases: 'bool | None' = None) -> 'InstallRequirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `prereleases` | `bool \| None` | `None` | pos/kw |

**Returns:** `InstallRequirement`

### `get_dependencies`

Given a pinned, URL, or editable InstallRequirement, returns a set of
dependencies (also InstallRequirements, but not necessarily pinned).
They indicate the secondary dependencies for the given requi…

```python
piptools.scripts.sync.PyPIRepository.get_dependencies(self, ireq: 'InstallRequirement') -> 'set[InstallRequirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[InstallRequirement]`

### `get_hashes`

Given an InstallRequirement, return a set of hashes that represent all
of the files for a given requirement. Unhashable requirements return an
empty set. Unpinned requirements raise a TypeError.

```python
piptools.scripts.sync.PyPIRepository.get_hashes(self, ireq: 'InstallRequirement') -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |

**Returns:** `set[str]`

### `resolve_reqs`

```python
piptools.scripts.sync.PyPIRepository.resolve_reqs(self, download_dir: 'str | None', ireq: 'InstallRequirement', wheel_cache: 'WheelCache') -> 'set[InstallationCandidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `download_dir` | `str \| None` | `—` | pos/kw |
| `ireq` | `InstallRequirement` | `—` | pos/kw |
| `wheel_cache` | `WheelCache` | `—` | pos/kw |

**Returns:** `set[InstallationCandidate]`

### `piptools.sync.Distribution` methods

### `from_pip_distribution`

```python
piptools.sync.Distribution.from_pip_distribution(dist: 'BaseDistribution') -> 'Distribution'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `BaseDistribution` | `—` | pos/kw |

**Returns:** `Distribution`


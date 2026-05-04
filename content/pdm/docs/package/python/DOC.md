---
name: package
description: "PDM package guide for Python projects using pyproject.toml, lockfiles, scripts, and publishing workflows"
metadata:
  languages: "python"
  versions: "2.26.6"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pdm,python,packaging,dependency-management,pyproject,lockfile,publishing,toml,private.example.com,Version-Sensitive,psycopg,EditableBuilder,build,check_requirements,get_overlay_env,get_shared_env,init_build_system,install,prepare_metadata,subprocess_runner,SdistBuilder,WheelBuilder,BuildError,EnvBuilder,LoggerWrapper,fileno,getName,isDaemon,is_alive,join,remove_newline,run,setDaemon,setName,start,stop,PythonEnvironment,get_finder,get_paths,get_working_set,which,Requirement,as_line,as_pinned_version,create,from_dist,from_pkg_requirement,from_req_dict,identify,matches,WorkingSet,get,is_owned,items,keys,values,build_error,get_sys_config_paths,log_subprocessor,parse_requirement,wrap_error,BareEnvironment,Candidate,as_lockfile_entry,copy_with,format,from_installation_candidate,get_revision,prepare,EnvSpec,as_dict,compare,compatibility,current,from_marker,from_spec,is_allow_all,markers,markers_with_defaults,markers_with_python,replace,wheel_compatibility,GroupSelection,all,from_options,one,validate,HookManager,should_run,skipping,try_emit,LockedRepository,add_package,dependency_generators,evaluate_candidates,fetch_hashes,find_candidates,get_dependencies,get_filtered_sources,get_hashes,is_this_package,make_this_candidate,merge_result,search,Package,PdmException,PdmUsageError,Project,add_dependencies,cache,env_or_setting,find_interpreters,get_best_matching_cpython_version,get_environment,get_locked_repository,get_provider,get_reporter,get_repository,get_resolver,get_setting,get_sources,get_synchronizer,init_global_project,is_lockfile_hash_match"
---

# pdm — package

## Install

```bash
pip install pdm
```

## Imports

```python
import pdm
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `EditableBuilder` | Class | Build egg-info in isolated env with managed Python. |
| `build` | Method | Build and store the artifact in out_dir, return the absolute path of the built… |
| `check_requirements` | Method |  |
| `get_overlay_env` | Method |  |
| `get_shared_env` | Method |  |
| `init_build_system` | Method | Initialize the build system and requires list from the PEP 517 spec |
| `install` | Method |  |
| `prepare_metadata` | Method | Prepare metadata and store in the out_dir. Some backends doesn't provide that A… |
| `subprocess_runner` | Method |  |
| `SdistBuilder` | Class | Build sdist in isolated env with managed Python. |
| `build` | Method | Build and store the artifact in out_dir, return the absolute path of the built… |
| `check_requirements` | Method |  |
| `get_overlay_env` | Method |  |
| `get_shared_env` | Method |  |
| `init_build_system` | Method | Initialize the build system and requires list from the PEP 517 spec |
| `install` | Method |  |
| `prepare_metadata` | Method | Prepare metadata and store in the out_dir. Some backends doesn't provide that A… |
| `subprocess_runner` | Method |  |
| `WheelBuilder` | Class | Build wheel in isolated env with managed Python. |
| `build` | Method | Build and store the artifact in out_dir, return the absolute path of the built… |
| `check_requirements` | Method |  |
| `get_overlay_env` | Method |  |
| `get_shared_env` | Method |  |
| `init_build_system` | Method | Initialize the build system and requires list from the PEP 517 spec |
| `install` | Method |  |
| `prepare_metadata` | Method | Prepare metadata and store in the out_dir. Some backends doesn't provide that A… |
| `subprocess_runner` | Method |  |
| `BuildError` | Class | Unspecified run-time error. |
| `EnvBuilder` | Class | A simple PEP 517 builder for an isolated environment |
| `build` | Method | Build and store the artifact in out_dir, return the absolute path of the built… |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `EditableBuilder`

Build egg-info in isolated env with managed Python.

```python
pdm.builders.EditableBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `SdistBuilder`

Build sdist in isolated env with managed Python.

```python
pdm.builders.SdistBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `WheelBuilder`

Build wheel in isolated env with managed Python.

```python
pdm.builders.WheelBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `BuildError`

Unspecified run-time error.

```python
pdm.builders.base.BuildError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `EnvBuilder`

A simple PEP 517 builder for an isolated environment

```python
pdm.builders.base.EnvBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `LoggerWrapper`

Read messages from a pipe and redirect them
to a logger (see python's logging module).

```python
pdm.builders.base.LoggerWrapper(self, logger: 'Logger', level: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logger` | `Logger` | `—` | pos/kw |
| `level` | `int` | `—` | pos/kw |

### `PythonEnvironment`

A project environment that is directly derived from a Python interpreter

```python
pdm.builders.base.PythonEnvironment(self, project: 'Project', *, python: 'str | None' = None, prefix: 'str | None' = None, extra_paths: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Project` | `—` | pos/kw |
| `python` | `str \| None` | `None` | kw |
| `prefix` | `str \| None` | `None` | kw |
| `extra_paths` | `list[str] \| None` | `None` | kw |

### `Requirement`

Base class of a package requirement.
A requirement is a (virtual) specification of a package which contains
some constraints of version, python version, or other marker.

```python
pdm.builders.base.Requirement(self, name: 'str | None' = None, marker: 'Marker | None' = None, extras: 'Sequence[str] | None' = None, specifier: 'SpecifierSet' = <SpecifierSet('')>, editable: 'bool' = False, prerelease: 'bool | None' = None, groups: 'list[str]' = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str \| None` | `None` | pos/kw |
| `marker` | `Marker \| None` | `None` | pos/kw |
| `extras` | `Sequence[str] \| None` | `None` | pos/kw |
| `specifier` | `SpecifierSet` | `<SpecifierSet('')>` | pos/kw |
| `editable` | `bool` | `False` | pos/kw |
| `prerelease` | `bool \| None` | `None` | pos/kw |
| `groups` | `list[str]` | `<factory>` | pos/kw |

### `WorkingSet`

A dictionary of currently installed distributions

```python
pdm.builders.base.WorkingSet(self, paths: 'list[str] | None' = None, shared_paths: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `list[str] \| None` | `None` | pos/kw |
| `shared_paths` | `list[str] \| None` | `None` | pos/kw |

### `EditableBuilder`

Build egg-info in isolated env with managed Python.

```python
pdm.builders.editable.EditableBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `EnvBuilder`

A simple PEP 517 builder for an isolated environment

```python
pdm.builders.editable.EnvBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `EnvBuilder`

A simple PEP 517 builder for an isolated environment

```python
pdm.builders.sdist.EnvBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `SdistBuilder`

Build sdist in isolated env with managed Python.

```python
pdm.builders.sdist.SdistBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `EnvBuilder`

A simple PEP 517 builder for an isolated environment

```python
pdm.builders.wheel.EnvBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `WheelBuilder`

Build wheel in isolated env with managed Python.

```python
pdm.builders.wheel.WheelBuilder(self, src_dir: 'str | Path', environment: 'BaseEnvironment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_dir` | `str \| Path` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |

### `BareEnvironment`

Bare environment that does not depend on project files.

```python
pdm.cli.actions.BareEnvironment(self, project: 'Project') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Project` | `—` | pos/kw |

### `Candidate`

A concrete candidate that can be downloaded and installed.
A candidate comes from the PyPI index of a package, or from the requirement itself
(for file or VCS requirements). Each candidate has a name…

```python
pdm.cli.actions.Candidate(self, req: 'Requirement', name: 'str | None' = None, version: 'str | None' = None, link: 'Link | None' = None, installed: 'im.Distribution | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `req` | `Requirement` | `—` | pos/kw |
| `name` | `str \| None` | `None` | pos/kw |
| `version` | `str \| None` | `None` | pos/kw |
| `link` | `Link \| None` | `None` | pos/kw |
| `installed` | `im.Distribution \| None` | `None` | pos/kw |

### `EnvSpec`

EnvSpec(requires_python: 'VersionSpecifier', platform: 'Platform | None' = None, implementation: 'Implementation | None' = None)

```python
pdm.cli.actions.EnvSpec(self, requires_python: 'VersionSpecifier', platform: 'Platform | None' = None, implementation: 'Implementation | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `requires_python` | `VersionSpecifier` | `—` | pos/kw |
| `platform` | `Platform \| None` | `None` | pos/kw |
| `implementation` | `Implementation \| None` | `None` | pos/kw |

### `GroupSelection`

```python
pdm.cli.actions.GroupSelection(self, project: 'Project', *, default: 'bool' = True, dev: 'bool | None' = None, groups: 'Sequence[str]' = (), group: 'str | None' = None, excluded_groups: 'Sequence[str]' = (), exclude_non_existing: 'bool' = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Project` | `—` | pos/kw |
| `default` | `bool` | `True` | kw |
| `dev` | `bool \| None` | `None` | kw |
| `groups` | `Sequence[str]` | `()` | kw |
| `group` | `str \| None` | `None` | kw |
| `excluded_groups` | `Sequence[str]` | `()` | kw |
| `exclude_non_existing` | `bool` | `False` | kw |

### `HookManager`

```python
pdm.cli.actions.HookManager(self, project: 'Project', skip: 'list[str] | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Project` | `—` | pos/kw |
| `skip` | `list[str] \| None` | `None` | pos/kw |

### `LockedRepository`

A Repository acts as the source of packages and metadata.

```python
pdm.cli.actions.LockedRepository(self, lockfile: 'Mapping[str, Any]', sources: 'list[RepositoryConfig]', environment: 'BaseEnvironment', env_spec: 'EnvSpec | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lockfile` | `Mapping[str, Any]` | `—` | pos/kw |
| `sources` | `list[RepositoryConfig]` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |
| `env_spec` | `EnvSpec \| None` | `None` | pos/kw |

### `Package`

Package(candidate: 'Candidate', dependencies: 'list[str] | None' = None, summary: 'str' = '', marker: 'BaseMarker' = <factory>)

```python
pdm.cli.actions.Package(self, candidate: 'Candidate', dependencies: 'list[str] | None' = None, summary: 'str' = '', marker: 'BaseMarker' = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `candidate` | `Candidate` | `—` | pos/kw |
| `dependencies` | `list[str] \| None` | `None` | pos/kw |
| `summary` | `str` | `''` | pos/kw |
| `marker` | `BaseMarker` | `<factory>` | pos/kw |

### `PdmException`

Common base class for all non-exit exceptions.

```python
pdm.cli.actions.PdmException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PdmUsageError`

Common base class for all non-exit exceptions.

```python
pdm.cli.actions.PdmUsageError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Project`

Core project class.

Args:
    core: The core instance.
    root_path: The root path of the project.
    is_global: Whether the project is global.
    global_config: The path to the global config fil…

```python
pdm.cli.actions.Project(self, core: 'Core', root_path: 'str | Path | None', is_global: 'bool' = False, global_config: 'str | Path | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `core` | `Core` | `—` | pos/kw |
| `root_path` | `str \| Path \| None` | `—` | pos/kw |
| `is_global` | `bool` | `False` | pos/kw |
| `global_config` | `str \| Path \| None` | `None` | pos/kw |

## Functions

### `build_error`

Get a build error with meaningful error message
from the subprocess output.

```python
pdm.builders.base.build_error(e: 'subprocess.CalledProcessError') -> 'BuildError'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `e` | `subprocess.CalledProcessError` | `—` | pos/kw |

**Returns:** `BuildError`

### `get_sys_config_paths`

Return the sys_config.get_paths() result for the python interpreter

```python
pdm.builders.base.get_sys_config_paths(executable: 'str', vars: 'dict[str, str] | None' = None, kind: 'str' = 'default') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `executable` | `str` | `—` | pos/kw |
| `vars` | `dict[str, str] \| None` | `None` | pos/kw |
| `kind` | `str` | `'default'` | pos/kw |

**Returns:** `dict[str, str]`

### `log_subprocessor`

```python
pdm.builders.base.log_subprocessor(cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `parse_requirement`

```python
pdm.builders.base.parse_requirement(line: 'str', editable: 'bool' = False) -> 'Requirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `str` | `—` | pos/kw |
| `editable` | `bool` | `False` | pos/kw |

**Returns:** `Requirement`

### `wrap_error`

```python
pdm.builders.base.wrap_error(func: 'Callable[P, R]') -> 'Callable[P, R]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Callable[P, R]` | `—` | pos/kw |

**Returns:** `Callable[P, R]`

### `wrap_error`

```python
pdm.builders.editable.wrap_error(func: 'Callable[P, R]') -> 'Callable[P, R]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Callable[P, R]` | `—` | pos/kw |

**Returns:** `Callable[P, R]`

### `wrap_error`

```python
pdm.builders.sdist.wrap_error(func: 'Callable[P, R]') -> 'Callable[P, R]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Callable[P, R]` | `—` | pos/kw |

**Returns:** `Callable[P, R]`

### `wrap_error`

```python
pdm.builders.wheel.wrap_error(func: 'Callable[P, R]') -> 'Callable[P, R]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Callable[P, R]` | `—` | pos/kw |

**Returns:** `Callable[P, R]`

## Methods

### `pdm.builders.EditableBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.EditableBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.EditableBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.EditableBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.EditableBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.EditableBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.EditableBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.EditableBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.EditableBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.SdistBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.SdistBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.SdistBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.SdistBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.SdistBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.SdistBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.SdistBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.SdistBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.SdistBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.WheelBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.WheelBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.WheelBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.WheelBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.WheelBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.WheelBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.WheelBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.WheelBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.WheelBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.base.EnvBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.base.EnvBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.base.EnvBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.base.EnvBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.base.EnvBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.base.EnvBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.base.EnvBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.base.EnvBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.base.EnvBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.base.LoggerWrapper` methods

### `fileno`

```python
pdm.builders.base.LoggerWrapper.fileno(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `getName`

Return a string used for identification purposes only.

This method is deprecated, use the name attribute instead.

```python
pdm.builders.base.LoggerWrapper.getName(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `isDaemon`

Return whether this thread is a daemon.

This method is deprecated, use the daemon attribute instead.

```python
pdm.builders.base.LoggerWrapper.isDaemon(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_alive`

Return whether the thread is alive.

This method returns True just before the run() method starts until just
after the run() method terminates. See also the module function
enumerate().

```python
pdm.builders.base.LoggerWrapper.is_alive(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `join`

Wait until the thread terminates.

This blocks the calling thread until the thread whose join() method is
called terminates -- either normally or through an unhandled exception
or until the optional…

```python
pdm.builders.base.LoggerWrapper.join(self, timeout=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timeout` | `—` | `None` | pos/kw |

### `remove_newline`

```python
pdm.builders.base.LoggerWrapper.remove_newline(msg: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `msg` | `str` | `—` | pos/kw |

**Returns:** `str`

### `run`

Method representing the thread's activity.

You may override this method in a subclass. The standard run() method
invokes the callable object passed to the object's constructor as the
target argument…

```python
pdm.builders.base.LoggerWrapper.run(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setDaemon`

Set whether this thread is a daemon.

This method is deprecated, use the .daemon property instead.

```python
pdm.builders.base.LoggerWrapper.setDaemon(self, daemonic)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `daemonic` | `—` | `—` | pos/kw |

### `setName`

Set the name string for this thread.

This method is deprecated, use the name attribute instead.

```python
pdm.builders.base.LoggerWrapper.setName(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `start`

Start the thread's activity.

It must be called at most once per thread object. It arranges for the
object's run() method to be invoked in a separate thread of control.

This method will raise a Runt…

```python
pdm.builders.base.LoggerWrapper.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

```python
pdm.builders.base.LoggerWrapper.stop(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pdm.builders.base.PythonEnvironment` methods

### `get_finder`

Return the package finder of given index sources.

:param sources: a list of sources the finder should search in.
:param ignore_compatibility: (DEPRECATED)whether to ignore the python version
    and…

```python
pdm.builders.base.PythonEnvironment.get_finder(self, sources: 'list[RepositoryConfig] | None' = None, ignore_compatibility: 'bool | NotSetType' = <pdm._types.NotSetType object at 0x7049533ebcb0>, minimal_version: 'bool' = False, env_spec: 'EnvSpec | None' = None) -> 'Generator[unearth.PackageFinder]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sources` | `list[RepositoryConfig] \| None` | `None` | pos/kw |
| `ignore_compatibility` | `bool \| NotSetType` | `<pdm._types.NotSetType object at 0x7049533ebcb0>` | pos/kw |
| `minimal_version` | `bool` | `False` | pos/kw |
| `env_spec` | `EnvSpec \| None` | `None` | pos/kw |

**Returns:** `Generator[unearth.PackageFinder]`

### `get_paths`

Get paths like ``sysconfig.get_paths()`` for installation.

:param dist_name: The package name to be installed, if any.

```python
pdm.builders.base.PythonEnvironment.get_paths(self, dist_name: 'str | None' = None) -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dist_name` | `str \| None` | `None` | pos/kw |

**Returns:** `dict[str, str]`

### `get_working_set`

Get the working set based on local packages directory.

```python
pdm.builders.base.PythonEnvironment.get_working_set(self) -> 'WorkingSet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `WorkingSet`

### `which`

Get the full path of the given executable against this environment.

```python
pdm.builders.base.PythonEnvironment.which(self, command: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `pdm.builders.base.Requirement` methods

### `as_line`

```python
pdm.builders.base.Requirement.as_line(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `as_pinned_version`

Return a new requirement with the given pinned version.

```python
pdm.builders.base.Requirement.as_pinned_version(self: 'T', other_version: 'str | None') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |
| `other_version` | `str \| None` | `—` | pos/kw |

**Returns:** `T`

### `create`

```python
pdm.builders.base.Requirement.create(**kwargs: 'Any') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `T`

### `from_dist`

```python
pdm.builders.base.Requirement.from_dist(dist: 'Distribution') -> 'Requirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `Distribution` | `—` | pos/kw |

**Returns:** `Requirement`

### `from_pkg_requirement`

```python
pdm.builders.base.Requirement.from_pkg_requirement(req: 'PackageRequirement') -> 'Requirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `req` | `PackageRequirement` | `—` | pos/kw |

**Returns:** `Requirement`

### `from_req_dict`

```python
pdm.builders.base.Requirement.from_req_dict(name: 'str', req_dict: 'RequirementDict') -> 'Requirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `req_dict` | `RequirementDict` | `—` | pos/kw |

**Returns:** `Requirement`

### `identify`

```python
pdm.builders.base.Requirement.identify(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `matches`

Return whether the passed in PEP 508 string
is the same requirement as this one.

```python
pdm.builders.base.Requirement.matches(self, line: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `pdm.builders.base.WorkingSet` methods

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
pdm.builders.base.WorkingSet.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `is_owned`

```python
pdm.builders.base.WorkingSet.is_owned(self, key: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `items`

D.items() -> a set-like object providing a view on D's items

```python
pdm.builders.base.WorkingSet.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
pdm.builders.base.WorkingSet.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `values`

D.values() -> an object providing a view on D's values

```python
pdm.builders.base.WorkingSet.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pdm.builders.editable.EditableBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.editable.EditableBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.editable.EditableBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.editable.EditableBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.editable.EditableBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.editable.EditableBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.editable.EditableBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.editable.EditableBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.editable.EditableBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.editable.EnvBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.editable.EnvBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.editable.EnvBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.editable.EnvBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.editable.EnvBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.editable.EnvBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.editable.EnvBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.editable.EnvBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.editable.EnvBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.sdist.EnvBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.sdist.EnvBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.sdist.EnvBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.sdist.EnvBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.sdist.EnvBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.sdist.EnvBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.sdist.EnvBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.sdist.EnvBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.sdist.EnvBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.sdist.SdistBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.sdist.SdistBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.sdist.SdistBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.sdist.SdistBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.sdist.SdistBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.sdist.SdistBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.sdist.SdistBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.sdist.SdistBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.sdist.SdistBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.wheel.EnvBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.wheel.EnvBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.wheel.EnvBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.wheel.EnvBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.wheel.EnvBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.wheel.EnvBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.wheel.EnvBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.wheel.EnvBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.wheel.EnvBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.builders.wheel.WheelBuilder` methods

### `build`

Build and store the artifact in out_dir,
return the absolute path of the built result.

```python
pdm.builders.wheel.WheelBuilder.build(self, out_dir: 'str', metadata_directory: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |
| `metadata_directory` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `check_requirements`

```python
pdm.builders.wheel.WheelBuilder.check_requirements(self, reqs: 'Iterable[str]') -> 'Iterable[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reqs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Iterable[Requirement]`

### `get_overlay_env`

```python
pdm.builders.wheel.WheelBuilder.get_overlay_env(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get_shared_env`

```python
pdm.builders.wheel.WheelBuilder.get_shared_env(self, key: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `int` | `—` | pos/kw |

**Returns:** `str`

### `init_build_system`

Initialize the build system and requires list from the PEP 517 spec

```python
pdm.builders.wheel.WheelBuilder.init_build_system(self, build_system: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `build_system` | `dict[str, Any]` | `—` | pos/kw |

### `install`

```python
pdm.builders.wheel.WheelBuilder.install(self, requirements: 'Iterable[str]', shared: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str]` | `—` | pos/kw |
| `shared` | `bool` | `False` | pos/kw |

### `prepare_metadata`

Prepare metadata and store in the out_dir.
Some backends doesn't provide that API, in that case the metadata will be
retrieved from the built result.

```python
pdm.builders.wheel.WheelBuilder.prepare_metadata(self, out_dir: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out_dir` | `str` | `—` | pos/kw |

**Returns:** `str`

### `subprocess_runner`

```python
pdm.builders.wheel.WheelBuilder.subprocess_runner(self, cmd: 'list[str]', cwd: 'str | Path | None' = None, extra_environ: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `list[str]` | `—` | pos/kw |
| `cwd` | `str \| Path \| None` | `None` | pos/kw |
| `extra_environ` | `dict[str, str] \| None` | `None` | pos/kw |

### `pdm.cli.actions.BareEnvironment` methods

### `get_finder`

Return the package finder of given index sources.

:param sources: a list of sources the finder should search in.
:param ignore_compatibility: (DEPRECATED)whether to ignore the python version
    and…

```python
pdm.cli.actions.BareEnvironment.get_finder(self, sources: 'list[RepositoryConfig] | None' = None, ignore_compatibility: 'bool | NotSetType' = <pdm._types.NotSetType object at 0x7049533ebcb0>, minimal_version: 'bool' = False, env_spec: 'EnvSpec | None' = None) -> 'Generator[unearth.PackageFinder]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sources` | `list[RepositoryConfig] \| None` | `None` | pos/kw |
| `ignore_compatibility` | `bool \| NotSetType` | `<pdm._types.NotSetType object at 0x7049533ebcb0>` | pos/kw |
| `minimal_version` | `bool` | `False` | pos/kw |
| `env_spec` | `EnvSpec \| None` | `None` | pos/kw |

**Returns:** `Generator[unearth.PackageFinder]`

### `get_paths`

Get paths like ``sysconfig.get_paths()`` for installation.

:param dist_name: The package name to be installed, if any.

```python
pdm.cli.actions.BareEnvironment.get_paths(self, dist_name: 'str | None' = None) -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dist_name` | `str \| None` | `None` | pos/kw |

**Returns:** `dict[str, str]`

### `get_working_set`

Get the working set based on local packages directory.

```python
pdm.cli.actions.BareEnvironment.get_working_set(self) -> 'WorkingSet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `WorkingSet`

### `which`

Get the full path of the given executable against this environment.

```python
pdm.cli.actions.BareEnvironment.which(self, command: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `pdm.cli.actions.Candidate` methods

### `as_lockfile_entry`

Build a lockfile entry dictionary for the candidate.

```python
pdm.cli.actions.Candidate.as_lockfile_entry(self, project_root: 'Path') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_root` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `copy_with`

```python
pdm.cli.actions.Candidate.copy_with(self, requirement: 'Requirement') -> 'Candidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirement` | `Requirement` | `—` | pos/kw |

**Returns:** `Candidate`

### `format`

Format for output.

```python
pdm.cli.actions.Candidate.format(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `from_installation_candidate`

Build a candidate from unearth's find result.

```python
pdm.cli.actions.Candidate.from_installation_candidate(candidate: 'Package', req: 'Requirement') -> 'Candidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `candidate` | `Package` | `—` | pos/kw |
| `req` | `Requirement` | `—` | pos/kw |

**Returns:** `Candidate`

### `get_revision`

```python
pdm.cli.actions.Candidate.get_revision(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `identify`

```python
pdm.cli.actions.Candidate.identify(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `prepare`

Prepare the candidate for installation.

```python
pdm.cli.actions.Candidate.prepare(self, environment: 'BaseEnvironment', reporter: 'CandidateReporter | None' = None) -> 'PreparedCandidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `BaseEnvironment` | `—` | pos/kw |
| `reporter` | `CandidateReporter \| None` | `None` | pos/kw |

**Returns:** `PreparedCandidate`

### `pdm.cli.actions.EnvSpec` methods

### `as_dict`

```python
pdm.cli.actions.EnvSpec.as_dict(self) -> 'dict[str, str | bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, str | bool]`

### `compare`

```python
pdm.cli.actions.EnvSpec.compare(self, target: 'EnvSpec') -> 'EnvCompatibility'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `target` | `EnvSpec` | `—` | pos/kw |

**Returns:** `EnvCompatibility`

### `compatibility`

```python
pdm.cli.actions.EnvSpec.compatibility(self, wheel_python_tags: 'list[str]', wheel_abi_tags: 'list[str]', wheel_platform_tags: 'list[str]') -> 'tuple[int, int, int, int] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wheel_python_tags` | `list[str]` | `—` | pos/kw |
| `wheel_abi_tags` | `list[str]` | `—` | pos/kw |
| `wheel_platform_tags` | `list[str]` | `—` | pos/kw |

**Returns:** `tuple[int, int, int, int] | None`

### `current`

```python
pdm.cli.actions.EnvSpec.current() -> 'Self'
```

**Returns:** `Self`

### `from_marker`

Create an EnvSpec from a Marker object.

```python
pdm.cli.actions.EnvSpec.from_marker(marker: 'Marker') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `marker` | `Marker` | `—` | pos/kw |

**Returns:** `Self`

### `from_spec`

```python
pdm.cli.actions.EnvSpec.from_spec(requires_python: 'str', platform: 'str | None' = None, implementation: 'str | None' = None, gil_disabled: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `requires_python` | `str` | `—` | pos/kw |
| `platform` | `str \| None` | `None` | pos/kw |
| `implementation` | `str \| None` | `None` | pos/kw |
| `gil_disabled` | `bool` | `False` | pos/kw |

**Returns:** `Self`

### `is_allow_all`

```python
pdm.cli.actions.EnvSpec.is_allow_all(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `markers`

```python
pdm.cli.actions.EnvSpec.markers(self) -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `markers_with_defaults`

```python
pdm.cli.actions.EnvSpec.markers_with_defaults(self) -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `markers_with_python`

```python
pdm.cli.actions.EnvSpec.markers_with_python(self) -> 'Marker'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Marker`

### `replace`

```python
pdm.cli.actions.EnvSpec.replace(self, **kwargs: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `wheel_compatibility`

```python
pdm.cli.actions.EnvSpec.wheel_compatibility(self, wheel_filename: 'str') -> 'tuple[int, int, int, int] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wheel_filename` | `str` | `—` | pos/kw |

**Returns:** `tuple[int, int, int, int] | None`

### `pdm.cli.actions.GroupSelection` methods

### `all`

```python
pdm.cli.actions.GroupSelection.all(self) -> 'list[str] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str] | None`

### `from_options`

```python
pdm.cli.actions.GroupSelection.from_options(project: 'Project', options: 'argparse.Namespace') -> 'GroupSelection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Project` | `—` | pos/kw |
| `options` | `argparse.Namespace` | `—` | pos/kw |

**Returns:** `GroupSelection`

### `one`

```python
pdm.cli.actions.GroupSelection.one(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `validate`

```python
pdm.cli.actions.GroupSelection.validate(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pdm.cli.actions.HookManager` methods

### `should_run`

Tells whether a task given its name should run or not
according to the current skipping rules.

```python
pdm.cli.actions.HookManager.should_run(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `skipping`

Temporarily skip some hooks.

```python
pdm.cli.actions.HookManager.skipping(self, *names: 'str') -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `names` | `str` | `—` | *args |

**Returns:** `Generator[None]`

### `try_emit`

Emit a hook signal if rules allow it.

```python
pdm.cli.actions.HookManager.try_emit(self, name: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `pdm.cli.actions.LockedRepository` methods

### `add_package`

```python
pdm.cli.actions.LockedRepository.add_package(self, package: 'Package') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `Package` | `—` | pos/kw |

### `dependency_generators`

Return an iterable of getter functions to get dependencies, which will be
called one by one.

```python
pdm.cli.actions.LockedRepository.dependency_generators(self) -> 'Iterable[Callable[[Candidate], CandidateMetadata]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterable[Callable[[Candidate], CandidateMetadata]]`

### `evaluate_candidates`

```python
pdm.cli.actions.LockedRepository.evaluate_candidates(self, groups: 'Collection[str]', evaluate_markers: 'bool' = True) -> 'Iterable[Package]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `groups` | `Collection[str]` | `—` | pos/kw |
| `evaluate_markers` | `bool` | `True` | pos/kw |

**Returns:** `Iterable[Package]`

### `fetch_hashes`

Fetch hashes for candidates in parallel

```python
pdm.cli.actions.LockedRepository.fetch_hashes(self, candidates: 'Iterable[Candidate]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `candidates` | `Iterable[Candidate]` | `—` | pos/kw |

### `find_candidates`

Find candidates of the given NamedRequirement. Let it to be implemented in
subclasses.

:param requirement: the requirement to find
:param allow_prereleases: whether to include pre-releases
:param ig…

```python
pdm.cli.actions.LockedRepository.find_candidates(self, requirement: 'Requirement', allow_prereleases: 'bool | None' = None, ignore_requires_python: 'bool' = False, minimal_version: 'bool' = False) -> 'Iterable[Candidate]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirement` | `Requirement` | `—` | pos/kw |
| `allow_prereleases` | `bool \| None` | `None` | pos/kw |
| `ignore_requires_python` | `bool` | `False` | pos/kw |
| `minimal_version` | `bool` | `False` | pos/kw |

**Returns:** `Iterable[Candidate]`

### `get_dependencies`

Get (dependencies, python_specifier, summary) of the candidate.

```python
pdm.cli.actions.LockedRepository.get_dependencies(self, candidate: 'Candidate') -> 'tuple[list[Requirement], PySpecSet, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `candidate` | `Candidate` | `—` | pos/kw |

**Returns:** `tuple[list[Requirement], PySpecSet, str]`

### `get_filtered_sources`

Get matching sources based on the index attribute.

```python
pdm.cli.actions.LockedRepository.get_filtered_sources(self, req: 'Requirement') -> 'list[RepositoryConfig]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req` | `Requirement` | `—` | pos/kw |

**Returns:** `list[RepositoryConfig]`

### `get_hashes`

Get hashes of all possible installable candidates
of a given package version.

```python
pdm.cli.actions.LockedRepository.get_hashes(self, candidate: 'Candidate') -> 'list[FileHash]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `candidate` | `Candidate` | `—` | pos/kw |

**Returns:** `list[FileHash]`

### `is_this_package`

Whether the requirement is the same as this package

```python
pdm.cli.actions.LockedRepository.is_this_package(self, requirement: 'Requirement') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirement` | `Requirement` | `—` | pos/kw |

**Returns:** `bool`

### `make_this_candidate`

Make a candidate for this package.
In this case the finder will look for a candidate from the package sources

```python
pdm.cli.actions.LockedRepository.make_this_candidate(self, requirement: 'Requirement') -> 'Candidate'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirement` | `Requirement` | `—` | pos/kw |

**Returns:** `Candidate`

### `merge_result`

```python
pdm.cli.actions.LockedRepository.merge_result(self, env_spec: 'EnvSpec', result: 'Iterable[Package]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_spec` | `EnvSpec` | `—` | pos/kw |
| `result` | `Iterable[Package]` | `—` | pos/kw |

### `search`

Search package by name or summary.

:param query: query string
:returns: search result, a dictionary of name: package metadata

```python
pdm.cli.actions.LockedRepository.search(self, query: 'str') -> 'SearchResults'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `str` | `—` | pos/kw |

**Returns:** `SearchResults`

### `pdm.cli.actions.Project` methods

### `add_dependencies`

Add requirements to the given group, and return the requirements of that group.

```python
pdm.cli.actions.Project.add_dependencies(self, requirements: 'Iterable[str | Requirement]', to_group: 'str' = 'default', dev: 'bool' = False, show_message: 'bool' = True, write: 'bool' = True) -> 'list[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `Iterable[str \| Requirement]` | `—` | pos/kw |
| `to_group` | `str` | `'default'` | pos/kw |
| `dev` | `bool` | `False` | pos/kw |
| `show_message` | `bool` | `True` | pos/kw |
| `write` | `bool` | `True` | pos/kw |

**Returns:** `list[Requirement]`

### `cache`

```python
pdm.cli.actions.Project.cache(self, name: 'str') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `Path`

### `env_or_setting`

Get a value from environment variable and fallback on a given setting.

Returns `None` if both the environment variable and the key does not exists.

```python
pdm.cli.actions.Project.env_or_setting(self, var: 'str', key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `var` | `str` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `find_interpreters`

Return an iterable of interpreter paths that matches the given specifier,
which can be:
    1. a version specifier like 3.7
    2. an absolute path
    3. a short name like python3
    4. None that r…

```python
pdm.cli.actions.Project.find_interpreters(self, python_spec: 'str | None' = None, search_venv: 'bool | None' = None) -> 'Iterable[PythonInfo]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `python_spec` | `str \| None` | `None` | pos/kw |
| `search_venv` | `bool \| None` | `None` | pos/kw |

**Returns:** `Iterable[PythonInfo]`

### `get_best_matching_cpython_version`

Returns the best matching CPython version that fits requires-python, this platform and arch.
If no best match could be found, return None.

Default for best match strategy is "highest" possible inter…

```python
pdm.cli.actions.Project.get_best_matching_cpython_version(self, use_minimum: 'bool | None' = False, freethreaded: 'bool' = False) -> 'PythonVersion | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `use_minimum` | `bool \| None` | `False` | pos/kw |
| `freethreaded` | `bool` | `False` | pos/kw |

**Returns:** `PythonVersion | None`

### `get_dependencies`

```python
pdm.cli.actions.Project.get_dependencies(self, group: 'str | None' = None, all_dependencies: 'dict[str, list[Requirement]] | None' = None) -> 'Sequence[Requirement]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `group` | `str \| None` | `None` | pos/kw |
| `all_dependencies` | `dict[str, list[Requirement]] \| None` | `None` | pos/kw |

**Returns:** `Sequence[Requirement]`

### `get_environment`

```python
pdm.cli.actions.Project.get_environment(self) -> 'BaseEnvironment'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `BaseEnvironment`

### `get_locked_repository`

```python
pdm.cli.actions.Project.get_locked_repository(self, env_spec: 'EnvSpec | None' = None) -> 'LockedRepository'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_spec` | `EnvSpec \| None` | `None` | pos/kw |

**Returns:** `LockedRepository`

### `get_provider`

Build a provider class for resolver.

:param strategy: the resolve strategy
:param tracked_names: the names of packages that needs to update
:param for_install: if the provider is for install
:param…

```python
pdm.cli.actions.Project.get_provider(self, strategy: 'str' = 'all', tracked_names: 'Iterable[str] | None' = None, for_install: 'bool' = False, ignore_compatibility: 'bool | NotSetType' = <pdm._types.NotSetType object at 0x7049533ebcb0>, direct_minimal_versions: 'bool' = False, env_spec: 'EnvSpec | None' = None, locked_repository: 'LockedRepository | None' = None) -> 'BaseProvider'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `strategy` | `str` | `'all'` | pos/kw |
| `tracked_names` | `Iterable[str] \| None` | `None` | pos/kw |
| `for_install` | `bool` | `False` | pos/kw |
| `ignore_compatibility` | `bool \| NotSetType` | `<pdm._types.NotSetType object at 0x7049533ebcb0>` | pos/kw |
| `direct_minimal_versions` | `bool` | `False` | pos/kw |
| `env_spec` | `EnvSpec \| None` | `None` | pos/kw |
| `locked_repository` | `LockedRepository \| None` | `None` | pos/kw |

**Returns:** `BaseProvider`

### `get_reporter`

Return the reporter object to construct a resolver.

:param requirements: requirements to resolve
:param tracked_names: the names of packages that needs to update
:param spinner: optional spinner obj…

```python
pdm.cli.actions.Project.get_reporter(self, requirements: 'list[Requirement]', tracked_names: 'Iterable[str] | None' = None) -> 'RichLockReporter'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requirements` | `list[Requirement]` | `—` | pos/kw |
| `tracked_names` | `Iterable[str] \| None` | `None` | pos/kw |

**Returns:** `RichLockReporter`

### `get_repository`

Get the repository object

```python
pdm.cli.actions.Project.get_repository(self, cls: 'type[BaseRepository] | None' = None, ignore_compatibility: 'bool | NotSetType' = <pdm._types.NotSetType object at 0x7049533ebcb0>, env_spec: 'EnvSpec | None' = None) -> 'BaseRepository'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cls` | `type[BaseRepository] \| None` | `None` | pos/kw |
| `ignore_compatibility` | `bool \| NotSetType` | `<pdm._types.NotSetType object at 0x7049533ebcb0>` | pos/kw |
| `env_spec` | `EnvSpec \| None` | `None` | pos/kw |

**Returns:** `BaseRepository`

### `get_resolver`

Get the resolver class to use for the project.

```python
pdm.cli.actions.Project.get_resolver(self, allow_uv: 'bool' = True) -> 'type[Resolver]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `allow_uv` | `bool` | `True` | pos/kw |

**Returns:** `type[Resolver]`

### `get_setting`

Get a setting from its dotted key (without the `tool.pdm` prefix).

Returns `None` if the key does not exists.

```python
pdm.cli.actions.Project.get_setting(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `get_sources`

```python
pdm.cli.actions.Project.get_sources(self, expand_env: 'bool' = True, include_stored: 'bool' = False) -> 'list[RepositoryConfig]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expand_env` | `bool` | `True` | pos/kw |
| `include_stored` | `bool` | `False` | pos/kw |

**Returns:** `list[RepositoryConfig]`

### `get_synchronizer`

Get the synchronizer class to use for the project.

```python
pdm.cli.actions.Project.get_synchronizer(self, quiet: 'bool' = False, allow_uv: 'bool' = True) -> 'type[BaseSynchronizer]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |
| `allow_uv` | `bool` | `True` | pos/kw |

**Returns:** `type[BaseSynchronizer]`

### `init_global_project`

```python
pdm.cli.actions.Project.init_global_project(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_lockfile_hash_match`

```python
pdm.cli.actions.Project.is_lockfile_hash_match(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`


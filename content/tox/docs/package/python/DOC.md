---
name: package
description: "tox package guide for Python test environment orchestration and automation"
metadata:
  languages: "python"
  versions: "4.49.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "tox,python,testing,virtualenv,ci,pytest,toml,Version-Sensitive,main,Config,clear_env,get_env,get_section_config,make,pos_args,sections,ConfigSet,add_config,add_constant,get_configs,load,mark_finalized,primary_key,register_config,unused,CoreConfigSet,EnvConfigSet,CircularChainError,ConfigConstantDefinition,ConfigDefinition,ConfigDynamicDefinition,ConfigLoadArgs,copy,Loader,build,found_keys,load_raw,to,to_bool,to_command,to_dict,to_env_list,to_list,to_path,to_set,to_str,Fail,SetEnv,update,use_replacer,EnvList,Source,envs,get_base_sections,get_core_section,get_loader,get_loaders,get_tox_env_section,transform_section,discover_source,Command,MissingRequiredConfigKeyError,shell_cmd,ExecuteRequest,Outcome,assert_failure,assert_success,log_run_done,out_err,Execute,build_instance,call,register_conf,ExecuteInstance,ExecuteOptions,ExecuteStatus,interrupt,set_out_err,wait,write_stdin,StdinSource,SyncWrite,colored,handler,LocalSubProcessExecuteInstance,get_stream_file_no,LocalSubProcessExecutor,LocalSubprocessExecuteFailedStatus,LocalSubprocessExecuteStatus,ReadViaThread,shebang,LocalSubProcessPep517ExecuteInstance,LocalSubProcessPep517Executor,close,local_execute"
---

# tox — package

## Install

```bash
pip install tox
```

## Imports

```python
import tox
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `main` | Function |  |
| `Config` | Class | Main configuration object for tox. |
| `clear_env` | Method |  |
| `get_env` | Method | Return the configuration for a given tox environment (will create if not exist… |
| `get_section_config` | Method |  |
| `make` | Method | Make a tox configuration object. |
| `pos_args` | Method | :param to_path: if not None rewrite relative posargs paths from cwd to to_path… |
| `sections` | Method |  |
| `ConfigSet` | Class | A set of configuration that belong together (such as a tox environment settings… |
| `add_config` | Method | Add configuration value.  :param keys: the keys under what to register the conf… |
| `add_constant` | Method | Add a constant value.  :param keys: the keys under what to register the config… |
| `get_configs` | Method | :returns: a mapping of config keys to their definitions |
| `load` | Method | Get the config value for a given key (will materialize in case of dynamic confi… |
| `mark_finalized` | Method |  |
| `primary_key` | Method | Get the primary key for a config key.  :param key: the config key  :returns: th… |
| `register_config` | Method |  |
| `unused` | Method | :returns: Return a list of keys present in the config source but not used |
| `CoreConfigSet` | Class | Configuration set for the core tox config. |
| `add_config` | Method | Add configuration value.  :param keys: the keys under what to register the conf… |
| `add_constant` | Method | Add a constant value.  :param keys: the keys under what to register the config… |
| `get_configs` | Method | :returns: a mapping of config keys to their definitions |
| `load` | Method | Get the config value for a given key (will materialize in case of dynamic confi… |
| `mark_finalized` | Method |  |
| `primary_key` | Method | Get the primary key for a config key.  :param key: the config key  :returns: th… |
| `register_config` | Method |  |
| `unused` | Method | :returns: Return a list of keys present in the config source but not used |
| `EnvConfigSet` | Class | Configuration set for a tox environment. |
| `add_config` | Method | Add configuration value.  :param keys: the keys under what to register the conf… |
| `add_constant` | Method | Add a constant value.  :param keys: the keys under what to register the config… |
| `get_configs` | Method | :returns: a mapping of config keys to their definitions |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `Config`

Main configuration object for tox.

```python
tox.config.main.Config(self, config_source: 'Source', options: 'Parsed', root: 'Path', pos_args: 'Sequence[str] | None', work_dir: 'Path', extra_envs: 'Iterable[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_source` | `Source` | `—` | pos/kw |
| `options` | `Parsed` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `pos_args` | `Sequence[str] \| None` | `—` | pos/kw |
| `work_dir` | `Path` | `—` | pos/kw |
| `extra_envs` | `Iterable[str]` | `—` | pos/kw |

### `ConfigSet`

A set of configuration that belong together (such as a tox environment settings, core tox settings).

```python
tox.config.main.ConfigSet(self, conf: 'Config', section: 'Section', env_name: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf` | `Config` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |

### `CoreConfigSet`

Configuration set for the core tox config.

```python
tox.config.main.CoreConfigSet(self, conf: 'Config', section: 'Section', root: 'Path', src_path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf` | `Config` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `src_path` | `Path` | `—` | pos/kw |

### `EnvConfigSet`

Configuration set for a tox environment.

```python
tox.config.main.EnvConfigSet(self, conf: 'Config', section: 'Section', env_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf` | `Config` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `env_name` | `str` | `—` | pos/kw |

### `CircularChainError`

circular chain in config

```python
tox.config.of_type.CircularChainError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigConstantDefinition`

A configuration definition whose value is defined upfront (such as the tox environment name).

```python
tox.config.of_type.ConfigConstantDefinition(self, keys: 'Iterable[str]', desc: 'str', value: 'Callable[[], T] | T') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `Iterable[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `Callable[[], T] \| T` | `—` | pos/kw |

### `ConfigDefinition`

Abstract base class for configuration definitions.

```python
tox.config.of_type.ConfigDefinition(self, keys: 'Iterable[str]', desc: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `Iterable[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |

### `ConfigDynamicDefinition`

A configuration definition that comes from a source (such as in memory, an ini file, a toml file, etc.).

```python
tox.config.of_type.ConfigDynamicDefinition(self, keys: 'Iterable[str]', desc: 'str', of_type: 'type[T] | UnionType', default: 'Callable[[Config, str | None], T] | T', post_process: 'Callable[[T], T] | None' = None, factory: 'Factory[T] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `Iterable[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `of_type` | `type[T] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], T] \| T` | `—` | pos/kw |
| `post_process` | `Callable[[T], T] \| None` | `None` | pos/kw |
| `factory` | `Factory[T] \| None` | `None` | pos/kw |

### `ConfigLoadArgs`

Arguments that help loading a configuration value.

```python
tox.config.of_type.ConfigLoadArgs(self, chain: 'list[str] | None', name: 'str | None', env_name: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `chain` | `list[str] \| None` | `—` | pos/kw |
| `name` | `str \| None` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |

### `Loader`

Loader loads configuration values and converts it.

:param overrides: A list of overrides to be applied.

```python
tox.config.of_type.Loader(self, section: 'Section', overrides: 'list[Override]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `section` | `Section` | `—` | pos/kw |
| `overrides` | `list[Override]` | `—` | pos/kw |

### `ConfigLoadArgs`

Arguments that help loading a configuration value.

```python
tox.config.set_env.ConfigLoadArgs(self, chain: 'list[str] | None', name: 'str | None', env_name: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `chain` | `list[str] \| None` | `—` | pos/kw |
| `name` | `str \| None` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |

### `Fail`

Failed creating env.

```python
tox.config.set_env.Fail(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SetEnv`

```python
tox.config.set_env.SetEnv(self, raw: 'SetEnvRaw', name: 'str', env_name: 'str | None', root: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `raw` | `SetEnvRaw` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |

### `ConfigConstantDefinition`

A configuration definition whose value is defined upfront (such as the tox environment name).

```python
tox.config.sets.ConfigConstantDefinition(self, keys: 'Iterable[str]', desc: 'str', value: 'Callable[[], T] | T') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `Iterable[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `Callable[[], T] \| T` | `—` | pos/kw |

### `ConfigDefinition`

Abstract base class for configuration definitions.

```python
tox.config.sets.ConfigDefinition(self, keys: 'Iterable[str]', desc: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `Iterable[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |

### `ConfigDynamicDefinition`

A configuration definition that comes from a source (such as in memory, an ini file, a toml file, etc.).

```python
tox.config.sets.ConfigDynamicDefinition(self, keys: 'Iterable[str]', desc: 'str', of_type: 'type[T] | UnionType', default: 'Callable[[Config, str | None], T] | T', post_process: 'Callable[[T], T] | None' = None, factory: 'Factory[T] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `Iterable[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `of_type` | `type[T] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], T] \| T` | `—` | pos/kw |
| `post_process` | `Callable[[T], T] \| None` | `None` | pos/kw |
| `factory` | `Factory[T] \| None` | `None` | pos/kw |

### `ConfigLoadArgs`

Arguments that help loading a configuration value.

```python
tox.config.sets.ConfigLoadArgs(self, chain: 'list[str] | None', name: 'str | None', env_name: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `chain` | `list[str] \| None` | `—` | pos/kw |
| `name` | `str \| None` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |

### `ConfigSet`

A set of configuration that belong together (such as a tox environment settings, core tox settings).

```python
tox.config.sets.ConfigSet(self, conf: 'Config', section: 'Section', env_name: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf` | `Config` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |

### `CoreConfigSet`

Configuration set for the core tox config.

```python
tox.config.sets.CoreConfigSet(self, conf: 'Config', section: 'Section', root: 'Path', src_path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf` | `Config` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `src_path` | `Path` | `—` | pos/kw |

### `EnvConfigSet`

Configuration set for a tox environment.

```python
tox.config.sets.EnvConfigSet(self, conf: 'Config', section: 'Section', env_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf` | `Config` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `env_name` | `str` | `—` | pos/kw |

### `EnvList`

A tox environment list.

```python
tox.config.sets.EnvList(self, envs: 'Sequence[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `envs` | `Sequence[str]` | `—` | pos/kw |

### `SetEnv`

```python
tox.config.sets.SetEnv(self, raw: 'SetEnvRaw', name: 'str', env_name: 'str | None', root: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `raw` | `SetEnvRaw` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |

### `Source`

Source is able to return a configuration value (for either the core or per environment source).

```python
tox.config.source.Source(self, path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |

### `CircularChainError`

circular chain in config

```python
tox.config.types.CircularChainError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Command`

A command to execute.

```python
tox.config.types.Command(self, args: 'list[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `list[str]` | `—` | pos/kw |

### `EnvList`

A tox environment list.

```python
tox.config.types.EnvList(self, envs: 'Sequence[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `envs` | `Sequence[str]` | `—` | pos/kw |

### `MissingRequiredConfigKeyError`

missing required config key

Used by the two toml loaders in order to identify if config keys are present.

```python
tox.config.types.MissingRequiredConfigKeyError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ExecuteRequest`

Defines a commands execution request.

```python
tox.execute.ExecuteRequest(self, cmd: 'Sequence[str | Path]', cwd: 'Path', env: 'dict[str, str]', stdin: 'StdinSource', run_id: 'str', allow: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `Sequence[str \| Path]` | `—` | pos/kw |
| `cwd` | `Path` | `—` | pos/kw |
| `env` | `dict[str, str]` | `—` | pos/kw |
| `stdin` | `StdinSource` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `allow` | `list[str] \| None` | `None` | pos/kw |

### `Outcome`

Result of a command execution.

```python
tox.execute.Outcome(self, request: 'ExecuteRequest', show_on_standard: 'bool', exit_code: 'int | None', out: 'str', err: 'str', start: 'float', end: 'float', cmd: 'Sequence[str]', metadata: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show_on_standard` | `bool` | `—` | pos/kw |
| `exit_code` | `int \| None` | `—` | pos/kw |
| `out` | `str` | `—` | pos/kw |
| `err` | `str` | `—` | pos/kw |
| `start` | `float` | `—` | pos/kw |
| `end` | `float` | `—` | pos/kw |
| `cmd` | `Sequence[str]` | `—` | pos/kw |
| `metadata` | `dict[str, Any]` | `—` | pos/kw |

### `Execute`

Abstract API for execution of a tox environment.

```python
tox.execute.api.Execute(self, colored: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `colored` | `bool` | `—` | pos/kw |

### `ExecuteInstance`

An instance of a command execution.

```python
tox.execute.api.ExecuteInstance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

### `ExecuteOptions`

```python
tox.execute.api.ExecuteOptions(self, env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `ExecuteRequest`

Defines a commands execution request.

```python
tox.execute.api.ExecuteRequest(self, cmd: 'Sequence[str | Path]', cwd: 'Path', env: 'dict[str, str]', stdin: 'StdinSource', run_id: 'str', allow: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `Sequence[str \| Path]` | `—` | pos/kw |
| `cwd` | `Path` | `—` | pos/kw |
| `env` | `dict[str, str]` | `—` | pos/kw |
| `stdin` | `StdinSource` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `allow` | `list[str] \| None` | `None` | pos/kw |

### `ExecuteStatus`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
tox.execute.api.ExecuteStatus(self, options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

### `Outcome`

Result of a command execution.

```python
tox.execute.api.Outcome(self, request: 'ExecuteRequest', show_on_standard: 'bool', exit_code: 'int | None', out: 'str', err: 'str', start: 'float', end: 'float', cmd: 'Sequence[str]', metadata: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show_on_standard` | `bool` | `—` | pos/kw |
| `exit_code` | `int \| None` | `—` | pos/kw |
| `out` | `str` | `—` | pos/kw |
| `err` | `str` | `—` | pos/kw |
| `start` | `float` | `—` | pos/kw |
| `end` | `float` | `—` | pos/kw |
| `cmd` | `Sequence[str]` | `—` | pos/kw |
| `metadata` | `dict[str, Any]` | `—` | pos/kw |

### `StdinSource`

Create a collection of name/value pairs.

Example enumeration:

>>> class Color(Enum):
...     RED = 1
...     BLUE = 2
...     GREEN = 3

Access them by:

- attribute access:

  >>> Color.RED
  <Col…

```python
tox.execute.api.StdinSource(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `SyncWrite`

Make sure data collected is synced in-memory and to the target stream on every newline and time period.

Used to propagate executed commands output to the standard output/error streams visible to the…

```python
tox.execute.api.SyncWrite(self, name: 'str', target: 'IO[bytes] | None', color: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `target` | `IO[bytes] \| None` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |

### `Execute`

Abstract API for execution of a tox environment.

```python
tox.execute.local_sub_process.Execute(self, colored: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `colored` | `bool` | `—` | pos/kw |

### `ExecuteInstance`

An instance of a command execution.

```python
tox.execute.local_sub_process.ExecuteInstance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

### `ExecuteOptions`

```python
tox.execute.local_sub_process.ExecuteOptions(self, env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `ExecuteRequest`

Defines a commands execution request.

```python
tox.execute.local_sub_process.ExecuteRequest(self, cmd: 'Sequence[str | Path]', cwd: 'Path', env: 'dict[str, str]', stdin: 'StdinSource', run_id: 'str', allow: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `Sequence[str \| Path]` | `—` | pos/kw |
| `cwd` | `Path` | `—` | pos/kw |
| `env` | `dict[str, str]` | `—` | pos/kw |
| `stdin` | `StdinSource` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `allow` | `list[str] \| None` | `None` | pos/kw |

### `ExecuteStatus`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
tox.execute.local_sub_process.ExecuteStatus(self, options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

### `Fail`

Failed creating env.

```python
tox.execute.local_sub_process.Fail(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LocalSubProcessExecuteInstance`

An instance of a command execution.

```python
tox.execute.local_sub_process.LocalSubProcessExecuteInstance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite', on_exit_drain: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |
| `on_exit_drain` | `bool` | `True` | pos/kw |

### `LocalSubProcessExecutor`

Abstract API for execution of a tox environment.

```python
tox.execute.local_sub_process.LocalSubProcessExecutor(self, colored: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `colored` | `bool` | `—` | pos/kw |

### `LocalSubprocessExecuteFailedStatus`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
tox.execute.local_sub_process.LocalSubprocessExecuteFailedStatus(self, options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite', exit_code: 'int | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |
| `exit_code` | `int \| None` | `—` | pos/kw |

### `LocalSubprocessExecuteStatus`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
tox.execute.local_sub_process.LocalSubprocessExecuteStatus(self, options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite', process: 'Popen[bytes]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |
| `process` | `Popen[bytes]` | `—` | pos/kw |

### `ReadViaThread`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
tox.execute.local_sub_process.ReadViaThread(self, file_no: 'int', handler: 'Callable[[bytes], int]', name: 'str', drain: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `file_no` | `int` | `—` | pos/kw |
| `handler` | `Callable[[bytes], int]` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `drain` | `bool` | `—` | pos/kw |

### `StdinSource`

Create a collection of name/value pairs.

Example enumeration:

>>> class Color(Enum):
...     RED = 1
...     BLUE = 2
...     GREEN = 3

Access them by:

- attribute access:

  >>> Color.RED
  <Col…

```python
tox.execute.local_sub_process.StdinSource(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Execute`

Abstract API for execution of a tox environment.

```python
tox.execute.pep517_backend.Execute(self, colored: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `colored` | `bool` | `—` | pos/kw |

### `ExecuteInstance`

An instance of a command execution.

```python
tox.execute.pep517_backend.ExecuteInstance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

### `ExecuteOptions`

```python
tox.execute.pep517_backend.ExecuteOptions(self, env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `ExecuteRequest`

Defines a commands execution request.

```python
tox.execute.pep517_backend.ExecuteRequest(self, cmd: 'Sequence[str | Path]', cwd: 'Path', env: 'dict[str, str]', stdin: 'StdinSource', run_id: 'str', allow: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `Sequence[str \| Path]` | `—` | pos/kw |
| `cwd` | `Path` | `—` | pos/kw |
| `env` | `dict[str, str]` | `—` | pos/kw |
| `stdin` | `StdinSource` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `allow` | `list[str] \| None` | `None` | pos/kw |

### `ExecuteStatus`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
tox.execute.pep517_backend.ExecuteStatus(self, options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

### `LocalSubProcessExecuteInstance`

An instance of a command execution.

```python
tox.execute.pep517_backend.LocalSubProcessExecuteInstance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite', on_exit_drain: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |
| `on_exit_drain` | `bool` | `True` | pos/kw |

### `LocalSubProcessPep517ExecuteInstance`

A backend invocation.

```python
tox.execute.pep517_backend.LocalSubProcessPep517ExecuteInstance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite', instance_status: 'tuple[LocalSubProcessExecuteInstance, ExecuteStatus]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |
| `instance_status` | `tuple[LocalSubProcessExecuteInstance, ExecuteStatus]` | `—` | pos/kw |

### `LocalSubProcessPep517Executor`

Executor holding the backend process.

```python
tox.execute.pep517_backend.LocalSubProcessPep517Executor(self, colored: 'bool', cmd: 'Sequence[str]', env: 'dict[str, str]', cwd: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `colored` | `bool` | `—` | pos/kw |
| `cmd` | `Sequence[str]` | `—` | pos/kw |
| `env` | `dict[str, str]` | `—` | pos/kw |
| `cwd` | `Path` | `—` | pos/kw |

### `StdinSource`

Create a collection of name/value pairs.

Example enumeration:

>>> class Color(Enum):
...     RED = 1
...     BLUE = 2
...     GREEN = 3

Access them by:

- attribute access:

  >>> Color.RED
  <Col…

```python
tox.execute.pep517_backend.StdinSource(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

## Functions

### `main`

```python
tox.main(args: 'Sequence[str]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `int`

### `discover_source`

Discover a source for configuration.

:param config_file: the file storing the source
:param root_dir: the root directory as set by the user (None means not set)

:returns: the source of the config

```python
tox.config.source.discover_source(config_file: 'Path | None', root_dir: 'Path | None') -> 'Source'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `Path \| None` | `—` | pos/kw |
| `root_dir` | `Path \| None` | `—` | pos/kw |

**Returns:** `Source`

### `shell_cmd`

```python
tox.config.types.shell_cmd(cmd: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `shebang`

:param exe: the executable

:returns: the shebang interpreter arguments

```python
tox.execute.local_sub_process.shebang(exe: 'str') -> 'list[str] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exe` | `str` | `—` | pos/kw |

**Returns:** `list[str] | None`

## Methods

### `tox.config.main.Config` methods

### `clear_env`

```python
tox.config.main.Config.clear_env(self, name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `get_env`

Return the configuration for a given tox environment (will create if not exist yet).

:param item: the name of the environment is
:param package: a flag indicating if the environment is of type packa…

```python
tox.config.main.Config.get_env(self, item: 'str', package: 'bool' = False, loaders: 'Sequence[Loader[Any]] | None' = None) -> 'EnvConfigSet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `package` | `bool` | `False` | pos/kw |
| `loaders` | `Sequence[Loader[Any]] \| None` | `None` | pos/kw |

**Returns:** `EnvConfigSet`

### `get_section_config`

```python
tox.config.main.Config.get_section_config(self, section: 'Section', base: 'list[str] | None', of_type: 'type[T]', for_env: 'str | None', loaders: 'Sequence[Loader[Any]] | None' = None) -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `base` | `list[str] \| None` | `—` | pos/kw |
| `of_type` | `type[T]` | `—` | pos/kw |
| `for_env` | `str \| None` | `—` | pos/kw |
| `loaders` | `Sequence[Loader[Any]] \| None` | `None` | pos/kw |

**Returns:** `T`

### `make`

Make a tox configuration object.

```python
tox.config.main.Config.make(parsed: 'Parsed', pos_args: 'Sequence[str] | None', source: 'Source', extra_envs: 'Iterable[str]') -> 'Config'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parsed` | `Parsed` | `—` | pos/kw |
| `pos_args` | `Sequence[str] \| None` | `—` | pos/kw |
| `source` | `Source` | `—` | pos/kw |
| `extra_envs` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Config`

### `pos_args`

:param to_path: if not None rewrite relative posargs paths from cwd to to_path

:returns: positional argument

```python
tox.config.main.Config.pos_args(self, to_path: 'Path | None') -> 'tuple[str, ...] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `to_path` | `Path \| None` | `—` | pos/kw |

**Returns:** `tuple[str, ...] | None`

### `sections`

```python
tox.config.main.Config.sections(self) -> 'Iterator[Section]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[Section]`

### `tox.config.main.ConfigSet` methods

### `add_config`

Add configuration value.

:param keys: the keys under what to register the config (first is primary key)
:param of_type: the type of the config value
:param default: the default value of the config v…

```python
tox.config.main.ConfigSet.add_config(self, keys: 'str | Sequence[str]', of_type: 'type[V] | UnionType', default: 'Callable[[Config, str | None], V] | V', desc: 'str', post_process: 'Callable[[V], V] | None' = None, factory: 'Factory[Any] | None' = None) -> 'ConfigDynamicDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], V] \| V` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `post_process` | `Callable[[V], V] \| None` | `None` | pos/kw |
| `factory` | `Factory[Any] \| None` | `None` | pos/kw |

**Returns:** `ConfigDynamicDefinition[V]`

### `add_constant`

Add a constant value.

:param keys: the keys under what to register the config (first is primary key)
:param desc: a help message describing the configuration
:param value: the config value to use

:…

```python
tox.config.main.ConfigSet.add_constant(self, keys: 'str | Sequence[str]', desc: 'str', value: 'V') -> 'ConfigConstantDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `V` | `—` | pos/kw |

**Returns:** `ConfigConstantDefinition[V]`

### `get_configs`

:returns: a mapping of config keys to their definitions

```python
tox.config.main.ConfigSet.get_configs(self) -> 'Generator[ConfigDefinition[Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[ConfigDefinition[Any], None, None]`

### `load`

Get the config value for a given key (will materialize in case of dynamic config).

:param item: the config key
:param chain: a chain of configuration keys already loaded for this load operation (use…

```python
tox.config.main.ConfigSet.load(self, item: 'str', chain: 'list[str] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `chain` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `mark_finalized`

```python
tox.config.main.ConfigSet.mark_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `primary_key`

Get the primary key for a config key.

:param key: the config key

:returns: the key that's considered the primary for the input key

```python
tox.config.main.ConfigSet.primary_key(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `register_config`

```python
tox.config.main.ConfigSet.register_config(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused`

:returns: Return a list of keys present in the config source but not used

```python
tox.config.main.ConfigSet.unused(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `tox.config.main.CoreConfigSet` methods

### `add_config`

Add configuration value.

:param keys: the keys under what to register the config (first is primary key)
:param of_type: the type of the config value
:param default: the default value of the config v…

```python
tox.config.main.CoreConfigSet.add_config(self, keys: 'str | Sequence[str]', of_type: 'type[V] | UnionType', default: 'Callable[[Config, str | None], V] | V', desc: 'str', post_process: 'Callable[[V], V] | None' = None, factory: 'Factory[Any] | None' = None) -> 'ConfigDynamicDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], V] \| V` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `post_process` | `Callable[[V], V] \| None` | `None` | pos/kw |
| `factory` | `Factory[Any] \| None` | `None` | pos/kw |

**Returns:** `ConfigDynamicDefinition[V]`

### `add_constant`

Add a constant value.

:param keys: the keys under what to register the config (first is primary key)
:param desc: a help message describing the configuration
:param value: the config value to use

:…

```python
tox.config.main.CoreConfigSet.add_constant(self, keys: 'str | Sequence[str]', desc: 'str', value: 'V') -> 'ConfigConstantDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `V` | `—` | pos/kw |

**Returns:** `ConfigConstantDefinition[V]`

### `get_configs`

:returns: a mapping of config keys to their definitions

```python
tox.config.main.CoreConfigSet.get_configs(self) -> 'Generator[ConfigDefinition[Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[ConfigDefinition[Any], None, None]`

### `load`

Get the config value for a given key (will materialize in case of dynamic config).

:param item: the config key
:param chain: a chain of configuration keys already loaded for this load operation (use…

```python
tox.config.main.CoreConfigSet.load(self, item: 'str', chain: 'list[str] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `chain` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `mark_finalized`

```python
tox.config.main.CoreConfigSet.mark_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `primary_key`

Get the primary key for a config key.

:param key: the config key

:returns: the key that's considered the primary for the input key

```python
tox.config.main.CoreConfigSet.primary_key(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `register_config`

```python
tox.config.main.CoreConfigSet.register_config(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused`

:returns: Return a list of keys present in the config source but not used

```python
tox.config.main.CoreConfigSet.unused(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `tox.config.main.EnvConfigSet` methods

### `add_config`

Add configuration value.

:param keys: the keys under what to register the config (first is primary key)
:param of_type: the type of the config value
:param default: the default value of the config v…

```python
tox.config.main.EnvConfigSet.add_config(self, keys: 'str | Sequence[str]', of_type: 'type[V] | UnionType', default: 'Callable[[Config, str | None], V] | V', desc: 'str', post_process: 'Callable[[V], V] | None' = None, factory: 'Factory[Any] | None' = None) -> 'ConfigDynamicDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], V] \| V` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `post_process` | `Callable[[V], V] \| None` | `None` | pos/kw |
| `factory` | `Factory[Any] \| None` | `None` | pos/kw |

**Returns:** `ConfigDynamicDefinition[V]`

### `add_constant`

Add a constant value.

:param keys: the keys under what to register the config (first is primary key)
:param desc: a help message describing the configuration
:param value: the config value to use

:…

```python
tox.config.main.EnvConfigSet.add_constant(self, keys: 'str | Sequence[str]', desc: 'str', value: 'V') -> 'ConfigConstantDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `V` | `—` | pos/kw |

**Returns:** `ConfigConstantDefinition[V]`

### `get_configs`

:returns: a mapping of config keys to their definitions

```python
tox.config.main.EnvConfigSet.get_configs(self) -> 'Generator[ConfigDefinition[Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[ConfigDefinition[Any], None, None]`

### `load`

Get the config value for a given key (will materialize in case of dynamic config).

:param item: the config key
:param chain: a chain of configuration keys already loaded for this load operation (use…

```python
tox.config.main.EnvConfigSet.load(self, item: 'str', chain: 'list[str] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `chain` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `mark_finalized`

```python
tox.config.main.EnvConfigSet.mark_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `primary_key`

Get the primary key for a config key.

:param key: the config key

:returns: the key that's considered the primary for the input key

```python
tox.config.main.EnvConfigSet.primary_key(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `register_config`

```python
tox.config.main.EnvConfigSet.register_config(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused`

:returns: Return a list of keys present in the config source but not used

```python
tox.config.main.EnvConfigSet.unused(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `tox.config.of_type.ConfigLoadArgs` methods

### `copy`

:returns: create a copy of the object

```python
tox.config.of_type.ConfigLoadArgs.copy(self) -> 'ConfigLoadArgs'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `ConfigLoadArgs`

### `tox.config.of_type.Loader` methods

### `build`

Materialize the raw configuration value from the loader.

:param future: a future which when called will provide the converted config value
:param key: the config key
:param of_type: the config type…

```python
tox.config.of_type.Loader.build(self, key: 'str', of_type: 'type[V] | UnionType', factory: 'Factory[V]', conf: 'Config | None', raw: 'T', args: 'ConfigLoadArgs') -> 'V'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `factory` | `Factory[V]` | `—` | pos/kw |
| `conf` | `Config \| None` | `—` | pos/kw |
| `raw` | `T` | `—` | pos/kw |
| `args` | `ConfigLoadArgs` | `—` | pos/kw |

**Returns:** `V`

### `found_keys`

A list of configuration keys found within the configuration.

```python
tox.config.of_type.Loader.found_keys(self) -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `set[str]`

### `load`

Load a value (raw and then convert).

:param key: the key under it lives
:param of_type: the type to convert to
:param factory: factory method to build the object
:param conf: the configuration objec…

```python
tox.config.of_type.Loader.load(self, key: 'str', of_type: 'type[V] | UnionType', factory: 'Factory[V]', conf: 'Config | None', args: 'ConfigLoadArgs', all_keys: 'Iterable[str]' = ()) -> 'V'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `factory` | `Factory[V]` | `—` | pos/kw |
| `conf` | `Config \| None` | `—` | pos/kw |
| `args` | `ConfigLoadArgs` | `—` | pos/kw |
| `all_keys` | `Iterable[str]` | `()` | pos/kw |

**Returns:** `V`

### `load_raw`

Load the raw object from the config store.

:param key: the key under what we want the configuration
:param env_name: load for env name
:param conf: the global config object

```python
tox.config.of_type.Loader.load_raw(self, key: 'str', conf: 'Config | None', env_name: 'str | None') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `conf` | `Config \| None` | `—` | pos/kw |
| `env_name` | `str \| None` | `—` | pos/kw |

**Returns:** `T`

### `to`

Convert given raw type to python type.

:param raw: the raw type
:param of_type: python type
:param factory: factory method to build the object

:returns: the converted type

```python
tox.config.of_type.Loader.to(self, raw: 'T', of_type: 'type[V] | UnionType', factory: 'Factory[V]') -> 'V'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `raw` | `T` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `factory` | `Factory[V]` | `—` | pos/kw |

**Returns:** `V`

### `to_bool`

Convert to boolean.

:param value: the value to convert

:returns: a boolean representation of the value

```python
tox.config.of_type.Loader.to_bool(value: 'T') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |

**Returns:** `bool`

### `to_command`

Convert to a command to execute.

:param value: the value to convert

:returns: command representation of the value

```python
tox.config.of_type.Loader.to_command(value: 'T') -> 'Command | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |

**Returns:** `Command | None`

### `to_dict`

Convert to dictionary.

:param value: the value to convert
:param of_type: a tuple indicating the type of the key and the value

:returns: a iteration of key-value pairs that gets populated into a di…

```python
tox.config.of_type.Loader.to_dict(value: 'T', of_type: 'tuple[type[Any], type[Any]]') -> 'Iterator[tuple[T, T]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |
| `of_type` | `tuple[type[Any], type[Any]]` | `—` | pos/kw |

**Returns:** `Iterator[tuple[T, T]]`

### `to_env_list`

Convert to a tox EnvList.

:param value: the value to convert

:returns: a list of tox environments from the value

```python
tox.config.of_type.Loader.to_env_list(value: 'T') -> 'EnvList'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |

**Returns:** `EnvList`

### `to_list`

Convert to list.

:param value: the value to convert
:param of_type: the type of elements in the list

:returns: a list representation of the value

```python
tox.config.of_type.Loader.to_list(value: 'T', of_type: 'type[Any]') -> 'Iterator[T]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |
| `of_type` | `type[Any]` | `—` | pos/kw |

**Returns:** `Iterator[T]`

### `to_path`

Convert to path.

:param value: the value to convert

:returns: path representation of the value

```python
tox.config.of_type.Loader.to_path(value: 'T') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |

**Returns:** `Path`

### `to_set`

Convert to set.

:param value: the value to convert
:param of_type: the type of elements in the set

:returns: a set representation of the value

```python
tox.config.of_type.Loader.to_set(value: 'T', of_type: 'type[Any]') -> 'Iterator[T]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |
| `of_type` | `type[Any]` | `—` | pos/kw |

**Returns:** `Iterator[T]`

### `to_str`

Convert to string.

:param value: the value to convert

:returns: a string representation of the value

```python
tox.config.of_type.Loader.to_str(value: 'T') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `T` | `—` | pos/kw |

**Returns:** `str`

### `tox.config.set_env.ConfigLoadArgs` methods

### `copy`

:returns: create a copy of the object

```python
tox.config.set_env.ConfigLoadArgs.copy(self) -> 'ConfigLoadArgs'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `ConfigLoadArgs`

### `tox.config.set_env.SetEnv` methods

### `load`

```python
tox.config.set_env.SetEnv.load(self, item: 'str', args: 'ConfigLoadArgs | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `args` | `ConfigLoadArgs \| None` | `None` | pos/kw |

**Returns:** `str`

### `update`

```python
tox.config.set_env.SetEnv.update(self, param: 'Mapping[str, str] | SetEnv', *, override: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `param` | `Mapping[str, str] \| SetEnv` | `—` | pos/kw |
| `override` | `bool` | `True` | kw |

### `use_replacer`

```python
tox.config.set_env.SetEnv.use_replacer(self, value: 'Replacer', args: 'ConfigLoadArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Replacer` | `—` | pos/kw |
| `args` | `ConfigLoadArgs` | `—` | pos/kw |

### `tox.config.sets.ConfigLoadArgs` methods

### `copy`

:returns: create a copy of the object

```python
tox.config.sets.ConfigLoadArgs.copy(self) -> 'ConfigLoadArgs'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `ConfigLoadArgs`

### `tox.config.sets.ConfigSet` methods

### `add_config`

Add configuration value.

:param keys: the keys under what to register the config (first is primary key)
:param of_type: the type of the config value
:param default: the default value of the config v…

```python
tox.config.sets.ConfigSet.add_config(self, keys: 'str | Sequence[str]', of_type: 'type[V] | UnionType', default: 'Callable[[Config, str | None], V] | V', desc: 'str', post_process: 'Callable[[V], V] | None' = None, factory: 'Factory[Any] | None' = None) -> 'ConfigDynamicDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], V] \| V` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `post_process` | `Callable[[V], V] \| None` | `None` | pos/kw |
| `factory` | `Factory[Any] \| None` | `None` | pos/kw |

**Returns:** `ConfigDynamicDefinition[V]`

### `add_constant`

Add a constant value.

:param keys: the keys under what to register the config (first is primary key)
:param desc: a help message describing the configuration
:param value: the config value to use

:…

```python
tox.config.sets.ConfigSet.add_constant(self, keys: 'str | Sequence[str]', desc: 'str', value: 'V') -> 'ConfigConstantDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `V` | `—` | pos/kw |

**Returns:** `ConfigConstantDefinition[V]`

### `get_configs`

:returns: a mapping of config keys to their definitions

```python
tox.config.sets.ConfigSet.get_configs(self) -> 'Generator[ConfigDefinition[Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[ConfigDefinition[Any], None, None]`

### `load`

Get the config value for a given key (will materialize in case of dynamic config).

:param item: the config key
:param chain: a chain of configuration keys already loaded for this load operation (use…

```python
tox.config.sets.ConfigSet.load(self, item: 'str', chain: 'list[str] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `chain` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `mark_finalized`

```python
tox.config.sets.ConfigSet.mark_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `primary_key`

Get the primary key for a config key.

:param key: the config key

:returns: the key that's considered the primary for the input key

```python
tox.config.sets.ConfigSet.primary_key(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `register_config`

```python
tox.config.sets.ConfigSet.register_config(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused`

:returns: Return a list of keys present in the config source but not used

```python
tox.config.sets.ConfigSet.unused(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `tox.config.sets.CoreConfigSet` methods

### `add_config`

Add configuration value.

:param keys: the keys under what to register the config (first is primary key)
:param of_type: the type of the config value
:param default: the default value of the config v…

```python
tox.config.sets.CoreConfigSet.add_config(self, keys: 'str | Sequence[str]', of_type: 'type[V] | UnionType', default: 'Callable[[Config, str | None], V] | V', desc: 'str', post_process: 'Callable[[V], V] | None' = None, factory: 'Factory[Any] | None' = None) -> 'ConfigDynamicDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], V] \| V` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `post_process` | `Callable[[V], V] \| None` | `None` | pos/kw |
| `factory` | `Factory[Any] \| None` | `None` | pos/kw |

**Returns:** `ConfigDynamicDefinition[V]`

### `add_constant`

Add a constant value.

:param keys: the keys under what to register the config (first is primary key)
:param desc: a help message describing the configuration
:param value: the config value to use

:…

```python
tox.config.sets.CoreConfigSet.add_constant(self, keys: 'str | Sequence[str]', desc: 'str', value: 'V') -> 'ConfigConstantDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `V` | `—` | pos/kw |

**Returns:** `ConfigConstantDefinition[V]`

### `get_configs`

:returns: a mapping of config keys to their definitions

```python
tox.config.sets.CoreConfigSet.get_configs(self) -> 'Generator[ConfigDefinition[Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[ConfigDefinition[Any], None, None]`

### `load`

Get the config value for a given key (will materialize in case of dynamic config).

:param item: the config key
:param chain: a chain of configuration keys already loaded for this load operation (use…

```python
tox.config.sets.CoreConfigSet.load(self, item: 'str', chain: 'list[str] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `chain` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `mark_finalized`

```python
tox.config.sets.CoreConfigSet.mark_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `primary_key`

Get the primary key for a config key.

:param key: the config key

:returns: the key that's considered the primary for the input key

```python
tox.config.sets.CoreConfigSet.primary_key(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `register_config`

```python
tox.config.sets.CoreConfigSet.register_config(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused`

:returns: Return a list of keys present in the config source but not used

```python
tox.config.sets.CoreConfigSet.unused(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `tox.config.sets.EnvConfigSet` methods

### `add_config`

Add configuration value.

:param keys: the keys under what to register the config (first is primary key)
:param of_type: the type of the config value
:param default: the default value of the config v…

```python
tox.config.sets.EnvConfigSet.add_config(self, keys: 'str | Sequence[str]', of_type: 'type[V] | UnionType', default: 'Callable[[Config, str | None], V] | V', desc: 'str', post_process: 'Callable[[V], V] | None' = None, factory: 'Factory[Any] | None' = None) -> 'ConfigDynamicDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `of_type` | `type[V] \| UnionType` | `—` | pos/kw |
| `default` | `Callable[[Config, str \| None], V] \| V` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `post_process` | `Callable[[V], V] \| None` | `None` | pos/kw |
| `factory` | `Factory[Any] \| None` | `None` | pos/kw |

**Returns:** `ConfigDynamicDefinition[V]`

### `add_constant`

Add a constant value.

:param keys: the keys under what to register the config (first is primary key)
:param desc: a help message describing the configuration
:param value: the config value to use

:…

```python
tox.config.sets.EnvConfigSet.add_constant(self, keys: 'str | Sequence[str]', desc: 'str', value: 'V') -> 'ConfigConstantDefinition[V]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `str \| Sequence[str]` | `—` | pos/kw |
| `desc` | `str` | `—` | pos/kw |
| `value` | `V` | `—` | pos/kw |

**Returns:** `ConfigConstantDefinition[V]`

### `get_configs`

:returns: a mapping of config keys to their definitions

```python
tox.config.sets.EnvConfigSet.get_configs(self) -> 'Generator[ConfigDefinition[Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[ConfigDefinition[Any], None, None]`

### `load`

Get the config value for a given key (will materialize in case of dynamic config).

:param item: the config key
:param chain: a chain of configuration keys already loaded for this load operation (use…

```python
tox.config.sets.EnvConfigSet.load(self, item: 'str', chain: 'list[str] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `chain` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `mark_finalized`

```python
tox.config.sets.EnvConfigSet.mark_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `primary_key`

Get the primary key for a config key.

:param key: the config key

:returns: the key that's considered the primary for the input key

```python
tox.config.sets.EnvConfigSet.primary_key(self, key: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `str`

### `register_config`

```python
tox.config.sets.EnvConfigSet.register_config(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused`

:returns: Return a list of keys present in the config source but not used

```python
tox.config.sets.EnvConfigSet.unused(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `tox.config.sets.SetEnv` methods

### `load`

```python
tox.config.sets.SetEnv.load(self, item: 'str', args: 'ConfigLoadArgs | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |
| `args` | `ConfigLoadArgs \| None` | `None` | pos/kw |

**Returns:** `str`

### `update`

```python
tox.config.sets.SetEnv.update(self, param: 'Mapping[str, str] | SetEnv', *, override: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `param` | `Mapping[str, str] \| SetEnv` | `—` | pos/kw |
| `override` | `bool` | `True` | kw |

### `use_replacer`

```python
tox.config.sets.SetEnv.use_replacer(self, value: 'Replacer', args: 'ConfigLoadArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Replacer` | `—` | pos/kw |
| `args` | `ConfigLoadArgs` | `—` | pos/kw |

### `tox.config.source.Source` methods

### `envs`

:param core_conf: the core configuration set

:returns: a list of environments defined within this source

```python
tox.config.source.Source.envs(self, core_conf: 'CoreConfigSet') -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `core_conf` | `CoreConfigSet` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `get_base_sections`

```python
tox.config.source.Source.get_base_sections(self, base: 'list[str]', in_section: 'Section') -> 'Iterator[Section]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `base` | `list[str]` | `—` | pos/kw |
| `in_section` | `Section` | `—` | pos/kw |

**Returns:** `Iterator[Section]`

### `get_core_section`

:returns: the core section

```python
tox.config.source.Source.get_core_section(self) -> 'Section'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Section`

### `get_loader`

```python
tox.config.source.Source.get_loader(self, section: 'Section', override_map: 'OverrideMap') -> 'Loader[Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `override_map` | `OverrideMap` | `—` | pos/kw |

**Returns:** `Loader[Any] | None`

### `get_loaders`

Return a loader that loads settings from a given section name.

:param section: the section to load
:param base: base sections to fallback to
:param override_map: a list of overrides to apply
:param…

```python
tox.config.source.Source.get_loaders(self, section: 'Section', base: 'list[str] | None', override_map: 'OverrideMap', conf: 'ConfigSet') -> 'Iterator[Loader[Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |
| `base` | `list[str] \| None` | `—` | pos/kw |
| `override_map` | `OverrideMap` | `—` | pos/kw |
| `conf` | `ConfigSet` | `—` | pos/kw |

**Returns:** `Iterator[Loader[Any]]`

### `get_tox_env_section`

:returns: the section for a tox environment

```python
tox.config.source.Source.get_tox_env_section(self, item: 'str') -> 'tuple[Section, list[str], list[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `str` | `—` | pos/kw |

**Returns:** `tuple[Section, list[str], list[str]]`

### `sections`

Return a loader that loads the core configuration values.

:returns: the core loader from this source

```python
tox.config.source.Source.sections(self) -> 'Iterator[Section]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[Section]`

### `transform_section`

```python
tox.config.source.Source.transform_section(self, section: 'Section') -> 'Section'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `section` | `Section` | `—` | pos/kw |

**Returns:** `Section`

### `tox.execute.Outcome` methods

### `assert_failure`

Assert that the execution failed.

```python
tox.execute.Outcome.assert_failure(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `assert_success`

Assert that the execution succeeded.

```python
tox.execute.Outcome.assert_success(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `log_run_done`

Log that the run was done.

:param lvl: the level on what to log as interpreted by :func:`logging.log`

```python
tox.execute.Outcome.log_run_done(self, lvl: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lvl` | `int` | `—` | pos/kw |

### `out_err`

:returns: a tuple of the standard output and standard error

```python
tox.execute.Outcome.out_err(self) -> 'tuple[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str, str]`

### `tox.execute.api.Execute` methods

### `build_instance`

```python
tox.execute.api.Execute.build_instance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'ExecuteInstance'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `ExecuteInstance`

### `call`

```python
tox.execute.api.Execute.call(self, request: 'ExecuteRequest', show: 'bool', out_err: 'OutErr', env: 'ToxEnv') -> 'Iterator[ExecuteStatus]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show` | `bool` | `—` | pos/kw |
| `out_err` | `OutErr` | `—` | pos/kw |
| `env` | `ToxEnv` | `—` | pos/kw |

**Returns:** `Iterator[ExecuteStatus]`

### `register_conf`

```python
tox.execute.api.Execute.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.api.ExecuteOptions` methods

### `register_conf`

```python
tox.execute.api.ExecuteOptions.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.api.ExecuteStatus` methods

### `interrupt`

```python
tox.execute.api.ExecuteStatus.interrupt(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_out_err`

```python
tox.execute.api.ExecuteStatus.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `wait`

```python
tox.execute.api.ExecuteStatus.wait(self, timeout: 'float | None' = None) -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timeout` | `float \| None` | `None` | pos/kw |

**Returns:** `int | None`

### `write_stdin`

```python
tox.execute.api.ExecuteStatus.write_stdin(self, content: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |

### `tox.execute.api.Outcome` methods

### `assert_failure`

Assert that the execution failed.

```python
tox.execute.api.Outcome.assert_failure(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `assert_success`

Assert that the execution succeeded.

```python
tox.execute.api.Outcome.assert_success(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `log_run_done`

Log that the run was done.

:param lvl: the level on what to log as interpreted by :func:`logging.log`

```python
tox.execute.api.Outcome.log_run_done(self, lvl: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lvl` | `int` | `—` | pos/kw |

### `out_err`

:returns: a tuple of the standard output and standard error

```python
tox.execute.api.Outcome.out_err(self) -> 'tuple[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str, str]`

### `tox.execute.api.SyncWrite` methods

### `colored`

```python
tox.execute.api.SyncWrite.colored(self) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[None]`

### `handler`

A callback called whenever content is written.

```python
tox.execute.api.SyncWrite.handler(self, content: 'bytes') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `bytes` | `—` | pos/kw |

**Returns:** `int`

### `tox.execute.local_sub_process.Execute` methods

### `build_instance`

```python
tox.execute.local_sub_process.Execute.build_instance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'ExecuteInstance'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `ExecuteInstance`

### `call`

```python
tox.execute.local_sub_process.Execute.call(self, request: 'ExecuteRequest', show: 'bool', out_err: 'OutErr', env: 'ToxEnv') -> 'Iterator[ExecuteStatus]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show` | `bool` | `—` | pos/kw |
| `out_err` | `OutErr` | `—` | pos/kw |
| `env` | `ToxEnv` | `—` | pos/kw |

**Returns:** `Iterator[ExecuteStatus]`

### `register_conf`

```python
tox.execute.local_sub_process.Execute.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.local_sub_process.ExecuteOptions` methods

### `register_conf`

```python
tox.execute.local_sub_process.ExecuteOptions.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.local_sub_process.ExecuteStatus` methods

### `interrupt`

```python
tox.execute.local_sub_process.ExecuteStatus.interrupt(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_out_err`

```python
tox.execute.local_sub_process.ExecuteStatus.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `wait`

```python
tox.execute.local_sub_process.ExecuteStatus.wait(self, timeout: 'float | None' = None) -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timeout` | `float \| None` | `None` | pos/kw |

**Returns:** `int | None`

### `write_stdin`

```python
tox.execute.local_sub_process.ExecuteStatus.write_stdin(self, content: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |

### `tox.execute.local_sub_process.LocalSubProcessExecuteInstance` methods

### `get_stream_file_no`

```python
tox.execute.local_sub_process.LocalSubProcessExecuteInstance.get_stream_file_no(key: 'str') -> 'Generator[int, Popen[bytes], None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `Generator[int, Popen[bytes], None]`

### `set_out_err`

```python
tox.execute.local_sub_process.LocalSubProcessExecuteInstance.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `tox.execute.local_sub_process.LocalSubProcessExecutor` methods

### `build_instance`

```python
tox.execute.local_sub_process.LocalSubProcessExecutor.build_instance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'ExecuteInstance'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `ExecuteInstance`

### `call`

```python
tox.execute.local_sub_process.LocalSubProcessExecutor.call(self, request: 'ExecuteRequest', show: 'bool', out_err: 'OutErr', env: 'ToxEnv') -> 'Iterator[ExecuteStatus]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show` | `bool` | `—` | pos/kw |
| `out_err` | `OutErr` | `—` | pos/kw |
| `env` | `ToxEnv` | `—` | pos/kw |

**Returns:** `Iterator[ExecuteStatus]`

### `register_conf`

```python
tox.execute.local_sub_process.LocalSubProcessExecutor.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.local_sub_process.LocalSubprocessExecuteFailedStatus` methods

### `interrupt`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteFailedStatus.interrupt(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_out_err`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteFailedStatus.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `wait`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteFailedStatus.wait(self, timeout: 'float | None' = None) -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timeout` | `float \| None` | `None` | pos/kw |

**Returns:** `int | None`

### `write_stdin`

Cannot write.

```python
tox.execute.local_sub_process.LocalSubprocessExecuteFailedStatus.write_stdin(self, content: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |

### `tox.execute.local_sub_process.LocalSubprocessExecuteStatus` methods

### `interrupt`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteStatus.interrupt(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_out_err`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteStatus.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `wait`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteStatus.wait(self, timeout: 'float | None' = None) -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timeout` | `float \| None` | `None` | pos/kw |

**Returns:** `int | None`

### `write_stdin`

```python
tox.execute.local_sub_process.LocalSubprocessExecuteStatus.write_stdin(self, content: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |

### `tox.execute.pep517_backend.Execute` methods

### `build_instance`

```python
tox.execute.pep517_backend.Execute.build_instance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'ExecuteInstance'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `ExecuteInstance`

### `call`

```python
tox.execute.pep517_backend.Execute.call(self, request: 'ExecuteRequest', show: 'bool', out_err: 'OutErr', env: 'ToxEnv') -> 'Iterator[ExecuteStatus]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show` | `bool` | `—` | pos/kw |
| `out_err` | `OutErr` | `—` | pos/kw |
| `env` | `ToxEnv` | `—` | pos/kw |

**Returns:** `Iterator[ExecuteStatus]`

### `register_conf`

```python
tox.execute.pep517_backend.Execute.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.pep517_backend.ExecuteOptions` methods

### `register_conf`

```python
tox.execute.pep517_backend.ExecuteOptions.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |

### `tox.execute.pep517_backend.ExecuteStatus` methods

### `interrupt`

```python
tox.execute.pep517_backend.ExecuteStatus.interrupt(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_out_err`

```python
tox.execute.pep517_backend.ExecuteStatus.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `wait`

```python
tox.execute.pep517_backend.ExecuteStatus.wait(self, timeout: 'float | None' = None) -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timeout` | `float \| None` | `None` | pos/kw |

**Returns:** `int | None`

### `write_stdin`

```python
tox.execute.pep517_backend.ExecuteStatus.write_stdin(self, content: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |

### `tox.execute.pep517_backend.LocalSubProcessExecuteInstance` methods

### `get_stream_file_no`

```python
tox.execute.pep517_backend.LocalSubProcessExecuteInstance.get_stream_file_no(key: 'str') -> 'Generator[int, Popen[bytes], None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `Generator[int, Popen[bytes], None]`

### `set_out_err`

```python
tox.execute.pep517_backend.LocalSubProcessExecuteInstance.set_out_err(self, out: 'SyncWrite', err: 'SyncWrite') -> 'tuple[SyncWrite, SyncWrite]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `tuple[SyncWrite, SyncWrite]`

### `tox.execute.pep517_backend.LocalSubProcessPep517Executor` methods

### `build_instance`

```python
tox.execute.pep517_backend.LocalSubProcessPep517Executor.build_instance(self, request: 'ExecuteRequest', options: 'ExecuteOptions', out: 'SyncWrite', err: 'SyncWrite') -> 'ExecuteInstance'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |
| `out` | `SyncWrite` | `—` | pos/kw |
| `err` | `SyncWrite` | `—` | pos/kw |

**Returns:** `ExecuteInstance`

### `call`

```python
tox.execute.pep517_backend.LocalSubProcessPep517Executor.call(self, request: 'ExecuteRequest', show: 'bool', out_err: 'OutErr', env: 'ToxEnv') -> 'Iterator[ExecuteStatus]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `ExecuteRequest` | `—` | pos/kw |
| `show` | `bool` | `—` | pos/kw |
| `out_err` | `OutErr` | `—` | pos/kw |
| `env` | `ToxEnv` | `—` | pos/kw |

**Returns:** `Iterator[ExecuteStatus]`

### `close`

```python
tox.execute.pep517_backend.LocalSubProcessPep517Executor.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `local_execute`

```python
tox.execute.pep517_backend.LocalSubProcessPep517Executor.local_execute(self, options: 'ExecuteOptions') -> 'tuple[LocalSubProcessExecuteInstance, ExecuteStatus]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `options` | `ExecuteOptions` | `—` | pos/kw |

**Returns:** `tuple[LocalSubProcessExecuteInstance, ExecuteStatus]`

### `register_conf`

```python
tox.execute.pep517_backend.LocalSubProcessPep517Executor.register_conf(env: 'ToxEnv') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `ToxEnv` | `—` | pos/kw |


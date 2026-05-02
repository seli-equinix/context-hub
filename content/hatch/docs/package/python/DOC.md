---
name: package
description: "Hatch Python project manager for environments, builds, publishing, and versioning"
metadata:
  languages: "python"
  versions: "1.16.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "hatch,python,packaging,pyproject,build,publish,virtualenv,toml,Version-Sensitive,AppEnvVars,Application,abort,confirm,display,display_critical,display_debug,display_error,display_header,display_info,display_markdown,display_mini_header,display_pair,display_success,display_syntax,display_table,display_waiting,display_warning,ensure_environment_plugin_dependencies,ensure_plugin_dependencies,execute_context,get_env_directory,get_environment,get_python_manager,initialize_styles,output,prepare_environment,prompt,run_shell_commands,runner_context,status_if,style_debug,ConfigEnvVars,Path,absolute,as_cwd,as_posix,as_uri,chmod,cwd,ensure_dir_exists,ensure_parent_dir_exists,exists,expand,expanduser,from_uri,full_match,glob,group,hardlink_to,home,is_absolute,is_block_device,is_char_device,is_dir,is_fifo,is_file,is_junction,is_mount,is_relative_to,is_reserved,is_socket,is_symlink,iterdir,Project,canonicalize_name,ensure_cwd,expand_environments,find_project_root,from_config,get_dependencies,initialize,managed_environment,prepare_build_environment,save_config,set_app,set_path,main,running_in_ci,ConfigFile,get_default_location,load,read,read_scrubbed,restore,save,update,ExecutionContext,add_shell_command,Platform,capture_process,check_command,check_command_output,exit_with_code,exit_with_command,format_for_subprocess,populate_default_popen_kwargs,run_command,stream_process_output,RootConfig,parse_fields,raise_error,Terminal"
---

# hatch — package

## Install

```bash
pip install hatch
```

## Imports

```python
import hatch
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `AppEnvVars` | Class |  |
| `Application` | Class |  |
| `abort` | Method |  |
| `confirm` | Method |  |
| `display` | Method |  |
| `display_critical` | Method |  |
| `display_debug` | Method |  |
| `display_error` | Method |  |
| `display_header` | Method |  |
| `display_info` | Method |  |
| `display_markdown` | Method |  |
| `display_mini_header` | Method |  |
| `display_pair` | Method |  |
| `display_success` | Method |  |
| `display_syntax` | Method |  |
| `display_table` | Method |  |
| `display_waiting` | Method |  |
| `display_warning` | Method |  |
| `ensure_environment_plugin_dependencies` | Method |  |
| `ensure_plugin_dependencies` | Method |  |
| `execute_context` | Method |  |
| `get_env_directory` | Method |  |
| `get_environment` | Method |  |
| `get_python_manager` | Method |  |
| `initialize_styles` | Method |  |
| `output` | Method |  |
| `prepare_environment` | Method |  |
| `prompt` | Method |  |
| `run_shell_commands` | Method |  |
| `runner_context` | Method |  |
| `status_if` | Method |  |
| `style_debug` | Method |  |
| `ConfigEnvVars` | Class |  |
| `Path` | Class | Path subclass for non-Windows systems.  On a POSIX system, instantiating a Path… |
| `absolute` | Method | Return an absolute version of this path No normalization or symlink resolution… |
| `as_cwd` | Method |  |
| `as_posix` | Method | Return the string representation of the path with forward (/) slashes. |
| `as_uri` | Method | Return the path as a URI. |
| `chmod` | Method | Change the permissions of the path, like os.chmod(). |
| `cwd` | Method | Return a new path pointing to the current working directory. |
| `ensure_dir_exists` | Method |  |
| `ensure_parent_dir_exists` | Method |  |
| `exists` | Method | Whether this path exists.  This method normally follows symlinks; to check whet… |
| `expand` | Method |  |
| `expanduser` | Method | Return a new path with expanded ~ and ~user constructs (as returned by os.path.… |
| `from_uri` | Method | Return a new path from the given 'file' URI. |
| `full_match` | Method | Return True if this path matches the given glob-style pattern. The pattern is m… |
| `glob` | Method | Iterate over this subtree and yield all existing files (of any kind, including… |
| `group` | Method | Return the group name of the file gid. |
| `hardlink_to` | Method | Make this path a hard link pointing to the same file as *target*.  Note the ord… |
| `home` | Method | Return a new path pointing to expanduser('~'). |
| `is_absolute` | Method | True if the path is absolute (has both a root and, if applicable, a drive). |
| `is_block_device` | Method | Whether this path is a block device. |
| `is_char_device` | Method | Whether this path is a character device. |
| `is_dir` | Method | Whether this path is a directory. |
| `is_fifo` | Method | Whether this path is a FIFO. |
| `is_file` | Method | Whether this path is a regular file (also True for symlinks pointing to regular… |
| `is_junction` | Method | Whether this path is a junction. |
| `is_mount` | Method | Check if this path is a mount point |
| `is_relative_to` | Method | Return True if the path is relative to another path or False. |
| `is_reserved` | Method | Return True if the path contains one of the special names reserved by the syste… |
| `is_socket` | Method | Whether this path is a socket. |
| `is_symlink` | Method | Whether this path is a symbolic link. |
| `iterdir` | Method | Yield path objects of the directory contents.  The children are yielded in arbi… |
| `Project` | Class |  |
| `canonicalize_name` | Method |  |
| `ensure_cwd` | Method |  |
| `expand_environments` | Method |  |
| `find_project_root` | Method |  |
| `from_config` | Method |  |
| `get_dependencies` | Method |  |
| `get_environment` | Method |  |
| `initialize` | Method |  |
| `managed_environment` | Method | Context manager that removes environment on error unless keep_env is True. |
| `prepare_build_environment` | Method |  |
| `prepare_environment` | Method |  |
| `save_config` | Method |  |
| `set_app` | Method |  |
| `set_path` | Method |  |
| `main` | Function |  |
| `running_in_ci` | Function |  |
| `Application` | Class |  |
| `abort` | Method |  |
| `confirm` | Method |  |
| `display` | Method |  |
| `display_critical` | Method |  |
| `display_debug` | Method |  |
| `display_error` | Method |  |
| `display_header` | Method |  |
| `display_info` | Method |  |
| `display_markdown` | Method |  |
| `display_mini_header` | Method |  |
| `display_pair` | Method |  |
| `display_success` | Method |  |
| `display_syntax` | Method |  |
| `display_table` | Method |  |
| `display_waiting` | Method |  |
| `display_warning` | Method |  |
| `ensure_environment_plugin_dependencies` | Method |  |
| `ensure_plugin_dependencies` | Method |  |
| `execute_context` | Method |  |
| `get_env_directory` | Method |  |
| `get_environment` | Method |  |
| `get_python_manager` | Method |  |
| `initialize_styles` | Method |  |
| `output` | Method |  |
| `prepare_environment` | Method |  |
| `prompt` | Method |  |
| `run_shell_commands` | Method |  |
| `runner_context` | Method |  |
| `status_if` | Method |  |
| `style_debug` | Method |  |
| `ConfigFile` | Class |  |
| `get_default_location` | Method |  |
| `load` | Method |  |
| `read` | Method |  |
| `read_scrubbed` | Method |  |
| `restore` | Method |  |
| `save` | Method |  |
| `update` | Method |  |
| `ExecutionContext` | Class |  |
| `add_shell_command` | Method |  |
| `Path` | Class | Path subclass for non-Windows systems.  On a POSIX system, instantiating a Path… |
| `absolute` | Method | Return an absolute version of this path No normalization or symlink resolution… |
| `as_cwd` | Method |  |
| `as_posix` | Method | Return the string representation of the path with forward (/) slashes. |
| `as_uri` | Method | Return the path as a URI. |
| `chmod` | Method | Change the permissions of the path, like os.chmod(). |
| `cwd` | Method | Return a new path pointing to the current working directory. |
| `ensure_dir_exists` | Method |  |
| `ensure_parent_dir_exists` | Method |  |
| `exists` | Method | Whether this path exists.  This method normally follows symlinks; to check whet… |
| `expand` | Method |  |
| `expanduser` | Method | Return a new path with expanded ~ and ~user constructs (as returned by os.path.… |
| `from_uri` | Method | Return a new path from the given 'file' URI. |
| `full_match` | Method | Return True if this path matches the given glob-style pattern. The pattern is m… |
| `glob` | Method | Iterate over this subtree and yield all existing files (of any kind, including… |
| `group` | Method | Return the group name of the file gid. |
| `hardlink_to` | Method | Make this path a hard link pointing to the same file as *target*.  Note the ord… |
| `home` | Method | Return a new path pointing to expanduser('~'). |
| `is_absolute` | Method | True if the path is absolute (has both a root and, if applicable, a drive). |
| `is_block_device` | Method | Whether this path is a block device. |
| `is_char_device` | Method | Whether this path is a character device. |
| `is_dir` | Method | Whether this path is a directory. |
| `is_fifo` | Method | Whether this path is a FIFO. |
| `is_file` | Method | Whether this path is a regular file (also True for symlinks pointing to regular… |
| `is_junction` | Method | Whether this path is a junction. |
| `is_mount` | Method | Check if this path is a mount point |
| `is_relative_to` | Method | Return True if the path is relative to another path or False. |
| `is_reserved` | Method | Return True if the path contains one of the special names reserved by the syste… |
| `is_socket` | Method | Whether this path is a socket. |
| `is_symlink` | Method | Whether this path is a symbolic link. |
| `iterdir` | Method | Yield path objects of the directory contents.  The children are yielded in arbi… |
| `Platform` | Class |  |
| `capture_process` | Method | Equivalent to the standard library's [subprocess.Popen](https://docs.python.org… |
| `check_command` | Method | Equivalent to [run_command](utilities.md#hatch.utils.platform.Platform.run_comm… |
| `check_command_output` | Method | Equivalent to the output from the process returned by [capture_process](utiliti… |
| `exit_with_code` | Method |  |
| `exit_with_command` | Method | Run the given command and exit with its exit code. On non-Windows systems, this… |
| `format_for_subprocess` | Method | Format the given command in a cross-platform manner for immediate consumption b… |
| `populate_default_popen_kwargs` | Method |  |
| `run_command` | Method | Equivalent to the standard library's [subprocess.run](https://docs.python.org/3… |
| `stream_process_output` | Method |  |
| `Project` | Class |  |
| `canonicalize_name` | Method |  |
| `ensure_cwd` | Method |  |
| `expand_environments` | Method |  |
| `find_project_root` | Method |  |
| `from_config` | Method |  |
| `get_dependencies` | Method |  |
| `get_environment` | Method |  |
| `initialize` | Method |  |
| `managed_environment` | Method | Context manager that removes environment on error unless keep_env is True. |
| `prepare_build_environment` | Method |  |
| `prepare_environment` | Method |  |
| `save_config` | Method |  |
| `set_app` | Method |  |
| `set_path` | Method |  |
| `RootConfig` | Class |  |
| `parse_fields` | Method |  |
| `raise_error` | Method |  |
| `Terminal` | Class |  |
| `confirm` | Method |  |
| `display` | Method |  |
| `display_critical` | Method |  |
| `display_debug` | Method |  |
| `display_error` | Method |  |
| `display_header` | Method |  |
| `display_info` | Method |  |
| `display_markdown` | Method |  |
| `display_mini_header` | Method |  |
| `display_pair` | Method |  |
| `display_success` | Method |  |
| `display_syntax` | Method |  |
| `display_table` | Method |  |
| `display_waiting` | Method |  |
| `display_warning` | Method |  |
| `initialize_styles` | Method |  |
| `output` | Method |  |
| `prompt` | Method |  |

## Classes

### `AppEnvVars`

```python
hatch.cli.AppEnvVars(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Application`

```python
hatch.cli.Application(self, exit_func, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exit_func` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigEnvVars`

```python
hatch.cli.ConfigEnvVars(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Path`

Path subclass for non-Windows systems.

On a POSIX system, instantiating a Path should return this object.

```python
hatch.cli.Path(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Project`

```python
hatch.cli.Project(self, path: 'Path', *, name: 'str | None' = None, config=None, locate: 'bool' = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `name` | `str \| None` | `None` | kw |
| `config` | `—` | `None` | kw |
| `locate` | `bool` | `True` | kw |

### `Application`

```python
hatch.cli.application.Application(self, exit_func, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exit_func` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigFile`

```python
hatch.cli.application.ConfigFile(self, path: 'Path | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| None` | `None` | pos/kw |

### `ExecutionContext`

```python
hatch.cli.application.ExecutionContext(self, environment: 'EnvironmentInterface', *, shell_commands: 'list[str] | None' = None, env_vars: 'dict[str, str] | None' = None, force_continue: 'bool' = False, show_code_on_error: 'bool' = False, hide_commands: 'bool' = False, source: 'str' = 'cmd') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `shell_commands` | `list[str] \| None` | `None` | kw |
| `env_vars` | `dict[str, str] \| None` | `None` | kw |
| `force_continue` | `bool` | `False` | kw |
| `show_code_on_error` | `bool` | `False` | kw |
| `hide_commands` | `bool` | `False` | kw |
| `source` | `str` | `'cmd'` | kw |

### `Path`

Path subclass for non-Windows systems.

On a POSIX system, instantiating a Path should return this object.

```python
hatch.cli.application.Path(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Platform`

```python
hatch.cli.application.Platform(self, display_func: 'Callable' = <built-in function print>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `display_func` | `Callable` | `<built-in function print>` | pos/kw |

### `Project`

```python
hatch.cli.application.Project(self, path: 'Path', *, name: 'str | None' = None, config=None, locate: 'bool' = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `name` | `str \| None` | `None` | kw |
| `config` | `—` | `None` | kw |
| `locate` | `bool` | `True` | kw |

### `RootConfig`

```python
hatch.cli.application.RootConfig(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Terminal`

```python
hatch.cli.application.Terminal(self, *, verbosity: 'int', enable_color: 'bool | None', interactive: 'bool | None')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `verbosity` | `int` | `—` | kw |
| `enable_color` | `bool \| None` | `—` | kw |
| `interactive` | `bool \| None` | `—` | kw |

## Functions

### `main`

```python
hatch.cli.main()
```

### `running_in_ci`

```python
hatch.cli.running_in_ci() -> bool
```

**Returns:** `<class 'bool'>`

## Methods

### `hatch.cli.Application` methods

### `abort`

```python
hatch.cli.Application.abort(self, text='', code=1, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `code` | `—` | `1` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `confirm`

```python
hatch.cli.Application.confirm(text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display`

```python
hatch.cli.Application.display(self, text='', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_critical`

```python
hatch.cli.Application.display_critical(self, text='', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_debug`

```python
hatch.cli.Application.display_debug(self, text='', level=1, *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `level` | `—` | `1` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_error`

```python
hatch.cli.Application.display_error(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_header`

```python
hatch.cli.Application.display_header(self, title='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `—` | `''` | pos/kw |

### `display_info`

```python
hatch.cli.Application.display_info(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_markdown`

```python
hatch.cli.Application.display_markdown(self, text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_mini_header`

```python
hatch.cli.Application.display_mini_header(self, text, *, stderr=False, indent=None, link=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `stderr` | `—` | `False` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |

### `display_pair`

```python
hatch.cli.Application.display_pair(self, key, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `display_success`

```python
hatch.cli.Application.display_success(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_syntax`

```python
hatch.cli.Application.display_syntax(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `display_table`

```python
hatch.cli.Application.display_table(self, title, columns, *, show_lines=False, column_options=None, force_ascii=False, num_rows=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `—` | `—` | pos/kw |
| `columns` | `—` | `—` | pos/kw |
| `show_lines` | `—` | `False` | kw |
| `column_options` | `—` | `None` | kw |
| `force_ascii` | `—` | `False` | kw |
| `num_rows` | `—` | `0` | kw |

### `display_waiting`

```python
hatch.cli.Application.display_waiting(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_warning`

```python
hatch.cli.Application.display_warning(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ensure_environment_plugin_dependencies`

```python
hatch.cli.Application.ensure_environment_plugin_dependencies(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_plugin_dependencies`

```python
hatch.cli.Application.ensure_plugin_dependencies(self, dependencies: 'list[Dependency]', *, wait_message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dependencies` | `list[Dependency]` | `—` | pos/kw |
| `wait_message` | `str` | `—` | kw |

### `execute_context`

```python
hatch.cli.Application.execute_context(self, context: 'ExecutionContext') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `ExecutionContext` | `—` | pos/kw |

### `get_env_directory`

```python
hatch.cli.Application.get_env_directory(self, environment_type)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment_type` | `—` | `—` | pos/kw |

### `get_environment`

```python
hatch.cli.Application.get_environment(self, env_name: 'str | None' = None) -> 'EnvironmentInterface'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_name` | `str \| None` | `None` | pos/kw |

**Returns:** `EnvironmentInterface`

### `get_python_manager`

```python
hatch.cli.Application.get_python_manager(self, directory: 'str | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `directory` | `str \| None` | `None` | pos/kw |

### `initialize_styles`

```python
hatch.cli.Application.initialize_styles(self, styles: 'dict')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `styles` | `dict` | `—` | pos/kw |

### `output`

```python
hatch.cli.Application.output(self, *args, stderr=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `stderr` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `prepare_environment`

```python
hatch.cli.Application.prepare_environment(self, environment: 'EnvironmentInterface', *, keep_env: 'bool' = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `keep_env` | `bool` | `False` | kw |

### `prompt`

```python
hatch.cli.Application.prompt(text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `run_shell_commands`

```python
hatch.cli.Application.run_shell_commands(self, context: 'ExecutionContext') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `ExecutionContext` | `—` | pos/kw |

### `runner_context`

```python
hatch.cli.Application.runner_context(self, environments: 'list[str]', *, ignore_compat: 'bool' = False, display_header: 'bool' = False, keep_env: 'bool' = False) -> 'Generator[ExecutionContext, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environments` | `list[str]` | `—` | pos/kw |
| `ignore_compat` | `bool` | `False` | kw |
| `display_header` | `bool` | `False` | kw |
| `keep_env` | `bool` | `False` | kw |

**Returns:** `Generator[ExecutionContext, None, None]`

### `status_if`

```python
hatch.cli.Application.status_if(self, *args, condition: 'bool', **kwargs) -> 'TerminalStatus'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `condition` | `bool` | `—` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `TerminalStatus`

### `style_debug`

```python
hatch.cli.Application.style_debug(self, text: 'str') -> 'Text'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

**Returns:** `Text`

### `hatch.cli.Path` methods

### `absolute`

Return an absolute version of this path
No normalization or symlink resolution is performed.

Use resolve() to resolve symlinks and remove '..' segments.

```python
hatch.cli.Path.absolute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_cwd`

```python
hatch.cli.Path.as_cwd(self, *args: 'Any', **kwargs: 'Any') -> 'Generator[Path, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Generator[Path, None, None]`

### `as_posix`

Return the string representation of the path with forward (/)
slashes.

```python
hatch.cli.Path.as_posix(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_uri`

Return the path as a URI.

```python
hatch.cli.Path.as_uri(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `chmod`

Change the permissions of the path, like os.chmod().

```python
hatch.cli.Path.chmod(self, mode, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `cwd`

Return a new path pointing to the current working directory.

```python
hatch.cli.Path.cwd()
```

### `ensure_dir_exists`

```python
hatch.cli.Path.ensure_dir_exists(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_parent_dir_exists`

```python
hatch.cli.Path.ensure_parent_dir_exists(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `exists`

Whether this path exists.

This method normally follows symlinks; to check whether a symlink exists,
add the argument follow_symlinks=False.

```python
hatch.cli.Path.exists(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `expand`

```python
hatch.cli.Path.expand(self) -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Path`

### `expanduser`

Return a new path with expanded ~ and ~user constructs
(as returned by os.path.expanduser)

```python
hatch.cli.Path.expanduser(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_uri`

Return a new path from the given 'file' URI.

```python
hatch.cli.Path.from_uri(path: 'str') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

**Returns:** `Path`

### `full_match`

Return True if this path matches the given glob-style pattern. The
pattern is matched against the entire path.

```python
hatch.cli.Path.full_match(self, pattern, *, case_sensitive=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `—` | pos/kw |
| `case_sensitive` | `—` | `None` | kw |

### `glob`

Iterate over this subtree and yield all existing files (of any
kind, including directories) matching the given relative pattern.

```python
hatch.cli.Path.glob(self, pattern, *, case_sensitive=None, recurse_symlinks=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `—` | pos/kw |
| `case_sensitive` | `—` | `None` | kw |
| `recurse_symlinks` | `—` | `False` | kw |

### `group`

Return the group name of the file gid.

```python
hatch.cli.Path.group(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `hardlink_to`

Make this path a hard link pointing to the same file as *target*.

Note the order of arguments (self, target) is the reverse of os.link's.

```python
hatch.cli.Path.hardlink_to(self, target)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `target` | `—` | `—` | pos/kw |

### `home`

Return a new path pointing to expanduser('~').

```python
hatch.cli.Path.home()
```

### `is_absolute`

True if the path is absolute (has both a root and, if applicable,
a drive).

```python
hatch.cli.Path.is_absolute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_block_device`

Whether this path is a block device.

```python
hatch.cli.Path.is_block_device(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_char_device`

Whether this path is a character device.

```python
hatch.cli.Path.is_char_device(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_dir`

Whether this path is a directory.

```python
hatch.cli.Path.is_dir(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `is_fifo`

Whether this path is a FIFO.

```python
hatch.cli.Path.is_fifo(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_file`

Whether this path is a regular file (also True for symlinks pointing
to regular files).

```python
hatch.cli.Path.is_file(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `is_junction`

Whether this path is a junction.

```python
hatch.cli.Path.is_junction(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_mount`

Check if this path is a mount point

```python
hatch.cli.Path.is_mount(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_relative_to`

Return True if the path is relative to another path or False.

```python
hatch.cli.Path.is_relative_to(self, other, /, *_deprecated)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `—` | pos |
| `_deprecated` | `—` | `—` | *args |

### `is_reserved`

Return True if the path contains one of the special names reserved
by the system, if any.

```python
hatch.cli.Path.is_reserved(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_socket`

Whether this path is a socket.

```python
hatch.cli.Path.is_socket(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_symlink`

Whether this path is a symbolic link.

```python
hatch.cli.Path.is_symlink(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `iterdir`

Yield path objects of the directory contents.

The children are yielded in arbitrary order, and the
special entries '.' and '..' are not included.

```python
hatch.cli.Path.iterdir(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `hatch.cli.Project` methods

### `canonicalize_name`

```python
hatch.cli.Project.canonicalize_name(name: 'str', *, strict=True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `strict` | `—` | `True` | kw |

**Returns:** `str`

### `ensure_cwd`

```python
hatch.cli.Project.ensure_cwd(self) -> 'Generator[Path, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[Path, None, None]`

### `expand_environments`

```python
hatch.cli.Project.expand_environments(self, env_name: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_name` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

### `find_project_root`

```python
hatch.cli.Project.find_project_root(self) -> 'Path | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Path | None`

### `from_config`

```python
hatch.cli.Project.from_config(config: 'RootConfig', project: 'str') -> 'Project | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `RootConfig` | `—` | pos/kw |
| `project` | `str` | `—` | pos/kw |

**Returns:** `Project | None`

### `get_dependencies`

```python
hatch.cli.Project.get_dependencies(self) -> 'tuple[list[str], dict[str, list[str]]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[list[str], dict[str, list[str]]]`

### `get_environment`

```python
hatch.cli.Project.get_environment(self, env_name: 'str | None' = None) -> 'EnvironmentInterface'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_name` | `str \| None` | `None` | pos/kw |

**Returns:** `EnvironmentInterface`

### `initialize`

```python
hatch.cli.Project.initialize(project_file_path, template_config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project_file_path` | `—` | `—` | pos/kw |
| `template_config` | `—` | `—` | pos/kw |

### `managed_environment`

Context manager that removes environment on error unless keep_env is True.

```python
hatch.cli.Project.managed_environment(environment: 'EnvironmentInterface', *, keep_env: 'bool' = False) -> 'Generator[EnvironmentInterface, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `keep_env` | `bool` | `False` | kw |

**Returns:** `Generator[EnvironmentInterface, None, None]`

### `prepare_build_environment`

```python
hatch.cli.Project.prepare_build_environment(self, *, targets: 'list[str] | None' = None, keep_env: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `targets` | `list[str] \| None` | `None` | kw |
| `keep_env` | `bool` | `False` | kw |

### `prepare_environment`

```python
hatch.cli.Project.prepare_environment(self, environment: 'EnvironmentInterface', *, keep_env: 'bool')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `keep_env` | `bool` | `—` | kw |

### `save_config`

```python
hatch.cli.Project.save_config(self, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `set_app`

```python
hatch.cli.Project.set_app(self, app: 'Application') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `app` | `Application` | `—` | pos/kw |

### `set_path`

```python
hatch.cli.Project.set_path(self, path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `Path` | `—` | pos/kw |

### `hatch.cli.application.Application` methods

### `abort`

```python
hatch.cli.application.Application.abort(self, text='', code=1, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `code` | `—` | `1` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `confirm`

```python
hatch.cli.application.Application.confirm(text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display`

```python
hatch.cli.application.Application.display(self, text='', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_critical`

```python
hatch.cli.application.Application.display_critical(self, text='', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_debug`

```python
hatch.cli.application.Application.display_debug(self, text='', level=1, *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `level` | `—` | `1` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_error`

```python
hatch.cli.application.Application.display_error(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_header`

```python
hatch.cli.application.Application.display_header(self, title='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `—` | `''` | pos/kw |

### `display_info`

```python
hatch.cli.application.Application.display_info(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_markdown`

```python
hatch.cli.application.Application.display_markdown(self, text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_mini_header`

```python
hatch.cli.application.Application.display_mini_header(self, text, *, stderr=False, indent=None, link=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `stderr` | `—` | `False` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |

### `display_pair`

```python
hatch.cli.application.Application.display_pair(self, key, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `display_success`

```python
hatch.cli.application.Application.display_success(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_syntax`

```python
hatch.cli.application.Application.display_syntax(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `display_table`

```python
hatch.cli.application.Application.display_table(self, title, columns, *, show_lines=False, column_options=None, force_ascii=False, num_rows=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `—` | `—` | pos/kw |
| `columns` | `—` | `—` | pos/kw |
| `show_lines` | `—` | `False` | kw |
| `column_options` | `—` | `None` | kw |
| `force_ascii` | `—` | `False` | kw |
| `num_rows` | `—` | `0` | kw |

### `display_waiting`

```python
hatch.cli.application.Application.display_waiting(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_warning`

```python
hatch.cli.application.Application.display_warning(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ensure_environment_plugin_dependencies`

```python
hatch.cli.application.Application.ensure_environment_plugin_dependencies(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_plugin_dependencies`

```python
hatch.cli.application.Application.ensure_plugin_dependencies(self, dependencies: 'list[Dependency]', *, wait_message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dependencies` | `list[Dependency]` | `—` | pos/kw |
| `wait_message` | `str` | `—` | kw |

### `execute_context`

```python
hatch.cli.application.Application.execute_context(self, context: 'ExecutionContext') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `ExecutionContext` | `—` | pos/kw |

### `get_env_directory`

```python
hatch.cli.application.Application.get_env_directory(self, environment_type)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment_type` | `—` | `—` | pos/kw |

### `get_environment`

```python
hatch.cli.application.Application.get_environment(self, env_name: 'str | None' = None) -> 'EnvironmentInterface'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_name` | `str \| None` | `None` | pos/kw |

**Returns:** `EnvironmentInterface`

### `get_python_manager`

```python
hatch.cli.application.Application.get_python_manager(self, directory: 'str | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `directory` | `str \| None` | `None` | pos/kw |

### `initialize_styles`

```python
hatch.cli.application.Application.initialize_styles(self, styles: 'dict')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `styles` | `dict` | `—` | pos/kw |

### `output`

```python
hatch.cli.application.Application.output(self, *args, stderr=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `stderr` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `prepare_environment`

```python
hatch.cli.application.Application.prepare_environment(self, environment: 'EnvironmentInterface', *, keep_env: 'bool' = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `keep_env` | `bool` | `False` | kw |

### `prompt`

```python
hatch.cli.application.Application.prompt(text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `run_shell_commands`

```python
hatch.cli.application.Application.run_shell_commands(self, context: 'ExecutionContext') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `ExecutionContext` | `—` | pos/kw |

### `runner_context`

```python
hatch.cli.application.Application.runner_context(self, environments: 'list[str]', *, ignore_compat: 'bool' = False, display_header: 'bool' = False, keep_env: 'bool' = False) -> 'Generator[ExecutionContext, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environments` | `list[str]` | `—` | pos/kw |
| `ignore_compat` | `bool` | `False` | kw |
| `display_header` | `bool` | `False` | kw |
| `keep_env` | `bool` | `False` | kw |

**Returns:** `Generator[ExecutionContext, None, None]`

### `status_if`

```python
hatch.cli.application.Application.status_if(self, *args, condition: 'bool', **kwargs) -> 'TerminalStatus'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `condition` | `bool` | `—` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `TerminalStatus`

### `style_debug`

```python
hatch.cli.application.Application.style_debug(self, text: 'str') -> 'Text'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

**Returns:** `Text`

### `hatch.cli.application.ConfigFile` methods

### `get_default_location`

```python
hatch.cli.application.ConfigFile.get_default_location() -> 'Path'
```

**Returns:** `Path`

### `load`

```python
hatch.cli.application.ConfigFile.load(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `read`

```python
hatch.cli.application.ConfigFile.read(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `read_scrubbed`

```python
hatch.cli.application.ConfigFile.read_scrubbed(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `restore`

```python
hatch.cli.application.ConfigFile.restore(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `save`

```python
hatch.cli.application.ConfigFile.save(self, content=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `—` | `None` | pos/kw |

### `update`

```python
hatch.cli.application.ConfigFile.update(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `hatch.cli.application.ExecutionContext` methods

### `add_shell_command`

```python
hatch.cli.application.ExecutionContext.add_shell_command(self, command: 'str | list[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| list[str]` | `—` | pos/kw |

### `hatch.cli.application.Path` methods

### `absolute`

Return an absolute version of this path
No normalization or symlink resolution is performed.

Use resolve() to resolve symlinks and remove '..' segments.

```python
hatch.cli.application.Path.absolute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_cwd`

```python
hatch.cli.application.Path.as_cwd(self, *args: 'Any', **kwargs: 'Any') -> 'Generator[Path, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Generator[Path, None, None]`

### `as_posix`

Return the string representation of the path with forward (/)
slashes.

```python
hatch.cli.application.Path.as_posix(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_uri`

Return the path as a URI.

```python
hatch.cli.application.Path.as_uri(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `chmod`

Change the permissions of the path, like os.chmod().

```python
hatch.cli.application.Path.chmod(self, mode, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `cwd`

Return a new path pointing to the current working directory.

```python
hatch.cli.application.Path.cwd()
```

### `ensure_dir_exists`

```python
hatch.cli.application.Path.ensure_dir_exists(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_parent_dir_exists`

```python
hatch.cli.application.Path.ensure_parent_dir_exists(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `exists`

Whether this path exists.

This method normally follows symlinks; to check whether a symlink exists,
add the argument follow_symlinks=False.

```python
hatch.cli.application.Path.exists(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `expand`

```python
hatch.cli.application.Path.expand(self) -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Path`

### `expanduser`

Return a new path with expanded ~ and ~user constructs
(as returned by os.path.expanduser)

```python
hatch.cli.application.Path.expanduser(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_uri`

Return a new path from the given 'file' URI.

```python
hatch.cli.application.Path.from_uri(path: 'str') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

**Returns:** `Path`

### `full_match`

Return True if this path matches the given glob-style pattern. The
pattern is matched against the entire path.

```python
hatch.cli.application.Path.full_match(self, pattern, *, case_sensitive=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `—` | pos/kw |
| `case_sensitive` | `—` | `None` | kw |

### `glob`

Iterate over this subtree and yield all existing files (of any
kind, including directories) matching the given relative pattern.

```python
hatch.cli.application.Path.glob(self, pattern, *, case_sensitive=None, recurse_symlinks=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `—` | pos/kw |
| `case_sensitive` | `—` | `None` | kw |
| `recurse_symlinks` | `—` | `False` | kw |

### `group`

Return the group name of the file gid.

```python
hatch.cli.application.Path.group(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `hardlink_to`

Make this path a hard link pointing to the same file as *target*.

Note the order of arguments (self, target) is the reverse of os.link's.

```python
hatch.cli.application.Path.hardlink_to(self, target)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `target` | `—` | `—` | pos/kw |

### `home`

Return a new path pointing to expanduser('~').

```python
hatch.cli.application.Path.home()
```

### `is_absolute`

True if the path is absolute (has both a root and, if applicable,
a drive).

```python
hatch.cli.application.Path.is_absolute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_block_device`

Whether this path is a block device.

```python
hatch.cli.application.Path.is_block_device(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_char_device`

Whether this path is a character device.

```python
hatch.cli.application.Path.is_char_device(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_dir`

Whether this path is a directory.

```python
hatch.cli.application.Path.is_dir(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `is_fifo`

Whether this path is a FIFO.

```python
hatch.cli.application.Path.is_fifo(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_file`

Whether this path is a regular file (also True for symlinks pointing
to regular files).

```python
hatch.cli.application.Path.is_file(self, *, follow_symlinks=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `follow_symlinks` | `—` | `True` | kw |

### `is_junction`

Whether this path is a junction.

```python
hatch.cli.application.Path.is_junction(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_mount`

Check if this path is a mount point

```python
hatch.cli.application.Path.is_mount(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_relative_to`

Return True if the path is relative to another path or False.

```python
hatch.cli.application.Path.is_relative_to(self, other, /, *_deprecated)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `—` | pos |
| `_deprecated` | `—` | `—` | *args |

### `is_reserved`

Return True if the path contains one of the special names reserved
by the system, if any.

```python
hatch.cli.application.Path.is_reserved(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_socket`

Whether this path is a socket.

```python
hatch.cli.application.Path.is_socket(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_symlink`

Whether this path is a symbolic link.

```python
hatch.cli.application.Path.is_symlink(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `iterdir`

Yield path objects of the directory contents.

The children are yielded in arbitrary order, and the
special entries '.' and '..' are not included.

```python
hatch.cli.application.Path.iterdir(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `hatch.cli.application.Platform` methods

### `capture_process`

Equivalent to the standard library's
[subprocess.Popen](https://docs.python.org/3/library/subprocess.html#subprocess.Popen),
with all output captured by `stdout` and the command first being
[properly…

```python
hatch.cli.application.Platform.capture_process(self, command: 'str | list[str]', *, shell: 'bool' = False, **kwargs: 'Any') -> 'Popen'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| list[str]` | `—` | pos/kw |
| `shell` | `bool` | `False` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Popen`

### `check_command`

Equivalent to [run_command](utilities.md#hatch.utils.platform.Platform.run_command),
but non-zero exit codes will gracefully end program execution.

```python
hatch.cli.application.Platform.check_command(self, command: 'str | list[str]', *, shell: 'bool' = False, **kwargs: 'Any') -> 'CompletedProcess'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| list[str]` | `—` | pos/kw |
| `shell` | `bool` | `False` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `CompletedProcess`

### `check_command_output`

Equivalent to the output from the process returned by
[capture_process](utilities.md#hatch.utils.platform.Platform.capture_process),
but non-zero exit codes will gracefully end program execution.

```python
hatch.cli.application.Platform.check_command_output(self, command: 'str | list[str]', *, shell: 'bool' = False, **kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| list[str]` | `—` | pos/kw |
| `shell` | `bool` | `False` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `exit_with_code`

```python
hatch.cli.application.Platform.exit_with_code(code: 'str | int | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `str \| int \| None` | `—` | pos/kw |

### `exit_with_command`

Run the given command and exit with its exit code. On non-Windows systems, this uses the standard library's
[os.execvp](https://docs.python.org/3/library/os.html#os.execvp).

```python
hatch.cli.application.Platform.exit_with_command(self, command: 'list[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `list[str]` | `—` | pos/kw |

### `format_for_subprocess`

Format the given command in a cross-platform manner for immediate consumption by subprocess utilities.

```python
hatch.cli.application.Platform.format_for_subprocess(self, command: 'str | list[str]', *, shell: 'bool') -> 'str | list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| list[str]` | `—` | pos/kw |
| `shell` | `bool` | `—` | kw |

**Returns:** `str | list[str]`

### `populate_default_popen_kwargs`

```python
hatch.cli.application.Platform.populate_default_popen_kwargs(self, kwargs: 'dict[str, Any]', *, shell: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `dict[str, Any]` | `—` | pos/kw |
| `shell` | `bool` | `—` | kw |

### `run_command`

Equivalent to the standard library's
[subprocess.run](https://docs.python.org/3/library/subprocess.html#subprocess.run),
with the command first being
[properly formatted](utilities.md#hatch.utils.pla…

```python
hatch.cli.application.Platform.run_command(self, command: 'str | list[str]', *, shell: 'bool' = False, **kwargs: 'Any') -> 'CompletedProcess'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| list[str]` | `—` | pos/kw |
| `shell` | `bool` | `False` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `CompletedProcess`

### `stream_process_output`

```python
hatch.cli.application.Platform.stream_process_output(process: 'Popen') -> 'Iterable[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `process` | `Popen` | `—` | pos/kw |

**Returns:** `Iterable[str]`

### `hatch.cli.application.Project` methods

### `canonicalize_name`

```python
hatch.cli.application.Project.canonicalize_name(name: 'str', *, strict=True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `strict` | `—` | `True` | kw |

**Returns:** `str`

### `ensure_cwd`

```python
hatch.cli.application.Project.ensure_cwd(self) -> 'Generator[Path, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[Path, None, None]`

### `expand_environments`

```python
hatch.cli.application.Project.expand_environments(self, env_name: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_name` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

### `find_project_root`

```python
hatch.cli.application.Project.find_project_root(self) -> 'Path | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Path | None`

### `from_config`

```python
hatch.cli.application.Project.from_config(config: 'RootConfig', project: 'str') -> 'Project | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `RootConfig` | `—` | pos/kw |
| `project` | `str` | `—` | pos/kw |

**Returns:** `Project | None`

### `get_dependencies`

```python
hatch.cli.application.Project.get_dependencies(self) -> 'tuple[list[str], dict[str, list[str]]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[list[str], dict[str, list[str]]]`

### `get_environment`

```python
hatch.cli.application.Project.get_environment(self, env_name: 'str | None' = None) -> 'EnvironmentInterface'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env_name` | `str \| None` | `None` | pos/kw |

**Returns:** `EnvironmentInterface`

### `initialize`

```python
hatch.cli.application.Project.initialize(project_file_path, template_config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project_file_path` | `—` | `—` | pos/kw |
| `template_config` | `—` | `—` | pos/kw |

### `managed_environment`

Context manager that removes environment on error unless keep_env is True.

```python
hatch.cli.application.Project.managed_environment(environment: 'EnvironmentInterface', *, keep_env: 'bool' = False) -> 'Generator[EnvironmentInterface, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `keep_env` | `bool` | `False` | kw |

**Returns:** `Generator[EnvironmentInterface, None, None]`

### `prepare_build_environment`

```python
hatch.cli.application.Project.prepare_build_environment(self, *, targets: 'list[str] | None' = None, keep_env: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `targets` | `list[str] \| None` | `None` | kw |
| `keep_env` | `bool` | `False` | kw |

### `prepare_environment`

```python
hatch.cli.application.Project.prepare_environment(self, environment: 'EnvironmentInterface', *, keep_env: 'bool')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `EnvironmentInterface` | `—` | pos/kw |
| `keep_env` | `bool` | `—` | kw |

### `save_config`

```python
hatch.cli.application.Project.save_config(self, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `set_app`

```python
hatch.cli.application.Project.set_app(self, app: 'Application') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `app` | `Application` | `—` | pos/kw |

### `set_path`

```python
hatch.cli.application.Project.set_path(self, path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `Path` | `—` | pos/kw |

### `hatch.cli.application.RootConfig` methods

### `parse_fields`

```python
hatch.cli.application.RootConfig.parse_fields(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `raise_error`

```python
hatch.cli.application.RootConfig.raise_error(self, message, *, extra_steps=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `—` | `—` | pos/kw |
| `extra_steps` | `—` | `()` | kw |

### `hatch.cli.application.Terminal` methods

### `confirm`

```python
hatch.cli.application.Terminal.confirm(text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display`

```python
hatch.cli.application.Terminal.display(self, text='', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_critical`

```python
hatch.cli.application.Terminal.display_critical(self, text='', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_debug`

```python
hatch.cli.application.Terminal.display_debug(self, text='', level=1, *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `level` | `—` | `1` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_error`

```python
hatch.cli.application.Terminal.display_error(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_header`

```python
hatch.cli.application.Terminal.display_header(self, title='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `—` | `''` | pos/kw |

### `display_info`

```python
hatch.cli.application.Terminal.display_info(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_markdown`

```python
hatch.cli.application.Terminal.display_markdown(self, text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_mini_header`

```python
hatch.cli.application.Terminal.display_mini_header(self, text, *, stderr=False, indent=None, link=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `stderr` | `—` | `False` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |

### `display_pair`

```python
hatch.cli.application.Terminal.display_pair(self, key, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `display_success`

```python
hatch.cli.application.Terminal.display_success(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_syntax`

```python
hatch.cli.application.Terminal.display_syntax(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `display_table`

```python
hatch.cli.application.Terminal.display_table(self, title, columns, *, show_lines=False, column_options=None, force_ascii=False, num_rows=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `—` | `—` | pos/kw |
| `columns` | `—` | `—` | pos/kw |
| `show_lines` | `—` | `False` | kw |
| `column_options` | `—` | `None` | kw |
| `force_ascii` | `—` | `False` | kw |
| `num_rows` | `—` | `0` | kw |

### `display_waiting`

```python
hatch.cli.application.Terminal.display_waiting(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `display_warning`

```python
hatch.cli.application.Terminal.display_warning(self, text='', *, stderr=True, indent=None, link=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `stderr` | `—` | `True` | kw |
| `indent` | `—` | `None` | kw |
| `link` | `—` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `initialize_styles`

```python
hatch.cli.application.Terminal.initialize_styles(self, styles: 'dict')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `styles` | `dict` | `—` | pos/kw |

### `output`

```python
hatch.cli.application.Terminal.output(self, *args, stderr=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `stderr` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `prompt`

```python
hatch.cli.application.Terminal.prompt(text, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |


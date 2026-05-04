---
name: package
description: "JupyterLab package guide for Python projects using the JupyterLab 4.5.x application and extension workflow"
metadata:
  languages: "python"
  versions: "4.5.6"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "jupyterlab,python,jupyter,notebook,ide,extensions,Version-Sensitive,CheckForUpdate,CheckForUpdateABC,NeverCheckForUpdate,load_jupyter_server_extension,BrowserApp,add_traits,class_config_rst_doc,class_config_section,class_get_help,class_get_trait_help,class_own_trait_events,class_own_traits,class_print_help,class_trait_names,class_traits,clear_instance,close_handlers,current_activity,document_config_options,emit_alias_help,emit_description,emit_examples,emit_flag_help,emit_help,emit_help_epilogue,emit_options_help,emit_subcommands_help,exit,flatten_flags,generate_config_file,get_default_logging_config,get_extension_package,get_extension_point,has_trait,hold_trait_notifications,LabApp,LogErrorHandler,acquire,addFilter,close,createLock,emit,filter,flush,format,get_name,handle,handleError,release,removeFilter,setFormatter,setLevel,setStream,set_name,TestEnv,start,stop,get_app_dir,run_async_process,run_browser,run_browser_sync,run_test,run_test_async,AppOptions,notify_change,observe,on_trait_change,set_trait,setup_instance,trait_defaults,trait_events,trait_has_value,trait_metadata,trait_names,trait_values,traits,unobserve,unobserve_all,CoreConfig,add,clear_packages,remove,LockStatus,Process,get_log,terminate,wait,wait_async,ProgressProcess,Range,parse_range,test,WatchHelper,build,build_check,check_extension,clean,dedupe_yarn,disable_extension,enable_extension,ensure_app,ensure_core,ensure_dev,ensure_node_modules,get_allowed_levels,get_app_info,get_app_version,get_federated_extensions,get_latest_compatible_package_versions,get_package_url,get_page_config,get_static_page_config,get_user_settings_dir,get_workspaces_dir,gt,gte,install_extension,link_package,list2cmdline,list_extensions,lock_extension,lt,lte,make_semver,pjoin,read_package,uninstall_extension,unlink_package,unlock_extension,update_extension,watch,watch_dev,watch_packages,which,write_page_config,DebugLogFileMixin,debug_logging"
---

# jupyterlab — package

Server extension for JupyterLab.

## Install

```bash
pip install jupyterlab
```

## Imports

```python
import jupyterlab
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `CheckForUpdate` | Class | Default class to check for update.  Args:     version: Current JupyterLab versi… |
| `CheckForUpdateABC` | Class | Abstract class to check for update.  Args:     version: Current JupyterLab vers… |
| `NeverCheckForUpdate` | Class | Check update version that does nothing.  This is provided for administrators th… |
| `load_jupyter_server_extension` | Function |  |
| `BrowserApp` | Class | An app the launches JupyterLab and waits for it to start up, checking for JS co… |
| `add_traits` | Method | Dynamically add trait attributes to the HasTraits instance. |
| `class_config_rst_doc` | Method | Generate rST documentation for this class' config options.  Excludes traits def… |
| `class_config_section` | Method | Get the config section for this class.  Parameters ---------- classes : list, o… |
| `class_get_help` | Method | Get the help string for this class in ReST format.  If `inst` is given, its cur… |
| `class_get_trait_help` | Method | Get the helptext string for a single trait.  :param inst:     If given, its cur… |
| `class_own_trait_events` | Method | Get a dict of all event handlers defined on this class, not a parent.  Works li… |
| `class_own_traits` | Method | Get a dict of all the traitlets defined on this class, not a parent.  Works lik… |
| `class_print_help` | Method | Get the help string for a single trait and print it. |
| `class_trait_names` | Method | Get a list of all the names of this class' traits.  This method is just like th… |
| `class_traits` | Method | Get a ``dict`` of all the traits of this class.  The dictionary is keyed on the… |
| `clear_instance` | Method | unset _instance for this class and singleton parents. |
| `close_handlers` | Method |  |
| `current_activity` | Method | Return a list of activity happening in this extension. |
| `document_config_options` | Method | Generate rST format documentation for the config options this application  Retu… |
| `emit_alias_help` | Method | Yield the lines for alias part of the help. |
| `emit_description` | Method | Yield lines with the application description. |
| `emit_examples` | Method | Yield lines with the usage and examples.  This usage string goes at the end of… |
| `emit_flag_help` | Method | Yield the lines for the flag part of the help. |
| `emit_help` | Method | Yield the help-lines for each Configurable class in self.classes.  If classes=F… |
| `emit_help_epilogue` | Method | Yield the very bottom lines of the help message.  If classes=False (the default… |
| `emit_options_help` | Method | Yield the lines for the options part of the help. |
| `emit_subcommands_help` | Method | Yield the lines for the subcommand part of the help. |
| `exit` | Method |  |
| `flatten_flags` | Method | Flatten flags and aliases for loaders, so cl-args override as expected.  This p… |
| `generate_config_file` | Method | generate default config file from Configurables |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `CheckForUpdate`

Default class to check for update.

Args:
    version: Current JupyterLab version

Attributes:
    version - str: Current JupyterLab version
    logger - logging.Logger: Server logger

```python
jupyterlab.CheckForUpdate(self, version: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

### `CheckForUpdateABC`

Abstract class to check for update.

Args:
    version: Current JupyterLab version

Attributes:
    version - str: Current JupyterLab version
    logger - logging.Logger: Server logger

```python
jupyterlab.CheckForUpdateABC(self, version: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

### `NeverCheckForUpdate`

Check update version that does nothing.

This is provided for administrators that want to
turn off requesting external resources.

Args:
    version: Current JupyterLab version

Attributes:
    versi…

```python
jupyterlab.NeverCheckForUpdate(self, version: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

### `BrowserApp`

An app the launches JupyterLab and waits for it to start up, checking for
JS console errors, JS errors, and Python logged errors.

```python
jupyterlab.browser_check.BrowserApp(self, **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `t.Any` | `—` | **kwargs |

### `LabApp`

A Mixin class for shimming configuration from
NotebookApp to ServerApp. This class handles warnings, errors,
etc.

This class should be used during a transition period for apps
that are switching fro…

```python
jupyterlab.browser_check.LabApp(self, **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `t.Any` | `—` | **kwargs |

### `LogErrorHandler`

A handler that exits with 1 on a logged error.

```python
jupyterlab.browser_check.LogErrorHandler(self)
```

### `TestEnv`

Set Jupyter path variables to a temporary directory

Useful as a context manager or with explicit start/stop

```python
jupyterlab.browser_check.TestEnv(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `AppOptions`

Options object for build system

```python
jupyterlab.commands.AppOptions(self, logger=None, core_config=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logger` | `—` | `None` | pos/kw |
| `core_config` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CoreConfig`

An object representing a core config.

This enables custom lab application to override some parts of the core
configuration of the build system.

```python
jupyterlab.commands.CoreConfig(self)
```

### `LockStatus`

LockStatus(entire_extension_locked: bool, locked_plugins: Optional[frozenset[str]] = None)

```python
jupyterlab.commands.LockStatus(self, entire_extension_locked: bool, locked_plugins: Optional[frozenset[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `entire_extension_locked` | `bool` | `—` | pos/kw |
| `locked_plugins` | `Optional` | `None` | pos/kw |

### `Process`

A wrapper for a child process.

```python
jupyterlab.commands.Process(self, cmd: 'list[str]', logger: 'Logger | None' = None, cwd: 'str | None' = None, kill_event: 'threading.Event | None' = None, env: 'dict[str, str] | None' = None, quiet: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `list[str]` | `—` | pos/kw |
| `logger` | `Logger \| None` | `None` | pos/kw |
| `cwd` | `str \| None` | `None` | pos/kw |
| `kill_event` | `threading.Event \| None` | `None` | pos/kw |
| `env` | `dict[str, str] \| None` | `None` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |

### `ProgressProcess`

A wrapper for a child process.

```python
jupyterlab.commands.ProgressProcess(self, cmd, logger=None, cwd=None, kill_event=None, env=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `—` | `—` | pos/kw |
| `logger` | `—` | `None` | pos/kw |
| `cwd` | `—` | `None` | pos/kw |
| `kill_event` | `—` | `None` | pos/kw |
| `env` | `—` | `None` | pos/kw |

### `Range`

```python
jupyterlab.commands.Range(self, range_, loose)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `range_` | `—` | `—` | pos/kw |
| `loose` | `—` | `—` | pos/kw |

### `WatchHelper`

A process helper for a watch process.

```python
jupyterlab.commands.WatchHelper(self, cmd: 'list[str]', startup_regex: 'str', logger: 'Logger | None' = None, cwd: 'str | None' = None, kill_event: 'threading.Event | None' = None, env: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `list[str]` | `—` | pos/kw |
| `startup_regex` | `str` | `—` | pos/kw |
| `logger` | `Logger \| None` | `None` | pos/kw |
| `cwd` | `str \| None` | `None` | pos/kw |
| `kill_event` | `threading.Event \| None` | `None` | pos/kw |
| `env` | `dict[str, str] \| None` | `None` | pos/kw |

### `CoreConfig`

An object representing a core config.

This enables custom lab application to override some parts of the core
configuration of the build system.

```python
jupyterlab.coreconfig.CoreConfig(self)
```

### `DebugLogFileMixin`

The base class for all classes that have descriptors.

```python
jupyterlab.debuglog.DebugLogFileMixin(self, **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `t.Any` | `—` | **kwargs |

## Functions

### `load_jupyter_server_extension`

```python
jupyterlab.load_jupyter_server_extension(serverapp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `serverapp` | `—` | `—` | pos/kw |

### `get_app_dir`

Get the configured JupyterLab app directory.

```python
jupyterlab.browser_check.get_app_dir()
```

### `run_async_process`

Run an asynchronous command

```python
jupyterlab.browser_check.run_async_process(cmd, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `run_browser`

Run the browser test and return an exit code.

```python
jupyterlab.browser_check.run_browser(url)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `—` | `—` | pos/kw |

### `run_browser_sync`

Run the browser test and return an exit code.

```python
jupyterlab.browser_check.run_browser_sync(url)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `—` | `—` | pos/kw |

### `run_test`

Synchronous entry point to run a test function.
func is a function that accepts an app url as a parameter and returns a result.
func can be synchronous or asynchronous.  If it is synchronous, it will…

```python
jupyterlab.browser_check.run_test(app, func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app` | `—` | `—` | pos/kw |
| `func` | `—` | `—` | pos/kw |

### `run_test_async`

Run a test against the application.
func is a function that accepts an app url as a parameter and returns a result.
func can be synchronous or asynchronous.  If it is synchronous, it will be run
in a…

```python
jupyterlab.browser_check.run_test_async(app, func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app` | `—` | `—` | pos/kw |
| `func` | `—` | `—` | pos/kw |

### `build`

Build the JupyterLab application.

```python
jupyterlab.commands.build(name=None, version=None, static_url=None, kill_event=None, clean_staging=False, app_options=None, production=True, minimize=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `None` | pos/kw |
| `version` | `—` | `None` | pos/kw |
| `static_url` | `—` | `None` | pos/kw |
| `kill_event` | `—` | `None` | pos/kw |
| `clean_staging` | `—` | `False` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `production` | `—` | `True` | pos/kw |
| `minimize` | `—` | `True` | pos/kw |

### `build_check`

Determine whether JupyterLab should be built.

Returns a list of messages.

```python
jupyterlab.commands.build_check(app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_options` | `—` | `None` | pos/kw |

### `check_extension`

Check if a JupyterLab extension is enabled or disabled.

```python
jupyterlab.commands.check_extension(extension, installed=False, app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extension` | `—` | `—` | pos/kw |
| `installed` | `—` | `False` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |

### `clean`

Clean the JupyterLab application directory.

```python
jupyterlab.commands.clean(app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_options` | `—` | `None` | pos/kw |

### `dedupe_yarn`

`yarn-deduplicate` with the `fewer` strategy to minimize total
packages installed in a given staging directory

This means a extension (or dependency) _could_ cause a downgrade of an
version expected…

```python
jupyterlab.commands.dedupe_yarn(path, logger=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `logger` | `—` | `None` | pos/kw |

### `disable_extension`

Disable a JupyterLab extension/plugin.

Returns `True` if a rebuild is recommended, `False` otherwise.

```python
jupyterlab.commands.disable_extension(extension, app_options=None, level='sys_prefix')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extension` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `level` | `—` | `'sys_prefix'` | pos/kw |

### `enable_extension`

Enable a JupyterLab extension/plugin.

Returns `True` if a rebuild is recommended, `False` otherwise.

```python
jupyterlab.commands.enable_extension(extension, app_options=None, level='sys_prefix')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extension` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `level` | `—` | `'sys_prefix'` | pos/kw |

### `ensure_app`

Ensure that an application directory is available.

If it does not exist, return a list of messages to prompt the user.

```python
jupyterlab.commands.ensure_app(app_dir)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_dir` | `—` | `—` | pos/kw |

### `ensure_core`

Ensure that the core assets are available.

```python
jupyterlab.commands.ensure_core(logger=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logger` | `—` | `None` | pos/kw |

### `ensure_dev`

Ensure that the dev assets are available.

```python
jupyterlab.commands.ensure_dev(logger=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logger` | `—` | `None` | pos/kw |

### `ensure_node_modules`

Ensure that node_modules is up to date.

Returns true if the node_modules was updated.

```python
jupyterlab.commands.ensure_node_modules(cwd, logger=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cwd` | `—` | `—` | pos/kw |
| `logger` | `—` | `None` | pos/kw |

### `get_allowed_levels`

Returns the levels where configs can be stored.

```python
jupyterlab.commands.get_allowed_levels() -> 'list[str]'
```

**Returns:** `list[str]`

### `get_app_dir`

Get the configured JupyterLab app directory.

```python
jupyterlab.commands.get_app_dir()
```

### `get_app_info`

Get a dictionary of information about the app.

```python
jupyterlab.commands.get_app_info(app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_options` | `—` | `None` | pos/kw |

### `get_app_version`

Get the application version.

```python
jupyterlab.commands.get_app_version(app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_options` | `—` | `None` | pos/kw |

### `get_federated_extensions`

Get the metadata about federated extensions

```python
jupyterlab.commands.get_federated_extensions(labextensions_path: 'list[str]') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `labextensions_path` | `list[str]` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_latest_compatible_package_versions`

Get the latest compatible version of a list of packages.

```python
jupyterlab.commands.get_latest_compatible_package_versions(names, app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `names` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |

### `get_package_url`

Get the url from the extension data

```python
jupyterlab.commands.get_package_url(data: 'dict[str, Any]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `str`

### `get_page_config`

Get the page config for the application handler

```python
jupyterlab.commands.get_page_config(labextensions_path: 'list[str]', app_settings_dir: 'str | None' = None, logger: 'Logger | None' = None) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `labextensions_path` | `list[str]` | `—` | pos/kw |
| `app_settings_dir` | `str \| None` | `None` | pos/kw |
| `logger` | `Logger \| None` | `None` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_static_page_config`

Get the static page config for JupyterLab

Parameters
----------
logger: logger, optional
    An optional logging object
level: string, optional ['all']
    The level at which to get config: can be '…

```python
jupyterlab.commands.get_static_page_config(app_settings_dir: 'str | None' = None, logger: 'Logger | None' = None, level: 'str' = 'all', include_higher_levels: 'bool' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_settings_dir` | `str \| None` | `None` | pos/kw |
| `logger` | `Logger \| None` | `None` | pos/kw |
| `level` | `str` | `'all'` | pos/kw |
| `include_higher_levels` | `bool` | `False` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_user_settings_dir`

Get the configured JupyterLab user settings directory.

```python
jupyterlab.commands.get_user_settings_dir()
```

### `get_workspaces_dir`

Get the configured JupyterLab workspaces directory.

```python
jupyterlab.commands.get_workspaces_dir()
```

### `gt`

```python
jupyterlab.commands.gt(a, b, loose)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `loose` | `—` | `—` | pos/kw |

### `gte`

```python
jupyterlab.commands.gte(a, b, loose)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `loose` | `—` | `—` | pos/kw |

### `install_extension`

Install an extension package into JupyterLab.

The extension is first validated.

Returns `True` if a rebuild is recommended, `False` otherwise.

```python
jupyterlab.commands.install_extension(extension, app_options=None, pin=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extension` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `pin` | `—` | `None` | pos/kw |

### `link_package`

Link a package against the JupyterLab build.

Returns `True` if a rebuild is recommended, `False` otherwise.

```python
jupyterlab.commands.link_package(path, app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |

### `list2cmdline`

Shim for list2cmdline on posix.

```python
jupyterlab.commands.list2cmdline(cmd_list: 'list[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd_list` | `list[str]` | `—` | pos/kw |

**Returns:** `str`

### `list_extensions`

List the extensions.

```python
jupyterlab.commands.list_extensions(app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_options` | `—` | `None` | pos/kw |

### `lock_extension`

Lock a JupyterLab extension/plugin.

```python
jupyterlab.commands.lock_extension(extension, app_options=None, level='sys_prefix')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extension` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `level` | `—` | `'sys_prefix'` | pos/kw |

### `lt`

```python
jupyterlab.commands.lt(a, b, loose)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `loose` | `—` | `—` | pos/kw |

### `lte`

```python
jupyterlab.commands.lte(a, b, loose)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `loose` | `—` | `—` | pos/kw |

### `make_semver`

```python
jupyterlab.commands.make_semver(version, loose)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `—` | `—` | pos/kw |
| `loose` | `—` | `—` | pos/kw |

### `pjoin`

Join paths to create a real path.

```python
jupyterlab.commands.pjoin(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `read_package`

Read the package data in a given target tarball.

```python
jupyterlab.commands.read_package(target)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target` | `—` | `—` | pos/kw |

### `uninstall_extension`

Uninstall an extension by name or path.

Returns `True` if a rebuild is recommended, `False` otherwise.

```python
jupyterlab.commands.uninstall_extension(name=None, app_options=None, all_=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `None` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `all_` | `—` | `False` | pos/kw |

### `unlink_package`

Unlink a package from JupyterLab by path or name.

Returns `True` if a rebuild is recommended, `False` otherwise.

```python
jupyterlab.commands.unlink_package(package, app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `package` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |

### `unlock_extension`

Unlock a JupyterLab extension/plugin.

```python
jupyterlab.commands.unlock_extension(extension, app_options=None, level='sys_prefix')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extension` | `—` | `—` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |
| `level` | `—` | `'sys_prefix'` | pos/kw |

### `update_extension`

Update an extension by name, or all extensions.
Either `name` must be given as a string, or `all_` must be `True`.
If `all_` is `True`, the value of `name` is ignored.
Returns `True` if a rebuild is…

```python
jupyterlab.commands.update_extension(name=None, all_=False, app_dir=None, app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `None` | pos/kw |
| `all_` | `—` | `False` | pos/kw |
| `app_dir` | `—` | `None` | pos/kw |
| `app_options` | `—` | `None` | pos/kw |

### `watch`

Watch the application.

Parameters
----------
app_options: :class:`AppOptions`, optional
    The application options.

Returns
-------
A list of processes to run asynchronously.

```python
jupyterlab.commands.watch(app_options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_options` | `—` | `None` | pos/kw |

### `watch_dev`

Run watch mode in a given directory.

Parameters
----------
logger: :class:`~logger.Logger`, optional
    The logger instance.

Returns
-------
A list of `WatchHelper` objects.

```python
jupyterlab.commands.watch_dev(logger=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logger` | `—` | `None` | pos/kw |

### `watch_packages`

Run watch mode for the source packages.

Parameters
----------
logger: :class:`~logger.Logger`, optional
    The logger instance.

Returns
-------
A list of `WatchHelper` objects.

```python
jupyterlab.commands.watch_packages(logger=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logger` | `—` | `None` | pos/kw |

### `which`

Get the full path to a command.

Parameters
----------
command: str
    The command name or path.
env: dict, optional
    The environment variables, defaults to `os.environ`.

```python
jupyterlab.commands.which(command: 'str', env: 'dict[str, str] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `command` | `str` | `—` | pos/kw |
| `env` | `dict[str, str] \| None` | `None` | pos/kw |

**Returns:** `str`

### `write_page_config`

Write page config to disk

```python
jupyterlab.commands.write_page_config(page_config: 'dict[str, Any]', level: 'str' = 'all') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `page_config` | `dict[str, Any]` | `—` | pos/kw |
| `level` | `str` | `'all'` | pos/kw |

### `pjoin`

Join paths to create a real path.

```python
jupyterlab.coreconfig.pjoin(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

## Methods

### `jupyterlab.browser_check.BrowserApp` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
jupyterlab.browser_check.BrowserApp.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `class_config_rst_doc`

Generate rST documentation for this class' config options.

Excludes traits defined on parent classes.

```python
jupyterlab.browser_check.BrowserApp.class_config_rst_doc() -> 'str'
```

**Returns:** `str`

### `class_config_section`

Get the config section for this class.

Parameters
----------
classes : list, optional
    The list of other classes in the config file.
    Used to reduce redundant information.

```python
jupyterlab.browser_check.BrowserApp.class_config_section(classes: 't.Sequence[type[HasTraits]] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classes` | `t.Sequence[type[HasTraits]] \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_help`

Get the help string for this class in ReST format.

If `inst` is given, its current trait values will be used in place of
class defaults.

```python
jupyterlab.browser_check.BrowserApp.class_get_help(inst: 'HasTraits | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_trait_help`

Get the helptext string for a single trait.

:param inst:
    If given, its current trait values will be used in place of
    the class default.
:param helptext:
    If not given, uses the `help` att…

```python
jupyterlab.browser_check.BrowserApp.class_get_trait_help(trait: 'TraitType[t.Any, t.Any]', inst: 'HasTraits | None' = None, helptext: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `trait` | `TraitType[t.Any, t.Any]` | `—` | pos/kw |
| `inst` | `HasTraits \| None` | `None` | pos/kw |
| `helptext` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
jupyterlab.browser_check.BrowserApp.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
jupyterlab.browser_check.BrowserApp.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_print_help`

Get the help string for a single trait and print it.

```python
jupyterlab.browser_check.BrowserApp.class_print_help(inst: 'HasTraits | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
jupyterlab.browser_check.BrowserApp.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
jupyterlab.browser_check.BrowserApp.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `clear_instance`

unset _instance for this class and singleton parents.

```python
jupyterlab.browser_check.BrowserApp.clear_instance() -> 'None'
```

### `close_handlers`

```python
jupyterlab.browser_check.BrowserApp.close_handlers(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `current_activity`

Return a list of activity happening in this extension.

```python
jupyterlab.browser_check.BrowserApp.current_activity(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `document_config_options`

Generate rST format documentation for the config options this application

Returns a multiline string.

```python
jupyterlab.browser_check.BrowserApp.document_config_options(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `emit_alias_help`

Yield the lines for alias part of the help.

```python
jupyterlab.browser_check.BrowserApp.emit_alias_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_description`

Yield lines with the application description.

```python
jupyterlab.browser_check.BrowserApp.emit_description(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_examples`

Yield lines with the usage and examples.

This usage string goes at the end of the command line help string
and should contain examples of the application's usage.

```python
jupyterlab.browser_check.BrowserApp.emit_examples(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_flag_help`

Yield the lines for the flag part of the help.

```python
jupyterlab.browser_check.BrowserApp.emit_flag_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_help`

Yield the help-lines for each Configurable class in self.classes.

If classes=False (the default), only flags and aliases are printed.

```python
jupyterlab.browser_check.BrowserApp.emit_help(self, classes: 'bool' = False) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `bool` | `False` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_help_epilogue`

Yield the very bottom lines of the help message.

If classes=False (the default), print `--help-all` msg.

```python
jupyterlab.browser_check.BrowserApp.emit_help_epilogue(self, classes: 'bool') -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `bool` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_options_help`

Yield the lines for the options part of the help.

```python
jupyterlab.browser_check.BrowserApp.emit_options_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_subcommands_help`

Yield the lines for the subcommand part of the help.

```python
jupyterlab.browser_check.BrowserApp.emit_subcommands_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `exit`

```python
jupyterlab.browser_check.BrowserApp.exit(self, exit_status: 'int | str | None' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `exit_status` | `int \| str \| None` | `0` | pos/kw |

### `flatten_flags`

Flatten flags and aliases for loaders, so cl-args override as expected.

This prevents issues such as an alias pointing to InteractiveShell,
but a config file setting the same trait in TerminalIntera…

```python
jupyterlab.browser_check.BrowserApp.flatten_flags(self) -> 'tuple[dict[str, t.Any], dict[str, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[dict[str, t.Any], dict[str, t.Any]]`

### `generate_config_file`

generate default config file from Configurables

```python
jupyterlab.browser_check.BrowserApp.generate_config_file(self, classes: 'ClassesType | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `ClassesType \| None` | `None` | pos/kw |

**Returns:** `str`

### `get_default_logging_config`

Return the base logging configuration.

The default is to log to stderr using a StreamHandler, if no default
handler already exists.

The log handler level starts at logging.WARN, but this can be adj…

```python
jupyterlab.browser_check.BrowserApp.get_default_logging_config(self) -> 'StrDict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `StrDict`

### `get_extension_package`

Get an extension package.

```python
jupyterlab.browser_check.BrowserApp.get_extension_package()
```

### `get_extension_point`

Get an extension point.

```python
jupyterlab.browser_check.BrowserApp.get_extension_point()
```

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
jupyterlab.browser_check.BrowserApp.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `hold_trait_notifications`

Context manager for bundling trait change notifications and cross
validation.

Use this when doing multiple trait assignments (init, config), to avoid
race conditions in trait notifiers requesting ot…

```python
jupyterlab.browser_check.BrowserApp.hold_trait_notifications(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `jupyterlab.browser_check.LabApp` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
jupyterlab.browser_check.LabApp.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `class_config_rst_doc`

Generate rST documentation for this class' config options.

Excludes traits defined on parent classes.

```python
jupyterlab.browser_check.LabApp.class_config_rst_doc() -> 'str'
```

**Returns:** `str`

### `class_config_section`

Get the config section for this class.

Parameters
----------
classes : list, optional
    The list of other classes in the config file.
    Used to reduce redundant information.

```python
jupyterlab.browser_check.LabApp.class_config_section(classes: 't.Sequence[type[HasTraits]] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classes` | `t.Sequence[type[HasTraits]] \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_help`

Get the help string for this class in ReST format.

If `inst` is given, its current trait values will be used in place of
class defaults.

```python
jupyterlab.browser_check.LabApp.class_get_help(inst: 'HasTraits | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_trait_help`

Get the helptext string for a single trait.

:param inst:
    If given, its current trait values will be used in place of
    the class default.
:param helptext:
    If not given, uses the `help` att…

```python
jupyterlab.browser_check.LabApp.class_get_trait_help(trait: 'TraitType[t.Any, t.Any]', inst: 'HasTraits | None' = None, helptext: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `trait` | `TraitType[t.Any, t.Any]` | `—` | pos/kw |
| `inst` | `HasTraits \| None` | `None` | pos/kw |
| `helptext` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
jupyterlab.browser_check.LabApp.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
jupyterlab.browser_check.LabApp.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_print_help`

Get the help string for a single trait and print it.

```python
jupyterlab.browser_check.LabApp.class_print_help(inst: 'HasTraits | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
jupyterlab.browser_check.LabApp.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
jupyterlab.browser_check.LabApp.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `clear_instance`

unset _instance for this class and singleton parents.

```python
jupyterlab.browser_check.LabApp.clear_instance() -> 'None'
```

### `close_handlers`

```python
jupyterlab.browser_check.LabApp.close_handlers(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `current_activity`

Return a list of activity happening in this extension.

```python
jupyterlab.browser_check.LabApp.current_activity(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `document_config_options`

Generate rST format documentation for the config options this application

Returns a multiline string.

```python
jupyterlab.browser_check.LabApp.document_config_options(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `emit_alias_help`

Yield the lines for alias part of the help.

```python
jupyterlab.browser_check.LabApp.emit_alias_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_description`

Yield lines with the application description.

```python
jupyterlab.browser_check.LabApp.emit_description(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_examples`

Yield lines with the usage and examples.

This usage string goes at the end of the command line help string
and should contain examples of the application's usage.

```python
jupyterlab.browser_check.LabApp.emit_examples(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_flag_help`

Yield the lines for the flag part of the help.

```python
jupyterlab.browser_check.LabApp.emit_flag_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_help`

Yield the help-lines for each Configurable class in self.classes.

If classes=False (the default), only flags and aliases are printed.

```python
jupyterlab.browser_check.LabApp.emit_help(self, classes: 'bool' = False) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `bool` | `False` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_help_epilogue`

Yield the very bottom lines of the help message.

If classes=False (the default), print `--help-all` msg.

```python
jupyterlab.browser_check.LabApp.emit_help_epilogue(self, classes: 'bool') -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `bool` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_options_help`

Yield the lines for the options part of the help.

```python
jupyterlab.browser_check.LabApp.emit_options_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_subcommands_help`

Yield the lines for the subcommand part of the help.

```python
jupyterlab.browser_check.LabApp.emit_subcommands_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `exit`

```python
jupyterlab.browser_check.LabApp.exit(self, exit_status: 'int | str | None' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `exit_status` | `int \| str \| None` | `0` | pos/kw |

### `flatten_flags`

Flatten flags and aliases for loaders, so cl-args override as expected.

This prevents issues such as an alias pointing to InteractiveShell,
but a config file setting the same trait in TerminalIntera…

```python
jupyterlab.browser_check.LabApp.flatten_flags(self) -> 'tuple[dict[str, t.Any], dict[str, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[dict[str, t.Any], dict[str, t.Any]]`

### `generate_config_file`

generate default config file from Configurables

```python
jupyterlab.browser_check.LabApp.generate_config_file(self, classes: 'ClassesType | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `ClassesType \| None` | `None` | pos/kw |

**Returns:** `str`

### `get_default_logging_config`

Return the base logging configuration.

The default is to log to stderr using a StreamHandler, if no default
handler already exists.

The log handler level starts at logging.WARN, but this can be adj…

```python
jupyterlab.browser_check.LabApp.get_default_logging_config(self) -> 'StrDict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `StrDict`

### `get_extension_package`

Get an extension package.

```python
jupyterlab.browser_check.LabApp.get_extension_package()
```

### `get_extension_point`

Get an extension point.

```python
jupyterlab.browser_check.LabApp.get_extension_point()
```

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
jupyterlab.browser_check.LabApp.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `hold_trait_notifications`

Context manager for bundling trait change notifications and cross
validation.

Use this when doing multiple trait assignments (init, config), to avoid
race conditions in trait notifiers requesting ot…

```python
jupyterlab.browser_check.LabApp.hold_trait_notifications(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `jupyterlab.browser_check.LogErrorHandler` methods

### `acquire`

Acquire the I/O thread lock.

```python
jupyterlab.browser_check.LogErrorHandler.acquire(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `addFilter`

Add the specified filter to this handler.

```python
jupyterlab.browser_check.LogErrorHandler.addFilter(self, filter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filter` | `—` | `—` | pos/kw |

### `close`

Tidy up any resources used by the handler.

This version removes the handler from an internal map of handlers,
_handlers, which is used for handler lookup by name. Subclasses
should ensure that this…

```python
jupyterlab.browser_check.LogErrorHandler.close(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `createLock`

Acquire a thread lock for serializing access to the underlying I/O.

```python
jupyterlab.browser_check.LogErrorHandler.createLock(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `emit`

Emit a record.

If a formatter is specified, it is used to format the record.
The record is then written to the stream with a trailing newline.  If
exception information is present, it is formatted u…

```python
jupyterlab.browser_check.LogErrorHandler.emit(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `filter`

Determine if a record is loggable by consulting all the filters.

The default is to allow the record to be logged; any filter can veto
this by returning a false value.
If a filter attached to a handl…

```python
jupyterlab.browser_check.LogErrorHandler.filter(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `flush`

Flushes the stream.

```python
jupyterlab.browser_check.LogErrorHandler.flush(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `format`

Format the specified record.

If a formatter is set, use it. Otherwise, use the default formatter
for the module.

```python
jupyterlab.browser_check.LogErrorHandler.format(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `get_name`

```python
jupyterlab.browser_check.LogErrorHandler.get_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle`

Conditionally emit the specified logging record.

Emission depends on filters which may have been added to the handler.
Wrap the actual emission of the record with acquisition/release of
the I/O thre…

```python
jupyterlab.browser_check.LogErrorHandler.handle(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `handleError`

Handle errors which occur during an emit() call.

This method should be called from handlers when an exception is
encountered during an emit() call. If raiseExceptions is false,
exceptions get silent…

```python
jupyterlab.browser_check.LogErrorHandler.handleError(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `release`

Release the I/O thread lock.

```python
jupyterlab.browser_check.LogErrorHandler.release(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `removeFilter`

Remove the specified filter from this handler.

```python
jupyterlab.browser_check.LogErrorHandler.removeFilter(self, filter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filter` | `—` | `—` | pos/kw |

### `setFormatter`

Set the formatter for this handler.

```python
jupyterlab.browser_check.LogErrorHandler.setFormatter(self, fmt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `fmt` | `—` | `—` | pos/kw |

### `setLevel`

Set the logging level of this handler.  level must be an int or a str.

```python
jupyterlab.browser_check.LogErrorHandler.setLevel(self, level)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `level` | `—` | `—` | pos/kw |

### `setStream`

Sets the StreamHandler's stream to the specified value,
if it is different.

Returns the old stream, if the stream was changed, or None
if it wasn't.

```python
jupyterlab.browser_check.LogErrorHandler.setStream(self, stream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |

### `set_name`

```python
jupyterlab.browser_check.LogErrorHandler.set_name(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `jupyterlab.browser_check.TestEnv` methods

### `start`

```python
jupyterlab.browser_check.TestEnv.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

```python
jupyterlab.browser_check.TestEnv.stop(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `jupyterlab.commands.AppOptions` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
jupyterlab.commands.AppOptions.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
jupyterlab.commands.AppOptions.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
jupyterlab.commands.AppOptions.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
jupyterlab.commands.AppOptions.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
jupyterlab.commands.AppOptions.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
jupyterlab.commands.AppOptions.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `hold_trait_notifications`

Context manager for bundling trait change notifications and cross
validation.

Use this when doing multiple trait assignments (init, config), to avoid
race conditions in trait notifiers requesting ot…

```python
jupyterlab.commands.AppOptions.hold_trait_notifications(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `notify_change`

Notify observers of a change event

```python
jupyterlab.commands.AppOptions.notify_change(self, change: 'Bunch') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `change` | `Bunch` | `—` | pos/kw |

### `observe`

Setup a handler to be called when a trait changes.

This is used to setup dynamic notifications of trait changes.

Parameters
----------
handler : callable
    A callable that is called when a trait…

```python
jupyterlab.commands.AppOptions.observe(self, handler: 't.Callable[..., t.Any]', names: 'Sentinel | str | t.Iterable[Sentinel | str]' = traitlets.All, type: 'Sentinel | str' = 'change') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `t.Callable[..., t.Any]` | `—` | pos/kw |
| `names` | `Sentinel \| str \| t.Iterable[Sentinel \| str]` | `traitlets.All` | pos/kw |
| `type` | `Sentinel \| str` | `'change'` | pos/kw |

### `on_trait_change`

DEPRECATED: Setup a handler to be called when a trait changes.

This is used to setup dynamic notifications of trait changes.

Static handlers can be created by creating methods on a HasTraits
subcla…

```python
jupyterlab.commands.AppOptions.on_trait_change(self, handler: 'EventHandler | None' = None, name: 'Sentinel | str | None' = None, remove: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `EventHandler \| None` | `None` | pos/kw |
| `name` | `Sentinel \| str \| None` | `None` | pos/kw |
| `remove` | `bool` | `False` | pos/kw |

### `set_trait`

Forcibly sets trait attribute, including read-only attributes.

```python
jupyterlab.commands.AppOptions.set_trait(self, name: 'str', value: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `t.Any` | `—` | pos/kw |

### `setup_instance`

This is called **before** self.__init__ is called.

```python
jupyterlab.commands.AppOptions.setup_instance(*args: 't.Any', **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `t.Any` | `—` | *args |
| `kwargs` | `t.Any` | `—` | **kwargs |

### `trait_defaults`

Return a trait's default value or a dictionary of them

Notes
-----
Dynamically generated default values may
depend on the current state of the object.

```python
jupyterlab.commands.AppOptions.trait_defaults(self, *names: 'str', **metadata: 't.Any') -> 'dict[str, t.Any] | Sentinel'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `names` | `str` | `—` | *args |
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, t.Any] | Sentinel`

### `trait_events`

Get a ``dict`` of all the event handlers of this class.

Parameters
----------
name : str (default: None)
    The name of a trait of this class. If name is ``None`` then all
    the event handlers of…

```python
jupyterlab.commands.AppOptions.trait_events(name: 'str | None' = None) -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str \| None` | `None` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `trait_has_value`

Returns True if the specified trait has a value.

This will return false even if ``getattr`` would return a
dynamically generated default value. These default values
will be recognized as existing on…

```python
jupyterlab.commands.AppOptions.trait_has_value(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `trait_metadata`

Get metadata values for trait by key.

```python
jupyterlab.commands.AppOptions.trait_metadata(self, traitname: 'str', key: 'str', default: 't.Any' = None) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traitname` | `str` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `default` | `t.Any` | `None` | pos/kw |

**Returns:** `t.Any`

### `trait_names`

Get a list of all the names of this class' traits.

```python
jupyterlab.commands.AppOptions.trait_names(self, **metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `trait_values`

A ``dict`` of trait names and their values.

The metadata kwargs allow functions to be passed in which
filter traits based on metadata values.  The functions should
take a single value as an argument…

```python
jupyterlab.commands.AppOptions.trait_values(self, **metadata: 't.Any') -> 'dict[str, t.Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, t.Any]`

### `traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

The TraitTypes returned don't know anything about the values
that the v…

```python
jupyterlab.commands.AppOptions.traits(self, **metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `unobserve`

Remove a trait change handler.

This is used to unregister handlers to trait change notifications.

Parameters
----------
handler : callable
    The callable called when a trait attribute changes.
na…

```python
jupyterlab.commands.AppOptions.unobserve(self, handler: 't.Callable[..., t.Any]', names: 'Sentinel | str | t.Iterable[Sentinel | str]' = traitlets.All, type: 'Sentinel | str' = 'change') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `t.Callable[..., t.Any]` | `—` | pos/kw |
| `names` | `Sentinel \| str \| t.Iterable[Sentinel \| str]` | `traitlets.All` | pos/kw |
| `type` | `Sentinel \| str` | `'change'` | pos/kw |

### `unobserve_all`

Remove trait change handlers of any type for the specified name.
If name is not specified, removes all trait notifiers.

```python
jupyterlab.commands.AppOptions.unobserve_all(self, name: 'str | t.Any' = traitlets.All) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str \| t.Any` | `traitlets.All` | pos/kw |

### `jupyterlab.commands.CoreConfig` methods

### `add`

Remove an extension/singleton.

If neither extension or mimeExtension is True (the default)
the package is added as a singleton dependency.

name: string
    The npm package name
semver: string
    T…

```python
jupyterlab.commands.CoreConfig.add(self, name, semver, extension=False, mime_extension=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `semver` | `—` | `—` | pos/kw |
| `extension` | `—` | `False` | pos/kw |
| `mime_extension` | `—` | `False` | pos/kw |

### `clear_packages`

Clear the packages/extensions.

```python
jupyterlab.commands.CoreConfig.clear_packages(self, lab_only=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lab_only` | `—` | `True` | pos/kw |

### `remove`

Remove a package/extension.

name: string
    The npm package name

```python
jupyterlab.commands.CoreConfig.remove(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `jupyterlab.commands.Process` methods

### `get_log`

Get our logger.

```python
jupyterlab.commands.Process.get_log(self) -> 'Logger'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Logger`

### `terminate`

Terminate the process and return the exit code.

```python
jupyterlab.commands.Process.terminate(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `wait`

Wait for the process to finish.

Returns
-------
The process exit code.

```python
jupyterlab.commands.Process.wait(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `wait_async`

Asynchronously wait for the process to finish.

```python
jupyterlab.commands.Process.wait_async(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `jupyterlab.commands.ProgressProcess` methods

### `get_log`

Get our logger.

```python
jupyterlab.commands.ProgressProcess.get_log(self) -> 'Logger'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Logger`

### `terminate`

Terminate the process and return the exit code.

```python
jupyterlab.commands.ProgressProcess.terminate(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `wait`

Wait for the process to finish.

Returns
-------
The process exit code.

```python
jupyterlab.commands.ProgressProcess.wait(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `wait_async`

Asynchronously wait for the process to finish.

```python
jupyterlab.commands.ProgressProcess.wait_async(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `jupyterlab.commands.Range` methods

### `format`

```python
jupyterlab.commands.Range.format(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `parse_range`

```python
jupyterlab.commands.Range.parse_range(self, range_)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `range_` | `—` | `—` | pos/kw |

### `test`

```python
jupyterlab.commands.Range.test(self, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `jupyterlab.commands.WatchHelper` methods

### `get_log`

Get our logger.

```python
jupyterlab.commands.WatchHelper.get_log(self) -> 'Logger'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Logger`

### `terminate`

Terminate the process.

```python
jupyterlab.commands.WatchHelper.terminate(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `wait`

Wait for the process to finish.

Returns
-------
The process exit code.

```python
jupyterlab.commands.WatchHelper.wait(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `wait_async`

Asynchronously wait for the process to finish.

```python
jupyterlab.commands.WatchHelper.wait_async(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `jupyterlab.coreconfig.CoreConfig` methods

### `add`

Remove an extension/singleton.

If neither extension or mimeExtension is True (the default)
the package is added as a singleton dependency.

name: string
    The npm package name
semver: string
    T…

```python
jupyterlab.coreconfig.CoreConfig.add(self, name, semver, extension=False, mime_extension=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `semver` | `—` | `—` | pos/kw |
| `extension` | `—` | `False` | pos/kw |
| `mime_extension` | `—` | `False` | pos/kw |

### `clear_packages`

Clear the packages/extensions.

```python
jupyterlab.coreconfig.CoreConfig.clear_packages(self, lab_only=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lab_only` | `—` | `True` | pos/kw |

### `remove`

Remove a package/extension.

name: string
    The npm package name

```python
jupyterlab.coreconfig.CoreConfig.remove(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `jupyterlab.debuglog.DebugLogFileMixin` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
jupyterlab.debuglog.DebugLogFileMixin.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `class_config_rst_doc`

Generate rST documentation for this class' config options.

Excludes traits defined on parent classes.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_config_rst_doc() -> 'str'
```

**Returns:** `str`

### `class_config_section`

Get the config section for this class.

Parameters
----------
classes : list, optional
    The list of other classes in the config file.
    Used to reduce redundant information.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_config_section(classes: 't.Sequence[type[HasTraits]] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classes` | `t.Sequence[type[HasTraits]] \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_help`

Get the help string for this class in ReST format.

If `inst` is given, its current trait values will be used in place of
class defaults.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_get_help(inst: 'HasTraits | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_trait_help`

Get the helptext string for a single trait.

:param inst:
    If given, its current trait values will be used in place of
    the class default.
:param helptext:
    If not given, uses the `help` att…

```python
jupyterlab.debuglog.DebugLogFileMixin.class_get_trait_help(trait: 'TraitType[t.Any, t.Any]', inst: 'HasTraits | None' = None, helptext: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `trait` | `TraitType[t.Any, t.Any]` | `—` | pos/kw |
| `inst` | `HasTraits \| None` | `None` | pos/kw |
| `helptext` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_print_help`

Get the help string for a single trait and print it.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_print_help(inst: 'HasTraits | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
jupyterlab.debuglog.DebugLogFileMixin.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
jupyterlab.debuglog.DebugLogFileMixin.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `debug_logging`

```python
jupyterlab.debuglog.DebugLogFileMixin.debug_logging(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
jupyterlab.debuglog.DebugLogFileMixin.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`


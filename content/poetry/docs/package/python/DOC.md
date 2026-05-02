---
name: package
description: "Poetry package guide for Python dependency management, virtual environments, packaging, and publishing"
metadata:
  languages: "python"
  versions: "2.3.2"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "poetry,python,packaging,dependencies,virtualenv,pyproject,publishing,toml,false,Version-Sensitive,Config,all,create,get,merge,process,raw,set_auth_config_source,set_config_source,DictConfigSource,add_property,get_property,remove_property,FileConfigSource,secure,PackageFilterPolicy,allows,has_exact_package,is_reserved,normalize,validator,TOMLFile,exists,read,write,boolean_normalizer,boolean_validator,build_config_setting_normalizer,build_config_setting_validator,data_dir,int_normalizer,ConfigSource,ConfigSourceMigration,apply,dry_run,PropertyNotFoundError,drop_empty_config_category,Priority,Source,to_dict,to_toml_table,Application,add,are_exceptions_caught,auto_exits,catch_exceptions,configure_env,configure_installer_for_command,configure_installer_for_event,create_io,extract_namespace,find,find_namespace,get_namespaces,has,is_auto_exit_enabled,is_single_command,register_command_loggers,render_error,reset_poetry,run,set_command_loader,set_display_name,set_event_dispatcher,set_name,set_solution_provider_repository,set_ui,set_version,Command,add_style,argument,ask,call,call_silent,choice,comment,configure,confirm,create_question,execute,get_application,handle,ignore_validation_errors,info,initialize,interact,line,line_error,merge_application_definition,option,overwrite,progress_bar,progress_indicator,question,render_table,secret,set_application,CommandLoader,register_factory,PoetryRuntimeError,append,get_text,directory,ensure_path,load_command,main,ConsoleMessage,indent,make_section,wrap,GroupNotFoundError,PoetryConsoleError,PrettyCalledProcessError,decode,PoetryCoreError,Dependency,activate,allows_prereleases,clone,create_from_pep_508,deactivate,is_activated,is_direct_origin,is_directory,is_file,is_optional,is_same_package_as,is_same_source_as,is_url,is_vcs,provides,to_pep_508,with_constraint,with_features,with_groups,without_features,DependencyGroup,add_dependency,add_poetry_dependency,include_dependency_group,remove_dependency,Factory,configure_package,create_dependency,create_poetry,get_package,locate,validate,combine_unicode,readme_content_type,ValidationError,validate_object"
---

# poetry — package

## Install

```bash
pip install poetry
```

## Imports

```python
import poetry
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Config` | Class |  |
| `all` | Method |  |
| `create` | Method |  |
| `get` | Method | Retrieve a setting value. |
| `merge` | Method |  |
| `process` | Method |  |
| `raw` | Method |  |
| `set_auth_config_source` | Method |  |
| `set_config_source` | Method |  |
| `DictConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `FileConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `secure` | Method |  |
| `PackageFilterPolicy` | Class | PackageFilterPolicy(policy: 'dataclasses.InitVar[str \| list[str] \| None]') |
| `allows` | Method |  |
| `has_exact_package` | Method |  |
| `is_reserved` | Method |  |
| `normalize` | Method |  |
| `validator` | Method |  |
| `TOMLFile` | Class | Represents a TOML file.  :param path: path to the TOML file |
| `exists` | Method |  |
| `read` | Method | Read the file content as a :class:`tomlkit.toml_document.TOMLDocument`. |
| `write` | Method | Write the TOMLDocument to the file. |
| `boolean_normalizer` | Function |  |
| `boolean_validator` | Function |  |
| `build_config_setting_normalizer` | Function |  |
| `build_config_setting_validator` | Function |  |
| `data_dir` | Function |  |
| `int_normalizer` | Function |  |
| `ConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `ConfigSourceMigration` | Class | ConfigSourceMigration(old_key: 'str', new_key: 'str \| None', value_migration: '… |
| `apply` | Method |  |
| `dry_run` | Method |  |
| `PropertyNotFoundError` | Class | Inappropriate argument value (of correct type). |
| `drop_empty_config_category` | Function |  |
| `ConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `DictConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `PropertyNotFoundError` | Class | Inappropriate argument value (of correct type). |
| `ConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `FileConfigSource` | Class | Helper class that provides a standard way to create an ABC using inheritance. |
| `add_property` | Method |  |
| `get_property` | Method |  |
| `remove_property` | Method |  |
| `secure` | Method |  |
| `PropertyNotFoundError` | Class | Inappropriate argument value (of correct type). |
| `drop_empty_config_category` | Function |  |
| `Priority` | Class | Enum where members are also (and must be) ints |
| `Source` | Class | Source(name: 'str', url: 'str' = '', priority: 'Priority' = <Priority.PRIMARY:… |
| `to_dict` | Method |  |
| `to_toml_table` | Method |  |
| `Application` | Class | An Application is the container for a collection of commands.  This class is op… |
| `add` | Method |  |
| `all` | Method |  |
| `are_exceptions_caught` | Method |  |
| `auto_exits` | Method |  |
| `catch_exceptions` | Method |  |
| `configure_env` | Method |  |
| `configure_installer_for_command` | Method |  |
| `configure_installer_for_event` | Method |  |
| `create_io` | Method |  |
| `extract_namespace` | Method |  |
| `find` | Method |  |
| `find_namespace` | Method |  |
| `get` | Method |  |
| `get_namespaces` | Method |  |
| `has` | Method |  |
| `is_auto_exit_enabled` | Method |  |
| `is_single_command` | Method |  |
| `register_command_loggers` | Method |  |
| `render_error` | Method |  |
| `reset_poetry` | Method |  |
| `run` | Method |  |
| `set_command_loader` | Method |  |
| `set_display_name` | Method |  |
| `set_event_dispatcher` | Method |  |
| `set_name` | Method |  |
| `set_solution_provider_repository` | Method |  |
| `set_ui` | Method |  |
| `set_version` | Method |  |
| `Command` | Class |  |
| `add_style` | Method | Adds a new style |
| `argument` | Method | Get the value of a command argument. |
| `ask` | Method | Prompt the user for input. |
| `call` | Method | Call another command. |
| `call_silent` | Method | Call another command silently. |
| `choice` | Method | Give the user a single choice from an list of answers. |
| `comment` | Method | Write a string as comment output.  :param text: The line to write :type text: s… |
| `configure` | Method | Configures the current command. |
| `confirm` | Method | Confirm a question with the user. |
| `create_question` | Method | Returns a Question of specified type. |
| `execute` | Method |  |
| `get_application` | Method |  |
| `handle` | Method | Execute the command. |
| `ignore_validation_errors` | Method |  |
| `info` | Method | Write a string as information output.  :param text: The line to write :type tex… |
| `initialize` | Method |  |
| `interact` | Method | Interacts with the user. |
| `line` | Method | Write a string as information output. |
| `line_error` | Method | Write a string as information output to stderr. |
| `merge_application_definition` | Method |  |
| `option` | Method | Get the value of a command option. |
| `overwrite` | Method | Overwrites the current line.  It will not add a new line so use line('') if nec… |
| `progress_bar` | Method | Creates a new progress bar |
| `progress_indicator` | Method | Creates a new progress indicator. |
| `question` | Method | Write a string as question output.  :param text: The line to write :type text:… |
| `render_table` | Method | Format input to textual table. |
| `reset_poetry` | Method |  |
| `run` | Method |  |
| `secret` | Method | Prompt the user for input but hide the answer from the console. |
| `set_application` | Method |  |
| `CommandLoader` | Class | A simple command loader using factories to instantiate commands lazily. |
| `get` | Method | Loads a command. |
| `has` | Method | Checks whether a command exists or not. |
| `register_factory` | Method |  |
| `PoetryRuntimeError` | Class | Represents a runtime error in the Poetry console application. |
| `append` | Method |  |
| `create` | Method | Create an instance of this class using the provided reason. If an exception is… |
| `get_text` | Method | Convert the error messages to a formatted string. All empty messages are ignore… |
| `write` | Method | Write the error text to the provided IO iff there is any text to write. |
| `directory` | Function |  |
| `ensure_path` | Function |  |
| `load_command` | Function |  |
| `main` | Function |  |
| `CommandLoader` | Class | A simple command loader using factories to instantiate commands lazily. |
| `get` | Method | Loads a command. |
| `has` | Method | Checks whether a command exists or not. |
| `register_factory` | Method |  |
| `ConsoleMessage` | Class | Representation of a console message, providing utilities for formatting text wi… |
| `indent` | Method |  |
| `make_section` | Method |  |
| `wrap` | Method |  |
| `GroupNotFoundError` | Class | Base Cleo exception. |
| `PoetryConsoleError` | Class | Base Cleo exception. |
| `PoetryRuntimeError` | Class | Represents a runtime error in the Poetry console application. |
| `append` | Method |  |
| `create` | Method | Create an instance of this class using the provided reason. If an exception is… |
| `get_text` | Method | Convert the error messages to a formatted string. All empty messages are ignore… |
| `write` | Method | Write the error text to the provided IO iff there is any text to write. |
| `PrettyCalledProcessError` | Class | Represents a formatted and decorated error object for a subprocess call.  This… |
| `decode` | Function |  |
| `PoetryCoreError` | Class | Common base class for all non-exit exceptions. |
| `Dependency` | Class |  |
| `activate` | Method | Set the dependency as mandatory. |
| `allows_prereleases` | Method | None (default): only use pre-release versions                 if no stable vers… |
| `clone` | Method |  |
| `create_from_pep_508` | Method | Resolve a PEP-508 requirement string to a `Dependency` instance. If a `relative… |
| `deactivate` | Method | Set the dependency as optional. |
| `is_activated` | Method |  |
| `is_direct_origin` | Method |  |
| `is_directory` | Method |  |
| `is_file` | Method |  |
| `is_optional` | Method |  |
| `is_same_package_as` | Method |  |
| `is_same_source_as` | Method |  |
| `is_url` | Method |  |
| `is_vcs` | Method |  |
| `provides` | Method | Helper method to determine if this package provides the given specification.  T… |
| `to_pep_508` | Method |  |
| `with_constraint` | Method |  |
| `with_features` | Method |  |
| `with_groups` | Method |  |
| `without_features` | Method |  |
| `DependencyGroup` | Class |  |
| `add_dependency` | Method |  |
| `add_poetry_dependency` | Method |  |
| `include_dependency_group` | Method |  |
| `is_optional` | Method |  |
| `remove_dependency` | Method |  |
| `Factory` | Class | Factory class to create various elements needed by Poetry. |
| `configure_package` | Method |  |
| `create_dependency` | Method |  |
| `create_poetry` | Method |  |
| `get_package` | Method |  |
| `locate` | Method |  |
| `validate` | Method | Checks the validity of a configuration |
| `combine_unicode` | Function |  |
| `readme_content_type` | Function |  |
| `ValidationError` | Class | Inappropriate argument value (of correct type). |
| `validate_object` | Function |  |
| `Dependency` | Class |  |
| `activate` | Method | Set the dependency as mandatory. |
| `allows_prereleases` | Method | None (default): only use pre-release versions                 if no stable vers… |
| `clone` | Method |  |

## Classes

### `Config`

```python
poetry.config.config.Config(self, use_environment: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `use_environment` | `bool` | `True` | pos/kw |

### `DictConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.config.DictConfigSource(self) -> 'None'
```

### `FileConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.config.FileConfigSource(self, file: 'TOMLFile') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `file` | `TOMLFile` | `—` | pos/kw |

### `PackageFilterPolicy`

PackageFilterPolicy(policy: 'dataclasses.InitVar[str | list[str] | None]')

```python
poetry.config.config.PackageFilterPolicy(self, policy: 'dataclasses.InitVar[str | list[str] | None]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `policy` | `dataclasses.InitVar[str \| list[str] \| None]` | `—` | pos/kw |

### `TOMLFile`

Represents a TOML file.

:param path: path to the TOML file

```python
poetry.config.config.TOMLFile(self, path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |

### `ConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.config_source.ConfigSource(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigSourceMigration`

ConfigSourceMigration(old_key: 'str', new_key: 'str | None', value_migration: 'dict[Any, Any]' = <factory>)

```python
poetry.config.config_source.ConfigSourceMigration(self, old_key: 'str', new_key: 'str | None', value_migration: 'dict[Any, Any]' = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old_key` | `str` | `—` | pos/kw |
| `new_key` | `str \| None` | `—` | pos/kw |
| `value_migration` | `dict[Any, Any]` | `<factory>` | pos/kw |

### `PropertyNotFoundError`

Inappropriate argument value (of correct type).

```python
poetry.config.config_source.PropertyNotFoundError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.dict_config_source.ConfigSource(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DictConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.dict_config_source.DictConfigSource(self) -> 'None'
```

### `PropertyNotFoundError`

Inappropriate argument value (of correct type).

```python
poetry.config.dict_config_source.PropertyNotFoundError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.file_config_source.ConfigSource(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FileConfigSource`

Helper class that provides a standard way to create an ABC using
inheritance.

```python
poetry.config.file_config_source.FileConfigSource(self, file: 'TOMLFile') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `file` | `TOMLFile` | `—` | pos/kw |

### `PropertyNotFoundError`

Inappropriate argument value (of correct type).

```python
poetry.config.file_config_source.PropertyNotFoundError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Priority`

Enum where members are also (and must be) ints

```python
poetry.config.source.Priority(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Source`

Source(name: 'str', url: 'str' = '', priority: 'Priority' = <Priority.PRIMARY: 1>)

```python
poetry.config.source.Source(self, name: 'str', url: 'str' = '', priority: 'Priority' = <Priority.PRIMARY: 1>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `url` | `str` | `''` | pos/kw |
| `priority` | `Priority` | `<Priority.PRIMARY: 1>` | pos/kw |

### `Application`

An Application is the container for a collection of commands.

This class is optimized for a standard CLI environment.

Usage:
>>> app = Application('myapp', '1.0 (stable)')
>>> app.add(Command())
>>…

```python
poetry.console.application.Application(self) -> 'None'
```

### `Command`

```python
poetry.console.application.Command(self) -> 'None'
```

### `CommandLoader`

A simple command loader using factories to instantiate commands lazily.

```python
poetry.console.application.CommandLoader(self, factories: 'dict[str, Factory]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `factories` | `dict[str, Factory]` | `—` | pos/kw |

### `PoetryRuntimeError`

Represents a runtime error in the Poetry console application.

```python
poetry.console.application.PoetryRuntimeError(self, reason: 'str', messages: 'list[ConsoleMessage] | None' = None, exit_code: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `reason` | `str` | `—` | pos/kw |
| `messages` | `list[ConsoleMessage] \| None` | `None` | pos/kw |
| `exit_code` | `int` | `1` | pos/kw |

### `CommandLoader`

A simple command loader using factories to instantiate commands lazily.

```python
poetry.console.command_loader.CommandLoader(self, factories: 'dict[str, Factory]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `factories` | `dict[str, Factory]` | `—` | pos/kw |

### `ConsoleMessage`

Representation of a console message, providing utilities for formatting text
with tags, indentation, and sections.

The ConsoleMessage class is designed to represent text messages that might be
displ…

```python
poetry.console.exceptions.ConsoleMessage(self, text: 'str', debug: 'bool' = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `str` | `—` | pos/kw |
| `debug` | `bool` | `False` | pos/kw |

### `GroupNotFoundError`

Base Cleo exception.

```python
poetry.console.exceptions.GroupNotFoundError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PoetryConsoleError`

Base Cleo exception.

```python
poetry.console.exceptions.PoetryConsoleError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PoetryRuntimeError`

Represents a runtime error in the Poetry console application.

```python
poetry.console.exceptions.PoetryRuntimeError(self, reason: 'str', messages: 'list[ConsoleMessage] | None' = None, exit_code: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `reason` | `str` | `—` | pos/kw |
| `messages` | `list[ConsoleMessage] \| None` | `None` | pos/kw |
| `exit_code` | `int` | `1` | pos/kw |

### `PrettyCalledProcessError`

Represents a formatted and decorated error object for a subprocess call.

This class is used to encapsulate information about a `CalledProcessError`,
providing additional context such as command outp…

```python
poetry.console.exceptions.PrettyCalledProcessError(self, exception: 'InitVar[CalledProcessError]', indent: 'InitVar[str]' = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exception` | `InitVar[CalledProcessError]` | `—` | pos/kw |
| `indent` | `InitVar[str]` | `''` | pos/kw |

### `PoetryCoreError`

Common base class for all non-exit exceptions.

```python
poetry.core.exceptions.PoetryCoreError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Dependency`

```python
poetry.core.factory.Dependency(self, name: 'str', constraint: 'str | VersionConstraint', optional: 'bool' = False, groups: 'Iterable[str] | None' = None, allows_prereleases: 'bool | None' = None, extras: 'Iterable[str] | None' = None, source_type: 'str | None' = None, source_url: 'str | None' = None, source_reference: 'str | None' = None, source_resolved_reference: 'str | None' = None, source_subdirectory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `constraint` | `str \| VersionConstraint` | `—` | pos/kw |
| `optional` | `bool` | `False` | pos/kw |
| `groups` | `Iterable[str] \| None` | `None` | pos/kw |
| `allows_prereleases` | `bool \| None` | `None` | pos/kw |
| `extras` | `Iterable[str] \| None` | `None` | pos/kw |
| `source_type` | `str \| None` | `None` | pos/kw |
| `source_url` | `str \| None` | `None` | pos/kw |
| `source_reference` | `str \| None` | `None` | pos/kw |
| `source_resolved_reference` | `str \| None` | `None` | pos/kw |
| `source_subdirectory` | `str \| None` | `None` | pos/kw |

### `DependencyGroup`

```python
poetry.core.factory.DependencyGroup(self, name: 'str', *, optional: 'bool' = False, mixed_dynamic: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `optional` | `bool` | `False` | kw |
| `mixed_dynamic` | `bool` | `False` | kw |

### `Factory`

Factory class to create various elements needed by Poetry.

```python
poetry.core.factory.Factory(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ValidationError`

Inappropriate argument value (of correct type).

```python
poetry.core.json.ValidationError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Dependency`

```python
poetry.core.poetry.Dependency(self, name: 'str', constraint: 'str | VersionConstraint', optional: 'bool' = False, groups: 'Iterable[str] | None' = None, allows_prereleases: 'bool | None' = None, extras: 'Iterable[str] | None' = None, source_type: 'str | None' = None, source_url: 'str | None' = None, source_reference: 'str | None' = None, source_resolved_reference: 'str | None' = None, source_subdirectory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `constraint` | `str \| VersionConstraint` | `—` | pos/kw |
| `optional` | `bool` | `False` | pos/kw |
| `groups` | `Iterable[str] \| None` | `None` | pos/kw |
| `allows_prereleases` | `bool \| None` | `None` | pos/kw |
| `extras` | `Iterable[str] \| None` | `None` | pos/kw |
| `source_type` | `str \| None` | `None` | pos/kw |
| `source_url` | `str \| None` | `None` | pos/kw |
| `source_reference` | `str \| None` | `None` | pos/kw |
| `source_resolved_reference` | `str \| None` | `None` | pos/kw |
| `source_subdirectory` | `str \| None` | `None` | pos/kw |

## Functions

### `boolean_normalizer`

```python
poetry.config.config.boolean_normalizer(val: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `val` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `boolean_validator`

```python
poetry.config.config.boolean_validator(val: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `val` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `build_config_setting_normalizer`

```python
poetry.config.config.build_config_setting_normalizer(val: 'str') -> 'Mapping[str, str | Sequence[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `val` | `str` | `—` | pos/kw |

**Returns:** `Mapping[str, str | Sequence[str]]`

### `build_config_setting_validator`

```python
poetry.config.config.build_config_setting_validator(val: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `val` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `data_dir`

```python
poetry.config.config.data_dir() -> 'Path'
```

**Returns:** `Path`

### `int_normalizer`

```python
poetry.config.config.int_normalizer(val: 'str') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `val` | `str` | `—` | pos/kw |

**Returns:** `int`

### `drop_empty_config_category`

```python
poetry.config.config_source.drop_empty_config_category(keys: 'list[str]', config: 'dict[Any, Any]') -> 'dict[Any, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `list[str]` | `—` | pos/kw |
| `config` | `dict[Any, Any]` | `—` | pos/kw |

**Returns:** `dict[Any, Any]`

### `drop_empty_config_category`

```python
poetry.config.file_config_source.drop_empty_config_category(keys: 'list[str]', config: 'dict[Any, Any]') -> 'dict[Any, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keys` | `list[str]` | `—` | pos/kw |
| `config` | `dict[Any, Any]` | `—` | pos/kw |

**Returns:** `dict[Any, Any]`

### `directory`

```python
poetry.console.application.directory(path: 'Path') -> 'Iterator[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |

**Returns:** `Iterator[Path]`

### `ensure_path`

```python
poetry.console.application.ensure_path(path: 'str | Path', is_directory: 'bool' = False) -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str \| Path` | `—` | pos/kw |
| `is_directory` | `bool` | `False` | pos/kw |

**Returns:** `Path`

### `load_command`

```python
poetry.console.application.load_command(name: 'str') -> 'Callable[[], Command]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `Callable[[], Command]`

### `main`

```python
poetry.console.application.main() -> 'int'
```

**Returns:** `int`

### `decode`

```python
poetry.console.exceptions.decode(string: 'bytes | str', encodings: 'list[str] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `bytes \| str` | `—` | pos/kw |
| `encodings` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `str`

### `combine_unicode`

```python
poetry.core.factory.combine_unicode(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `readme_content_type`

```python
poetry.core.factory.readme_content_type(path: 'str | Path') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str \| Path` | `—` | pos/kw |

**Returns:** `str`

### `validate_object`

```python
poetry.core.json.validate_object(obj: 'dict[str, Any]', schema_name: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `dict[str, Any]` | `—` | pos/kw |
| `schema_name` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

## Methods

### `poetry.config.config.Config` methods

### `all`

```python
poetry.config.config.Config.all(self) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `create`

```python
poetry.config.config.Config.create(reload: 'bool' = False) -> 'Config'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `reload` | `bool` | `False` | pos/kw |

**Returns:** `Config`

### `get`

Retrieve a setting value.

```python
poetry.config.config.Config.get(self, setting_name: 'str', default: 'Any' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `setting_name` | `str` | `—` | pos/kw |
| `default` | `Any` | `None` | pos/kw |

**Returns:** `Any`

### `merge`

```python
poetry.config.config.Config.merge(self, config: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `dict[str, Any]` | `—` | pos/kw |

### `process`

```python
poetry.config.config.Config.process(self, value: 'Any') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

**Returns:** `Any`

### `raw`

```python
poetry.config.config.Config.raw(self) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `set_auth_config_source`

```python
poetry.config.config.Config.set_auth_config_source(self, config_source: 'ConfigSource') -> 'Config'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_source` | `ConfigSource` | `—` | pos/kw |

**Returns:** `Config`

### `set_config_source`

```python
poetry.config.config.Config.set_config_source(self, config_source: 'ConfigSource') -> 'Config'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_source` | `ConfigSource` | `—` | pos/kw |

**Returns:** `Config`

### `poetry.config.config.DictConfigSource` methods

### `add_property`

```python
poetry.config.config.DictConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.config.DictConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.config.DictConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `poetry.config.config.FileConfigSource` methods

### `add_property`

```python
poetry.config.config.FileConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.config.FileConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.config.FileConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `secure`

```python
poetry.config.config.FileConfigSource.secure(self) -> 'Iterator[TOMLDocument]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[TOMLDocument]`

### `poetry.config.config.PackageFilterPolicy` methods

### `allows`

```python
poetry.config.config.PackageFilterPolicy.allows(self, package_name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package_name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `has_exact_package`

```python
poetry.config.config.PackageFilterPolicy.has_exact_package(self, package_name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package_name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `is_reserved`

```python
poetry.config.config.PackageFilterPolicy.is_reserved(name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `normalize`

```python
poetry.config.config.PackageFilterPolicy.normalize(policy: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `policy` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

### `validator`

```python
poetry.config.config.PackageFilterPolicy.validator(policy: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `policy` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `poetry.config.config.TOMLFile` methods

### `exists`

```python
poetry.config.config.TOMLFile.exists(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `read`

Read the file content as a :class:`tomlkit.toml_document.TOMLDocument`.

```python
poetry.config.config.TOMLFile.read(self) -> 'TOMLDocument'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `TOMLDocument`

### `write`

Write the TOMLDocument to the file.

```python
poetry.config.config.TOMLFile.write(self, data: tomlkit.toml_document.TOMLDocument) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `TOMLDocument` | `—` | pos/kw |

### `poetry.config.config_source.ConfigSource` methods

### `add_property`

```python
poetry.config.config_source.ConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.config_source.ConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.config_source.ConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `poetry.config.config_source.ConfigSourceMigration` methods

### `apply`

```python
poetry.config.config_source.ConfigSourceMigration.apply(self, config_source: 'ConfigSource') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_source` | `ConfigSource` | `—` | pos/kw |

### `dry_run`

```python
poetry.config.config_source.ConfigSourceMigration.dry_run(self, config_source: 'ConfigSource', io: 'IO | None' = None) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_source` | `ConfigSource` | `—` | pos/kw |
| `io` | `IO \| None` | `None` | pos/kw |

**Returns:** `bool`

### `poetry.config.dict_config_source.ConfigSource` methods

### `add_property`

```python
poetry.config.dict_config_source.ConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.dict_config_source.ConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.dict_config_source.ConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `poetry.config.dict_config_source.DictConfigSource` methods

### `add_property`

```python
poetry.config.dict_config_source.DictConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.dict_config_source.DictConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.dict_config_source.DictConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `poetry.config.file_config_source.ConfigSource` methods

### `add_property`

```python
poetry.config.file_config_source.ConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.file_config_source.ConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.file_config_source.ConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `poetry.config.file_config_source.FileConfigSource` methods

### `add_property`

```python
poetry.config.file_config_source.FileConfigSource.add_property(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `get_property`

```python
poetry.config.file_config_source.FileConfigSource.get_property(self, key: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `remove_property`

```python
poetry.config.file_config_source.FileConfigSource.remove_property(self, key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `secure`

```python
poetry.config.file_config_source.FileConfigSource.secure(self) -> 'Iterator[TOMLDocument]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[TOMLDocument]`

### `poetry.config.source.Source` methods

### `to_dict`

```python
poetry.config.source.Source.to_dict(self) -> 'dict[str, str | bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, str | bool]`

### `to_toml_table`

```python
poetry.config.source.Source.to_toml_table(self) -> 'Table'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Table`

### `poetry.console.application.Application` methods

### `add`

```python
poetry.console.application.Application.add(self, command: 'Command') -> 'Command | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `Command` | `—` | pos/kw |

**Returns:** `Command | None`

### `all`

```python
poetry.console.application.Application.all(self, namespace: 'str | None' = None) -> 'dict[str, Command]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `namespace` | `str \| None` | `None` | pos/kw |

**Returns:** `dict[str, Command]`

### `are_exceptions_caught`

```python
poetry.console.application.Application.are_exceptions_caught(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `auto_exits`

```python
poetry.console.application.Application.auto_exits(self, auto_exits: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `auto_exits` | `bool` | `True` | pos/kw |

### `catch_exceptions`

```python
poetry.console.application.Application.catch_exceptions(self, catch_exceptions: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `catch_exceptions` | `bool` | `True` | pos/kw |

### `configure_env`

```python
poetry.console.application.Application.configure_env(self, event: 'Event', event_name: 'str', _: 'EventDispatcher') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `Event` | `—` | pos/kw |
| `event_name` | `str` | `—` | pos/kw |
| `_` | `EventDispatcher` | `—` | pos/kw |

### `configure_installer_for_command`

```python
poetry.console.application.Application.configure_installer_for_command(command: 'InstallerCommand', io: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `command` | `InstallerCommand` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

### `configure_installer_for_event`

```python
poetry.console.application.Application.configure_installer_for_event(event: 'Event', event_name: 'str', _: 'EventDispatcher') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `event` | `Event` | `—` | pos/kw |
| `event_name` | `str` | `—` | pos/kw |
| `_` | `EventDispatcher` | `—` | pos/kw |

### `create_io`

```python
poetry.console.application.Application.create_io(self, input: 'Input | None' = None, output: 'Output | None' = None, error_output: 'Output | None' = None) -> 'IO'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `input` | `Input \| None` | `None` | pos/kw |
| `output` | `Output \| None` | `None` | pos/kw |
| `error_output` | `Output \| None` | `None` | pos/kw |

**Returns:** `IO`

### `extract_namespace`

```python
poetry.console.application.Application.extract_namespace(self, name: 'str', limit: 'int | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |

**Returns:** `str`

### `find`

```python
poetry.console.application.Application.find(self, name: 'str') -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `Command`

### `find_namespace`

```python
poetry.console.application.Application.find_namespace(self, namespace: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `namespace` | `str` | `—` | pos/kw |

**Returns:** `str`

### `get`

```python
poetry.console.application.Application.get(self, name: 'str') -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `Command`

### `get_namespaces`

```python
poetry.console.application.Application.get_namespaces(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `has`

```python
poetry.console.application.Application.has(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `is_auto_exit_enabled`

```python
poetry.console.application.Application.is_auto_exit_enabled(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_single_command`

```python
poetry.console.application.Application.is_single_command(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `register_command_loggers`

```python
poetry.console.application.Application.register_command_loggers(self, event: 'Event', event_name: 'str', _: 'EventDispatcher') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event` | `Event` | `—` | pos/kw |
| `event_name` | `str` | `—` | pos/kw |
| `_` | `EventDispatcher` | `—` | pos/kw |

### `render_error`

```python
poetry.console.application.Application.render_error(self, error: 'Exception', io: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `error` | `Exception` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

### `reset_poetry`

```python
poetry.console.application.Application.reset_poetry(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run`

```python
poetry.console.application.Application.run(self, input: 'Input | None' = None, output: 'Output | None' = None, error_output: 'Output | None' = None) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `input` | `Input \| None` | `None` | pos/kw |
| `output` | `Output \| None` | `None` | pos/kw |
| `error_output` | `Output \| None` | `None` | pos/kw |

**Returns:** `int`

### `set_command_loader`

```python
poetry.console.application.Application.set_command_loader(self, command_loader: 'CommandLoader') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command_loader` | `CommandLoader` | `—` | pos/kw |

### `set_display_name`

```python
poetry.console.application.Application.set_display_name(self, display_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `display_name` | `str` | `—` | pos/kw |

### `set_event_dispatcher`

```python
poetry.console.application.Application.set_event_dispatcher(self, event_dispatcher: 'EventDispatcher') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `event_dispatcher` | `EventDispatcher` | `—` | pos/kw |

### `set_name`

```python
poetry.console.application.Application.set_name(self, name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `set_solution_provider_repository`

```python
poetry.console.application.Application.set_solution_provider_repository(self, solution_provider_repository: 'SolutionProviderRepository') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `solution_provider_repository` | `SolutionProviderRepository` | `—` | pos/kw |

### `set_ui`

```python
poetry.console.application.Application.set_ui(self, ui: 'UI') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ui` | `UI` | `—` | pos/kw |

### `set_version`

```python
poetry.console.application.Application.set_version(self, version: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

### `poetry.console.application.Command` methods

### `add_style`

Adds a new style

```python
poetry.console.application.Command.add_style(self, name: 'str', fg: 'str | None' = None, bg: 'str | None' = None, options: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `fg` | `str \| None` | `None` | pos/kw |
| `bg` | `str \| None` | `None` | pos/kw |
| `options` | `list[str] \| None` | `None` | pos/kw |

### `argument`

Get the value of a command argument.

```python
poetry.console.application.Command.argument(self, name: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `ask`

Prompt the user for input.

```python
poetry.console.application.Command.ask(self, question: 'str | Question', default: 'Any | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `question` | `str \| Question` | `—` | pos/kw |
| `default` | `Any \| None` | `None` | pos/kw |

**Returns:** `Any`

### `call`

Call another command.

```python
poetry.console.application.Command.call(self, name: 'str', args: 'str | None' = None) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `str \| None` | `None` | pos/kw |

**Returns:** `int`

### `call_silent`

Call another command silently.

```python
poetry.console.application.Command.call_silent(self, name: 'str', args: 'str | None' = None) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `str \| None` | `None` | pos/kw |

**Returns:** `int`

### `choice`

Give the user a single choice from an list of answers.

```python
poetry.console.application.Command.choice(self, question: 'str', choices: 'list[str]', default: 'Any | None' = None, attempts: 'int | None' = None, multiple: 'bool' = False) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `question` | `str` | `—` | pos/kw |
| `choices` | `list[str]` | `—` | pos/kw |
| `default` | `Any \| None` | `None` | pos/kw |
| `attempts` | `int \| None` | `None` | pos/kw |
| `multiple` | `bool` | `False` | pos/kw |

**Returns:** `Any`

### `comment`

Write a string as comment output.

:param text: The line to write
:type text: str

```python
poetry.console.application.Command.comment(self, text: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

### `configure`

Configures the current command.

```python
poetry.console.application.Command.configure(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `confirm`

Confirm a question with the user.

```python
poetry.console.application.Command.confirm(self, question: 'str', default: 'bool' = False, true_answer_regex: 'str' = '(?i)^y') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `question` | `str` | `—` | pos/kw |
| `default` | `bool` | `False` | pos/kw |
| `true_answer_regex` | `str` | `'(?i)^y'` | pos/kw |

**Returns:** `bool`

### `create_question`

Returns a Question of specified type.

```python
poetry.console.application.Command.create_question(self, question: 'str', type: "Literal['choice', 'confirmation'] | None" = None, **kwargs: 'Any') -> 'Question'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `question` | `str` | `—` | pos/kw |
| `type` | `Literal['choice', 'confirmation'] \| None` | `None` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Question`

### `execute`

```python
poetry.console.application.Command.execute(self, io: 'IO') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

**Returns:** `int`

### `get_application`

```python
poetry.console.application.Command.get_application(self) -> 'Application'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Application`

### `handle`

Execute the command.

```python
poetry.console.application.Command.handle(self) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `int`

### `ignore_validation_errors`

```python
poetry.console.application.Command.ignore_validation_errors(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `info`

Write a string as information output.

:param text: The line to write
:type text: str

```python
poetry.console.application.Command.info(self, text: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

### `initialize`

```python
poetry.console.application.Command.initialize(self, io: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

### `interact`

Interacts with the user.

```python
poetry.console.application.Command.interact(self, io: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

### `line`

Write a string as information output.

```python
poetry.console.application.Command.line(self, text: 'str', style: 'str | None' = None, verbosity: 'Verbosity' = <Verbosity.NORMAL: 32>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `style` | `str \| None` | `None` | pos/kw |
| `verbosity` | `Verbosity` | `<Verbosity.NORMAL: 32>` | pos/kw |

### `line_error`

Write a string as information output to stderr.

```python
poetry.console.application.Command.line_error(self, text: 'str', style: 'str | None' = None, verbosity: 'Verbosity' = <Verbosity.NORMAL: 32>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `style` | `str \| None` | `None` | pos/kw |
| `verbosity` | `Verbosity` | `<Verbosity.NORMAL: 32>` | pos/kw |

### `merge_application_definition`

```python
poetry.console.application.Command.merge_application_definition(self, merge_args: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `merge_args` | `bool` | `True` | pos/kw |

### `option`

Get the value of a command option.

```python
poetry.console.application.Command.option(self, name: 'str', default: 'Any' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Any` | `None` | pos/kw |

**Returns:** `Any`

### `overwrite`

Overwrites the current line.

It will not add a new line so use line('')
if necessary.

```python
poetry.console.application.Command.overwrite(self, text: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

### `progress_bar`

Creates a new progress bar

```python
poetry.console.application.Command.progress_bar(self, max: 'int' = 0) -> 'ProgressBar'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max` | `int` | `0` | pos/kw |

**Returns:** `ProgressBar`

### `progress_indicator`

Creates a new progress indicator.

```python
poetry.console.application.Command.progress_indicator(self, fmt: 'str | None' = None, interval: 'int' = 100, values: 'list[str] | None' = None) -> 'ProgressIndicator'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `fmt` | `str \| None` | `None` | pos/kw |
| `interval` | `int` | `100` | pos/kw |
| `values` | `list[str] \| None` | `None` | pos/kw |

**Returns:** `ProgressIndicator`

### `question`

Write a string as question output.

:param text: The line to write
:type text: str

```python
poetry.console.application.Command.question(self, text: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |

### `render_table`

Format input to textual table.

```python
poetry.console.application.Command.render_table(self, headers: 'str', rows: 'Rows', style: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `headers` | `str` | `—` | pos/kw |
| `rows` | `Rows` | `—` | pos/kw |
| `style` | `str \| None` | `None` | pos/kw |

### `reset_poetry`

```python
poetry.console.application.Command.reset_poetry(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run`

```python
poetry.console.application.Command.run(self, io: 'IO') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

**Returns:** `int`

### `secret`

Prompt the user for input but hide the answer from the console.

```python
poetry.console.application.Command.secret(self, question: 'str | Question', default: 'Any | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `question` | `str \| Question` | `—` | pos/kw |
| `default` | `Any \| None` | `None` | pos/kw |

**Returns:** `Any`

### `set_application`

```python
poetry.console.application.Command.set_application(self, application: 'Application | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `application` | `Application \| None` | `None` | pos/kw |

### `poetry.console.application.CommandLoader` methods

### `get`

Loads a command.

```python
poetry.console.application.CommandLoader.get(self, name: 'str') -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `Command`

### `has`

Checks whether a command exists or not.

```python
poetry.console.application.CommandLoader.has(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `register_factory`

```python
poetry.console.application.CommandLoader.register_factory(self, command_name: 'str', factory: 'Callable[[], Command]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command_name` | `str` | `—` | pos/kw |
| `factory` | `Callable[[], Command]` | `—` | pos/kw |

### `poetry.console.application.PoetryRuntimeError` methods

### `append`

```python
poetry.console.application.PoetryRuntimeError.append(self, message: 'str | ConsoleMessage') -> 'PoetryRuntimeError'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str \| ConsoleMessage` | `—` | pos/kw |

**Returns:** `PoetryRuntimeError`

### `create`

Create an instance of this class using the provided reason. If
an exception is provided, this is also injected as a debug
`ConsoleMessage`.

There is specific handling for known exception types. For…

```python
poetry.console.application.PoetryRuntimeError.create(reason: 'str', exception: 'CalledProcessError | Exception | None' = None, info: 'list[str] | str | None' = None) -> 'PoetryRuntimeError'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `reason` | `str` | `—` | pos/kw |
| `exception` | `CalledProcessError \| Exception \| None` | `None` | pos/kw |
| `info` | `list[str] \| str \| None` | `None` | pos/kw |

**Returns:** `PoetryRuntimeError`

### `get_text`

Convert the error messages to a formatted string. All empty messages
are ignored along with debug level messages if `debug` is `False`.

```python
poetry.console.application.PoetryRuntimeError.get_text(self, debug: 'bool' = False, indent: 'str' = '', strip: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `debug` | `bool` | `False` | pos/kw |
| `indent` | `str` | `''` | pos/kw |
| `strip` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `write`

Write the error text to the provided IO iff there is any text
to write.

```python
poetry.console.application.PoetryRuntimeError.write(self, io: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

### `poetry.console.command_loader.CommandLoader` methods

### `get`

Loads a command.

```python
poetry.console.command_loader.CommandLoader.get(self, name: 'str') -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `Command`

### `has`

Checks whether a command exists or not.

```python
poetry.console.command_loader.CommandLoader.has(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `register_factory`

```python
poetry.console.command_loader.CommandLoader.register_factory(self, command_name: 'str', factory: 'Callable[[], Command]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command_name` | `str` | `—` | pos/kw |
| `factory` | `Callable[[], Command]` | `—` | pos/kw |

### `poetry.console.exceptions.ConsoleMessage` methods

### `indent`

```python
poetry.console.exceptions.ConsoleMessage.indent(self, indent: 'str') -> 'ConsoleMessage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `indent` | `str` | `—` | pos/kw |

**Returns:** `ConsoleMessage`

### `make_section`

```python
poetry.console.exceptions.ConsoleMessage.make_section(self, title: 'str', indent: 'str' = '') -> 'ConsoleMessage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `title` | `str` | `—` | pos/kw |
| `indent` | `str` | `''` | pos/kw |

**Returns:** `ConsoleMessage`

### `wrap`

```python
poetry.console.exceptions.ConsoleMessage.wrap(self, tag: 'str') -> 'ConsoleMessage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str` | `—` | pos/kw |

**Returns:** `ConsoleMessage`

### `poetry.console.exceptions.PoetryRuntimeError` methods

### `append`

```python
poetry.console.exceptions.PoetryRuntimeError.append(self, message: 'str | ConsoleMessage') -> 'PoetryRuntimeError'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str \| ConsoleMessage` | `—` | pos/kw |

**Returns:** `PoetryRuntimeError`

### `create`

Create an instance of this class using the provided reason. If
an exception is provided, this is also injected as a debug
`ConsoleMessage`.

There is specific handling for known exception types. For…

```python
poetry.console.exceptions.PoetryRuntimeError.create(reason: 'str', exception: 'CalledProcessError | Exception | None' = None, info: 'list[str] | str | None' = None) -> 'PoetryRuntimeError'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `reason` | `str` | `—` | pos/kw |
| `exception` | `CalledProcessError \| Exception \| None` | `None` | pos/kw |
| `info` | `list[str] \| str \| None` | `None` | pos/kw |

**Returns:** `PoetryRuntimeError`

### `get_text`

Convert the error messages to a formatted string. All empty messages
are ignored along with debug level messages if `debug` is `False`.

```python
poetry.console.exceptions.PoetryRuntimeError.get_text(self, debug: 'bool' = False, indent: 'str' = '', strip: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `debug` | `bool` | `False` | pos/kw |
| `indent` | `str` | `''` | pos/kw |
| `strip` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `write`

Write the error text to the provided IO iff there is any text
to write.

```python
poetry.console.exceptions.PoetryRuntimeError.write(self, io: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `io` | `IO` | `—` | pos/kw |

### `poetry.core.factory.Dependency` methods

### `activate`

Set the dependency as mandatory.

```python
poetry.core.factory.Dependency.activate(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `allows_prereleases`

None (default): only use pre-release versions
                if no stable version satisfies the constraint
False: do not allow pre-release versions
       even if this means there is no solution
Tru…

```python
poetry.core.factory.Dependency.allows_prereleases(self) -> 'bool | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool | None`

### `clone`

```python
poetry.core.factory.Dependency.clone(self: 'T') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |

**Returns:** `T`

### `create_from_pep_508`

Resolve a PEP-508 requirement string to a `Dependency` instance. If a
`relative_to` path is specified, this is used as the base directory if the
identified dependency is of file or directory type.

```python
poetry.core.factory.Dependency.create_from_pep_508(name: 'str', relative_to: 'Path | None' = None, groups: 'Iterable[str] | None' = None) -> 'Dependency'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `relative_to` | `Path \| None` | `None` | pos/kw |
| `groups` | `Iterable[str] \| None` | `None` | pos/kw |

**Returns:** `Dependency`

### `deactivate`

Set the dependency as optional.

```python
poetry.core.factory.Dependency.deactivate(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_activated`

```python
poetry.core.factory.Dependency.is_activated(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_direct_origin`

```python
poetry.core.factory.Dependency.is_direct_origin(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_directory`

```python
poetry.core.factory.Dependency.is_directory(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_file`

```python
poetry.core.factory.Dependency.is_file(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_optional`

```python
poetry.core.factory.Dependency.is_optional(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_same_package_as`

```python
poetry.core.factory.Dependency.is_same_package_as(self, other: 'PackageSpecification') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `PackageSpecification` | `—` | pos/kw |

**Returns:** `bool`

### `is_same_source_as`

```python
poetry.core.factory.Dependency.is_same_source_as(self, other: 'PackageSpecification') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `PackageSpecification` | `—` | pos/kw |

**Returns:** `bool`

### `is_url`

```python
poetry.core.factory.Dependency.is_url(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_vcs`

```python
poetry.core.factory.Dependency.is_vcs(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `provides`

Helper method to determine if this package provides the given specification.

This determination is made to be true, if the names are the same and this
package provides all features required by the o…

```python
poetry.core.factory.Dependency.provides(self, other: 'PackageSpecification') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `PackageSpecification` | `—` | pos/kw |

**Returns:** `bool`

### `to_pep_508`

```python
poetry.core.factory.Dependency.to_pep_508(self, with_extras: 'bool' = True, *, resolved: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `with_extras` | `bool` | `True` | pos/kw |
| `resolved` | `bool` | `False` | kw |

**Returns:** `str`

### `with_constraint`

```python
poetry.core.factory.Dependency.with_constraint(self: 'T', constraint: 'str | VersionConstraint') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |
| `constraint` | `str \| VersionConstraint` | `—` | pos/kw |

**Returns:** `T`

### `with_features`

```python
poetry.core.factory.Dependency.with_features(self: 'T', features: 'Iterable[str]') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |
| `features` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `T`

### `with_groups`

```python
poetry.core.factory.Dependency.with_groups(self, groups: 'Iterable[str]') -> 'Dependency'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `groups` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Dependency`

### `without_features`

```python
poetry.core.factory.Dependency.without_features(self: 'T') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |

**Returns:** `T`

### `poetry.core.factory.DependencyGroup` methods

### `add_dependency`

```python
poetry.core.factory.DependencyGroup.add_dependency(self, dependency: 'Dependency') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dependency` | `Dependency` | `—` | pos/kw |

### `add_poetry_dependency`

```python
poetry.core.factory.DependencyGroup.add_poetry_dependency(self, dependency: 'Dependency') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dependency` | `Dependency` | `—` | pos/kw |

### `include_dependency_group`

```python
poetry.core.factory.DependencyGroup.include_dependency_group(self, dependency_group: 'DependencyGroup') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dependency_group` | `DependencyGroup` | `—` | pos/kw |

### `is_optional`

```python
poetry.core.factory.DependencyGroup.is_optional(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `remove_dependency`

```python
poetry.core.factory.DependencyGroup.remove_dependency(self, name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `poetry.core.factory.Factory` methods

### `configure_package`

```python
poetry.core.factory.Factory.configure_package(package: 'ProjectPackage', pyproject: 'PyProjectTOML', root: 'Path', with_groups: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `package` | `ProjectPackage` | `—` | pos/kw |
| `pyproject` | `PyProjectTOML` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `with_groups` | `bool` | `True` | pos/kw |

### `create_dependency`

```python
poetry.core.factory.Factory.create_dependency(name: 'str', constraint: 'DependencyConstraint', groups: 'list[str] | None' = None, root_dir: 'Path | None' = None) -> 'Dependency'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `constraint` | `DependencyConstraint` | `—` | pos/kw |
| `groups` | `list[str] \| None` | `None` | pos/kw |
| `root_dir` | `Path \| None` | `None` | pos/kw |

**Returns:** `Dependency`

### `create_poetry`

```python
poetry.core.factory.Factory.create_poetry(self, cwd: 'Path | None' = None, with_groups: 'bool' = True) -> 'Poetry'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cwd` | `Path \| None` | `None` | pos/kw |
| `with_groups` | `bool` | `True` | pos/kw |

**Returns:** `Poetry`

### `get_package`

```python
poetry.core.factory.Factory.get_package(name: 'str', version: 'str') -> 'ProjectPackage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

**Returns:** `ProjectPackage`

### `locate`

```python
poetry.core.factory.Factory.locate(cwd: 'Path | None' = None) -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cwd` | `Path \| None` | `None` | pos/kw |

**Returns:** `Path`

### `validate`

Checks the validity of a configuration

```python
poetry.core.factory.Factory.validate(toml_data: 'dict[str, Any]', strict: 'bool' = False) -> 'dict[str, list[str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `toml_data` | `dict[str, Any]` | `—` | pos/kw |
| `strict` | `bool` | `False` | pos/kw |

**Returns:** `dict[str, list[str]]`

### `poetry.core.poetry.Dependency` methods

### `activate`

Set the dependency as mandatory.

```python
poetry.core.poetry.Dependency.activate(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `allows_prereleases`

None (default): only use pre-release versions
                if no stable version satisfies the constraint
False: do not allow pre-release versions
       even if this means there is no solution
Tru…

```python
poetry.core.poetry.Dependency.allows_prereleases(self) -> 'bool | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool | None`

### `clone`

```python
poetry.core.poetry.Dependency.clone(self: 'T') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |

**Returns:** `T`


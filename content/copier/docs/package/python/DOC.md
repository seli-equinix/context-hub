---
name: package
description: "Copier Python package guide for rendering and updating project templates from local paths and Git repositories"
metadata:
  languages: "python"
  versions: "9.13.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "copier,python,scaffolding,templates,jinja,code-generation,run_copy,run_recopy,run_update,Version-Sensitive,example.com,Phase,Settings,VcsRef,deprecate_member_as_internal,load_settings,deprecate_module_as_internal,ConfigFileError,CopierAnswersInterrupt,CopierError,CopierWarning,DirtyLocalWarning,ExtensionNotFoundError,ForbiddenPathError,InteractiveSessionError,InvalidConfigFileError,InvalidTypeError,MissingFileWarning,MissingSettingsWarning,MultipleConfigFilesError,MultipleYieldTagsError,OldTemplateWarning,PathError,PathNotAbsoluteError,PathNotRelativeError,SettingsError,ShallowCloneWarning,TaskError,from_process,UnknownCopierVersionWarning,UnsafeTemplateError,UnsupportedVersionError,UserMessageError,YieldTagInFileError,printf_exception,deprecate_member"
---

# copier — package

Copier.

Docs: https://copier.readthedocs.io/

## Install

```bash
pip install copier
```

## Imports

```python
import copier
```

## Symbols (55)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Phase` | Class | The known execution phases. |
| `Settings` | Class | User settings. |
| `VcsRef` | Class | Create a collection of name/value pairs.  Example enumeration:  >>> class Color… |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `load_settings` | Function | Load settings from a YAML file.  If `settings_path` is not given, the path is d… |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `ConfigFileError` | Class | Parent class defining problems with the config file. |
| `CopierAnswersInterrupt` | Class | CopierAnswersInterrupt is raised during interactive question prompts.  It typic… |
| `CopierError` | Class | Base class for all other Copier errors. |
| `CopierWarning` | Class | Base class for all other Copier warnings. |
| `DirtyLocalWarning` | Class | Changes and untracked files present in template. |
| `ExtensionNotFoundError` | Class | Extensions listed in the configuration could not be loaded. |
| `ForbiddenPathError` | Class | The path is forbidden in the given context. |
| `InteractiveSessionError` | Class | An interactive session is required to run this program. |
| `InvalidConfigFileError` | Class | Indicates that the config file is wrong. |
| `InvalidTypeError` | Class | The question type is not among the supported ones. |
| `MissingFileWarning` | Class | I still couldn't find what I'm looking for. |
| `MissingSettingsWarning` | Class | Settings path has been defined but file is missing. |
| `MultipleConfigFilesError` | Class | Both copier.yml and copier.yaml found, and that's an error. |
| `MultipleYieldTagsError` | Class | Multiple yield tags are used in one path name, but it is not allowed. |
| `OldTemplateWarning` | Class | Template was designed for an older Copier version. |
| `PathError` | Class | The path is invalid in the given context. |
| `PathNotAbsoluteError` | Class | The path is not absolute, but it should be. |
| `PathNotRelativeError` | Class | The path is not relative, but it should be. |
| `SettingsError` | Class | Exception raised when the settings are invalid. |
| `ShallowCloneWarning` | Class | The template repository is a shallow clone. |
| `TaskError` | Class | Exception raised when a task fails. |
| `from_process` | Method | Create a TaskError from a CompletedProcess. |
| `UnknownCopierVersionWarning` | Class | Cannot determine installed Copier version. |
| `UnsafeTemplateError` | Class | Unsafe Copier template features are used without explicit consent. |
| `UnsupportedVersionError` | Class | Copier version does not support template version. |
| `UserMessageError` | Class | Exit the program giving a message to the user. |
| `YieldTagInFileError` | Class | A yield tag is used in the file content, but it is not allowed. |
| `printf_exception` | Function | Print exception with common format. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member` | Function | Deprecate a module member with a new import statement with a warning.  Args:… |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member` | Function | Deprecate a module member with a new import statement with a warning.  Args:… |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |
| `deprecate_member_as_internal` | Function | Deprecate a module member as internal with a warning.  Args:     member: The mo… |
| `deprecate_module_as_internal` | Function | Deprecate a module as internal with a warning.  Args:     name: The module name. |

## Classes

### `Phase`

The known execution phases.

```python
copier.Phase(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Settings`

User settings.

```python
copier.Settings(self, defaults: 'Mapping[str, Any]' = <factory>, trust: 'Sequence[str]' = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `defaults` | `Mapping[str, Any]` | `<factory>` | pos/kw |
| `trust` | `Sequence[str]` | `<factory>` | pos/kw |

### `VcsRef`

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
copier.VcsRef(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `ConfigFileError`

Parent class defining problems with the config file.

```python
copier.errors.ConfigFileError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CopierAnswersInterrupt`

CopierAnswersInterrupt is raised during interactive question prompts.

It typically follows a KeyboardInterrupt (i.e. ctrl-c) and provides an
opportunity for the caller to conduct additional cleanup,…

```python
copier.errors.CopierAnswersInterrupt(self, answers: 'AnswersMap', last_question: 'Question', template: 'Template') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `answers` | `AnswersMap` | `—` | pos/kw |
| `last_question` | `Question` | `—` | pos/kw |
| `template` | `Template` | `—` | pos/kw |

### `CopierError`

Base class for all other Copier errors.

```python
copier.errors.CopierError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CopierWarning`

Base class for all other Copier warnings.

```python
copier.errors.CopierWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DirtyLocalWarning`

Changes and untracked files present in template.

```python
copier.errors.DirtyLocalWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ExtensionNotFoundError`

Extensions listed in the configuration could not be loaded.

```python
copier.errors.ExtensionNotFoundError(self, message: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `ForbiddenPathError`

The path is forbidden in the given context.

```python
copier.errors.ForbiddenPathError(self, *, path: 'Path', hint: 'str' = '') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | kw |
| `hint` | `str` | `''` | kw |

### `InteractiveSessionError`

An interactive session is required to run this program.

```python
copier.errors.InteractiveSessionError(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `InvalidConfigFileError`

Indicates that the config file is wrong.

```python
copier.errors.InvalidConfigFileError(self, conf_path: 'Path', quiet: 'bool')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf_path` | `Path` | `—` | pos/kw |
| `quiet` | `bool` | `—` | pos/kw |

### `InvalidTypeError`

The question type is not among the supported ones.

```python
copier.errors.InvalidTypeError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MissingFileWarning`

I still couldn't find what I'm looking for.

```python
copier.errors.MissingFileWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MissingSettingsWarning`

Settings path has been defined but file is missing.

```python
copier.errors.MissingSettingsWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MultipleConfigFilesError`

Both copier.yml and copier.yaml found, and that's an error.

```python
copier.errors.MultipleConfigFilesError(self, conf_paths: 'PathSeq')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conf_paths` | `PathSeq` | `—` | pos/kw |

### `MultipleYieldTagsError`

Multiple yield tags are used in one path name, but it is not allowed.

```python
copier.errors.MultipleYieldTagsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OldTemplateWarning`

Template was designed for an older Copier version.

```python
copier.errors.OldTemplateWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PathError`

The path is invalid in the given context.

```python
copier.errors.PathError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PathNotAbsoluteError`

The path is not absolute, but it should be.

```python
copier.errors.PathNotAbsoluteError(self, *, path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | kw |

### `PathNotRelativeError`

The path is not relative, but it should be.

```python
copier.errors.PathNotRelativeError(self, *, path: 'Path') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | kw |

### `SettingsError`

Exception raised when the settings are invalid.

```python
copier.errors.SettingsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ShallowCloneWarning`

The template repository is a shallow clone.

```python
copier.errors.ShallowCloneWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TaskError`

Exception raised when a task fails.

```python
copier.errors.TaskError(self, command: 'str | Sequence[str]', returncode: 'int', stdout: 'str | bytes | None', stderr: 'str | bytes | None')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `command` | `str \| Sequence[str]` | `—` | pos/kw |
| `returncode` | `int` | `—` | pos/kw |
| `stdout` | `str \| bytes \| None` | `—` | pos/kw |
| `stderr` | `str \| bytes \| None` | `—` | pos/kw |

### `UnknownCopierVersionWarning`

Cannot determine installed Copier version.

```python
copier.errors.UnknownCopierVersionWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnsafeTemplateError`

Unsafe Copier template features are used without explicit consent.

```python
copier.errors.UnsafeTemplateError(self, features: 'Sequence[str]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `features` | `Sequence[str]` | `—` | pos/kw |

### `UnsupportedVersionError`

Copier version does not support template version.

```python
copier.errors.UnsupportedVersionError(self, message: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `UserMessageError`

Exit the program giving a message to the user.

```python
copier.errors.UserMessageError(self, message: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `YieldTagInFileError`

A yield tag is used in the file content, but it is not allowed.

```python
copier.errors.YieldTagInFileError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

## Functions

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `load_settings`

Load settings from a YAML file.

If `settings_path` is not given, the path is determined from the
`COPIER_SETTINGS_PATH` environment variable or the platform-specific
default configuration directory.…

```python
copier.load_settings(settings_path: 'Path | None' = None) -> 'Settings'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings_path` | `Path \| None` | `None` | pos/kw |

**Returns:** `Settings`

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.cli.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.cli.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `printf_exception`

Print exception with common format.

```python
copier.errors.printf_exception(e: 'Exception', action: 'str', msg: 'str' = '', indent: 'int' = 0, quiet: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `e` | `Exception` | `—` | pos/kw |
| `action` | `str` | `—` | pos/kw |
| `msg` | `str` | `''` | pos/kw |
| `indent` | `int` | `0` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.jinja_ext.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.jinja_ext.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member`

Deprecate a module member with a new import statement with a warning.

Args:
    member: The module member name.
    module: The module name.
    new_import: The new import statement.

```python
copier.main.deprecate_member(member: 'str', module: 'str', new_import: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |
| `new_import` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.main.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.main.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member`

Deprecate a module member with a new import statement with a warning.

Args:
    member: The module member name.
    module: The module name.
    new_import: The new import statement.

```python
copier.settings.deprecate_member(member: 'str', module: 'str', new_import: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |
| `new_import` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.settings.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.settings.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.subproject.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.subproject.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.template.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.template.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.tools.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.tools.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.types.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.types.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.user_data.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.user_data.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `deprecate_member_as_internal`

Deprecate a module member as internal with a warning.

Args:
    member: The module member name.
    module: The module name.

```python
copier.vcs.deprecate_member_as_internal(member: 'str', module: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `member` | `str` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

### `deprecate_module_as_internal`

Deprecate a module as internal with a warning.

Args:
    name: The module name.

```python
copier.vcs.deprecate_module_as_internal(name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

## Methods

### `copier.errors.TaskError` methods

### `from_process`

Create a TaskError from a CompletedProcess.

```python
copier.errors.TaskError.from_process(process: 'CompletedProcess[str] | CompletedProcess[bytes]') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `process` | `CompletedProcess[str] \| CompletedProcess[bytes]` | `—` | pos/kw |

**Returns:** `Self`


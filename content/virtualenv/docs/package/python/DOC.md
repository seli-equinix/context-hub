---
name: package
description: "virtualenv package guide for creating isolated Python environments with the official virtualenv docs"
metadata:
  languages: "python"
  versions: "21.2.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "virtualenv,python,packaging,environments,venv,pip,cli_run,session_via_cli,BASH_SOURCE,Set-ExecutionPolicy,Version-Sensitive,BashActivator,add_parser_arguments,as_name,generate,instantiate_template,quote,replacements,supports,templates,BatchActivator,CShellActivator,FishActivator,NushellActivator,PowerShellActivator,PythonActivator,XonshActivator,Activator,ViaTemplateActivator"
---

# virtualenv — package

## Install

```bash
pip install virtualenv
```

## Imports

```python
import virtualenv
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `cli_run` | Function | Create a virtual environment given some command line interface arguments.  :par… |
| `session_via_cli` | Function | Create a virtualenv session (same as cli_run, but this does not perform the cre… |
| `BashActivator` | Class | Generates activate script for the virtual environment. |
| `add_parser_arguments` | Method | Add CLI arguments for this activation script.  :param parser: the CLI parser :p… |
| `as_name` | Method |  |
| `generate` | Method | Generate activate script for the given creator.  :param creator: the creator (b… |
| `instantiate_template` | Method |  |
| `quote` | Method | Quote strings in the activation script.  :param string: the string to quote  :r… |
| `replacements` | Method |  |
| `supports` | Method | Check if the activation script is supported in the given interpreter.  :param i… |
| `templates` | Method |  |
| `BatchActivator` | Class | Generates activate script for the virtual environment. |
| `add_parser_arguments` | Method | Add CLI arguments for this activation script.  :param parser: the CLI parser :p… |
| `as_name` | Method |  |
| `generate` | Method | Generate activate script for the given creator.  :param creator: the creator (b… |
| `instantiate_template` | Method |  |
| `quote` | Method | Quote strings in the activation script.  :param string: the string to quote  :r… |
| `replacements` | Method |  |
| `supports` | Method | Check if the activation script is supported in the given interpreter.  :param i… |
| `templates` | Method |  |
| `CShellActivator` | Class | Generates activate script for the virtual environment. |
| `add_parser_arguments` | Method | Add CLI arguments for this activation script.  :param parser: the CLI parser :p… |
| `as_name` | Method |  |
| `generate` | Method | Generate activate script for the given creator.  :param creator: the creator (b… |
| `instantiate_template` | Method |  |
| `quote` | Method | Quote strings in the activation script.  :param string: the string to quote  :r… |
| `replacements` | Method |  |
| `supports` | Method | Check if the activation script is supported in the given interpreter.  :param i… |
| `templates` | Method |  |
| `FishActivator` | Class | Generates activate script for the virtual environment. |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `BashActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.BashActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `BatchActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.BatchActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `CShellActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.CShellActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `FishActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.FishActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `NushellActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.NushellActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `PowerShellActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.PowerShellActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `PythonActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.PythonActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `XonshActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.XonshActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `Activator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.activator.Activator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `BashActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.bash.BashActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.bash.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `BatchActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.batch.BatchActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.batch.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `CShellActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.cshell.CShellActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.cshell.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `FishActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.fish.FishActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.fish.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `NushellActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.nushell.NushellActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.nushell.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `PowerShellActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.powershell.PowerShellActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.powershell.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `PythonActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.python.PythonActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

### `ViaTemplateActivator`

Generates activate script for the virtual environment.

```python
virtualenv.activation.python.ViaTemplateActivator(self, options: 'VirtualEnvOptions') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `VirtualEnvOptions` | `—` | pos/kw |

## Functions

### `cli_run`

Create a virtual environment given some command line interface arguments.

:param args: the command line arguments
:param options: passing in a ``VirtualEnvOptions`` object allows return of the parse…

```python
virtualenv.cli_run(args: 'list[str]', options: 'VirtualEnvOptions | None' = None, setup_logging: 'bool' = True, env: 'MutableMapping[str, str] | None' = None) -> 'Session'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `list[str]` | `—` | pos/kw |
| `options` | `VirtualEnvOptions \| None` | `None` | pos/kw |
| `setup_logging` | `bool` | `True` | pos/kw |
| `env` | `MutableMapping[str, str] \| None` | `None` | pos/kw |

**Returns:** `Session`

### `session_via_cli`

Create a virtualenv session (same as cli_run, but this does not perform the creation). Use this if you just want to query what the virtual environment would look like, but not actually create it.

:p…

```python
virtualenv.session_via_cli(args: 'list[str]', options: 'VirtualEnvOptions | None' = None, setup_logging: 'bool' = True, env: 'MutableMapping[str, str] | None' = None) -> 'Session'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `list[str]` | `—` | pos/kw |
| `options` | `VirtualEnvOptions \| None` | `None` | pos/kw |
| `setup_logging` | `bool` | `True` | pos/kw |
| `env` | `MutableMapping[str, str] \| None` | `None` | pos/kw |

**Returns:** `Session`

## Methods

### `virtualenv.activation.BashActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.BashActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.BashActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.BashActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.BashActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.BashActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.BashActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.BashActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.BashActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.BatchActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.BatchActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.BatchActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.BatchActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.BatchActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.BatchActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.BatchActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.BatchActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.BatchActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.CShellActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.CShellActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.CShellActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.CShellActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.CShellActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.CShellActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.CShellActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.CShellActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.CShellActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.FishActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.FishActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.FishActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.FishActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.FishActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.FishActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.FishActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.FishActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.FishActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.NushellActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.NushellActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.NushellActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.NushellActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.NushellActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Nushell supports raw strings like: r###'this is a string'###.

https://github.com/nushell/nushell.github.io/blob/main/book/working_with_strings.md

This method finds the maximum continuous sharps in…

```python
virtualenv.activation.NushellActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.NushellActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.NushellActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.NushellActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.PowerShellActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.PowerShellActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.PowerShellActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.PowerShellActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.PowerShellActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

This should satisfy PowerShell quoting rules [1], unless the quoted string is passed directly to Windows native commands [2].

[1]: https://learn.microsoft.com/en-us/powershell/module/microsoft.power…

```python
virtualenv.activation.PowerShellActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.PowerShellActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.PowerShellActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.PowerShellActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.PythonActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.PythonActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.PythonActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.PythonActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.PythonActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.PythonActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.PythonActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.PythonActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.PythonActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.XonshActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.XonshActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.XonshActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.XonshActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.XonshActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote as a Python literal — xonsh parses the activation script as Python.

```python
virtualenv.activation.XonshActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.XonshActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.XonshActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.XonshActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.activator.Activator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.activator.Activator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.activator.Activator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.activator.Activator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `virtualenv.activation.bash.BashActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.bash.BashActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.bash.BashActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.bash.BashActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.bash.BashActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.bash.BashActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.bash.BashActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.bash.BashActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.bash.BashActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.bash.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.bash.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.bash.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.bash.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.bash.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.bash.ViaTemplateActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.bash.ViaTemplateActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.bash.ViaTemplateActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.bash.ViaTemplateActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.batch.BatchActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.batch.BatchActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.batch.BatchActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.batch.BatchActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.batch.BatchActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.batch.BatchActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.batch.BatchActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.batch.BatchActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.batch.BatchActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.batch.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.batch.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.batch.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.batch.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.batch.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.batch.ViaTemplateActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.batch.ViaTemplateActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.batch.ViaTemplateActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.batch.ViaTemplateActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.cshell.CShellActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.cshell.CShellActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.cshell.CShellActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.cshell.CShellActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.cshell.CShellActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.cshell.CShellActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.cshell.CShellActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.cshell.CShellActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.cshell.CShellActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.cshell.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.cshell.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.cshell.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.cshell.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.cshell.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.cshell.ViaTemplateActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.cshell.ViaTemplateActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.cshell.ViaTemplateActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.cshell.ViaTemplateActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.fish.FishActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.fish.FishActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.fish.FishActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.fish.FishActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.fish.FishActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.fish.FishActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.fish.FishActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.fish.FishActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.fish.FishActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.fish.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.fish.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.fish.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.fish.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.fish.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.fish.ViaTemplateActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.fish.ViaTemplateActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.fish.ViaTemplateActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.fish.ViaTemplateActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.nushell.NushellActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.nushell.NushellActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.nushell.NushellActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.nushell.NushellActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.nushell.NushellActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Nushell supports raw strings like: r###'this is a string'###.

https://github.com/nushell/nushell.github.io/blob/main/book/working_with_strings.md

This method finds the maximum continuous sharps in…

```python
virtualenv.activation.nushell.NushellActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.nushell.NushellActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.nushell.NushellActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.nushell.NushellActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.nushell.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.nushell.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.nushell.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.nushell.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.nushell.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.nushell.ViaTemplateActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.nushell.ViaTemplateActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.nushell.ViaTemplateActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.nushell.ViaTemplateActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.powershell.PowerShellActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.powershell.PowerShellActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.powershell.PowerShellActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.powershell.PowerShellActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.powershell.PowerShellActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

This should satisfy PowerShell quoting rules [1], unless the quoted string is passed directly to Windows native commands [2].

[1]: https://learn.microsoft.com/en-us/powershell/module/microsoft.power…

```python
virtualenv.activation.powershell.PowerShellActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.powershell.PowerShellActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.powershell.PowerShellActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.powershell.PowerShellActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.powershell.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.powershell.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.powershell.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.powershell.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.powershell.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.powershell.ViaTemplateActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.powershell.ViaTemplateActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.powershell.ViaTemplateActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.powershell.ViaTemplateActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.python.PythonActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.python.PythonActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.python.PythonActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.python.PythonActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.python.PythonActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`

### `quote`

Quote strings in the activation script.

:param string: the string to quote

:returns: quoted string that works in the activation script

```python
virtualenv.activation.python.PythonActivator.quote(string: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `str` | `—` | pos/kw |

**Returns:** `str`

### `replacements`

```python
virtualenv.activation.python.PythonActivator.replacements(self, creator: 'Creator', dest_folder: 'Path') -> 'dict[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |
| `dest_folder` | `Path` | `—` | pos/kw |

**Returns:** `dict[str, str]`

### `supports`

Check if the activation script is supported in the given interpreter.

:param interpreter: the interpreter we need to support

:returns: ``True`` if supported, ``False`` otherwise

```python
virtualenv.activation.python.PythonActivator.supports(interpreter: 'PythonInfo') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interpreter` | `PythonInfo` | `—` | pos/kw |

**Returns:** `bool`

### `templates`

```python
virtualenv.activation.python.PythonActivator.templates(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `virtualenv.activation.python.ViaTemplateActivator` methods

### `add_parser_arguments`

Add CLI arguments for this activation script.

:param parser: the CLI parser
:param interpreter: the interpreter this virtual environment is based of

```python
virtualenv.activation.python.ViaTemplateActivator.add_parser_arguments(parser: 'ArgumentParser', interpreter: 'PythonInfo') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |
| `interpreter` | `PythonInfo` | `—` | pos/kw |

### `as_name`

```python
virtualenv.activation.python.ViaTemplateActivator.as_name(self, template: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `str`

### `generate`

Generate activate script for the given creator.

:param creator: the creator (based of :class:`virtualenv.create.creator.Creator`) we used to create this virtual
    environment

```python
virtualenv.activation.python.ViaTemplateActivator.generate(self, creator: 'Creator') -> 'list[Path]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `list[Path]`

### `instantiate_template`

```python
virtualenv.activation.python.ViaTemplateActivator.instantiate_template(self, replacements: 'dict[str, str]', template: 'str', creator: 'Creator') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replacements` | `dict[str, str]` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `creator` | `Creator` | `—` | pos/kw |

**Returns:** `str`


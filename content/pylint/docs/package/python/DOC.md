---
name: package
description: "Pylint 4.0.5 package guide for Python linting, config setup, CI integration, and common false-positive traps"
metadata:
  languages: "python"
  versions: "4.0.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pylint,python,linting,static-analysis,quality,ci,Version-Sensitive,modify_sys_path,run_pylint,run_pyreverse,run_symilar,BaseChecker,add_message,check_consistency,close,create_message_definition_from_tuple,get_full_documentation,get_map_data,open,reduce_map_data,BaseRawFileChecker,process_module,BaseTokenChecker,process_tokens,DeprecatedMixin,check_deprecated_attribute,check_deprecated_class,check_deprecated_class_in_call,check_deprecated_method,check_deprecated_module,deprecated_arguments,deprecated_attributes,deprecated_classes,deprecated_decorators,deprecated_methods,deprecated_modules,visit_attribute,visit_call,visit_decorators,visit_import,visit_importfrom,LinterStats,get_bad_names,get_code_count,get_global_message_count,get_module_message_count,get_node_count,get_undocumented,increase_bad_name,increase_single_message_count,increase_single_module_message_count,init_single_module,reset_bad_names,reset_code_count,reset_duplicated_lines,reset_message_count,reset_node_count,reset_undocumented,diff_string,initialize,register_plugins,table_lines_from_stats,AsyncChecker,visit_asyncfunctiondef,visit_asyncwith,decorated_with,register,BadChainedComparisonChecker,visit_compare,AnyStyle,get_regex,BasicChecker,leave_try,visit_assert,visit_assign,visit_break,visit_classdef,visit_comprehension,visit_continue,visit_dict,visit_expr,visit_for,visit_functiondef,visit_if,visit_ifexp,visit_lambda,visit_module,visit_raise,visit_return,visit_set,visit_try,visit_with,BasicErrorChecker,visit_nonlocal,visit_starred,visit_unaryop,visit_while,visit_yield,visit_yieldfrom,CamelCaseStyle,ComparisonChecker,DocStringChecker,FunctionChecker"
---

# pylint — package

## Install

```bash
pip install pylint
```

## Imports

```python
import pylint
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `modify_sys_path` | Function | Modify sys path for execution as Python module.  Strip out the current working… |
| `run_pylint` | Function | Run pylint.  argv can be a sequence of strings normally supplied as arguments o… |
| `run_pyreverse` | Function | Run pyreverse.  argv can be a sequence of strings normally supplied as argument… |
| `run_symilar` | Function | Run symilar.  argv can be a sequence of strings normally supplied as arguments… |
| `BaseChecker` | Class | Base class for classes that provide arguments. |
| `add_message` | Method |  |
| `check_consistency` | Method | Check the consistency of msgid.  msg ids for a checker should be a string of le… |
| `close` | Method | Called after visiting project (i.e set of modules). |
| `create_message_definition_from_tuple` | Method |  |
| `get_full_documentation` | Method |  |
| `get_map_data` | Method |  |
| `open` | Method | Called before visiting project (i.e. set of modules). |
| `reduce_map_data` | Method |  |
| `BaseRawFileChecker` | Class | Base class for checkers which need to parse the raw file. |
| `add_message` | Method |  |
| `check_consistency` | Method | Check the consistency of msgid.  msg ids for a checker should be a string of le… |
| `close` | Method | Called after visiting project (i.e set of modules). |
| `create_message_definition_from_tuple` | Method |  |
| `get_full_documentation` | Method |  |
| `get_map_data` | Method |  |
| `open` | Method | Called before visiting project (i.e. set of modules). |
| `process_module` | Method | Process a module.  The module's content is accessible via ``astroid.stream`` |
| `reduce_map_data` | Method |  |
| `BaseTokenChecker` | Class | Base class for checkers that want to have access to the token stream. |
| `add_message` | Method |  |
| `check_consistency` | Method | Check the consistency of msgid.  msg ids for a checker should be a string of le… |
| `close` | Method | Called after visiting project (i.e set of modules). |
| `create_message_definition_from_tuple` | Method |  |
| `get_full_documentation` | Method |  |
| `get_map_data` | Method |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `BaseChecker`

Base class for classes that provide arguments.

```python
pylint.checkers.BaseChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `BaseRawFileChecker`

Base class for checkers which need to parse the raw file.

```python
pylint.checkers.BaseRawFileChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `BaseTokenChecker`

Base class for checkers that want to have access to the token stream.

```python
pylint.checkers.BaseTokenChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `DeprecatedMixin`

A mixin implementing logic for checking deprecated symbols.

A class implementing mixin must define "deprecated-method" Message.

```python
pylint.checkers.DeprecatedMixin(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `LinterStats`

Class used to linter stats.

```python
pylint.checkers.LinterStats(self, bad_names: 'BadNames | None' = None, by_module: 'dict[str, ModuleStats] | None' = None, by_msg: 'dict[str, int] | None' = None, code_type_count: 'CodeTypeCount | None' = None, dependencies: 'dict[str, set[str]] | None' = None, duplicated_lines: 'DuplicatedLines | None' = None, node_count: 'NodeCount | None' = None, undocumented: 'UndocumentedNodes | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `bad_names` | `BadNames \| None` | `None` | pos/kw |
| `by_module` | `dict[str, ModuleStats] \| None` | `None` | pos/kw |
| `by_msg` | `dict[str, int] \| None` | `None` | pos/kw |
| `code_type_count` | `CodeTypeCount \| None` | `None` | pos/kw |
| `dependencies` | `dict[str, set[str]] \| None` | `None` | pos/kw |
| `duplicated_lines` | `DuplicatedLines \| None` | `None` | pos/kw |
| `node_count` | `NodeCount \| None` | `None` | pos/kw |
| `undocumented` | `UndocumentedNodes \| None` | `None` | pos/kw |

### `AsyncChecker`

Base class for classes that provide arguments.

```python
pylint.checkers.async_checker.AsyncChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `BadChainedComparisonChecker`

Checks for unintentional usage of chained comparison.

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `BaseChecker`

Base class for classes that provide arguments.

```python
pylint.checkers.bad_chained_comparison.BaseChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `AnyStyle`

Class to register all accepted forms of a single naming style.

It may seem counter-intuitive that single naming style has multiple "accepted"
forms of regular expressions, but we need to special-cas…

```python
pylint.checkers.base.AnyStyle(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BasicChecker`

Basic checker.

Checks for :
* doc strings
* number of arguments, local variables, branches, returns and statements in
functions, methods
* required module attributes
* dangerous default values as ar…

```python
pylint.checkers.base.BasicChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `BasicErrorChecker`

Permits separating multiple checks with the same checker name into
classes/file.

```python
pylint.checkers.base.BasicErrorChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `CamelCaseStyle`

Regex rules for camelCase naming style.

```python
pylint.checkers.base.CamelCaseStyle(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ComparisonChecker`

Checks for comparisons.

- singleton comparison: 'expr == True', 'expr == False' and 'expr == None'
- yoda condition: 'const "comp" right' where comp can be '==', '!=', '<',
  '<=', '>' or '>=', and…

```python
pylint.checkers.base.ComparisonChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `DocStringChecker`

Permits separating multiple checks with the same checker name into
classes/file.

```python
pylint.checkers.base.DocStringChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `FunctionChecker`

Check if a function definition handles possible side effects.

```python
pylint.checkers.base.FunctionChecker(self, linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

## Functions

### `modify_sys_path`

Modify sys path for execution as Python module.

Strip out the current working directory from sys.path.
Having the working directory in `sys.path` means that `pylint` might
inadvertently import user…

```python
pylint.modify_sys_path() -> 'None'
```

### `run_pylint`

Run pylint.

argv can be a sequence of strings normally supplied as arguments on the command line

```python
pylint.run_pylint(argv: 'Sequence[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `Sequence[str] \| None` | `None` | pos/kw |

### `run_pyreverse`

Run pyreverse.

argv can be a sequence of strings normally supplied as arguments on the command line

```python
pylint.run_pyreverse(argv: 'Sequence[str] | None' = None) -> 'NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `Sequence[str] \| None` | `None` | pos/kw |

**Returns:** `NoReturn`

### `run_symilar`

Run symilar.

argv can be a sequence of strings normally supplied as arguments on the command line

```python
pylint.run_symilar(argv: 'Sequence[str] | None' = None) -> 'NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `Sequence[str] \| None` | `None` | pos/kw |

**Returns:** `NoReturn`

### `diff_string`

Given an old and new value, return a string representing the difference.

```python
pylint.checkers.diff_string(old: 'float', new: 'float') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old` | `float` | `—` | pos/kw |
| `new` | `float` | `—` | pos/kw |

**Returns:** `str`

### `initialize`

Initialize linter with checkers in this package.

```python
pylint.checkers.initialize(linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `register_plugins`

Load all module and package in the given directory, looking for a
'register' function in each one, used to register pylint checkers.

```python
pylint.checkers.register_plugins(linter: 'PyLinter', directory: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |
| `directory` | `str` | `—` | pos/kw |

### `table_lines_from_stats`

Get values listed in <columns> from <stats> and <old_stats>,
and return a formatted list of values.

The return value is designed to be given to a ureport.Table object

```python
pylint.checkers.table_lines_from_stats(stats: 'LinterStats', old_stats: 'LinterStats | None', stat_type: "Literal['duplicated_lines', 'message_types']") -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stats` | `LinterStats` | `—` | pos/kw |
| `old_stats` | `LinterStats \| None` | `—` | pos/kw |
| `stat_type` | `Literal['duplicated_lines', 'message_types']` | `—` | pos/kw |

**Returns:** `list[str]`

### `decorated_with`

Determine if the `func` node has a decorator with the qualified name `qname`.

```python
pylint.checkers.async_checker.decorated_with(func: 'nodes.ClassDef | nodes.FunctionDef | astroid.BoundMethod | astroid.UnboundMethod', qnames: 'Iterable[str]') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `nodes.ClassDef \| nodes.FunctionDef \| astroid.BoundMethod \| astroid.UnboundMethod` | `—` | pos/kw |
| `qnames` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `bool`

### `register`

```python
pylint.checkers.async_checker.register(linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

### `register`

```python
pylint.checkers.bad_chained_comparison.register(linter: 'PyLinter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `linter` | `PyLinter` | `—` | pos/kw |

## Methods

### `pylint.checkers.BaseChecker` methods

### `add_message`

```python
pylint.checkers.BaseChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.BaseChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.BaseChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.BaseChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.BaseChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.BaseChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.BaseChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.BaseChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `pylint.checkers.BaseRawFileChecker` methods

### `add_message`

```python
pylint.checkers.BaseRawFileChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.BaseRawFileChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.BaseRawFileChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.BaseRawFileChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.BaseRawFileChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.BaseRawFileChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.BaseRawFileChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_module`

Process a module.

The module's content is accessible via ``astroid.stream``

```python
pylint.checkers.BaseRawFileChecker.process_module(self, node: 'nodes.Module') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Module` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.BaseRawFileChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `pylint.checkers.BaseTokenChecker` methods

### `add_message`

```python
pylint.checkers.BaseTokenChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.BaseTokenChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.BaseTokenChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.BaseTokenChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.BaseTokenChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.BaseTokenChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.BaseTokenChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_tokens`

Should be overridden by subclasses.

```python
pylint.checkers.BaseTokenChecker.process_tokens(self, tokens: 'list[TokenInfo]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tokens` | `list[TokenInfo]` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.BaseTokenChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `pylint.checkers.DeprecatedMixin` methods

### `add_message`

```python
pylint.checkers.DeprecatedMixin.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.DeprecatedMixin.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_deprecated_attribute`

Checks if the attribute is deprecated.

```python
pylint.checkers.DeprecatedMixin.check_deprecated_attribute(self, node: 'nodes.Attribute') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Attribute` | `—` | pos/kw |

### `check_deprecated_class`

Checks if the class is deprecated.

```python
pylint.checkers.DeprecatedMixin.check_deprecated_class(self, node: 'nodes.NodeNG', mod_name: 'str', class_names: 'Iterable[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.NodeNG` | `—` | pos/kw |
| `mod_name` | `str` | `—` | pos/kw |
| `class_names` | `Iterable[str]` | `—` | pos/kw |

### `check_deprecated_class_in_call`

Checks if call the deprecated class.

```python
pylint.checkers.DeprecatedMixin.check_deprecated_class_in_call(self, node: 'nodes.Call') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Call` | `—` | pos/kw |

### `check_deprecated_method`

Executes the checker for the given node.

This method should be called from the checker implementing this mixin.

```python
pylint.checkers.DeprecatedMixin.check_deprecated_method(self, node: 'nodes.Call', inferred: 'nodes.NodeNG') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Call` | `—` | pos/kw |
| `inferred` | `nodes.NodeNG` | `—` | pos/kw |

### `check_deprecated_module`

Checks if the module is deprecated.

```python
pylint.checkers.DeprecatedMixin.check_deprecated_module(self, node: 'nodes.Import', mod_path: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Import` | `—` | pos/kw |
| `mod_path` | `str \| None` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.DeprecatedMixin.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.DeprecatedMixin.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `deprecated_arguments`

Callback returning the deprecated arguments of method/function.

Args:
    method (str): name of function/method checked for deprecated arguments

Returns:
    collections.abc.Iterable in form:…

```python
pylint.checkers.DeprecatedMixin.deprecated_arguments(self, method: 'str') -> 'Iterable[tuple[int | None, str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `method` | `str` | `—` | pos/kw |

**Returns:** `Iterable[tuple[int | None, str]]`

### `deprecated_attributes`

Callback returning the deprecated attributes.

```python
pylint.checkers.DeprecatedMixin.deprecated_attributes(self) -> 'Iterable[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterable[str]`

### `deprecated_classes`

Callback returning the deprecated classes of module.

Args:
    module (str): name of module checked for deprecated classes

Returns:
    collections.abc.Container of deprecated class names.

```python
pylint.checkers.DeprecatedMixin.deprecated_classes(self, module: 'str') -> 'Iterable[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module` | `str` | `—` | pos/kw |

**Returns:** `Iterable[str]`

### `deprecated_decorators`

Callback returning the deprecated decorators.

Returns:
    collections.abc.Container of deprecated decorator names.

```python
pylint.checkers.DeprecatedMixin.deprecated_decorators(self) -> 'Iterable[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterable[str]`

### `deprecated_methods`

Callback returning the deprecated methods/functions.

Returns:
    collections.abc.Container of deprecated function/method names.

```python
pylint.checkers.DeprecatedMixin.deprecated_methods(self) -> 'Container[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Container[str]`

### `deprecated_modules`

Callback returning the deprecated modules.

Returns:
    collections.abc.Container of deprecated module names.

```python
pylint.checkers.DeprecatedMixin.deprecated_modules(self) -> 'Iterable[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterable[str]`

### `get_full_documentation`

```python
pylint.checkers.DeprecatedMixin.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.DeprecatedMixin.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.DeprecatedMixin.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.DeprecatedMixin.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_attribute`

Called when an `Attribute` node is visited.

```python
pylint.checkers.DeprecatedMixin.visit_attribute(self, node: 'nodes.Attribute') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Attribute` | `—` | pos/kw |

### `visit_call`

Called when a :class:`nodes.Call` node is visited.

```python
pylint.checkers.DeprecatedMixin.visit_call(self, node: 'nodes.Call') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Call` | `—` | pos/kw |

### `visit_decorators`

Triggered when a decorator statement is seen.

```python
pylint.checkers.DeprecatedMixin.visit_decorators(self, node: 'nodes.Decorators') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Decorators` | `—` | pos/kw |

### `visit_import`

Triggered when an import statement is seen.

```python
pylint.checkers.DeprecatedMixin.visit_import(self, node: 'nodes.Import') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Import` | `—` | pos/kw |

### `visit_importfrom`

Triggered when a from statement is seen.

```python
pylint.checkers.DeprecatedMixin.visit_importfrom(self, node: 'nodes.ImportFrom') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.ImportFrom` | `—` | pos/kw |

### `pylint.checkers.LinterStats` methods

### `get_bad_names`

Get a bad names node count.

```python
pylint.checkers.LinterStats.get_bad_names(self, node_name: "Literal['argument', 'attr', 'class', 'class_attribute', 'class_const', 'const', 'inlinevar', 'function', 'method', 'module', 'variable', 'typevar', 'paramspec', 'typevartuple', 'typealias']") -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node_name` | `Literal['argument', 'attr', 'class', 'class_attribute', 'class_const', 'const', 'inlinevar', 'function', 'method', 'module', 'variable', 'typevar', 'paramspec', 'typevartuple', 'typealias']` | `—` | pos/kw |

**Returns:** `int`

### `get_code_count`

Get a code type count.

```python
pylint.checkers.LinterStats.get_code_count(self, type_name: "Literal['code', 'comment', 'docstring', 'empty', 'total']") -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `type_name` | `Literal['code', 'comment', 'docstring', 'empty', 'total']` | `—` | pos/kw |

**Returns:** `int`

### `get_global_message_count`

Get a global message count.

```python
pylint.checkers.LinterStats.get_global_message_count(self, type_name: 'str') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `type_name` | `str` | `—` | pos/kw |

**Returns:** `int`

### `get_module_message_count`

Get a module message count.

```python
pylint.checkers.LinterStats.get_module_message_count(self, modname: 'str', type_name: 'MessageTypesFullName') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `modname` | `str` | `—` | pos/kw |
| `type_name` | `MessageTypesFullName` | `—` | pos/kw |

**Returns:** `int`

### `get_node_count`

Get a node count while handling some extra conditions.

```python
pylint.checkers.LinterStats.get_node_count(self, node_name: "Literal['function', 'class', 'method', 'module']") -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node_name` | `Literal['function', 'class', 'method', 'module']` | `—` | pos/kw |

**Returns:** `int`

### `get_undocumented`

Get a undocumented node count.

```python
pylint.checkers.LinterStats.get_undocumented(self, node_name: "Literal['function', 'class', 'method', 'module']") -> 'float'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node_name` | `Literal['function', 'class', 'method', 'module']` | `—` | pos/kw |

**Returns:** `float`

### `increase_bad_name`

Increase a bad names node count.

```python
pylint.checkers.LinterStats.increase_bad_name(self, node_name: 'str', increase: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node_name` | `str` | `—` | pos/kw |
| `increase` | `int` | `—` | pos/kw |

### `increase_single_message_count`

Increase the message type count of an individual message type.

```python
pylint.checkers.LinterStats.increase_single_message_count(self, type_name: 'str', increase: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `type_name` | `str` | `—` | pos/kw |
| `increase` | `int` | `—` | pos/kw |

### `increase_single_module_message_count`

Increase the message type count of an individual message type of a
module.

```python
pylint.checkers.LinterStats.increase_single_module_message_count(self, modname: 'str', type_name: 'MessageTypesFullName', increase: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `modname` | `str` | `—` | pos/kw |
| `type_name` | `MessageTypesFullName` | `—` | pos/kw |
| `increase` | `int` | `—` | pos/kw |

### `init_single_module`

Use through PyLinter.set_current_module so PyLinter.current_name is
consistent.

```python
pylint.checkers.LinterStats.init_single_module(self, module_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module_name` | `str` | `—` | pos/kw |

### `reset_bad_names`

Resets the bad_names attribute.

```python
pylint.checkers.LinterStats.reset_bad_names(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reset_code_count`

Resets the code_type_count attribute.

```python
pylint.checkers.LinterStats.reset_code_count(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reset_duplicated_lines`

Resets the duplicated_lines attribute.

```python
pylint.checkers.LinterStats.reset_duplicated_lines(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reset_message_count`

Resets the message type count of the stats object.

```python
pylint.checkers.LinterStats.reset_message_count(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reset_node_count`

Resets the node count attribute.

```python
pylint.checkers.LinterStats.reset_node_count(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reset_undocumented`

Resets the undocumented attribute.

```python
pylint.checkers.LinterStats.reset_undocumented(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pylint.checkers.async_checker.AsyncChecker` methods

### `add_message`

```python
pylint.checkers.async_checker.AsyncChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.async_checker.AsyncChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.async_checker.AsyncChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.async_checker.AsyncChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.async_checker.AsyncChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.async_checker.AsyncChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.async_checker.AsyncChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.async_checker.AsyncChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_asyncfunctiondef`

```python
pylint.checkers.async_checker.AsyncChecker.visit_asyncfunctiondef(self, node: 'nodes.AsyncFunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.AsyncFunctionDef` | `—` | pos/kw |

### `visit_asyncwith`

```python
pylint.checkers.async_checker.AsyncChecker.visit_asyncwith(self, node: 'nodes.AsyncWith') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.AsyncWith` | `—` | pos/kw |

### `pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker` methods

### `add_message`

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_compare`

```python
pylint.checkers.bad_chained_comparison.BadChainedComparisonChecker.visit_compare(self, node: 'nodes.Compare') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Compare` | `—` | pos/kw |

### `pylint.checkers.bad_chained_comparison.BaseChecker` methods

### `add_message`

```python
pylint.checkers.bad_chained_comparison.BaseChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.bad_chained_comparison.BaseChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.bad_chained_comparison.BaseChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.bad_chained_comparison.BaseChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.bad_chained_comparison.BaseChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.bad_chained_comparison.BaseChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.bad_chained_comparison.BaseChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.bad_chained_comparison.BaseChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `pylint.checkers.base.AnyStyle` methods

### `get_regex`

```python
pylint.checkers.base.AnyStyle.get_regex(name_type: 'str') -> 'Pattern[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name_type` | `str` | `—` | pos/kw |

**Returns:** `Pattern[str]`

### `pylint.checkers.base.BasicChecker` methods

### `add_message`

```python
pylint.checkers.base.BasicChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.base.BasicChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.base.BasicChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.base.BasicChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.base.BasicChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.base.BasicChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `leave_try`

Update try block flag.

```python
pylint.checkers.base.BasicChecker.leave_try(self, _: 'nodes.Try') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `nodes.Try` | `—` | pos/kw |

### `open`

Initialize visit variables and statistics.

```python
pylint.checkers.base.BasicChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.base.BasicChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_assert`

Check whether assert is used on a tuple or string literal.

```python
pylint.checkers.base.BasicChecker.visit_assert(self, node: 'nodes.Assert') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Assert` | `—` | pos/kw |

### `visit_assign`

```python
pylint.checkers.base.BasicChecker.visit_assign(self, node: 'nodes.Assign') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Assign` | `—` | pos/kw |

### `visit_asyncfunctiondef`

Check function name, docstring, arguments, redefinition,
variable names, max locals.

```python
pylint.checkers.base.BasicChecker.visit_asyncfunctiondef(self, node: 'nodes.FunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.FunctionDef` | `—` | pos/kw |

### `visit_break`

Break node visitor.

1 - check if the node has a right sibling (if so, that's some
unreachable code)
2 - check if the node is inside the 'finally' clause of a 'try...finally'
block

```python
pylint.checkers.base.BasicChecker.visit_break(self, node: 'nodes.Break') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Break` | `—` | pos/kw |

### `visit_call`

Visit a Call node.

```python
pylint.checkers.base.BasicChecker.visit_call(self, node: 'nodes.Call') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Call` | `—` | pos/kw |

### `visit_classdef`

Check module name, docstring and redefinition
increment branch counter.

```python
pylint.checkers.base.BasicChecker.visit_classdef(self, _: 'nodes.ClassDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `nodes.ClassDef` | `—` | pos/kw |

### `visit_comprehension`

```python
pylint.checkers.base.BasicChecker.visit_comprehension(self, node: 'nodes.Comprehension') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Comprehension` | `—` | pos/kw |

### `visit_continue`

Check is the node has a right sibling (if so, that's some unreachable
code).

```python
pylint.checkers.base.BasicChecker.visit_continue(self, node: 'nodes.Continue') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Continue` | `—` | pos/kw |

### `visit_dict`

Check duplicate key in dictionary.

```python
pylint.checkers.base.BasicChecker.visit_dict(self, node: 'nodes.Dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Dict` | `—` | pos/kw |

### `visit_expr`

Check for various kind of statements without effect.

```python
pylint.checkers.base.BasicChecker.visit_expr(self, node: 'nodes.Expr') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Expr` | `—` | pos/kw |

### `visit_for`

```python
pylint.checkers.base.BasicChecker.visit_for(self, node: 'nodes.For') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.For` | `—` | pos/kw |

### `visit_functiondef`

Check function name, docstring, arguments, redefinition,
variable names, max locals.

```python
pylint.checkers.base.BasicChecker.visit_functiondef(self, node: 'nodes.FunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.FunctionDef` | `—` | pos/kw |

### `visit_if`

```python
pylint.checkers.base.BasicChecker.visit_if(self, node: 'nodes.If') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.If` | `—` | pos/kw |

### `visit_ifexp`

```python
pylint.checkers.base.BasicChecker.visit_ifexp(self, node: 'nodes.IfExp') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.IfExp` | `—` | pos/kw |

### `visit_lambda`

Check whether the lambda is suspicious.

```python
pylint.checkers.base.BasicChecker.visit_lambda(self, node: 'nodes.Lambda') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Lambda` | `—` | pos/kw |

### `visit_module`

Check module name, docstring and required arguments.

```python
pylint.checkers.base.BasicChecker.visit_module(self, _: 'nodes.Module') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `nodes.Module` | `—` | pos/kw |

### `visit_raise`

Check if the node has a right sibling (if so, that's some unreachable
code).

```python
pylint.checkers.base.BasicChecker.visit_raise(self, node: 'nodes.Raise') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Raise` | `—` | pos/kw |

### `visit_return`

Return node visitor.

1 - check if the node has a right sibling (if so, that's some
unreachable code)
2 - check if the node is inside the 'finally' clause of a 'try...finally'
block

```python
pylint.checkers.base.BasicChecker.visit_return(self, node: 'nodes.Return') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Return` | `—` | pos/kw |

### `visit_set`

Check duplicate value in set.

```python
pylint.checkers.base.BasicChecker.visit_set(self, node: 'nodes.Set') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Set` | `—` | pos/kw |

### `visit_try`

Update try block flag.

```python
pylint.checkers.base.BasicChecker.visit_try(self, node: 'nodes.Try') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Try` | `—` | pos/kw |

### `visit_with`

```python
pylint.checkers.base.BasicChecker.visit_with(self, node: 'nodes.With') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.With` | `—` | pos/kw |

### `pylint.checkers.base.BasicErrorChecker` methods

### `add_message`

```python
pylint.checkers.base.BasicErrorChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.base.BasicErrorChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.base.BasicErrorChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.base.BasicErrorChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.base.BasicErrorChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.base.BasicErrorChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.base.BasicErrorChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.base.BasicErrorChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_assign`

```python
pylint.checkers.base.BasicErrorChecker.visit_assign(self, node: 'nodes.Assign') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Assign` | `—` | pos/kw |

### `visit_asyncfunctiondef`

```python
pylint.checkers.base.BasicErrorChecker.visit_asyncfunctiondef(self, node: 'nodes.FunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.FunctionDef` | `—` | pos/kw |

### `visit_break`

```python
pylint.checkers.base.BasicErrorChecker.visit_break(self, node: 'nodes.Break') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Break` | `—` | pos/kw |

### `visit_call`

Check instantiating abstract class with
abc.ABCMeta as metaclass.

```python
pylint.checkers.base.BasicErrorChecker.visit_call(self, node: 'nodes.Call') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Call` | `—` | pos/kw |

### `visit_classdef`

```python
pylint.checkers.base.BasicErrorChecker.visit_classdef(self, node: 'nodes.ClassDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.ClassDef` | `—` | pos/kw |

### `visit_continue`

```python
pylint.checkers.base.BasicErrorChecker.visit_continue(self, node: 'nodes.Continue') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Continue` | `—` | pos/kw |

### `visit_for`

```python
pylint.checkers.base.BasicErrorChecker.visit_for(self, node: 'nodes.For') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.For` | `—` | pos/kw |

### `visit_functiondef`

```python
pylint.checkers.base.BasicErrorChecker.visit_functiondef(self, node: 'nodes.FunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.FunctionDef` | `—` | pos/kw |

### `visit_nonlocal`

```python
pylint.checkers.base.BasicErrorChecker.visit_nonlocal(self, node: 'nodes.Nonlocal') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Nonlocal` | `—` | pos/kw |

### `visit_return`

```python
pylint.checkers.base.BasicErrorChecker.visit_return(self, node: 'nodes.Return') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Return` | `—` | pos/kw |

### `visit_starred`

Check that a Starred expression is used in an assignment target.

```python
pylint.checkers.base.BasicErrorChecker.visit_starred(self, node: 'nodes.Starred') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Starred` | `—` | pos/kw |

### `visit_unaryop`

Check use of the non-existent ++ and -- operators.

```python
pylint.checkers.base.BasicErrorChecker.visit_unaryop(self, node: 'nodes.UnaryOp') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.UnaryOp` | `—` | pos/kw |

### `visit_while`

```python
pylint.checkers.base.BasicErrorChecker.visit_while(self, node: 'nodes.While') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.While` | `—` | pos/kw |

### `visit_yield`

```python
pylint.checkers.base.BasicErrorChecker.visit_yield(self, node: 'nodes.Yield') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Yield` | `—` | pos/kw |

### `visit_yieldfrom`

```python
pylint.checkers.base.BasicErrorChecker.visit_yieldfrom(self, node: 'nodes.YieldFrom') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.YieldFrom` | `—` | pos/kw |

### `pylint.checkers.base.CamelCaseStyle` methods

### `get_regex`

```python
pylint.checkers.base.CamelCaseStyle.get_regex(name_type: 'str') -> 'Pattern[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name_type` | `str` | `—` | pos/kw |

**Returns:** `Pattern[str]`

### `pylint.checkers.base.ComparisonChecker` methods

### `add_message`

```python
pylint.checkers.base.ComparisonChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.base.ComparisonChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.base.ComparisonChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.base.ComparisonChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.base.ComparisonChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.base.ComparisonChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.base.ComparisonChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.base.ComparisonChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_compare`

```python
pylint.checkers.base.ComparisonChecker.visit_compare(self, node: astroid.nodes.node_classes.Compare) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `Compare` | `—` | pos/kw |

### `pylint.checkers.base.DocStringChecker` methods

### `add_message`

```python
pylint.checkers.base.DocStringChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.base.DocStringChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.base.DocStringChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.base.DocStringChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.base.DocStringChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_map_data`

```python
pylint.checkers.base.DocStringChecker.get_map_data(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `open`

Called before visiting project (i.e. set of modules).

```python
pylint.checkers.base.DocStringChecker.open(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reduce_map_data`

```python
pylint.checkers.base.DocStringChecker.reduce_map_data(self, linter: 'PyLinter', data: 'list[Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `linter` | `PyLinter` | `—` | pos/kw |
| `data` | `list[Any]` | `—` | pos/kw |

### `visit_asyncfunctiondef`

```python
pylint.checkers.base.DocStringChecker.visit_asyncfunctiondef(self, node: 'nodes.FunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.FunctionDef` | `—` | pos/kw |

### `visit_classdef`

```python
pylint.checkers.base.DocStringChecker.visit_classdef(self, node: 'nodes.ClassDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.ClassDef` | `—` | pos/kw |

### `visit_functiondef`

```python
pylint.checkers.base.DocStringChecker.visit_functiondef(self, node: 'nodes.FunctionDef') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.FunctionDef` | `—` | pos/kw |

### `visit_module`

```python
pylint.checkers.base.DocStringChecker.visit_module(self, node: 'nodes.Module') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `nodes.Module` | `—` | pos/kw |

### `pylint.checkers.base.FunctionChecker` methods

### `add_message`

```python
pylint.checkers.base.FunctionChecker.add_message(self, msgid: 'str', line: 'int | None' = None, node: 'nodes.NodeNG | None' = None, args: 'Any' = None, confidence: 'Confidence | None' = None, col_offset: 'int | None' = None, end_lineno: 'int | None' = None, end_col_offset: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `line` | `int \| None` | `None` | pos/kw |
| `node` | `nodes.NodeNG \| None` | `None` | pos/kw |
| `args` | `Any` | `None` | pos/kw |
| `confidence` | `Confidence \| None` | `None` | pos/kw |
| `col_offset` | `int \| None` | `None` | pos/kw |
| `end_lineno` | `int \| None` | `None` | pos/kw |
| `end_col_offset` | `int \| None` | `None` | pos/kw |

### `check_consistency`

Check the consistency of msgid.

msg ids for a checker should be a string of len 4, where the two first
characters are the checker id and the two last the msg id in this
checker.

:raises InvalidMess…

```python
pylint.checkers.base.FunctionChecker.check_consistency(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

Called after visiting project (i.e set of modules).

```python
pylint.checkers.base.FunctionChecker.close(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_message_definition_from_tuple`

```python
pylint.checkers.base.FunctionChecker.create_message_definition_from_tuple(self, msgid: 'str', msg_tuple: 'MessageDefinitionTuple') -> 'MessageDefinition'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgid` | `str` | `—` | pos/kw |
| `msg_tuple` | `MessageDefinitionTuple` | `—` | pos/kw |

**Returns:** `MessageDefinition`

### `get_full_documentation`

```python
pylint.checkers.base.FunctionChecker.get_full_documentation(self, msgs: 'dict[str, MessageDefinitionTuple]', options: 'Iterable[tuple[str, OptionDict, Any]]', reports: 'Sequence[tuple[str, str, ReportsCallable]]', doc: 'str | None' = None, module: 'str | None' = None, show_options: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msgs` | `dict[str, MessageDefinitionTuple]` | `—` | pos/kw |
| `options` | `Iterable[tuple[str, OptionDict, Any]]` | `—` | pos/kw |
| `reports` | `Sequence[tuple[str, str, ReportsCallable]]` | `—` | pos/kw |
| `doc` | `str \| None` | `None` | pos/kw |
| `module` | `str \| None` | `None` | pos/kw |
| `show_options` | `bool` | `True` | pos/kw |

**Returns:** `str`


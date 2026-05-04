---
name: package
description: "detect-secrets guide for baselines, audits, and pre-commit enforcement in Python projects"
metadata:
  languages: "python"
  versions: "1.5.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "detect-secrets,python,security,secrets,pre-commit,cli,SecretsCollection,exactly_equals,json,load_from_baseline,merge,scan_diff,scan_file,scan_files,trim,audit_baseline,compare_baselines,PotentialSecret,hash_secret,load_secret_from_dict,set_secret,StatisticsAggregator,record_secret,StatisticsCounter,calculate_precision,calculate_recall,calculate_statistics_for_baseline,get_baseline_from_file,BidirectionalIterator,can_step_back,next,step_back_on_next_iteration,NoLineNumberError,SecretContext,SecretNotFoundOnSpecifiedLineError,get_code_snippet,get_raw_secret_from_file,get_secret_iterator,BasePlugin,analyze_line,analyze_string,format_scan_result,verify,InvalidBaselineError,LineGetter,open_file,NamedIO,call_function_with_arguments,get_raw_secrets_from_file,get_transformed_file,AnsiColor,colorize,transient_settings,InputOptions,UserPrompt,clear_screen,get_user_decision,print_context,print_error,print_message,print_secret_not_found,SecretClassToPrint,VerifiedResult,generate_report,get_prioritized_verified_result,UnableToReadBaselineError,Version,configure_settings_from_baseline,create,format_for_output,get_files_to_scan,import_modules_from_package,load,load_from_file,save_to_file,upgrade,CustomLogger,addFilter,addHandler,callHandlers,critical,debug,error,exception,fatal,filter,findCaller,getChild,getChildren,getEffectiveLevel,handle,hasHandlers,info,isEnabledFor,log,makeRecord,removeFilter,removeHandler,setLevel,set_debug_level,warn,warning,get_logger,convert_local_os_path,CodeSnippet,add_line_numbers,apply_highlight,get_line_number,highlight_line"
---

# detect-secrets — package

## Install

```bash
pip install detect-secrets
```

## Imports

```python
import detect_secrets
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `SecretsCollection` | Class |  |
| `exactly_equals` | Method |  |
| `json` | Method | Custom JSON encoder |
| `load_from_baseline` | Method |  |
| `merge` | Method | We operate under an assumption that the latest results are always more accurate… |
| `scan_diff` | Method | :raises: UnidiffParseError |
| `scan_file` | Method |  |
| `scan_files` | Method | Just like scan_file, but optimized through parallel processing. |
| `trim` | Method | Removes invalid entries in the current SecretsCollection.  This behaves *kinda*… |
| `audit_baseline` | Function | :raises: InvalidBaselineError |
| `compare_baselines` | Function |  |
| `PotentialSecret` | Class | This custom data type represents a string found, matching the plugin rules defi… |
| `hash_secret` | Method | This offers a way to coherently test this class, without mocking self.secret_ha… |
| `json` | Method | Custom JSON encoder |
| `load_secret_from_dict` | Method | Custom JSON decoder |
| `set_secret` | Method |  |
| `StatisticsAggregator` | Class |  |
| `json` | Method |  |
| `record_secret` | Method |  |
| `StatisticsCounter` | Class |  |
| `calculate_precision` | Method |  |
| `calculate_recall` | Method |  |
| `json` | Method |  |
| `calculate_statistics_for_baseline` | Function | :raises: InvalidBaselineError |
| `get_baseline_from_file` | Function | :raises: InvalidBaselineError |
| `BidirectionalIterator` | Class |  |
| `can_step_back` | Method |  |
| `next` | Method |  |
| `step_back_on_next_iteration` | Method |  |
| `NoLineNumberError` | Class | Common base class for all non-exit exceptions. |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `SecretsCollection`

```python
detect_secrets.SecretsCollection(self, root: str = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `str` | `''` | pos/kw |

### `PotentialSecret`

This custom data type represents a string found, matching the
plugin rules defined in SecretsCollection, that has the potential
to be a secret that we actually care about.

"Potential" is the operati…

```python
detect_secrets.audit.analytics.PotentialSecret(self, type: str, filename: str, secret: str, line_number: int = 0, is_secret: Optional[bool] = None, is_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `is_secret` | `Optional` | `None` | pos/kw |
| `is_verified` | `bool` | `False` | pos/kw |

### `StatisticsAggregator`

```python
detect_secrets.audit.analytics.StatisticsAggregator(self) -> None
```

### `StatisticsCounter`

```python
detect_secrets.audit.analytics.StatisticsCounter(self) -> None
```

### `BidirectionalIterator`

```python
detect_secrets.audit.audit.BidirectionalIterator(self, collection: Sequence)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `collection` | `Sequence` | `—` | pos/kw |

### `NoLineNumberError`

Common base class for all non-exit exceptions.

```python
detect_secrets.audit.audit.NoLineNumberError(self) -> None
```

### `SecretContext`

SecretContext(current_index, num_total_secrets, secret, header, snippet, error)

```python
detect_secrets.audit.audit.SecretContext(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SecretNotFoundOnSpecifiedLineError`

Common base class for all non-exit exceptions.

```python
detect_secrets.audit.audit.SecretNotFoundOnSpecifiedLineError(self, line: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `int` | `—` | pos/kw |

### `BasePlugin`

```python
detect_secrets.audit.common.BasePlugin(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidBaselineError`

Think of this as a 400, if getting a baseline had a HTTPError code.

```python
detect_secrets.audit.common.InvalidBaselineError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LineGetter`

The problem we try to address with this class is to cache the lines of a transformed file,
without knowing beforehand what type of transformation that file needs to undergo.

When we scan the file, w…

```python
detect_secrets.audit.common.LineGetter(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `NamedIO`

Base class for text I/O.

This class provides a character and line based interface to stream
I/O. There is no readinto method because Python's character strings
are immutable.

```python
detect_secrets.audit.common.NamedIO(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NoLineNumberError`

Common base class for all non-exit exceptions.

```python
detect_secrets.audit.common.NoLineNumberError(self) -> None
```

### `PotentialSecret`

This custom data type represents a string found, matching the
plugin rules defined in SecretsCollection, that has the potential
to be a secret that we actually care about.

"Potential" is the operati…

```python
detect_secrets.audit.common.PotentialSecret(self, type: str, filename: str, secret: str, line_number: int = 0, is_secret: Optional[bool] = None, is_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `is_secret` | `Optional` | `None` | pos/kw |
| `is_verified` | `bool` | `False` | pos/kw |

### `SecretNotFoundOnSpecifiedLineError`

Common base class for all non-exit exceptions.

```python
detect_secrets.audit.common.SecretNotFoundOnSpecifiedLineError(self, line: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `int` | `—` | pos/kw |

### `SecretsCollection`

```python
detect_secrets.audit.common.SecretsCollection(self, root: str = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `str` | `''` | pos/kw |

### `AnsiColor`

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
detect_secrets.audit.compare.AnsiColor(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `BidirectionalIterator`

```python
detect_secrets.audit.compare.BidirectionalIterator(self, collection: Sequence)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `collection` | `Sequence` | `—` | pos/kw |

### `NoLineNumberError`

Common base class for all non-exit exceptions.

```python
detect_secrets.audit.compare.NoLineNumberError(self) -> None
```

### `PotentialSecret`

This custom data type represents a string found, matching the
plugin rules defined in SecretsCollection, that has the potential
to be a secret that we actually care about.

"Potential" is the operati…

```python
detect_secrets.audit.compare.PotentialSecret(self, type: str, filename: str, secret: str, line_number: int = 0, is_secret: Optional[bool] = None, is_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `is_secret` | `Optional` | `None` | pos/kw |
| `is_verified` | `bool` | `False` | pos/kw |

### `SecretContext`

SecretContext(current_index, num_total_secrets, secret, header, snippet, error)

```python
detect_secrets.audit.compare.SecretContext(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SecretNotFoundOnSpecifiedLineError`

Common base class for all non-exit exceptions.

```python
detect_secrets.audit.compare.SecretNotFoundOnSpecifiedLineError(self, line: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `int` | `—` | pos/kw |

### `SecretsCollection`

```python
detect_secrets.audit.compare.SecretsCollection(self, root: str = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `str` | `''` | pos/kw |

### `AnsiColor`

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
detect_secrets.audit.io.AnsiColor(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `InputOptions`

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
detect_secrets.audit.io.InputOptions(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `SecretContext`

SecretContext(current_index, num_total_secrets, secret, header, snippet, error)

```python
detect_secrets.audit.io.SecretContext(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UserPrompt`

```python
detect_secrets.audit.io.UserPrompt(self, allow_labelling: bool, allow_backstep: bool) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `allow_labelling` | `bool` | `—` | pos/kw |
| `allow_backstep` | `bool` | `—` | pos/kw |

### `BidirectionalIterator`

```python
detect_secrets.audit.iterator.BidirectionalIterator(self, collection: Sequence)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `collection` | `Sequence` | `—` | pos/kw |

### `SecretsCollection`

```python
detect_secrets.audit.iterator.SecretsCollection(self, root: str = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `str` | `''` | pos/kw |

### `LineGetter`

The problem we try to address with this class is to cache the lines of a transformed file,
without knowing beforehand what type of transformation that file needs to undergo.

When we scan the file, w…

```python
detect_secrets.audit.report.LineGetter(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `SecretClassToPrint`

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
detect_secrets.audit.report.SecretClassToPrint(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `VerifiedResult`

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
detect_secrets.audit.report.VerifiedResult(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `PotentialSecret`

This custom data type represents a string found, matching the
plugin rules defined in SecretsCollection, that has the potential
to be a secret that we actually care about.

"Potential" is the operati…

```python
detect_secrets.constants.PotentialSecret(self, type: str, filename: str, secret: str, line_number: int = 0, is_secret: Optional[bool] = None, is_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `is_secret` | `Optional` | `None` | pos/kw |
| `is_verified` | `bool` | `False` | pos/kw |

### `VerifiedResult`

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
detect_secrets.constants.VerifiedResult(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `SecretsCollection`

```python
detect_secrets.core.baseline.SecretsCollection(self, root: str = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `str` | `''` | pos/kw |

### `UnableToReadBaselineError`

Think of this as a 404, if getting a baseline had a HTTPError code.

```python
detect_secrets.core.baseline.UnableToReadBaselineError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Version`

```python
detect_secrets.core.baseline.Version(self, version: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

### `CustomLogger`

Instances of the Logger class represent a single logging channel. A
"logging channel" indicates an area of an application. Exactly how an
"area" is defined is up to the application developer. Since a…

```python
detect_secrets.core.log.CustomLogger(self, name, level=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `level` | `—` | `0` | pos/kw |

### `AnsiColor`

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
detect_secrets.core.potential_secret.AnsiColor(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `PotentialSecret`

This custom data type represents a string found, matching the
plugin rules defined in SecretsCollection, that has the potential
to be a secret that we actually care about.

"Potential" is the operati…

```python
detect_secrets.core.potential_secret.PotentialSecret(self, type: str, filename: str, secret: str, line_number: int = 0, is_secret: Optional[bool] = None, is_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `is_secret` | `Optional` | `None` | pos/kw |
| `is_verified` | `bool` | `False` | pos/kw |

### `CodeSnippet`

```python
detect_secrets.core.scan.CodeSnippet(self, snippet: List[str], start_line: int, target_index: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `snippet` | `List` | `—` | pos/kw |
| `start_line` | `int` | `—` | pos/kw |
| `target_index` | `int` | `—` | pos/kw |

### `NamedIO`

Base class for text I/O.

This class provides a character and line based interface to stream
I/O. There is no readinto method because Python's character strings
are immutable.

```python
detect_secrets.core.scan.NamedIO(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PotentialSecret`

This custom data type represents a string found, matching the
plugin rules defined in SecretsCollection, that has the potential
to be a secret that we actually care about.

"Potential" is the operati…

```python
detect_secrets.core.scan.PotentialSecret(self, type: str, filename: str, secret: str, line_number: int = 0, is_secret: Optional[bool] = None, is_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `is_secret` | `Optional` | `None` | pos/kw |
| `is_verified` | `bool` | `False` | pos/kw |

## Functions

### `audit_baseline`

:raises: InvalidBaselineError

```python
detect_secrets.audit.audit_baseline(filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `compare_baselines`

```python
detect_secrets.audit.compare_baselines(old_baseline_filename: str, new_baseline_filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old_baseline_filename` | `str` | `—` | pos/kw |
| `new_baseline_filename` | `str` | `—` | pos/kw |

### `calculate_statistics_for_baseline`

:raises: InvalidBaselineError

```python
detect_secrets.audit.analytics.calculate_statistics_for_baseline(filename: str, **kwargs: Any) -> 'StatisticsAggregator'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `StatisticsAggregator`

### `get_baseline_from_file`

:raises: InvalidBaselineError

```python
detect_secrets.audit.analytics.get_baseline_from_file(filename: str) -> detect_secrets.core.secrets_collection.SecretsCollection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `<class 'detect_secrets.core.secrets_collection.SecretsCollection'>`

### `audit_baseline`

:raises: InvalidBaselineError

```python
detect_secrets.audit.audit.audit_baseline(filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `get_baseline_from_file`

:raises: InvalidBaselineError

```python
detect_secrets.audit.audit.get_baseline_from_file(filename: str) -> detect_secrets.core.secrets_collection.SecretsCollection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `<class 'detect_secrets.core.secrets_collection.SecretsCollection'>`

### `get_code_snippet`

:param lines: an iterator of lines in the file
:param line_number: line which you want to focus on
:param lines_of_context: how many lines to display around the line you want
    to focus on.

```python
detect_secrets.audit.audit.get_code_snippet(lines: List[str], line_number: int, lines_of_context: int = 5) -> 'CodeSnippet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `List` | `—` | pos/kw |
| `line_number` | `int` | `—` | pos/kw |
| `lines_of_context` | `int` | `5` | pos/kw |

**Returns:** `CodeSnippet`

### `get_raw_secret_from_file`

We're analyzing the contents straight from the baseline, and therefore, we don't know
the secret value (by design). However, we have line numbers, filenames, and how we detected
it was a secret in th…

```python
detect_secrets.audit.audit.get_raw_secret_from_file(secret: detect_secrets.core.potential_secret.PotentialSecret, line_getter_factory: Callable[[str], ForwardRef('LineGetter')] = <functools._lru_cache_wrapper object at 0x764af5bf9590>) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `PotentialSecret` | `—` | pos/kw |
| `line_getter_factory` | `Callable` | `<functools._lru_cache_wrapper object at 0x764af5bf9590>` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_secret_iterator`

:returns: (index, filename, secret)

```python
detect_secrets.audit.audit.get_secret_iterator(baseline: detect_secrets.core.secrets_collection.SecretsCollection) -> 'BidirectionalIterator'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `SecretsCollection` | `—` | pos/kw |

**Returns:** `BidirectionalIterator`

### `call_function_with_arguments`

:raises: TypeError

```python
detect_secrets.audit.common.call_function_with_arguments(func: Union[Callable, detect_secrets.types.SelfAwareCallable], **kwargs: Any) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Union` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `typing.Any`

### `get_baseline_from_file`

:raises: InvalidBaselineError

```python
detect_secrets.audit.common.get_baseline_from_file(filename: str) -> detect_secrets.core.secrets_collection.SecretsCollection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `<class 'detect_secrets.core.secrets_collection.SecretsCollection'>`

### `get_code_snippet`

:param lines: an iterator of lines in the file
:param line_number: line which you want to focus on
:param lines_of_context: how many lines to display around the line you want
    to focus on.

```python
detect_secrets.audit.common.get_code_snippet(lines: List[str], line_number: int, lines_of_context: int = 5) -> 'CodeSnippet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `List` | `—` | pos/kw |
| `line_number` | `int` | `—` | pos/kw |
| `lines_of_context` | `int` | `5` | pos/kw |

**Returns:** `CodeSnippet`

### `get_raw_secret_from_file`

We're analyzing the contents straight from the baseline, and therefore, we don't know
the secret value (by design). However, we have line numbers, filenames, and how we detected
it was a secret in th…

```python
detect_secrets.audit.common.get_raw_secret_from_file(secret: detect_secrets.core.potential_secret.PotentialSecret, line_getter_factory: Callable[[str], ForwardRef('LineGetter')] = <functools._lru_cache_wrapper object at 0x764af5bf9590>) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `PotentialSecret` | `—` | pos/kw |
| `line_getter_factory` | `Callable` | `<functools._lru_cache_wrapper object at 0x764af5bf9590>` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_raw_secrets_from_file`

We're analyzing the contents straight from the baseline, and therefore, we don't know
the secret value (by design). However, we have secret hashes, filenames, and how we detected
it was a secret in t…

```python
detect_secrets.audit.common.get_raw_secrets_from_file(secret: detect_secrets.core.potential_secret.PotentialSecret, line_getter_factory: Callable[[str], ForwardRef('LineGetter')] = <functools._lru_cache_wrapper object at 0x764af5bf9590>) -> List[detect_secrets.core.potential_secret.PotentialSecret]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `PotentialSecret` | `—` | pos/kw |
| `line_getter_factory` | `Callable` | `<functools._lru_cache_wrapper object at 0x764af5bf9590>` | pos/kw |

**Returns:** `typing.List[detect_secrets.core.potential_secret.PotentialSecret]`

### `get_transformed_file`

```python
detect_secrets.audit.common.get_transformed_file(file: detect_secrets.types.NamedIO, use_eager_transformers: bool = False) -> Optional[List[str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `file` | `NamedIO` | `—` | pos/kw |
| `use_eager_transformers` | `bool` | `False` | pos/kw |

**Returns:** `typing.Optional[typing.List[str]]`

### `colorize`

```python
detect_secrets.audit.compare.colorize(text: str, color: detect_secrets.util.color.AnsiColor) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `str` | `—` | pos/kw |
| `color` | `AnsiColor` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `compare_baselines`

```python
detect_secrets.audit.compare.compare_baselines(old_baseline_filename: str, new_baseline_filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old_baseline_filename` | `str` | `—` | pos/kw |
| `new_baseline_filename` | `str` | `—` | pos/kw |

### `get_code_snippet`

:param lines: an iterator of lines in the file
:param line_number: line which you want to focus on
:param lines_of_context: how many lines to display around the line you want
    to focus on.

```python
detect_secrets.audit.compare.get_code_snippet(lines: List[str], line_number: int, lines_of_context: int = 5) -> 'CodeSnippet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `List` | `—` | pos/kw |
| `line_number` | `int` | `—` | pos/kw |
| `lines_of_context` | `int` | `5` | pos/kw |

**Returns:** `CodeSnippet`

### `get_raw_secret_from_file`

We're analyzing the contents straight from the baseline, and therefore, we don't know
the secret value (by design). However, we have line numbers, filenames, and how we detected
it was a secret in th…

```python
detect_secrets.audit.compare.get_raw_secret_from_file(secret: detect_secrets.core.potential_secret.PotentialSecret, line_getter_factory: Callable[[str], ForwardRef('LineGetter')] = <functools._lru_cache_wrapper object at 0x764af5bf9590>) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `PotentialSecret` | `—` | pos/kw |
| `line_getter_factory` | `Callable` | `<functools._lru_cache_wrapper object at 0x764af5bf9590>` | pos/kw |

**Returns:** `typing.Optional[str]`

### `transient_settings`

Allows the customizability of non-global settings per invocation.

```python
detect_secrets.audit.compare.transient_settings(config: Dict[str, Any]) -> Generator[ForwardRef('Settings'), NoneType, NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `Dict` | `—` | pos/kw |

**Returns:** `typing.Generator[ForwardRef('Settings'), NoneType, NoneType]`

### `clear_screen`

```python
detect_secrets.audit.io.clear_screen() -> None
```

### `colorize`

```python
detect_secrets.audit.io.colorize(text: str, color: detect_secrets.util.color.AnsiColor) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `str` | `—` | pos/kw |
| `color` | `AnsiColor` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_user_decision`

:param prompt_secret_decision: if False, won't ask to label secret.
    e.g. if the secret isn't found on the line

```python
detect_secrets.audit.io.get_user_decision(prompt_secret_decision: bool = True, can_step_back: bool = False) -> 'InputOptions'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt_secret_decision` | `bool` | `True` | pos/kw |
| `can_step_back` | `bool` | `False` | pos/kw |

**Returns:** `InputOptions`

### `print_context`

```python
detect_secrets.audit.io.print_context(context: detect_secrets.types.SecretContext) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `SecretContext` | `—` | pos/kw |

### `print_error`

```python
detect_secrets.audit.io.print_error(message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `print_message`

```python
detect_secrets.audit.io.print_message(message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `print_secret_not_found`

```python
detect_secrets.audit.io.print_secret_not_found(context: detect_secrets.types.SecretContext) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `SecretContext` | `—` | pos/kw |

### `get_secret_iterator`

:returns: (index, filename, secret)

```python
detect_secrets.audit.iterator.get_secret_iterator(baseline: detect_secrets.core.secrets_collection.SecretsCollection) -> 'BidirectionalIterator'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `SecretsCollection` | `—` | pos/kw |

**Returns:** `BidirectionalIterator`

### `generate_report`

```python
detect_secrets.audit.report.generate_report(baseline_file: str, class_to_print: detect_secrets.audit.report.SecretClassToPrint = None, line_getter_factory: Callable[[str], ForwardRef('LineGetter')] = <functools._lru_cache_wrapper object at 0x764af5bf9590>) -> Dict[str, List[Dict[str, Any]]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline_file` | `str` | `—` | pos/kw |
| `class_to_print` | `SecretClassToPrint` | `None` | pos/kw |
| `line_getter_factory` | `Callable` | `<functools._lru_cache_wrapper object at 0x764af5bf9590>` | pos/kw |

**Returns:** `typing.Dict[str, typing.List[typing.Dict[str, typing.Any]]]`

### `get_baseline_from_file`

:raises: InvalidBaselineError

```python
detect_secrets.audit.report.get_baseline_from_file(filename: str) -> detect_secrets.core.secrets_collection.SecretsCollection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `<class 'detect_secrets.core.secrets_collection.SecretsCollection'>`

### `get_prioritized_verified_result`

```python
detect_secrets.audit.report.get_prioritized_verified_result(result1: detect_secrets.constants.VerifiedResult, result2: detect_secrets.constants.VerifiedResult) -> detect_secrets.constants.VerifiedResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `result1` | `VerifiedResult` | `—` | pos/kw |
| `result2` | `VerifiedResult` | `—` | pos/kw |

**Returns:** `<enum 'VerifiedResult'>`

### `get_raw_secrets_from_file`

We're analyzing the contents straight from the baseline, and therefore, we don't know
the secret value (by design). However, we have secret hashes, filenames, and how we detected
it was a secret in t…

```python
detect_secrets.audit.report.get_raw_secrets_from_file(secret: detect_secrets.core.potential_secret.PotentialSecret, line_getter_factory: Callable[[str], ForwardRef('LineGetter')] = <functools._lru_cache_wrapper object at 0x764af5bf9590>) -> List[detect_secrets.core.potential_secret.PotentialSecret]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `PotentialSecret` | `—` | pos/kw |
| `line_getter_factory` | `Callable` | `<functools._lru_cache_wrapper object at 0x764af5bf9590>` | pos/kw |

**Returns:** `typing.List[detect_secrets.core.potential_secret.PotentialSecret]`

### `configure_settings_from_baseline`

:raises: KeyError

```python
detect_secrets.core.baseline.configure_settings_from_baseline(baseline: Dict[str, Any], filename: str = '') -> 'Settings'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |
| `filename` | `str` | `''` | pos/kw |

**Returns:** `Settings`

### `create`

Scans all the files recursively in path to initialize a baseline.

```python
detect_secrets.core.baseline.create(*paths: str, should_scan_all_files: bool = False, root: str = '', num_processors: Optional[int] = None) -> detect_secrets.core.secrets_collection.SecretsCollection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `str` | `—` | *args |
| `should_scan_all_files` | `bool` | `False` | kw |
| `root` | `str` | `''` | kw |
| `num_processors` | `Optional` | `None` | kw |

**Returns:** `<class 'detect_secrets.core.secrets_collection.SecretsCollection'>`

### `format_for_output`

```python
detect_secrets.core.baseline.format_for_output(secrets: detect_secrets.core.secrets_collection.SecretsCollection, is_slim_mode: bool = False) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secrets` | `SecretsCollection` | `—` | pos/kw |
| `is_slim_mode` | `bool` | `False` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_files_to_scan`

If we specify specific files, we should be able to scan them. This abides by the
Principle of Least Surprise -- so users don't have to do:

    $ detect-secrets scan test_data/config.env --all-files…

```python
detect_secrets.core.baseline.get_files_to_scan(*paths: str, should_scan_all_files: bool = False, root: str = '') -> Generator[str, NoneType, NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `str` | `—` | *args |
| `should_scan_all_files` | `bool` | `False` | kw |
| `root` | `str` | `''` | kw |

**Returns:** `typing.Generator[str, NoneType, NoneType]`

### `import_modules_from_package`

```python
detect_secrets.core.baseline.import_modules_from_package(root: module, filter: Callable[[str], bool]) -> Iterable[module]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `module` | `—` | pos/kw |
| `filter` | `Callable` | `—` | pos/kw |

**Returns:** `typing.Iterable[module]`

### `load`

With a given baseline file, load all settings and discovered secrets from it.

:raises: KeyError

```python
detect_secrets.core.baseline.load(baseline: Dict[str, Any], filename: str = '') -> detect_secrets.core.secrets_collection.SecretsCollection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |
| `filename` | `str` | `''` | pos/kw |

**Returns:** `<class 'detect_secrets.core.secrets_collection.SecretsCollection'>`

### `load_from_file`

:raises: UnableToReadBaselineError
:raises: InvalidBaselineError

```python
detect_secrets.core.baseline.load_from_file(filename: str) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `save_to_file`

:param secrets: if this is a SecretsCollection, it will output the baseline in its latest
    format. Otherwise, you should pass in a dictionary to this function, to manually
    specify the baseline…

```python
detect_secrets.core.baseline.save_to_file(secrets: Union[detect_secrets.core.secrets_collection.SecretsCollection, Dict[str, Any]], filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secrets` | `Union` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |

### `upgrade`

Baselines will eventually require format changes. This function is responsible for upgrading
an older baseline to the latest version.

```python
detect_secrets.core.baseline.upgrade(baseline: Dict[str, Any]) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_logger`

:param name: used for declaring log channels.
:param format_string: for custom formatting

```python
detect_secrets.core.log.get_logger(name: Optional[str] = None, format_string: Optional[str] = None) -> 'CustomLogger'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `Optional` | `None` | pos/kw |
| `format_string` | `Optional` | `None` | pos/kw |

**Returns:** `CustomLogger`

### `colorize`

```python
detect_secrets.core.potential_secret.colorize(text: str, color: detect_secrets.util.color.AnsiColor) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `str` | `—` | pos/kw |
| `color` | `AnsiColor` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_local_os_path`

```python
detect_secrets.core.potential_secret.convert_local_os_path(path: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

## Methods

### `detect_secrets.SecretsCollection` methods

### `exactly_equals`

```python
detect_secrets.SecretsCollection.exactly_equals(self, other: Any) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `Any` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `json`

Custom JSON encoder

```python
detect_secrets.SecretsCollection.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `load_from_baseline`

```python
detect_secrets.SecretsCollection.load_from_baseline(baseline: Dict[str, Any]) -> 'SecretsCollection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |

**Returns:** `SecretsCollection`

### `merge`

We operate under an assumption that the latest results are always more accurate,
assuming that the baseline is created on the same repository. However, we cannot
merely discard the old results in fav…

```python
detect_secrets.SecretsCollection.merge(self, old_results: 'SecretsCollection') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `old_results` | `SecretsCollection` | `—` | pos/kw |

### `scan_diff`

:raises: UnidiffParseError

```python
detect_secrets.SecretsCollection.scan_diff(self, diff: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `diff` | `str` | `—` | pos/kw |

### `scan_file`

```python
detect_secrets.SecretsCollection.scan_file(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |

### `scan_files`

Just like scan_file, but optimized through parallel processing.

```python
detect_secrets.SecretsCollection.scan_files(self, *filenames: str, num_processors: Optional[int] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `str` | `—` | *args |
| `num_processors` | `Optional` | `None` | kw |

### `trim`

Removes invalid entries in the current SecretsCollection.

This behaves *kinda* like set intersection and left-join. That is, for matching files,
a set intersection is performed. For non-matching fil…

```python
detect_secrets.SecretsCollection.trim(self, scanned_results: Optional[ForwardRef('SecretsCollection')] = None, filelist: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scanned_results` | `Optional` | `None` | pos/kw |
| `filelist` | `Optional` | `None` | pos/kw |

### `detect_secrets.audit.analytics.PotentialSecret` methods

### `hash_secret`

This offers a way to coherently test this class, without mocking self.secret_hash.

```python
detect_secrets.audit.analytics.PotentialSecret.hash_secret(secret: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

Custom JSON encoder

```python
detect_secrets.audit.analytics.PotentialSecret.json(self) -> Dict[str, Union[str, int, bool]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Union[str, int, bool]]`

### `load_secret_from_dict`

Custom JSON decoder

```python
detect_secrets.audit.analytics.PotentialSecret.load_secret_from_dict(data: Dict[str, Union[str, int, bool]]) -> 'PotentialSecret'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Dict` | `—` | pos/kw |

**Returns:** `PotentialSecret`

### `set_secret`

```python
detect_secrets.audit.analytics.PotentialSecret.set_secret(self, secret: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |

### `detect_secrets.audit.analytics.StatisticsAggregator` methods

### `json`

```python
detect_secrets.audit.analytics.StatisticsAggregator.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `record_secret`

```python
detect_secrets.audit.analytics.StatisticsAggregator.record_secret(self, secret: detect_secrets.core.potential_secret.PotentialSecret) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `PotentialSecret` | `—` | pos/kw |

### `detect_secrets.audit.analytics.StatisticsCounter` methods

### `calculate_precision`

```python
detect_secrets.audit.analytics.StatisticsCounter.calculate_precision(self) -> float
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'float'>`

### `calculate_recall`

```python
detect_secrets.audit.analytics.StatisticsCounter.calculate_recall(self) -> float
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'float'>`

### `json`

```python
detect_secrets.audit.analytics.StatisticsCounter.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `detect_secrets.audit.audit.BidirectionalIterator` methods

### `can_step_back`

```python
detect_secrets.audit.audit.BidirectionalIterator.can_step_back(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `next`

```python
detect_secrets.audit.audit.BidirectionalIterator.next(self) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Any`

### `step_back_on_next_iteration`

```python
detect_secrets.audit.audit.BidirectionalIterator.step_back_on_next_iteration(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `detect_secrets.audit.common.BasePlugin` methods

### `analyze_line`

This examines a line and finds all possible secret values in it.

```python
detect_secrets.audit.common.BasePlugin.analyze_line(self, filename: str, line: str, line_number: int = 0, context: detect_secrets.util.code_snippet.CodeSnippet = None, **kwargs: Any) -> Set[detect_secrets.core.potential_secret.PotentialSecret]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |
| `line_number` | `int` | `0` | pos/kw |
| `context` | `CodeSnippet` | `None` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `typing.Set[detect_secrets.core.potential_secret.PotentialSecret]`

### `analyze_string`

Yields all the raw secret values within a supplied string.

```python
detect_secrets.audit.common.BasePlugin.analyze_string(self, string: str) -> Generator[str, NoneType, NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `string` | `str` | `—` | pos/kw |

**Returns:** `typing.Generator[str, NoneType, NoneType]`

### `format_scan_result`

```python
detect_secrets.audit.common.BasePlugin.format_scan_result(self, secret: detect_secrets.core.potential_secret.PotentialSecret) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `PotentialSecret` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

```python
detect_secrets.audit.common.BasePlugin.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `verify`

```python
detect_secrets.audit.common.BasePlugin.verify(self, secret: str) -> detect_secrets.constants.VerifiedResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<enum 'VerifiedResult'>`

### `detect_secrets.audit.common.LineGetter` methods

### `open_file`

This is split up into a different function, so it can be overridden if necessary.

```python
detect_secrets.audit.common.LineGetter.open_file(self) -> Iterator[detect_secrets.types.NamedIO]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Iterator[detect_secrets.types.NamedIO]`

### `detect_secrets.audit.common.PotentialSecret` methods

### `hash_secret`

This offers a way to coherently test this class, without mocking self.secret_hash.

```python
detect_secrets.audit.common.PotentialSecret.hash_secret(secret: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

Custom JSON encoder

```python
detect_secrets.audit.common.PotentialSecret.json(self) -> Dict[str, Union[str, int, bool]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Union[str, int, bool]]`

### `load_secret_from_dict`

Custom JSON decoder

```python
detect_secrets.audit.common.PotentialSecret.load_secret_from_dict(data: Dict[str, Union[str, int, bool]]) -> 'PotentialSecret'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Dict` | `—` | pos/kw |

**Returns:** `PotentialSecret`

### `set_secret`

```python
detect_secrets.audit.common.PotentialSecret.set_secret(self, secret: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |

### `detect_secrets.audit.common.SecretsCollection` methods

### `exactly_equals`

```python
detect_secrets.audit.common.SecretsCollection.exactly_equals(self, other: Any) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `Any` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `json`

Custom JSON encoder

```python
detect_secrets.audit.common.SecretsCollection.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `load_from_baseline`

```python
detect_secrets.audit.common.SecretsCollection.load_from_baseline(baseline: Dict[str, Any]) -> 'SecretsCollection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |

**Returns:** `SecretsCollection`

### `merge`

We operate under an assumption that the latest results are always more accurate,
assuming that the baseline is created on the same repository. However, we cannot
merely discard the old results in fav…

```python
detect_secrets.audit.common.SecretsCollection.merge(self, old_results: 'SecretsCollection') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `old_results` | `SecretsCollection` | `—` | pos/kw |

### `scan_diff`

:raises: UnidiffParseError

```python
detect_secrets.audit.common.SecretsCollection.scan_diff(self, diff: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `diff` | `str` | `—` | pos/kw |

### `scan_file`

```python
detect_secrets.audit.common.SecretsCollection.scan_file(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |

### `scan_files`

Just like scan_file, but optimized through parallel processing.

```python
detect_secrets.audit.common.SecretsCollection.scan_files(self, *filenames: str, num_processors: Optional[int] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `str` | `—` | *args |
| `num_processors` | `Optional` | `None` | kw |

### `trim`

Removes invalid entries in the current SecretsCollection.

This behaves *kinda* like set intersection and left-join. That is, for matching files,
a set intersection is performed. For non-matching fil…

```python
detect_secrets.audit.common.SecretsCollection.trim(self, scanned_results: Optional[ForwardRef('SecretsCollection')] = None, filelist: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scanned_results` | `Optional` | `None` | pos/kw |
| `filelist` | `Optional` | `None` | pos/kw |

### `detect_secrets.audit.compare.BidirectionalIterator` methods

### `can_step_back`

```python
detect_secrets.audit.compare.BidirectionalIterator.can_step_back(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `next`

```python
detect_secrets.audit.compare.BidirectionalIterator.next(self) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Any`

### `step_back_on_next_iteration`

```python
detect_secrets.audit.compare.BidirectionalIterator.step_back_on_next_iteration(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `detect_secrets.audit.compare.PotentialSecret` methods

### `hash_secret`

This offers a way to coherently test this class, without mocking self.secret_hash.

```python
detect_secrets.audit.compare.PotentialSecret.hash_secret(secret: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

Custom JSON encoder

```python
detect_secrets.audit.compare.PotentialSecret.json(self) -> Dict[str, Union[str, int, bool]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Union[str, int, bool]]`

### `load_secret_from_dict`

Custom JSON decoder

```python
detect_secrets.audit.compare.PotentialSecret.load_secret_from_dict(data: Dict[str, Union[str, int, bool]]) -> 'PotentialSecret'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Dict` | `—` | pos/kw |

**Returns:** `PotentialSecret`

### `set_secret`

```python
detect_secrets.audit.compare.PotentialSecret.set_secret(self, secret: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |

### `detect_secrets.audit.compare.SecretsCollection` methods

### `exactly_equals`

```python
detect_secrets.audit.compare.SecretsCollection.exactly_equals(self, other: Any) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `Any` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `json`

Custom JSON encoder

```python
detect_secrets.audit.compare.SecretsCollection.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `load_from_baseline`

```python
detect_secrets.audit.compare.SecretsCollection.load_from_baseline(baseline: Dict[str, Any]) -> 'SecretsCollection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |

**Returns:** `SecretsCollection`

### `merge`

We operate under an assumption that the latest results are always more accurate,
assuming that the baseline is created on the same repository. However, we cannot
merely discard the old results in fav…

```python
detect_secrets.audit.compare.SecretsCollection.merge(self, old_results: 'SecretsCollection') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `old_results` | `SecretsCollection` | `—` | pos/kw |

### `scan_diff`

:raises: UnidiffParseError

```python
detect_secrets.audit.compare.SecretsCollection.scan_diff(self, diff: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `diff` | `str` | `—` | pos/kw |

### `scan_file`

```python
detect_secrets.audit.compare.SecretsCollection.scan_file(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |

### `scan_files`

Just like scan_file, but optimized through parallel processing.

```python
detect_secrets.audit.compare.SecretsCollection.scan_files(self, *filenames: str, num_processors: Optional[int] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `str` | `—` | *args |
| `num_processors` | `Optional` | `None` | kw |

### `trim`

Removes invalid entries in the current SecretsCollection.

This behaves *kinda* like set intersection and left-join. That is, for matching files,
a set intersection is performed. For non-matching fil…

```python
detect_secrets.audit.compare.SecretsCollection.trim(self, scanned_results: Optional[ForwardRef('SecretsCollection')] = None, filelist: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scanned_results` | `Optional` | `None` | pos/kw |
| `filelist` | `Optional` | `None` | pos/kw |

### `detect_secrets.audit.iterator.BidirectionalIterator` methods

### `can_step_back`

```python
detect_secrets.audit.iterator.BidirectionalIterator.can_step_back(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `next`

```python
detect_secrets.audit.iterator.BidirectionalIterator.next(self) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Any`

### `step_back_on_next_iteration`

```python
detect_secrets.audit.iterator.BidirectionalIterator.step_back_on_next_iteration(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `detect_secrets.audit.iterator.SecretsCollection` methods

### `exactly_equals`

```python
detect_secrets.audit.iterator.SecretsCollection.exactly_equals(self, other: Any) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `Any` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `json`

Custom JSON encoder

```python
detect_secrets.audit.iterator.SecretsCollection.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `load_from_baseline`

```python
detect_secrets.audit.iterator.SecretsCollection.load_from_baseline(baseline: Dict[str, Any]) -> 'SecretsCollection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |

**Returns:** `SecretsCollection`

### `merge`

We operate under an assumption that the latest results are always more accurate,
assuming that the baseline is created on the same repository. However, we cannot
merely discard the old results in fav…

```python
detect_secrets.audit.iterator.SecretsCollection.merge(self, old_results: 'SecretsCollection') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `old_results` | `SecretsCollection` | `—` | pos/kw |

### `scan_diff`

:raises: UnidiffParseError

```python
detect_secrets.audit.iterator.SecretsCollection.scan_diff(self, diff: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `diff` | `str` | `—` | pos/kw |

### `scan_file`

```python
detect_secrets.audit.iterator.SecretsCollection.scan_file(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |

### `scan_files`

Just like scan_file, but optimized through parallel processing.

```python
detect_secrets.audit.iterator.SecretsCollection.scan_files(self, *filenames: str, num_processors: Optional[int] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `str` | `—` | *args |
| `num_processors` | `Optional` | `None` | kw |

### `trim`

Removes invalid entries in the current SecretsCollection.

This behaves *kinda* like set intersection and left-join. That is, for matching files,
a set intersection is performed. For non-matching fil…

```python
detect_secrets.audit.iterator.SecretsCollection.trim(self, scanned_results: Optional[ForwardRef('SecretsCollection')] = None, filelist: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scanned_results` | `Optional` | `None` | pos/kw |
| `filelist` | `Optional` | `None` | pos/kw |

### `detect_secrets.audit.report.LineGetter` methods

### `open_file`

This is split up into a different function, so it can be overridden if necessary.

```python
detect_secrets.audit.report.LineGetter.open_file(self) -> Iterator[detect_secrets.types.NamedIO]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Iterator[detect_secrets.types.NamedIO]`

### `detect_secrets.constants.PotentialSecret` methods

### `hash_secret`

This offers a way to coherently test this class, without mocking self.secret_hash.

```python
detect_secrets.constants.PotentialSecret.hash_secret(secret: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

Custom JSON encoder

```python
detect_secrets.constants.PotentialSecret.json(self) -> Dict[str, Union[str, int, bool]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Union[str, int, bool]]`

### `load_secret_from_dict`

Custom JSON decoder

```python
detect_secrets.constants.PotentialSecret.load_secret_from_dict(data: Dict[str, Union[str, int, bool]]) -> 'PotentialSecret'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Dict` | `—` | pos/kw |

**Returns:** `PotentialSecret`

### `set_secret`

```python
detect_secrets.constants.PotentialSecret.set_secret(self, secret: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |

### `detect_secrets.core.baseline.SecretsCollection` methods

### `exactly_equals`

```python
detect_secrets.core.baseline.SecretsCollection.exactly_equals(self, other: Any) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `Any` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `json`

Custom JSON encoder

```python
detect_secrets.core.baseline.SecretsCollection.json(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `load_from_baseline`

```python
detect_secrets.core.baseline.SecretsCollection.load_from_baseline(baseline: Dict[str, Any]) -> 'SecretsCollection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `baseline` | `Dict` | `—` | pos/kw |

**Returns:** `SecretsCollection`

### `merge`

We operate under an assumption that the latest results are always more accurate,
assuming that the baseline is created on the same repository. However, we cannot
merely discard the old results in fav…

```python
detect_secrets.core.baseline.SecretsCollection.merge(self, old_results: 'SecretsCollection') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `old_results` | `SecretsCollection` | `—` | pos/kw |

### `scan_diff`

:raises: UnidiffParseError

```python
detect_secrets.core.baseline.SecretsCollection.scan_diff(self, diff: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `diff` | `str` | `—` | pos/kw |

### `scan_file`

```python
detect_secrets.core.baseline.SecretsCollection.scan_file(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `str` | `—` | pos/kw |

### `scan_files`

Just like scan_file, but optimized through parallel processing.

```python
detect_secrets.core.baseline.SecretsCollection.scan_files(self, *filenames: str, num_processors: Optional[int] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `str` | `—` | *args |
| `num_processors` | `Optional` | `None` | kw |

### `trim`

Removes invalid entries in the current SecretsCollection.

This behaves *kinda* like set intersection and left-join. That is, for matching files,
a set intersection is performed. For non-matching fil…

```python
detect_secrets.core.baseline.SecretsCollection.trim(self, scanned_results: Optional[ForwardRef('SecretsCollection')] = None, filelist: Optional[List[str]] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scanned_results` | `Optional` | `None` | pos/kw |
| `filelist` | `Optional` | `None` | pos/kw |

### `detect_secrets.core.log.CustomLogger` methods

### `addFilter`

Add the specified filter to this handler.

```python
detect_secrets.core.log.CustomLogger.addFilter(self, filter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filter` | `—` | `—` | pos/kw |

### `addHandler`

Add the specified handler to this logger.

```python
detect_secrets.core.log.CustomLogger.addHandler(self, hdlr)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `hdlr` | `—` | `—` | pos/kw |

### `callHandlers`

Pass a record to all relevant handlers.

Loop through all handlers for this logger and its parents in the
logger hierarchy. If no handler was found, output a one-off error
message to sys.stderr. Stop…

```python
detect_secrets.core.log.CustomLogger.callHandlers(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `critical`

Log 'msg % args' with severity 'CRITICAL'.

To pass exception information, use the keyword argument exc_info with
a true value, e.g.

logger.critical("Houston, we have a %s", "major disaster", exc_in…

```python
detect_secrets.core.log.CustomLogger.critical(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `debug`

Log 'msg % args' with severity 'DEBUG'.

To pass exception information, use the keyword argument exc_info with
a true value, e.g.

logger.debug("Houston, we have a %s", "thorny problem", exc_info=Tru…

```python
detect_secrets.core.log.CustomLogger.debug(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `error`

Log 'msg % args' with severity 'ERROR'.

To pass exception information, use the keyword argument exc_info with
a true value, e.g.

logger.error("Houston, we have a %s", "major problem", exc_info=True)

```python
detect_secrets.core.log.CustomLogger.error(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `exception`

Convenience method for logging an ERROR with exception information.

```python
detect_secrets.core.log.CustomLogger.exception(self, msg, *args, exc_info=True, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `exc_info` | `—` | `True` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `fatal`

Don't use this method, use critical() instead.

```python
detect_secrets.core.log.CustomLogger.fatal(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `filter`

Determine if a record is loggable by consulting all the filters.

The default is to allow the record to be logged; any filter can veto
this by returning a false value.
If a filter attached to a handl…

```python
detect_secrets.core.log.CustomLogger.filter(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `findCaller`

Find the stack frame of the caller so that we can note the source
file name, line number and function name.

```python
detect_secrets.core.log.CustomLogger.findCaller(self, stack_info=False, stacklevel=1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stack_info` | `—` | `False` | pos/kw |
| `stacklevel` | `—` | `1` | pos/kw |

### `getChild`

Get a logger which is a descendant to this one.

This is a convenience method, such that

logging.getLogger('abc').getChild('def.ghi')

is the same as

logging.getLogger('abc.def.ghi')

It's useful,…

```python
detect_secrets.core.log.CustomLogger.getChild(self, suffix)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `suffix` | `—` | `—` | pos/kw |

### `getChildren`

```python
detect_secrets.core.log.CustomLogger.getChildren(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `getEffectiveLevel`

Get the effective level for this logger.

Loop through this logger and its parents in the logger hierarchy,
looking for a non-zero logging level. Return the first one found.

```python
detect_secrets.core.log.CustomLogger.getEffectiveLevel(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle`

Call the handlers for the specified record.

This method is used for unpickled records received from a socket, as
well as those created locally. Logger-level filtering is applied.

```python
detect_secrets.core.log.CustomLogger.handle(self, record)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `record` | `—` | `—` | pos/kw |

### `hasHandlers`

See if this logger has any handlers configured.

Loop through all handlers for this logger and its parents in the
logger hierarchy. Return True if a handler was found, else False.
Stop searching up t…

```python
detect_secrets.core.log.CustomLogger.hasHandlers(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `info`

Log 'msg % args' with severity 'INFO'.

To pass exception information, use the keyword argument exc_info with
a true value, e.g.

logger.info("Houston, we have a %s", "notable problem", exc_info=True)

```python
detect_secrets.core.log.CustomLogger.info(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `isEnabledFor`

Is this logger enabled for level 'level'?

```python
detect_secrets.core.log.CustomLogger.isEnabledFor(self, level)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `level` | `—` | `—` | pos/kw |

### `log`

Log 'msg % args' with the integer severity 'level'.

To pass exception information, use the keyword argument exc_info with
a true value, e.g.

logger.log(level, "We have a %s", "mysterious problem",…

```python
detect_secrets.core.log.CustomLogger.log(self, level, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `level` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `makeRecord`

A factory method which can be overridden in subclasses to create
specialized LogRecords.

```python
detect_secrets.core.log.CustomLogger.makeRecord(self, name, level, fn, lno, msg, args, exc_info, func=None, extra=None, sinfo=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `level` | `—` | `—` | pos/kw |
| `fn` | `—` | `—` | pos/kw |
| `lno` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | pos/kw |
| `exc_info` | `—` | `—` | pos/kw |
| `func` | `—` | `None` | pos/kw |
| `extra` | `—` | `None` | pos/kw |
| `sinfo` | `—` | `None` | pos/kw |

### `removeFilter`

Remove the specified filter from this handler.

```python
detect_secrets.core.log.CustomLogger.removeFilter(self, filter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filter` | `—` | `—` | pos/kw |

### `removeHandler`

Remove the specified handler from this logger.

```python
detect_secrets.core.log.CustomLogger.removeHandler(self, hdlr)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `hdlr` | `—` | `—` | pos/kw |

### `setLevel`

Set the logging level of this logger.  level must be an int or a str.

```python
detect_secrets.core.log.CustomLogger.setLevel(self, level)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `level` | `—` | `—` | pos/kw |

### `set_debug_level`

:param debug_level: between 0-2, configure verbosity of log

```python
detect_secrets.core.log.CustomLogger.set_debug_level(self, debug_level: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `debug_level` | `int` | `—` | pos/kw |

### `warn`

```python
detect_secrets.core.log.CustomLogger.warn(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `warning`

Log 'msg % args' with severity 'WARNING'.

To pass exception information, use the keyword argument exc_info with
a true value, e.g.

logger.warning("Houston, we have a %s", "bit of a problem", exc_in…

```python
detect_secrets.core.log.CustomLogger.warning(self, msg, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `detect_secrets.core.potential_secret.PotentialSecret` methods

### `hash_secret`

This offers a way to coherently test this class, without mocking self.secret_hash.

```python
detect_secrets.core.potential_secret.PotentialSecret.hash_secret(secret: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

Custom JSON encoder

```python
detect_secrets.core.potential_secret.PotentialSecret.json(self) -> Dict[str, Union[str, int, bool]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Union[str, int, bool]]`

### `load_secret_from_dict`

Custom JSON decoder

```python
detect_secrets.core.potential_secret.PotentialSecret.load_secret_from_dict(data: Dict[str, Union[str, int, bool]]) -> 'PotentialSecret'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Dict` | `—` | pos/kw |

**Returns:** `PotentialSecret`

### `set_secret`

```python
detect_secrets.core.potential_secret.PotentialSecret.set_secret(self, secret: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `secret` | `str` | `—` | pos/kw |

### `detect_secrets.core.scan.CodeSnippet` methods

### `add_line_numbers`

```python
detect_secrets.core.scan.CodeSnippet.add_line_numbers(self) -> 'CodeSnippet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `CodeSnippet`

### `apply_highlight`

Broken out, for custom colorization.

```python
detect_secrets.core.scan.CodeSnippet.apply_highlight(self, payload: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `payload` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_line_number`

Broken out, for custom colorization.

```python
detect_secrets.core.scan.CodeSnippet.get_line_number(self, line_number: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line_number` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `highlight_line`

:param payload: string to highlight, on chosen line

```python
detect_secrets.core.scan.CodeSnippet.highlight_line(self, payload: str) -> 'CodeSnippet'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `payload` | `str` | `—` | pos/kw |

**Returns:** `CodeSnippet`

### `detect_secrets.core.scan.PotentialSecret` methods

### `hash_secret`

This offers a way to coherently test this class, without mocking self.secret_hash.

```python
detect_secrets.core.scan.PotentialSecret.hash_secret(secret: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secret` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `json`

Custom JSON encoder

```python
detect_secrets.core.scan.PotentialSecret.json(self) -> Dict[str, Union[str, int, bool]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Union[str, int, bool]]`

### `load_secret_from_dict`

Custom JSON decoder

```python
detect_secrets.core.scan.PotentialSecret.load_secret_from_dict(data: Dict[str, Union[str, int, bool]]) -> 'PotentialSecret'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Dict` | `—` | pos/kw |

**Returns:** `PotentialSecret`


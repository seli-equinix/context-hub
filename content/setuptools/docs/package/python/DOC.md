---
name: package
description: "setuptools packaging backend and build configuration guide for Python projects"
metadata:
  languages: "python"
  versions: "82.0.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "setuptools,python,packaging,build,pyproject,wheel,sdist,toml,setup,main,Version-Sensitive,Command,announce,copy_file,copy_tree,debug_print,dump_options,ensure_dirname,ensure_filename,ensure_finalized,ensure_string,ensure_string_list,execute,finalize_options,get_command_name,get_finalized_command,get_sub_commands,initialize_options,make_archive,make_file,mkpath,move_file,reinitialize_command,run,run_command,set_undefined_options,spawn,warn,Distribution,dump_option_dicts,exclude,exclude_package,fetch_build_egg,fetch_build_eggs,find_config_files,get_cmdline_options,get_command_class,get_command_list,get_command_obj,get_command_packages,get_egg_cache_dir,get_option_dict,handle_display_options,has_c_libraries,has_contents_for,has_data_files,has_ext_modules,has_headers,has_modules,has_pure_modules,has_scripts,include,is_pure,iter_distribution_names,parse_command_line,parse_config_files,print_command_list,Extension,PEP420PackageFinder,find,PackageFinder,Require,full_name,get_version,is_current,is_present,version_ok,SetuptoolsDeprecationWarning,emit,findall,sic,UnrecognizedFormat,default_filter,ensure_directory,unpack_archive,unpack_directory,unpack_tarfile,unpack_zipfile,patch,SetupRequirementsError,no_install_setup_requires,parse_strings,same_path,suppress_known_deprecation,alias,config_file,edit_config,format_alias,option_base,shquote"
---

# setuptools — package

Extensions to the 'distutils' for large or complex distributions

## Install

```bash
pip install setuptools
```

## Imports

```python
import setuptools
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Command` | Class | Setuptools internal actions are organized using a *command design pattern*. Thi… |
| `announce` | Method |  |
| `copy_file` | Method | Copy a file respecting verbose, dry-run and force flags.  (The former two defau… |
| `copy_tree` | Method | Copy an entire directory tree respecting verbose, dry-run, and force flags. |
| `debug_print` | Method | Print 'msg' to stdout if the global DEBUG (taken from the DISTUTILS_DEBUG envir… |
| `dump_options` | Method |  |
| `ensure_dirname` | Method |  |
| `ensure_filename` | Method | Ensure that 'option' is the name of an existing file. |
| `ensure_finalized` | Method |  |
| `ensure_string` | Method | Ensure that 'option' is a string; if not defined, set it to 'default'. |
| `ensure_string_list` | Method | Ensure that 'option' is a list of strings.  If 'option' is currently a string,… |
| `execute` | Method |  |
| `finalize_options` | Method | Set final values for all options/attributes used by the command. Most of the ti… |
| `get_command_name` | Method |  |
| `get_finalized_command` | Method | Wrapper around Distribution's 'get_command_obj()' method: find (create if neces… |
| `get_sub_commands` | Method | Determine the sub-commands that are relevant in the current distribution (ie.,… |
| `initialize_options` | Method | Set or (reset) all options/attributes/caches used by the command to their defau… |
| `make_archive` | Method |  |
| `make_file` | Method | Special case of 'execute()' for operations that process one or more input files… |
| `mkpath` | Method |  |
| `move_file` | Method | Move a file respecting dry-run flag. |
| `reinitialize_command` | Method |  |
| `run` | Method | Execute the actions intended by the command. (Side effects **SHOULD** only take… |
| `run_command` | Method | Run some other command: uses the 'run_command()' method of Distribution, which… |
| `set_undefined_options` | Method | Set the values of any "undefined" options from corresponding option values in s… |
| `spawn` | Method | Spawn an external command respecting dry-run flag. |
| `warn` | Method |  |
| `Distribution` | Class | Distribution with support for tests and package data  This is an enhanced versi… |
| `announce` | Method |  |
| `dump_option_dicts` | Method |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `Command`

Setuptools internal actions are organized using a *command design pattern*.
This means that each action (or group of closely related actions) executed during
the build should be implemented as a ``Co…

```python
setuptools.Command(self, dist: 'Distribution', **kw) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `Distribution` | `—` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

### `Distribution`

Distribution with support for tests and package data

This is an enhanced version of 'distutils.dist.Distribution' that
effectively adds the following new optional keyword arguments to 'setup()':

 '…

```python
setuptools.Distribution(self, attrs: 'MutableMapping[str, Any] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `attrs` | `MutableMapping[str, Any] \| None` | `None` | pos/kw |

### `Extension`

Describes a single extension module.

This means that all source files will be compiled into a single binary file
``<module path>.<suffix>`` (with ``<module path>`` derived from ``name`` and
``<suffi…

```python
setuptools.Extension(self, name: 'str', sources: 'Iterable[StrPath]', *args, py_limited_api: 'bool' = False, **kw) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `sources` | `Iterable[StrPath]` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `py_limited_api` | `bool` | `False` | kw |
| `kw` | `—` | `—` | **kwargs |

### `PEP420PackageFinder`

Generate a list of all Python packages found within a directory

```python
setuptools.PEP420PackageFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PackageFinder`

Generate a list of all Python packages found within a directory

```python
setuptools.PackageFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Require`

A prerequisite to building or installing a distribution

```python
setuptools.Require(self, name, requested_version, module, homepage: 'str' = '', attribute=None, format=None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `requested_version` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |
| `homepage` | `str` | `''` | pos/kw |
| `attribute` | `—` | `None` | pos/kw |
| `format` | `—` | `None` | pos/kw |

### `SetuptoolsDeprecationWarning`

Base class for warning deprecations in ``setuptools``

This class is not derived from ``DeprecationWarning``, and as such is
visible by default.

```python
setuptools.SetuptoolsDeprecationWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `sic`

Treat this string as-is (https://en.wikipedia.org/wiki/Sic)

```python
setuptools.sic(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnrecognizedFormat`

Couldn't recognize the archive type

```python
setuptools.archive_util.UnrecognizedFormat(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Distribution`

Distribution with support for tests and package data

This is an enhanced version of 'distutils.dist.Distribution' that
effectively adds the following new optional keyword arguments to 'setup()':

 '…

```python
setuptools.build_meta.Distribution(self, attrs: 'MutableMapping[str, Any] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `attrs` | `MutableMapping[str, Any] \| None` | `None` | pos/kw |

### `SetupRequirementsError`

Common base class for all exceptions

```python
setuptools.build_meta.SetupRequirementsError(self, specifiers) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `specifiers` | `—` | `—` | pos/kw |

### `SetuptoolsDeprecationWarning`

Base class for warning deprecations in ``setuptools``

This class is not derived from ``DeprecationWarning``, and as such is
visible by default.

```python
setuptools.build_meta.SetuptoolsDeprecationWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `alias`

Define a shortcut that invokes one or more commands

```python
setuptools.command.alias.alias(self, dist: 'Distribution', **kw) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `Distribution` | `—` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

### `option_base`

Abstract base class for commands that mess with config files

```python
setuptools.command.alias.option_base(self, dist: 'Distribution', **kw) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `Distribution` | `—` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

### `Command`

Setuptools internal actions are organized using a *command design pattern*.
This means that each action (or group of closely related actions) executed during
the build should be implemented as a ``Co…

```python
setuptools.command.bdist_egg.Command(self, dist: 'Distribution', **kw) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dist` | `Distribution` | `—` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

## Functions

### `findall`

Find all files under 'dir' and return the list of full filenames.
Unless dir is '.', return full filenames with dir prepended.

```python
setuptools.findall(dir='.')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dir` | `—` | `'.'` | pos/kw |

### `setup`

The gateway to the Distutils: do everything your setup script needs
to do, in a highly flexible and user-driven way.  Briefly: create a
Distribution instance; find and parse config files; parse the c…

```python
setuptools.setup(**attrs) -> 'Distribution'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `attrs` | `—` | `—` | **kwargs |

**Returns:** `Distribution`

### `default_filter`

The default progress/filter callback; returns True for all files

```python
setuptools.archive_util.default_filter(src, dst)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `dst` | `—` | `—` | pos/kw |

### `ensure_directory`

Ensure that the parent directory of `path` exists

```python
setuptools.archive_util.ensure_directory(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `unpack_archive`

Unpack `filename` to `extract_dir`, or raise ``UnrecognizedFormat``

`progress_filter` is a function taking two arguments: a source path
internal to the archive ('/'-separated), and a filesystem path…

```python
setuptools.archive_util.unpack_archive(filename, extract_dir, progress_filter=<function default_filter at 0x7b06805e62a0>, drivers=None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `extract_dir` | `—` | `—` | pos/kw |
| `progress_filter` | `—` | `<function default_filter at 0x7b06805e62a0>` | pos/kw |
| `drivers` | `—` | `None` | pos/kw |

### `unpack_directory`

"Unpack" a directory, using the same interface as for archives

Raises ``UnrecognizedFormat`` if `filename` is not a directory

```python
setuptools.archive_util.unpack_directory(filename, extract_dir, progress_filter=<function default_filter at 0x7b06805e62a0>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `extract_dir` | `—` | `—` | pos/kw |
| `progress_filter` | `—` | `<function default_filter at 0x7b06805e62a0>` | pos/kw |

### `unpack_tarfile`

Unpack tar/tar.gz/tar.bz2 `filename` to `extract_dir`

Raises ``UnrecognizedFormat`` if `filename` is not a tarfile (as determined
by ``tarfile.open()``).  See ``unpack_archive()`` for an explanation…

```python
setuptools.archive_util.unpack_tarfile(filename, extract_dir, progress_filter=<function default_filter at 0x7b06805e62a0>) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `extract_dir` | `—` | `—` | pos/kw |
| `progress_filter` | `—` | `<function default_filter at 0x7b06805e62a0>` | pos/kw |

**Returns:** `<class 'bool'>`

### `unpack_zipfile`

Unpack zip `filename` to `extract_dir`

Raises ``UnrecognizedFormat`` if `filename` is not a zipfile (as determined
by ``zipfile.is_zipfile()``).  See ``unpack_archive()`` for an explanation
of the `…

```python
setuptools.archive_util.unpack_zipfile(filename, extract_dir, progress_filter=<function default_filter at 0x7b06805e62a0>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `extract_dir` | `—` | `—` | pos/kw |
| `progress_filter` | `—` | `<function default_filter at 0x7b06805e62a0>` | pos/kw |

### `no_install_setup_requires`

Temporarily disable installing setup_requires

Under PEP 517, the backend reports build dependencies to the frontend,
and the frontend is responsible for ensuring they're installed.
So setuptools (ac…

```python
setuptools.build_meta.no_install_setup_requires()
```

### `parse_strings`

Yield requirement strings for each specification in `strs`.

`strs` must be a string, or a (possibly-nested) iterable thereof.

```python
setuptools.build_meta.parse_strings(strs: '_StrOrIter') -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `strs` | `_StrOrIter` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `same_path`

Differs from os.path.samefile because it does not require paths to exist.
Purely string based (no comparison between i-nodes).
>>> same_path("a/b", "./a/b")
True
>>> same_path("a/b", "a/./b")
True
>>…

```python
setuptools.build_meta.same_path(p1: 'StrPath', p2: 'StrPath') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `p1` | `StrPath` | `—` | pos/kw |
| `p2` | `StrPath` | `—` | pos/kw |

**Returns:** `bool`

### `suppress_known_deprecation`

```python
setuptools.build_meta.suppress_known_deprecation()
```

### `config_file`

Get the filename of the distutils, local, global, or per-user config

`kind` must be one of "local", "global", or "user"

```python
setuptools.command.alias.config_file(kind='local')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kind` | `—` | `'local'` | pos/kw |

### `edit_config`

Edit a configuration file to include `settings`

`settings` is a dictionary of dictionaries or ``None`` values, keyed by
command/section name.  A ``None`` value means to delete the entire section,
wh…

```python
setuptools.command.alias.edit_config(filename, settings) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `settings` | `—` | `—` | pos/kw |

### `format_alias`

```python
setuptools.command.alias.format_alias(name, aliases)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `aliases` | `—` | `—` | pos/kw |

### `shquote`

Quote an argument for later parsing by shlex.split()

```python
setuptools.command.alias.shquote(arg)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `arg` | `—` | `—` | pos/kw |

## Methods

### `setuptools.Command` methods

### `announce`

```python
setuptools.Command.announce(self, msg: 'object', level: 'int' = 10) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |
| `level` | `int` | `10` | pos/kw |

### `copy_file`

Copy a file respecting verbose, dry-run and force flags.  (The
former two default to whatever is in the Distribution object, and
the latter defaults to false for commands that don't define it.)

```python
setuptools.Command.copy_file(self, infile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, link: 'str | None' = None, level: 'int' = 1) -> 'tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `link` | `str \| None` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]`

### `copy_tree`

Copy an entire directory tree respecting verbose, dry-run,
and force flags.

```python
setuptools.Command.copy_tree(self, infile: 'str | os.PathLike[str]', outfile: 'str', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, preserve_symlinks: 'bool' = False, level: 'int' = 1) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `outfile` | `str` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `preserve_symlinks` | `bool` | `False` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `list[str]`

### `debug_print`

Print 'msg' to stdout if the global DEBUG (taken from the
DISTUTILS_DEBUG environment variable) flag is true.

```python
setuptools.Command.debug_print(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `dump_options`

```python
setuptools.Command.dump_options(self, header=None, indent='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `header` | `—` | `None` | pos/kw |
| `indent` | `—` | `''` | pos/kw |

### `ensure_dirname`

```python
setuptools.Command.ensure_dirname(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_filename`

Ensure that 'option' is the name of an existing file.

```python
setuptools.Command.ensure_filename(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_finalized`

```python
setuptools.Command.ensure_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_string`

Ensure that 'option' is a string; if not defined, set it to
'default'.

```python
setuptools.Command.ensure_string(self, option: 'str', default: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |
| `default` | `str \| None` | `None` | pos/kw |

### `ensure_string_list`

Ensure that 'option' is a list of strings.  If 'option' is
currently a string, we split it either on /,\s*/ or /\s+/, so
"foo bar baz", "foo,bar,baz", and "foo,   bar baz" all become
["foo", "bar", "…

```python
setuptools.Command.ensure_string_list(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `execute`

```python
setuptools.Command.execute(self, func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `finalize_options`

Set final values for all options/attributes used by the command.
Most of the time, each option/attribute/cache should only be set if it does not
have any value yet (e.g. ``if self.attr is None: self.…

```python
setuptools.Command.finalize_options(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_command_name`

```python
setuptools.Command.get_command_name(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_finalized_command`

Wrapper around Distribution's 'get_command_obj()' method: find
(create if necessary and 'create' is true) the command object for
'command', call its 'ensure_finalized()' method, and return the
finali…

```python
setuptools.Command.get_finalized_command(self, command: 'str', create: 'bool' = True) -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |
| `create` | `bool` | `True` | pos/kw |

**Returns:** `Command`

### `get_sub_commands`

Determine the sub-commands that are relevant in the current
distribution (ie., that need to be run).  This is based on the
'sub_commands' class attribute: each tuple in that list may include
a method…

```python
setuptools.Command.get_sub_commands(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `initialize_options`

Set or (reset) all options/attributes/caches used by the command
to their default values. Note that these values may be overwritten during
the build.

```python
setuptools.Command.initialize_options(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `make_archive`

```python
setuptools.Command.make_archive(self, base_name: 'str | os.PathLike[str]', format: 'str', root_dir: 'str | os.PathLike[str] | bytes | os.PathLike[bytes] | None' = None, base_dir: 'str | None' = None, owner: 'str | None' = None, group: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `base_name` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `format` | `str` | `—` | pos/kw |
| `root_dir` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes] \| None` | `None` | pos/kw |
| `base_dir` | `str \| None` | `None` | pos/kw |
| `owner` | `str \| None` | `None` | pos/kw |
| `group` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `make_file`

Special case of 'execute()' for operations that process one or
more input files and generate one output file.  Works just like
'execute()', except the operation is skipped and a different
message pri…

```python
setuptools.Command.make_file(self, infiles: 'str | list[str] | tuple[str, ...]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', exec_msg: 'object' = None, skip_msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infiles` | `str \| list[str] \| tuple[str, ...]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `exec_msg` | `object` | `None` | pos/kw |
| `skip_msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `mkpath`

```python
setuptools.Command.mkpath(self, name: 'str', mode: 'int' = 511) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `mode` | `int` | `511` | pos/kw |

### `move_file`

Move a file respecting dry-run flag.

```python
setuptools.Command.move_file(self, src: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', dst: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', level: 'int' = 1) -> 'str | os.PathLike[str] | bytes | os.PathLike[bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `dst` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `str | os.PathLike[str] | bytes | os.PathLike[bytes]`

### `reinitialize_command`

```python
setuptools.Command.reinitialize_command(self, command: 'str | _Command', reinit_subcommands: 'bool' = False, **kw) -> 'Command | _Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| _Command` | `—` | pos/kw |
| `reinit_subcommands` | `bool` | `False` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

**Returns:** `Command | _Command`

### `run`

Execute the actions intended by the command.
(Side effects **SHOULD** only take place when :meth:`run` is executed,
for example, creating new files or writing to the terminal output).

```python
setuptools.Command.run(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_command`

Run some other command: uses the 'run_command()' method of
Distribution, which creates and finalizes the command object if
necessary and then invokes its 'run()' method.

```python
setuptools.Command.run_command(self, command: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

### `set_undefined_options`

Set the values of any "undefined" options from corresponding
option values in some other command object.  "Undefined" here means
"is None", which is the convention used to indicate that an option
has…

```python
setuptools.Command.set_undefined_options(self, src_cmd: 'str', *option_pairs: 'tuple[str, str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src_cmd` | `str` | `—` | pos/kw |
| `option_pairs` | `tuple[str, str]` | `—` | *args |

### `spawn`

Spawn an external command respecting dry-run flag.

```python
setuptools.Command.spawn(self, cmd: 'MutableSequence[str]', search_path: 'bool' = True, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `MutableSequence[str]` | `—` | pos/kw |
| `search_path` | `bool` | `True` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `warn`

```python
setuptools.Command.warn(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `setuptools.Distribution` methods

### `announce`

```python
setuptools.Distribution.announce(self, msg, level: 'int' = 20) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `level` | `int` | `20` | pos/kw |

### `dump_option_dicts`

```python
setuptools.Distribution.dump_option_dicts(self, header=None, commands=None, indent: 'str' = '') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `header` | `—` | `None` | pos/kw |
| `commands` | `—` | `None` | pos/kw |
| `indent` | `str` | `''` | pos/kw |

### `exclude`

Remove items from distribution that are named in keyword arguments

For example, 'dist.exclude(py_modules=["x"])' would remove 'x' from
the distribution's 'py_modules' attribute.  Excluding packages…

```python
setuptools.Distribution.exclude(self, **attrs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attrs` | `—` | `—` | **kwargs |

### `exclude_package`

Remove packages, modules, and extensions in named package

```python
setuptools.Distribution.exclude_package(self, package: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `str` | `—` | pos/kw |

### `fetch_build_egg`

Fetch an egg needed for building

```python
setuptools.Distribution.fetch_build_egg(self, req)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req` | `—` | `—` | pos/kw |

### `fetch_build_eggs`

Resolve pre-setup requirements

```python
setuptools.Distribution.fetch_build_eggs(self, requires: '_StrOrIter') -> 'list[metadata.Distribution]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `requires` | `_StrOrIter` | `—` | pos/kw |

**Returns:** `list[metadata.Distribution]`

### `finalize_options`

Allow plugins to apply arbitrary operations to the
distribution. Each hook may optionally define a 'order'
to influence the order of execution. Smaller numbers
go first and the default is 0.

```python
setuptools.Distribution.finalize_options(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_config_files`

Find as many configuration files as should be processed for this
platform, and return a list of filenames in the order in which they
should be parsed.  The filenames returned are guaranteed to exist…

```python
setuptools.Distribution.find_config_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_cmdline_options`

Return a '{cmd: {opt:val}}' map of all command-line options

Option names are all long, but do not include the leading '--', and
contain dashes rather than underscores.  If the option doesn't take
an…

```python
setuptools.Distribution.get_cmdline_options(self) -> 'dict[str, dict[str, str | None]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, dict[str, str | None]]`

### `get_command_class`

Pluggable version of get_command_class()

```python
setuptools.Distribution.get_command_class(self, command: 'str') -> 'type[distutils.cmd.Command]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

**Returns:** `type[distutils.cmd.Command]`

### `get_command_list`

Get a list of (command, description) tuples.
The list is divided into "standard commands" (listed in
distutils.command.__all__) and "extra commands" (mentioned in
self.cmdclass, but not a standard co…

```python
setuptools.Distribution.get_command_list(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_command_obj`

Return the command object for 'command'.  Normally this object
is cached on a previous call to 'get_command_obj()'; if no command
object for 'command' is in the cache, then we either create and
retur…

```python
setuptools.Distribution.get_command_obj(self, command: 'str', create: 'bool' = True) -> 'Command | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |
| `create` | `bool` | `True` | pos/kw |

**Returns:** `Command | None`

### `get_command_packages`

Return a list of packages from which commands are loaded.

```python
setuptools.Distribution.get_command_packages(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_egg_cache_dir`

```python
setuptools.Distribution.get_egg_cache_dir(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_option_dict`

Get the option dictionary for a given command.  If that
command's option dictionary hasn't been created yet, then create it
and return the new dictionary; otherwise, return the existing
option dictio…

```python
setuptools.Distribution.get_option_dict(self, command)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `—` | `—` | pos/kw |

### `handle_display_options`

If there were any non-global "display-only" options
(--help-commands or the metadata display options) on the command
line, display the requested info and return true; else return
false.

```python
setuptools.Distribution.handle_display_options(self, option_order)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option_order` | `—` | `—` | pos/kw |

### `has_c_libraries`

```python
setuptools.Distribution.has_c_libraries(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_contents_for`

Return true if 'exclude_package(package)' would do something

```python
setuptools.Distribution.has_contents_for(self, package: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `has_data_files`

```python
setuptools.Distribution.has_data_files(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_ext_modules`

```python
setuptools.Distribution.has_ext_modules(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_headers`

```python
setuptools.Distribution.has_headers(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_modules`

```python
setuptools.Distribution.has_modules(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_pure_modules`

```python
setuptools.Distribution.has_pure_modules(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_scripts`

```python
setuptools.Distribution.has_scripts(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `include`

Add items to distribution that are named in keyword arguments

For example, 'dist.include(py_modules=["x"])' would add 'x' to
the distribution's 'py_modules' attribute, if it was not already
there.…

```python
setuptools.Distribution.include(self, **attrs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attrs` | `—` | `—` | **kwargs |

### `is_pure`

```python
setuptools.Distribution.is_pure(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `iter_distribution_names`

Yield all packages, modules, and extension names in distribution

```python
setuptools.Distribution.iter_distribution_names(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `parse_command_line`

Parse the setup script's command line, taken from the
'script_args' instance attribute (which defaults to 'sys.argv[1:]'
-- see 'setup()' in core.py).  This list is first processed for
"global option…

```python
setuptools.Distribution.parse_command_line(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `parse_config_files`

Parses configuration files from various levels
and loads configuration.

```python
setuptools.Distribution.parse_config_files(self, filenames: 'Iterable[StrPath] | None' = None, ignore_option_errors: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `Iterable[StrPath] \| None` | `None` | pos/kw |
| `ignore_option_errors` | `bool` | `False` | pos/kw |

### `print_command_list`

Print a subset of the list of all commands -- used by
'print_commands()'.

```python
setuptools.Distribution.print_command_list(self, commands, header, max_length) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `commands` | `—` | `—` | pos/kw |
| `header` | `—` | `—` | pos/kw |
| `max_length` | `—` | `—` | pos/kw |

### `setuptools.PEP420PackageFinder` methods

### `find`

Return a list of all Python items (packages or modules, depending on
the finder implementation) found within directory ``where``.

``where`` is the root directory which will be searched.
It should be…

```python
setuptools.PEP420PackageFinder.find(where: 'StrPath' = '.', exclude: 'Iterable[str]' = (), include: 'Iterable[str]' = ('*',)) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `where` | `StrPath` | `'.'` | pos/kw |
| `exclude` | `Iterable[str]` | `()` | pos/kw |
| `include` | `Iterable[str]` | `('*',)` | pos/kw |

**Returns:** `list[str]`

### `setuptools.PackageFinder` methods

### `find`

Return a list of all Python items (packages or modules, depending on
the finder implementation) found within directory ``where``.

``where`` is the root directory which will be searched.
It should be…

```python
setuptools.PackageFinder.find(where: 'StrPath' = '.', exclude: 'Iterable[str]' = (), include: 'Iterable[str]' = ('*',)) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `where` | `StrPath` | `'.'` | pos/kw |
| `exclude` | `Iterable[str]` | `()` | pos/kw |
| `include` | `Iterable[str]` | `('*',)` | pos/kw |

**Returns:** `list[str]`

### `setuptools.Require` methods

### `full_name`

Return full package/distribution name, w/version

```python
setuptools.Require.full_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_version`

Get version number of installed module, 'None', or 'default'

Search 'paths' for module.  If not found, return 'None'.  If found,
return the extracted version attribute, or 'default' if no version
at…

```python
setuptools.Require.get_version(self, paths=None, default: "_T | Literal['unknown']" = 'unknown') -> "_T | Literal['unknown'] | None | Any"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `paths` | `—` | `None` | pos/kw |
| `default` | `_T \| Literal['unknown']` | `'unknown'` | pos/kw |

**Returns:** `_T | Literal['unknown'] | None | Any`

### `is_current`

Return true if dependency is present and up-to-date on 'paths'

```python
setuptools.Require.is_current(self, paths=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `paths` | `—` | `None` | pos/kw |

### `is_present`

Return true if dependency is present on 'paths'

```python
setuptools.Require.is_present(self, paths=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `paths` | `—` | `None` | pos/kw |

### `version_ok`

Is 'version' sufficiently up-to-date?

```python
setuptools.Require.version_ok(self, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `setuptools.SetuptoolsDeprecationWarning` methods

### `emit`

Private: reserved for ``setuptools`` internal use only

```python
setuptools.SetuptoolsDeprecationWarning.emit(summary: 'str | None' = None, details: 'str | None' = None, due_date: '_DueDate | None' = None, see_docs: 'str | None' = None, see_url: 'str | None' = None, stacklevel: 'int' = 2, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `summary` | `str \| None` | `None` | pos/kw |
| `details` | `str \| None` | `None` | pos/kw |
| `due_date` | `_DueDate \| None` | `None` | pos/kw |
| `see_docs` | `str \| None` | `None` | pos/kw |
| `see_url` | `str \| None` | `None` | pos/kw |
| `stacklevel` | `int` | `2` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `setuptools.build_meta.Distribution` methods

### `announce`

```python
setuptools.build_meta.Distribution.announce(self, msg, level: 'int' = 20) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `level` | `int` | `20` | pos/kw |

### `dump_option_dicts`

```python
setuptools.build_meta.Distribution.dump_option_dicts(self, header=None, commands=None, indent: 'str' = '') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `header` | `—` | `None` | pos/kw |
| `commands` | `—` | `None` | pos/kw |
| `indent` | `str` | `''` | pos/kw |

### `exclude`

Remove items from distribution that are named in keyword arguments

For example, 'dist.exclude(py_modules=["x"])' would remove 'x' from
the distribution's 'py_modules' attribute.  Excluding packages…

```python
setuptools.build_meta.Distribution.exclude(self, **attrs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attrs` | `—` | `—` | **kwargs |

### `exclude_package`

Remove packages, modules, and extensions in named package

```python
setuptools.build_meta.Distribution.exclude_package(self, package: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `str` | `—` | pos/kw |

### `fetch_build_egg`

Fetch an egg needed for building

```python
setuptools.build_meta.Distribution.fetch_build_egg(self, req)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req` | `—` | `—` | pos/kw |

### `fetch_build_eggs`

Resolve pre-setup requirements

```python
setuptools.build_meta.Distribution.fetch_build_eggs(self, specifiers) -> 'NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `specifiers` | `—` | `—` | pos/kw |

**Returns:** `NoReturn`

### `finalize_options`

Allow plugins to apply arbitrary operations to the
distribution. Each hook may optionally define a 'order'
to influence the order of execution. Smaller numbers
go first and the default is 0.

```python
setuptools.build_meta.Distribution.finalize_options(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `find_config_files`

Find as many configuration files as should be processed for this
platform, and return a list of filenames in the order in which they
should be parsed.  The filenames returned are guaranteed to exist…

```python
setuptools.build_meta.Distribution.find_config_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_cmdline_options`

Return a '{cmd: {opt:val}}' map of all command-line options

Option names are all long, but do not include the leading '--', and
contain dashes rather than underscores.  If the option doesn't take
an…

```python
setuptools.build_meta.Distribution.get_cmdline_options(self) -> 'dict[str, dict[str, str | None]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, dict[str, str | None]]`

### `get_command_class`

Pluggable version of get_command_class()

```python
setuptools.build_meta.Distribution.get_command_class(self, command: 'str') -> 'type[distutils.cmd.Command]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

**Returns:** `type[distutils.cmd.Command]`

### `get_command_list`

Get a list of (command, description) tuples.
The list is divided into "standard commands" (listed in
distutils.command.__all__) and "extra commands" (mentioned in
self.cmdclass, but not a standard co…

```python
setuptools.build_meta.Distribution.get_command_list(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_command_obj`

Return the command object for 'command'.  Normally this object
is cached on a previous call to 'get_command_obj()'; if no command
object for 'command' is in the cache, then we either create and
retur…

```python
setuptools.build_meta.Distribution.get_command_obj(self, command: 'str', create: 'bool' = True) -> 'Command | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |
| `create` | `bool` | `True` | pos/kw |

**Returns:** `Command | None`

### `get_command_packages`

Return a list of packages from which commands are loaded.

```python
setuptools.build_meta.Distribution.get_command_packages(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_egg_cache_dir`

```python
setuptools.build_meta.Distribution.get_egg_cache_dir(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_option_dict`

Get the option dictionary for a given command.  If that
command's option dictionary hasn't been created yet, then create it
and return the new dictionary; otherwise, return the existing
option dictio…

```python
setuptools.build_meta.Distribution.get_option_dict(self, command)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `—` | `—` | pos/kw |

### `handle_display_options`

If there were any non-global "display-only" options
(--help-commands or the metadata display options) on the command
line, display the requested info and return true; else return
false.

```python
setuptools.build_meta.Distribution.handle_display_options(self, option_order)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option_order` | `—` | `—` | pos/kw |

### `has_c_libraries`

```python
setuptools.build_meta.Distribution.has_c_libraries(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_contents_for`

Return true if 'exclude_package(package)' would do something

```python
setuptools.build_meta.Distribution.has_contents_for(self, package: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `has_data_files`

```python
setuptools.build_meta.Distribution.has_data_files(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_ext_modules`

```python
setuptools.build_meta.Distribution.has_ext_modules(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_headers`

```python
setuptools.build_meta.Distribution.has_headers(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_modules`

```python
setuptools.build_meta.Distribution.has_modules(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_pure_modules`

```python
setuptools.build_meta.Distribution.has_pure_modules(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `has_scripts`

```python
setuptools.build_meta.Distribution.has_scripts(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `include`

Add items to distribution that are named in keyword arguments

For example, 'dist.include(py_modules=["x"])' would add 'x' to
the distribution's 'py_modules' attribute, if it was not already
there.…

```python
setuptools.build_meta.Distribution.include(self, **attrs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attrs` | `—` | `—` | **kwargs |

### `is_pure`

```python
setuptools.build_meta.Distribution.is_pure(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `iter_distribution_names`

Yield all packages, modules, and extension names in distribution

```python
setuptools.build_meta.Distribution.iter_distribution_names(self) -> 'Iterator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[str]`

### `parse_command_line`

Parse the setup script's command line, taken from the
'script_args' instance attribute (which defaults to 'sys.argv[1:]'
-- see 'setup()' in core.py).  This list is first processed for
"global option…

```python
setuptools.build_meta.Distribution.parse_command_line(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `parse_config_files`

Parses configuration files from various levels
and loads configuration.

```python
setuptools.build_meta.Distribution.parse_config_files(self, filenames: 'Iterable[StrPath] | None' = None, ignore_option_errors: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filenames` | `Iterable[StrPath] \| None` | `None` | pos/kw |
| `ignore_option_errors` | `bool` | `False` | pos/kw |

### `patch`

Replace
distutils.dist.Distribution with this class
for the duration of this context.

```python
setuptools.build_meta.Distribution.patch() -> 'Iterator[None]'
```

**Returns:** `Iterator[None]`

### `setuptools.build_meta.SetuptoolsDeprecationWarning` methods

### `emit`

Private: reserved for ``setuptools`` internal use only

```python
setuptools.build_meta.SetuptoolsDeprecationWarning.emit(summary: 'str | None' = None, details: 'str | None' = None, due_date: '_DueDate | None' = None, see_docs: 'str | None' = None, see_url: 'str | None' = None, stacklevel: 'int' = 2, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `summary` | `str \| None` | `None` | pos/kw |
| `details` | `str \| None` | `None` | pos/kw |
| `due_date` | `_DueDate \| None` | `None` | pos/kw |
| `see_docs` | `str \| None` | `None` | pos/kw |
| `see_url` | `str \| None` | `None` | pos/kw |
| `stacklevel` | `int` | `2` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `setuptools.command.alias.alias` methods

### `announce`

```python
setuptools.command.alias.alias.announce(self, msg: 'object', level: 'int' = 10) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |
| `level` | `int` | `10` | pos/kw |

### `copy_file`

Copy a file respecting verbose, dry-run and force flags.  (The
former two default to whatever is in the Distribution object, and
the latter defaults to false for commands that don't define it.)

```python
setuptools.command.alias.alias.copy_file(self, infile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, link: 'str | None' = None, level: 'int' = 1) -> 'tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `link` | `str \| None` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]`

### `copy_tree`

Copy an entire directory tree respecting verbose, dry-run,
and force flags.

```python
setuptools.command.alias.alias.copy_tree(self, infile: 'str | os.PathLike[str]', outfile: 'str', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, preserve_symlinks: 'bool' = False, level: 'int' = 1) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `outfile` | `str` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `preserve_symlinks` | `bool` | `False` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `list[str]`

### `debug_print`

Print 'msg' to stdout if the global DEBUG (taken from the
DISTUTILS_DEBUG environment variable) flag is true.

```python
setuptools.command.alias.alias.debug_print(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `dump_options`

```python
setuptools.command.alias.alias.dump_options(self, header=None, indent='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `header` | `—` | `None` | pos/kw |
| `indent` | `—` | `''` | pos/kw |

### `ensure_dirname`

```python
setuptools.command.alias.alias.ensure_dirname(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_filename`

Ensure that 'option' is the name of an existing file.

```python
setuptools.command.alias.alias.ensure_filename(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_finalized`

```python
setuptools.command.alias.alias.ensure_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_string`

Ensure that 'option' is a string; if not defined, set it to
'default'.

```python
setuptools.command.alias.alias.ensure_string(self, option: 'str', default: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |
| `default` | `str \| None` | `None` | pos/kw |

### `ensure_string_list`

Ensure that 'option' is a list of strings.  If 'option' is
currently a string, we split it either on /,\s*/ or /\s+/, so
"foo bar baz", "foo,bar,baz", and "foo,   bar baz" all become
["foo", "bar", "…

```python
setuptools.command.alias.alias.ensure_string_list(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `execute`

```python
setuptools.command.alias.alias.execute(self, func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `finalize_options`

Set final values for all options/attributes used by the command.
Most of the time, each option/attribute/cache should only be set if it does not
have any value yet (e.g. ``if self.attr is None: self.…

```python
setuptools.command.alias.alias.finalize_options(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_command_name`

```python
setuptools.command.alias.alias.get_command_name(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_finalized_command`

Wrapper around Distribution's 'get_command_obj()' method: find
(create if necessary and 'create' is true) the command object for
'command', call its 'ensure_finalized()' method, and return the
finali…

```python
setuptools.command.alias.alias.get_finalized_command(self, command: 'str', create: 'bool' = True) -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |
| `create` | `bool` | `True` | pos/kw |

**Returns:** `Command`

### `get_sub_commands`

Determine the sub-commands that are relevant in the current
distribution (ie., that need to be run).  This is based on the
'sub_commands' class attribute: each tuple in that list may include
a method…

```python
setuptools.command.alias.alias.get_sub_commands(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `initialize_options`

Set or (reset) all options/attributes/caches used by the command
to their default values. Note that these values may be overwritten during
the build.

```python
setuptools.command.alias.alias.initialize_options(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `make_archive`

```python
setuptools.command.alias.alias.make_archive(self, base_name: 'str | os.PathLike[str]', format: 'str', root_dir: 'str | os.PathLike[str] | bytes | os.PathLike[bytes] | None' = None, base_dir: 'str | None' = None, owner: 'str | None' = None, group: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `base_name` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `format` | `str` | `—` | pos/kw |
| `root_dir` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes] \| None` | `None` | pos/kw |
| `base_dir` | `str \| None` | `None` | pos/kw |
| `owner` | `str \| None` | `None` | pos/kw |
| `group` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `make_file`

Special case of 'execute()' for operations that process one or
more input files and generate one output file.  Works just like
'execute()', except the operation is skipped and a different
message pri…

```python
setuptools.command.alias.alias.make_file(self, infiles: 'str | list[str] | tuple[str, ...]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', exec_msg: 'object' = None, skip_msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infiles` | `str \| list[str] \| tuple[str, ...]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `exec_msg` | `object` | `None` | pos/kw |
| `skip_msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `mkpath`

```python
setuptools.command.alias.alias.mkpath(self, name: 'str', mode: 'int' = 511) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `mode` | `int` | `511` | pos/kw |

### `move_file`

Move a file respecting dry-run flag.

```python
setuptools.command.alias.alias.move_file(self, src: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', dst: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', level: 'int' = 1) -> 'str | os.PathLike[str] | bytes | os.PathLike[bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `dst` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `str | os.PathLike[str] | bytes | os.PathLike[bytes]`

### `reinitialize_command`

```python
setuptools.command.alias.alias.reinitialize_command(self, command: 'str | _Command', reinit_subcommands: 'bool' = False, **kw) -> 'Command | _Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| _Command` | `—` | pos/kw |
| `reinit_subcommands` | `bool` | `False` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

**Returns:** `Command | _Command`

### `run`

Execute the actions intended by the command.
(Side effects **SHOULD** only take place when :meth:`run` is executed,
for example, creating new files or writing to the terminal output).

```python
setuptools.command.alias.alias.run(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_command`

Run some other command: uses the 'run_command()' method of
Distribution, which creates and finalizes the command object if
necessary and then invokes its 'run()' method.

```python
setuptools.command.alias.alias.run_command(self, command: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

### `set_undefined_options`

Set the values of any "undefined" options from corresponding
option values in some other command object.  "Undefined" here means
"is None", which is the convention used to indicate that an option
has…

```python
setuptools.command.alias.alias.set_undefined_options(self, src_cmd: 'str', *option_pairs: 'tuple[str, str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src_cmd` | `str` | `—` | pos/kw |
| `option_pairs` | `tuple[str, str]` | `—` | *args |

### `spawn`

Spawn an external command respecting dry-run flag.

```python
setuptools.command.alias.alias.spawn(self, cmd: 'MutableSequence[str]', search_path: 'bool' = True, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `MutableSequence[str]` | `—` | pos/kw |
| `search_path` | `bool` | `True` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `warn`

```python
setuptools.command.alias.alias.warn(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `setuptools.command.alias.option_base` methods

### `announce`

```python
setuptools.command.alias.option_base.announce(self, msg: 'object', level: 'int' = 10) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |
| `level` | `int` | `10` | pos/kw |

### `copy_file`

Copy a file respecting verbose, dry-run and force flags.  (The
former two default to whatever is in the Distribution object, and
the latter defaults to false for commands that don't define it.)

```python
setuptools.command.alias.option_base.copy_file(self, infile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, link: 'str | None' = None, level: 'int' = 1) -> 'tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `link` | `str \| None` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]`

### `copy_tree`

Copy an entire directory tree respecting verbose, dry-run,
and force flags.

```python
setuptools.command.alias.option_base.copy_tree(self, infile: 'str | os.PathLike[str]', outfile: 'str', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, preserve_symlinks: 'bool' = False, level: 'int' = 1) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `outfile` | `str` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `preserve_symlinks` | `bool` | `False` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `list[str]`

### `debug_print`

Print 'msg' to stdout if the global DEBUG (taken from the
DISTUTILS_DEBUG environment variable) flag is true.

```python
setuptools.command.alias.option_base.debug_print(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `dump_options`

```python
setuptools.command.alias.option_base.dump_options(self, header=None, indent='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `header` | `—` | `None` | pos/kw |
| `indent` | `—` | `''` | pos/kw |

### `ensure_dirname`

```python
setuptools.command.alias.option_base.ensure_dirname(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_filename`

Ensure that 'option' is the name of an existing file.

```python
setuptools.command.alias.option_base.ensure_filename(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_finalized`

```python
setuptools.command.alias.option_base.ensure_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_string`

Ensure that 'option' is a string; if not defined, set it to
'default'.

```python
setuptools.command.alias.option_base.ensure_string(self, option: 'str', default: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |
| `default` | `str \| None` | `None` | pos/kw |

### `ensure_string_list`

Ensure that 'option' is a list of strings.  If 'option' is
currently a string, we split it either on /,\s*/ or /\s+/, so
"foo bar baz", "foo,bar,baz", and "foo,   bar baz" all become
["foo", "bar", "…

```python
setuptools.command.alias.option_base.ensure_string_list(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `execute`

```python
setuptools.command.alias.option_base.execute(self, func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `finalize_options`

Set final values for all options/attributes used by the command.
Most of the time, each option/attribute/cache should only be set if it does not
have any value yet (e.g. ``if self.attr is None: self.…

```python
setuptools.command.alias.option_base.finalize_options(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_command_name`

```python
setuptools.command.alias.option_base.get_command_name(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_finalized_command`

Wrapper around Distribution's 'get_command_obj()' method: find
(create if necessary and 'create' is true) the command object for
'command', call its 'ensure_finalized()' method, and return the
finali…

```python
setuptools.command.alias.option_base.get_finalized_command(self, command: 'str', create: 'bool' = True) -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |
| `create` | `bool` | `True` | pos/kw |

**Returns:** `Command`

### `get_sub_commands`

Determine the sub-commands that are relevant in the current
distribution (ie., that need to be run).  This is based on the
'sub_commands' class attribute: each tuple in that list may include
a method…

```python
setuptools.command.alias.option_base.get_sub_commands(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `initialize_options`

Set or (reset) all options/attributes/caches used by the command
to their default values. Note that these values may be overwritten during
the build.

```python
setuptools.command.alias.option_base.initialize_options(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `make_archive`

```python
setuptools.command.alias.option_base.make_archive(self, base_name: 'str | os.PathLike[str]', format: 'str', root_dir: 'str | os.PathLike[str] | bytes | os.PathLike[bytes] | None' = None, base_dir: 'str | None' = None, owner: 'str | None' = None, group: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `base_name` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `format` | `str` | `—` | pos/kw |
| `root_dir` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes] \| None` | `None` | pos/kw |
| `base_dir` | `str \| None` | `None` | pos/kw |
| `owner` | `str \| None` | `None` | pos/kw |
| `group` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `make_file`

Special case of 'execute()' for operations that process one or
more input files and generate one output file.  Works just like
'execute()', except the operation is skipped and a different
message pri…

```python
setuptools.command.alias.option_base.make_file(self, infiles: 'str | list[str] | tuple[str, ...]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', exec_msg: 'object' = None, skip_msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infiles` | `str \| list[str] \| tuple[str, ...]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `exec_msg` | `object` | `None` | pos/kw |
| `skip_msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `mkpath`

```python
setuptools.command.alias.option_base.mkpath(self, name: 'str', mode: 'int' = 511) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `mode` | `int` | `511` | pos/kw |

### `move_file`

Move a file respecting dry-run flag.

```python
setuptools.command.alias.option_base.move_file(self, src: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', dst: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', level: 'int' = 1) -> 'str | os.PathLike[str] | bytes | os.PathLike[bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `dst` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `str | os.PathLike[str] | bytes | os.PathLike[bytes]`

### `reinitialize_command`

```python
setuptools.command.alias.option_base.reinitialize_command(self, command: 'str | _Command', reinit_subcommands: 'bool' = False, **kw) -> 'Command | _Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| _Command` | `—` | pos/kw |
| `reinit_subcommands` | `bool` | `False` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

**Returns:** `Command | _Command`

### `run`

Execute the actions intended by the command.
(Side effects **SHOULD** only take place when :meth:`run` is executed,
for example, creating new files or writing to the terminal output).

```python
setuptools.command.alias.option_base.run(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_command`

Run some other command: uses the 'run_command()' method of
Distribution, which creates and finalizes the command object if
necessary and then invokes its 'run()' method.

```python
setuptools.command.alias.option_base.run_command(self, command: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |

### `set_undefined_options`

Set the values of any "undefined" options from corresponding
option values in some other command object.  "Undefined" here means
"is None", which is the convention used to indicate that an option
has…

```python
setuptools.command.alias.option_base.set_undefined_options(self, src_cmd: 'str', *option_pairs: 'tuple[str, str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src_cmd` | `str` | `—` | pos/kw |
| `option_pairs` | `tuple[str, str]` | `—` | *args |

### `spawn`

Spawn an external command respecting dry-run flag.

```python
setuptools.command.alias.option_base.spawn(self, cmd: 'MutableSequence[str]', search_path: 'bool' = True, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `MutableSequence[str]` | `—` | pos/kw |
| `search_path` | `bool` | `True` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `warn`

```python
setuptools.command.alias.option_base.warn(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `setuptools.command.bdist_egg.Command` methods

### `announce`

```python
setuptools.command.bdist_egg.Command.announce(self, msg: 'object', level: 'int' = 10) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |
| `level` | `int` | `10` | pos/kw |

### `copy_file`

Copy a file respecting verbose, dry-run and force flags.  (The
former two default to whatever is in the Distribution object, and
the latter defaults to false for commands that don't define it.)

```python
setuptools.command.bdist_egg.Command.copy_file(self, infile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, link: 'str | None' = None, level: 'int' = 1) -> 'tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `link` | `str \| None` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `tuple[str | os.PathLike[str] | bytes | os.PathLike[bytes], bool]`

### `copy_tree`

Copy an entire directory tree respecting verbose, dry-run,
and force flags.

```python
setuptools.command.bdist_egg.Command.copy_tree(self, infile: 'str | os.PathLike[str]', outfile: 'str', preserve_mode: 'bool' = True, preserve_times: 'bool' = True, preserve_symlinks: 'bool' = False, level: 'int' = 1) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infile` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `outfile` | `str` | `—` | pos/kw |
| `preserve_mode` | `bool` | `True` | pos/kw |
| `preserve_times` | `bool` | `True` | pos/kw |
| `preserve_symlinks` | `bool` | `False` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `list[str]`

### `debug_print`

Print 'msg' to stdout if the global DEBUG (taken from the
DISTUTILS_DEBUG environment variable) flag is true.

```python
setuptools.command.bdist_egg.Command.debug_print(self, msg: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `object` | `—` | pos/kw |

### `dump_options`

```python
setuptools.command.bdist_egg.Command.dump_options(self, header=None, indent='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `header` | `—` | `None` | pos/kw |
| `indent` | `—` | `''` | pos/kw |

### `ensure_dirname`

```python
setuptools.command.bdist_egg.Command.ensure_dirname(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_filename`

Ensure that 'option' is the name of an existing file.

```python
setuptools.command.bdist_egg.Command.ensure_filename(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `ensure_finalized`

```python
setuptools.command.bdist_egg.Command.ensure_finalized(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ensure_string`

Ensure that 'option' is a string; if not defined, set it to
'default'.

```python
setuptools.command.bdist_egg.Command.ensure_string(self, option: 'str', default: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |
| `default` | `str \| None` | `None` | pos/kw |

### `ensure_string_list`

Ensure that 'option' is a list of strings.  If 'option' is
currently a string, we split it either on /,\s*/ or /\s+/, so
"foo bar baz", "foo,bar,baz", and "foo,   bar baz" all become
["foo", "bar", "…

```python
setuptools.command.bdist_egg.Command.ensure_string_list(self, option: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option` | `str` | `—` | pos/kw |

### `execute`

```python
setuptools.command.bdist_egg.Command.execute(self, func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `finalize_options`

Set final values for all options/attributes used by the command.
Most of the time, each option/attribute/cache should only be set if it does not
have any value yet (e.g. ``if self.attr is None: self.…

```python
setuptools.command.bdist_egg.Command.finalize_options(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_command_name`

```python
setuptools.command.bdist_egg.Command.get_command_name(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_finalized_command`

Wrapper around Distribution's 'get_command_obj()' method: find
(create if necessary and 'create' is true) the command object for
'command', call its 'ensure_finalized()' method, and return the
finali…

```python
setuptools.command.bdist_egg.Command.get_finalized_command(self, command: 'str', create: 'bool' = True) -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str` | `—` | pos/kw |
| `create` | `bool` | `True` | pos/kw |

**Returns:** `Command`

### `get_sub_commands`

Determine the sub-commands that are relevant in the current
distribution (ie., that need to be run).  This is based on the
'sub_commands' class attribute: each tuple in that list may include
a method…

```python
setuptools.command.bdist_egg.Command.get_sub_commands(self) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[str]`

### `initialize_options`

Set or (reset) all options/attributes/caches used by the command
to their default values. Note that these values may be overwritten during
the build.

```python
setuptools.command.bdist_egg.Command.initialize_options(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `make_archive`

```python
setuptools.command.bdist_egg.Command.make_archive(self, base_name: 'str | os.PathLike[str]', format: 'str', root_dir: 'str | os.PathLike[str] | bytes | os.PathLike[bytes] | None' = None, base_dir: 'str | None' = None, owner: 'str | None' = None, group: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `base_name` | `str \| os.PathLike[str]` | `—` | pos/kw |
| `format` | `str` | `—` | pos/kw |
| `root_dir` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes] \| None` | `None` | pos/kw |
| `base_dir` | `str \| None` | `None` | pos/kw |
| `owner` | `str \| None` | `None` | pos/kw |
| `group` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `make_file`

Special case of 'execute()' for operations that process one or
more input files and generate one output file.  Works just like
'execute()', except the operation is skipped and a different
message pri…

```python
setuptools.command.bdist_egg.Command.make_file(self, infiles: 'str | list[str] | tuple[str, ...]', outfile: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', func: 'Callable[[Unpack[_Ts]], object]', args: 'tuple[Unpack[_Ts]]', exec_msg: 'object' = None, skip_msg: 'object' = None, level: 'int' = 1) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infiles` | `str \| list[str] \| tuple[str, ...]` | `—` | pos/kw |
| `outfile` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `func` | `Callable[[Unpack[_Ts]], object]` | `—` | pos/kw |
| `args` | `tuple[Unpack[_Ts]]` | `—` | pos/kw |
| `exec_msg` | `object` | `None` | pos/kw |
| `skip_msg` | `object` | `None` | pos/kw |
| `level` | `int` | `1` | pos/kw |

### `mkpath`

```python
setuptools.command.bdist_egg.Command.mkpath(self, name: 'str', mode: 'int' = 511) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `mode` | `int` | `511` | pos/kw |

### `move_file`

Move a file respecting dry-run flag.

```python
setuptools.command.bdist_egg.Command.move_file(self, src: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', dst: 'str | os.PathLike[str] | bytes | os.PathLike[bytes]', level: 'int' = 1) -> 'str | os.PathLike[str] | bytes | os.PathLike[bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `dst` | `str \| os.PathLike[str] \| bytes \| os.PathLike[bytes]` | `—` | pos/kw |
| `level` | `int` | `1` | pos/kw |

**Returns:** `str | os.PathLike[str] | bytes | os.PathLike[bytes]`

### `reinitialize_command`

```python
setuptools.command.bdist_egg.Command.reinitialize_command(self, command: 'str | _Command', reinit_subcommands: 'bool' = False, **kw) -> 'Command | _Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `command` | `str \| _Command` | `—` | pos/kw |
| `reinit_subcommands` | `bool` | `False` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

**Returns:** `Command | _Command`

### `run`

Execute the actions intended by the command.
(Side effects **SHOULD** only take place when :meth:`run` is executed,
for example, creating new files or writing to the terminal output).

```python
setuptools.command.bdist_egg.Command.run(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |


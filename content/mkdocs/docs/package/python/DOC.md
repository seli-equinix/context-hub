---
name: package
description: "MkDocs package guide for building and deploying Markdown documentation sites from Python projects"
metadata:
  languages: "python"
  versions: "1.6.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "mkdocs,python,documentation,static-site,markdown,Python-Markdown,Abort,format_message,show,BuildError,DuplicateFilter,File,copy_file,generated,is_css,is_documentation_page,is_javascript,is_media_file,is_modified,is_static_page,url_relative_to,Files,add_files_from_theme,append,copy_static_files,css_files,documentation_pages,get_file_from_path,javascript_files,media_files,remove,static_pages,InclusionLevel,Navigation,Page,read_source,render,validate_anchor_links,build,get_context,get_files,get_navigation,set_exclusions,site_directory_contains_stale_files,gh_deploy,new,LiveReloadServer,close_request,fileno,finish_request,get_app,get_request,handle_error,handle_request,handle_timeout,process_request,process_request_thread,serve,serve_forever,serve_request,server_activate,server_bind,server_close,service_actions,set_app,setup_environ,shutdown,shutdown_request,unwatch,verify_request,watch,load_config,Config,clear,copy,fromkeys,get,items,keys,load_dict,load_file,pop,popitem,set_defaults,setdefault,update,validate,values,BaseConfigOption,post_validation,pre_validation,reset_warnings,run_validation,LegacyConfig,ValidationError,weak_property,Choice,ConfigItems,ConfigurationError,Deprecated,DictOfItems,Dir,existence_test,DocsDir,EditURI"
---

# mkdocs — package

## Install

```bash
pip install mkdocs
```

## Imports

```python
import mkdocs
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Abort` | Class | Abort the build. |
| `format_message` | Method |  |
| `show` | Method |  |
| `BuildError` | Class | This error may be raised by MkDocs during the build process. Plugins should not… |
| `format_message` | Method |  |
| `show` | Method |  |
| `DuplicateFilter` | Class | Avoid logging duplicate messages. |
| `File` | Class | A MkDocs File object.  It represents how the contents of one file should be pop… |
| `copy_file` | Method | Copy source file to destination, ensuring parent directories exist. |
| `generated` | Method | Create a virtual file, backed either by in-memory `content` or by a file at `ab… |
| `is_css` | Method | Return True if file is a CSS file. |
| `is_documentation_page` | Method | Return True if file is a Markdown page. |
| `is_javascript` | Method | Return True if file is a JavaScript file. |
| `is_media_file` | Method | Return True if file is not a documentation or static page. |
| `is_modified` | Method |  |
| `is_static_page` | Method | Return True if file is a static page (HTML, XML, JSON). |
| `url_relative_to` | Method | Return url for file relative to other file. |
| `Files` | Class | A collection of [File][mkdocs.structure.files.File] objects. |
| `add_files_from_theme` | Method | Retrieve static files from Jinja environment and add to collection. |
| `append` | Method | Add file to the Files collection. |
| `copy_static_files` | Method | Copy static files from source to destination. |
| `css_files` | Method | Return iterable of all CSS file objects. |
| `documentation_pages` | Method | Return iterable of all Markdown page file objects. |
| `get_file_from_path` | Method | Return a File instance with File.src_uri equal to path. |
| `javascript_files` | Method | Return iterable of all javascript file objects. |
| `media_files` | Method | Return iterable of all file objects which are not documentation or static pages. |
| `remove` | Method | Remove file from Files collection. |
| `static_pages` | Method | Return iterable of all static page file objects. |
| `InclusionLevel` | Class | Create a collection of name/value pairs.  Example enumeration:  >>> class Color… |
| `Navigation` | Class |  |
| `Page` | Class | An item in MkDocs structure - see concrete subclasses Section, Page or Link. |
| `read_source` | Method |  |
| `render` | Method | Convert the Markdown source file to HTML as per the config. |
| `validate_anchor_links` | Method |  |
| `build` | Function | Perform a full site build. |
| `get_context` | Function | Return the template context for a given page or template. |
| `get_files` | Function | Walk the `docs_dir` and return a Files collection. |
| `get_navigation` | Function | Build site navigation from config and files. |
| `set_exclusions` | Function | Re-calculate which files are excluded, based on the patterns in the config. |
| `site_directory_contains_stale_files` | Function | Check if the site directory contains stale files from a previous build. |
| `Abort` | Class | Abort the build. |
| `format_message` | Method |  |
| `show` | Method |  |
| `gh_deploy` | Function |  |
| `new` | Function |  |
| `LiveReloadServer` | Class | Mix-in class to handle each request in a new thread. |
| `close_request` | Method | Called to clean up an individual request. |
| `fileno` | Method | Return socket file number.  Interface required by selector. |
| `finish_request` | Method | Finish one request by instantiating RequestHandlerClass. |
| `get_app` | Method |  |
| `get_request` | Method | Get the request and client address from the socket.  May be overridden. |
| `handle_error` | Method | Handle an error gracefully.  May be overridden.  The default is to print a trac… |
| `handle_request` | Method | Handle one request, possibly blocking.  Respects self.timeout. |
| `handle_timeout` | Method | Called if no new request arrives within self.timeout.  Overridden by ForkingMix… |
| `process_request` | Method | Start a new thread to process the request. |
| `process_request_thread` | Method | Same as in BaseServer but as a thread.  In addition, exception handling is done… |
| `serve` | Method |  |
| `serve_forever` | Method | Handle one request at a time until shutdown.  Polls for shutdown every poll_int… |
| `serve_request` | Method |  |
| `server_activate` | Method | Called by constructor to activate the server.  May be overridden. |
| `server_bind` | Method | Override server_bind to store the server name. |
| `server_close` | Method |  |
| `service_actions` | Method | Called by the serve_forever() loop.  May be overridden by a subclass / Mixin to… |
| `set_app` | Method |  |
| `setup_environ` | Method |  |
| `shutdown` | Method | Stops the serve_forever loop.  Blocks until the loop has finished. This must be… |
| `shutdown_request` | Method | Called to shutdown and close an individual request. |
| `unwatch` | Method | Stop watching file changes for path. Raises if there was no corresponding `watc… |
| `verify_request` | Method | Verify the request.  May be overridden.  Return True if we should proceed with… |
| `watch` | Method | Add the 'path' to watched paths, call the function and reload when any file cha… |
| `build` | Function | Perform a full site build. |
| `load_config` | Function | Load the configuration for a given file object or name.  The config_file can ei… |
| `serve` | Function | Start the MkDocs development server.  By default it will serve the documentatio… |
| `Config` | Class | Base class for MkDocs configuration, plugin configuration (and sub-configuratio… |
| `clear` | Method | D.clear() -> None.  Remove all items from D. |
| `copy` | Method |  |
| `fromkeys` | Method |  |
| `get` | Method | D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None. |
| `items` | Method | D.items() -> a set-like object providing a view on D's items |
| `keys` | Method | D.keys() -> a set-like object providing a view on D's keys |
| `load_dict` | Method | Load config options from a dictionary. |
| `load_file` | Method | Load config options from the open file descriptor of a YAML file. |
| `pop` | Method | D.pop(k[,d]) -> v, remove specified key and return the corresponding value. If… |
| `popitem` | Method | D.popitem() -> (k, v), remove and return some (key, value) pair as a 2-tuple; b… |
| `set_defaults` | Method | Set the base config by going through each validator and getting the default if… |
| `setdefault` | Method | D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D |
| `update` | Method | D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F. If E prese… |
| `validate` | Method |  |
| `values` | Method | D.values() -> an object providing a view on D's values |
| `load_config` | Function | Load the configuration for a given file object or name.  The config_file can ei… |
| `BaseConfigOption` | Class | Abstract base class for generic types.  On Python 3.12 and newer, generic class… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method |  |
| `Config` | Class | Base class for MkDocs configuration, plugin configuration (and sub-configuratio… |
| `clear` | Method | D.clear() -> None.  Remove all items from D. |
| `copy` | Method |  |
| `fromkeys` | Method |  |
| `get` | Method | D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None. |
| `items` | Method | D.items() -> a set-like object providing a view on D's items |
| `keys` | Method | D.keys() -> a set-like object providing a view on D's keys |
| `load_dict` | Method | Load config options from a dictionary. |
| `load_file` | Method | Load config options from the open file descriptor of a YAML file. |
| `pop` | Method | D.pop(k[,d]) -> v, remove specified key and return the corresponding value. If… |
| `popitem` | Method | D.popitem() -> (k, v), remove and return some (key, value) pair as a 2-tuple; b… |
| `set_defaults` | Method | Set the base config by going through each validator and getting the default if… |
| `setdefault` | Method | D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D |
| `update` | Method | D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F. If E prese… |
| `validate` | Method |  |
| `values` | Method | D.values() -> an object providing a view on D's values |
| `LegacyConfig` | Class | A configuration object for plugins, as just a dict without type-safe attribute… |
| `clear` | Method | D.clear() -> None.  Remove all items from D. |
| `copy` | Method |  |
| `fromkeys` | Method |  |
| `get` | Method | D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None. |
| `items` | Method | D.items() -> a set-like object providing a view on D's items |
| `keys` | Method | D.keys() -> a set-like object providing a view on D's keys |
| `load_dict` | Method | Load config options from a dictionary. |
| `load_file` | Method | Load config options from the open file descriptor of a YAML file. |
| `pop` | Method | D.pop(k[,d]) -> v, remove specified key and return the corresponding value. If… |
| `popitem` | Method | D.popitem() -> (k, v), remove and return some (key, value) pair as a 2-tuple; b… |
| `set_defaults` | Method | Set the base config by going through each validator and getting the default if… |
| `setdefault` | Method | D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D |
| `update` | Method | D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F. If E prese… |
| `validate` | Method |  |
| `values` | Method | D.values() -> an object providing a view on D's values |
| `ValidationError` | Class | Raised during the validation process of the config on errors. |
| `load_config` | Function | Load the configuration for a given file object or name.  The config_file can ei… |
| `weak_property` | Class | Same as a read-only property, but allows overwriting the field for good. |
| `BaseConfigOption` | Class | Abstract base class for generic types.  On Python 3.12 and newer, generic class… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method |  |
| `Choice` | Class | Choice Config Option.  Validate the config option against a strict set of value… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method | Perform some initial validation.  If the option is empty (None) and isn't requi… |
| `Config` | Class | Base class for MkDocs configuration, plugin configuration (and sub-configuratio… |
| `clear` | Method | D.clear() -> None.  Remove all items from D. |
| `copy` | Method |  |
| `fromkeys` | Method |  |
| `get` | Method | D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None. |
| `items` | Method | D.items() -> a set-like object providing a view on D's items |
| `keys` | Method | D.keys() -> a set-like object providing a view on D's keys |
| `load_dict` | Method | Load config options from a dictionary. |
| `load_file` | Method | Load config options from the open file descriptor of a YAML file. |
| `pop` | Method | D.pop(k[,d]) -> v, remove specified key and return the corresponding value. If… |
| `popitem` | Method | D.popitem() -> (k, v), remove and return some (key, value) pair as a 2-tuple; b… |
| `set_defaults` | Method | Set the base config by going through each validator and getting the default if… |
| `setdefault` | Method | D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D |
| `update` | Method | D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F. If E prese… |
| `validate` | Method |  |
| `values` | Method | D.values() -> an object providing a view on D's values |
| `ConfigItems` | Class | Deprecated: Use `ListOfItems(SubConfig(...))` instead of `ConfigItems(...)`.  V… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method |  |
| `ConfigurationError` | Class | This error is raised by configuration validation when a validation error is enc… |
| `format_message` | Method |  |
| `show` | Method |  |
| `Deprecated` | Class | Deprecated Config Option.  Raises a warning as the option is deprecated. Uses `… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method |  |
| `DictOfItems` | Class | Validates a dict of items. Keys are always strings.  E.g. for `config_options.D… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method |  |
| `Dir` | Class | Dir Config Option.  Validate a path to a directory, optionally verifying that i… |
| `existence_test` | Method | Return true if the pathname refers to an existing directory. |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method | Perform some initial validation.  If the option is empty (None) and isn't requi… |
| `DocsDir` | Class | Dir Config Option.  Validate a path to a directory, optionally verifying that i… |
| `existence_test` | Method | Return true if the pathname refers to an existing directory. |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method | Perform some initial validation.  If the option is empty (None) and isn't requi… |
| `EditURI` | Class | Type Config Option.  Validate the type of a config option against a given Pytho… |
| `post_validation` | Method | After all options have passed validation, perform a post-validation process to… |
| `pre_validation` | Method | Before all options are validated, perform a pre-validation process.  The pre-va… |
| `reset_warnings` | Method |  |
| `run_validation` | Method | Perform validation for a value.  The run_validation method should be implemente… |
| `validate` | Method | Perform some initial validation.  If the option is empty (None) and isn't requi… |

## Classes

### `Abort`

Abort the build.

```python
mkdocs.commands.build.Abort(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `BuildError`

This error may be raised by MkDocs during the build process. Plugins should
not raise this error.

```python
mkdocs.commands.build.BuildError(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `DuplicateFilter`

Avoid logging duplicate messages.

```python
mkdocs.commands.build.DuplicateFilter(self) -> 'None'
```

### `File`

A MkDocs File object.

It represents how the contents of one file should be populated in the destination site.

A file always has its `abs_dest_path` (obtained by joining `dest_dir` and `dest_path`),…

```python
mkdocs.commands.build.File(self, path: 'str', src_dir: 'str | None', dest_dir: 'str', use_directory_urls: 'bool', *, dest_uri: 'str | None' = None, inclusion: 'InclusionLevel' = <InclusionLevel.UNDEFINED: 0>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |
| `src_dir` | `str \| None` | `—` | pos/kw |
| `dest_dir` | `str` | `—` | pos/kw |
| `use_directory_urls` | `bool` | `—` | pos/kw |
| `dest_uri` | `str \| None` | `None` | kw |
| `inclusion` | `InclusionLevel` | `<InclusionLevel.UNDEFINED: 0>` | kw |

### `Files`

A collection of [File][mkdocs.structure.files.File] objects.

```python
mkdocs.commands.build.Files(self, files: 'Iterable[File]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `files` | `Iterable[File]` | `—` | pos/kw |

### `InclusionLevel`

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
mkdocs.commands.build.InclusionLevel(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Navigation`

```python
mkdocs.commands.build.Navigation(self, items: 'list', pages: 'list[Page]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `list` | `—` | pos/kw |
| `pages` | `list[Page]` | `—` | pos/kw |

### `Page`

An item in MkDocs structure - see concrete subclasses Section, Page or Link.

```python
mkdocs.commands.build.Page(self, title: 'str | None', file: 'File', config: 'MkDocsConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `title` | `str \| None` | `—` | pos/kw |
| `file` | `File` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

### `Abort`

Abort the build.

```python
mkdocs.commands.gh_deploy.Abort(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `LiveReloadServer`

Mix-in class to handle each request in a new thread.

```python
mkdocs.commands.serve.LiveReloadServer(self, builder: 'Callable[[], None]', host: 'str', port: 'int', root: 'str', mount_path: 'str' = '/', polling_interval: 'float' = 0.5, shutdown_delay: 'float' = 0.25) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `builder` | `Callable[[], None]` | `—` | pos/kw |
| `host` | `str` | `—` | pos/kw |
| `port` | `int` | `—` | pos/kw |
| `root` | `str` | `—` | pos/kw |
| `mount_path` | `str` | `'/'` | pos/kw |
| `polling_interval` | `float` | `0.5` | pos/kw |
| `shutdown_delay` | `float` | `0.25` | pos/kw |

### `Config`

Base class for MkDocs configuration, plugin configuration (and sub-configuration) objects.

It should be subclassed and have `ConfigOption`s defined as attributes.
For examples, see mkdocs/contrib/se…

```python
mkdocs.config.Config(self, config_file_path: 'str | bytes | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file_path` | `str \| bytes \| None` | `None` | pos/kw |

### `BaseConfigOption`

Abstract base class for generic types.

On Python 3.12 and newer, generic classes implicitly inherit from
Generic when they declare a parameter list after the class's name::

    class Mapping[KT, VT…

```python
mkdocs.config.base.BaseConfigOption(self) -> 'None'
```

### `Config`

Base class for MkDocs configuration, plugin configuration (and sub-configuration) objects.

It should be subclassed and have `ConfigOption`s defined as attributes.
For examples, see mkdocs/contrib/se…

```python
mkdocs.config.base.Config(self, config_file_path: 'str | bytes | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file_path` | `str \| bytes \| None` | `None` | pos/kw |

### `LegacyConfig`

A configuration object for plugins, as just a dict without type-safe attribute access.

```python
mkdocs.config.base.LegacyConfig(self, schema: 'PlainConfigSchema', config_file_path: 'str | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `PlainConfigSchema` | `—` | pos/kw |
| `config_file_path` | `str \| None` | `None` | pos/kw |

### `ValidationError`

Raised during the validation process of the config on errors.

```python
mkdocs.config.base.ValidationError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `weak_property`

Same as a read-only property, but allows overwriting the field for good.

```python
mkdocs.config.base.weak_property(self, func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `BaseConfigOption`

Abstract base class for generic types.

On Python 3.12 and newer, generic classes implicitly inherit from
Generic when they declare a parameter list after the class's name::

    class Mapping[KT, VT…

```python
mkdocs.config.config_options.BaseConfigOption(self) -> 'None'
```

### `Choice`

Choice Config Option.

Validate the config option against a strict set of values.

```python
mkdocs.config.config_options.Choice(self, choices: 'Collection[T]', default: 'T | None' = None, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `choices` | `Collection[T]` | `—` | pos/kw |
| `default` | `T \| None` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `Config`

Base class for MkDocs configuration, plugin configuration (and sub-configuration) objects.

It should be subclassed and have `ConfigOption`s defined as attributes.
For examples, see mkdocs/contrib/se…

```python
mkdocs.config.config_options.Config(self, config_file_path: 'str | bytes | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file_path` | `str \| bytes \| None` | `None` | pos/kw |

### `ConfigItems`

Deprecated: Use `ListOfItems(SubConfig(...))` instead of `ConfigItems(...)`.

Validates a list of mappings that all must match the same set of
options.

```python
mkdocs.config.config_options.ConfigItems(self, *config_options: 'PlainConfigSchemaItem', required=None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_options` | `PlainConfigSchemaItem` | `—` | *args |
| `required` | `—` | `None` | kw |

### `ConfigurationError`

This error is raised by configuration validation when a validation error
is encountered. This error should be raised by any configuration options
defined in a plugin's [config_scheme][].

```python
mkdocs.config.config_options.ConfigurationError(self, message: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |

### `Deprecated`

Deprecated Config Option.

Raises a warning as the option is deprecated. Uses `message` for the
warning. If `move_to` is set to the name of a new config option, the value
is moved to the new option o…

```python
mkdocs.config.config_options.Deprecated(self, moved_to: 'str | None' = None, message: 'str | None' = None, removed: 'bool' = False, option_type: 'BaseConfigOption | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `moved_to` | `str \| None` | `None` | pos/kw |
| `message` | `str \| None` | `None` | pos/kw |
| `removed` | `bool` | `False` | pos/kw |
| `option_type` | `BaseConfigOption \| None` | `None` | pos/kw |

### `DictOfItems`

Validates a dict of items. Keys are always strings.

E.g. for `config_options.DictOfItems(config_options.Type(int))` a valid item is `{"a": 1, "b": 2}`.

```python
mkdocs.config.config_options.DictOfItems(self, option_type: 'BaseConfigOption[T]', default=None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `option_type` | `BaseConfigOption[T]` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `Dir`

Dir Config Option.

Validate a path to a directory, optionally verifying that it exists.

```python
mkdocs.config.config_options.Dir(self, exists: 'bool' = False, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exists` | `bool` | `False` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `DocsDir`

Dir Config Option.

Validate a path to a directory, optionally verifying that it exists.

```python
mkdocs.config.config_options.DocsDir(self, exists: 'bool' = False, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exists` | `bool` | `False` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `EditURI`

Type Config Option.

Validate the type of a config option against a given Python type.

```python
mkdocs.config.config_options.EditURI(self, repo_url_key: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_url_key` | `str` | `—` | pos/kw |

## Functions

### `build`

Perform a full site build.

```python
mkdocs.commands.build.build(config: 'MkDocsConfig', *, serve_url: 'str | None' = None, dirty: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `serve_url` | `str \| None` | `None` | kw |
| `dirty` | `bool` | `False` | kw |

### `get_context`

Return the template context for a given page or template.

```python
mkdocs.commands.build.get_context(nav: 'Navigation', files: 'Sequence[File] | Files', config: 'MkDocsConfig', page: 'Page | None' = None, base_url: 'str' = '') -> 'templates.TemplateContext'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nav` | `Navigation` | `—` | pos/kw |
| `files` | `Sequence[File] \| Files` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `page` | `Page \| None` | `None` | pos/kw |
| `base_url` | `str` | `''` | pos/kw |

**Returns:** `templates.TemplateContext`

### `get_files`

Walk the `docs_dir` and return a Files collection.

```python
mkdocs.commands.build.get_files(config: 'MkDocsConfig') -> 'Files'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `MkDocsConfig` | `—` | pos/kw |

**Returns:** `Files`

### `get_navigation`

Build site navigation from config and files.

```python
mkdocs.commands.build.get_navigation(files: 'Files', config: 'MkDocsConfig') -> 'Navigation'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `files` | `Files` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

**Returns:** `Navigation`

### `set_exclusions`

Re-calculate which files are excluded, based on the patterns in the config.

```python
mkdocs.commands.build.set_exclusions(files: 'Iterable[File]', config: 'MkDocsConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `files` | `Iterable[File]` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

### `site_directory_contains_stale_files`

Check if the site directory contains stale files from a previous build.

```python
mkdocs.commands.build.site_directory_contains_stale_files(site_directory: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `site_directory` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `gh_deploy`

```python
mkdocs.commands.gh_deploy.gh_deploy(config: 'MkDocsConfig', message: 'str | None' = None, force=False, no_history=False, ignore_version=False, shell=False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `message` | `str \| None` | `None` | pos/kw |
| `force` | `—` | `False` | pos/kw |
| `no_history` | `—` | `False` | pos/kw |
| `ignore_version` | `—` | `False` | pos/kw |
| `shell` | `—` | `False` | pos/kw |

### `new`

```python
mkdocs.commands.new.new(output_dir: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `output_dir` | `str` | `—` | pos/kw |

### `build`

Perform a full site build.

```python
mkdocs.commands.serve.build(config: 'MkDocsConfig', *, serve_url: 'str | None' = None, dirty: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `serve_url` | `str \| None` | `None` | kw |
| `dirty` | `bool` | `False` | kw |

### `load_config`

Load the configuration for a given file object or name.

The config_file can either be a file object, string or None. If it is None
the default `mkdocs.yml` filename will loaded.

Extra kwargs are pa…

```python
mkdocs.commands.serve.load_config(config_file: 'str | IO | None' = None, *, config_file_path: 'str | None' = None, **kwargs) -> 'MkDocsConfig'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| IO \| None` | `None` | pos/kw |
| `config_file_path` | `str \| None` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `MkDocsConfig`

### `serve`

Start the MkDocs development server.

By default it will serve the documentation on http://localhost:8000/ and
it will rebuild the documentation and refresh the page automatically
whenever a file is…

```python
mkdocs.commands.serve.serve(config_file: 'str | None' = None, livereload: 'bool' = True, build_type: 'str | None' = None, watch_theme: 'bool' = False, watch: 'list[str]' = [], *, open_in_browser: 'bool' = False, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| None` | `None` | pos/kw |
| `livereload` | `bool` | `True` | pos/kw |
| `build_type` | `str \| None` | `None` | pos/kw |
| `watch_theme` | `bool` | `False` | pos/kw |
| `watch` | `list[str]` | `[]` | pos/kw |
| `open_in_browser` | `bool` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `load_config`

Load the configuration for a given file object or name.

The config_file can either be a file object, string or None. If it is None
the default `mkdocs.yml` filename will loaded.

Extra kwargs are pa…

```python
mkdocs.config.load_config(config_file: 'str | IO | None' = None, *, config_file_path: 'str | None' = None, **kwargs) -> 'MkDocsConfig'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| IO \| None` | `None` | pos/kw |
| `config_file_path` | `str \| None` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `MkDocsConfig`

### `load_config`

Load the configuration for a given file object or name.

The config_file can either be a file object, string or None. If it is None
the default `mkdocs.yml` filename will loaded.

Extra kwargs are pa…

```python
mkdocs.config.base.load_config(config_file: 'str | IO | None' = None, *, config_file_path: 'str | None' = None, **kwargs) -> 'MkDocsConfig'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| IO \| None` | `None` | pos/kw |
| `config_file_path` | `str \| None` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `MkDocsConfig`

## Methods

### `mkdocs.commands.build.Abort` methods

### `format_message`

```python
mkdocs.commands.build.Abort.format_message(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `show`

```python
mkdocs.commands.build.Abort.show(self, *args, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `mkdocs.commands.build.BuildError` methods

### `format_message`

```python
mkdocs.commands.build.BuildError.format_message(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `show`

```python
mkdocs.commands.build.BuildError.show(self, file: 't.IO[t.Any] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `t.IO[t.Any] \| None` | `None` | pos/kw |

### `mkdocs.commands.build.File` methods

### `copy_file`

Copy source file to destination, ensuring parent directories exist.

```python
mkdocs.commands.build.File.copy_file(self, dirty: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dirty` | `bool` | `False` | pos/kw |

### `generated`

Create a virtual file, backed either by in-memory `content` or by a file at `abs_src_path`.

It will pretend to be a file in the docs dir at `src_uri`.

```python
mkdocs.commands.build.File.generated(config: 'MkDocsConfig', src_uri: 'str', *, content: 'str | bytes | None' = None, abs_src_path: 'str | None' = None, inclusion: 'InclusionLevel' = <InclusionLevel.UNDEFINED: 0>) -> 'File'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `src_uri` | `str` | `—` | pos/kw |
| `content` | `str \| bytes \| None` | `None` | kw |
| `abs_src_path` | `str \| None` | `None` | kw |
| `inclusion` | `InclusionLevel` | `<InclusionLevel.UNDEFINED: 0>` | kw |

**Returns:** `File`

### `is_css`

Return True if file is a CSS file.

```python
mkdocs.commands.build.File.is_css(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_documentation_page`

Return True if file is a Markdown page.

```python
mkdocs.commands.build.File.is_documentation_page(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_javascript`

Return True if file is a JavaScript file.

```python
mkdocs.commands.build.File.is_javascript(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_media_file`

Return True if file is not a documentation or static page.

```python
mkdocs.commands.build.File.is_media_file(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_modified`

```python
mkdocs.commands.build.File.is_modified(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `is_static_page`

Return True if file is a static page (HTML, XML, JSON).

```python
mkdocs.commands.build.File.is_static_page(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `url_relative_to`

Return url for file relative to other file.

```python
mkdocs.commands.build.File.url_relative_to(self, other: 'File | str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `File \| str` | `—` | pos/kw |

**Returns:** `str`

### `mkdocs.commands.build.Files` methods

### `add_files_from_theme`

Retrieve static files from Jinja environment and add to collection.

```python
mkdocs.commands.build.Files.add_files_from_theme(self, env: 'jinja2.Environment', config: 'MkDocsConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `env` | `jinja2.Environment` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

### `append`

Add file to the Files collection.

```python
mkdocs.commands.build.Files.append(self, file: 'File') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `File` | `—` | pos/kw |

### `copy_static_files`

Copy static files from source to destination.

```python
mkdocs.commands.build.Files.copy_static_files(self, dirty: 'bool' = False, *, inclusion: 'Callable[[InclusionLevel], bool]' = <function InclusionLevel.is_included at 0x755d9ffc7e20>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dirty` | `bool` | `False` | pos/kw |
| `inclusion` | `Callable[[InclusionLevel], bool]` | `<function InclusionLevel.is_included at 0x755d9ffc7e20>` | kw |

### `css_files`

Return iterable of all CSS file objects.

```python
mkdocs.commands.build.Files.css_files(self) -> 'Sequence[File]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Sequence[File]`

### `documentation_pages`

Return iterable of all Markdown page file objects.

```python
mkdocs.commands.build.Files.documentation_pages(self, *, inclusion: 'Callable[[InclusionLevel], bool]' = <function InclusionLevel.is_included at 0x755d9ffc7e20>) -> 'Sequence[File]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `inclusion` | `Callable[[InclusionLevel], bool]` | `<function InclusionLevel.is_included at 0x755d9ffc7e20>` | kw |

**Returns:** `Sequence[File]`

### `get_file_from_path`

Return a File instance with File.src_uri equal to path.

```python
mkdocs.commands.build.Files.get_file_from_path(self, path: 'str') -> 'File | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `File | None`

### `javascript_files`

Return iterable of all javascript file objects.

```python
mkdocs.commands.build.Files.javascript_files(self) -> 'Sequence[File]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Sequence[File]`

### `media_files`

Return iterable of all file objects which are not documentation or static pages.

```python
mkdocs.commands.build.Files.media_files(self) -> 'Sequence[File]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Sequence[File]`

### `remove`

Remove file from Files collection.

```python
mkdocs.commands.build.Files.remove(self, file: 'File') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `File` | `—` | pos/kw |

### `static_pages`

Return iterable of all static page file objects.

```python
mkdocs.commands.build.Files.static_pages(self) -> 'Sequence[File]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Sequence[File]`

### `mkdocs.commands.build.Page` methods

### `read_source`

```python
mkdocs.commands.build.Page.read_source(self, config: 'MkDocsConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

### `render`

Convert the Markdown source file to HTML as per the config.

```python
mkdocs.commands.build.Page.render(self, config: 'MkDocsConfig', files: 'Files') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `files` | `Files` | `—` | pos/kw |

### `validate_anchor_links`

```python
mkdocs.commands.build.Page.validate_anchor_links(self, *, files: 'Files', log_level: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `files` | `Files` | `—` | kw |
| `log_level` | `int` | `—` | kw |

### `mkdocs.commands.gh_deploy.Abort` methods

### `format_message`

```python
mkdocs.commands.gh_deploy.Abort.format_message(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `show`

```python
mkdocs.commands.gh_deploy.Abort.show(self, *args, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `mkdocs.commands.serve.LiveReloadServer` methods

### `close_request`

Called to clean up an individual request.

```python
mkdocs.commands.serve.LiveReloadServer.close_request(self, request)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |

### `fileno`

Return socket file number.

Interface required by selector.

```python
mkdocs.commands.serve.LiveReloadServer.fileno(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish_request`

Finish one request by instantiating RequestHandlerClass.

```python
mkdocs.commands.serve.LiveReloadServer.finish_request(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `get_app`

```python
mkdocs.commands.serve.LiveReloadServer.get_app(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_request`

Get the request and client address from the socket.

May be overridden.

```python
mkdocs.commands.serve.LiveReloadServer.get_request(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_error`

Handle an error gracefully.  May be overridden.

The default is to print a traceback and continue.

```python
mkdocs.commands.serve.LiveReloadServer.handle_error(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `handle_request`

Handle one request, possibly blocking.

Respects self.timeout.

```python
mkdocs.commands.serve.LiveReloadServer.handle_request(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_timeout`

Called if no new request arrives within self.timeout.

Overridden by ForkingMixIn.

```python
mkdocs.commands.serve.LiveReloadServer.handle_timeout(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_request`

Start a new thread to process the request.

```python
mkdocs.commands.serve.LiveReloadServer.process_request(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `process_request_thread`

Same as in BaseServer but as a thread.

In addition, exception handling is done here.

```python
mkdocs.commands.serve.LiveReloadServer.process_request_thread(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `serve`

```python
mkdocs.commands.serve.LiveReloadServer.serve(self, *, open_in_browser=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `open_in_browser` | `—` | `False` | kw |

### `serve_forever`

Handle one request at a time until shutdown.

Polls for shutdown every poll_interval seconds. Ignores
self.timeout. If you need to do periodic tasks, do them in
another thread.

```python
mkdocs.commands.serve.LiveReloadServer.serve_forever(self, poll_interval=0.5)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `poll_interval` | `—` | `0.5` | pos/kw |

### `serve_request`

```python
mkdocs.commands.serve.LiveReloadServer.serve_request(self, environ, start_response) -> 'Iterable[bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environ` | `—` | `—` | pos/kw |
| `start_response` | `—` | `—` | pos/kw |

**Returns:** `Iterable[bytes]`

### `server_activate`

Called by constructor to activate the server.

May be overridden.

```python
mkdocs.commands.serve.LiveReloadServer.server_activate(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `server_bind`

Override server_bind to store the server name.

```python
mkdocs.commands.serve.LiveReloadServer.server_bind(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `server_close`

```python
mkdocs.commands.serve.LiveReloadServer.server_close(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `service_actions`

Called by the serve_forever() loop.

May be overridden by a subclass / Mixin to implement any code that
needs to be run during the loop.

```python
mkdocs.commands.serve.LiveReloadServer.service_actions(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_app`

```python
mkdocs.commands.serve.LiveReloadServer.set_app(self, application)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `application` | `—` | `—` | pos/kw |

### `setup_environ`

```python
mkdocs.commands.serve.LiveReloadServer.setup_environ(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `shutdown`

Stops the serve_forever loop.

Blocks until the loop has finished. This must be called while
serve_forever() is running in another thread, or it will
deadlock.

```python
mkdocs.commands.serve.LiveReloadServer.shutdown(self, wait=False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `—` | `False` | pos/kw |

### `shutdown_request`

Called to shutdown and close an individual request.

```python
mkdocs.commands.serve.LiveReloadServer.shutdown_request(self, request)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |

### `unwatch`

Stop watching file changes for path. Raises if there was no corresponding `watch` call.

```python
mkdocs.commands.serve.LiveReloadServer.unwatch(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `verify_request`

Verify the request.  May be overridden.

Return True if we should proceed with this request.

```python
mkdocs.commands.serve.LiveReloadServer.verify_request(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `watch`

Add the 'path' to watched paths, call the function and reload when any file changes under it.

```python
mkdocs.commands.serve.LiveReloadServer.watch(self, path: 'str', func: 'None' = None, *, recursive: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `func` | `None` | `None` | pos/kw |
| `recursive` | `bool` | `True` | kw |

### `mkdocs.config.Config` methods

### `clear`

D.clear() -> None.  Remove all items from D.

```python
mkdocs.config.Config.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

```python
mkdocs.config.Config.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fromkeys`

```python
mkdocs.config.Config.fromkeys(iterable, value=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `—` | `—` | pos/kw |
| `value` | `—` | `None` | pos/kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
mkdocs.config.Config.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
mkdocs.config.Config.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
mkdocs.config.Config.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load_dict`

Load config options from a dictionary.

```python
mkdocs.config.Config.load_dict(self, patch: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `patch` | `dict` | `—` | pos/kw |

### `load_file`

Load config options from the open file descriptor of a YAML file.

```python
mkdocs.config.Config.load_file(self, config_file: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_file` | `IO` | `—` | pos/kw |

### `pop`

D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
If key is not found, d is returned if given, otherwise KeyError is raised.

```python
mkdocs.config.Config.pop(self, key, default=<object object at 0x755da0f801a0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `<object object at 0x755da0f801a0>` | pos/kw |

### `popitem`

D.popitem() -> (k, v), remove and return some (key, value) pair
as a 2-tuple; but raise KeyError if D is empty.

```python
mkdocs.config.Config.popitem(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_defaults`

Set the base config by going through each validator and getting the
default if it has one.

```python
mkdocs.config.Config.set_defaults(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setdefault`

D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

```python
mkdocs.config.Config.setdefault(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `update`

D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F.
If E present and has a .keys() method, does:     for k in E.keys(): D[k] = E[k]
If E present and lacks .keys() method, does:     f…

```python
mkdocs.config.Config.update(self, other=(), /, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `()` | pos |
| `kwds` | `—` | `—` | **kwargs |

### `validate`

```python
mkdocs.config.Config.validate(self) -> 'tuple[ConfigErrors, ConfigWarnings]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[ConfigErrors, ConfigWarnings]`

### `values`

D.values() -> an object providing a view on D's values

```python
mkdocs.config.Config.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `mkdocs.config.base.BaseConfigOption` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.base.BaseConfigOption.post_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.base.BaseConfigOption.pre_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.base.BaseConfigOption.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.base.BaseConfigOption.run_validation(self, value: 'object', /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

### `validate`

```python
mkdocs.config.base.BaseConfigOption.validate(self, value: 'object', /) -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

**Returns:** `T`

### `mkdocs.config.base.Config` methods

### `clear`

D.clear() -> None.  Remove all items from D.

```python
mkdocs.config.base.Config.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

```python
mkdocs.config.base.Config.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fromkeys`

```python
mkdocs.config.base.Config.fromkeys(iterable, value=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `—` | `—` | pos/kw |
| `value` | `—` | `None` | pos/kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
mkdocs.config.base.Config.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
mkdocs.config.base.Config.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
mkdocs.config.base.Config.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load_dict`

Load config options from a dictionary.

```python
mkdocs.config.base.Config.load_dict(self, patch: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `patch` | `dict` | `—` | pos/kw |

### `load_file`

Load config options from the open file descriptor of a YAML file.

```python
mkdocs.config.base.Config.load_file(self, config_file: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_file` | `IO` | `—` | pos/kw |

### `pop`

D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
If key is not found, d is returned if given, otherwise KeyError is raised.

```python
mkdocs.config.base.Config.pop(self, key, default=<object object at 0x755da0f801a0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `<object object at 0x755da0f801a0>` | pos/kw |

### `popitem`

D.popitem() -> (k, v), remove and return some (key, value) pair
as a 2-tuple; but raise KeyError if D is empty.

```python
mkdocs.config.base.Config.popitem(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_defaults`

Set the base config by going through each validator and getting the
default if it has one.

```python
mkdocs.config.base.Config.set_defaults(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setdefault`

D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

```python
mkdocs.config.base.Config.setdefault(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `update`

D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F.
If E present and has a .keys() method, does:     for k in E.keys(): D[k] = E[k]
If E present and lacks .keys() method, does:     f…

```python
mkdocs.config.base.Config.update(self, other=(), /, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `()` | pos |
| `kwds` | `—` | `—` | **kwargs |

### `validate`

```python
mkdocs.config.base.Config.validate(self) -> 'tuple[ConfigErrors, ConfigWarnings]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[ConfigErrors, ConfigWarnings]`

### `values`

D.values() -> an object providing a view on D's values

```python
mkdocs.config.base.Config.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `mkdocs.config.base.LegacyConfig` methods

### `clear`

D.clear() -> None.  Remove all items from D.

```python
mkdocs.config.base.LegacyConfig.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

```python
mkdocs.config.base.LegacyConfig.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fromkeys`

```python
mkdocs.config.base.LegacyConfig.fromkeys(iterable, value=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `—` | `—` | pos/kw |
| `value` | `—` | `None` | pos/kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
mkdocs.config.base.LegacyConfig.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
mkdocs.config.base.LegacyConfig.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
mkdocs.config.base.LegacyConfig.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load_dict`

Load config options from a dictionary.

```python
mkdocs.config.base.LegacyConfig.load_dict(self, patch: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `patch` | `dict` | `—` | pos/kw |

### `load_file`

Load config options from the open file descriptor of a YAML file.

```python
mkdocs.config.base.LegacyConfig.load_file(self, config_file: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_file` | `IO` | `—` | pos/kw |

### `pop`

D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
If key is not found, d is returned if given, otherwise KeyError is raised.

```python
mkdocs.config.base.LegacyConfig.pop(self, key, default=<object object at 0x755da0f801a0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `<object object at 0x755da0f801a0>` | pos/kw |

### `popitem`

D.popitem() -> (k, v), remove and return some (key, value) pair
as a 2-tuple; but raise KeyError if D is empty.

```python
mkdocs.config.base.LegacyConfig.popitem(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_defaults`

Set the base config by going through each validator and getting the
default if it has one.

```python
mkdocs.config.base.LegacyConfig.set_defaults(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setdefault`

D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

```python
mkdocs.config.base.LegacyConfig.setdefault(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `update`

D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F.
If E present and has a .keys() method, does:     for k in E.keys(): D[k] = E[k]
If E present and lacks .keys() method, does:     f…

```python
mkdocs.config.base.LegacyConfig.update(self, other=(), /, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `()` | pos |
| `kwds` | `—` | `—` | **kwargs |

### `validate`

```python
mkdocs.config.base.LegacyConfig.validate(self) -> 'tuple[ConfigErrors, ConfigWarnings]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[ConfigErrors, ConfigWarnings]`

### `values`

D.values() -> an object providing a view on D's values

```python
mkdocs.config.base.LegacyConfig.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `mkdocs.config.config_options.BaseConfigOption` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.BaseConfigOption.post_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.BaseConfigOption.pre_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.BaseConfigOption.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.BaseConfigOption.run_validation(self, value: 'object', /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

### `validate`

```python
mkdocs.config.config_options.BaseConfigOption.validate(self, value: 'object', /) -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

**Returns:** `T`

### `mkdocs.config.config_options.Choice` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.Choice.post_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.Choice.pre_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.Choice.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.Choice.run_validation(self, value: 'object') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `T`

### `validate`

Perform some initial validation.

If the option is empty (None) and isn't required, leave it as such. If
it is empty but has a default, use that. Finally, call the
run_validation method on the subcla…

```python
mkdocs.config.config_options.Choice.validate(self, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `mkdocs.config.config_options.Config` methods

### `clear`

D.clear() -> None.  Remove all items from D.

```python
mkdocs.config.config_options.Config.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

```python
mkdocs.config.config_options.Config.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fromkeys`

```python
mkdocs.config.config_options.Config.fromkeys(iterable, value=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `—` | `—` | pos/kw |
| `value` | `—` | `None` | pos/kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
mkdocs.config.config_options.Config.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
mkdocs.config.config_options.Config.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
mkdocs.config.config_options.Config.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load_dict`

Load config options from a dictionary.

```python
mkdocs.config.config_options.Config.load_dict(self, patch: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `patch` | `dict` | `—` | pos/kw |

### `load_file`

Load config options from the open file descriptor of a YAML file.

```python
mkdocs.config.config_options.Config.load_file(self, config_file: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_file` | `IO` | `—` | pos/kw |

### `pop`

D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
If key is not found, d is returned if given, otherwise KeyError is raised.

```python
mkdocs.config.config_options.Config.pop(self, key, default=<object object at 0x755da0f801a0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `<object object at 0x755da0f801a0>` | pos/kw |

### `popitem`

D.popitem() -> (k, v), remove and return some (key, value) pair
as a 2-tuple; but raise KeyError if D is empty.

```python
mkdocs.config.config_options.Config.popitem(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_defaults`

Set the base config by going through each validator and getting the
default if it has one.

```python
mkdocs.config.config_options.Config.set_defaults(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setdefault`

D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

```python
mkdocs.config.config_options.Config.setdefault(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `update`

D.update([E, ]**F) -> None.  Update D from mapping/iterable E and F.
If E present and has a .keys() method, does:     for k in E.keys(): D[k] = E[k]
If E present and lacks .keys() method, does:     f…

```python
mkdocs.config.config_options.Config.update(self, other=(), /, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `()` | pos |
| `kwds` | `—` | `—` | **kwargs |

### `validate`

```python
mkdocs.config.config_options.Config.validate(self) -> 'tuple[ConfigErrors, ConfigWarnings]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[ConfigErrors, ConfigWarnings]`

### `values`

D.values() -> an object providing a view on D's values

```python
mkdocs.config.config_options.Config.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `mkdocs.config.config_options.ConfigItems` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.ConfigItems.post_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.ConfigItems.pre_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.ConfigItems.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.ConfigItems.run_validation(self, value: 'object') -> 'list[T]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `list[T]`

### `validate`

```python
mkdocs.config.config_options.ConfigItems.validate(self, value: 'object', /) -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

**Returns:** `T`

### `mkdocs.config.config_options.ConfigurationError` methods

### `format_message`

```python
mkdocs.config.config_options.ConfigurationError.format_message(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `show`

```python
mkdocs.config.config_options.ConfigurationError.show(self, file: 't.IO[t.Any] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `t.IO[t.Any] \| None` | `None` | pos/kw |

### `mkdocs.config.config_options.Deprecated` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.Deprecated.post_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.Deprecated.pre_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.Deprecated.reset_warnings(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.Deprecated.run_validation(self, value: 'object', /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

### `validate`

```python
mkdocs.config.config_options.Deprecated.validate(self, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `mkdocs.config.config_options.DictOfItems` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.DictOfItems.post_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.DictOfItems.pre_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.DictOfItems.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.DictOfItems.run_validation(self, value: 'object') -> 'dict[str, T]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `dict[str, T]`

### `validate`

```python
mkdocs.config.config_options.DictOfItems.validate(self, value: 'object', /) -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `object` | `—` | pos |

**Returns:** `T`

### `mkdocs.config.config_options.Dir` methods

### `existence_test`

Return true if the pathname refers to an existing directory.

```python
mkdocs.config.config_options.Dir.existence_test(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.Dir.post_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.Dir.pre_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.Dir.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.Dir.run_validation(self, value: 'object') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `str`

### `validate`

Perform some initial validation.

If the option is empty (None) and isn't required, leave it as such. If
it is empty but has a default, use that. Finally, call the
run_validation method on the subcla…

```python
mkdocs.config.config_options.Dir.validate(self, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `mkdocs.config.config_options.DocsDir` methods

### `existence_test`

Return true if the pathname refers to an existing directory.

```python
mkdocs.config.config_options.DocsDir.existence_test(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.DocsDir.post_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.DocsDir.pre_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.DocsDir.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.DocsDir.run_validation(self, value: 'object') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `str`

### `validate`

Perform some initial validation.

If the option is empty (None) and isn't required, leave it as such. If
it is empty but has a default, use that. Finally, call the
run_validation method on the subcla…

```python
mkdocs.config.config_options.DocsDir.validate(self, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `mkdocs.config.config_options.EditURI` methods

### `post_validation`

After all options have passed validation, perform a post-validation
process to do any additional changes dependent on other config values.

The post-validation process method should be implemented by…

```python
mkdocs.config.config_options.EditURI.post_validation(self, config: 'Config', key_name: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `pre_validation`

Before all options are validated, perform a pre-validation process.

The pre-validation process method should be implemented by subclasses.

```python
mkdocs.config.config_options.EditURI.pre_validation(self, config: 'Config', key_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |
| `key_name` | `str` | `—` | pos/kw |

### `reset_warnings`

```python
mkdocs.config.config_options.EditURI.reset_warnings(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run_validation`

Perform validation for a value.

The run_validation method should be implemented by subclasses.

```python
mkdocs.config.config_options.EditURI.run_validation(self, value: 'object') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `T`

### `validate`

Perform some initial validation.

If the option is empty (None) and isn't required, leave it as such. If
it is empty but has a default, use that. Finally, call the
run_validation method on the subcla…

```python
mkdocs.config.config_options.EditURI.validate(self, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |


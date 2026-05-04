---
name: package
description: "pdoc package guide for generating API documentation from Python modules and docstrings"
metadata:
  languages: "python"
  versions: "16.0.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pdoc,python,documentation,docstrings,api-docs,add,Path,cleanly,path matters,Class,Doc,Function,Module,from_name,Namespace,Variable,resolve_annotations,safe_eval_type,AstInfo,get_source,parse,sort_by_source,type_checking_sections,walk_tree,include_typeinfo_from_stub_files,embed_images,google,numpy,rst,invalidate_caches,iter_modules2,load_module,mock_some_common_side_effects,module_mtime,parse_spec,walk_packages2,walk_specs,DefaultMacroExtension,attr,bind,call_method,filter_stream,preprocess,configure,defuse_unsafe_reprs,edit_url,format_signature,html_error,html_index,html_module,link,linkify,make_index,minify_css,precompile_index,repr_module,root_module_name,search_index,to_markdown_with_context,module_candidates,possible_sources,qualname_candidates,split_identifier,to_markdown,AllModules,get,items,keys,values,DocHandler,address_string,date_time_string,do_GET,do_HEAD,end_headers,finish,flush_headers,handle,handle_expect_100,handle_one_request,handle_request,log_date_time_string,log_error,log_message,log_request,parse_request,send_error,send_header,send_response,send_response_only,setup,version_string,DocServer,close_request,fileno,finish_request,get_request,handle_error,handle_timeout,process_request,serve_forever,server_activate,server_bind,server_close,service_actions,shutdown,shutdown_request,verify_request,open_browser"
---

# pdoc — package

# What is pdoc?

pdoc auto-generates API documentation that follows your project's Python module hierarchy.

pdoc's main feature is a focus on simplicity: pdoc aims to do one thing and do it well.

 - Easy setup, no configuration necessary.
 - Documentation is plain [Markdown](#markdown-support).
 - First-class support for type annotations.
 - Builtin web server with live reloading.
 - Customizable HTML templates.
 - Understands numpydoc and Google-style docstrings.

# Quickstart

As an example, we want to generate API documentation for `demo.py`.
Our demo module already includes a bunch of docstrings:

```python
"""
A small `pdoc` example.
"""

class Dog:
    """🐕"""
    name: str
    """The name of our dog."""
    friends: list["Dog"]
    """The friends of our dog."""

    def __init__(…

## Install

```bash
pip install pdoc
```

## Imports

```python
import pdoc
```

## Symbols (125)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `pdoc` | Function | Render the documentation for a list of modules.   - If `output_directory` is `N… |
| `Class` | Class | Representation of a class's documentation. |
| `Doc` | Class | A base class for all documentation objects. |
| `Function` | Class | Representation of a function's documentation.  This class covers all "flavors"… |
| `Module` | Class | Representation of a module's documentation. |
| `from_name` | Method | Create a `Module` object by supplying the module's (full) name. |
| `Namespace` | Class | A documentation object that can have children. In other words, either a module… |
| `Variable` | Class | Representation of a variable's documentation. This includes module, class and i… |
| `resolve_annotations` | Function | Given an `annotations` dictionary with type annotations (for example, `cls.__an… |
| `safe_eval_type` | Function | This method wraps `typing._eval_type`, but doesn't raise on errors. It is used… |
| `AstInfo` | Class | The information extracted from walking the syntax tree. |
| `get_source` | Function | Returns the source code of the Python object `obj` as a str.  If this fails, an… |
| `parse` | Function | Parse a module, class or function and return the (unwrapped) AST node. If an ob… |
| `sort_by_source` | Function | Takes items from `unsorted` and inserts them into `sorted` in order of appearan… |
| `type_checking_sections` | Function | Walks the abstract syntax tree for `mod` and returns all statements guarded by… |
| `walk_tree` | Function | Walks the abstract syntax tree for `obj` and returns the extracted information. |
| `include_typeinfo_from_stub_files` | Function | Patch the provided module with type information from a matching .pyi file. |
| `resolve_annotations` | Function | Given an `annotations` dictionary with type annotations (for example, `cls.__an… |
| `safe_eval_type` | Function | This method wraps `typing._eval_type`, but doesn't raise on errors. It is used… |
| `type_checking_sections` | Function | Walks the abstract syntax tree for `mod` and returns all statements guarded by… |
| `embed_images` | Function |  |
| `google` | Function | Convert Google-style docstring sections into Markdown. |
| `numpy` | Function | Convert NumPy-style docstring sections into Markdown.  See <https://numpydoc.re… |
| `rst` | Function | Convert reStructuredText elements to Markdown. We support the most common eleme… |
| `invalidate_caches` | Function | Invalidate module cache to allow live-reloading of modules. |
| `iter_modules2` | Function | Returns all direct child modules of a given module. This function is similar to… |
| `load_module` | Function | Try to import a module. If import fails, a RuntimeError is raised.  Returns the… |
| `mock_some_common_side_effects` | Function | This context manager is applied when importing modules. It mocks some common si… |
| `module_mtime` | Function | Returns the time the specified module file was last modified, or `None` if this… |
| `parse_spec` | Function | This functions parses a user's module specification into a module identifier th… |

_Plus 95 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `Class`

Representation of a class's documentation.

```python
pdoc.doc.Class(self, modulename: 'str', qualname: 'str', obj: 'T', taken_from: 'tuple[str, str]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `qualname` | `str` | `—` | pos/kw |
| `obj` | `T` | `—` | pos/kw |
| `taken_from` | `tuple[str, str]` | `—` | pos/kw |

### `Doc`

A base class for all documentation objects.

```python
pdoc.doc.Doc(self, modulename: 'str', qualname: 'str', obj: 'T', taken_from: 'tuple[str, str]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `qualname` | `str` | `—` | pos/kw |
| `obj` | `T` | `—` | pos/kw |
| `taken_from` | `tuple[str, str]` | `—` | pos/kw |

### `Function`

Representation of a function's documentation.

This class covers all "flavors" of functions, for example it also
supports `@classmethod`s or `@staticmethod`s.

```python
pdoc.doc.Function(self, modulename: 'str', qualname: 'str', func: 'WrappedFunction', taken_from: 'tuple[str, str]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `qualname` | `str` | `—` | pos/kw |
| `func` | `WrappedFunction` | `—` | pos/kw |
| `taken_from` | `tuple[str, str]` | `—` | pos/kw |

### `Module`

Representation of a module's documentation.

```python
pdoc.doc.Module(self, module: 'types.ModuleType')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `types.ModuleType` | `—` | pos/kw |

### `Namespace`

A documentation object that can have children. In other words, either a module or a class.

```python
pdoc.doc.Namespace(self, modulename: 'str', qualname: 'str', obj: 'T', taken_from: 'tuple[str, str]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `qualname` | `str` | `—` | pos/kw |
| `obj` | `T` | `—` | pos/kw |
| `taken_from` | `tuple[str, str]` | `—` | pos/kw |

### `Variable`

Representation of a variable's documentation. This includes module, class and instance variables.

```python
pdoc.doc.Variable(self, modulename: 'str', qualname: 'str', *, taken_from: 'tuple[str, str]', docstring: 'str', annotation: 'type | empty', default_value: 'Any | empty')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `qualname` | `str` | `—` | pos/kw |
| `taken_from` | `tuple[str, str]` | `—` | kw |
| `docstring` | `str` | `—` | kw |
| `annotation` | `type \| empty` | `—` | kw |
| `default_value` | `Any \| empty` | `—` | kw |

### `AstInfo`

The information extracted from walking the syntax tree.

```python
pdoc.doc_ast.AstInfo(self, var_docstrings: 'dict[str, str]', func_docstrings: 'dict[str, str]', annotations: 'dict[str, str | type[pdoc.doc_types.empty]]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var_docstrings` | `dict[str, str]` | `—` | pos/kw |
| `func_docstrings` | `dict[str, str]` | `—` | pos/kw |
| `annotations` | `dict[str, str \| type[pdoc.doc_types.empty]]` | `—` | pos/kw |

### `DefaultMacroExtension`

This extension provides a new `{% defaultmacro %}` statement, which defines a macro only if it does not exist.

For example,

```html+jinja
{% defaultmacro example() %}
    test 123
{% enddefaultmacr…

```python
pdoc.render.DefaultMacroExtension(self, environment: jinja2.environment.Environment) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `DefaultMacroExtension`

This extension provides a new `{% defaultmacro %}` statement, which defines a macro only if it does not exist.

For example,

```html+jinja
{% defaultmacro example() %}
    test 123
{% enddefaultmacr…

```python
pdoc.render_helpers.DefaultMacroExtension(self, environment: jinja2.environment.Environment) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `AllModules`

A lazy-loading implementation of all_modules.

This behaves like a regular dict, but modules are only imported on demand for performance reasons.
This has the somewhat annoying side effect that __get…

```python
pdoc.web.AllModules(self, allowed_modules: 'Iterable[str]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `allowed_modules` | `Iterable[str]` | `—` | pos/kw |

### `DocHandler`

A handler for individual requests.

```python
pdoc.web.DocHandler(self, request, client_address, server)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |
| `server` | `—` | `—` | pos/kw |

### `DocServer`

pdoc's live-reloading web server

```python
pdoc.web.DocServer(self, addr: 'tuple[str, int]', specs: 'list[str]', **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `addr` | `tuple[str, int]` | `—` | pos/kw |
| `specs` | `list[str]` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

## Functions

### `pdoc`

Render the documentation for a list of modules.

 - If `output_directory` is `None`, returns the rendered documentation
   for the first module in the list.
 - If `output_directory` is set, recursive…

```python
pdoc.pdoc(*modules: 'Path | str', output_directory: 'Path | None' = None) -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modules` | `Path \| str` | `—` | *args |
| `output_directory` | `Path \| None` | `None` | kw |

**Returns:** `str | None`

### `resolve_annotations`

Given an `annotations` dictionary with type annotations (for example, `cls.__annotations__`),
this function tries to resolve all types using `pdoc.doc_types.safe_eval_type`.

Returns: A dictionary wi…

```python
pdoc.doc.resolve_annotations(annotations: 'dict[str, Any]', module: 'ModuleType | None', localns: 'dict[str, Any] | None', fullname: 'str') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotations` | `dict[str, Any]` | `—` | pos/kw |
| `module` | `ModuleType \| None` | `—` | pos/kw |
| `localns` | `dict[str, Any] \| None` | `—` | pos/kw |
| `fullname` | `str` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `safe_eval_type`

This method wraps `typing._eval_type`, but doesn't raise on errors.
It is used to evaluate a type annotation, which might already be
a proper type (in which case no action is required), or a forward…

```python
pdoc.doc.safe_eval_type(t: 'Any', globalns: 'dict[str, Any]', localns: 'dict[str, Any] | None', module: 'types.ModuleType | None', fullname: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `t` | `Any` | `—` | pos/kw |
| `globalns` | `dict[str, Any]` | `—` | pos/kw |
| `localns` | `dict[str, Any] \| None` | `—` | pos/kw |
| `module` | `types.ModuleType \| None` | `—` | pos/kw |
| `fullname` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `get_source`

Returns the source code of the Python object `obj` as a str.

If this fails, an empty string is returned.

```python
pdoc.doc_ast.get_source(obj: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `str`

### `parse`

Parse a module, class or function and return the (unwrapped) AST node.
If an object's source code cannot be found, this function returns an empty ast node stub
which can still be walked.

```python
pdoc.doc_ast.parse(obj)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `—` | pos/kw |

### `sort_by_source`

Takes items from `unsorted` and inserts them into `sorted` in order of appearance in the source code of `obj`.
The only exception to this rule is `__init__`, which (if present) is always inserted fir…

```python
pdoc.doc_ast.sort_by_source(obj: 'types.ModuleType | type', sorted: 'dict[str, T]', unsorted: 'dict[str, T]') -> 'tuple[dict[str, T], dict[str, T]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `types.ModuleType \| type` | `—` | pos/kw |
| `sorted` | `dict[str, T]` | `—` | pos/kw |
| `unsorted` | `dict[str, T]` | `—` | pos/kw |

**Returns:** `tuple[dict[str, T], dict[str, T]]`

### `type_checking_sections`

Walks the abstract syntax tree for `mod` and returns all statements guarded by TYPE_CHECKING blocks.

```python
pdoc.doc_ast.type_checking_sections(mod: 'types.ModuleType') -> 'ast.Module'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mod` | `types.ModuleType` | `—` | pos/kw |

**Returns:** `ast.Module`

### `walk_tree`

Walks the abstract syntax tree for `obj` and returns the extracted information.

```python
pdoc.doc_ast.walk_tree(obj: 'types.ModuleType | type') -> 'AstInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `types.ModuleType \| type` | `—` | pos/kw |

**Returns:** `AstInfo`

### `include_typeinfo_from_stub_files`

Patch the provided module with type information from a matching .pyi file.

```python
pdoc.doc_pyi.include_typeinfo_from_stub_files(module: 'doc.Module') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `doc.Module` | `—` | pos/kw |

### `resolve_annotations`

Given an `annotations` dictionary with type annotations (for example, `cls.__annotations__`),
this function tries to resolve all types using `pdoc.doc_types.safe_eval_type`.

Returns: A dictionary wi…

```python
pdoc.doc_types.resolve_annotations(annotations: 'dict[str, Any]', module: 'ModuleType | None', localns: 'dict[str, Any] | None', fullname: 'str') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotations` | `dict[str, Any]` | `—` | pos/kw |
| `module` | `ModuleType \| None` | `—` | pos/kw |
| `localns` | `dict[str, Any] \| None` | `—` | pos/kw |
| `fullname` | `str` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `safe_eval_type`

This method wraps `typing._eval_type`, but doesn't raise on errors.
It is used to evaluate a type annotation, which might already be
a proper type (in which case no action is required), or a forward…

```python
pdoc.doc_types.safe_eval_type(t: 'Any', globalns: 'dict[str, Any]', localns: 'dict[str, Any] | None', module: 'types.ModuleType | None', fullname: 'str') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `t` | `Any` | `—` | pos/kw |
| `globalns` | `dict[str, Any]` | `—` | pos/kw |
| `localns` | `dict[str, Any] \| None` | `—` | pos/kw |
| `module` | `types.ModuleType \| None` | `—` | pos/kw |
| `fullname` | `str` | `—` | pos/kw |

**Returns:** `Any`

### `type_checking_sections`

Walks the abstract syntax tree for `mod` and returns all statements guarded by TYPE_CHECKING blocks.

```python
pdoc.doc_types.type_checking_sections(mod: 'types.ModuleType') -> 'ast.Module'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mod` | `types.ModuleType` | `—` | pos/kw |

**Returns:** `ast.Module`

### `embed_images`

```python
pdoc.docstrings.embed_images(docstring: 'str', source_file: 'Path') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `str` | `—` | pos/kw |
| `source_file` | `Path` | `—` | pos/kw |

**Returns:** `str`

### `google`

Convert Google-style docstring sections into Markdown.

```python
pdoc.docstrings.google(docstring: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `str` | `—` | pos/kw |

**Returns:** `str`

### `numpy`

Convert NumPy-style docstring sections into Markdown.

See <https://numpydoc.readthedocs.io/en/latest/format.html> for details.

```python
pdoc.docstrings.numpy(docstring: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `str` | `—` | pos/kw |

**Returns:** `str`

### `rst`

Convert reStructuredText elements to Markdown.
We support the most common elements, but we do not aim to mirror the full complexity of the spec here.

```python
pdoc.docstrings.rst(contents: 'str', source_file: 'Path | None') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `contents` | `str` | `—` | pos/kw |
| `source_file` | `Path \| None` | `—` | pos/kw |

**Returns:** `str`

### `invalidate_caches`

Invalidate module cache to allow live-reloading of modules.

```python
pdoc.extract.invalidate_caches(module_name: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module_name` | `str` | `—` | pos/kw |

### `iter_modules2`

Returns all direct child modules of a given module.
This function is similar to `pkgutil.iter_modules`, but

  1. Respects a package's `__all__` attribute if specified.
     If `__all__` is defined,…

```python
pdoc.extract.iter_modules2(module: 'types.ModuleType') -> 'dict[str, pkgutil.ModuleInfo]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `types.ModuleType` | `—` | pos/kw |

**Returns:** `dict[str, pkgutil.ModuleInfo]`

### `load_module`

Try to import a module. If import fails, a RuntimeError is raised.

Returns the imported module.

```python
pdoc.extract.load_module(module: 'str') -> 'types.ModuleType'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `str` | `—` | pos/kw |

**Returns:** `types.ModuleType`

### `mock_some_common_side_effects`

This context manager is applied when importing modules. It mocks some common side effects that may happen upon
module import. For example, `import antigravity` normally causes a web browser to open,…

```python
pdoc.extract.mock_some_common_side_effects()
```

### `module_mtime`

Returns the time the specified module file was last modified, or `None` if this cannot be determined.
The primary use of this is live-reloading modules on modification.

```python
pdoc.extract.module_mtime(modulename: 'str') -> 'float | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |

**Returns:** `float | None`

### `parse_spec`

This functions parses a user's module specification into a module identifier that can be imported.
If both a local file/directory and an importable module with the same name exist, a warning will be…

```python
pdoc.extract.parse_spec(spec: 'Path | str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `spec` | `Path \| str` | `—` | pos/kw |

**Returns:** `str`

### `walk_packages2`

For a given list of modules, recursively yield their names and all their submodules' names.

This function is similar to `pkgutil.walk_packages`, but based on `iter_modules2`.

```python
pdoc.extract.walk_packages2(modules: 'Iterable[pkgutil.ModuleInfo]') -> 'Iterator[pkgutil.ModuleInfo]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modules` | `Iterable[pkgutil.ModuleInfo]` | `—` | pos/kw |

**Returns:** `Iterator[pkgutil.ModuleInfo]`

### `walk_specs`

This function processes a list of module specifications and returns a collection of module names, including all
submodules, that should be processed by pdoc.

A module specification can either be the…

```python
pdoc.extract.walk_specs(specs: 'Sequence[Path | str]') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `specs` | `Sequence[Path \| str]` | `—` | pos/kw |

**Returns:** `list[str]`

### `configure`

Configure the rendering output.

- `docformat` is the docstring flavor in use.
  pdoc prefers plain Markdown (the default), but also supports other formats.
- `include_undocumented` controls whether…

```python
pdoc.render.configure(*, docformat: "Literal['markdown', 'google', 'numpy', 'restructuredtext']" = 'restructuredtext', include_undocumented: 'bool' = True, edit_url_map: 'Mapping[str, str] | None' = None, favicon: 'str | None' = None, footer_text: 'str' = '', logo: 'str | None' = None, logo_link: 'str | None' = None, math: 'bool' = False, mermaid: 'bool' = False, search: 'bool' = True, show_source: 'bool' = True, template_directory: 'Path | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docformat` | `Literal['markdown', 'google', 'numpy', 'restructuredtext']` | `'restructuredtext'` | kw |
| `include_undocumented` | `bool` | `True` | kw |
| `edit_url_map` | `Mapping[str, str] \| None` | `None` | kw |
| `favicon` | `str \| None` | `None` | kw |
| `footer_text` | `str` | `''` | kw |
| `logo` | `str \| None` | `None` | kw |
| `logo_link` | `str \| None` | `None` | kw |
| `math` | `bool` | `False` | kw |
| `mermaid` | `bool` | `False` | kw |
| `search` | `bool` | `True` | kw |
| `show_source` | `bool` | `True` | kw |
| `template_directory` | `Path \| None` | `None` | kw |

### `defuse_unsafe_reprs`

This decorator is applied by pdoc before calling an object's repr().
It applies some heuristics to patch our sensitive information.
For example, `os.environ`'s default `__repr__` implementation expos…

```python
pdoc.render.defuse_unsafe_reprs()
```

### `edit_url`

Create a link to edit a particular file in the used version control system.

```python
pdoc.render.edit_url(modulename: 'str', is_package: 'bool', mapping: 'Mapping[str, str]') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `is_package` | `bool` | `—` | pos/kw |
| `mapping` | `Mapping[str, str]` | `—` | pos/kw |

**Returns:** `str | None`

### `format_signature`

Format and highlight a function signature using pygments. Returns HTML.

```python
pdoc.render.format_signature(sig: 'inspect.Signature', colon: 'bool') -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sig` | `inspect.Signature` | `—` | pos/kw |
| `colon` | `bool` | `—` | pos/kw |

**Returns:** `Markup`

### `html_error`

Renders an error message.

```python
pdoc.render.html_error(error: 'str', details: 'str' = '') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `error` | `str` | `—` | pos/kw |
| `details` | `str` | `''` | pos/kw |

**Returns:** `str`

### `html_index`

Renders the module index.

```python
pdoc.render.html_index(all_modules: 'Mapping[str, pdoc.doc.Module]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |

**Returns:** `str`

### `html_module`

Renders the documentation for a `pdoc.doc.Module`.

- `all_modules` contains all modules that are rendered in this invocation.
  This is used to determine which identifiers should be linked and which…

```python
pdoc.render.html_module(module: 'pdoc.doc.Module', all_modules: 'Mapping[str, pdoc.doc.Module]', mtime: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `pdoc.doc.Module` | `—` | pos/kw |
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |
| `mtime` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `link`

Create a link for a specific `(modulename, qualname)` tuple.

```python
pdoc.render.link(context: 'Context', spec: 'tuple[str, str]', text: 'str | None' = None) -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `Context` | `—` | pos/kw |
| `spec` | `tuple[str, str]` | `—` | pos/kw |
| `text` | `str \| None` | `None` | pos/kw |

**Returns:** `Markup`

### `linkify`

Link all identifiers in a block of text. Identifiers referencing unknown modules or modules that
are not rendered at the moment will be ignored.
A piece of text is considered to be an identifier if i…

```python
pdoc.render.linkify(context: 'Context', code: 'str', namespace: 'str' = '', shorten: 'bool' = True) -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `Context` | `—` | pos/kw |
| `code` | `str` | `—` | pos/kw |
| `namespace` | `str` | `''` | pos/kw |
| `shorten` | `bool` | `True` | pos/kw |

**Returns:** `Markup`

### `make_index`

This method compiles all currently documented modules into a pile of documentation JSON objects,
which can then be ingested by Elasticlunr.js.

```python
pdoc.render.make_index(all_modules: 'Mapping[str, pdoc.doc.Module]', is_public: 'Callable[[pdoc.doc.Doc], bool]', default_docformat: 'str') -> 'list[dict]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |
| `is_public` | `Callable[[pdoc.doc.Doc], bool]` | `—` | pos/kw |
| `default_docformat` | `str` | `—` | pos/kw |

**Returns:** `list[dict]`

### `minify_css`

Do some very basic CSS minification.

```python
pdoc.render.minify_css(css: 'str') -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `css` | `str` | `—` | pos/kw |

**Returns:** `Markup`

### `precompile_index`

This method tries to precompile the Elasticlunr.js search index by invoking `nodejs` or `node`.
If that fails, an unprocessed index will be returned (which will be compiled locally on the client side…

```python
pdoc.render.precompile_index(documents: 'list[dict]', compile_js: 'Path') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `documents` | `list[dict]` | `—` | pos/kw |
| `compile_js` | `Path` | `—` | pos/kw |

**Returns:** `str`

### `repr_module`

Renders `repr(pdoc.doc.Module)`, primarily used for tests and debugging.

```python
pdoc.render.repr_module(module: 'pdoc.doc.Module') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `module` | `pdoc.doc.Module` | `—` | pos/kw |

**Returns:** `str`

### `root_module_name`

Return the name of the (unique) top-level module, or `None`
if no such module exists.

For example, assuming `foo`, `foo.bar`, and `foo.baz` are documented,
this function will return `foo`. If `foo`…

```python
pdoc.render.root_module_name(all_modules: 'Mapping[str, pdoc.doc.Module]') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |

**Returns:** `str | None`

### `search_index`

Renders the Elasticlunr.js search index.

```python
pdoc.render.search_index(all_modules: 'Mapping[str, pdoc.doc.Module]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |

**Returns:** `str`

### `to_markdown_with_context`

Converts `docstring` from a custom docformat to Markdown (if necessary), and then from Markdown to HTML.

```python
pdoc.render.to_markdown_with_context(context: 'Context', docstring: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `Context` | `—` | pos/kw |
| `docstring` | `str` | `—` | pos/kw |

**Returns:** `str`

### `defuse_unsafe_reprs`

This decorator is applied by pdoc before calling an object's repr().
It applies some heuristics to patch our sensitive information.
For example, `os.environ`'s default `__repr__` implementation expos…

```python
pdoc.render_helpers.defuse_unsafe_reprs()
```

### `edit_url`

Create a link to edit a particular file in the used version control system.

```python
pdoc.render_helpers.edit_url(modulename: 'str', is_package: 'bool', mapping: 'Mapping[str, str]') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `modulename` | `str` | `—` | pos/kw |
| `is_package` | `bool` | `—` | pos/kw |
| `mapping` | `Mapping[str, str]` | `—` | pos/kw |

**Returns:** `str | None`

### `format_signature`

Format and highlight a function signature using pygments. Returns HTML.

```python
pdoc.render_helpers.format_signature(sig: 'inspect.Signature', colon: 'bool') -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sig` | `inspect.Signature` | `—` | pos/kw |
| `colon` | `bool` | `—` | pos/kw |

**Returns:** `Markup`

### `link`

Create a link for a specific `(modulename, qualname)` tuple.

```python
pdoc.render_helpers.link(context: 'Context', spec: 'tuple[str, str]', text: 'str | None' = None) -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `Context` | `—` | pos/kw |
| `spec` | `tuple[str, str]` | `—` | pos/kw |
| `text` | `str \| None` | `None` | pos/kw |

**Returns:** `Markup`

### `linkify`

Link all identifiers in a block of text. Identifiers referencing unknown modules or modules that
are not rendered at the moment will be ignored.
A piece of text is considered to be an identifier if i…

```python
pdoc.render_helpers.linkify(context: 'Context', code: 'str', namespace: 'str' = '', shorten: 'bool' = True) -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `Context` | `—` | pos/kw |
| `code` | `str` | `—` | pos/kw |
| `namespace` | `str` | `''` | pos/kw |
| `shorten` | `bool` | `True` | pos/kw |

**Returns:** `Markup`

### `minify_css`

Do some very basic CSS minification.

```python
pdoc.render_helpers.minify_css(css: 'str') -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `css` | `str` | `—` | pos/kw |

**Returns:** `Markup`

### `module_candidates`

Given an identifier and the current module name, return the module names we should look at
to find where the target object is exposed. Module names are ordered by preferences, i.e.
we always prefer t…

```python
pdoc.render_helpers.module_candidates(identifier: 'str', current_module: 'str') -> 'Iterable[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `identifier` | `str` | `—` | pos/kw |
| `current_module` | `str` | `—` | pos/kw |

**Returns:** `Iterable[str]`

### `possible_sources`

For a given identifier, return all possible sources where it could originate from.
For example, assume `examplepkg._internal.Foo` with all_modules=["examplepkg"].
This could be a Foo class in _intern…

```python
pdoc.render_helpers.possible_sources(all_modules: 'Collection[str]', identifier: 'str') -> 'Iterable[tuple[str, str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Collection[str]` | `—` | pos/kw |
| `identifier` | `str` | `—` | pos/kw |

**Returns:** `Iterable[tuple[str, str]]`

### `qualname_candidates`

Given an identifier in a current namespace, return all possible qualnames in the current module.
For example, if we are in Foo's subclass Bar and `baz()` is the identifier,
return `Foo.Bar.baz()`, `F…

```python
pdoc.render_helpers.qualname_candidates(identifier: 'str', context_qualname: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `identifier` | `str` | `—` | pos/kw |
| `context_qualname` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

### `root_module_name`

Return the name of the (unique) top-level module, or `None`
if no such module exists.

For example, assuming `foo`, `foo.bar`, and `foo.baz` are documented,
this function will return `foo`. If `foo`…

```python
pdoc.render_helpers.root_module_name(all_modules: 'Mapping[str, pdoc.doc.Module]') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |

**Returns:** `str | None`

### `split_identifier`

Split an identifier into a `(modulename, qualname)` tuple. For example, `pdoc.render_helpers.split_identifier`
would be split into `("pdoc.render_helpers","split_identifier")`. This is necessary to g…

```python
pdoc.render_helpers.split_identifier(all_modules: 'Collection[str]', fullname: 'str') -> 'tuple[str, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Collection[str]` | `—` | pos/kw |
| `fullname` | `str` | `—` | pos/kw |

**Returns:** `tuple[str, str]`

### `to_markdown`

```python
pdoc.render_helpers.to_markdown(docstring: 'str', module: 'pdoc.doc.Module', default_docformat: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `str` | `—` | pos/kw |
| `module` | `pdoc.doc.Module` | `—` | pos/kw |
| `default_docformat` | `str` | `—` | pos/kw |

**Returns:** `str`

### `to_markdown_with_context`

Converts `docstring` from a custom docformat to Markdown (if necessary), and then from Markdown to HTML.

```python
pdoc.render_helpers.to_markdown_with_context(context: 'Context', docstring: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `Context` | `—` | pos/kw |
| `docstring` | `str` | `—` | pos/kw |

**Returns:** `str`

### `format_signature`

Format and highlight a function signature using pygments. Returns HTML.

```python
pdoc.search.format_signature(sig: 'inspect.Signature', colon: 'bool') -> 'Markup'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sig` | `inspect.Signature` | `—` | pos/kw |
| `colon` | `bool` | `—` | pos/kw |

**Returns:** `Markup`

### `make_index`

This method compiles all currently documented modules into a pile of documentation JSON objects,
which can then be ingested by Elasticlunr.js.

```python
pdoc.search.make_index(all_modules: 'Mapping[str, pdoc.doc.Module]', is_public: 'Callable[[pdoc.doc.Doc], bool]', default_docformat: 'str') -> 'list[dict]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `all_modules` | `Mapping[str, pdoc.doc.Module]` | `—` | pos/kw |
| `is_public` | `Callable[[pdoc.doc.Doc], bool]` | `—` | pos/kw |
| `default_docformat` | `str` | `—` | pos/kw |

**Returns:** `list[dict]`

### `precompile_index`

This method tries to precompile the Elasticlunr.js search index by invoking `nodejs` or `node`.
If that fails, an unprocessed index will be returned (which will be compiled locally on the client side…

```python
pdoc.search.precompile_index(documents: 'list[dict]', compile_js: 'Path') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `documents` | `list[dict]` | `—` | pos/kw |
| `compile_js` | `Path` | `—` | pos/kw |

**Returns:** `str`

### `to_markdown`

```python
pdoc.search.to_markdown(docstring: 'str', module: 'pdoc.doc.Module', default_docformat: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `str` | `—` | pos/kw |
| `module` | `pdoc.doc.Module` | `—` | pos/kw |
| `default_docformat` | `str` | `—` | pos/kw |

**Returns:** `str`

### `open_browser`

Open a URL in a browser window.
In contrast to `webbrowser.open`, we limit the list of suitable browsers.
This gracefully degrades to a no-op on headless servers, where `webbrowser.open`
would otherw…

```python
pdoc.web.open_browser(url: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `str` | `—` | pos/kw |

**Returns:** `bool`

## Methods

### `pdoc.doc.Module` methods

### `from_name`

Create a `Module` object by supplying the module's (full) name.

```python
pdoc.doc.Module.from_name(name: 'str') -> 'Module'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `Module`

### `pdoc.render.DefaultMacroExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
pdoc.render.DefaultMacroExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
pdoc.render.DefaultMacroExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
pdoc.render.DefaultMacroExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
pdoc.render.DefaultMacroExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

If any of the :attr:`tags` matched this method is called with the
parser as first argument.  The token the parser stream is pointing at
is the name token that matched.  This method has to return one…

```python
pdoc.render.DefaultMacroExtension.parse(self, parser)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `—` | `—` | pos/kw |

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
pdoc.render.DefaultMacroExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `pdoc.render_helpers.DefaultMacroExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
pdoc.render_helpers.DefaultMacroExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
pdoc.render_helpers.DefaultMacroExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
pdoc.render_helpers.DefaultMacroExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
pdoc.render_helpers.DefaultMacroExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

If any of the :attr:`tags` matched this method is called with the
parser as first argument.  The token the parser stream is pointing at
is the name token that matched.  This method has to return one…

```python
pdoc.render_helpers.DefaultMacroExtension.parse(self, parser)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `—` | `—` | pos/kw |

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
pdoc.render_helpers.DefaultMacroExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `pdoc.web.AllModules` methods

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
pdoc.web.AllModules.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
pdoc.web.AllModules.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
pdoc.web.AllModules.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `values`

D.values() -> an object providing a view on D's values

```python
pdoc.web.AllModules.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pdoc.web.DocHandler` methods

### `address_string`

Return the client address.

```python
pdoc.web.DocHandler.address_string(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `date_time_string`

Return the current date and time formatted for a message header.

```python
pdoc.web.DocHandler.date_time_string(self, timestamp=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `timestamp` | `—` | `None` | pos/kw |

### `do_GET`

```python
pdoc.web.DocHandler.do_GET(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `do_HEAD`

```python
pdoc.web.DocHandler.do_HEAD(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `end_headers`

Send the blank line ending the MIME headers.

```python
pdoc.web.DocHandler.end_headers(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish`

```python
pdoc.web.DocHandler.finish(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `flush_headers`

```python
pdoc.web.DocHandler.flush_headers(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle`

Handle multiple requests if necessary.

```python
pdoc.web.DocHandler.handle(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_expect_100`

Decide what to do with an "Expect: 100-continue" header.

If the client is expecting a 100 Continue response, we must
respond with either a 100 Continue or a final response before
waiting for the req…

```python
pdoc.web.DocHandler.handle_expect_100(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_one_request`

Handle a single HTTP request.

You normally don't need to override this method; see the class
__doc__ string for information on how to handle specific HTTP
commands such as GET and POST.

```python
pdoc.web.DocHandler.handle_one_request(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_request`

Actually handle a request. Called by `do_HEAD` and `do_GET`.

```python
pdoc.web.DocHandler.handle_request(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `log_date_time_string`

Return the current time formatted for logging.

```python
pdoc.web.DocHandler.log_date_time_string(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `log_error`

Log an error.

This is called when a request cannot be fulfilled.  By
default it passes the message on to log_message().

Arguments are the same as for log_message().

XXX This should go to the separ…

```python
pdoc.web.DocHandler.log_error(self, format, *args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `format` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `log_message`

Log an arbitrary message.

This is used by all other logging functions.  Override
it if you have specific logging wishes.

The first argument, FORMAT, is a format string for the
message to be logged.…

```python
pdoc.web.DocHandler.log_message(self, format, *args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `format` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `log_request`

Override logging to disable it.

```python
pdoc.web.DocHandler.log_request(self, code: 'int | str' = Ellipsis, size: 'int | str' = Ellipsis) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `code` | `int \| str` | `Ellipsis` | pos/kw |
| `size` | `int \| str` | `Ellipsis` | pos/kw |

### `parse_request`

Parse a request (internal).

The request should be stored in self.raw_requestline; the results
are in self.command, self.path, self.request_version and
self.headers.

Return True for success, False f…

```python
pdoc.web.DocHandler.parse_request(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `send_error`

Send and log an error reply.

Arguments are
* code:    an HTTP error code
           3 digits
* message: a simple optional 1 line reason phrase.
           *( HTAB / SP / VCHAR / %x80-FF )…

```python
pdoc.web.DocHandler.send_error(self, code, message=None, explain=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `code` | `—` | `—` | pos/kw |
| `message` | `—` | `None` | pos/kw |
| `explain` | `—` | `None` | pos/kw |

### `send_header`

Send a MIME header to the headers buffer.

```python
pdoc.web.DocHandler.send_header(self, keyword, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keyword` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `send_response`

Add the response header to the headers buffer and log the
response code.

Also send two standard headers with the server software
version and the current date.

```python
pdoc.web.DocHandler.send_response(self, code, message=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `code` | `—` | `—` | pos/kw |
| `message` | `—` | `None` | pos/kw |

### `send_response_only`

Send the response header only.

```python
pdoc.web.DocHandler.send_response_only(self, code, message=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `code` | `—` | `—` | pos/kw |
| `message` | `—` | `None` | pos/kw |

### `setup`

```python
pdoc.web.DocHandler.setup(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `version_string`

Return the server software version string.

```python
pdoc.web.DocHandler.version_string(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pdoc.web.DocServer` methods

### `close_request`

Called to clean up an individual request.

```python
pdoc.web.DocServer.close_request(self, request)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |

### `fileno`

Return socket file number.

Interface required by selector.

```python
pdoc.web.DocServer.fileno(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `finish_request`

Finish one request by instantiating RequestHandlerClass.

```python
pdoc.web.DocServer.finish_request(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `get_request`

Get the request and client address from the socket.

May be overridden.

```python
pdoc.web.DocServer.get_request(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_error`

Handle an error gracefully.  May be overridden.

The default is to print a traceback and continue.

```python
pdoc.web.DocServer.handle_error(self, request, client_address)
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
pdoc.web.DocServer.handle_request(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `handle_timeout`

Called if no new request arrives within self.timeout.

Overridden by ForkingMixIn.

```python
pdoc.web.DocServer.handle_timeout(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_request`

Call finish_request.

Overridden by ForkingMixIn and ThreadingMixIn.

```python
pdoc.web.DocServer.process_request(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |

### `serve_forever`

Handle one request at a time until shutdown.

Polls for shutdown every poll_interval seconds. Ignores
self.timeout. If you need to do periodic tasks, do them in
another thread.

```python
pdoc.web.DocServer.serve_forever(self, poll_interval=0.5)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `poll_interval` | `—` | `0.5` | pos/kw |

### `server_activate`

Called by constructor to activate the server.

May be overridden.

```python
pdoc.web.DocServer.server_activate(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `server_bind`

Override server_bind to store the server name.

```python
pdoc.web.DocServer.server_bind(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `server_close`

Called to clean-up the server.

May be overridden.

```python
pdoc.web.DocServer.server_close(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `service_actions`

Called by the serve_forever() loop.

May be overridden by a subclass / Mixin to implement any code that
needs to be run during the loop.

```python
pdoc.web.DocServer.service_actions(self)
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
pdoc.web.DocServer.shutdown(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `shutdown_request`

Called to shutdown and close an individual request.

```python
pdoc.web.DocServer.shutdown_request(self, request)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |

### `verify_request`

Verify the request.  May be overridden.

Return True if we should proceed with this request.

```python
pdoc.web.DocServer.verify_request(self, request, client_address)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `client_address` | `—` | `—` | pos/kw |


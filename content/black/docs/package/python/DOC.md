---
name: package
description: "Black Python formatter guide for install, pyproject.toml configuration, CLI usage, and pre-commit integration"
metadata:
  languages: "python"
  versions: "26.3.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "black,python,formatter,code-style,pre-commit,pyproject,toml,Version-Sensitive,ASTSafetyError,Cache,Changed,EmptyLineTracker,Feature,FileMode,InvalidInput,LineGenerator,LinesBlock,Mode,NothingChanged,Preview,Report,done,failed,path_ignored,TargetVersion,WriteBack,adjusted_lines,assert_equivalent,assert_stable,best_effort_relative_path,check_stability_and_equivalence,color_diff,convert_unchanged_lines,decode_bytes,detect_target_versions,diff,dump_to_file,enable_unstable_feature_callback,err,find_pyproject_toml,format_cell,format_file_contents,format_file_in_place,format_ipynb_string,format_stdin_to_stdout,format_str,gen_python_files,get_features_used,get_future_imports,get_sources,ipynb_diff,is_number_token,is_simple_decorator_expression,lib2to3_parse,mask_cell,normalize_fmt_off,out,parse_ast,parse_line_ranges,parse_pyproject_toml,patched_main,path_is_excluded,put_trailing_semicolon_back,re_compile_maybe_verbose,read_pyproject_toml,reformat_code,reformat_one,remove_trailing_semicolon,resolves_outside_root_or_cannot_stat,sanitized_lines,spellcheck_pyproject_toml_keys,stringify_ast,supports_feature,target_version_option_callback,transform_line,unmask_cell,validate_cell,validate_metadata,validate_regex,wrap_stream_for_windows,BracketMatchError,BracketTracker,get_leaves_inside_matching_brackets,is_split_after_delimiter,is_split_before_delimiter,is_vararg,max_delimiter_priority_in_atom,FileData,get_cache_dir,get_cache_file,ProtoComment,children_contains_fmt_on,container_of,contains_fmt_directive,contains_pragma_comment,convert_one_fmt_off_pair,first_leaf_of,generate_comments,generate_ignored_nodes,is_fmt_on,is_type_comment_string,make_comment,make_simple_prefix,normalize_trailing_prefix,preceding_leaf,cancel,maybe_use_uvloop,reformat_many,schedule_formatting,shutdown,DebugVisitor,show,visit_default,Visitor,infer_target_version,parse_req_python_specifier,parse_req_python_version,strip_specifier_set,CellMagic,CellMagicFinder,generic_visit,visit,visit_Constant,MagicFinder,OffsetAndMagic,Replacement,create_token,get_token,replace_cell_magics,replace_magics,CannotSplit,CannotTransform,Line,RHSResult,StringMerger,StringParenStripper,StringParenWrapper,StringSplitter,append_leaves,bracket_split_build_line,bracket_split_succeeded_or_raise,can_be_split,can_omit_invisible_parens,dont_increase_indentation,ensure_visible,fix_multiline_docstring,fstring_tstring_to_string,generate_trailers_to_omit,get_annotation_type,get_string_prefix,has_sibling_with_type,hug_power_op,is_arith_like,is_async_stmt_or_funcdef,is_atom_with_invisible_parens,is_docstring,is_empty_tuple,is_generator"
---

# black — package

## Install

```bash
pip install black
```

## Imports

```python
import black
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `ASTSafetyError` | Class |  |
| `Cache` | Class |  |
| `Changed` | Class | Create a collection of name/value pairs.  Example enumeration:  >>> class Color… |
| `EmptyLineTracker` | Class |  |
| `Feature` | Class | mypyc filler docstring |
| `FileMode` | Class |  |
| `InvalidInput` | Class |  |
| `LineGenerator` | Class |  |
| `LinesBlock` | Class |  |
| `Mode` | Class |  |
| `NothingChanged` | Class | Raised when reformatted code is the same as source. |
| `Preview` | Class | mypyc filler docstring |
| `Report` | Class | Provides a reformatting counter. Can be rendered with `str(report)`. |
| `done` | Method | Increment the counter for successful reformatting. Write out a message. |
| `failed` | Method | Increment the counter for failed reformatting. Write out a message. |
| `path_ignored` | Method |  |
| `TargetVersion` | Class | mypyc filler docstring |
| `WriteBack` | Class | mypyc filler docstring |
| `adjusted_lines` | Function |  |
| `assert_equivalent` | Function |  |
| `assert_stable` | Function |  |
| `best_effort_relative_path` | Function |  |
| `check_stability_and_equivalence` | Function |  |
| `color_diff` | Function | Inject the ANSI color codes to the diff. |
| `convert_unchanged_lines` | Function |  |
| `decode_bytes` | Function |  |
| `detect_target_versions` | Function |  |
| `diff` | Function | Return a unified diff string between strings `a` and `b`. |
| `dump_to_file` | Function | Dump `output` to a temporary file. Return path to the file. |
| `enable_unstable_feature_callback` | Function |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `ASTSafetyError`

```python
black.ASTSafetyError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Cache`

```python
black.Cache(self, mode: black.mode.Mode, cache_file: pathlib._local.Path, file_data: dict = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `Mode` | `—` | pos/kw |
| `cache_file` | `Path` | `—` | pos/kw |
| `file_data` | `dict` | `<factory>` | pos/kw |

### `Changed`

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
black.Changed(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `EmptyLineTracker`

```python
black.EmptyLineTracker(self, mode: black.mode.Mode, previous_line: type = None, previous_block: type = None, previous_defs: list = <factory>, semantic_leading_comment: type = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `Mode` | `—` | pos/kw |
| `previous_line` | `type` | `None` | pos/kw |
| `previous_block` | `type` | `None` | pos/kw |
| `previous_defs` | `list` | `<factory>` | pos/kw |
| `semantic_leading_comment` | `type` | `None` | pos/kw |

### `Feature`

mypyc filler docstring

```python
black.Feature(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `FileMode`

```python
black.FileMode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `InvalidInput`

```python
black.InvalidInput(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LineGenerator`

```python
black.LineGenerator(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LinesBlock`

```python
black.LinesBlock(self, mode: black.mode.Mode, previous_block: type, original_line: black.lines.Line, before: int = 0, content_lines: list = <factory>, after: int = 0, form_feed: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `Mode` | `—` | pos/kw |
| `previous_block` | `type` | `—` | pos/kw |
| `original_line` | `Line` | `—` | pos/kw |
| `before` | `int` | `0` | pos/kw |
| `content_lines` | `list` | `<factory>` | pos/kw |
| `after` | `int` | `0` | pos/kw |
| `form_feed` | `bool` | `False` | pos/kw |

### `Mode`

```python
black.Mode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `NothingChanged`

Raised when reformatted code is the same as source.

```python
black.NothingChanged(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Preview`

mypyc filler docstring

```python
black.Preview(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Report`

Provides a reformatting counter. Can be rendered with `str(report)`.

```python
black.Report(self, check: bool = False, diff: bool = False, quiet: bool = False, verbose: bool = False, change_count: int = 0, same_count: int = 0, failure_count: int = 0) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `check` | `bool` | `False` | pos/kw |
| `diff` | `bool` | `False` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |
| `verbose` | `bool` | `False` | pos/kw |
| `change_count` | `int` | `0` | pos/kw |
| `same_count` | `int` | `0` | pos/kw |
| `failure_count` | `int` | `0` | pos/kw |

### `TargetVersion`

mypyc filler docstring

```python
black.TargetVersion(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `WriteBack`

mypyc filler docstring

```python
black.WriteBack(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `BracketMatchError`

```python
black.brackets.BracketMatchError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BracketTracker`

```python
black.brackets.BracketTracker(self, depth: int = 0, bracket_match: dict = <factory>, delimiters: dict = <factory>, previous: type = None, _for_loop_depths: list = <factory>, _lambda_argument_depths: list = <factory>, invisible: list = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `depth` | `int` | `0` | pos/kw |
| `bracket_match` | `dict` | `<factory>` | pos/kw |
| `delimiters` | `dict` | `<factory>` | pos/kw |
| `previous` | `type` | `None` | pos/kw |
| `_for_loop_depths` | `list` | `<factory>` | pos/kw |
| `_lambda_argument_depths` | `list` | `<factory>` | pos/kw |
| `invisible` | `list` | `<factory>` | pos/kw |

### `Cache`

```python
black.cache.Cache(self, mode: black.mode.Mode, cache_file: pathlib._local.Path, file_data: dict = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `Mode` | `—` | pos/kw |
| `cache_file` | `Path` | `—` | pos/kw |
| `file_data` | `dict` | `<factory>` | pos/kw |

### `FileData`

mypyc filler docstring

```python
black.cache.FileData(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Mode`

```python
black.cache.Mode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `Mode`

```python
black.comments.Mode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `ProtoComment`

```python
black.comments.ProtoComment(self, type: int, value: str, newlines: int, consumed: int, form_feed: bool, leading_whitespace: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `int` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |
| `newlines` | `int` | `—` | pos/kw |
| `consumed` | `int` | `—` | pos/kw |
| `form_feed` | `bool` | `—` | pos/kw |
| `leading_whitespace` | `str` | `—` | pos/kw |

### `Cache`

```python
black.concurrency.Cache(self, mode: black.mode.Mode, cache_file: pathlib._local.Path, file_data: dict = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `Mode` | `—` | pos/kw |
| `cache_file` | `Path` | `—` | pos/kw |
| `file_data` | `dict` | `<factory>` | pos/kw |

### `Changed`

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
black.concurrency.Changed(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Mode`

```python
black.concurrency.Mode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `Report`

Provides a reformatting counter. Can be rendered with `str(report)`.

```python
black.concurrency.Report(self, check: bool = False, diff: bool = False, quiet: bool = False, verbose: bool = False, change_count: int = 0, same_count: int = 0, failure_count: int = 0) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `check` | `bool` | `False` | pos/kw |
| `diff` | `bool` | `False` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |
| `verbose` | `bool` | `False` | pos/kw |
| `change_count` | `int` | `0` | pos/kw |
| `same_count` | `int` | `0` | pos/kw |
| `failure_count` | `int` | `0` | pos/kw |

### `WriteBack`

mypyc filler docstring

```python
black.concurrency.WriteBack(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `DebugVisitor`

DebugVisitor(tree_depth: int = 0, list_output: list[str] = <factory>, print_output: bool = True)

```python
black.debug.DebugVisitor(self, tree_depth: int = 0, list_output: list[str] = <factory>, print_output: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree_depth` | `int` | `0` | pos/kw |
| `list_output` | `list` | `<factory>` | pos/kw |
| `print_output` | `bool` | `True` | pos/kw |

### `Visitor`

```python
black.debug.Visitor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Report`

Provides a reformatting counter. Can be rendered with `str(report)`.

```python
black.files.Report(self, check: bool = False, diff: bool = False, quiet: bool = False, verbose: bool = False, change_count: int = 0, same_count: int = 0, failure_count: int = 0) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `check` | `bool` | `False` | pos/kw |
| `diff` | `bool` | `False` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |
| `verbose` | `bool` | `False` | pos/kw |
| `change_count` | `int` | `0` | pos/kw |
| `same_count` | `int` | `0` | pos/kw |
| `failure_count` | `int` | `0` | pos/kw |

### `TargetVersion`

mypyc filler docstring

```python
black.files.TargetVersion(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `CellMagic`

```python
black.handle_ipynb_magics.CellMagic(self, name: str, params: type, body: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `params` | `type` | `—` | pos/kw |
| `body` | `str` | `—` | pos/kw |

### `CellMagicFinder`

```python
black.handle_ipynb_magics.CellMagicFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MagicFinder`

```python
black.handle_ipynb_magics.MagicFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Mode`

```python
black.handle_ipynb_magics.Mode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `NothingChanged`

Raised when reformatted code is the same as source.

```python
black.handle_ipynb_magics.NothingChanged(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OffsetAndMagic`

```python
black.handle_ipynb_magics.OffsetAndMagic(self, col_offset: int, magic: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `col_offset` | `int` | `—` | pos/kw |
| `magic` | `str` | `—` | pos/kw |

### `Replacement`

```python
black.handle_ipynb_magics.Replacement(self, mask: str, src: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mask` | `str` | `—` | pos/kw |
| `src` | `str` | `—` | pos/kw |

### `CannotSplit`

```python
black.linegen.CannotSplit(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CannotTransform`

```python
black.linegen.CannotTransform(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Feature`

mypyc filler docstring

```python
black.linegen.Feature(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Line`

```python
black.linegen.Line(self, mode: black.mode.Mode, depth: int = 0, leaves: list = <factory>, comments: dict = <factory>, bracket_tracker: black.brackets.BracketTracker = <factory>, inside_brackets: bool = False, should_split_rhs: bool = False, magic_trailing_comma: type = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `Mode` | `—` | pos/kw |
| `depth` | `int` | `0` | pos/kw |
| `leaves` | `list` | `<factory>` | pos/kw |
| `comments` | `dict` | `<factory>` | pos/kw |
| `bracket_tracker` | `BracketTracker` | `<factory>` | pos/kw |
| `inside_brackets` | `bool` | `False` | pos/kw |
| `should_split_rhs` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `type` | `None` | pos/kw |

### `LineGenerator`

```python
black.linegen.LineGenerator(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Mode`

```python
black.linegen.Mode(self, target_versions: set = <factory>, line_length: int = 88, string_normalization: bool = True, is_pyi: bool = False, is_ipynb: bool = False, skip_source_first_line: bool = False, magic_trailing_comma: bool = True, python_cell_magics: set = <factory>, preview: bool = False, unstable: bool = False, enabled_features: set = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `set` | `<factory>` | pos/kw |
| `line_length` | `int` | `88` | pos/kw |
| `string_normalization` | `bool` | `True` | pos/kw |
| `is_pyi` | `bool` | `False` | pos/kw |
| `is_ipynb` | `bool` | `False` | pos/kw |
| `skip_source_first_line` | `bool` | `False` | pos/kw |
| `magic_trailing_comma` | `bool` | `True` | pos/kw |
| `python_cell_magics` | `set` | `<factory>` | pos/kw |
| `preview` | `bool` | `False` | pos/kw |
| `unstable` | `bool` | `False` | pos/kw |
| `enabled_features` | `set` | `<factory>` | pos/kw |

### `Preview`

mypyc filler docstring

```python
black.linegen.Preview(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `RHSResult`

```python
black.linegen.RHSResult(self, head: black.lines.Line, body: black.lines.Line, tail: black.lines.Line, opening_bracket: blib2to3.pytree.Leaf, closing_bracket: blib2to3.pytree.Leaf) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `head` | `Line` | `—` | pos/kw |
| `body` | `Line` | `—` | pos/kw |
| `tail` | `Line` | `—` | pos/kw |
| `opening_bracket` | `Leaf` | `—` | pos/kw |
| `closing_bracket` | `Leaf` | `—` | pos/kw |

### `StringMerger`

```python
black.linegen.StringMerger(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StringParenStripper`

```python
black.linegen.StringParenStripper(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StringParenWrapper`

```python
black.linegen.StringParenWrapper(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StringSplitter`

```python
black.linegen.StringSplitter(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Visitor`

```python
black.linegen.Visitor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

## Functions

### `adjusted_lines`

```python
black.adjusted_lines(lines, original_source, modified_source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `—` | `—` | pos/kw |
| `original_source` | `—` | `—` | pos/kw |
| `modified_source` | `—` | `—` | pos/kw |

### `assert_equivalent`

```python
black.assert_equivalent(src, dst)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `dst` | `—` | `—` | pos/kw |

### `assert_stable`

```python
black.assert_stable(src, dst, mode, *, lines=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `dst` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `lines` | `—` | `()` | kw |

### `best_effort_relative_path`

```python
black.best_effort_relative_path(path: pathlib._local.Path, root: pathlib._local.Path) -> pathlib._local.Path
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |

**Returns:** `<class 'pathlib._local.Path'>`

### `check_stability_and_equivalence`

```python
black.check_stability_and_equivalence(src_contents, dst_contents, *, mode, lines=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_contents` | `—` | `—` | pos/kw |
| `dst_contents` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | kw |
| `lines` | `—` | `()` | kw |

### `color_diff`

Inject the ANSI color codes to the diff.

```python
black.color_diff(contents: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `contents` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_unchanged_lines`

```python
black.convert_unchanged_lines(src_node, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_node` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `decode_bytes`

```python
black.decode_bytes(src, mode, *, encoding_overwrite=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `encoding_overwrite` | `—` | `None` | kw |

### `detect_target_versions`

```python
black.detect_target_versions(node, *, future_imports=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `future_imports` | `—` | `None` | kw |

### `diff`

Return a unified diff string between strings `a` and `b`.

```python
black.diff(a: str, b: str, a_name: str, b_name: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `str` | `—` | pos/kw |
| `b` | `str` | `—` | pos/kw |
| `a_name` | `str` | `—` | pos/kw |
| `b_name` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dump_to_file`

Dump `output` to a temporary file. Return path to the file.

```python
black.dump_to_file(*output: str, ensure_final_newline: bool = True) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `output` | `str` | `—` | *args |
| `ensure_final_newline` | `bool` | `True` | kw |

**Returns:** `<class 'str'>`

### `enable_unstable_feature_callback`

```python
black.enable_unstable_feature_callback(c, p, v)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `c` | `—` | `—` | pos/kw |
| `p` | `—` | `—` | pos/kw |
| `v` | `—` | `—` | pos/kw |

### `err`

```python
black.err(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `find_pyproject_toml`

Find the absolute filepath to a pyproject.toml if it exists

```python
black.find_pyproject_toml(path_search_start: tuple[str, ...], stdin_filename: str | None = None) -> str | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path_search_start` | `tuple` | `—` | pos/kw |
| `stdin_filename` | `str \| None` | `None` | pos/kw |

**Returns:** `str | None`

### `format_cell`

```python
black.format_cell(src, *, fast, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `fast` | `—` | `—` | kw |
| `mode` | `—` | `—` | kw |

### `format_file_contents`

```python
black.format_file_contents(src_contents, *, fast, mode, lines=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_contents` | `—` | `—` | pos/kw |
| `fast` | `—` | `—` | kw |
| `mode` | `—` | `—` | kw |
| `lines` | `—` | `()` | kw |

### `format_file_in_place`

```python
black.format_file_in_place(...)
```

### `format_ipynb_string`

```python
black.format_ipynb_string(src_contents, *, fast, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_contents` | `—` | `—` | pos/kw |
| `fast` | `—` | `—` | kw |
| `mode` | `—` | `—` | kw |

### `format_stdin_to_stdout`

```python
black.format_stdin_to_stdout(...)
```

### `format_str`

```python
black.format_str(src_contents, *, mode, lines=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_contents` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | kw |
| `lines` | `—` | `()` | kw |

### `gen_python_files`

Generate all files under `path` whose paths are not excluded by the
`exclude_regex`, `extend_exclude`, or `force_exclude` regexes,
but are included by the `include` regex.

Symbolic links pointing ou…

```python
black.gen_python_files(paths: collections.abc.Iterable[pathlib._local.Path], root: pathlib._local.Path, include: re.Pattern[str], exclude: re.Pattern[str], extend_exclude: re.Pattern[str] | None, force_exclude: re.Pattern[str] | None, report: black.report.Report, gitignore_dict: dict[pathlib._local.Path, pathspec.gitignore.GitIgnoreSpec] | None, *, verbose: bool, quiet: bool) -> collections.abc.Iterator[pathlib._local.Path]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `Iterable` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `include` | `Pattern` | `—` | pos/kw |
| `exclude` | `Pattern` | `—` | pos/kw |
| `extend_exclude` | `re.Pattern[str] \| None` | `—` | pos/kw |
| `force_exclude` | `re.Pattern[str] \| None` | `—` | pos/kw |
| `report` | `Report` | `—` | pos/kw |
| `gitignore_dict` | `dict[pathlib._local.Path, pathspec.gitignore.GitIgnoreSpec] \| None` | `—` | pos/kw |
| `verbose` | `bool` | `—` | kw |
| `quiet` | `bool` | `—` | kw |

**Returns:** `collections.abc.Iterator[pathlib._local.Path]`

### `get_features_used`

```python
black.get_features_used(node, *, future_imports=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `future_imports` | `—` | `None` | kw |

### `get_future_imports`

```python
black.get_future_imports(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `get_sources`

```python
black.get_sources(*, root, src, quiet, verbose, include, exclude, extend_exclude, force_exclude, report, stdin_filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `—` | `—` | kw |
| `src` | `—` | `—` | kw |
| `quiet` | `—` | `—` | kw |
| `verbose` | `—` | `—` | kw |
| `include` | `—` | `—` | kw |
| `exclude` | `—` | `—` | kw |
| `extend_exclude` | `—` | `—` | kw |
| `force_exclude` | `—` | `—` | kw |
| `report` | `—` | `—` | kw |
| `stdin_filename` | `—` | `—` | kw |

### `ipynb_diff`

Return a unified diff string between each cell in notebooks `a` and `b`.

```python
black.ipynb_diff(a: str, b: str, a_name: str, b_name: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `str` | `—` | pos/kw |
| `b` | `str` | `—` | pos/kw |
| `a_name` | `str` | `—` | pos/kw |
| `b_name` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `is_number_token`

```python
black.is_number_token(nl)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nl` | `—` | `—` | pos/kw |

### `is_simple_decorator_expression`

```python
black.is_simple_decorator_expression(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `lib2to3_parse`

```python
black.lib2to3_parse(src_txt, target_versions=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_txt` | `—` | `—` | pos/kw |
| `target_versions` | `—` | `()` | pos/kw |

### `mask_cell`

```python
black.mask_cell(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `normalize_fmt_off`

```python
black.normalize_fmt_off(node, mode, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `out`

```python
black.out(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `parse_ast`

```python
black.parse_ast(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `parse_line_ranges`

```python
black.parse_line_ranges(line_ranges)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line_ranges` | `—` | `—` | pos/kw |

### `parse_pyproject_toml`

Parse a pyproject toml file, pulling out relevant parts for Black.

If parsing fails, will raise a tomllib.TOMLDecodeError.

```python
black.parse_pyproject_toml(path_config: str) -> dict[str, typing.Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path_config` | `str` | `—` | pos/kw |

**Returns:** `dict[str, typing.Any]`

### `patched_main`

```python
black.patched_main()
```

### `path_is_excluded`

```python
black.path_is_excluded(normalized_path: str, pattern: re.Pattern[str] | None) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `normalized_path` | `str` | `—` | pos/kw |
| `pattern` | `re.Pattern[str] \| None` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `put_trailing_semicolon_back`

```python
black.put_trailing_semicolon_back(src, has_trailing_semicolon)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `has_trailing_semicolon` | `—` | `—` | pos/kw |

### `re_compile_maybe_verbose`

```python
black.re_compile_maybe_verbose(regex)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `regex` | `—` | `—` | pos/kw |

### `read_pyproject_toml`

```python
black.read_pyproject_toml(ctx, param, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |
| `param` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `reformat_code`

```python
black.reformat_code(content, fast, write_back, mode, report, *, lines=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `content` | `—` | `—` | pos/kw |
| `fast` | `—` | `—` | pos/kw |
| `write_back` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `report` | `—` | `—` | pos/kw |
| `lines` | `—` | `()` | kw |

### `reformat_one`

```python
black.reformat_one(src, fast, write_back, mode, report, *, lines=(), no_cache=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `fast` | `—` | `—` | pos/kw |
| `write_back` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `report` | `—` | `—` | pos/kw |
| `lines` | `—` | `()` | kw |
| `no_cache` | `—` | `False` | kw |

### `remove_trailing_semicolon`

```python
black.remove_trailing_semicolon(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `resolves_outside_root_or_cannot_stat`

Returns whether the path is a symbolic link that points outside the
root directory. Also returns True if we failed to resolve the path.

```python
black.resolves_outside_root_or_cannot_stat(path: pathlib._local.Path, root: pathlib._local.Path, report: black.report.Report | None = None) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `report` | `black.report.Report \| None` | `None` | pos/kw |

**Returns:** `<class 'bool'>`

### `sanitized_lines`

```python
black.sanitized_lines(lines, src_contents)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `—` | `—` | pos/kw |
| `src_contents` | `—` | `—` | pos/kw |

### `spellcheck_pyproject_toml_keys`

```python
black.spellcheck_pyproject_toml_keys(ctx, config_keys, config_file_path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |
| `config_keys` | `—` | `—` | pos/kw |
| `config_file_path` | `—` | `—` | pos/kw |

### `stringify_ast`

```python
black.stringify_ast(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `supports_feature`

```python
black.supports_feature(target_versions, feature)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_versions` | `—` | `—` | pos/kw |
| `feature` | `—` | `—` | pos/kw |

### `target_version_option_callback`

```python
black.target_version_option_callback(c, p, v)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `c` | `—` | `—` | pos/kw |
| `p` | `—` | `—` | pos/kw |
| `v` | `—` | `—` | pos/kw |

### `transform_line`

```python
black.transform_line(line, mode, features=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `features` | `—` | `()` | pos/kw |

### `unmask_cell`

```python
black.unmask_cell(src, replacements)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `replacements` | `—` | `—` | pos/kw |

### `validate_cell`

```python
black.validate_cell(src, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `validate_metadata`

```python
black.validate_metadata(nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `validate_regex`

```python
black.validate_regex(ctx, param, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |
| `param` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `wrap_stream_for_windows`

Wrap stream with colorama's wrap_stream so colors are shown on Windows.

If `colorama` is unavailable, the original stream is returned unmodified.
Otherwise, the `wrap_stream()` function determines w…

```python
black.wrap_stream_for_windows(f: _io.TextIOWrapper) -> Union[_io.TextIOWrapper, ForwardRef('colorama.AnsiToWin32')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `f` | `TextIOWrapper` | `—` | pos/kw |

**Returns:** `typing.Union[_io.TextIOWrapper, ForwardRef('colorama.AnsiToWin32')]`

### `get_leaves_inside_matching_brackets`

```python
black.brackets.get_leaves_inside_matching_brackets(leaves)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaves` | `—` | `—` | pos/kw |

### `is_split_after_delimiter`

```python
black.brackets.is_split_after_delimiter(leaf)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |

### `is_split_before_delimiter`

```python
black.brackets.is_split_before_delimiter(leaf, previous=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |
| `previous` | `—` | `None` | pos/kw |

### `is_vararg`

```python
black.brackets.is_vararg(leaf, within)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |
| `within` | `—` | `—` | pos/kw |

### `max_delimiter_priority_in_atom`

```python
black.brackets.max_delimiter_priority_in_atom(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `err`

```python
black.cache.err(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `get_cache_dir`

```python
black.cache.get_cache_dir()
```

### `get_cache_file`

```python
black.cache.get_cache_file(mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `—` | `—` | pos/kw |

### `children_contains_fmt_on`

```python
black.comments.children_contains_fmt_on(container, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `container` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `container_of`

```python
black.comments.container_of(leaf)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |

### `contains_fmt_directive`

```python
black.comments.contains_fmt_directive(...)
```

### `contains_pragma_comment`

```python
black.comments.contains_pragma_comment(comment_list)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `comment_list` | `—` | `—` | pos/kw |

### `convert_one_fmt_off_pair`

```python
black.comments.convert_one_fmt_off_pair(node, mode, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `first_leaf_of`

```python
black.comments.first_leaf_of(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `generate_comments`

```python
black.comments.generate_comments(leaf, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `generate_ignored_nodes`

```python
black.comments.generate_ignored_nodes(leaf, comment, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |
| `comment` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `is_fmt_on`

```python
black.comments.is_fmt_on(container, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `container` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `is_type_comment_string`

```python
black.comments.is_type_comment_string(value, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `make_comment`

```python
black.comments.make_comment(content, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `content` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `make_simple_prefix`

```python
black.comments.make_simple_prefix(nl_count, form_feed, empty_line='\n')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nl_count` | `—` | `—` | pos/kw |
| `form_feed` | `—` | `—` | pos/kw |
| `empty_line` | `—` | `'\n'` | pos/kw |

### `normalize_fmt_off`

```python
black.comments.normalize_fmt_off(node, mode, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `normalize_trailing_prefix`

```python
black.comments.normalize_trailing_prefix(leaf, total_consumed)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |
| `total_consumed` | `—` | `—` | pos/kw |

### `preceding_leaf`

```python
black.comments.preceding_leaf(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `cancel`

asyncio signal handler that cancels all `tasks` and reports to stderr.

```python
black.concurrency.cancel(tasks: 'Iterable[asyncio.Future[Any]]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tasks` | `Iterable[asyncio.Future[Any]]` | `—` | pos/kw |

### `err`

```python
black.concurrency.err(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `format_file_in_place`

```python
black.concurrency.format_file_in_place(...)
```

### `maybe_use_uvloop`

If our environment has uvloop or winloop installed we use it otherwise
a normal asyncio eventloop is called as fallback.

This is called only from command-line entry points to avoid
interfering with…

```python
black.concurrency.maybe_use_uvloop() -> 'asyncio.AbstractEventLoop'
```

**Returns:** `asyncio.AbstractEventLoop`

### `reformat_many`

Reformat multiple files using a ProcessPoolExecutor.

```python
black.concurrency.reformat_many(sources: 'set[Path]', fast: 'bool', write_back: 'WriteBack', mode: 'Mode', report: 'Report', workers: 'int | None', no_cache: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sources` | `set[Path]` | `—` | pos/kw |
| `fast` | `bool` | `—` | pos/kw |
| `write_back` | `WriteBack` | `—` | pos/kw |
| `mode` | `Mode` | `—` | pos/kw |
| `report` | `Report` | `—` | pos/kw |
| `workers` | `int \| None` | `—` | pos/kw |
| `no_cache` | `bool` | `False` | pos/kw |

### `schedule_formatting`

Run formatting of `sources` in parallel using the provided `executor`.

(Use ProcessPoolExecutors for actual parallelism.)

`write_back`, `fast`, and `mode` options are passed to
:func:`format_file_i…

```python
black.concurrency.schedule_formatting(sources: 'set[Path]', fast: 'bool', write_back: 'WriteBack', mode: 'Mode', report: 'Report', loop: 'asyncio.AbstractEventLoop', executor: 'Executor', no_cache: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sources` | `set[Path]` | `—` | pos/kw |
| `fast` | `bool` | `—` | pos/kw |
| `write_back` | `WriteBack` | `—` | pos/kw |
| `mode` | `Mode` | `—` | pos/kw |
| `report` | `Report` | `—` | pos/kw |
| `loop` | `asyncio.AbstractEventLoop` | `—` | pos/kw |
| `executor` | `Executor` | `—` | pos/kw |
| `no_cache` | `bool` | `False` | pos/kw |

### `shutdown`

Cancel all pending tasks on `loop`, wait for them, and close the loop.

```python
black.concurrency.shutdown(loop: 'asyncio.AbstractEventLoop') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loop` | `asyncio.AbstractEventLoop` | `—` | pos/kw |

### `lib2to3_parse`

```python
black.debug.lib2to3_parse(src_txt, target_versions=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src_txt` | `—` | `—` | pos/kw |
| `target_versions` | `—` | `()` | pos/kw |

### `out`

```python
black.debug.out(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `best_effort_relative_path`

```python
black.files.best_effort_relative_path(path: pathlib._local.Path, root: pathlib._local.Path) -> pathlib._local.Path
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |

**Returns:** `<class 'pathlib._local.Path'>`

### `err`

```python
black.files.err(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `find_pyproject_toml`

Find the absolute filepath to a pyproject.toml if it exists

```python
black.files.find_pyproject_toml(path_search_start: tuple[str, ...], stdin_filename: str | None = None) -> str | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path_search_start` | `tuple` | `—` | pos/kw |
| `stdin_filename` | `str \| None` | `None` | pos/kw |

**Returns:** `str | None`

### `gen_python_files`

Generate all files under `path` whose paths are not excluded by the
`exclude_regex`, `extend_exclude`, or `force_exclude` regexes,
but are included by the `include` regex.

Symbolic links pointing ou…

```python
black.files.gen_python_files(paths: collections.abc.Iterable[pathlib._local.Path], root: pathlib._local.Path, include: re.Pattern[str], exclude: re.Pattern[str], extend_exclude: re.Pattern[str] | None, force_exclude: re.Pattern[str] | None, report: black.report.Report, gitignore_dict: dict[pathlib._local.Path, pathspec.gitignore.GitIgnoreSpec] | None, *, verbose: bool, quiet: bool) -> collections.abc.Iterator[pathlib._local.Path]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `Iterable` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `include` | `Pattern` | `—` | pos/kw |
| `exclude` | `Pattern` | `—` | pos/kw |
| `extend_exclude` | `re.Pattern[str] \| None` | `—` | pos/kw |
| `force_exclude` | `re.Pattern[str] \| None` | `—` | pos/kw |
| `report` | `Report` | `—` | pos/kw |
| `gitignore_dict` | `dict[pathlib._local.Path, pathspec.gitignore.GitIgnoreSpec] \| None` | `—` | pos/kw |
| `verbose` | `bool` | `—` | kw |
| `quiet` | `bool` | `—` | kw |

**Returns:** `collections.abc.Iterator[pathlib._local.Path]`

### `infer_target_version`

Infer Black's target version from the project metadata in pyproject.toml.

Supports the PyPA standard format (PEP 621):
https://packaging.python.org/en/latest/specifications/declaring-project-metadat…

```python
black.files.infer_target_version(pyproject_toml: dict[str, typing.Any]) -> list[black.mode.TargetVersion] | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pyproject_toml` | `dict` | `—` | pos/kw |

**Returns:** `list[black.mode.TargetVersion] | None`

### `parse_pyproject_toml`

Parse a pyproject toml file, pulling out relevant parts for Black.

If parsing fails, will raise a tomllib.TOMLDecodeError.

```python
black.files.parse_pyproject_toml(path_config: str) -> dict[str, typing.Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path_config` | `str` | `—` | pos/kw |

**Returns:** `dict[str, typing.Any]`

### `parse_req_python_specifier`

Parse a specifier string (i.e. ``">=3.7,<3.10"``) to a list of TargetVersion.

If parsing fails, will raise a packaging.specifiers.InvalidSpecifier error.
If the parsed specifier cannot be mapped to…

```python
black.files.parse_req_python_specifier(requires_python: str) -> list[black.mode.TargetVersion] | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `requires_python` | `str` | `—` | pos/kw |

**Returns:** `list[black.mode.TargetVersion] | None`

### `parse_req_python_version`

Parse a version string (i.e. ``"3.7"``) to a list of TargetVersion.

If parsing fails, will raise a packaging.version.InvalidVersion error.
If the parsed version cannot be mapped to a valid TargetVer…

```python
black.files.parse_req_python_version(requires_python: str) -> list[black.mode.TargetVersion] | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `requires_python` | `str` | `—` | pos/kw |

**Returns:** `list[black.mode.TargetVersion] | None`

### `path_is_excluded`

```python
black.files.path_is_excluded(normalized_path: str, pattern: re.Pattern[str] | None) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `normalized_path` | `str` | `—` | pos/kw |
| `pattern` | `re.Pattern[str] \| None` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `resolves_outside_root_or_cannot_stat`

Returns whether the path is a symbolic link that points outside the
root directory. Also returns True if we failed to resolve the path.

```python
black.files.resolves_outside_root_or_cannot_stat(path: pathlib._local.Path, root: pathlib._local.Path, report: black.report.Report | None = None) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `root` | `Path` | `—` | pos/kw |
| `report` | `black.report.Report \| None` | `None` | pos/kw |

**Returns:** `<class 'bool'>`

### `strip_specifier_set`

Strip minor versions for some specifiers in the specifier set.

For background on version specifiers, see PEP 440:
https://peps.python.org/pep-0440/#version-specifiers

```python
black.files.strip_specifier_set(specifier_set: packaging.specifiers.SpecifierSet) -> packaging.specifiers.SpecifierSet
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `specifier_set` | `SpecifierSet` | `—` | pos/kw |

**Returns:** `<class 'packaging.specifiers.SpecifierSet'>`

### `wrap_stream_for_windows`

Wrap stream with colorama's wrap_stream so colors are shown on Windows.

If `colorama` is unavailable, the original stream is returned unmodified.
Otherwise, the `wrap_stream()` function determines w…

```python
black.files.wrap_stream_for_windows(f: _io.TextIOWrapper) -> Union[_io.TextIOWrapper, ForwardRef('colorama.AnsiToWin32')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `f` | `TextIOWrapper` | `—` | pos/kw |

**Returns:** `typing.Union[_io.TextIOWrapper, ForwardRef('colorama.AnsiToWin32')]`

### `create_token`

```python
black.handle_ipynb_magics.create_token(n_chars)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `n_chars` | `—` | `—` | pos/kw |

### `get_token`

```python
black.handle_ipynb_magics.get_token(src, magic, existing_tokens=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `magic` | `—` | `—` | pos/kw |
| `existing_tokens` | `—` | `()` | pos/kw |

### `mask_cell`

```python
black.handle_ipynb_magics.mask_cell(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `out`

```python
black.handle_ipynb_magics.out(message: str | None = None, nl: bool = True, **styles: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str \| None` | `None` | pos/kw |
| `nl` | `bool` | `True` | pos/kw |
| `styles` | `Any` | `—` | **kwargs |

### `put_trailing_semicolon_back`

```python
black.handle_ipynb_magics.put_trailing_semicolon_back(src, has_trailing_semicolon)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `has_trailing_semicolon` | `—` | `—` | pos/kw |

### `remove_trailing_semicolon`

```python
black.handle_ipynb_magics.remove_trailing_semicolon(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `replace_cell_magics`

```python
black.handle_ipynb_magics.replace_cell_magics(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `replace_magics`

```python
black.handle_ipynb_magics.replace_magics(src)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |

### `unmask_cell`

```python
black.handle_ipynb_magics.unmask_cell(src, replacements)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `replacements` | `—` | `—` | pos/kw |

### `validate_cell`

```python
black.handle_ipynb_magics.validate_cell(src, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `append_leaves`

```python
black.linegen.append_leaves(new_line, old_line, leaves, preformatted=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `new_line` | `—` | `—` | pos/kw |
| `old_line` | `—` | `—` | pos/kw |
| `leaves` | `—` | `—` | pos/kw |
| `preformatted` | `—` | `False` | pos/kw |

### `bracket_split_build_line`

```python
black.linegen.bracket_split_build_line(leaves, original, opening_bracket, *, component)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaves` | `—` | `—` | pos/kw |
| `original` | `—` | `—` | pos/kw |
| `opening_bracket` | `—` | `—` | pos/kw |
| `component` | `—` | `—` | kw |

### `bracket_split_succeeded_or_raise`

```python
black.linegen.bracket_split_succeeded_or_raise(head, body, tail)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `head` | `—` | `—` | pos/kw |
| `body` | `—` | `—` | pos/kw |
| `tail` | `—` | `—` | pos/kw |

### `can_be_split`

```python
black.linegen.can_be_split(line)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |

### `can_omit_invisible_parens`

```python
black.linegen.can_omit_invisible_parens(rhs, line_length)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `rhs` | `—` | `—` | pos/kw |
| `line_length` | `—` | `—` | pos/kw |

### `contains_fmt_directive`

```python
black.linegen.contains_fmt_directive(...)
```

### `dont_increase_indentation`

```python
black.linegen.dont_increase_indentation(split_func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `split_func` | `—` | `—` | pos/kw |

### `ensure_visible`

```python
black.linegen.ensure_visible(leaf)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |

### `fix_multiline_docstring`

```python
black.linegen.fix_multiline_docstring(docstring, prefix)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `—` | `—` | pos/kw |
| `prefix` | `—` | `—` | pos/kw |

### `fstring_tstring_to_string`

```python
black.linegen.fstring_tstring_to_string(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `generate_comments`

```python
black.linegen.generate_comments(leaf, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `generate_trailers_to_omit`

```python
black.linegen.generate_trailers_to_omit(line, line_length)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |
| `line_length` | `—` | `—` | pos/kw |

### `get_annotation_type`

```python
black.linegen.get_annotation_type(leaf)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |

### `get_leaves_inside_matching_brackets`

```python
black.linegen.get_leaves_inside_matching_brackets(leaves)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaves` | `—` | `—` | pos/kw |

### `get_string_prefix`

```python
black.linegen.get_string_prefix(string)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `string` | `—` | `—` | pos/kw |

### `has_sibling_with_type`

```python
black.linegen.has_sibling_with_type(node, type)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `type` | `—` | `—` | pos/kw |

### `hug_power_op`

```python
black.linegen.hug_power_op(line, features, mode)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |
| `features` | `—` | `—` | pos/kw |
| `mode` | `—` | `—` | pos/kw |

### `is_arith_like`

```python
black.linegen.is_arith_like(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `is_async_stmt_or_funcdef`

```python
black.linegen.is_async_stmt_or_funcdef(leaf)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `leaf` | `—` | `—` | pos/kw |

### `is_atom_with_invisible_parens`

```python
black.linegen.is_atom_with_invisible_parens(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `is_docstring`

```python
black.linegen.is_docstring(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `is_empty_tuple`

```python
black.linegen.is_empty_tuple(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `is_generator`

```python
black.linegen.is_generator(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

## Methods

### `black.Report` methods

### `done`

Increment the counter for successful reformatting. Write out a message.

```python
black.Report.done(self, src: pathlib._local.Path, changed: black.report.Changed) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `Path` | `—` | pos/kw |
| `changed` | `Changed` | `—` | pos/kw |

### `failed`

Increment the counter for failed reformatting. Write out a message.

```python
black.Report.failed(self, src: pathlib._local.Path, message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `Path` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

### `path_ignored`

```python
black.Report.path_ignored(self, path: pathlib._local.Path, message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `Path` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

### `black.concurrency.Report` methods

### `done`

Increment the counter for successful reformatting. Write out a message.

```python
black.concurrency.Report.done(self, src: pathlib._local.Path, changed: black.report.Changed) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `Path` | `—` | pos/kw |
| `changed` | `Changed` | `—` | pos/kw |

### `failed`

Increment the counter for failed reformatting. Write out a message.

```python
black.concurrency.Report.failed(self, src: pathlib._local.Path, message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `Path` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

### `path_ignored`

```python
black.concurrency.Report.path_ignored(self, path: pathlib._local.Path, message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `Path` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

### `black.debug.DebugVisitor` methods

### `out`

```python
black.debug.DebugVisitor.out(self, message: str, *args: Any, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `show`

Pretty-print the lib2to3 AST of a given string of `code`.

Convenience method for debugging.

```python
black.debug.DebugVisitor.show(code: str | blib2to3.pytree.Leaf | blib2to3.pytree.Node) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `str \| blib2to3.pytree.Leaf \| blib2to3.pytree.Node` | `—` | pos/kw |

### `visit_default`

```python
black.debug.DebugVisitor.visit_default(self, node: Union[blib2to3.pytree.Leaf, blib2to3.pytree.Node]) -> collections.abc.Iterator[~T]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `Union` | `—` | pos/kw |

**Returns:** `collections.abc.Iterator[~T]`

### `black.files.Report` methods

### `done`

Increment the counter for successful reformatting. Write out a message.

```python
black.files.Report.done(self, src: pathlib._local.Path, changed: black.report.Changed) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `Path` | `—` | pos/kw |
| `changed` | `Changed` | `—` | pos/kw |

### `failed`

Increment the counter for failed reformatting. Write out a message.

```python
black.files.Report.failed(self, src: pathlib._local.Path, message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `src` | `Path` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

### `path_ignored`

```python
black.files.Report.path_ignored(self, path: pathlib._local.Path, message: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `Path` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

### `black.handle_ipynb_magics.CellMagicFinder` methods

### `generic_visit`

Called if no explicit visitor function exists for a node.

```python
black.handle_ipynb_magics.CellMagicFinder.generic_visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit`

Visit a node.

```python
black.handle_ipynb_magics.CellMagicFinder.visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Constant`

```python
black.handle_ipynb_magics.CellMagicFinder.visit_Constant(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `black.handle_ipynb_magics.MagicFinder` methods

### `generic_visit`

Called if no explicit visitor function exists for a node.

```python
black.handle_ipynb_magics.MagicFinder.generic_visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit`

Visit a node.

```python
black.handle_ipynb_magics.MagicFinder.visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Constant`

```python
black.handle_ipynb_magics.MagicFinder.visit_Constant(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |


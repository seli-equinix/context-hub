---
name: package
description: "autopep8 package guide for formatting Python code to PEP 8 with the maintainer's CLI and module API"
metadata:
  languages: "python"
  versions: "2.3.2"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "autopep8,python,pep8,formatter,pycodestyle,pre-commit,toml,fix_code,Version-Sensitive,Atom,emit,reflow,CachedTokenizer,generate_tokens,Container,DictOrSet,FixPEP8,fix,fix_e112,fix_e113,fix_e116,fix_e117,fix_e125,fix_e131,fix_e201,fix_e224,fix_e225,fix_e231,fix_e251,fix_e262,fix_e265,fix_e266,fix_e271,fix_e301,fix_e302,fix_e303,fix_e304,fix_e305,fix_e401,fix_e402,fix_e502,fix_e701,fix_e702,fix_e704,fix_e711,fix_e712,fix_e713,IfExpression,LineEndingWrapper,flush,write,List,ListComprehension,ReformattedLines,add,add_comment,add_indent,add_line_break,add_line_break_at,add_space_if_needed,current_size,fits_on_current_line,line_empty,previous_item,Reindenter,getline,run,Token,Tuple,apply_global_fixes,check_syntax,code_almost_equal,code_match,commented_out_code_lines,continued_indentation,count_unbalanced_brackets,create_parser,decode_filename,detect_encoding,docstring_summary,extended_blank_lines,extract_code_from_function,filter_disabled_results,filter_results,find_files,find_newline,find_with_line_numbers,fix_file,fix_lines,fix_multiple_files,fix_whitespace,get_diff_text,get_disabled_ranges,get_encoding,get_fixed_long_line,get_index_offset_contents,get_item,get_module_imports_on_top_of_file,global_fixes,has_arithmetic_operator,is_probably_part_of_multiline,is_python_file,join_logical_line,line_shortening_rank,longest_line_length,main,match_file,multiline_string_lines,mutual_startswith,normalize_line_endings,normalize_multiline,open_with_encoding,parse_args,read_config,read_pyproject_toml,readlines_from_file,reindent,shorten_comment,shorten_line,split_and_strip_non_empty_lines,split_at_offsets,standard_deviation,supported_fixes,token_offsets,untokenize_without_newlines,wrap_output"
---

# autopep8 — package

Automatically formats Python code to conform to the PEP 8 style guide.

Fixes that only need be done once can be added by adding a function of the form
"fix_<code>(source)" to this module. They should return the fixed source code.
These fixes are picked up by apply_global_fixes().

Fixes that depend on pycodestyle should be added as methods to FixPEP8. See the
class documentation for more information.

## Install

```bash
pip install autopep8
```

## Imports

```python
import autopep8
```

## Symbols (125)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Atom` | Class | The smallest unbreakable unit that can be reflowed. |
| `emit` | Method |  |
| `reflow` | Method |  |
| `CachedTokenizer` | Class | A one-element cache around tokenize.generate_tokens().  Original code written b… |
| `generate_tokens` | Method | A stand-in for tokenize.generate_tokens(). |
| `Container` | Class | Base class for all container types. |
| `reflow` | Method |  |
| `DictOrSet` | Class | A high-level representation of a dictionary or set. |
| `reflow` | Method |  |
| `FixPEP8` | Class | Fix invalid code.  Fixer methods are prefixed "fix_". The _fix_source() method… |
| `fix` | Method | Return a version of the source code with PEP 8 violations fixed. |
| `fix_e112` | Method | Fix under-indented comments. |
| `fix_e113` | Method | Fix unexpected indentation. |
| `fix_e116` | Method | Fix over-indented comments. |
| `fix_e117` | Method | Fix over-indented. |
| `fix_e125` | Method | Fix indentation undistinguish from the next logical line. |
| `fix_e131` | Method | Fix indentation undistinguish from the next logical line. |
| `fix_e201` | Method | Remove extraneous whitespace. |
| `fix_e224` | Method | Remove extraneous whitespace around operator. |
| `fix_e225` | Method | Fix missing whitespace around operator. |
| `fix_e231` | Method | Add missing whitespace. |
| `fix_e251` | Method | Remove whitespace around parameter '=' sign. |
| `fix_e262` | Method | Fix spacing after inline comment hash. |
| `fix_e265` | Method | Fix spacing after block comment hash. |
| `fix_e266` | Method | Fix too many block comment hashes. |
| `fix_e271` | Method | Fix extraneous whitespace around keywords. |
| `fix_e301` | Method | Add missing blank line. |
| `fix_e302` | Method | Add missing 2 blank lines. |
| `fix_e303` | Method | Remove extra blank lines. |
| `fix_e304` | Method | Remove blank line following function decorator. |

_Plus 95 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `Atom`

The smallest unbreakable unit that can be reflowed.

```python
autopep8.Atom(self, atom)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `atom` | `—` | `—` | pos/kw |

### `CachedTokenizer`

A one-element cache around tokenize.generate_tokens().

Original code written by Ned Batchelder, in coverage.py.

```python
autopep8.CachedTokenizer(self)
```

### `Container`

Base class for all container types.

```python
autopep8.Container(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

### `DictOrSet`

A high-level representation of a dictionary or set.

```python
autopep8.DictOrSet(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

### `FixPEP8`

Fix invalid code.

Fixer methods are prefixed "fix_". The _fix_source() method looks for these
automatically.

The fixer method can take either one or two arguments (in addition to
self). The first a…

```python
autopep8.FixPEP8(self, filename, options, contents=None, long_line_ignore_cache=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `contents` | `—` | `None` | pos/kw |
| `long_line_ignore_cache` | `—` | `None` | pos/kw |

### `IfExpression`

A high-level representation of an if-expression.

```python
autopep8.IfExpression(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

### `LineEndingWrapper`

Replace line endings to work with sys.stdout.

It seems that sys.stdout expects only '\n' as the line ending, no matter
the platform. Otherwise, we get repeated line endings.

```python
autopep8.LineEndingWrapper(self, output)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `output` | `—` | `—` | pos/kw |

### `List`

A high-level representation of a list.

```python
autopep8.List(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

### `ListComprehension`

A high-level representation of a list comprehension.

```python
autopep8.ListComprehension(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

### `ReformattedLines`

The reflowed lines of atoms.

Each part of the line is represented as an "atom." They can be moved
around when need be to get the optimal formatting.

```python
autopep8.ReformattedLines(self, max_line_length)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `max_line_length` | `—` | `—` | pos/kw |

### `Reindenter`

Reindents badly-indented code to uniformly use four-space indentation.

Released to the public domain, by Tim Peters, 03 October 2000.

```python
autopep8.Reindenter(self, input_text, leave_tabs=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `input_text` | `—` | `—` | pos/kw |
| `leave_tabs` | `—` | `False` | pos/kw |

### `Token`

Token(token_type, token_string, spos, epos, line)

```python
autopep8.Token(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Tuple`

A high-level representation of a tuple.

```python
autopep8.Tuple(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

## Functions

### `apply_global_fixes`

Run global fixes on source code.

These are fixes that only need be done once (unlike those in
FixPEP8, which are dependent on pycodestyle).

```python
autopep8.apply_global_fixes(source, options, where='global', filename='', codes=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `where` | `—` | `'global'` | pos/kw |
| `filename` | `—` | `''` | pos/kw |
| `codes` | `—` | `None` | pos/kw |

### `check_syntax`

Return True if syntax is okay.

```python
autopep8.check_syntax(code)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `—` | `—` | pos/kw |

### `code_almost_equal`

Return True if code is similar.

Ignore whitespace when comparing specific line.

```python
autopep8.code_almost_equal(a, b)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |

### `code_match`

```python
autopep8.code_match(code, select, ignore)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `—` | `—` | pos/kw |
| `select` | `—` | `—` | pos/kw |
| `ignore` | `—` | `—` | pos/kw |

### `commented_out_code_lines`

Return line numbers of comments that are likely code.

Commented-out code is bad practice, but modifying it just adds even
more clutter.

```python
autopep8.commented_out_code_lines(source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |

### `continued_indentation`

Override pycodestyle's function to provide indentation information.

```python
autopep8.continued_indentation(logical_line, tokens, indent_level, hang_closing, indent_char, noqa)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logical_line` | `—` | `—` | pos/kw |
| `tokens` | `—` | `—` | pos/kw |
| `indent_level` | `—` | `—` | pos/kw |
| `hang_closing` | `—` | `—` | pos/kw |
| `indent_char` | `—` | `—` | pos/kw |
| `noqa` | `—` | `—` | pos/kw |

### `count_unbalanced_brackets`

Return number of unmatched open/close brackets.

```python
autopep8.count_unbalanced_brackets(line)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |

### `create_parser`

Return command-line parser.

```python
autopep8.create_parser()
```

### `decode_filename`

Return Unicode filename.

```python
autopep8.decode_filename(filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |

### `detect_encoding`

Return file encoding.

```python
autopep8.detect_encoding(filename, limit_byte_check=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `limit_byte_check` | `—` | `-1` | pos/kw |

### `docstring_summary`

Return summary of docstring.

```python
autopep8.docstring_summary(docstring)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `docstring` | `—` | `—` | pos/kw |

### `extended_blank_lines`

Check for missing blank lines after class declaration.

```python
autopep8.extended_blank_lines(logical_line, blank_lines, blank_before, indent_level, previous_logical)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logical_line` | `—` | `—` | pos/kw |
| `blank_lines` | `—` | `—` | pos/kw |
| `blank_before` | `—` | `—` | pos/kw |
| `indent_level` | `—` | `—` | pos/kw |
| `previous_logical` | `—` | `—` | pos/kw |

### `extract_code_from_function`

Return code handled by function.

```python
autopep8.extract_code_from_function(function)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `function` | `—` | `—` | pos/kw |

### `filter_disabled_results`

Filter out reports based on tuple of disabled ranges.

```python
autopep8.filter_disabled_results(result, disabled_ranges)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `result` | `—` | `—` | pos/kw |
| `disabled_ranges` | `—` | `—` | pos/kw |

### `filter_results`

Filter out spurious reports from pycodestyle.

If aggressive is True, we allow possibly unsafe fixes (E711, E712).

```python
autopep8.filter_results(source, results, aggressive)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `results` | `—` | `—` | pos/kw |
| `aggressive` | `—` | `—` | pos/kw |

### `find_files`

Yield filenames.

```python
autopep8.find_files(filenames, recursive, exclude)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filenames` | `—` | `—` | pos/kw |
| `recursive` | `—` | `—` | pos/kw |
| `exclude` | `—` | `—` | pos/kw |

### `find_newline`

Return type of newline used in source.

Input is a list of lines.

```python
autopep8.find_newline(source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |

### `find_with_line_numbers`

A wrapper around 're.finditer' to find line numbers.

Returns a list of line numbers where pattern was found in contents.

```python
autopep8.find_with_line_numbers(pattern, contents)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pattern` | `—` | `—` | pos/kw |
| `contents` | `—` | `—` | pos/kw |

### `fix_code`

Return fixed source code.

"encoding" will be used to decode "source" if it is a byte string.

```python
autopep8.fix_code(source, options=None, encoding=None, apply_config=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `options` | `—` | `None` | pos/kw |
| `encoding` | `—` | `None` | pos/kw |
| `apply_config` | `—` | `False` | pos/kw |

### `fix_file`

```python
autopep8.fix_file(filename, options=None, output=None, apply_config=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `options` | `—` | `None` | pos/kw |
| `output` | `—` | `None` | pos/kw |
| `apply_config` | `—` | `False` | pos/kw |

### `fix_lines`

Return fixed source code.

```python
autopep8.fix_lines(source_lines, options, filename='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source_lines` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `filename` | `—` | `''` | pos/kw |

### `fix_multiple_files`

Fix list of files.

Optionally fix files recursively.

```python
autopep8.fix_multiple_files(filenames, options, output=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filenames` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `output` | `—` | `None` | pos/kw |

### `fix_whitespace`

Replace whitespace at offset and return fixed line.

```python
autopep8.fix_whitespace(line, offset, replacement)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |
| `offset` | `—` | `—` | pos/kw |
| `replacement` | `—` | `—` | pos/kw |

### `get_diff_text`

Return text of unified diff between old and new.

```python
autopep8.get_diff_text(old, new, filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old` | `—` | `—` | pos/kw |
| `new` | `—` | `—` | pos/kw |
| `filename` | `—` | `—` | pos/kw |

### `get_disabled_ranges`

Returns a list of tuples representing the disabled ranges.

If disabled and no re-enable will disable for rest of file.

```python
autopep8.get_disabled_ranges(source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |

### `get_encoding`

Return preferred encoding.

```python
autopep8.get_encoding()
```

### `get_fixed_long_line`

Break up long line and return result.

Do this by generating multiple reformatted candidates and then
ranking the candidates to heuristically select the best option.

```python
autopep8.get_fixed_long_line(target, previous_line, original, indent_word='    ', max_line_length=79, aggressive=0, experimental=False, verbose=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target` | `—` | `—` | pos/kw |
| `previous_line` | `—` | `—` | pos/kw |
| `original` | `—` | `—` | pos/kw |
| `indent_word` | `—` | `'    '` | pos/kw |
| `max_line_length` | `—` | `79` | pos/kw |
| `aggressive` | `—` | `0` | pos/kw |
| `experimental` | `—` | `False` | pos/kw |
| `verbose` | `—` | `False` | pos/kw |

### `get_index_offset_contents`

Return (line_index, column_offset, line_contents).

```python
autopep8.get_index_offset_contents(result, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `result` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `get_item`

```python
autopep8.get_item(items, index, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |
| `index` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `get_module_imports_on_top_of_file`

return import or from keyword position

example:
  > 0: import sys
    1: import os
    2:
    3: def function():

```python
autopep8.get_module_imports_on_top_of_file(source, import_line_index)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `import_line_index` | `—` | `—` | pos/kw |

### `global_fixes`

Yield multiple (code, function) tuples.

```python
autopep8.global_fixes()
```

### `has_arithmetic_operator`

Return True if line contains any arithmetic operators.

```python
autopep8.has_arithmetic_operator(line)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |

### `is_probably_part_of_multiline`

Return True if line is likely part of a multiline string.

When multiline strings are involved, pep8 reports the error as being
at the start of the multiline string, which doesn't work for us.

```python
autopep8.is_probably_part_of_multiline(line)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |

### `is_python_file`

Return True if filename is Python file.

```python
autopep8.is_python_file(filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |

### `join_logical_line`

Return single line based on logical line input.

```python
autopep8.join_logical_line(logical_line)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `logical_line` | `—` | `—` | pos/kw |

### `line_shortening_rank`

Return rank of candidate.

This is for sorting candidates.

```python
autopep8.line_shortening_rank(candidate, indent_word, max_line_length, experimental=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `candidate` | `—` | `—` | pos/kw |
| `indent_word` | `—` | `—` | pos/kw |
| `max_line_length` | `—` | `—` | pos/kw |
| `experimental` | `—` | `False` | pos/kw |

### `longest_line_length`

Return length of longest line.

```python
autopep8.longest_line_length(code)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `—` | `—` | pos/kw |

### `main`

Command-line entry.

```python
autopep8.main(argv=None, apply_config=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `—` | `None` | pos/kw |
| `apply_config` | `—` | `True` | pos/kw |

### `match_file`

Return True if file is okay for modifying/recursing.

```python
autopep8.match_file(filename, exclude)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `exclude` | `—` | `—` | pos/kw |

### `multiline_string_lines`

Return line numbers that are within multiline strings.

The line numbers are indexed at 1.

Docstrings are ignored.

```python
autopep8.multiline_string_lines(source, include_docstrings=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `include_docstrings` | `—` | `False` | pos/kw |

### `mutual_startswith`

```python
autopep8.mutual_startswith(a, b)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |

### `normalize_line_endings`

Return fixed line endings.

All lines will be modified to use the most common line ending.

```python
autopep8.normalize_line_endings(lines, newline)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `—` | `—` | pos/kw |
| `newline` | `—` | `—` | pos/kw |

### `normalize_multiline`

Normalize multiline-related code that will cause syntax error.

This is for purposes of checking syntax.

```python
autopep8.normalize_multiline(line)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |

### `open_with_encoding`

Return opened file with a specific encoding.

```python
autopep8.open_with_encoding(filename, mode='r', encoding=None, limit_byte_check=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `mode` | `—` | `'r'` | pos/kw |
| `encoding` | `—` | `None` | pos/kw |
| `limit_byte_check` | `—` | `-1` | pos/kw |

### `parse_args`

Parse command-line options.

```python
autopep8.parse_args(arguments, apply_config=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `arguments` | `—` | `—` | pos/kw |
| `apply_config` | `—` | `False` | pos/kw |

### `read_config`

Read both user configuration and local configuration.

```python
autopep8.read_config(args, parser)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |
| `parser` | `—` | `—` | pos/kw |

### `read_pyproject_toml`

Read pyproject.toml and load configuration.

```python
autopep8.read_pyproject_toml(args, parser)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |
| `parser` | `—` | `—` | pos/kw |

### `readlines_from_file`

Return contents of file.

```python
autopep8.readlines_from_file(filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |

### `reindent`

Reindent all lines.

```python
autopep8.reindent(source, indent_size, leave_tabs=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `indent_size` | `—` | `—` | pos/kw |
| `leave_tabs` | `—` | `False` | pos/kw |

### `shorten_comment`

Return trimmed or split long comment line.

If there are no comments immediately following it, do a text wrap.
Doing this wrapping on all comments in general would lead to jagged
comment text.

```python
autopep8.shorten_comment(line, max_line_length, last_comment=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |
| `max_line_length` | `—` | `—` | pos/kw |
| `last_comment` | `—` | `False` | pos/kw |

### `shorten_line`

Separate line at OPERATOR.

Multiple candidates will be yielded.

```python
autopep8.shorten_line(tokens, source, indentation, indent_word, max_line_length, aggressive=0, experimental=False, previous_line='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tokens` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `indentation` | `—` | `—` | pos/kw |
| `indent_word` | `—` | `—` | pos/kw |
| `max_line_length` | `—` | `—` | pos/kw |
| `aggressive` | `—` | `0` | pos/kw |
| `experimental` | `—` | `False` | pos/kw |
| `previous_line` | `—` | `''` | pos/kw |

### `split_and_strip_non_empty_lines`

Return lines split by newline.

Ignore empty lines.

```python
autopep8.split_and_strip_non_empty_lines(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `split_at_offsets`

Split line at offsets.

Return list of strings.

```python
autopep8.split_at_offsets(line, offsets)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `—` | `—` | pos/kw |
| `offsets` | `—` | `—` | pos/kw |

### `standard_deviation`

Return standard deviation.

```python
autopep8.standard_deviation(numbers)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `numbers` | `—` | `—` | pos/kw |

### `supported_fixes`

Yield pep8 error codes that autopep8 fixes.

Each item we yield is a tuple of the code followed by its
description.

```python
autopep8.supported_fixes()
```

### `token_offsets`

Yield tokens and offsets.

```python
autopep8.token_offsets(tokens)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tokens` | `—` | `—` | pos/kw |

### `untokenize_without_newlines`

Return source code based on tokens.

```python
autopep8.untokenize_without_newlines(tokens)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tokens` | `—` | `—` | pos/kw |

### `wrap_output`

Return output with specified encoding.

```python
autopep8.wrap_output(output, encoding)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `output` | `—` | `—` | pos/kw |
| `encoding` | `—` | `—` | pos/kw |

## Methods

### `autopep8.Atom` methods

### `emit`

```python
autopep8.Atom.emit(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `reflow`

```python
autopep8.Atom.reflow(self, reflowed_lines, continued_indent, extent, break_after_open_bracket=False, is_list_comp_or_if_expr=False, next_is_dot=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `extent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |
| `is_list_comp_or_if_expr` | `—` | `False` | pos/kw |
| `next_is_dot` | `—` | `False` | pos/kw |

### `autopep8.CachedTokenizer` methods

### `generate_tokens`

A stand-in for tokenize.generate_tokens().

```python
autopep8.CachedTokenizer.generate_tokens(self, text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |

### `autopep8.Container` methods

### `reflow`

```python
autopep8.Container.reflow(self, reflowed_lines, continued_indent, break_after_open_bracket=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |

### `autopep8.DictOrSet` methods

### `reflow`

```python
autopep8.DictOrSet.reflow(self, reflowed_lines, continued_indent, break_after_open_bracket=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |

### `autopep8.FixPEP8` methods

### `fix`

Return a version of the source code with PEP 8 violations fixed.

```python
autopep8.FixPEP8.fix(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fix_e112`

Fix under-indented comments.

```python
autopep8.FixPEP8.fix_e112(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e113`

Fix unexpected indentation.

```python
autopep8.FixPEP8.fix_e113(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e116`

Fix over-indented comments.

```python
autopep8.FixPEP8.fix_e116(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e117`

Fix over-indented.

```python
autopep8.FixPEP8.fix_e117(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e125`

Fix indentation undistinguish from the next logical line.

```python
autopep8.FixPEP8.fix_e125(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e131`

Fix indentation undistinguish from the next logical line.

```python
autopep8.FixPEP8.fix_e131(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e201`

Remove extraneous whitespace.

```python
autopep8.FixPEP8.fix_e201(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e224`

Remove extraneous whitespace around operator.

```python
autopep8.FixPEP8.fix_e224(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e225`

Fix missing whitespace around operator.

```python
autopep8.FixPEP8.fix_e225(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e231`

Add missing whitespace.

```python
autopep8.FixPEP8.fix_e231(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e251`

Remove whitespace around parameter '=' sign.

```python
autopep8.FixPEP8.fix_e251(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e262`

Fix spacing after inline comment hash.

```python
autopep8.FixPEP8.fix_e262(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e265`

Fix spacing after block comment hash.

```python
autopep8.FixPEP8.fix_e265(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e266`

Fix too many block comment hashes.

```python
autopep8.FixPEP8.fix_e266(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e271`

Fix extraneous whitespace around keywords.

```python
autopep8.FixPEP8.fix_e271(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e301`

Add missing blank line.

```python
autopep8.FixPEP8.fix_e301(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e302`

Add missing 2 blank lines.

```python
autopep8.FixPEP8.fix_e302(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e303`

Remove extra blank lines.

```python
autopep8.FixPEP8.fix_e303(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e304`

Remove blank line following function decorator.

```python
autopep8.FixPEP8.fix_e304(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e305`

Add missing 2 blank lines after end of function or class.

```python
autopep8.FixPEP8.fix_e305(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e401`

Put imports on separate lines.

```python
autopep8.FixPEP8.fix_e401(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e402`

```python
autopep8.FixPEP8.fix_e402(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e502`

Remove extraneous escape of newline.

```python
autopep8.FixPEP8.fix_e502(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e701`

Put colon-separated compound statement on separate lines.

```python
autopep8.FixPEP8.fix_e701(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e702`

Put semicolon-separated compound statement on separate lines.

```python
autopep8.FixPEP8.fix_e702(self, result, logical)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |
| `logical` | `—` | `—` | pos/kw |

### `fix_e704`

Fix multiple statements on one line def

```python
autopep8.FixPEP8.fix_e704(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e711`

Fix comparison with None.

```python
autopep8.FixPEP8.fix_e711(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e712`

Fix (trivial case of) comparison with boolean.

```python
autopep8.FixPEP8.fix_e712(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `fix_e713`

Fix (trivial case of) non-membership check.

```python
autopep8.FixPEP8.fix_e713(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `result` | `—` | `—` | pos/kw |

### `autopep8.IfExpression` methods

### `reflow`

```python
autopep8.IfExpression.reflow(self, reflowed_lines, continued_indent, break_after_open_bracket=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |

### `autopep8.LineEndingWrapper` methods

### `flush`

```python
autopep8.LineEndingWrapper.flush(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `write`

```python
autopep8.LineEndingWrapper.write(self, s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `s` | `—` | `—` | pos/kw |

### `autopep8.List` methods

### `reflow`

```python
autopep8.List.reflow(self, reflowed_lines, continued_indent, break_after_open_bracket=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |

### `autopep8.ListComprehension` methods

### `reflow`

```python
autopep8.ListComprehension.reflow(self, reflowed_lines, continued_indent, break_after_open_bracket=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |

### `autopep8.ReformattedLines` methods

### `add`

```python
autopep8.ReformattedLines.add(self, obj, indent_amt, break_after_open_bracket)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `indent_amt` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `—` | pos/kw |

### `add_comment`

```python
autopep8.ReformattedLines.add_comment(self, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item` | `—` | `—` | pos/kw |

### `add_indent`

```python
autopep8.ReformattedLines.add_indent(self, indent_amt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `indent_amt` | `—` | `—` | pos/kw |

### `add_line_break`

```python
autopep8.ReformattedLines.add_line_break(self, indent)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `indent` | `—` | `—` | pos/kw |

### `add_line_break_at`

```python
autopep8.ReformattedLines.add_line_break_at(self, index, indent_amt)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `index` | `—` | `—` | pos/kw |
| `indent_amt` | `—` | `—` | pos/kw |

### `add_space_if_needed`

```python
autopep8.ReformattedLines.add_space_if_needed(self, curr_text, equal=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `curr_text` | `—` | `—` | pos/kw |
| `equal` | `—` | `False` | pos/kw |

### `current_size`

The size of the current line minus the indentation.

```python
autopep8.ReformattedLines.current_size(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `emit`

```python
autopep8.ReformattedLines.emit(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fits_on_current_line`

```python
autopep8.ReformattedLines.fits_on_current_line(self, item_extent)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `item_extent` | `—` | `—` | pos/kw |

### `line_empty`

```python
autopep8.ReformattedLines.line_empty(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `previous_item`

Return the previous non-whitespace item.

```python
autopep8.ReformattedLines.previous_item(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `autopep8.Reindenter` methods

### `getline`

Line-getter for tokenize.

```python
autopep8.Reindenter.getline(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `run`

Fix indentation and return modified line numbers.

Line numbers are indexed at 1.

```python
autopep8.Reindenter.run(self, indent_size=4)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `indent_size` | `—` | `4` | pos/kw |

### `autopep8.Tuple` methods

### `reflow`

```python
autopep8.Tuple.reflow(self, reflowed_lines, continued_indent, break_after_open_bracket=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reflowed_lines` | `—` | `—` | pos/kw |
| `continued_indent` | `—` | `—` | pos/kw |
| `break_after_open_bracket` | `—` | `False` | pos/kw |


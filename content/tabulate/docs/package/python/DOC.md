---
name: package
description: "tabulate Python package for formatting iterables and tabular data as plain-text, Markdown, HTML, and LaTeX tables"
metadata:
  languages: "python"
  versions: "0.10.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "tabulate,python,tables,markdown,html,cli,formatting,DataRow,JupyterHTMLStr,Line,TableFormat,simple_separated_format,grid,pipe,latex,rst,github,orgtbl,psql,jira,floatfmt,stralign,numalign"
---

# tabulate — package

Pretty-print tabular data.

## 1. Golden Rule

Use `tabulate` for tabulate python package for formatting iterables and tabular data as plain-text, markdown, html, and latex tables.

### Install

```bash
pip install tabulate
```

### Imports

```python
import tabulate
```

## 2. Core Operations

### 1. `tabulate`

Format a fixed width table for pretty printing.

>>> print(tabulate([[1, 2.34], [-56, "8.999"], ["2", "10001"]]))
---  ---------
  1      2.34
-56      8.999
  2  10001
---  ---------

The first required argument (`tabular_data`) can be a
list-of-lists (or another iterable of iterables), a list of…

```python
tabulate.tabulate(tabular_data, headers=(), tablefmt='simple', floatfmt='g', intfmt='', numalign='default', stralign='default', missingval='', showindex='default', disable_numparse=False, colglobalalign=None, colalign=None, preserve_whitespace=False, maxcolwidths=None, headersglobalalign=None, headersalign=None, rowalign=None, maxheadercolwidths=None, break_long_words=True, break_on_hyphens=True)
```

**Parameters:**

- `tabular_data`
- `headers` = `()`
- `tablefmt` = `'simple'`
- `floatfmt` = `'g'`
- `intfmt` = `''`
- `numalign` = `'default'`
- `stralign` = `'default'`
- `missingval` = `''`
- `showindex` = `'default'`
- `disable_numparse` = `False`
- `colglobalalign` = `None`
- `colalign` = `None`
- `preserve_whitespace` = `False`
- `maxcolwidths` = `None`
- `headersglobalalign` = `None`
- `headersalign` = `None`
- `rowalign` = `None`
- `maxheadercolwidths` = `None`
- `break_long_words` = `True`
- `break_on_hyphens` = `True`

### 2. `simple_separated_format`

Construct a simple TableFormat with columns separated by a separator.

>>> tsv = simple_separated_format("\t") ;         tabulate([["foo", 1], ["spam", 23]], tablefmt=tsv) == 'foo \t 1\nspam\t23'
True

```python
tabulate.simple_separated_format(separator)
```

**Parameters:**

- `separator`

### 3. `TableFormat`

TableFormat(lineabove, linebelowheader, linebetweenrows, linebelow, headerrow, datarow, padding, with_header_hide)

```python
tabulate.TableFormat(self, /, *args, **kwargs)
```

**Parameters:**

- `args`
- `kwargs`

### 4. `JupyterHTMLStr`

Wrap the string with a _repr_html_ method so that Jupyter
displays the HTML table

```python
tabulate.JupyterHTMLStr(self, /, *args, **kwargs)
```

**Parameters:**

- `args`
- `kwargs`

### 5. `Line`

Line(begin, hline, sep, end)

```python
tabulate.Line(self, /, *args, **kwargs)
```

**Parameters:**

- `args`
- `kwargs`

### 6. `DataRow`

DataRow(begin, sep, end)

```python
tabulate.DataRow(self, /, *args, **kwargs)
```

**Parameters:**

- `args`
- `kwargs`

## API Classes Summary

| Class | Synopsis |
|-------|----------|
| `DataRow` | DataRow(begin, sep, end) |
| `JupyterHTMLStr` | Wrap the string with a _repr_html_ method so that Jupyter displays the HTML table |
| `Line` | Line(begin, hline, sep, end) |
| `TableFormat` | TableFormat(lineabove, linebelowheader, linebetweenrows, linebelow, headerrow, datarow, padding, wi… |

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`tabulate==0.10.0`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `tabulate`

Each name below is a real top-level export of `tabulate`, verified via `dir(__import__('tabulate'))` against `tabulate` installed from PyPI.

```python
import tabulate

# Public classes
class DataRow: pass
class JupyterHTMLStr: pass
class Line: pass
class TableFormat: pass

# Public functions
def simple_separated_format(): pass
def tabulate(): pass
```

```python
# Verified call shapes — every name resolves in tabulate.dir()
tabulate.simple_separated_format()
tabulate.tabulate()
```

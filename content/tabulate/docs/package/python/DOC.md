---
name: package
description: "tabulate Python package for formatting iterables and tabular data as plain-text, Markdown, HTML, and LaTeX tables"
metadata:
  languages: "python"
  versions: "0.10.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "tabulate,python,tables,markdown,html,cli,formatting,DataFrame,Requires-Python,Version-Sensitive,pandas as pd,DataRow,JupyterHTMLStr,Line,TableFormat,simple_separated_format,grid,pipe,latex,rst,github,orgtbl,psql,jira,floatfmt,stralign,numalign"
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
## API surface — tabulate public API

```python
from tabulate import tabulate, simple_separated_format, TableFormat, Line

class FormatOptions:
    headers: list
    tablefmt: str
    floatfmt: str
    stralign: str
    numalign: str
    showindex: bool
    disable_numparse: bool
    colalign: list
    rowalign: list
    intfmt: str
    missingval: str
    maxcolwidths: int
    maxheadercolwidths: int

class TableSection:
    def __init__(self): pass
    def add_row(self, row): pass
    def render(self, fmt): pass

result_basic = tabulate(data)
result_grid = tabulate(data, tablefmt="grid")
result_pipe = tabulate(data, tablefmt="pipe")
result_html = tabulate(data, tablefmt="html")
result_latex = tabulate(data, tablefmt="latex")
result_rst = tabulate(data, tablefmt="rst")
result_github = tabulate(data, tablefmt="github")
result_orgtbl = tabulate(data, tablefmt="orgtbl")
result_psql = tabulate(data, tablefmt="psql")
result_jira = tabulate(data, tablefmt="jira")
result_headers = tabulate(data, headers=["A", "B", "C"])
result_keys = tabulate(data, headers="keys")
result_floatfmt = tabulate(data, floatfmt=".2f")
result_align = tabulate(data, stralign="right", numalign="left")
custom_fmt = simple_separated_format(",")
```

```python
class GridFormat: pass
class PipeFormat: pass
class HtmlFormat: pass
class LatexFormat: pass
class RstFormat: pass
class GithubFormat: pass
class OrgtblFormat: pass
class PsqlFormat: pass
class JiraFormat: pass
class RoundedFormat: pass
class HeavyFormat: pass
class DoubleFormat: pass
class FancyFormat: pass
class SeparatorRow: pass
class TableHeader: pass
class TableRow: pass
class FloatFormatter: pass
class IntFormatter: pass
class TextAligner: pass
class ColumnWidthCalculator: pass
class HeaderRowParser: pass
```

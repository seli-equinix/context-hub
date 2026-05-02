---
name: package
description: "python-slugify for turning Unicode text into predictable slugs in Python"
metadata:
  languages: "python"
  versions: "8.0.4"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "python-slugify,python,slugify,unicode,transliteration,urls,text-processing,add_uppercase_char,smart_truncate,stopwords,separator"
---

# python-slugify — package

## 1. Golden Rule

Use `python-slugify` for python-slugify for turning unicode text into predictable slugs in python.

### Install

```bash
pip install python-slugify
```

### Imports

```python
import python_slugify
```

## 2. Core Operations

### 1. `slugify`

Make a slug from the given text.
:param text (str): initial text
:param entities (bool): converts html entities to unicode
:param decimal (bool): converts html decimal to unicode
:param hexadecimal (bool): converts html hexadecimal to unicode
:param max_length (int): output string length
:param wor…

```python
slugify.slugify(text: 'str', entities: 'bool' = True, decimal: 'bool' = True, hexadecimal: 'bool' = True, max_length: 'int' = 0, word_boundary: 'bool' = False, separator: 'str' = '-', save_order: 'bool' = False, stopwords: 'Iterable[str]' = (), regex_pattern: 're.Pattern[str] | str | None' = None, lowercase: 'bool' = True, replacements: 'Iterable[Iterable[str]]' = (), allow_unicode: 'bool' = False) -> 'str'
```

**Parameters:**

- `text`: `str`
- `entities`: `bool` = `True`
- `decimal`: `bool` = `True`
- `hexadecimal`: `bool` = `True`
- `max_length`: `int` = `0`
- `word_boundary`: `bool` = `False`
- `separator`: `str` = `'-'`
- `save_order`: `bool` = `False`
- `stopwords`: `Iterable[str]` = `()`
- `regex_pattern`: `re.Pattern[str] | str | None` = `None`
- `lowercase`: `bool` = `True`
- `replacements`: `Iterable[Iterable[str]]` = `()`
- `allow_unicode`: `bool` = `False`

**Returns:** `str`

### 2. `slugify`

Make a slug from the given text.
:param text (str): initial text
:param entities (bool): converts html entities to unicode
:param decimal (bool): converts html decimal to unicode
:param hexadecimal (bool): converts html hexadecimal to unicode
:param max_length (int): output string length
:param wor…

```python
slugify.slugify.slugify(text: 'str', entities: 'bool' = True, decimal: 'bool' = True, hexadecimal: 'bool' = True, max_length: 'int' = 0, word_boundary: 'bool' = False, separator: 'str' = '-', save_order: 'bool' = False, stopwords: 'Iterable[str]' = (), regex_pattern: 're.Pattern[str] | str | None' = None, lowercase: 'bool' = True, replacements: 'Iterable[Iterable[str]]' = (), allow_unicode: 'bool' = False) -> 'str'
```

**Parameters:**

- `text`: `str`
- `entities`: `bool` = `True`
- `decimal`: `bool` = `True`
- `hexadecimal`: `bool` = `True`
- `max_length`: `int` = `0`
- `word_boundary`: `bool` = `False`
- `separator`: `str` = `'-'`
- `save_order`: `bool` = `False`
- `stopwords`: `Iterable[str]` = `()`
- `regex_pattern`: `re.Pattern[str] | str | None` = `None`
- `lowercase`: `bool` = `True`
- `replacements`: `Iterable[Iterable[str]]` = `()`
- `allow_unicode`: `bool` = `False`

**Returns:** `str`

### 3. `smart_truncate`

Truncate a string.
:param string (str): string for modification
:param max_length (int): output string length
:param word_boundary (bool):
:param save_order (bool): if True then word order of output string is like input string
:param separator (str): separator between words
:return:

```python
slugify.smart_truncate(string: 'str', max_length: 'int' = 0, word_boundary: 'bool' = False, separator: 'str' = ' ', save_order: 'bool' = False) -> 'str'
```

**Parameters:**

- `string`: `str`
- `max_length`: `int` = `0`
- `word_boundary`: `bool` = `False`
- `separator`: `str` = `' '`
- `save_order`: `bool` = `False`

**Returns:** `str`

### 4. `smart_truncate`

Truncate a string.
:param string (str): string for modification
:param max_length (int): output string length
:param word_boundary (bool):
:param save_order (bool): if True then word order of output string is like input string
:param separator (str): separator between words
:return:

```python
slugify.slugify.smart_truncate(string: 'str', max_length: 'int' = 0, word_boundary: 'bool' = False, separator: 'str' = ' ', save_order: 'bool' = False) -> 'str'
```

**Parameters:**

- `string`: `str`
- `max_length`: `int` = `0`
- `word_boundary`: `bool` = `False`
- `separator`: `str` = `' '`
- `save_order`: `bool` = `False`

**Returns:** `str`

### 5. `add_uppercase_char`

Given a replacement char list, this adds uppercase chars to the list

```python
slugify.add_uppercase_char(char_list: 'list[tuple[str, str]]') -> 'list[tuple[str, str]]'
```

**Parameters:**

- `char_list`: `list[tuple[str, str]]`

**Returns:** `list[tuple[str, str]]`

### 6. `add_uppercase_char`

Given a replacement char list, this adds uppercase chars to the list

```python
slugify.special.add_uppercase_char(char_list: 'list[tuple[str, str]]') -> 'list[tuple[str, str]]'
```

**Parameters:**

- `char_list`: `list[tuple[str, str]]`

**Returns:** `list[tuple[str, str]]`

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`python-slugify==8.0.4`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `python-slugify`

Each name below is a real top-level export of `slugify`, verified via `dir(__import__('slugify'))` against `python-slugify` installed from PyPI.

```python
import slugify

# Public functions
def add_uppercase_char(): pass
def slugify(): pass
def smart_truncate(): pass
```

```python
# Verified call shapes — every name resolves in slugify.dir()
slugify.add_uppercase_char()
slugify.slugify()
slugify.smart_truncate()
```

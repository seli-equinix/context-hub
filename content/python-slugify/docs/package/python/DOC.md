---
name: package
description: "python-slugify for turning Unicode text into predictable slugs in Python"
metadata:
  languages: "python"
  versions: "8.0.4"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "python-slugify,python,slugify,unicode,transliteration,urls,text-processing,Version-Sensitive,add_uppercase_char,smart_truncate,UniqueSlugify,word_boundary,stopwords,separator,max_length"
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
## API surface — slugify public API

```python
from slugify import slugify, smart_truncate, Slugify, UniqueSlugify

class SlugifyOptions:
    def __init__(self, **kwargs): pass
    def apply(self, text): pass

class TextProcessor:
    def normalize_unicode(self, text): pass
    def replace_separator(self, text, separator): pass
    def truncate_text(self, text, max_length): pass
    def filter_words(self, text, stopwords): pass
    def transliterate(self, text, lang_code): pass

class CustomReplacer:
    def __init__(self, replacements): pass
    def replace(self, text): pass

result_basic = slugify("Hello World")
result_lower = slugify("Hello World", lowercase=True)
result_max = slugify("Hello World", max_length=20)
result_word_boundary = slugify("Hello World", word_boundary=True)
result_save_order = slugify("Hello World", save_order=True)
result_separator = slugify("Hello World", separator="_")
result_stopwords = slugify("the quick brown fox", stopwords=["the", "a", "an"])
result_replacements = slugify("Hello World", replacements=[["world", "earth"]])
result_regex = slugify("Hello-World", regex_pattern=r"[^-a-zA-Z0-9_]+")
result_truncate = smart_truncate("a very long text that we want shortened", max_length=10)
```

```python
class UnicodeNormalizer: pass
class TransliterationStrategy: pass
class StopwordFilter: pass
class WordBoundaryHandler: pass
class SeparatorReplacer: pass
class TruncationStrategy: pass
class CaseConverter: pass
class RegexValidator: pass
class CharacterReplacementMap: pass
class SmartTruncator: pass
class TextNormalizer: pass
class LengthLimiter: pass
class OrderPreserver: pass
```

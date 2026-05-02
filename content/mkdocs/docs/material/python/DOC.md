---
name: material
description: "Material for MkDocs package guide for building and customizing MkDocs documentation sites"
metadata:
  languages: "python"
  versions: "9.7.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "mkdocs,python,mkdocs-material,documentation,static-site,theme,to_svg,twemoji,FileFilter,FilterConfig,clear,copy,fromkeys,get,items,keys,load_dict,load_file,pop,popitem,set_defaults,setdefault,update,validate,values,PreviewExtension,extendMarkdown,getConfig,getConfigInfo,getConfigs,setConfig,setConfigs,PreviewProcessor,run,get_filter,makeExtension,View,read_source,render,validate_anchor_links,view_name,view_post_count,Mapping,Tag,item_title,item_url,tag_name,tag_name_casefold,is_mkdocs,Filter"
---

# mkdocs — material

## Install

```bash
pip install mkdocs
```

## Imports

```python
import mkdocs
```

## Symbols (61)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `to_svg` | Function |  |
| `twemoji` | Function |  |
| `FileFilter` | Class | A file filter. |
| `FilterConfig` | Class | A filter configuration. |
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
| `PreviewExtension` | Class | A Markdown extension to enable instant previews on links.  This extensions allo… |
| `extendMarkdown` | Method | Register Markdown extension.  Arguments:     md: The Markdown instance. |
| `getConfig` | Method | Return a single configuration option value.  Arguments:     key: The configurat… |
| `getConfigInfo` | Method | Return descriptions of all configuration options.  Returns:     All description… |
| `getConfigs` | Method | Return all configuration options.  Returns:     All configuration options. |
| `setConfig` | Method | Set a configuration option.  If the corresponding default value set in [`config… |
| `setConfigs` | Method | Loop through a collection of configuration options, passing each to [`setConfig… |
| `PreviewProcessor` | Class | A Markdown treeprocessor to enable instant previews on links.  Note that this t… |
| `run` | Method | Run the treeprocessor.  Arguments:     root: The root element of the parsed Mar… |
| `get_filter` | Function | Get file filter from settings.  Arguments:     settings: The settings.     key:… |
| `makeExtension` | Function | Register Markdown extension.  Arguments:     **kwargs: Configuration options.… |
| `View` | Class | An item in MkDocs structure - see concrete subclasses Section, Page or Link. |
| `read_source` | Method |  |
| `render` | Method | Convert the Markdown source file to HTML as per the config. |
| `validate_anchor_links` | Method |  |
| `view_name` | Function |  |
| `view_post_count` | Function |  |
| `Mapping` | Class | A mapping between a page or link and a set of tags.  We use this class to store… |
| `Tag` | Class | A tag.  Tags can be used to categorize pages and group them into a tag structur… |
| `item_title` | Function |  |
| `item_url` | Function |  |
| `tag_name` | Function |  |
| `tag_name_casefold` | Function |  |
| `is_mkdocs` | Function |  |
| `FileFilter` | Class | A file filter. |
| `Filter` | Class | A filter. |
| `FilterConfig` | Class | A filter configuration. |
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

## Classes

### `FileFilter`

A file filter.

```python
material.extensions.preview.FileFilter(self, config: 'FilterConfig')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `FilterConfig` | `—` | pos/kw |

### `FilterConfig`

A filter configuration.

```python
material.extensions.preview.FilterConfig(self, config_file_path: 'str | bytes | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file_path` | `str \| bytes \| None` | `None` | pos/kw |

### `PreviewExtension`

A Markdown extension to enable instant previews on links.

This extensions allows to automatically add the `data-preview` attribute to
internal links matching specific criteria, so Material for MkDoc…

```python
material.extensions.preview.PreviewExtension(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PreviewProcessor`

A Markdown treeprocessor to enable instant previews on links.

Note that this treeprocessor is dependent on the `relpath` treeprocessor
registered programmatically by MkDocs before rendering a page.

```python
material.extensions.preview.PreviewProcessor(self, md: 'Markdown', config: 'dict')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `md` | `Markdown` | `—` | pos/kw |
| `config` | `dict` | `—` | pos/kw |

### `View`

An item in MkDocs structure - see concrete subclasses Section, Page or Link.

```python
material.plugins.blog.View(self, name: 'str | None', file: 'File', config: 'MkDocsConfig')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str \| None` | `—` | pos/kw |
| `file` | `File` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

### `Mapping`

A mapping between a page or link and a set of tags.

We use this class to store the mapping between a page or link and a set of
tags. This is necessary as we don't want to store the tags directly on…

```python
material.plugins.tags.Mapping(self, item: 'Page | Link', *, tags: 'Iterable[Tag] | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `item` | `Page \| Link` | `—` | pos/kw |
| `tags` | `Iterable[Tag] \| None` | `None` | kw |

### `Tag`

A tag.

Tags can be used to categorize pages and group them into a tag structure. A
tag is a simple string, which can be split into a hierarchy of tags by using
the character or string as defined in…

```python
material.plugins.tags.Tag(self, name: 'str', *, parent: 'Tag | None' = None, hidden=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `parent` | `Tag \| None` | `None` | kw |
| `hidden` | `—` | `False` | kw |

### `FileFilter`

A file filter.

```python
material.utilities.filter.FileFilter(self, config: 'FilterConfig')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `FilterConfig` | `—` | pos/kw |

### `Filter`

A filter.

```python
material.utilities.filter.Filter(self, config: 'FilterConfig')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `FilterConfig` | `—` | pos/kw |

### `FilterConfig`

A filter configuration.

```python
material.utilities.filter.FilterConfig(self, config_file_path: 'str | bytes | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file_path` | `str \| bytes \| None` | `None` | pos/kw |

## Functions

### `to_svg`

```python
material.extensions.emoji.to_svg(index: 'str', shortname: 'str', alias: 'str', uc: 'str | None', alt: 'str', title: 'str', category: 'str', options: 'object', md: 'Markdown')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `index` | `str` | `—` | pos/kw |
| `shortname` | `str` | `—` | pos/kw |
| `alias` | `str` | `—` | pos/kw |
| `uc` | `str \| None` | `—` | pos/kw |
| `alt` | `str` | `—` | pos/kw |
| `title` | `str` | `—` | pos/kw |
| `category` | `str` | `—` | pos/kw |
| `options` | `object` | `—` | pos/kw |
| `md` | `Markdown` | `—` | pos/kw |

### `twemoji`

```python
material.extensions.emoji.twemoji(options: 'object', md: 'Markdown')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `object` | `—` | pos/kw |
| `md` | `Markdown` | `—` | pos/kw |

### `get_filter`

Get file filter from settings.

Arguments:
    settings: The settings.
    key: The key in the settings.

Returns:
    The file filter.

```python
material.extensions.preview.get_filter(settings: 'dict', key: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `dict` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

### `makeExtension`

Register Markdown extension.

Arguments:
    **kwargs: Configuration options.

Returns:
    The Markdown extension.

```python
material.extensions.preview.makeExtension(**kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `—` | `—` | **kwargs |

### `view_name`

```python
material.plugins.blog.view_name(view: material.plugins.blog.structure.View)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `view` | `View` | `—` | pos/kw |

### `view_post_count`

```python
material.plugins.blog.view_post_count(view: material.plugins.blog.structure.View)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `view` | `View` | `—` | pos/kw |

### `item_title`

```python
material.plugins.tags.item_title(mapping: material.plugins.tags.structure.mapping.Mapping)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `Mapping` | `—` | pos/kw |

### `item_url`

```python
material.plugins.tags.item_url(mapping: material.plugins.tags.structure.mapping.Mapping)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `Mapping` | `—` | pos/kw |

### `tag_name`

```python
material.plugins.tags.tag_name(tag: material.plugins.tags.structure.tag.Tag, *args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag` | `Tag` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `tag_name_casefold`

```python
material.plugins.tags.tag_name_casefold(tag: material.plugins.tags.structure.tag.Tag, *args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag` | `Tag` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `is_mkdocs`

```python
material.templates.is_mkdocs()
```

## Methods

### `material.extensions.preview.FilterConfig` methods

### `clear`

D.clear() -> None.  Remove all items from D.

```python
material.extensions.preview.FilterConfig.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

```python
material.extensions.preview.FilterConfig.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fromkeys`

```python
material.extensions.preview.FilterConfig.fromkeys(iterable, value=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `—` | `—` | pos/kw |
| `value` | `—` | `None` | pos/kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
material.extensions.preview.FilterConfig.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
material.extensions.preview.FilterConfig.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
material.extensions.preview.FilterConfig.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load_dict`

Load config options from a dictionary.

```python
material.extensions.preview.FilterConfig.load_dict(self, patch: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `patch` | `dict` | `—` | pos/kw |

### `load_file`

Load config options from the open file descriptor of a YAML file.

```python
material.extensions.preview.FilterConfig.load_file(self, config_file: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_file` | `IO` | `—` | pos/kw |

### `pop`

D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
If key is not found, d is returned if given, otherwise KeyError is raised.

```python
material.extensions.preview.FilterConfig.pop(self, key, default=<object object at 0x73152c7801a0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `<object object at 0x73152c7801a0>` | pos/kw |

### `popitem`

D.popitem() -> (k, v), remove and return some (key, value) pair
as a 2-tuple; but raise KeyError if D is empty.

```python
material.extensions.preview.FilterConfig.popitem(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_defaults`

Set the base config by going through each validator and getting the
default if it has one.

```python
material.extensions.preview.FilterConfig.set_defaults(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setdefault`

D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

```python
material.extensions.preview.FilterConfig.setdefault(self, key, default=None)
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
material.extensions.preview.FilterConfig.update(self, other=(), /, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `()` | pos |
| `kwds` | `—` | `—` | **kwargs |

### `validate`

```python
material.extensions.preview.FilterConfig.validate(self) -> 'tuple[ConfigErrors, ConfigWarnings]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[ConfigErrors, ConfigWarnings]`

### `values`

D.values() -> an object providing a view on D's values

```python
material.extensions.preview.FilterConfig.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `material.extensions.preview.PreviewExtension` methods

### `extendMarkdown`

Register Markdown extension.

Arguments:
    md: The Markdown instance.

```python
material.extensions.preview.PreviewExtension.extendMarkdown(self, md: 'Markdown')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `md` | `Markdown` | `—` | pos/kw |

### `getConfig`

Return a single configuration option value.

Arguments:
    key: The configuration option name.
    default: Default value to return if key is not set.

Returns:
    Value of stored configuration opt…

```python
material.extensions.preview.PreviewExtension.getConfig(self, key: 'str', default: 'Any' = '') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `default` | `Any` | `''` | pos/kw |

**Returns:** `Any`

### `getConfigInfo`

Return descriptions of all configuration options.

Returns:
    All descriptions of configuration options.

```python
material.extensions.preview.PreviewExtension.getConfigInfo(self) -> 'list[tuple[str, str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[tuple[str, str]]`

### `getConfigs`

Return all configuration options.

Returns:
    All configuration options.

```python
material.extensions.preview.PreviewExtension.getConfigs(self) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `setConfig`

Set a configuration option.

If the corresponding default value set in [`config`][markdown.extensions.Extension.config]
is a `bool` value or `None`, then `value` is passed through
[`parseBoolValue`][…

```python
material.extensions.preview.PreviewExtension.setConfig(self, key: 'str', value: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

### `setConfigs`

Loop through a collection of configuration options, passing each to
[`setConfig`][markdown.extensions.Extension.setConfig].

Arguments:
    items: Collection of configuration options.

Raises:
    Ke…

```python
material.extensions.preview.PreviewExtension.setConfigs(self, items: 'Mapping[str, Any] | Iterable[tuple[str, Any]]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `items` | `Mapping[str, Any] \| Iterable[tuple[str, Any]]` | `—` | pos/kw |

### `material.extensions.preview.PreviewProcessor` methods

### `run`

Run the treeprocessor.

Arguments:
    root: The root element of the parsed Markdown document.

```python
material.extensions.preview.PreviewProcessor.run(self, root: 'Element')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `root` | `Element` | `—` | pos/kw |

### `material.plugins.blog.View` methods

### `read_source`

```python
material.plugins.blog.View.read_source(self, config: 'MkDocsConfig')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |

### `render`

Convert the Markdown source file to HTML as per the config.

```python
material.plugins.blog.View.render(self, config: 'MkDocsConfig', files: 'Files') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `MkDocsConfig` | `—` | pos/kw |
| `files` | `Files` | `—` | pos/kw |

### `validate_anchor_links`

```python
material.plugins.blog.View.validate_anchor_links(self, *, files: 'Files', log_level: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `files` | `Files` | `—` | kw |
| `log_level` | `int` | `—` | kw |

### `material.utilities.filter.FilterConfig` methods

### `clear`

D.clear() -> None.  Remove all items from D.

```python
material.utilities.filter.FilterConfig.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

```python
material.utilities.filter.FilterConfig.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fromkeys`

```python
material.utilities.filter.FilterConfig.fromkeys(iterable, value=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `iterable` | `—` | `—` | pos/kw |
| `value` | `—` | `None` | pos/kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
material.utilities.filter.FilterConfig.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
material.utilities.filter.FilterConfig.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
material.utilities.filter.FilterConfig.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load_dict`

Load config options from a dictionary.

```python
material.utilities.filter.FilterConfig.load_dict(self, patch: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `patch` | `dict` | `—` | pos/kw |

### `load_file`

Load config options from the open file descriptor of a YAML file.

```python
material.utilities.filter.FilterConfig.load_file(self, config_file: 'IO') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config_file` | `IO` | `—` | pos/kw |

### `pop`

D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
If key is not found, d is returned if given, otherwise KeyError is raised.

```python
material.utilities.filter.FilterConfig.pop(self, key, default=<object object at 0x73152c7801a0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `<object object at 0x73152c7801a0>` | pos/kw |

### `popitem`

D.popitem() -> (k, v), remove and return some (key, value) pair
as a 2-tuple; but raise KeyError if D is empty.

```python
material.utilities.filter.FilterConfig.popitem(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_defaults`

Set the base config by going through each validator and getting the
default if it has one.

```python
material.utilities.filter.FilterConfig.set_defaults(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setdefault`

D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

```python
material.utilities.filter.FilterConfig.setdefault(self, key, default=None)
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
material.utilities.filter.FilterConfig.update(self, other=(), /, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `()` | pos |
| `kwds` | `—` | `—` | **kwargs |

### `validate`

```python
material.utilities.filter.FilterConfig.validate(self) -> 'tuple[ConfigErrors, ConfigWarnings]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[ConfigErrors, ConfigWarnings]`

### `values`

D.values() -> an object providing a view on D's values

```python
material.utilities.filter.FilterConfig.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |


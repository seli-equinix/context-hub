---
name: package
description: "nbdev for building, testing, documenting, and packaging Python libraries from Jupyter notebooks"
metadata:
  languages: "python"
  versions: "3.0.12"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "nbdev,python,jupyter,notebooks,quarto,packaging,documentation,say_hello,ini,show_doc,Version-Sensitive,example.com,nbdev_export,ConfigToml,copy,get,path,absolute_import,add_init,bump_version,clean_jupyter,clean_nb,create_output,first_code_ln,get_config,import_obj,is_nbdev,nbdev_clean,nbdev_create_config,nbdev_install_hooks,nbdev_trust,nbdev_update,process_write,read_version,set_version,show_src,update_proj,update_version,write_cells,FilterDefaults,base_procs,nb_proc,procs,xtra_procs,FrontmatterProc,begin,cell,end,NBProcessor,process,NbdevLookup,code,doc,link_line,linkify,Processor,add_fold,add_links,add_show_docs,ai_magics,boxify,cell_lang,chelp,clean_magics,clean_show_doc,create_index,exec_show_docs,extract_directives,extract_tgz,fdiv,filter_stream_,fs_watchdog,hide_,hide_line,insert_warning,mv_exports,nb_export,nb_export_cli,nb_lang,nbdev_contributing,nbdev_filter,nbdev_new,nbdev_readme,nbdev_test,nbdev_update_license,nbglob,nbglob_cli,opt_set,patch_name,populate_language,refresh_quarto_yml,rm_export,rm_header_dash,strip_ansi,strip_hidden_metadata,test_nb,watch_export,cell_diffs,changed_cells,nbs_pair,read_nb_from_git,source_diff,ExportModuleProc,ModuleMaker,make,make_all,decor_id,find_var,make_code_cells,read_var,relative_import,update_import,update_var"
---

# nbdev — package

## Install

```bash
pip install nbdev
```

## Imports

```python
import nbdev
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `nbdev_export` | Function | Export notebooks in `path` to Python modules |
| `show_doc` | Function | Show signature and docstring for `sym` |
| `ConfigToml` | Class | `dict` subclass that also provides access to keys as attrs, and has a pretty ma… |
| `copy` | Method | Return a shallow copy of the dict. |
| `get` | Method | Return the value for key if key is in the dictionary, else default. |
| `path` | Method |  |
| `absolute_import` | Function | Unwarps a relative import in `name` according to `fname` |
| `add_init` | Function | Add `__init__.py` in all subdirs of `path` containing python files if it's not… |
| `bump_version` | Function | Bump semver string `v` at index `part` (0=major, 1=minor, 2=patch) |
| `clean_jupyter` | Function | Clean Jupyter `model` pre save to `path` |
| `clean_nb` | Function | Clean `nb` from superfluous metadata |
| `create_output` | Function | Add a cell output containing `txt` of the `mime` text MIME sub-type |
| `first_code_ln` | Function | get first line number where code occurs, where `code_list` is a list of code |
| `get_config` | Function | Return nbdev config. |
| `import_obj` | Function | Import and return `module:obj` string |
| `is_nbdev` | Function |  |
| `nbdev_clean` | Function | Clean all notebooks in `fname` to avoid merge conflicts |
| `nbdev_create_config` | Function | Create a pyproject.toml config file. |
| `nbdev_install_hooks` | Function | Install Jupyter and git hooks to automatically clean, trust, and fix merge conf… |
| `nbdev_trust` | Function | Trust notebooks matching `fname`. |
| `nbdev_update` | Function | Propagate change in modules matching `fname` to notebooks that created them |
| `process_write` | Function |  |
| `read_version` | Function | Read __version__ from `path/__init__.py`, or None if not found |
| `set_version` | Function | Set __version__ in `path/__init__.py` |
| `show_src` | Function |  |
| `update_proj` | Function | Create or update `pyproject.toml` in the project root. |
| `update_version` | Function | Add __version__ to `path/__init__.py` if it doesn't exist |
| `write_cells` | Function | Write `cells` to `file` along with header `hdr` (mainly for nbdev internal use). |
| `ConfigToml` | Class | `dict` subclass that also provides access to keys as attrs, and has a pretty ma… |
| `copy` | Method | Return a shallow copy of the dict. |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `ConfigToml`

`dict` subclass that also provides access to keys as attrs, and has a pretty markdown repr

```python
nbdev.clean.ConfigToml(self, d, proj, cfg_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `proj` | `—` | `—` | pos/kw |
| `cfg_file` | `—` | `—` | pos/kw |

### `ConfigToml`

`dict` subclass that also provides access to keys as attrs, and has a pretty markdown repr

```python
nbdev.cli.ConfigToml(self, d, proj, cfg_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `proj` | `—` | `—` | pos/kw |
| `cfg_file` | `—` | `—` | pos/kw |

### `FilterDefaults`

Override `FilterDefaults` to change which notebook processors are used

```python
nbdev.cli.FilterDefaults(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FrontmatterProc`

A YAML and formatted-markdown frontmatter processor

```python
nbdev.cli.FrontmatterProc(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `NBProcessor`

Process cells and nbdev comments in a notebook

```python
nbdev.cli.NBProcessor(self, path=None, procs=None, nb=None, debug=False, rm_directives=True, process=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `procs` | `—` | `None` | pos/kw |
| `nb` | `—` | `None` | pos/kw |
| `debug` | `—` | `False` | pos/kw |
| `rm_directives` | `—` | `True` | pos/kw |
| `process` | `—` | `False` | pos/kw |

### `NbdevLookup`

Mapping from symbol names to docs and source URLs

```python
nbdev.cli.NbdevLookup(self, strip_libs=None, incl_libs=None, skip_mods=None, ns=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `strip_libs` | `—` | `None` | pos/kw |
| `incl_libs` | `—` | `None` | pos/kw |
| `skip_mods` | `—` | `None` | pos/kw |
| `ns` | `—` | `None` | pos/kw |

### `Processor`

Base class for processors

```python
nbdev.cli.Processor(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `add_show_docs`

Add show_doc cells after exported cells, unless they are already documented

```python
nbdev.cli.add_show_docs(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `exec_show_docs`

Execute cells needed for `show_docs` output, including exported cells and imports

```python
nbdev.cli.exec_show_docs(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `insert_warning`

Insert Autogenerated Warning Into Notebook after the first cell.

```python
nbdev.cli.insert_warning(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `mv_exports`

Move `exports` cells to after the `show_doc`

```python
nbdev.cli.mv_exports(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `populate_language`

Set cell language based on NB metadata and magics

```python
nbdev.cli.populate_language(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `ConfigToml`

`dict` subclass that also provides access to keys as attrs, and has a pretty markdown repr

```python
nbdev.config.ConfigToml(self, d, proj, cfg_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `proj` | `—` | `—` | pos/kw |
| `cfg_file` | `—` | `—` | pos/kw |

### `ConfigToml`

`dict` subclass that also provides access to keys as attrs, and has a pretty markdown repr

```python
nbdev.doclinks.ConfigToml(self, d, proj, cfg_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `proj` | `—` | `—` | pos/kw |
| `cfg_file` | `—` | `—` | pos/kw |

### `ExportModuleProc`

A processor which exports code to a module

```python
nbdev.doclinks.ExportModuleProc(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ModuleMaker`

Helper class to create exported library from notebook source cells

```python
nbdev.doclinks.ModuleMaker(self, dest, name, nb_path, is_new=True, parse=True, solo_nb=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dest` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `nb_path` | `—` | `—` | pos/kw |
| `is_new` | `—` | `True` | pos/kw |
| `parse` | `—` | `True` | pos/kw |
| `solo_nb` | `—` | `False` | pos/kw |

### `NbdevLookup`

Mapping from symbol names to docs and source URLs

```python
nbdev.doclinks.NbdevLookup(self, strip_libs=None, incl_libs=None, skip_mods=None, ns=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `strip_libs` | `—` | `None` | pos/kw |
| `incl_libs` | `—` | `None` | pos/kw |
| `skip_mods` | `—` | `None` | pos/kw |
| `ns` | `—` | `None` | pos/kw |

### `ConfigToml`

`dict` subclass that also provides access to keys as attrs, and has a pretty markdown repr

```python
nbdev.export.ConfigToml(self, d, proj, cfg_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `proj` | `—` | `—` | pos/kw |
| `cfg_file` | `—` | `—` | pos/kw |

### `ExportModuleProc`

A processor which exports code to a module

```python
nbdev.export.ExportModuleProc(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ModuleMaker`

Helper class to create exported library from notebook source cells

```python
nbdev.export.ModuleMaker(self, dest, name, nb_path, is_new=True, parse=True, solo_nb=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dest` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `nb_path` | `—` | `—` | pos/kw |
| `is_new` | `—` | `True` | pos/kw |
| `parse` | `—` | `True` | pos/kw |
| `solo_nb` | `—` | `False` | pos/kw |

### `NBProcessor`

Process cells and nbdev comments in a notebook

```python
nbdev.export.NBProcessor(self, path=None, procs=None, nb=None, debug=False, rm_directives=True, process=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `procs` | `—` | `None` | pos/kw |
| `nb` | `—` | `None` | pos/kw |
| `debug` | `—` | `False` | pos/kw |
| `rm_directives` | `—` | `True` | pos/kw |
| `process` | `—` | `False` | pos/kw |

### `Processor`

Base class for processors

```python
nbdev.export.Processor(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

## Functions

### `nbdev_export`

Export notebooks in `path` to Python modules

```python
nbdev.nbdev_export(path: str = None, procs: str = '', *, symlinks: bool = False, file_glob: str = '*.ipynb', file_re: str = None, folder_re: str = None, skip_file_glob: str = None, skip_file_re: str = '^[_.]', skip_folder_re: str = '^[_.]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `procs` | `str` | `''` | pos/kw |
| `symlinks` | `bool` | `False` | kw |
| `file_glob` | `str` | `'*.ipynb'` | kw |
| `file_re` | `str` | `None` | kw |
| `folder_re` | `str` | `None` | kw |
| `skip_file_glob` | `str` | `None` | kw |
| `skip_file_re` | `str` | `'^[_.]'` | kw |
| `skip_folder_re` | `str` | `'^[_.]'` | kw |

### `show_doc`

Show signature and docstring for `sym`

```python
nbdev.show_doc(sym, renderer=None, name: str | None = None, title_level: int = 3)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sym` | `—` | `—` | pos/kw |
| `renderer` | `—` | `None` | pos/kw |
| `name` | `str \| None` | `None` | pos/kw |
| `title_level` | `int` | `3` | pos/kw |

### `absolute_import`

Unwarps a relative import in `name` according to `fname`

```python
nbdev.clean.absolute_import(name, fname, level)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `fname` | `—` | `—` | pos/kw |
| `level` | `—` | `—` | pos/kw |

### `add_init`

Add `__init__.py` in all subdirs of `path` containing python files if it's not there already.

```python
nbdev.clean.add_init(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `bump_version`

Bump semver string `v` at index `part` (0=major, 1=minor, 2=patch)

```python
nbdev.clean.bump_version(v, part=2, unbump=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `v` | `—` | `—` | pos/kw |
| `part` | `—` | `2` | pos/kw |
| `unbump` | `—` | `False` | pos/kw |

### `clean_jupyter`

Clean Jupyter `model` pre save to `path`

```python
nbdev.clean.clean_jupyter(path, model, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `model` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `clean_nb`

Clean `nb` from superfluous metadata

```python
nbdev.clean.clean_nb(nb, clear_all=False, allowed_metadata_keys: list = None, allowed_cell_metadata_keys: list = None, clean_ids=True, allowed_out_metadata_keys: list = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `clear_all` | `—` | `False` | pos/kw |
| `allowed_metadata_keys` | `list` | `None` | pos/kw |
| `allowed_cell_metadata_keys` | `list` | `None` | pos/kw |
| `clean_ids` | `—` | `True` | pos/kw |
| `allowed_out_metadata_keys` | `list` | `None` | pos/kw |

### `create_output`

Add a cell output containing `txt` of the `mime` text MIME sub-type

```python
nbdev.clean.create_output(txt, mime)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `txt` | `—` | `—` | pos/kw |
| `mime` | `—` | `—` | pos/kw |

### `first_code_ln`

get first line number where code occurs, where `code_list` is a list of code

```python
nbdev.clean.first_code_ln(code_list, re_pattern=None, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code_list` | `—` | `—` | pos/kw |
| `re_pattern` | `—` | `None` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `get_config`

Return nbdev config.

```python
nbdev.clean.get_config(path=None, also_settings=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `also_settings` | `—` | `False` | pos/kw |

### `import_obj`

Import and return `module:obj` string

```python
nbdev.clean.import_obj(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `is_nbdev`

```python
nbdev.clean.is_nbdev(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `nbdev_clean`

Clean all notebooks in `fname` to avoid merge conflicts

```python
nbdev.clean.nbdev_clean(fname: str = None, clear_all: bool = False, disp: bool = False, stdin: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fname` | `str` | `None` | pos/kw |
| `clear_all` | `bool` | `False` | pos/kw |
| `disp` | `bool` | `False` | pos/kw |
| `stdin` | `bool` | `False` | pos/kw |

### `nbdev_create_config`

Create a pyproject.toml config file.

```python
nbdev.clean.nbdev_create_config(repo: str = None, branch: str = 'main', user: str = None, author: str = None, author_email: str = None, description: str = '', path: str = '.', min_python: str = '3.10', license: str = 'Apache-2.0')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `None` | pos/kw |
| `branch` | `str` | `'main'` | pos/kw |
| `user` | `str` | `None` | pos/kw |
| `author` | `str` | `None` | pos/kw |
| `author_email` | `str` | `None` | pos/kw |
| `description` | `str` | `''` | pos/kw |
| `path` | `str` | `'.'` | pos/kw |
| `min_python` | `str` | `'3.10'` | pos/kw |
| `license` | `str` | `'Apache-2.0'` | pos/kw |

### `nbdev_install_hooks`

Install Jupyter and git hooks to automatically clean, trust, and fix merge conflicts in notebooks

```python
nbdev.clean.nbdev_install_hooks()
```

### `nbdev_trust`

Trust notebooks matching `fname`.

```python
nbdev.clean.nbdev_trust(fname: str = None, force_all: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fname` | `str` | `None` | pos/kw |
| `force_all` | `bool` | `False` | pos/kw |

### `nbdev_update`

Propagate change in modules matching `fname` to notebooks that created them

```python
nbdev.clean.nbdev_update(fname: str = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fname` | `str` | `None` | pos/kw |

### `process_write`

```python
nbdev.clean.process_write(warn_msg, proc_nb, f_in, f_out=None, disp=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `warn_msg` | `—` | `—` | pos/kw |
| `proc_nb` | `—` | `—` | pos/kw |
| `f_in` | `—` | `—` | pos/kw |
| `f_out` | `—` | `None` | pos/kw |
| `disp` | `—` | `False` | pos/kw |

### `read_version`

Read __version__ from `path/__init__.py`, or None if not found

```python
nbdev.clean.read_version(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `set_version`

Set __version__ in `path/__init__.py`

```python
nbdev.clean.set_version(path, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `show_src`

```python
nbdev.clean.show_src(src, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `update_proj`

Create or update `pyproject.toml` in the project root.

```python
nbdev.clean.update_proj(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `update_version`

Add __version__ to `path/__init__.py` if it doesn't exist

```python
nbdev.clean.update_version(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `write_cells`

Write `cells` to `file` along with header `hdr` (mainly for nbdev internal use).

```python
nbdev.clean.write_cells(cells, hdr, file, solo_nb=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cells` | `—` | `—` | pos/kw |
| `hdr` | `—` | `—` | pos/kw |
| `file` | `—` | `—` | pos/kw |
| `solo_nb` | `—` | `False` | pos/kw |

### `add_fold`

Add `code-fold` to `exports` cells

```python
nbdev.cli.add_fold(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `add_init`

Add `__init__.py` in all subdirs of `path` containing python files if it's not there already.

```python
nbdev.cli.add_init(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `add_links`

Add links to markdown cells

```python
nbdev.cli.add_links(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `ai_magics`

A preprocessor to convert AI magics to markdown

```python
nbdev.cli.ai_magics(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `boxify`

Add a box around `cells`

```python
nbdev.cli.boxify(cells)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cells` | `—` | `—` | pos/kw |

### `bump_version`

Bump semver string `v` at index `part` (0=major, 1=minor, 2=patch)

```python
nbdev.cli.bump_version(v, part=2, unbump=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `v` | `—` | `—` | pos/kw |
| `part` | `—` | `2` | pos/kw |
| `unbump` | `—` | `False` | pos/kw |

### `cell_lang`

```python
nbdev.cli.cell_lang(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `chelp`

Show help for all console scripts

```python
nbdev.cli.chelp()
```

### `clean_jupyter`

Clean Jupyter `model` pre save to `path`

```python
nbdev.cli.clean_jupyter(path, model, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `model` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `clean_magics`

A preprocessor to remove cell magic commands

```python
nbdev.cli.clean_magics(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `clean_nb`

Clean `nb` from superfluous metadata

```python
nbdev.cli.clean_nb(nb, clear_all=False, allowed_metadata_keys: list = None, allowed_cell_metadata_keys: list = None, clean_ids=True, allowed_out_metadata_keys: list = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `clear_all` | `—` | `False` | pos/kw |
| `allowed_metadata_keys` | `list` | `None` | pos/kw |
| `allowed_cell_metadata_keys` | `list` | `None` | pos/kw |
| `clean_ids` | `—` | `True` | pos/kw |
| `allowed_out_metadata_keys` | `list` | `None` | pos/kw |

### `clean_show_doc`

Remove ShowDoc input cells

```python
nbdev.cli.clean_show_doc(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `create_index`

Create a documentation index from a sphinx inventory file at `url`, with optional prefix `pre`

```python
nbdev.cli.create_index(url, pre=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `—` | `—` | pos/kw |
| `pre` | `—` | `None` | pos/kw |

### `create_output`

Add a cell output containing `txt` of the `mime` text MIME sub-type

```python
nbdev.cli.create_output(txt, mime)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `txt` | `—` | `—` | pos/kw |
| `mime` | `—` | `—` | pos/kw |

### `extract_directives`

Take leading comment directives from lines of code in `ss`, remove `#|`, and split

```python
nbdev.cli.extract_directives(cell, remove=True, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |
| `remove` | `—` | `True` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `extract_tgz`

```python
nbdev.cli.extract_tgz(url, dest='.')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `—` | `—` | pos/kw |
| `dest` | `—` | `'.'` | pos/kw |

### `fdiv`

Create a fenced div markdown cell in quarto

```python
nbdev.cli.fdiv(attrs='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `attrs` | `—` | `''` | pos/kw |

### `filter_stream_`

Remove output lines containing any of `words` in `cell` stream output

```python
nbdev.cli.filter_stream_(cell, *words)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |
| `words` | `—` | `—` | *args |

### `first_code_ln`

get first line number where code occurs, where `code_list` is a list of code

```python
nbdev.cli.first_code_ln(code_list, re_pattern=None, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code_list` | `—` | `—` | pos/kw |
| `re_pattern` | `—` | `None` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `fs_watchdog`

File system watchdog dispatching to `func`

```python
nbdev.cli.fs_watchdog(func, path, recursive: bool = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `recursive` | `bool` | `True` | pos/kw |

### `get_config`

Return nbdev config.

```python
nbdev.cli.get_config(path=None, also_settings=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `also_settings` | `—` | `False` | pos/kw |

### `hide_`

Hide cell from output

```python
nbdev.cli.hide_(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `hide_line`

Hide lines of code in code cells with the directive `hide_line` at the end of a line of code

```python
nbdev.cli.hide_line(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `import_obj`

Import and return `module:obj` string

```python
nbdev.cli.import_obj(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `is_nbdev`

```python
nbdev.cli.is_nbdev(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `nb_export`

Create module(s) from notebook

```python
nbdev.cli.nb_export(nbname: str, lib_path: str = None, procs=None, name: str = None, mod_maker=<class 'nbdev.maker.ModuleMaker'>, debug: bool = False, solo_nb: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nbname` | `str` | `—` | pos/kw |
| `lib_path` | `str` | `None` | pos/kw |
| `procs` | `—` | `None` | pos/kw |
| `name` | `str` | `None` | pos/kw |
| `mod_maker` | `—` | `<class 'nbdev.maker.ModuleMaker'>` | pos/kw |
| `debug` | `bool` | `False` | pos/kw |
| `solo_nb` | `bool` | `False` | pos/kw |

### `nb_export_cli`

Export a single nbdev notebook to a python script.

```python
nbdev.cli.nb_export_cli(nbname, debug: <function store_true at 0x77a63380d260> = False, *, lib_path: str = None, name: str = None, solo_nb: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nbname` | `—` | `—` | pos/kw |
| `debug` | `store_true` | `False` | pos/kw |
| `lib_path` | `str` | `None` | kw |
| `name` | `str` | `None` | kw |
| `solo_nb` | `bool` | `False` | kw |

### `nb_lang`

```python
nbdev.cli.nb_lang(nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `nbdev_clean`

Clean all notebooks in `fname` to avoid merge conflicts

```python
nbdev.cli.nbdev_clean(fname: str = None, clear_all: bool = False, disp: bool = False, stdin: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fname` | `str` | `None` | pos/kw |
| `clear_all` | `bool` | `False` | pos/kw |
| `disp` | `bool` | `False` | pos/kw |
| `stdin` | `bool` | `False` | pos/kw |

### `nbdev_contributing`

Create CONTRIBUTING.md from contributing_nb (defaults to 'contributing.ipynb' if present). Skips if the file doesn't exist.

```python
nbdev.cli.nbdev_contributing(path: str = None, chk_time: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `chk_time` | `bool` | `False` | pos/kw |

### `nbdev_create_config`

Create a pyproject.toml config file.

```python
nbdev.cli.nbdev_create_config(repo: str = None, branch: str = 'main', user: str = None, author: str = None, author_email: str = None, description: str = '', path: str = '.', min_python: str = '3.10', license: str = 'Apache-2.0')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `None` | pos/kw |
| `branch` | `str` | `'main'` | pos/kw |
| `user` | `str` | `None` | pos/kw |
| `author` | `str` | `None` | pos/kw |
| `author_email` | `str` | `None` | pos/kw |
| `description` | `str` | `''` | pos/kw |
| `path` | `str` | `'.'` | pos/kw |
| `min_python` | `str` | `'3.10'` | pos/kw |
| `license` | `str` | `'Apache-2.0'` | pos/kw |

### `nbdev_export`

Export notebooks in `path` to Python modules

```python
nbdev.cli.nbdev_export(path: str = None, procs: str = '', *, symlinks: bool = False, file_glob: str = '*.ipynb', file_re: str = None, folder_re: str = None, skip_file_glob: str = None, skip_file_re: str = '^[_.]', skip_folder_re: str = '^[_.]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `procs` | `str` | `''` | pos/kw |
| `symlinks` | `bool` | `False` | kw |
| `file_glob` | `str` | `'*.ipynb'` | kw |
| `file_re` | `str` | `None` | kw |
| `folder_re` | `str` | `None` | kw |
| `skip_file_glob` | `str` | `None` | kw |
| `skip_file_re` | `str` | `'^[_.]'` | kw |
| `skip_folder_re` | `str` | `'^[_.]'` | kw |

### `nbdev_filter`

A notebook filter for Quarto

```python
nbdev.cli.nbdev_filter(nb_txt: str = None, fname: str = None, printit: <function bool_arg at 0x77a633641080> = True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_txt` | `str` | `None` | pos/kw |
| `fname` | `str` | `None` | pos/kw |
| `printit` | `bool_arg` | `True` | pos/kw |

### `nbdev_install_hooks`

Install Jupyter and git hooks to automatically clean, trust, and fix merge conflicts in notebooks

```python
nbdev.cli.nbdev_install_hooks()
```

### `nbdev_new`

Create an nbdev project.

```python
nbdev.cli.nbdev_new(*, repo: str = None, branch: str = 'main', user: str = None, author: str = None, author_email: str = None, description: str = '', path: str = '.', min_python: str = '3.10', license: str = 'Apache-2.0')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `None` | kw |
| `branch` | `str` | `'main'` | kw |
| `user` | `str` | `None` | kw |
| `author` | `str` | `None` | kw |
| `author_email` | `str` | `None` | kw |
| `description` | `str` | `''` | kw |
| `path` | `str` | `'.'` | kw |
| `min_python` | `str` | `'3.10'` | kw |
| `license` | `str` | `'Apache-2.0'` | kw |

### `nbdev_readme`

Create README.md from readme_nb (index.ipynb by default)

```python
nbdev.cli.nbdev_readme(path: str = None, chk_time: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `chk_time` | `bool` | `False` | pos/kw |

### `nbdev_test`

Test in parallel notebooks matching `path`, passing along `flags`

```python
nbdev.cli.nbdev_test(path: str = None, flags: str = '', n_workers: int = None, timing: bool = False, do_print: bool = False, pause: float = 0.01, ignore_fname: str = '.notest', verbose: bool = False, save: bool = False, *, symlinks: bool = False, file_glob: str = '*.ipynb', file_re: str = None, folder_re: str = None, skip_file_glob: str = None, skip_file_re: str = '^[_.]', skip_folder_re: str = '^[_.]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `flags` | `str` | `''` | pos/kw |
| `n_workers` | `int` | `None` | pos/kw |
| `timing` | `bool` | `False` | pos/kw |
| `do_print` | `bool` | `False` | pos/kw |
| `pause` | `float` | `0.01` | pos/kw |
| `ignore_fname` | `str` | `'.notest'` | pos/kw |
| `verbose` | `bool` | `False` | pos/kw |
| `save` | `bool` | `False` | pos/kw |
| `symlinks` | `bool` | `False` | kw |
| `file_glob` | `str` | `'*.ipynb'` | kw |
| `file_re` | `str` | `None` | kw |
| `folder_re` | `str` | `None` | kw |
| `skip_file_glob` | `str` | `None` | kw |
| `skip_file_re` | `str` | `'^[_.]'` | kw |
| `skip_folder_re` | `str` | `'^[_.]'` | kw |

### `nbdev_trust`

Trust notebooks matching `fname`.

```python
nbdev.cli.nbdev_trust(fname: str = None, force_all: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fname` | `str` | `None` | pos/kw |
| `force_all` | `bool` | `False` | pos/kw |

### `nbdev_update_license`

Allows you to update the license of your project.

```python
nbdev.cli.nbdev_update_license(to: str = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `to` | `str` | `None` | pos/kw |

### `nbglob`

Find all files in a directory matching an extension given a config key.

```python
nbdev.cli.nbglob(path=None, skip_folder_re='^[_.]', file_glob='*.ipynb', skip_file_re='^[_.]', key='nbs_path', as_path=False, *, recursive: bool = True, maxdepth: int = None, symlinks: bool = True, file_re: str = None, folder_re: str = None, skip_file_glob: str = None, func: <built-in function callable> = <function walk_join at 0x77a63445fe20>, ret_folders: bool = False, sort: bool = True, types: str | list = None, exts: str | list = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `skip_folder_re` | `—` | `'^[_.]'` | pos/kw |
| `file_glob` | `—` | `'*.ipynb'` | pos/kw |
| `skip_file_re` | `—` | `'^[_.]'` | pos/kw |
| `key` | `—` | `'nbs_path'` | pos/kw |
| `as_path` | `—` | `False` | pos/kw |
| `recursive` | `bool` | `True` | kw |
| `maxdepth` | `int` | `None` | kw |
| `symlinks` | `bool` | `True` | kw |
| `file_re` | `str` | `None` | kw |
| `folder_re` | `str` | `None` | kw |
| `skip_file_glob` | `str` | `None` | kw |
| `func` | `callable` | `<function walk_join at 0x77a63445fe20>` | kw |
| `ret_folders` | `bool` | `False` | kw |
| `sort` | `bool` | `True` | kw |
| `types` | `str \| list` | `None` | kw |
| `exts` | `str \| list` | `None` | kw |

### `nbglob_cli`

Find all files in a directory matching an extension given a config key.

```python
nbdev.cli.nbglob_cli(path: str = None, symlinks: bool = False, file_glob: str = '*.ipynb', file_re: str = None, folder_re: str = None, skip_file_glob: str = None, skip_file_re: str = '^[_.]', skip_folder_re: str = '^[_.]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `symlinks` | `bool` | `False` | pos/kw |
| `file_glob` | `str` | `'*.ipynb'` | pos/kw |
| `file_re` | `str` | `None` | pos/kw |
| `folder_re` | `str` | `None` | pos/kw |
| `skip_file_glob` | `str` | `None` | pos/kw |
| `skip_file_re` | `str` | `'^[_.]'` | pos/kw |
| `skip_folder_re` | `str` | `'^[_.]'` | pos/kw |

### `opt_set`

newval if newval else var

```python
nbdev.cli.opt_set(var, newval)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var` | `—` | `—` | pos/kw |
| `newval` | `—` | `—` | pos/kw |

### `patch_name`

If `o` is decorated with `patch` or `patch_to`, return its class-prefix name

```python
nbdev.cli.patch_name(o)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `o` | `—` | `—` | pos/kw |

### `process_write`

```python
nbdev.cli.process_write(warn_msg, proc_nb, f_in, f_out=None, disp=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `warn_msg` | `—` | `—` | pos/kw |
| `proc_nb` | `—` | `—` | pos/kw |
| `f_in` | `—` | `—` | pos/kw |
| `f_out` | `—` | `None` | pos/kw |
| `disp` | `—` | `False` | pos/kw |

### `read_version`

Read __version__ from `path/__init__.py`, or None if not found

```python
nbdev.cli.read_version(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `refresh_quarto_yml`

Generate `_quarto.yml` from `pyproject.toml`.

```python
nbdev.cli.refresh_quarto_yml()
```

### `rm_export`

Remove cells that are exported or hidden

```python
nbdev.cli.rm_export(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `rm_header_dash`

Remove headings that end with a dash -

```python
nbdev.cli.rm_header_dash(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `set_version`

Set __version__ in `path/__init__.py`

```python
nbdev.cli.set_version(path, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `show_src`

```python
nbdev.cli.show_src(src, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `strip_ansi`

Strip Ansi Characters.

```python
nbdev.cli.strip_ansi(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `strip_hidden_metadata`

Strips "hidden" metadata property from code cells so it doesn't interfere with docs rendering

```python
nbdev.cli.strip_hidden_metadata(cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell` | `—` | `—` | pos/kw |

### `test_nb`

Execute tests in notebook in `fn` except those with `skip_flags`

```python
nbdev.cli.test_nb(fn, skip_flags=None, force_flags=None, do_print=False, showerr=True, basepath=None, verbose=False, save=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fn` | `—` | `—` | pos/kw |
| `skip_flags` | `—` | `None` | pos/kw |
| `force_flags` | `—` | `None` | pos/kw |
| `do_print` | `—` | `False` | pos/kw |
| `showerr` | `—` | `True` | pos/kw |
| `basepath` | `—` | `None` | pos/kw |
| `verbose` | `—` | `False` | pos/kw |
| `save` | `—` | `False` | pos/kw |

### `update_proj`

Create or update `pyproject.toml` in the project root.

```python
nbdev.cli.update_proj(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `update_version`

Add __version__ to `path/__init__.py` if it doesn't exist

```python
nbdev.cli.update_version(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `watch_export`

Use `nb_export` on ipynb files in `nbs` directory on changes using nbdev config if available

```python
nbdev.cli.watch_export(nbs: str = None, lib: str = None, force: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nbs` | `str` | `None` | pos/kw |
| `lib` | `str` | `None` | pos/kw |
| `force` | `bool` | `False` | pos/kw |

### `write_cells`

Write `cells` to `file` along with header `hdr` (mainly for nbdev internal use).

```python
nbdev.cli.write_cells(cells, hdr, file, solo_nb=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cells` | `—` | `—` | pos/kw |
| `hdr` | `—` | `—` | pos/kw |
| `file` | `—` | `—` | pos/kw |
| `solo_nb` | `—` | `False` | pos/kw |

### `add_init`

Add `__init__.py` in all subdirs of `path` containing python files if it's not there already.

```python
nbdev.config.add_init(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `bump_version`

Bump semver string `v` at index `part` (0=major, 1=minor, 2=patch)

```python
nbdev.config.bump_version(v, part=2, unbump=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `v` | `—` | `—` | pos/kw |
| `part` | `—` | `2` | pos/kw |
| `unbump` | `—` | `False` | pos/kw |

### `create_output`

Add a cell output containing `txt` of the `mime` text MIME sub-type

```python
nbdev.config.create_output(txt, mime)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `txt` | `—` | `—` | pos/kw |
| `mime` | `—` | `—` | pos/kw |

### `get_config`

Return nbdev config.

```python
nbdev.config.get_config(path=None, also_settings=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `also_settings` | `—` | `False` | pos/kw |

### `import_obj`

Import and return `module:obj` string

```python
nbdev.config.import_obj(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `is_nbdev`

```python
nbdev.config.is_nbdev(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `nbdev_create_config`

Create a pyproject.toml config file.

```python
nbdev.config.nbdev_create_config(repo: str = None, branch: str = 'main', user: str = None, author: str = None, author_email: str = None, description: str = '', path: str = '.', min_python: str = '3.10', license: str = 'Apache-2.0')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `None` | pos/kw |
| `branch` | `str` | `'main'` | pos/kw |
| `user` | `str` | `None` | pos/kw |
| `author` | `str` | `None` | pos/kw |
| `author_email` | `str` | `None` | pos/kw |
| `description` | `str` | `''` | pos/kw |
| `path` | `str` | `'.'` | pos/kw |
| `min_python` | `str` | `'3.10'` | pos/kw |
| `license` | `str` | `'Apache-2.0'` | pos/kw |

### `read_version`

Read __version__ from `path/__init__.py`, or None if not found

```python
nbdev.config.read_version(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `set_version`

Set __version__ in `path/__init__.py`

```python
nbdev.config.set_version(path, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `show_src`

```python
nbdev.config.show_src(src, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `update_proj`

Create or update `pyproject.toml` in the project root.

```python
nbdev.config.update_proj(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `update_version`

Add __version__ to `path/__init__.py` if it doesn't exist

```python
nbdev.config.update_version(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `write_cells`

Write `cells` to `file` along with header `hdr` (mainly for nbdev internal use).

```python
nbdev.config.write_cells(cells, hdr, file, solo_nb=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cells` | `—` | `—` | pos/kw |
| `hdr` | `—` | `—` | pos/kw |
| `file` | `—` | `—` | pos/kw |
| `solo_nb` | `—` | `False` | pos/kw |

### `cell_diffs`

{cell_id:diff} for changed/added/deleted cells between two refs

```python
nbdev.diff.cell_diffs(nb_path, *, ref_a='HEAD', ref_b=None, adds=True, changes=True, dels=False, metadata=False, outputs=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_path` | `—` | `—` | pos/kw |
| `ref_a` | `—` | `'HEAD'` | kw |
| `ref_b` | `—` | `None` | kw |
| `adds` | `—` | `True` | kw |
| `changes` | `—` | `True` | kw |
| `dels` | `—` | `False` | kw |
| `metadata` | `—` | `False` | kw |
| `outputs` | `—` | `False` | kw |

### `changed_cells`

Return set of cell IDs for changed/added/deleted cells between two refs

```python
nbdev.diff.changed_cells(nb_path, *, ref_a='HEAD', ref_b=None, adds=True, changes=True, dels=False, metadata=False, outputs=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_path` | `—` | `—` | pos/kw |
| `ref_a` | `—` | `'HEAD'` | kw |
| `ref_b` | `—` | `None` | kw |
| `adds` | `—` | `True` | kw |
| `changes` | `—` | `True` | kw |
| `dels` | `—` | `False` | kw |
| `metadata` | `—` | `False` | kw |
| `outputs` | `—` | `False` | kw |

### `nbs_pair`

NBs at two refs; None means working dir. By default provides HEAD and working dir

```python
nbdev.diff.nbs_pair(nb_path, ref_a='HEAD', ref_b=None, f=<function noop at 0x77a634446ca0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_path` | `—` | `—` | pos/kw |
| `ref_a` | `—` | `'HEAD'` | pos/kw |
| `ref_b` | `—` | `None` | pos/kw |
| `f` | `—` | `<function noop at 0x77a634446ca0>` | pos/kw |

### `read_nb_from_git`

Read notebook from git ref (e.g. HEAD) at path, or working dir if ref is None

```python
nbdev.diff.read_nb_from_git(g: fastgit.core.Git, path, ref=None) -> fastcore.basics.AttrDict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `g` | `Git` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `ref` | `—` | `None` | pos/kw |

**Returns:** `<class 'fastcore.basics.AttrDict'>`

### `source_diff`

Return unified diff string for source change

```python
nbdev.diff.source_diff(old_source, new_source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old_source` | `—` | `—` | pos/kw |
| `new_source` | `—` | `—` | pos/kw |

### `add_init`

Add `__init__.py` in all subdirs of `path` containing python files if it's not there already.

```python
nbdev.doclinks.add_init(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `bump_version`

Bump semver string `v` at index `part` (0=major, 1=minor, 2=patch)

```python
nbdev.doclinks.bump_version(v, part=2, unbump=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `v` | `—` | `—` | pos/kw |
| `part` | `—` | `2` | pos/kw |
| `unbump` | `—` | `False` | pos/kw |

### `create_index`

Create a documentation index from a sphinx inventory file at `url`, with optional prefix `pre`

```python
nbdev.doclinks.create_index(url, pre=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `—` | `—` | pos/kw |
| `pre` | `—` | `None` | pos/kw |

### `create_output`

Add a cell output containing `txt` of the `mime` text MIME sub-type

```python
nbdev.doclinks.create_output(txt, mime)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `txt` | `—` | `—` | pos/kw |
| `mime` | `—` | `—` | pos/kw |

### `decor_id`

`id` attr of decorator, regardless of whether called as function or bare

```python
nbdev.doclinks.decor_id(d)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |

### `find_var`

Find the line numbers where `varname` is defined in `lines`

```python
nbdev.doclinks.find_var(lines, varname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `lines` | `—` | `—` | pos/kw |
| `varname` | `—` | `—` | pos/kw |

### `get_config`

Return nbdev config.

```python
nbdev.doclinks.get_config(path=None, also_settings=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `also_settings` | `—` | `False` | pos/kw |

### `import_obj`

Import and return `module:obj` string

```python
nbdev.doclinks.import_obj(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `is_nbdev`

```python
nbdev.doclinks.is_nbdev(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `make_code_cells`

```python
nbdev.doclinks.make_code_cells(*ss)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ss` | `—` | `—` | *args |

### `nb_export`

Create module(s) from notebook

```python
nbdev.doclinks.nb_export(nbname: str, lib_path: str = None, procs=None, name: str = None, mod_maker=<class 'nbdev.maker.ModuleMaker'>, debug: bool = False, solo_nb: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nbname` | `str` | `—` | pos/kw |
| `lib_path` | `str` | `None` | pos/kw |
| `procs` | `—` | `None` | pos/kw |
| `name` | `str` | `None` | pos/kw |
| `mod_maker` | `—` | `<class 'nbdev.maker.ModuleMaker'>` | pos/kw |
| `debug` | `bool` | `False` | pos/kw |
| `solo_nb` | `bool` | `False` | pos/kw |

### `nbdev_create_config`

Create a pyproject.toml config file.

```python
nbdev.doclinks.nbdev_create_config(repo: str = None, branch: str = 'main', user: str = None, author: str = None, author_email: str = None, description: str = '', path: str = '.', min_python: str = '3.10', license: str = 'Apache-2.0')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `None` | pos/kw |
| `branch` | `str` | `'main'` | pos/kw |
| `user` | `str` | `None` | pos/kw |
| `author` | `str` | `None` | pos/kw |
| `author_email` | `str` | `None` | pos/kw |
| `description` | `str` | `''` | pos/kw |
| `path` | `str` | `'.'` | pos/kw |
| `min_python` | `str` | `'3.10'` | pos/kw |
| `license` | `str` | `'Apache-2.0'` | pos/kw |

### `nbdev_export`

Export notebooks in `path` to Python modules

```python
nbdev.doclinks.nbdev_export(path: str = None, procs: str = '', *, symlinks: bool = False, file_glob: str = '*.ipynb', file_re: str = None, folder_re: str = None, skip_file_glob: str = None, skip_file_re: str = '^[_.]', skip_folder_re: str = '^[_.]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `procs` | `str` | `''` | pos/kw |
| `symlinks` | `bool` | `False` | kw |
| `file_glob` | `str` | `'*.ipynb'` | kw |
| `file_re` | `str` | `None` | kw |
| `folder_re` | `str` | `None` | kw |
| `skip_file_glob` | `str` | `None` | kw |
| `skip_file_re` | `str` | `'^[_.]'` | kw |
| `skip_folder_re` | `str` | `'^[_.]'` | kw |

### `nbglob`

Find all files in a directory matching an extension given a config key.

```python
nbdev.doclinks.nbglob(path=None, skip_folder_re='^[_.]', file_glob='*.ipynb', skip_file_re='^[_.]', key='nbs_path', as_path=False, *, recursive: bool = True, maxdepth: int = None, symlinks: bool = True, file_re: str = None, folder_re: str = None, skip_file_glob: str = None, func: <built-in function callable> = <function walk_join at 0x77a63445fe20>, ret_folders: bool = False, sort: bool = True, types: str | list = None, exts: str | list = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |
| `skip_folder_re` | `—` | `'^[_.]'` | pos/kw |
| `file_glob` | `—` | `'*.ipynb'` | pos/kw |
| `skip_file_re` | `—` | `'^[_.]'` | pos/kw |
| `key` | `—` | `'nbs_path'` | pos/kw |
| `as_path` | `—` | `False` | pos/kw |
| `recursive` | `bool` | `True` | kw |
| `maxdepth` | `int` | `None` | kw |
| `symlinks` | `bool` | `True` | kw |
| `file_re` | `str` | `None` | kw |
| `folder_re` | `str` | `None` | kw |
| `skip_file_glob` | `str` | `None` | kw |
| `func` | `callable` | `<function walk_join at 0x77a63445fe20>` | kw |
| `ret_folders` | `bool` | `False` | kw |
| `sort` | `bool` | `True` | kw |
| `types` | `str \| list` | `None` | kw |
| `exts` | `str \| list` | `None` | kw |

### `nbglob_cli`

Find all files in a directory matching an extension given a config key.

```python
nbdev.doclinks.nbglob_cli(path: str = None, symlinks: bool = False, file_glob: str = '*.ipynb', file_re: str = None, folder_re: str = None, skip_file_glob: str = None, skip_file_re: str = '^[_.]', skip_folder_re: str = '^[_.]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `None` | pos/kw |
| `symlinks` | `bool` | `False` | pos/kw |
| `file_glob` | `str` | `'*.ipynb'` | pos/kw |
| `file_re` | `str` | `None` | pos/kw |
| `folder_re` | `str` | `None` | pos/kw |
| `skip_file_glob` | `str` | `None` | pos/kw |
| `skip_file_re` | `str` | `'^[_.]'` | pos/kw |
| `skip_folder_re` | `str` | `'^[_.]'` | pos/kw |

### `patch_name`

If `o` is decorated with `patch` or `patch_to`, return its class-prefix name

```python
nbdev.doclinks.patch_name(o)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `o` | `—` | `—` | pos/kw |

### `read_var`

Eval and return the value of `varname` defined in `code`

```python
nbdev.doclinks.read_var(code, varname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `—` | `—` | pos/kw |
| `varname` | `—` | `—` | pos/kw |

### `read_version`

Read __version__ from `path/__init__.py`, or None if not found

```python
nbdev.doclinks.read_version(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `relative_import`

Convert a module `name` to a name relative to `fname`

```python
nbdev.doclinks.relative_import(name, fname, level=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `fname` | `—` | `—` | pos/kw |
| `level` | `—` | `0` | pos/kw |

### `set_version`

Set __version__ in `path/__init__.py`

```python
nbdev.doclinks.set_version(path, version)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `version` | `—` | `—` | pos/kw |

### `show_src`

```python
nbdev.doclinks.show_src(src, lang='python')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `—` | `—` | pos/kw |
| `lang` | `—` | `'python'` | pos/kw |

### `update_import`

```python
nbdev.doclinks.update_import(source, tree, libname, f=<function relative_import at 0x77a632203ec0>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `libname` | `—` | `—` | pos/kw |
| `f` | `—` | `<function relative_import at 0x77a632203ec0>` | pos/kw |

### `update_proj`

Create or update `pyproject.toml` in the project root.

```python
nbdev.doclinks.update_proj(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `update_var`

Update the definition of `varname` in file `fn`, by calling `func` with the current definition

```python
nbdev.doclinks.update_var(varname, func, fn=None, code=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `varname` | `—` | `—` | pos/kw |
| `func` | `—` | `—` | pos/kw |
| `fn` | `—` | `None` | pos/kw |
| `code` | `—` | `None` | pos/kw |

### `update_version`

Add __version__ to `path/__init__.py` if it doesn't exist

```python
nbdev.doclinks.update_version(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `write_cells`

Write `cells` to `file` along with header `hdr` (mainly for nbdev internal use).

```python
nbdev.doclinks.write_cells(cells, hdr, file, solo_nb=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cells` | `—` | `—` | pos/kw |
| `hdr` | `—` | `—` | pos/kw |
| `file` | `—` | `—` | pos/kw |
| `solo_nb` | `—` | `False` | pos/kw |

### `add_init`

Add `__init__.py` in all subdirs of `path` containing python files if it's not there already.

```python
nbdev.export.add_init(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `bump_version`

Bump semver string `v` at index `part` (0=major, 1=minor, 2=patch)

```python
nbdev.export.bump_version(v, part=2, unbump=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `v` | `—` | `—` | pos/kw |
| `part` | `—` | `2` | pos/kw |
| `unbump` | `—` | `False` | pos/kw |

## Methods

### `nbdev.clean.ConfigToml` methods

### `copy`

Return a shallow copy of the dict.

```python
nbdev.clean.ConfigToml.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get`

Return the value for key if key is in the dictionary, else default.

```python
nbdev.clean.ConfigToml.get(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `path`

```python
nbdev.clean.ConfigToml.path(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `nbdev.cli.ConfigToml` methods

### `copy`

Return a shallow copy of the dict.

```python
nbdev.cli.ConfigToml.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get`

Return the value for key if key is in the dictionary, else default.

```python
nbdev.cli.ConfigToml.get(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `path`

```python
nbdev.cli.ConfigToml.path(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `nbdev.cli.FilterDefaults` methods

### `base_procs`

```python
nbdev.cli.FilterDefaults.base_procs(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nb_proc`

Get an `NBProcessor` with these processors

```python
nbdev.cli.FilterDefaults.nb_proc(self, nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `nb` | `—` | `—` | pos/kw |

### `procs`

Processors for export

```python
nbdev.cli.FilterDefaults.procs(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `xtra_procs`

```python
nbdev.cli.FilterDefaults.xtra_procs(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.cli.FrontmatterProc` methods

### `begin`

```python
nbdev.cli.FrontmatterProc.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell`

```python
nbdev.cli.FrontmatterProc.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `end`

```python
nbdev.cli.FrontmatterProc.end(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.cli.NBProcessor` methods

### `process`

Process all cells with all processors

```python
nbdev.cli.NBProcessor.process(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.cli.NbdevLookup` methods

### `code`

Link to source code for `sym`

```python
nbdev.cli.NbdevLookup.code(self, sym)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sym` | `—` | `—` | pos/kw |

### `doc`

Link to docs for `sym`

```python
nbdev.cli.NbdevLookup.doc(self, sym)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sym` | `—` | `—` | pos/kw |

### `link_line`

```python
nbdev.cli.NbdevLookup.link_line(self, l)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `l` | `—` | `—` | pos/kw |

### `linkify`

```python
nbdev.cli.NbdevLookup.linkify(self, md)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `md` | `—` | `—` | pos/kw |

### `nbdev.cli.Processor` methods

### `cell`

```python
nbdev.cli.Processor.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `nbdev.cli.add_show_docs` methods

### `begin`

```python
nbdev.cli.add_show_docs.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell`

```python
nbdev.cli.add_show_docs.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `nbdev.cli.exec_show_docs` methods

### `begin`

```python
nbdev.cli.exec_show_docs.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell`

```python
nbdev.cli.exec_show_docs.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `end`

```python
nbdev.cli.exec_show_docs.end(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.cli.insert_warning` methods

### `begin`

```python
nbdev.cli.insert_warning.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell`

```python
nbdev.cli.insert_warning.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `nbdev.cli.mv_exports` methods

### `begin`

```python
nbdev.cli.mv_exports.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell`

```python
nbdev.cli.mv_exports.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `nbdev.cli.populate_language` methods

### `begin`

```python
nbdev.cli.populate_language.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell`

```python
nbdev.cli.populate_language.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |

### `nbdev.config.ConfigToml` methods

### `copy`

Return a shallow copy of the dict.

```python
nbdev.config.ConfigToml.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get`

Return the value for key if key is in the dictionary, else default.

```python
nbdev.config.ConfigToml.get(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `path`

```python
nbdev.config.ConfigToml.path(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `nbdev.doclinks.ConfigToml` methods

### `copy`

Return a shallow copy of the dict.

```python
nbdev.doclinks.ConfigToml.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get`

Return the value for key if key is in the dictionary, else default.

```python
nbdev.doclinks.ConfigToml.get(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `path`

```python
nbdev.doclinks.ConfigToml.path(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `nbdev.doclinks.ExportModuleProc` methods

### `begin`

```python
nbdev.doclinks.ExportModuleProc.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.doclinks.ModuleMaker` methods

### `make`

Write module containing `cells` with `__all__` generated from `all_cells`

```python
nbdev.doclinks.ModuleMaker.make(self: nbdev.maker.ModuleMaker, cells, all_cells=None, lib_path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `ModuleMaker` | `—` | pos/kw |
| `cells` | `—` | `—` | pos/kw |
| `all_cells` | `—` | `None` | pos/kw |
| `lib_path` | `—` | `None` | pos/kw |

### `make_all`

Create `__all__` with all exports in `cells`

```python
nbdev.doclinks.ModuleMaker.make_all(self: nbdev.maker.ModuleMaker, cells)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `ModuleMaker` | `—` | pos/kw |
| `cells` | `—` | `—` | pos/kw |

### `nbdev.doclinks.NbdevLookup` methods

### `code`

Link to source code for `sym`

```python
nbdev.doclinks.NbdevLookup.code(self, sym)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sym` | `—` | `—` | pos/kw |

### `doc`

Link to docs for `sym`

```python
nbdev.doclinks.NbdevLookup.doc(self, sym)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sym` | `—` | `—` | pos/kw |

### `link_line`

```python
nbdev.doclinks.NbdevLookup.link_line(self, l)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `l` | `—` | `—` | pos/kw |

### `linkify`

```python
nbdev.doclinks.NbdevLookup.linkify(self, md)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `md` | `—` | `—` | pos/kw |

### `nbdev.export.ConfigToml` methods

### `copy`

Return a shallow copy of the dict.

```python
nbdev.export.ConfigToml.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get`

Return the value for key if key is in the dictionary, else default.

```python
nbdev.export.ConfigToml.get(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `path`

```python
nbdev.export.ConfigToml.path(self, k, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `k` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `nbdev.export.ExportModuleProc` methods

### `begin`

```python
nbdev.export.ExportModuleProc.begin(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.export.ModuleMaker` methods

### `make`

Write module containing `cells` with `__all__` generated from `all_cells`

```python
nbdev.export.ModuleMaker.make(self: nbdev.maker.ModuleMaker, cells, all_cells=None, lib_path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `ModuleMaker` | `—` | pos/kw |
| `cells` | `—` | `—` | pos/kw |
| `all_cells` | `—` | `None` | pos/kw |
| `lib_path` | `—` | `None` | pos/kw |

### `make_all`

Create `__all__` with all exports in `cells`

```python
nbdev.export.ModuleMaker.make_all(self: nbdev.maker.ModuleMaker, cells)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `ModuleMaker` | `—` | pos/kw |
| `cells` | `—` | `—` | pos/kw |

### `nbdev.export.NBProcessor` methods

### `process`

Process all cells with all processors

```python
nbdev.export.NBProcessor.process(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `nbdev.export.Processor` methods

### `cell`

```python
nbdev.export.Processor.cell(self, cell)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |


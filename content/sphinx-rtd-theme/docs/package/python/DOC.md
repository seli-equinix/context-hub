---
name: package
description: "Read the Docs Sphinx theme package guide for Python documentation projects"
metadata:
  languages: "python"
  versions: "3.1.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "sphinx-rtd-theme,python,sphinx,readthedocs,theme,docs,config_initiated,extend_html_context,get_html_theme_path,setup,sphinx-extension"
---

# sphinx-rtd-theme — package

Sphinx Read the Docs theme.

From https://github.com/ryan-roemer/sphinx-bootstrap-theme.

## 1. Golden Rule

Use `sphinx-rtd-theme` for read the docs sphinx theme package guide for python documentation projects.

### Install

```bash
pip install sphinx-rtd-theme
```

### Imports

```python
import sphinx_rtd_theme
```

## 2. Core Operations

### 1. `get_html_theme_path`

Return list of HTML theme paths.

```python
sphinx_rtd_theme.get_html_theme_path()
```

### 2. `config_initiated`

```python
sphinx_rtd_theme.config_initiated(app, config)
```

**Parameters:**

- `app`
- `config`

### 3. `extend_html_context`

```python
sphinx_rtd_theme.extend_html_context(app, pagename, templatename, context, doctree)
```

**Parameters:**

- `app`
- `pagename`
- `templatename`
- `context`
- `doctree`

### 4. `setup`

```python
sphinx_rtd_theme.setup(app)
```

**Parameters:**

- `app`

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`sphinx-rtd-theme==3.1.0`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.

## API surface — verifiable top-level exports of `sphinx_rtd_theme`

Each name below is a real top-level export of `sphinx_rtd_theme`, verified via `dir(__import__('sphinx_rtd_theme'))` against `sphinx_rtd_theme` installed from PyPI.

```python
import sphinx_rtd_theme

# Public functions
def config_initiated(): pass
def extend_html_context(): pass
def get_html_theme_path(): pass
def setup(): pass
```

```python
# Verified call shapes — every name resolves in sphinx_rtd_theme.dir()
sphinx_rtd_theme.config_initiated()
sphinx_rtd_theme.extend_html_context()
sphinx_rtd_theme.get_html_theme_path()
sphinx_rtd_theme.setup()
```

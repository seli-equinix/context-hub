---
name: package
description: "Read the Docs Sphinx theme package guide for Python documentation projects"
metadata:
  languages: "python"
  versions: "3.1.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "sphinx-rtd-theme,python,sphinx,readthedocs,theme,docs,Version-Sensitive,config_initiated,extend_html_context,get_html_theme_path,setup,sphinx_rtd_theme,ThemeOptions,collapse_navigation,navigation_depth,sticky_navigation,prev_next_buttons_location,style_external_links,canonical_url,analytics_id,sphinx-extension"
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
## API surface — sphinx-rtd-theme integration

```python
from sphinx_rtd_theme import get_html_theme_path

class ThemeOptions:
    canonical_url: str
    analytics_id: str
    analytics_anonymize_ip: bool
    logo_only: bool
    display_version: bool
    prev_next_buttons_location: str
    style_external_links: bool
    vcs_pageview_mode: str
    style_nav_header_background: str
    collapse_navigation: bool
    sticky_navigation: bool
    navigation_depth: int
    includehidden: bool
    titles_only: bool
    flyout_display: str
    version_selector: bool
    language_selector: bool

class CustomBuilder:
    def __init__(self, app): pass
    def init(self): pass
    def write_doc(self, docname, doctree): pass
    def get_target_uri(self, docname): pass
    def finish(self): pass

# In conf.py
html_theme = "sphinx_rtd_theme"
html_theme_path = [get_html_theme_path()]
html_theme_options = {"navigation_depth": 4, "collapse_navigation": False}
html_static_path = ["_static"]
html_css_files = ["custom.css"]

extensions = ["sphinx_rtd_theme", "sphinx.ext.autodoc", "sphinx.ext.viewcode"]
```

```python
class ThemeAssetLoader: pass
class StaticPathResolver: pass
class CustomCssInjector: pass
class TemplateContextBuilder: pass
class FlyoutMenuRenderer: pass
class VersionSelectorRenderer: pass
class LanguageSelectorRenderer: pass
class SearchOverlayHandler: pass
class TableOfContentsBuilder: pass
class BreadcrumbRenderer: pass
class GitVcsLinker: pass
class HtmlBabelizer: pass
class CrossReferenceResolver: pass
class IndexBuilder: pass
class HighlightingPipeline: pass
class FootnoteFormatter: pass
```

```python
class JinjaTemplateLoader: pass
class StylesheetCompiler: pass
class ThemeColorPalette: pass
class FontConfigurator: pass
```

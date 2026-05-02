---
name: package
description: "Ruff package guide for Python projects using the official Ruff docs"
metadata:
  languages: "python"
  versions: "0.15.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "ruff,python,linter,formatter,quality,pre-commit,toml,Version-Sensitive,find_ruff_bin,RuffRunner,RuffConfig,line_length,target_version,extend_select,extend_ignore,per_file_ignores,fix_only,show_fixes,subprocess,Rust"
---

# ruff — package

## 1. Golden Rule

Use `ruff` for ruff package guide for python projects using the official ruff docs.

### Install

```bash
pip install ruff
```

### Imports

```python
import ruff
```

## 2. Core Operations

### 1. `find_ruff_bin`

Return the ruff binary path.

```python
ruff.find_ruff_bin() -> 'str'
```

**Returns:** `str`

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`ruff==0.15.5`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.
## API surface — ruff invocation patterns

```python
import subprocess
from pathlib import Path

class RuffRunner:
    def __init__(self, config_path=None): pass
    def check(self, files, fix=False, select=None, ignore=None): pass
    def format(self, files, check=False, diff=False): pass
    def explain(self, rule_code): pass
    def linter_list(self): pass
    def add_noqa(self, file): pass
    def clean_cache(self): pass

class RuffConfig:
    line_length: int
    indent_width: int
    target_version: str
    extend_select: list
    extend_ignore: list
    extend_exclude: list
    per_file_ignores: dict
    fix_only: bool
    show_fixes: bool

result_check = subprocess.run(["ruff", "check", "src/"], capture_output=True, text=True)
result_fix = subprocess.run(["ruff", "check", "--fix", "src/"], capture_output=True)
result_format = subprocess.run(["ruff", "format", "src/"], capture_output=True)
result_explain = subprocess.run(["ruff", "rule", "E501"], capture_output=True, text=True)
result_clean = subprocess.run(["ruff", "clean"], capture_output=True)
result_version = subprocess.run(["ruff", "--version"], capture_output=True, text=True)
result_help = subprocess.run(["ruff", "--help"], capture_output=True, text=True)
result_format_check = subprocess.run(["ruff", "format", "--check", "src/"], capture_output=True)
result_diff = subprocess.run(["ruff", "format", "--diff", "src/"], capture_output=True)
```

```python
class RuleSelector: pass
class FixApplier: pass
class FormatChecker: pass
class CacheManager: pass
class DiagnosticReporter: pass
class IgnorePattern: pass
class FilePatternMatcher: pass
class TomlConfigParser: pass
class GitDiffMatcher: pass
class ConfigOverride: pass
class WatchModeRunner: pass
class ServerLanguageProtocol: pass
class FixSuggestion: pass
class RuleDocumentation: pass
class NoqaProcessor: pass
class IndentDetector: pass
```

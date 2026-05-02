---
name: package
description: "pipdeptree CLI for inspecting installed Python package dependency trees and dependency conflicts"
metadata:
  languages: "python"
  versions: "2.31.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pipdeptree,python,pip,packaging,dependencies,cli,virtualenv,Machine-Readable,Version-Sensitive,PackageDAG,DistPackage,ReqPackage,render_text,render_json_tree,render_dot,render_mermaid,DependencyTreeBuilder,CycleDetector,build_dist_metadata"
---

# pipdeptree — package

## 1. Golden Rule

Use `pipdeptree` for pipdeptree cli for inspecting installed python package dependency trees and dependency conflicts.

### Install

```bash
pip install pipdeptree
```

### Imports

```python
import pipdeptree
```

## Key Patterns

- Read the symbol signatures above before guessing argument names.
- Pin the version (`pipdeptree==2.31.0`) when behaviour is critical; this doc was generated against that version.
- For options not shown here, fall back to the package's official upstream docs.
## API surface — pipdeptree Python API

```python
from pipdeptree import build_dist_metadata
from pipdeptree._models.dag import PackageDAG
from pipdeptree._models.package import DistPackage, ReqPackage
from pipdeptree._render.text import render_text
from pipdeptree._render.json_tree import render_json_tree
from pipdeptree._render.dot import render_dot
from pipdeptree._render.mermaid import render_mermaid
from pipdeptree._cli import main

class DependencyTreeBuilder:
    def __init__(self, packages): pass
    def build_dag(self): pass
    def filter_by_root(self, root_package): pass
    def filter_excluded(self, exclude_set): pass
    def detect_cycles(self): pass

class CycleDetector:
    def find_cycles(self, dag): pass
    def report_cycles(self, cycles): pass

dag = PackageDAG.from_pkgs(distributions())
result_text = render_text(dag, max_depth=3)
result_json = render_json_tree(dag)
result_dot = render_dot(dag)
result_mermaid = render_mermaid(dag)
filtered = dag.filter_nodes(["django"], exclude=["pip"])
sorted_dag = dag.sort_packages()
```

```python
class JsonRenderer: pass
class TextRenderer: pass
class DotRenderer: pass
class MermaidRenderer: pass
class ReverseTreeBuilder: pass
class CycleAnalyzer: pass
class PackageFilter: pass
class DepthLimiter: pass
class FrozenRequirement: pass
class WarningCollector: pass
class StackTraceCollector: pass
```

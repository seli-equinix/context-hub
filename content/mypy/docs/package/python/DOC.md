---
name: package
description: "mypy package guide for Python projects using the official mypy 1.19.1 docs"
metadata:
  languages: "python"
  versions: "1.19.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "mypy,python,typing,type-checking,static-analysis,pep-561,true,toml,ignore,Version-Sensitive,run,run_dmypy,AnyType,CallableType,Context,Instance,ParamSpecFlavor,ParamSpecType,Parameters,PartialType,PolyTranslationError,PolyTranslator,ProperType,Type,TypeAliasType,TypeInfo,TypeTranslator,TypeVarId,TypeVarLikeType,TypeVarTupleType,TypeVarType,UninhabitedType,UnpackType,apply_generic_arguments,apply_poly,erase_typevars,expand_type,get_all_type_vars,get_proper_type,get_target_type,remove_dups,ArgTypeExpander,TupleType,TypeOfAny,TypedDictType,map_actuals_to_formals,map_formals_to_actuals,map_instance_to_supertype,ConditionalTypeBinder,accumulate_type_assignments,top_frame_context,CurrentType,Expression,Frame,FrameContext,IndexExpr,MemberExpr,NameExpr,NoneType,Options,RefExpr,TypeType,UnionType,Var,collapse_variadic_union,extract_var_from_literal_hash,fill_typevars_with_any,find_unpack_in_list,flatten_nested_unions,get_declaration,is_same_type,is_subtype,literal,literal_hash,make_simplified_union,remove_instance_last_known_values,subkeys,AckMessage,BadStatus,BuildManager,BuildResult,BuildSource,BuildSourceSet,CacheMeta,ChainedPlugin,CompileError,DecodeError,DefaultPlugin,ErrorCode,ErrorFormatter,ErrorInfo,Errors,FgDepMeta,FileRawData,FileSystemCache,FilesystemMetadataStore,FindModuleCache,GraphMessage,IPCClient,IPCException,IPCMessage,Import,ImportAll,ImportBase,ImportFrom,LimitedVariableRenameVisitor,enter_scope,MessageBuilder,disable_type_names,MetadataStore,ModuleNotFound,ModuleNotFoundReason,MypyFile,NodeInfo,Plugin,PossiblyUndefinedVariableVisitor,ReportConfigContext,SCC,SccRequestMessage,SccResponseMessage,SccsDataMessage,SearchPaths,SemanticAnalyzer,allow_unbound_tvars_set,enter,file_context,inside_except_star_block_set,isolated_error_analysis,overload_item_set,set_recurse_into_functions,tvar_scope_frame,SemanticAnalyzerPreAnalysis,SourcesDataMessage,SqliteMetadataStore,State,wrap_context,SuppressionReason,SymbolTable,TypeChecker,checking_await_set,enter_attribute_inference_context,enter_class,enter_final_context,enter_overload_impl,enter_partial_types,TypeIndirectionVisitor,VariableRenameVisitor,enter_block,enter_loop,enter_try,WorkerClient,add_catch_all_gitignore,build,build_error,build_inner,compute_hash,compute_search_paths,create_metastore,decode_python_encoding,default_data_dir,deps_filtered,deps_to_json,dispatch,dump_graph,dump_line_checking_stats,dump_timing_stats,dump_type_stats,exclude_from_backups,exist_added_packages,exist_removed_submodules,find_cache_meta,find_config_file_line_number,find_module_and_diagnose,find_module_simple,find_module_with_reason,find_stale_sccs,fixup_module,free_tree,generate_deps_for_cache,get_cache_names,get_config_module_names,get_errors_name,get_mypy_comments,hash_digest,hash_digest_bytes,import_priority,in_partial_package"
---

# mypy — package

## Install

```bash
pip install mypy
```

## Imports

```python
import mypy
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `run` | Function |  |
| `run_dmypy` | Function |  |
| `AnyType` | Class |  |
| `CallableType` | Class |  |
| `Context` | Class |  |
| `Instance` | Class |  |
| `ParamSpecFlavor` | Class |  |
| `ParamSpecType` | Class |  |
| `Parameters` | Class |  |
| `PartialType` | Class |  |
| `PolyTranslationError` | Class |  |
| `PolyTranslator` | Class |  |
| `ProperType` | Class |  |
| `Type` | Class |  |
| `TypeAliasType` | Class |  |
| `TypeInfo` | Class |  |
| `TypeTranslator` | Class |  |
| `TypeVarId` | Class |  |
| `TypeVarLikeType` | Class |  |
| `TypeVarTupleType` | Class |  |
| `TypeVarType` | Class |  |
| `UninhabitedType` | Class |  |
| `UnpackType` | Class |  |
| `apply_generic_arguments` | Function |  |
| `apply_poly` | Function |  |
| `erase_typevars` | Function |  |
| `expand_type` | Function |  |
| `get_all_type_vars` | Function |  |
| `get_proper_type` | Function |  |
| `get_target_type` | Function |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `AnyType`

```python
mypy.applytype.AnyType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CallableType`

```python
mypy.applytype.CallableType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Context`

```python
mypy.applytype.Context(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Instance`

```python
mypy.applytype.Instance(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ParamSpecFlavor`

```python
mypy.applytype.ParamSpecFlavor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ParamSpecType`

```python
mypy.applytype.ParamSpecType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Parameters`

```python
mypy.applytype.Parameters(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PartialType`

```python
mypy.applytype.PartialType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PolyTranslationError`

```python
mypy.applytype.PolyTranslationError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PolyTranslator`

```python
mypy.applytype.PolyTranslator(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ProperType`

```python
mypy.applytype.ProperType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Type`

```python
mypy.applytype.Type(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeAliasType`

```python
mypy.applytype.TypeAliasType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeInfo`

```python
mypy.applytype.TypeInfo(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeTranslator`

```python
mypy.applytype.TypeTranslator(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeVarId`

```python
mypy.applytype.TypeVarId(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeVarLikeType`

```python
mypy.applytype.TypeVarLikeType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeVarTupleType`

```python
mypy.applytype.TypeVarTupleType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeVarType`

```python
mypy.applytype.TypeVarType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UninhabitedType`

```python
mypy.applytype.UninhabitedType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnpackType`

```python
mypy.applytype.UnpackType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `AnyType`

```python
mypy.argmap.AnyType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ArgTypeExpander`

```python
mypy.argmap.ArgTypeExpander(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Instance`

```python
mypy.argmap.Instance(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ParamSpecType`

```python
mypy.argmap.ParamSpecType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TupleType`

```python
mypy.argmap.TupleType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Type`

```python
mypy.argmap.Type(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeOfAny`

```python
mypy.argmap.TypeOfAny(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeVarTupleType`

```python
mypy.argmap.TypeVarTupleType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypedDictType`

```python
mypy.argmap.TypedDictType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnpackType`

```python
mypy.argmap.UnpackType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `AnyType`

```python
mypy.binder.AnyType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConditionalTypeBinder`

```python
mypy.binder.ConditionalTypeBinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CurrentType`

mypyc filler docstring

```python
mypy.binder.CurrentType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Expression`

```python
mypy.binder.Expression(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Frame`

```python
mypy.binder.Frame(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FrameContext`

```python
mypy.binder.FrameContext(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `IndexExpr`

```python
mypy.binder.IndexExpr(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Instance`

```python
mypy.binder.Instance(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MemberExpr`

```python
mypy.binder.MemberExpr(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NameExpr`

```python
mypy.binder.NameExpr(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NoneType`

```python
mypy.binder.NoneType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Options`

```python
mypy.binder.Options(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PartialType`

```python
mypy.binder.PartialType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ProperType`

```python
mypy.binder.ProperType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RefExpr`

```python
mypy.binder.RefExpr(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TupleType`

```python
mypy.binder.TupleType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Type`

```python
mypy.binder.Type(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeInfo`

```python
mypy.binder.TypeInfo(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeOfAny`

```python
mypy.binder.TypeOfAny(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeType`

```python
mypy.binder.TypeType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeVarType`

```python
mypy.binder.TypeVarType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnionType`

```python
mypy.binder.UnionType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnpackType`

```python
mypy.binder.UnpackType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Var`

```python
mypy.binder.Var(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `AckMessage`

```python
mypy.build.AckMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BadStatus`

```python
mypy.build.BadStatus(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BuildManager`

```python
mypy.build.BuildManager(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BuildResult`

```python
mypy.build.BuildResult(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BuildSource`

```python
mypy.build.BuildSource(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BuildSourceSet`

```python
mypy.build.BuildSourceSet(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CacheMeta`

```python
mypy.build.CacheMeta(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ChainedPlugin`

```python
mypy.build.ChainedPlugin(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CompileError`

```python
mypy.build.CompileError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DecodeError`

```python
mypy.build.DecodeError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DefaultPlugin`

```python
mypy.build.DefaultPlugin(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ErrorCode`

```python
mypy.build.ErrorCode(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ErrorFormatter`

```python
mypy.build.ErrorFormatter(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ErrorInfo`

```python
mypy.build.ErrorInfo(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Errors`

```python
mypy.build.Errors(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Expression`

```python
mypy.build.Expression(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FgDepMeta`

mypyc filler docstring

```python
mypy.build.FgDepMeta(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FileRawData`

```python
mypy.build.FileRawData(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FileSystemCache`

```python
mypy.build.FileSystemCache(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FilesystemMetadataStore`

```python
mypy.build.FilesystemMetadataStore(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FindModuleCache`

```python
mypy.build.FindModuleCache(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `GraphMessage`

```python
mypy.build.GraphMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `IPCClient`

```python
mypy.build.IPCClient(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `IPCException`

```python
mypy.build.IPCException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `IPCMessage`

```python
mypy.build.IPCMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Import`

```python
mypy.build.Import(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ImportAll`

```python
mypy.build.ImportAll(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ImportBase`

```python
mypy.build.ImportBase(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ImportFrom`

```python
mypy.build.ImportFrom(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LimitedVariableRenameVisitor`

```python
mypy.build.LimitedVariableRenameVisitor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MessageBuilder`

```python
mypy.build.MessageBuilder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MetadataStore`

```python
mypy.build.MetadataStore(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ModuleNotFound`

Common base class for all non-exit exceptions.

```python
mypy.build.ModuleNotFound(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ModuleNotFoundReason`

mypyc filler docstring

```python
mypy.build.ModuleNotFoundReason(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `MypyFile`

```python
mypy.build.MypyFile(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NodeInfo`

```python
mypy.build.NodeInfo(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Options`

```python
mypy.build.Options(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Plugin`

```python
mypy.build.Plugin(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PossiblyUndefinedVariableVisitor`

```python
mypy.build.PossiblyUndefinedVariableVisitor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ReportConfigContext`

mypyc filler docstring

```python
mypy.build.ReportConfigContext(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SCC`

```python
mypy.build.SCC(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SccRequestMessage`

```python
mypy.build.SccRequestMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SccResponseMessage`

```python
mypy.build.SccResponseMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SccsDataMessage`

```python
mypy.build.SccsDataMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SearchPaths`

```python
mypy.build.SearchPaths(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SemanticAnalyzer`

```python
mypy.build.SemanticAnalyzer(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SemanticAnalyzerPreAnalysis`

```python
mypy.build.SemanticAnalyzerPreAnalysis(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SourcesDataMessage`

```python
mypy.build.SourcesDataMessage(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SqliteMetadataStore`

```python
mypy.build.SqliteMetadataStore(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `State`

```python
mypy.build.State(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SuppressionReason`

```python
mypy.build.SuppressionReason(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SymbolTable`

```python
mypy.build.SymbolTable(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Type`

```python
mypy.build.Type(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeChecker`

```python
mypy.build.TypeChecker(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TypeIndirectionVisitor`

```python
mypy.build.TypeIndirectionVisitor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `VariableRenameVisitor`

```python
mypy.build.VariableRenameVisitor(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `WorkerClient`

```python
mypy.build.WorkerClient(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

## Functions

### `run`

```python
mypy.api.run(args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |

### `run_dmypy`

```python
mypy.api.run_dmypy(args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |

### `apply_generic_arguments`

```python
mypy.applytype.apply_generic_arguments(callable, orig_types, report_incompatible_typevar_value, context, skip_unsatisfied=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `callable` | `—` | `—` | pos/kw |
| `orig_types` | `—` | `—` | pos/kw |
| `report_incompatible_typevar_value` | `—` | `—` | pos/kw |
| `context` | `—` | `—` | pos/kw |
| `skip_unsatisfied` | `—` | `False` | pos/kw |

### `apply_poly`

```python
mypy.applytype.apply_poly(tp, poly_tvars)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tp` | `—` | `—` | pos/kw |
| `poly_tvars` | `—` | `—` | pos/kw |

### `erase_typevars`

```python
mypy.applytype.erase_typevars(t, ids_to_erase=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `t` | `—` | `—` | pos/kw |
| `ids_to_erase` | `—` | `None` | pos/kw |

### `expand_type`

```python
mypy.applytype.expand_type(typ, env)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `typ` | `—` | `—` | pos/kw |
| `env` | `—` | `—` | pos/kw |

### `get_all_type_vars`

```python
mypy.applytype.get_all_type_vars(tp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tp` | `—` | `—` | pos/kw |

### `get_proper_type`

```python
mypy.applytype.get_proper_type(typ)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `typ` | `—` | `—` | pos/kw |

### `get_target_type`

```python
mypy.applytype.get_target_type(tvar, type, callable, report_incompatible_typevar_value, context, skip_unsatisfied)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tvar` | `—` | `—` | pos/kw |
| `type` | `—` | `—` | pos/kw |
| `callable` | `—` | `—` | pos/kw |
| `report_incompatible_typevar_value` | `—` | `—` | pos/kw |
| `context` | `—` | `—` | pos/kw |
| `skip_unsatisfied` | `—` | `—` | pos/kw |

### `remove_dups`

```python
mypy.applytype.remove_dups(types)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `types` | `—` | `—` | pos/kw |

### `get_proper_type`

```python
mypy.argmap.get_proper_type(typ)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `typ` | `—` | `—` | pos/kw |

### `map_actuals_to_formals`

```python
mypy.argmap.map_actuals_to_formals(actual_kinds, actual_names, formal_kinds, formal_names, actual_arg_type)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `actual_kinds` | `—` | `—` | pos/kw |
| `actual_names` | `—` | `—` | pos/kw |
| `formal_kinds` | `—` | `—` | pos/kw |
| `formal_names` | `—` | `—` | pos/kw |
| `actual_arg_type` | `—` | `—` | pos/kw |

### `map_formals_to_actuals`

```python
mypy.argmap.map_formals_to_actuals(actual_kinds, actual_names, formal_kinds, formal_names, actual_arg_type)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `actual_kinds` | `—` | `—` | pos/kw |
| `actual_names` | `—` | `—` | pos/kw |
| `formal_kinds` | `—` | `—` | pos/kw |
| `formal_names` | `—` | `—` | pos/kw |
| `actual_arg_type` | `—` | `—` | pos/kw |

### `map_instance_to_supertype`

```python
mypy.argmap.map_instance_to_supertype(instance, superclass)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `superclass` | `—` | `—` | pos/kw |

### `collapse_variadic_union`

```python
mypy.binder.collapse_variadic_union(typ)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `typ` | `—` | `—` | pos/kw |

### `extract_var_from_literal_hash`

```python
mypy.binder.extract_var_from_literal_hash(key)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `—` | `—` | pos/kw |

### `fill_typevars_with_any`

```python
mypy.binder.fill_typevars_with_any(typ)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `typ` | `—` | `—` | pos/kw |

### `find_unpack_in_list`

```python
mypy.binder.find_unpack_in_list(items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |

### `flatten_nested_unions`

```python
mypy.binder.flatten_nested_unions(types, *, handle_type_alias_type=True, handle_recursive=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `types` | `—` | `—` | pos/kw |
| `handle_type_alias_type` | `—` | `True` | kw |
| `handle_recursive` | `—` | `True` | kw |

### `get_declaration`

```python
mypy.binder.get_declaration(expr)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `expr` | `—` | `—` | pos/kw |

### `get_proper_type`

```python
mypy.binder.get_proper_type(typ)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `typ` | `—` | `—` | pos/kw |

### `is_same_type`

```python
mypy.binder.is_same_type(a, b, ignore_promotions=True, subtype_context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `ignore_promotions` | `—` | `True` | pos/kw |
| `subtype_context` | `—` | `None` | pos/kw |

### `is_subtype`

```python
mypy.binder.is_subtype(left, right, *, subtype_context=None, ignore_type_params=False, ignore_pos_arg_names=False, ignore_declared_variance=False, always_covariant=False, ignore_promotions=False, options=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `left` | `—` | `—` | pos/kw |
| `right` | `—` | `—` | pos/kw |
| `subtype_context` | `—` | `None` | kw |
| `ignore_type_params` | `—` | `False` | kw |
| `ignore_pos_arg_names` | `—` | `False` | kw |
| `ignore_declared_variance` | `—` | `False` | kw |
| `always_covariant` | `—` | `False` | kw |
| `ignore_promotions` | `—` | `False` | kw |
| `options` | `—` | `None` | kw |

### `literal`

```python
mypy.binder.literal(e)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `e` | `—` | `—` | pos/kw |

### `literal_hash`

```python
mypy.binder.literal_hash(e)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `e` | `—` | `—` | pos/kw |

### `make_simplified_union`

```python
mypy.binder.make_simplified_union(items, line=-1, column=-1, *, keep_erased=False, contract_literals=True, handle_recursive=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `—` | `—` | pos/kw |
| `line` | `—` | `-1` | pos/kw |
| `column` | `—` | `-1` | pos/kw |
| `keep_erased` | `—` | `False` | kw |
| `contract_literals` | `—` | `True` | kw |
| `handle_recursive` | `—` | `True` | kw |

### `remove_instance_last_known_values`

```python
mypy.binder.remove_instance_last_known_values(t)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `t` | `—` | `—` | pos/kw |

### `subkeys`

```python
mypy.binder.subkeys(key)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `—` | `—` | pos/kw |

### `add_catch_all_gitignore`

```python
mypy.build.add_catch_all_gitignore(target_dir)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_dir` | `—` | `—` | pos/kw |

### `build`

```python
mypy.build.build(sources, options, alt_lib_path=None, flush_errors=None, fscache=None, stdout=None, stderr=None, extra_plugins=None, worker_env=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sources` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `alt_lib_path` | `—` | `None` | pos/kw |
| `flush_errors` | `—` | `None` | pos/kw |
| `fscache` | `—` | `None` | pos/kw |
| `stdout` | `—` | `None` | pos/kw |
| `stderr` | `—` | `None` | pos/kw |
| `extra_plugins` | `—` | `None` | pos/kw |
| `worker_env` | `—` | `None` | pos/kw |

### `build_error`

```python
mypy.build.build_error(msg)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `msg` | `—` | `—` | pos/kw |

### `build_inner`

```python
mypy.build.build_inner(sources, options, alt_lib_path, flush_errors, fscache, stdout, stderr, extra_plugins, workers)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sources` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `alt_lib_path` | `—` | `—` | pos/kw |
| `flush_errors` | `—` | `—` | pos/kw |
| `fscache` | `—` | `—` | pos/kw |
| `stdout` | `—` | `—` | pos/kw |
| `stderr` | `—` | `—` | pos/kw |
| `extra_plugins` | `—` | `—` | pos/kw |
| `workers` | `—` | `—` | pos/kw |

### `compute_hash`

```python
mypy.build.compute_hash(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `compute_search_paths`

```python
mypy.build.compute_search_paths(sources, options, data_dir, alt_lib_path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sources` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `data_dir` | `—` | `—` | pos/kw |
| `alt_lib_path` | `—` | `None` | pos/kw |

### `create_metastore`

```python
mypy.build.create_metastore(options, parallel_worker)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `options` | `—` | `—` | pos/kw |
| `parallel_worker` | `—` | `—` | pos/kw |

### `decode_python_encoding`

```python
mypy.build.decode_python_encoding(source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |

### `default_data_dir`

```python
mypy.build.default_data_dir()
```

### `deps_filtered`

```python
mypy.build.deps_filtered(graph, vertices, id, pri_max)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `graph` | `—` | `—` | pos/kw |
| `vertices` | `—` | `—` | pos/kw |
| `id` | `—` | `—` | pos/kw |
| `pri_max` | `—` | `—` | pos/kw |

### `deps_to_json`

```python
mypy.build.deps_to_json(x)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `x` | `—` | `—` | pos/kw |

### `dispatch`

```python
mypy.build.dispatch(sources, manager, stdout)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sources` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |
| `stdout` | `—` | `—` | pos/kw |

### `dump_graph`

```python
mypy.build.dump_graph(graph, stdout=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `graph` | `—` | `—` | pos/kw |
| `stdout` | `—` | `None` | pos/kw |

### `dump_line_checking_stats`

```python
mypy.build.dump_line_checking_stats(path, graph)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `graph` | `—` | `—` | pos/kw |

### `dump_timing_stats`

```python
mypy.build.dump_timing_stats(path, graph)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `graph` | `—` | `—` | pos/kw |

### `dump_type_stats`

```python
mypy.build.dump_type_stats(tree, path, modules, inferred=False, typemap=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `modules` | `—` | `—` | pos/kw |
| `inferred` | `—` | `False` | pos/kw |
| `typemap` | `—` | `None` | pos/kw |

### `exclude_from_backups`

```python
mypy.build.exclude_from_backups(target_dir)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_dir` | `—` | `—` | pos/kw |

### `exist_added_packages`

```python
mypy.build.exist_added_packages(suppressed, manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `suppressed` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |

### `exist_removed_submodules`

```python
mypy.build.exist_removed_submodules(dependencies, manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dependencies` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |

### `find_cache_meta`

```python
mypy.build.find_cache_meta(id, path, manager, skip_validation=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |
| `skip_validation` | `—` | `False` | pos/kw |

### `find_config_file_line_number`

```python
mypy.build.find_config_file_line_number(path, section, setting_name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `section` | `—` | `—` | pos/kw |
| `setting_name` | `—` | `—` | pos/kw |

### `find_module_and_diagnose`

```python
mypy.build.find_module_and_diagnose(manager, id, options, caller_state=None, caller_line=0, ancestor_for=None, root_source=False, skip_diagnose=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `id` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `caller_state` | `—` | `None` | pos/kw |
| `caller_line` | `—` | `0` | pos/kw |
| `ancestor_for` | `—` | `None` | pos/kw |
| `root_source` | `—` | `False` | pos/kw |
| `skip_diagnose` | `—` | `False` | pos/kw |

### `find_module_simple`

```python
mypy.build.find_module_simple(id, manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |

### `find_module_with_reason`

```python
mypy.build.find_module_with_reason(id, manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |

### `find_stale_sccs`

```python
mypy.build.find_stale_sccs(sccs, graph, manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `sccs` | `—` | `—` | pos/kw |
| `graph` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |

### `fixup_module`

```python
mypy.build.fixup_module(tree, modules, allow_missing)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree` | `—` | `—` | pos/kw |
| `modules` | `—` | `—` | pos/kw |
| `allow_missing` | `—` | `—` | pos/kw |

### `free_tree`

```python
mypy.build.free_tree(tree)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree` | `—` | `—` | pos/kw |

### `generate_deps_for_cache`

```python
mypy.build.generate_deps_for_cache(manager, graph)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `graph` | `—` | `—` | pos/kw |

### `get_cache_names`

```python
mypy.build.get_cache_names(id, path, options)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |

### `get_config_module_names`

```python
mypy.build.get_config_module_names(filename, modules)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `modules` | `—` | `—` | pos/kw |

### `get_errors_name`

```python
mypy.build.get_errors_name(meta_name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `meta_name` | `—` | `—` | pos/kw |

### `get_mypy_comments`

```python
mypy.build.get_mypy_comments(source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `source` | `—` | `—` | pos/kw |

### `hash_digest`

```python
mypy.build.hash_digest(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `hash_digest_bytes`

```python
mypy.build.hash_digest_bytes(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `import_priority`

```python
mypy.build.import_priority(imp, toplevel_priority)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `imp` | `—` | `—` | pos/kw |
| `toplevel_priority` | `—` | `—` | pos/kw |

### `in_partial_package`

```python
mypy.build.in_partial_package(id, manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `—` | pos/kw |
| `manager` | `—` | `—` | pos/kw |

## Methods

### `mypy.binder.ConditionalTypeBinder` methods

### `accumulate_type_assignments`

```python
mypy.binder.ConditionalTypeBinder.accumulate_type_assignments(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `top_frame_context`

```python
mypy.binder.ConditionalTypeBinder.top_frame_context(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `mypy.build.LimitedVariableRenameVisitor` methods

### `enter_scope`

```python
mypy.build.LimitedVariableRenameVisitor.enter_scope(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `mypy.build.MessageBuilder` methods

### `disable_type_names`

```python
mypy.build.MessageBuilder.disable_type_names(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `mypy.build.SemanticAnalyzer` methods

### `allow_unbound_tvars_set`

```python
mypy.build.SemanticAnalyzer.allow_unbound_tvars_set(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `enter`

```python
mypy.build.SemanticAnalyzer.enter(self, /, function)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `function` | `—` | `—` | pos/kw |

### `file_context`

```python
mypy.build.SemanticAnalyzer.file_context(self, /, file_node, options, active_type=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `file_node` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `active_type` | `—` | `None` | pos/kw |

### `inside_except_star_block_set`

```python
mypy.build.SemanticAnalyzer.inside_except_star_block_set(self, /, value, entering_loop=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `value` | `—` | `—` | pos/kw |
| `entering_loop` | `—` | `False` | pos/kw |

### `isolated_error_analysis`

```python
mypy.build.SemanticAnalyzer.isolated_error_analysis(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `overload_item_set`

```python
mypy.build.SemanticAnalyzer.overload_item_set(self, /, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `item` | `—` | `—` | pos/kw |

### `set_recurse_into_functions`

```python
mypy.build.SemanticAnalyzer.set_recurse_into_functions(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `tvar_scope_frame`

```python
mypy.build.SemanticAnalyzer.tvar_scope_frame(self, /, frame)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `frame` | `—` | `—` | pos/kw |

### `mypy.build.State` methods

### `wrap_context`

```python
mypy.build.State.wrap_context(self, /, check_blockers=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `check_blockers` | `—` | `True` | pos/kw |

### `mypy.build.TypeChecker` methods

### `checking_await_set`

```python
mypy.build.TypeChecker.checking_await_set(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `enter_attribute_inference_context`

```python
mypy.build.TypeChecker.enter_attribute_inference_context(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `enter_class`

```python
mypy.build.TypeChecker.enter_class(self, /, type)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `type` | `—` | `—` | pos/kw |

### `enter_final_context`

```python
mypy.build.TypeChecker.enter_final_context(self, /, is_final_def)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `is_final_def` | `—` | `—` | pos/kw |

### `enter_overload_impl`

```python
mypy.build.TypeChecker.enter_overload_impl(self, /, impl)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `impl` | `—` | `—` | pos/kw |

### `enter_partial_types`

```python
mypy.build.TypeChecker.enter_partial_types(self, /, *, is_function=False, is_class=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `is_function` | `—` | `False` | kw |
| `is_class` | `—` | `False` | kw |

### `set_recurse_into_functions`

```python
mypy.build.TypeChecker.set_recurse_into_functions(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `mypy.build.VariableRenameVisitor` methods

### `enter_block`

```python
mypy.build.VariableRenameVisitor.enter_block(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `enter_loop`

```python
mypy.build.VariableRenameVisitor.enter_loop(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |

### `enter_scope`

```python
mypy.build.VariableRenameVisitor.enter_scope(self, /, kind)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `kind` | `—` | `—` | pos/kw |

### `enter_try`

```python
mypy.build.VariableRenameVisitor.enter_try(self, /)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |


---
name: package
description: "Bandit Python package guide for security scanning Python code with the Bandit CLI"
metadata:
  languages: "python"
  versions: "1.9.4"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "bandit,python,security,sast,static-analysis,lint,ci,toml,Version-Sensitive,ini,Cwe,as_dict,as_jsons,from_dict,link,Issue,filter,get_code,accepts_baseline,checks,cwe_from_dict,issue_from_dict,takes_config,test_id,gen_blacklist,build_conf_dict,baseline_setup,init_logger,initialize,main,get_config_settings,parse_args,blacklist,report_issue,BanditConfig,convert_legacy_blacklist_data,convert_legacy_blacklist_tests,convert_legacy_config,convert_names_to_ids,get_option,get_setting,validate,Context,check_call_arg_value,get_call_arg_at_position,get_call_arg_value,get_lineno_for_call_arg,is_module_being_imported,is_module_imported_exact,is_module_imported_like,get_url,Manager,check_id,get_test_id,load_blacklists,load_formatters,load_plugins,validate_profile,BanditManager,discover_files,filter_results,get_issue_list,get_skipped,output_results,populate_baseline,results_count,run_tests,BanditMetaAst,add_node,Metrics,aggregate,begin,count_issues,count_locs,note_nosec,note_skipped_test,BanditNodeVisitor,generic_visit,post_visit,pre_visit,process,update_scores,visit,visit_Bytes,visit_Call,visit_ClassDef,visit_Constant,visit_FunctionDef,visit_Import,visit_ImportFrom,visit_Str,BanditTestSet,get_tests,BanditTester,report_error,ConfigError,InvalidModulePath,ProfileNotFound,calc_linerange,check_ast_node,concat_string,deepgetattr,escaped_bytes_representation,get_call_name,get_called_name,get_func_name,get_module_qualname_from_path,get_nosec,get_path_for_function,get_qual_attr,linerange,namespace_path_join,namespace_path_split,parse_ini_file,warnings_formatter,report,SafeMapper,do_print,get_metrics,get_results,get_verbose_details,header,wrap_file_object,flask_debug_true,assert_used,gen_config,request_with_no_cert_validation,django_extra_used,django_rawsql_used,keywords2dict,DeepAssignation,is_assigned,is_assigned_in,check_risk,django_mark_safe,evaluate_call,evaluate_var,transform2call,exec_issue,exec_used,set_bad_file_permissions,hardcoded_bind_all_interfaces,hardcoded_password_default,hardcoded_password_funcarg,hardcoded_password_string,hardcoded_tmp_directory,hashlib,huggingface_unsafe_download,paramiko_calls,any_other_function_with_shell_equals_true,has_shell,start_process_with_a_shell,start_process_with_no_shell,start_process_with_partial_path,subprocess_popen_with_shell_equals_true,subprocess_without_shell_equals_true,hardcoded_sql_expressions,linux_commands_wildcard_injection"
---

# bandit — package

## Install

```bash
pip install bandit
```

## Imports

```python
import bandit
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Cwe` | Class |  |
| `as_dict` | Method |  |
| `as_jsons` | Method |  |
| `from_dict` | Method |  |
| `link` | Method |  |
| `Issue` | Class |  |
| `as_dict` | Method | Convert the issue to a dict of values for outputting. |
| `filter` | Method | Utility to filter on confidence and severity  This function determines whether… |
| `from_dict` | Method |  |
| `get_code` | Method | Gets lines of code from a file the generated this issue.  :param max_lines: Max… |
| `accepts_baseline` | Function | Decorator to indicate formatter accepts baseline results  Use of this decorator… |
| `checks` | Function | Decorator function to set checks to be run. |
| `cwe_from_dict` | Function |  |
| `issue_from_dict` | Function |  |
| `takes_config` | Function | Test function takes config  Use of this delegate before a test function indicat… |
| `test_id` | Function | Test function identifier  Use this decorator before a test function indicates i… |
| `gen_blacklist` | Function | Generate a list of items to blacklist.  Methods of this type, "bandit.blacklist… |
| `gen_blacklist` | Function | Generate a list of items to blacklist.  Methods of this type, "bandit.blacklist… |
| `build_conf_dict` | Function | Build and return a blacklist configuration dict. |
| `baseline_setup` | Function | Baseline setup by creating temp folder and resetting repo. |
| `init_logger` | Function | Init logger. |
| `initialize` | Function | Initialize arguments and output formats. |
| `main` | Function | Execute Bandit. |
| `get_config_settings` | Function | Get configuration settings. |
| `init_logger` | Function | Init logger. |
| `main` | Function | Config generator to write configuration file. |
| `parse_args` | Function | Parse arguments. |
| `main` | Function | Bandit CLI. |
| `Cwe` | Class |  |
| `as_dict` | Method |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `Cwe`

```python
bandit.Cwe(self, id=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `0` | pos/kw |

### `Issue`

```python
bandit.Issue(self, severity, cwe=0, confidence='UNDEFINED', text='', ident=None, lineno=None, test_id='', col_offset=-1, end_col_offset=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `severity` | `—` | `—` | pos/kw |
| `cwe` | `—` | `0` | pos/kw |
| `confidence` | `—` | `'UNDEFINED'` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `ident` | `—` | `None` | pos/kw |
| `lineno` | `—` | `None` | pos/kw |
| `test_id` | `—` | `''` | pos/kw |
| `col_offset` | `—` | `-1` | pos/kw |
| `end_col_offset` | `—` | `0` | pos/kw |

### `Cwe`

```python
bandit.core.Cwe(self, id=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `0` | pos/kw |

### `Issue`

```python
bandit.core.Issue(self, severity, cwe=0, confidence='UNDEFINED', text='', ident=None, lineno=None, test_id='', col_offset=-1, end_col_offset=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `severity` | `—` | `—` | pos/kw |
| `cwe` | `—` | `0` | pos/kw |
| `confidence` | `—` | `'UNDEFINED'` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `ident` | `—` | `None` | pos/kw |
| `lineno` | `—` | `None` | pos/kw |
| `test_id` | `—` | `''` | pos/kw |
| `col_offset` | `—` | `-1` | pos/kw |
| `end_col_offset` | `—` | `0` | pos/kw |

### `BanditConfig`

```python
bandit.core.config.BanditConfig(self, config_file=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `—` | `None` | pos/kw |

### `Context`

```python
bandit.core.context.Context(self, context_object=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context_object` | `—` | `None` | pos/kw |

### `Manager`

```python
bandit.core.extension_loader.Manager(self, formatters_namespace='bandit.formatters', plugins_namespace='bandit.plugins', blacklists_namespace='bandit.blacklists')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `formatters_namespace` | `—` | `'bandit.formatters'` | pos/kw |
| `plugins_namespace` | `—` | `'bandit.plugins'` | pos/kw |
| `blacklists_namespace` | `—` | `'bandit.blacklists'` | pos/kw |

### `Cwe`

```python
bandit.core.issue.Cwe(self, id=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `—` | `0` | pos/kw |

### `Issue`

```python
bandit.core.issue.Issue(self, severity, cwe=0, confidence='UNDEFINED', text='', ident=None, lineno=None, test_id='', col_offset=-1, end_col_offset=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `severity` | `—` | `—` | pos/kw |
| `cwe` | `—` | `0` | pos/kw |
| `confidence` | `—` | `'UNDEFINED'` | pos/kw |
| `text` | `—` | `''` | pos/kw |
| `ident` | `—` | `None` | pos/kw |
| `lineno` | `—` | `None` | pos/kw |
| `test_id` | `—` | `''` | pos/kw |
| `col_offset` | `—` | `-1` | pos/kw |
| `end_col_offset` | `—` | `0` | pos/kw |

### `BanditManager`

```python
bandit.core.manager.BanditManager(self, config, agg_type, debug=False, verbose=False, quiet=False, profile=None, ignore_nosec=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `—` | `—` | pos/kw |
| `agg_type` | `—` | `—` | pos/kw |
| `debug` | `—` | `False` | pos/kw |
| `verbose` | `—` | `False` | pos/kw |
| `quiet` | `—` | `False` | pos/kw |
| `profile` | `—` | `None` | pos/kw |
| `ignore_nosec` | `—` | `False` | pos/kw |

### `BanditMetaAst`

```python
bandit.core.meta_ast.BanditMetaAst(self)
```

### `Metrics`

Bandit metric gathering.

This class is a singleton used to gather and process metrics collected when
processing a code base with bandit. Metric collection is stateful, that
is, an active metric bloc…

```python
bandit.core.metrics.Metrics(self)
```

### `BanditNodeVisitor`

```python
bandit.core.node_visitor.BanditNodeVisitor(self, fname, fdata, metaast, testset, debug, nosec_lines, metrics)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fname` | `—` | `—` | pos/kw |
| `fdata` | `—` | `—` | pos/kw |
| `metaast` | `—` | `—` | pos/kw |
| `testset` | `—` | `—` | pos/kw |
| `debug` | `—` | `—` | pos/kw |
| `nosec_lines` | `—` | `—` | pos/kw |
| `metrics` | `—` | `—` | pos/kw |

### `BanditTestSet`

```python
bandit.core.test_set.BanditTestSet(self, config, profile=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `—` | `—` | pos/kw |
| `profile` | `—` | `None` | pos/kw |

### `BanditTester`

```python
bandit.core.tester.BanditTester(self, testset, debug, nosec_lines, metrics)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `testset` | `—` | `—` | pos/kw |
| `debug` | `—` | `—` | pos/kw |
| `nosec_lines` | `—` | `—` | pos/kw |
| `metrics` | `—` | `—` | pos/kw |

### `ConfigError`

Raised when the config file fails validation.

```python
bandit.core.utils.ConfigError(self, message, config_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `—` | pos/kw |
| `config_file` | `—` | `—` | pos/kw |

### `InvalidModulePath`

Common base class for all non-exit exceptions.

```python
bandit.core.utils.InvalidModulePath(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ProfileNotFound`

Raised when chosen profile cannot be found.

```python
bandit.core.utils.ProfileNotFound(self, config_file, profile)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `—` | `—` | pos/kw |
| `profile` | `—` | `—` | pos/kw |

### `SafeMapper`

Safe mapper to handle format key errors

```python
bandit.formatters.custom.SafeMapper(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DeepAssignation`

```python
bandit.plugins.django_xss.DeepAssignation(self, var_name, ignore_nodes=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var_name` | `—` | `—` | pos/kw |
| `ignore_nodes` | `—` | `None` | pos/kw |

## Functions

### `accepts_baseline`

Decorator to indicate formatter accepts baseline results

Use of this decorator before a formatter indicates that it is able to deal
with baseline results.  Specifically this means it has a way to di…

```python
bandit.accepts_baseline(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `checks`

Decorator function to set checks to be run.

```python
bandit.checks(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `cwe_from_dict`

```python
bandit.cwe_from_dict(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `issue_from_dict`

```python
bandit.issue_from_dict(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `takes_config`

Test function takes config

Use of this delegate before a test function indicates that it should be
passed data from the config file. Passing a name parameter allows
aliasing tests and thus sharing c…

```python
bandit.takes_config(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `test_id`

Test function identifier

Use this decorator before a test function indicates its simple ID

```python
bandit.test_id(id_val)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id_val` | `—` | `—` | pos/kw |

### `gen_blacklist`

Generate a list of items to blacklist.

Methods of this type, "bandit.blacklist" plugins, are used to build a list
of items that bandit's built in blacklisting tests will use to trigger
issues. They…

```python
bandit.blacklists.calls.gen_blacklist()
```

### `gen_blacklist`

Generate a list of items to blacklist.

Methods of this type, "bandit.blacklist" plugins, are used to build a list
of items that bandit's built in blacklisting tests will use to trigger
issues. They…

```python
bandit.blacklists.imports.gen_blacklist()
```

### `build_conf_dict`

Build and return a blacklist configuration dict.

```python
bandit.blacklists.utils.build_conf_dict(name, bid, cwe, qualnames, message, level='MEDIUM')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `bid` | `—` | `—` | pos/kw |
| `cwe` | `—` | `—` | pos/kw |
| `qualnames` | `—` | `—` | pos/kw |
| `message` | `—` | `—` | pos/kw |
| `level` | `—` | `'MEDIUM'` | pos/kw |

### `baseline_setup`

Baseline setup by creating temp folder and resetting repo.

```python
bandit.cli.baseline.baseline_setup()
```

### `init_logger`

Init logger.

```python
bandit.cli.baseline.init_logger()
```

### `initialize`

Initialize arguments and output formats.

```python
bandit.cli.baseline.initialize()
```

### `main`

Execute Bandit.

```python
bandit.cli.baseline.main()
```

### `get_config_settings`

Get configuration settings.

```python
bandit.cli.config_generator.get_config_settings()
```

### `init_logger`

Init logger.

```python
bandit.cli.config_generator.init_logger()
```

### `main`

Config generator to write configuration file.

```python
bandit.cli.config_generator.main()
```

### `parse_args`

Parse arguments.

```python
bandit.cli.config_generator.parse_args()
```

### `main`

Bandit CLI.

```python
bandit.cli.main.main()
```

### `accepts_baseline`

Decorator to indicate formatter accepts baseline results

Use of this decorator before a formatter indicates that it is able to deal
with baseline results.  Specifically this means it has a way to di…

```python
bandit.core.accepts_baseline(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `checks`

Decorator function to set checks to be run.

```python
bandit.core.checks(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `cwe_from_dict`

```python
bandit.core.cwe_from_dict(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `issue_from_dict`

```python
bandit.core.issue_from_dict(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `takes_config`

Test function takes config

Use of this delegate before a test function indicates that it should be
passed data from the config file. Passing a name parameter allows
aliasing tests and thus sharing c…

```python
bandit.core.takes_config(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `test_id`

Test function identifier

Use this decorator before a test function indicates its simple ID

```python
bandit.core.test_id(id_val)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id_val` | `—` | `—` | pos/kw |

### `blacklist`

Generic blacklist test, B001.

This generic blacklist test will be called for any encountered node with
defined blacklist data available. This data is loaded via plugins using
the 'bandit.blacklists'…

```python
bandit.core.blacklisting.blacklist(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `report_issue`

```python
bandit.core.blacklisting.report_issue(check, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `check` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `get_url`

```python
bandit.core.docs_utils.get_url(bid)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `bid` | `—` | `—` | pos/kw |

### `cwe_from_dict`

```python
bandit.core.issue.cwe_from_dict(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `issue_from_dict`

```python
bandit.core.issue.issue_from_dict(data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |

### `accepts_baseline`

Decorator to indicate formatter accepts baseline results

Use of this decorator before a formatter indicates that it is able to deal
with baseline results.  Specifically this means it has a way to di…

```python
bandit.core.test_properties.accepts_baseline(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `checks`

Decorator function to set checks to be run.

```python
bandit.core.test_properties.checks(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `takes_config`

Test function takes config

Use of this delegate before a test function indicates that it should be
passed data from the config file. Passing a name parameter allows
aliasing tests and thus sharing c…

```python
bandit.core.test_properties.takes_config(*args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

### `test_id`

Test function identifier

Use this decorator before a test function indicates its simple ID

```python
bandit.core.test_properties.test_id(id_val)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id_val` | `—` | `—` | pos/kw |

### `calc_linerange`

Calculate linerange for subtree

```python
bandit.core.utils.calc_linerange(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `check_ast_node`

Check if the given name is that of a valid AST node.

```python
bandit.core.utils.check_ast_node(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `concat_string`

Builds a string from a ast.BinOp chain.

This will build a string from a series of ast.Constant nodes wrapped in
ast.BinOp nodes. Something like "a" + "b" + "c" or "a %s" % val etc.
The provided node…

```python
bandit.core.utils.concat_string(node, stop=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `stop` | `—` | `None` | pos/kw |

### `deepgetattr`

Recurses through an attribute chain to get the ultimate value.

```python
bandit.core.utils.deepgetattr(obj, attr)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `—` | pos/kw |
| `attr` | `—` | `—` | pos/kw |

### `escaped_bytes_representation`

PY3 bytes need escaping for comparison with other strings.

In practice it turns control characters into acceptable codepoints then
encodes them into bytes again to turn unprintable bytes into printa…

```python
bandit.core.utils.escaped_bytes_representation(b)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `b` | `—` | `—` | pos/kw |

### `get_call_name`

```python
bandit.core.utils.get_call_name(node, aliases)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `aliases` | `—` | `—` | pos/kw |

### `get_called_name`

Get a function name from an ast.Call node.

An ast.Call node representing a method call with present differently to one
wrapping a function call: thing.call() vs call(). This helper will grab the
unq…

```python
bandit.core.utils.get_called_name(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `get_func_name`

```python
bandit.core.utils.get_func_name(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `get_module_qualname_from_path`

Get the module's qualified name by analysis of the path.

Resolve the absolute pathname and eliminate symlinks. This could result in
an incorrect name if symlinks are used to restructure the python l…

```python
bandit.core.utils.get_module_qualname_from_path(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `get_nosec`

```python
bandit.core.utils.get_nosec(nosec_lines, context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nosec_lines` | `—` | `—` | pos/kw |
| `context` | `—` | `—` | pos/kw |

### `get_path_for_function`

Get the path of the file where the function is defined.

:returns: the path, or None if one could not be found or f is not a real
    function

```python
bandit.core.utils.get_path_for_function(f)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `f` | `—` | `—` | pos/kw |

### `get_qual_attr`

```python
bandit.core.utils.get_qual_attr(node, aliases)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `aliases` | `—` | `—` | pos/kw |

### `linerange`

Get line number range from a node.

```python
bandit.core.utils.linerange(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `namespace_path_join`

Extend the current namespace path with an additional name

Take a namespace path (i.e., package.module.class) and extends it
with an additional name (i.e., package.module.class.subclass).
This is sim…

```python
bandit.core.utils.namespace_path_join(base, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `base` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `namespace_path_split`

Split the namespace path into a pair (head, tail).

Tail will be the last namespace path component and head will
be everything leading up to that in the path. This is similar to
os.path.split.

:para…

```python
bandit.core.utils.namespace_path_split(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `parse_ini_file`

```python
bandit.core.utils.parse_ini_file(f_loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `f_loc` | `—` | `—` | pos/kw |

### `warnings_formatter`

Monkey patch for warnings.warn to suppress cruft output.

```python
bandit.core.utils.warnings_formatter(message, category=<class 'UserWarning'>, filename='', lineno=-1, line='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `—` | pos/kw |
| `category` | `—` | `<class 'UserWarning'>` | pos/kw |
| `filename` | `—` | `''` | pos/kw |
| `lineno` | `—` | `-1` | pos/kw |
| `line` | `—` | `''` | pos/kw |

### `report`

Prints issues in CSV format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:param conf_level: Fi…

```python
bandit.formatters.csv.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `report`

Prints issues in custom format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:param conf_level:…

```python
bandit.formatters.custom.report(manager, fileobj, sev_level, conf_level, template=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `template` | `—` | `None` | pos/kw |

### `report`

Writes issues to 'fileobj' in HTML format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:param…

```python
bandit.formatters.html.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `report`

''Prints issues in JSON format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:param conf_level:…

```python
bandit.formatters.json.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `do_print`

```python
bandit.formatters.screen.do_print(bits)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `bits` | `—` | `—` | pos/kw |

### `get_metrics`

```python
bandit.formatters.screen.get_metrics(manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |

### `get_results`

```python
bandit.formatters.screen.get_results(manager, sev_level, conf_level, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `get_verbose_details`

```python
bandit.formatters.screen.get_verbose_details(manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |

### `header`

```python
bandit.formatters.screen.header(text, *args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |

### `report`

Prints discovered issues formatted for screen reading

This makes use of VT100 terminal codes for colored text.

:param manager: the bandit manager object
:param fileobj: The output file object, whic…

```python
bandit.formatters.screen.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `get_metrics`

```python
bandit.formatters.text.get_metrics(manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |

### `get_results`

```python
bandit.formatters.text.get_results(manager, sev_level, conf_level, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `get_verbose_details`

```python
bandit.formatters.text.get_verbose_details(manager)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |

### `report`

Prints discovered issues in the text format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:para…

```python
bandit.formatters.text.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `wrap_file_object`

If the fileobj passed in cannot handle text, use TextIOWrapper
to handle the conversion.

```python
bandit.formatters.utils.wrap_file_object(fileobj)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fileobj` | `—` | `—` | pos/kw |

### `report`

Prints issues in XML format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:param conf_level: Fi…

```python
bandit.formatters.xml.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `report`

Prints issues in YAML format

:param manager: the bandit manager object
:param fileobj: The output file object, which may be sys.stdout
:param sev_level: Filtering severity level
:param conf_level: F…

```python
bandit.formatters.yaml.report(manager, fileobj, sev_level, conf_level, lines=-1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manager` | `—` | `—` | pos/kw |
| `fileobj` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `lines` | `—` | `-1` | pos/kw |

### `flask_debug_true`

```python
bandit.plugins.app_debug.flask_debug_true(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `assert_used`

```python
bandit.plugins.asserts.assert_used(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `gen_config`

```python
bandit.plugins.asserts.gen_config(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `request_with_no_cert_validation`

```python
bandit.plugins.crypto_request_no_cert_validation.request_with_no_cert_validation(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `django_extra_used`

**B610: Potential SQL injection on extra function**

:Example:

.. code-block:: none

    >> Issue: [B610:django_extra_used] Use of extra potential SQL attack vector.
       Severity: Medium Confiden…

```python
bandit.plugins.django_sql_injection.django_extra_used(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `django_rawsql_used`

**B611: Potential SQL injection on RawSQL function**

:Example:

.. code-block:: none

    >> Issue: [B611:django_rawsql_used] Use of RawSQL potential SQL attack vector.
       Severity: Medium Confi…

```python
bandit.plugins.django_sql_injection.django_rawsql_used(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `keywords2dict`

```python
bandit.plugins.django_sql_injection.keywords2dict(keywords)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `keywords` | `—` | `—` | pos/kw |

### `check_risk`

```python
bandit.plugins.django_xss.check_risk(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `django_mark_safe`

**B703: Potential XSS on mark_safe function**

:Example:

.. code-block:: none

    >> Issue: [B703:django_mark_safe] Potential XSS on mark_safe function.
       Severity: Medium Confidence: High…

```python
bandit.plugins.django_xss.django_mark_safe(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `evaluate_call`

```python
bandit.plugins.django_xss.evaluate_call(call, parent, ignore_nodes=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `call` | `—` | `—` | pos/kw |
| `parent` | `—` | `—` | pos/kw |
| `ignore_nodes` | `—` | `None` | pos/kw |

### `evaluate_var`

```python
bandit.plugins.django_xss.evaluate_var(xss_var, parent, until, ignore_nodes=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `xss_var` | `—` | `—` | pos/kw |
| `parent` | `—` | `—` | pos/kw |
| `until` | `—` | `—` | pos/kw |
| `ignore_nodes` | `—` | `None` | pos/kw |

### `transform2call`

```python
bandit.plugins.django_xss.transform2call(var)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var` | `—` | `—` | pos/kw |

### `exec_issue`

```python
bandit.plugins.exec.exec_issue()
```

### `exec_used`

```python
bandit.plugins.exec.exec_used(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `set_bad_file_permissions`

```python
bandit.plugins.general_bad_file_permissions.set_bad_file_permissions(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `hardcoded_bind_all_interfaces`

```python
bandit.plugins.general_bind_all_interfaces.hardcoded_bind_all_interfaces(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `hardcoded_password_default`

**B107: Test for use of hard-coded password argument defaults**

The use of hard-coded passwords increases the possibility of password
guessing tremendously. This plugin test looks for all function d…

```python
bandit.plugins.general_hardcoded_password.hardcoded_password_default(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `hardcoded_password_funcarg`

**B106: Test for use of hard-coded password function arguments**

The use of hard-coded passwords increases the possibility of password
guessing tremendously. This plugin test looks for all function…

```python
bandit.plugins.general_hardcoded_password.hardcoded_password_funcarg(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `hardcoded_password_string`

**B105: Test for use of hard-coded password strings**

The use of hard-coded passwords increases the possibility of password
guessing tremendously. This plugin test looks for all string literals and…

```python
bandit.plugins.general_hardcoded_password.hardcoded_password_string(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `gen_config`

```python
bandit.plugins.general_hardcoded_tmp.gen_config(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `hardcoded_tmp_directory`

```python
bandit.plugins.general_hardcoded_tmp.hardcoded_tmp_directory(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `hashlib`

```python
bandit.plugins.hashlib_insecure_functions.hashlib(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `huggingface_unsafe_download`

This plugin checks for unsafe artifact download from Hugging Face Hub
without immutable/reproducible revision pinning.

```python
bandit.plugins.huggingface_unsafe_download.huggingface_unsafe_download(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `paramiko_calls`

```python
bandit.plugins.injection_paramiko.paramiko_calls(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `any_other_function_with_shell_equals_true`

**B604: Test for any function with shell equals true**

Python possesses many mechanisms to invoke an external executable. However,
doing so may present a security issue if appropriate care is not ta…

```python
bandit.plugins.injection_shell.any_other_function_with_shell_equals_true(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `gen_config`

```python
bandit.plugins.injection_shell.gen_config(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `has_shell`

```python
bandit.plugins.injection_shell.has_shell(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `start_process_with_a_shell`

**B605: Test for starting a process with a shell**

Python possesses many mechanisms to invoke an external executable. However,
doing so may present a security issue if appropriate care is not taken…

```python
bandit.plugins.injection_shell.start_process_with_a_shell(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `start_process_with_no_shell`

**B606: Test for starting a process with no shell**

Python possesses many mechanisms to invoke an external executable. However,
doing so may present a security issue if appropriate care is not taken…

```python
bandit.plugins.injection_shell.start_process_with_no_shell(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `start_process_with_partial_path`

**B607: Test for starting a process with a partial path**

Python possesses many mechanisms to invoke an external executable. If the
desired executable path is not fully qualified relative to the fil…

```python
bandit.plugins.injection_shell.start_process_with_partial_path(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `subprocess_popen_with_shell_equals_true`

**B602: Test for use of popen with shell equals true**

Python possesses many mechanisms to invoke an external executable. However,
doing so may present a security issue if appropriate care is not ta…

```python
bandit.plugins.injection_shell.subprocess_popen_with_shell_equals_true(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `subprocess_without_shell_equals_true`

**B603: Test for use of subprocess without shell equals true**

Python possesses many mechanisms to invoke an external executable. However,
doing so may present a security issue if appropriate care i…

```python
bandit.plugins.injection_shell.subprocess_without_shell_equals_true(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `hardcoded_sql_expressions`

```python
bandit.plugins.injection_sql.hardcoded_sql_expressions(context)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |

### `gen_config`

```python
bandit.plugins.injection_wildcard.gen_config(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `linux_commands_wildcard_injection`

```python
bandit.plugins.injection_wildcard.linux_commands_wildcard_injection(context, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

## Methods

### `bandit.Cwe` methods

### `as_dict`

```python
bandit.Cwe.as_dict(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_jsons`

```python
bandit.Cwe.as_jsons(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_dict`

```python
bandit.Cwe.from_dict(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |

### `link`

```python
bandit.Cwe.link(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `bandit.Issue` methods

### `as_dict`

Convert the issue to a dict of values for outputting.

```python
bandit.Issue.as_dict(self, with_code=True, max_lines=3)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `with_code` | `—` | `True` | pos/kw |
| `max_lines` | `—` | `3` | pos/kw |

### `filter`

Utility to filter on confidence and severity

This function determines whether an issue should be included by
comparing the severity and confidence rating of the issue to minimum
thresholds specified…

```python
bandit.Issue.filter(self, severity, confidence)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `severity` | `—` | `—` | pos/kw |
| `confidence` | `—` | `—` | pos/kw |

### `from_dict`

```python
bandit.Issue.from_dict(self, data, with_code=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |
| `with_code` | `—` | `True` | pos/kw |

### `get_code`

Gets lines of code from a file the generated this issue.

:param max_lines: Max lines of context to return
:param tabbed: Use tabbing in the output
:return: strings of code

```python
bandit.Issue.get_code(self, max_lines=3, tabbed=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_lines` | `—` | `3` | pos/kw |
| `tabbed` | `—` | `False` | pos/kw |

### `bandit.core.Cwe` methods

### `as_dict`

```python
bandit.core.Cwe.as_dict(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_jsons`

```python
bandit.core.Cwe.as_jsons(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_dict`

```python
bandit.core.Cwe.from_dict(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |

### `link`

```python
bandit.core.Cwe.link(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `bandit.core.Issue` methods

### `as_dict`

Convert the issue to a dict of values for outputting.

```python
bandit.core.Issue.as_dict(self, with_code=True, max_lines=3)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `with_code` | `—` | `True` | pos/kw |
| `max_lines` | `—` | `3` | pos/kw |

### `filter`

Utility to filter on confidence and severity

This function determines whether an issue should be included by
comparing the severity and confidence rating of the issue to minimum
thresholds specified…

```python
bandit.core.Issue.filter(self, severity, confidence)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `severity` | `—` | `—` | pos/kw |
| `confidence` | `—` | `—` | pos/kw |

### `from_dict`

```python
bandit.core.Issue.from_dict(self, data, with_code=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |
| `with_code` | `—` | `True` | pos/kw |

### `get_code`

Gets lines of code from a file the generated this issue.

:param max_lines: Max lines of context to return
:param tabbed: Use tabbing in the output
:return: strings of code

```python
bandit.core.Issue.get_code(self, max_lines=3, tabbed=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_lines` | `—` | `3` | pos/kw |
| `tabbed` | `—` | `False` | pos/kw |

### `bandit.core.config.BanditConfig` methods

### `convert_legacy_blacklist_data`

Detect legacy blacklist data and convert it to new format.

```python
bandit.core.config.BanditConfig.convert_legacy_blacklist_data(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `convert_legacy_blacklist_tests`

Detect old blacklist tests, convert to use new builtin.

```python
bandit.core.config.BanditConfig.convert_legacy_blacklist_tests(profiles, bad_imports, bad_calls)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `profiles` | `—` | `—` | pos/kw |
| `bad_imports` | `—` | `—` | pos/kw |
| `bad_calls` | `—` | `—` | pos/kw |

### `convert_legacy_config`

```python
bandit.core.config.BanditConfig.convert_legacy_config(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `convert_names_to_ids`

Convert test names to IDs, unknown names are left unchanged.

```python
bandit.core.config.BanditConfig.convert_names_to_ids(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_option`

Returns the option from the config specified by the option_string.

'.' can be used to denote levels, for example to retrieve the options
from the 'a' profile you can use 'profiles.a'
:param option_s…

```python
bandit.core.config.BanditConfig.get_option(self, option_string)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `option_string` | `—` | `—` | pos/kw |

### `get_setting`

```python
bandit.core.config.BanditConfig.get_setting(self, setting_name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `setting_name` | `—` | `—` | pos/kw |

### `validate`

Validate the config data.

```python
bandit.core.config.BanditConfig.validate(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `bandit.core.context.Context` methods

### `check_call_arg_value`

Checks for a value of a named argument in a function call.

Returns none if the specified argument is not found.
:param argument_name: A string - name of the argument to look for
:param argument_valu…

```python
bandit.core.context.Context.check_call_arg_value(self, argument_name, argument_values=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `argument_name` | `—` | `—` | pos/kw |
| `argument_values` | `—` | `None` | pos/kw |

### `get_call_arg_at_position`

Returns positional argument at the specified position (if it exists)

:param position_num: The index of the argument to return the value for
:return: Value of the argument at the specified position i…

```python
bandit.core.context.Context.get_call_arg_at_position(self, position_num)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `position_num` | `—` | `—` | pos/kw |

### `get_call_arg_value`

Gets the value of a named argument in a function call.

:return: named argument value

```python
bandit.core.context.Context.get_call_arg_value(self, argument_name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `argument_name` | `—` | `—` | pos/kw |

### `get_lineno_for_call_arg`

Get the line number for a specific named argument

In case the call is split over multiple lines, get the correct one for
the argument.
:param argument_name: A string - name of the argument to look f…

```python
bandit.core.context.Context.get_lineno_for_call_arg(self, argument_name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `argument_name` | `—` | `—` | pos/kw |

### `is_module_being_imported`

Check for the specified module is currently being imported

:param module: The module name to look for
:return: True if the module is found, False otherwise

```python
bandit.core.context.Context.is_module_being_imported(self, module)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |

### `is_module_imported_exact`

Check if a specified module has been imported; only exact matches.

:param module: The module name to look for
:return: True if the module is found, False otherwise

```python
bandit.core.context.Context.is_module_imported_exact(self, module)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |

### `is_module_imported_like`

Check if a specified module has been imported

Check if a specified module has been imported; specified module exists
as part of any import statement.
:param module: The module name to look for
:retu…

```python
bandit.core.context.Context.is_module_imported_like(self, module)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |

### `bandit.core.extension_loader.Manager` methods

### `check_id`

```python
bandit.core.extension_loader.Manager.check_id(self, test)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `test` | `—` | `—` | pos/kw |

### `get_test_id`

```python
bandit.core.extension_loader.Manager.get_test_id(self, test_name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `test_name` | `—` | `—` | pos/kw |

### `load_blacklists`

```python
bandit.core.extension_loader.Manager.load_blacklists(self, blacklist_namespace)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `blacklist_namespace` | `—` | `—` | pos/kw |

### `load_formatters`

```python
bandit.core.extension_loader.Manager.load_formatters(self, formatters_namespace)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `formatters_namespace` | `—` | `—` | pos/kw |

### `load_plugins`

```python
bandit.core.extension_loader.Manager.load_plugins(self, plugins_namespace)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `plugins_namespace` | `—` | `—` | pos/kw |

### `validate_profile`

Validate that everything in the configured profiles looks good.

```python
bandit.core.extension_loader.Manager.validate_profile(self, profile)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `profile` | `—` | `—` | pos/kw |

### `bandit.core.issue.Cwe` methods

### `as_dict`

```python
bandit.core.issue.Cwe.as_dict(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_jsons`

```python
bandit.core.issue.Cwe.as_jsons(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `from_dict`

```python
bandit.core.issue.Cwe.from_dict(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |

### `link`

```python
bandit.core.issue.Cwe.link(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `bandit.core.issue.Issue` methods

### `as_dict`

Convert the issue to a dict of values for outputting.

```python
bandit.core.issue.Issue.as_dict(self, with_code=True, max_lines=3)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `with_code` | `—` | `True` | pos/kw |
| `max_lines` | `—` | `3` | pos/kw |

### `filter`

Utility to filter on confidence and severity

This function determines whether an issue should be included by
comparing the severity and confidence rating of the issue to minimum
thresholds specified…

```python
bandit.core.issue.Issue.filter(self, severity, confidence)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `severity` | `—` | `—` | pos/kw |
| `confidence` | `—` | `—` | pos/kw |

### `from_dict`

```python
bandit.core.issue.Issue.from_dict(self, data, with_code=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |
| `with_code` | `—` | `True` | pos/kw |

### `get_code`

Gets lines of code from a file the generated this issue.

:param max_lines: Max lines of context to return
:param tabbed: Use tabbing in the output
:return: strings of code

```python
bandit.core.issue.Issue.get_code(self, max_lines=3, tabbed=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `max_lines` | `—` | `3` | pos/kw |
| `tabbed` | `—` | `False` | pos/kw |

### `bandit.core.manager.BanditManager` methods

### `discover_files`

Add tests directly and from a directory to the test set

:param targets: The command line list of files and directories
:param recursive: True/False - whether to add all files from dirs
:return:

```python
bandit.core.manager.BanditManager.discover_files(self, targets, recursive=False, excluded_paths='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `targets` | `—` | `—` | pos/kw |
| `recursive` | `—` | `False` | pos/kw |
| `excluded_paths` | `—` | `''` | pos/kw |

### `filter_results`

Returns a list of results filtered by the baseline

This works by checking the number of results returned from each file we
process. If the number of results is different to the number reported
for t…

```python
bandit.core.manager.BanditManager.filter_results(self, sev_filter, conf_filter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sev_filter` | `—` | `—` | pos/kw |
| `conf_filter` | `—` | `—` | pos/kw |

### `get_issue_list`

```python
bandit.core.manager.BanditManager.get_issue_list(self, sev_level='LOW', conf_level='LOW')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `'LOW'` | pos/kw |
| `conf_level` | `—` | `'LOW'` | pos/kw |

### `get_skipped`

```python
bandit.core.manager.BanditManager.get_skipped(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `output_results`

Outputs results from the result store

:param lines: How many surrounding lines to show per result
:param sev_level: Which severity levels to show (LOW, MEDIUM, HIGH)
:param conf_level: Which confide…

```python
bandit.core.manager.BanditManager.output_results(self, lines, sev_level, conf_level, output_file, output_format, template=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |
| `sev_level` | `—` | `—` | pos/kw |
| `conf_level` | `—` | `—` | pos/kw |
| `output_file` | `—` | `—` | pos/kw |
| `output_format` | `—` | `—` | pos/kw |
| `template` | `—` | `None` | pos/kw |

### `populate_baseline`

Populate a baseline set of issues from a JSON report

This will populate a list of baseline issues discovered from a previous
run of bandit. Later this baseline can be used to filter out the result
s…

```python
bandit.core.manager.BanditManager.populate_baseline(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |

### `results_count`

Return the count of results

:param sev_filter: Severity level to filter lower
:param conf_filter: Confidence level to filter
:return: Number of results in the set

```python
bandit.core.manager.BanditManager.results_count(self, sev_filter='LOW', conf_filter='LOW')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sev_filter` | `—` | `'LOW'` | pos/kw |
| `conf_filter` | `—` | `'LOW'` | pos/kw |

### `run_tests`

Runs through all files in the scope

:return: -

```python
bandit.core.manager.BanditManager.run_tests(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `bandit.core.meta_ast.BanditMetaAst` methods

### `add_node`

Add a node to the AST node collection

:param node: The AST node to add
:param parent_id: The ID of the node's parent
:param depth: The depth of the node
:return: -

```python
bandit.core.meta_ast.BanditMetaAst.add_node(self, node, parent_id, depth)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |
| `parent_id` | `—` | `—` | pos/kw |
| `depth` | `—` | `—` | pos/kw |

### `bandit.core.metrics.Metrics` methods

### `aggregate`

Do final aggregation of metrics.

```python
bandit.core.metrics.Metrics.aggregate(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `begin`

Begin a new metric block.

This starts a new metric collection name "fname" and makes is active.
:param fname: the metrics unique name, normally the file name.

```python
bandit.core.metrics.Metrics.begin(self, fname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `fname` | `—` | `—` | pos/kw |

### `count_issues`

```python
bandit.core.metrics.Metrics.count_issues(self, scores)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scores` | `—` | `—` | pos/kw |

### `count_locs`

Count lines of code.

We count lines that are not empty and are not comments. The result is
added to our currently active metrics loc count (normally this is 0).

:param lines: lines in the file to p…

```python
bandit.core.metrics.Metrics.count_locs(self, lines)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lines` | `—` | `—` | pos/kw |

### `note_nosec`

Note a "nosec" comment.

Increment the currently active metrics nosec count.
:param num: number of nosecs seen, defaults to 1

```python
bandit.core.metrics.Metrics.note_nosec(self, num=1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `num` | `—` | `1` | pos/kw |

### `note_skipped_test`

Note a "nosec BXXX, BYYY, ..." comment.

Increment the currently active metrics skipped_tests count.
:param num: number of skipped_tests seen, defaults to 1

```python
bandit.core.metrics.Metrics.note_skipped_test(self, num=1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `num` | `—` | `1` | pos/kw |

### `bandit.core.node_visitor.BanditNodeVisitor` methods

### `generic_visit`

Drive the visitor.

```python
bandit.core.node_visitor.BanditNodeVisitor.generic_visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `post_visit`

```python
bandit.core.node_visitor.BanditNodeVisitor.post_visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `pre_visit`

```python
bandit.core.node_visitor.BanditNodeVisitor.pre_visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `process`

Main process loop

Build and process the AST
:param lines: lines code to process
:return score: the aggregated score for the current file

```python
bandit.core.node_visitor.BanditNodeVisitor.process(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |

### `update_scores`

Score updater

Since we moved from a single score value to a map of scores per
severity, this is needed to update the stored list.
:param score: The score list to update our scores with

```python
bandit.core.node_visitor.BanditNodeVisitor.update_scores(self, scores)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `scores` | `—` | `—` | pos/kw |

### `visit`

```python
bandit.core.node_visitor.BanditNodeVisitor.visit(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Bytes`

Visitor for AST Bytes nodes

add relevant information about node to
the context for use in tests which inspect strings.
:param node: The node that is being inspected
:return: -

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_Bytes(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Call`

Visitor for AST Call nodes

add relevant information about the node to
the context for use in tests which inspect function calls.
:param node: The node that is being inspected
:return: -

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_Call(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_ClassDef`

Visitor for AST ClassDef node

Add class name to current namespace for all descendants.
:param node: Node being inspected
:return: -

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_ClassDef(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Constant`

Visitor for AST Constant nodes

call the appropriate method for the node type.
this maintains compatibility with <3.6 and 3.8+

This code is heavily influenced by Anthony Sottile (@asottile) here:
ht…

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_Constant(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_FunctionDef`

Visitor for AST FunctionDef nodes

add relevant information about the node to
the context for use in tests which inspect function definitions.
Add the function name to the current namespace for all d…

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_FunctionDef(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Import`

Visitor for AST Import nodes

add relevant information about node to
the context for use in tests which inspect imports.
:param node: The node that is being inspected
:return: -

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_Import(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_ImportFrom`

Visitor for AST ImportFrom nodes

add relevant information about node to
the context for use in tests which inspect imports.
:param node: The node that is being inspected
:return: -

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_ImportFrom(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `visit_Str`

Visitor for AST String nodes

add relevant information about node to
the context for use in tests which inspect strings.
:param node: The node that is being inspected
:return: -

```python
bandit.core.node_visitor.BanditNodeVisitor.visit_Str(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `bandit.core.test_set.BanditTestSet` methods

### `get_tests`

Returns all tests that are of type checktype

:param checktype: The type of test to filter on
:return: A list of tests which are of the specified type

```python
bandit.core.test_set.BanditTestSet.get_tests(self, checktype)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `checktype` | `—` | `—` | pos/kw |

### `bandit.core.tester.BanditTester` methods

### `report_error`

```python
bandit.core.tester.BanditTester.report_error(test, context, error)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `test` | `—` | `—` | pos/kw |
| `context` | `—` | `—` | pos/kw |
| `error` | `—` | `—` | pos/kw |

### `run_tests`

Runs all tests for a certain type of check, for example

Runs all tests for a certain type of check, for example 'functions'
store results in results.

:param raw_context: Raw context dictionary
:par…

```python
bandit.core.tester.BanditTester.run_tests(self, raw_context, checktype)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `raw_context` | `—` | `—` | pos/kw |
| `checktype` | `—` | `—` | pos/kw |

### `bandit.plugins.django_xss.DeepAssignation` methods

### `is_assigned`

```python
bandit.plugins.django_xss.DeepAssignation.is_assigned(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `is_assigned_in`

```python
bandit.plugins.django_xss.DeepAssignation.is_assigned_in(self, items)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `items` | `—` | `—` | pos/kw |


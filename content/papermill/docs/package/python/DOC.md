---
name: package
description: "papermill for parameterizing, executing, and saving Jupyter notebooks in Python pipelines"
metadata:
  languages: "python"
  versions: "2.7.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "papermill,python,jupyter,notebooks,pipeline,parameters,automation,execute_notebook,papermill as pm,Version-Sensitive,inspect_notebook,PapermillException,PapermillExecutionError,NoDatesSafeLoader,add_constructor,add_implicit_resolver,add_indent,add_multi_constructor,add_path_resolver,ascend_resolver,check_block_entry,check_data,check_directive,check_document_end,check_document_start,check_event,check_key,check_node,check_plain,check_printable,check_resolver_prefix,check_state_key,check_token,check_value,compose_document,compose_mapping_node,compose_node,compose_scalar_node,compose_sequence_node,construct_document,construct_mapping,construct_object,construct_pairs,construct_scalar,display_notebook_help,print_papermill_version,read_yaml_file,PapermillNotebookClient,add_traits,async_execute,async_execute_cell,async_setup_kernel,async_start_new_kernel,async_start_new_kernel_client,async_wait_for_reply,class_config_rst_doc,class_config_section,class_get_help,class_get_trait_help,class_own_trait_events,class_own_traits,class_print_help,class_trait_names,class_traits,clear_display_id_mapping,clear_output,create_kernel_manager,execute,execute_cell,handle_comm_msg,has_trait,hold_trait_notifications,log_output_message,notify_change,observe,on_comm_open_jupyter_widget,on_trait_change,output,Engine,execute_managed_notebook,nb_kernel_name,nb_language,NBClientEngine,NotebookExecutionManager,autosave_cell,cell_complete,cell_exception,cell_start,cleanup_pbar,complete_pbar,get_cell_description,notebook_complete,notebook_start,now,save,set_timer,PapermillEngines,execute_notebook_with_engine,get_engine,register,register_entry_points,catch_nb_assignment,merge_kwargs,remove_args,write_ipynb,AwsError,FileExistsError,PapermillMissingParameterException,PapermillOptionalDependencyException,PapermillParameterOverwriteWarning,PapermillRateLimitException,PapermillWarning,missing_dependency_generator,missing_environment_variable_generator,strip_color,add_builtin_parameters,chdir,get_pretty_path,load_notebook_node,local_file_io_cwd,parameterize_notebook,parameterize_path,prepare_notebook_metadata,raise_for_execution_errors,remove_error_markers,any_tagged_cell,find_first_tagged_cell_index,ABSHandler,listdir,pretty_path,read,write,ADL,ADLHandler,AzureBlobStore,GCSFileSystem,GCSHandler,Github,GithubHandler,HDFSHandler"
---

# papermill — package

## Install

```bash
pip install papermill
```

## Imports

```python
import papermill
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `PapermillException` | Class | Raised when an exception is encountered when operating on a notebook. |
| `PapermillExecutionError` | Class | Raised when an exception is encountered in a notebook. |
| `execute_notebook` | Function | Executes a single notebook locally.  Parameters ---------- input_path : str or… |
| `inspect_notebook` | Function | Return the inferred notebook parameters.  Parameters ---------- notebook_path :… |
| `NoDatesSafeLoader` | Class |  |
| `add_constructor` | Method |  |
| `add_implicit_resolver` | Method |  |
| `add_indent` | Method |  |
| `add_multi_constructor` | Method |  |
| `add_path_resolver` | Method |  |
| `ascend_resolver` | Method |  |
| `check_block_entry` | Method |  |
| `check_data` | Method |  |
| `check_directive` | Method |  |
| `check_document_end` | Method |  |
| `check_document_start` | Method |  |
| `check_event` | Method |  |
| `check_key` | Method |  |
| `check_node` | Method |  |
| `check_plain` | Method |  |
| `check_printable` | Method |  |
| `check_resolver_prefix` | Method |  |
| `check_state_key` | Method | Block special attributes/methods from being set in a newly created object, to p… |
| `check_token` | Method |  |
| `check_value` | Method |  |
| `compose_document` | Method |  |
| `compose_mapping_node` | Method |  |
| `compose_node` | Method |  |
| `compose_scalar_node` | Method |  |
| `compose_sequence_node` | Method |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `PapermillException`

Raised when an exception is encountered when operating on a notebook.

```python
papermill.PapermillException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillExecutionError`

Raised when an exception is encountered in a notebook.

```python
papermill.PapermillExecutionError(self, cell_index, exec_count, source, ename, evalue, traceback)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell_index` | `—` | `—` | pos/kw |
| `exec_count` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `ename` | `—` | `—` | pos/kw |
| `evalue` | `—` | `—` | pos/kw |
| `traceback` | `—` | `—` | pos/kw |

### `NoDatesSafeLoader`

```python
papermill.cli.NoDatesSafeLoader(self, stream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stream` | `—` | `—` | pos/kw |

### `PapermillNotebookClient`

Module containing a  that executes the code cells
and updates outputs

```python
papermill.clientwrap.PapermillNotebookClient(self, nb_man, km=None, raise_on_iopub_timeout=True, **kw)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_man` | `—` | `—` | pos/kw |
| `km` | `—` | `None` | pos/kw |
| `raise_on_iopub_timeout` | `—` | `True` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

### `Engine`

Base class for engines.

Other specific engine classes should inherit and implement the
`execute_managed_notebook` method.

Defines `execute_notebook` method which is used to correctly setup
the `Not…

```python
papermill.engines.Engine(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NBClientEngine`

A notebook engine representing an nbclient process.

This can execute a notebook document and update the `nb_man.nb` object with
the results.

```python
papermill.engines.NBClientEngine(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NotebookExecutionManager`

Wrapper for execution state of a notebook.

This class is a wrapper for notebook objects to house execution state
related to the notebook being run through an engine.

In particular the NotebookExecu…

```python
papermill.engines.NotebookExecutionManager(self, nb, output_path=None, log_output=False, progress_bar=True, autosave_cell_every=30)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `output_path` | `—` | `None` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `progress_bar` | `—` | `True` | pos/kw |
| `autosave_cell_every` | `—` | `30` | pos/kw |

### `PapermillEngines`

The holder which houses any engine registered with the system.

This object is used in a singleton manner to save and load particular
named Engine objects so they may be referenced externally.

```python
papermill.engines.PapermillEngines(self)
```

### `PapermillException`

Raised when an exception is encountered when operating on a notebook.

```python
papermill.engines.PapermillException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillNotebookClient`

Module containing a  that executes the code cells
and updates outputs

```python
papermill.engines.PapermillNotebookClient(self, nb_man, km=None, raise_on_iopub_timeout=True, **kw)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_man` | `—` | `—` | pos/kw |
| `km` | `—` | `None` | pos/kw |
| `raise_on_iopub_timeout` | `—` | `True` | pos/kw |
| `kw` | `—` | `—` | **kwargs |

### `AwsError`

Raised when an AWS Exception is encountered.

```python
papermill.exceptions.AwsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FileExistsError`

Raised when a File already exists on S3.

```python
papermill.exceptions.FileExistsError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillException`

Raised when an exception is encountered when operating on a notebook.

```python
papermill.exceptions.PapermillException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillExecutionError`

Raised when an exception is encountered in a notebook.

```python
papermill.exceptions.PapermillExecutionError(self, cell_index, exec_count, source, ename, evalue, traceback)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell_index` | `—` | `—` | pos/kw |
| `exec_count` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `ename` | `—` | `—` | pos/kw |
| `evalue` | `—` | `—` | pos/kw |
| `traceback` | `—` | `—` | pos/kw |

### `PapermillMissingParameterException`

Raised when a parameter without a value is required to operate on a notebook.

```python
papermill.exceptions.PapermillMissingParameterException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillOptionalDependencyException`

Raised when an exception is encountered when an optional plugin is missing.

```python
papermill.exceptions.PapermillOptionalDependencyException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillParameterOverwriteWarning`

Callee overwrites caller argument to pass down the stream.

```python
papermill.exceptions.PapermillParameterOverwriteWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillRateLimitException`

Raised when an io request has been rate limited

```python
papermill.exceptions.PapermillRateLimitException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillWarning`

Base warning for papermill.

```python
papermill.exceptions.PapermillWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PapermillExecutionError`

Raised when an exception is encountered in a notebook.

```python
papermill.execute.PapermillExecutionError(self, cell_index, exec_count, source, ename, evalue, traceback)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cell_index` | `—` | `—` | pos/kw |
| `exec_count` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `ename` | `—` | `—` | pos/kw |
| `evalue` | `—` | `—` | pos/kw |
| `traceback` | `—` | `—` | pos/kw |

### `ABSHandler`

```python
papermill.iorw.ABSHandler(self)
```

### `ADLHandler`

```python
papermill.iorw.ADLHandler(self)
```

### `GCSHandler`

```python
papermill.iorw.GCSHandler(self)
```

### `GithubHandler`

```python
papermill.iorw.GithubHandler(self)
```

### `HDFSHandler`

```python
papermill.iorw.HDFSHandler(self)
```

## Functions

### `execute_notebook`

Executes a single notebook locally.

Parameters
----------
input_path : str or Path or nbformat.NotebookNode
    Path to input notebook or NotebookNode object of notebook
output_path : str or Path or…

```python
papermill.execute_notebook(input_path, output_path, parameters=None, engine_name=None, request_save_on_cell_execute=True, prepare_only=False, kernel_name=None, language=None, progress_bar=True, log_output=False, stdout_file=None, stderr_file=None, start_timeout=60, report_mode=False, cwd=None, **engine_kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `input_path` | `—` | `—` | pos/kw |
| `output_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `None` | pos/kw |
| `engine_name` | `—` | `None` | pos/kw |
| `request_save_on_cell_execute` | `—` | `True` | pos/kw |
| `prepare_only` | `—` | `False` | pos/kw |
| `kernel_name` | `—` | `None` | pos/kw |
| `language` | `—` | `None` | pos/kw |
| `progress_bar` | `—` | `True` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `stdout_file` | `—` | `None` | pos/kw |
| `stderr_file` | `—` | `None` | pos/kw |
| `start_timeout` | `—` | `60` | pos/kw |
| `report_mode` | `—` | `False` | pos/kw |
| `cwd` | `—` | `None` | pos/kw |
| `engine_kwargs` | `—` | `—` | **kwargs |

### `inspect_notebook`

Return the inferred notebook parameters.

Parameters
----------
notebook_path : str or Path
    Path to notebook
parameters : dict, optional
    Arbitrary keyword arguments to pass to the notebook pa…

```python
papermill.inspect_notebook(notebook_path, parameters=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `notebook_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `None` | pos/kw |

### `display_notebook_help`

Display help on notebook parameters.

Parameters
----------
ctx : click.Context
    Click context
notebook_path : str
    Path to the notebook to be inspected

```python
papermill.cli.display_notebook_help(ctx, notebook_path, parameters)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |
| `notebook_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `—` | pos/kw |

### `execute_notebook`

Executes a single notebook locally.

Parameters
----------
input_path : str or Path or nbformat.NotebookNode
    Path to input notebook or NotebookNode object of notebook
output_path : str or Path or…

```python
papermill.cli.execute_notebook(input_path, output_path, parameters=None, engine_name=None, request_save_on_cell_execute=True, prepare_only=False, kernel_name=None, language=None, progress_bar=True, log_output=False, stdout_file=None, stderr_file=None, start_timeout=60, report_mode=False, cwd=None, **engine_kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `input_path` | `—` | `—` | pos/kw |
| `output_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `None` | pos/kw |
| `engine_name` | `—` | `None` | pos/kw |
| `request_save_on_cell_execute` | `—` | `True` | pos/kw |
| `prepare_only` | `—` | `False` | pos/kw |
| `kernel_name` | `—` | `None` | pos/kw |
| `language` | `—` | `None` | pos/kw |
| `progress_bar` | `—` | `True` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `stdout_file` | `—` | `None` | pos/kw |
| `stderr_file` | `—` | `None` | pos/kw |
| `start_timeout` | `—` | `60` | pos/kw |
| `report_mode` | `—` | `False` | pos/kw |
| `cwd` | `—` | `None` | pos/kw |
| `engine_kwargs` | `—` | `—` | **kwargs |

### `print_papermill_version`

```python
papermill.cli.print_papermill_version(ctx, param, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |
| `param` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `read_yaml_file`

Reads a YAML file from the location specified at 'path'.

```python
papermill.cli.read_yaml_file(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `catch_nb_assignment`

Wrapper to catch `nb` keyword arguments

This helps catch `nb` keyword arguments and assign onto self when passed to
the wrapped function.

Used for callback methods when the caller may optionally ha…

```python
papermill.engines.catch_nb_assignment(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `merge_kwargs`

Merge named argument.

Function takes a dictionary of caller arguments and callee arguments as keyword arguments
Returns a dictionary with merged arguments. If same argument is in both caller and cal…

```python
papermill.engines.merge_kwargs(caller_args, **callee_args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `caller_args` | `—` | `—` | pos/kw |
| `callee_args` | `—` | `—` | **kwargs |

### `nb_kernel_name`

Helper for fetching out the kernel name from a notebook object.

Parameters
----------
nb : nbformat.NotebookNode
    The notebook to introspect
name : str
    A provided name field

Returns
-------…

```python
papermill.engines.nb_kernel_name(nb, name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

### `nb_language`

Helper for fetching out the programming language from a notebook object.

Parameters
----------
nb : nbformat.NotebookNode
    The notebook to introspect
language : str
    A provided language field…

```python
papermill.engines.nb_language(nb, language=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `language` | `—` | `None` | pos/kw |

### `remove_args`

Remove arguments from kwargs.

Parameters
----------
args : list
    Argument names to remove from kwargs
**kwargs
    Arbitrary keyword arguments

Returns
-------
kwargs : dict
   New dictionary of…

```python
papermill.engines.remove_args(args=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `write_ipynb`

Saves a notebook object to the specified path.
Args:
    nb_node (nbformat.NotebookNode): Notebook object to save.
    notebook_path (str): Path to save the notebook object to.

```python
papermill.engines.write_ipynb(nb, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `missing_dependency_generator`

```python
papermill.exceptions.missing_dependency_generator(package, dep)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `package` | `—` | `—` | pos/kw |
| `dep` | `—` | `—` | pos/kw |

### `missing_environment_variable_generator`

```python
papermill.exceptions.missing_environment_variable_generator(package, env_key)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `package` | `—` | `—` | pos/kw |
| `env_key` | `—` | `—` | pos/kw |

### `strip_color`

Remove most ANSI color and style sequences from a string

Based on https://pypi.org/project/ansicolors/.

```python
papermill.exceptions.strip_color(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `add_builtin_parameters`

Add built-in parameters to a dictionary of parameters

Parameters
----------
parameters : dict
   Dictionary of parameters provided by the user

```python
papermill.execute.add_builtin_parameters(parameters)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parameters` | `—` | `—` | pos/kw |

### `chdir`

Change working directory to `path` and restore old path on exit.

`path` can be `None` in which case this is a no-op.

```python
papermill.execute.chdir(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `execute_notebook`

Executes a single notebook locally.

Parameters
----------
input_path : str or Path or nbformat.NotebookNode
    Path to input notebook or NotebookNode object of notebook
output_path : str or Path or…

```python
papermill.execute.execute_notebook(input_path, output_path, parameters=None, engine_name=None, request_save_on_cell_execute=True, prepare_only=False, kernel_name=None, language=None, progress_bar=True, log_output=False, stdout_file=None, stderr_file=None, start_timeout=60, report_mode=False, cwd=None, **engine_kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `input_path` | `—` | `—` | pos/kw |
| `output_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `None` | pos/kw |
| `engine_name` | `—` | `None` | pos/kw |
| `request_save_on_cell_execute` | `—` | `True` | pos/kw |
| `prepare_only` | `—` | `False` | pos/kw |
| `kernel_name` | `—` | `None` | pos/kw |
| `language` | `—` | `None` | pos/kw |
| `progress_bar` | `—` | `True` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `stdout_file` | `—` | `None` | pos/kw |
| `stderr_file` | `—` | `None` | pos/kw |
| `start_timeout` | `—` | `60` | pos/kw |
| `report_mode` | `—` | `False` | pos/kw |
| `cwd` | `—` | `None` | pos/kw |
| `engine_kwargs` | `—` | `—` | **kwargs |

### `get_pretty_path`

```python
papermill.execute.get_pretty_path(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `load_notebook_node`

Returns a notebook object with papermill metadata loaded from the specified path.

Args:
    notebook_path (str): Path to the notebook file.

Returns:
    nbformat.NotebookNode

```python
papermill.execute.load_notebook_node(notebook_path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `notebook_path` | `—` | `—` | pos/kw |

### `local_file_io_cwd`

```python
papermill.execute.local_file_io_cwd(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `parameterize_notebook`

Assigned parameters into the appropriate place in the input notebook

Parameters
----------
nb : NotebookNode
   Executable notebook object
parameters : dict
   Arbitrary keyword arguments to pass as…

```python
papermill.execute.parameterize_notebook(nb, parameters, report_mode=False, comment='Parameters', kernel_name=None, language=None, engine_name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `parameters` | `—` | `—` | pos/kw |
| `report_mode` | `—` | `False` | pos/kw |
| `comment` | `—` | `'Parameters'` | pos/kw |
| `kernel_name` | `—` | `None` | pos/kw |
| `language` | `—` | `None` | pos/kw |
| `engine_name` | `—` | `None` | pos/kw |

### `parameterize_path`

Format a path with a provided dictionary of parameters

Parameters
----------
path : string or nbformat.NotebookNode or None
   Path with optional parameters, as a python format string. If path is a…

```python
papermill.execute.parameterize_path(path, parameters)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `—` | pos/kw |

### `prepare_notebook_metadata`

Prepare metadata associated with a notebook and its cells

Parameters
----------
nb : NotebookNode
   Executable notebook object
input_path : str
    Path to input notebook
output_path : str
   Path…

```python
papermill.execute.prepare_notebook_metadata(nb, input_path, output_path, report_mode=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `input_path` | `—` | `—` | pos/kw |
| `output_path` | `—` | `—` | pos/kw |
| `report_mode` | `—` | `False` | pos/kw |

### `raise_for_execution_errors`

Assigned parameters into the appropriate place in the input notebook

Parameters
----------
nb : NotebookNode
   Executable notebook object
output_path : str
   Path to write executed notebook

```python
papermill.execute.raise_for_execution_errors(nb, output_path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `output_path` | `—` | `—` | pos/kw |

### `remove_error_markers`

```python
papermill.execute.remove_error_markers(nb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |

### `write_ipynb`

Saves a notebook object to the specified path.
Args:
    nb_node (nbformat.NotebookNode): Notebook object to save.
    notebook_path (str): Path to save the notebook object to.

```python
papermill.execute.write_ipynb(nb, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `add_builtin_parameters`

Add built-in parameters to a dictionary of parameters

Parameters
----------
parameters : dict
   Dictionary of parameters provided by the user

```python
papermill.inspection.add_builtin_parameters(parameters)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parameters` | `—` | `—` | pos/kw |

### `any_tagged_cell`

Whether the notebook contains at least one cell tagged ``tag``?

Parameters
----------
nb : nbformat.NotebookNode
    The notebook to introspect
tag : str
    The tag to look for

Returns
-------
boo…

```python
papermill.inspection.any_tagged_cell(nb, tag)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `tag` | `—` | `—` | pos/kw |

### `display_notebook_help`

Display help on notebook parameters.

Parameters
----------
ctx : click.Context
    Click context
notebook_path : str
    Path to the notebook to be inspected

```python
papermill.inspection.display_notebook_help(ctx, notebook_path, parameters)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |
| `notebook_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `—` | pos/kw |

### `find_first_tagged_cell_index`

Find the first tagged cell ``tag`` in the notebook.

Parameters
----------
nb : nbformat.NotebookNode
    The notebook to introspect
tag : str
    The tag to look for

Returns
-------
nbformat.Notebo…

```python
papermill.inspection.find_first_tagged_cell_index(nb, tag)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `tag` | `—` | `—` | pos/kw |

### `get_pretty_path`

```python
papermill.inspection.get_pretty_path(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `inspect_notebook`

Return the inferred notebook parameters.

Parameters
----------
notebook_path : str or Path
    Path to notebook
parameters : dict, optional
    Arbitrary keyword arguments to pass to the notebook pa…

```python
papermill.inspection.inspect_notebook(notebook_path, parameters=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `notebook_path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `None` | pos/kw |

### `load_notebook_node`

Returns a notebook object with papermill metadata loaded from the specified path.

Args:
    notebook_path (str): Path to the notebook file.

Returns:
    nbformat.NotebookNode

```python
papermill.inspection.load_notebook_node(notebook_path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `notebook_path` | `—` | `—` | pos/kw |

### `local_file_io_cwd`

```python
papermill.inspection.local_file_io_cwd(path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `None` | pos/kw |

### `nb_kernel_name`

Helper for fetching out the kernel name from a notebook object.

Parameters
----------
nb : nbformat.NotebookNode
    The notebook to introspect
name : str
    A provided name field

Returns
-------…

```python
papermill.inspection.nb_kernel_name(nb, name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

### `nb_language`

Helper for fetching out the programming language from a notebook object.

Parameters
----------
nb : nbformat.NotebookNode
    The notebook to introspect
language : str
    A provided language field…

```python
papermill.inspection.nb_language(nb, language=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `language` | `—` | `None` | pos/kw |

### `parameterize_path`

Format a path with a provided dictionary of parameters

Parameters
----------
path : string or nbformat.NotebookNode or None
   Path with optional parameters, as a python format string. If path is a…

```python
papermill.inspection.parameterize_path(path, parameters)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `parameters` | `—` | `—` | pos/kw |

### `ADL`

```python
papermill.iorw.ADL()
```

### `AzureBlobStore`

```python
papermill.iorw.AzureBlobStore()
```

### `GCSFileSystem`

```python
papermill.iorw.GCSFileSystem()
```

### `Github`

```python
papermill.iorw.Github()
```

## Methods

### `papermill.cli.NoDatesSafeLoader` methods

### `add_constructor`

```python
papermill.cli.NoDatesSafeLoader.add_constructor(tag, constructor)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag` | `—` | `—` | pos/kw |
| `constructor` | `—` | `—` | pos/kw |

### `add_implicit_resolver`

```python
papermill.cli.NoDatesSafeLoader.add_implicit_resolver(tag, regexp, first)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag` | `—` | `—` | pos/kw |
| `regexp` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |

### `add_indent`

```python
papermill.cli.NoDatesSafeLoader.add_indent(self, column)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `column` | `—` | `—` | pos/kw |

### `add_multi_constructor`

```python
papermill.cli.NoDatesSafeLoader.add_multi_constructor(tag_prefix, multi_constructor)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag_prefix` | `—` | `—` | pos/kw |
| `multi_constructor` | `—` | `—` | pos/kw |

### `add_path_resolver`

```python
papermill.cli.NoDatesSafeLoader.add_path_resolver(tag, path, kind=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `kind` | `—` | `None` | pos/kw |

### `ascend_resolver`

```python
papermill.cli.NoDatesSafeLoader.ascend_resolver(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_block_entry`

```python
papermill.cli.NoDatesSafeLoader.check_block_entry(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_data`

```python
papermill.cli.NoDatesSafeLoader.check_data(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_directive`

```python
papermill.cli.NoDatesSafeLoader.check_directive(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_document_end`

```python
papermill.cli.NoDatesSafeLoader.check_document_end(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_document_start`

```python
papermill.cli.NoDatesSafeLoader.check_document_start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_event`

```python
papermill.cli.NoDatesSafeLoader.check_event(self, *choices)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `choices` | `—` | `—` | *args |

### `check_key`

```python
papermill.cli.NoDatesSafeLoader.check_key(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_node`

```python
papermill.cli.NoDatesSafeLoader.check_node(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_plain`

```python
papermill.cli.NoDatesSafeLoader.check_plain(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `check_printable`

```python
papermill.cli.NoDatesSafeLoader.check_printable(self, data)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |

### `check_resolver_prefix`

```python
papermill.cli.NoDatesSafeLoader.check_resolver_prefix(self, depth, path, kind, current_node, current_index)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `depth` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `kind` | `—` | `—` | pos/kw |
| `current_node` | `—` | `—` | pos/kw |
| `current_index` | `—` | `—` | pos/kw |

### `check_state_key`

Block special attributes/methods from being set in a newly created
object, to prevent user-controlled methods from being called during
deserialization

```python
papermill.cli.NoDatesSafeLoader.check_state_key(self, key)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |

### `check_token`

```python
papermill.cli.NoDatesSafeLoader.check_token(self, *choices)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `choices` | `—` | `—` | *args |

### `check_value`

```python
papermill.cli.NoDatesSafeLoader.check_value(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compose_document`

```python
papermill.cli.NoDatesSafeLoader.compose_document(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compose_mapping_node`

```python
papermill.cli.NoDatesSafeLoader.compose_mapping_node(self, anchor)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `anchor` | `—` | `—` | pos/kw |

### `compose_node`

```python
papermill.cli.NoDatesSafeLoader.compose_node(self, parent, index)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parent` | `—` | `—` | pos/kw |
| `index` | `—` | `—` | pos/kw |

### `compose_scalar_node`

```python
papermill.cli.NoDatesSafeLoader.compose_scalar_node(self, anchor)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `anchor` | `—` | `—` | pos/kw |

### `compose_sequence_node`

```python
papermill.cli.NoDatesSafeLoader.compose_sequence_node(self, anchor)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `anchor` | `—` | `—` | pos/kw |

### `construct_document`

```python
papermill.cli.NoDatesSafeLoader.construct_document(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `construct_mapping`

```python
papermill.cli.NoDatesSafeLoader.construct_mapping(self, node, deep=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |
| `deep` | `—` | `False` | pos/kw |

### `construct_object`

```python
papermill.cli.NoDatesSafeLoader.construct_object(self, node, deep=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |
| `deep` | `—` | `False` | pos/kw |

### `construct_pairs`

```python
papermill.cli.NoDatesSafeLoader.construct_pairs(self, node, deep=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |
| `deep` | `—` | `False` | pos/kw |

### `construct_scalar`

```python
papermill.cli.NoDatesSafeLoader.construct_scalar(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `papermill.clientwrap.PapermillNotebookClient` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
papermill.clientwrap.PapermillNotebookClient.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `async_execute`

Executes each code cell.

Parameters
----------
kwargs :
    Any option for ``self.kernel_manager_class.start_kernel()``. Because
    that defaults to AsyncKernelManager, this will likely include opt…

```python
papermill.clientwrap.PapermillNotebookClient.async_execute(self, reset_kc: 'bool' = False, **kwargs: 't.Any') -> 'NotebookNode'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reset_kc` | `bool` | `False` | pos/kw |
| `kwargs` | `t.Any` | `—` | **kwargs |

**Returns:** `NotebookNode`

### `async_execute_cell`

Executes a single code cell.

To execute all cells see :meth:`execute`.

Parameters
----------
cell : nbformat.NotebookNode
    The cell which is currently being processed.
cell_index : int
    The p…

```python
papermill.clientwrap.PapermillNotebookClient.async_execute_cell(self, cell: 'NotebookNode', cell_index: 'int', execution_count: 'int | None' = None, store_history: 'bool' = True) -> 'NotebookNode'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `NotebookNode` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |
| `execution_count` | `int \| None` | `None` | pos/kw |
| `store_history` | `bool` | `True` | pos/kw |

**Returns:** `NotebookNode`

### `async_setup_kernel`

Context manager for setting up the kernel to execute a notebook.

This assigns the Kernel Manager (``self.km``) if missing and Kernel Client(``self.kc``).

When control returns from the yield it stop…

```python
papermill.clientwrap.PapermillNotebookClient.async_setup_kernel(self, **kwargs: 't.Any') -> 't.AsyncGenerator[None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `t.Any` | `—` | **kwargs |

**Returns:** `t.AsyncGenerator[None, None]`

### `async_start_new_kernel`

Creates a new kernel.

Parameters
----------
kwargs :
    Any options for ``self.kernel_manager_class.start_kernel()``. Because
    that defaults to AsyncKernelManager, this will likely include optio…

```python
papermill.clientwrap.PapermillNotebookClient.async_start_new_kernel(self, **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `t.Any` | `—` | **kwargs |

### `async_start_new_kernel_client`

Creates a new kernel client.

Returns
-------
kc : KernelClient
    Kernel client as created by the kernel manager ``km``.

```python
papermill.clientwrap.PapermillNotebookClient.async_start_new_kernel_client(self) -> 'KernelClient'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `KernelClient`

### `async_wait_for_reply`

Wait for a message reply.

```python
papermill.clientwrap.PapermillNotebookClient.async_wait_for_reply(self, msg_id: 'str', cell: 'NotebookNode | None' = None) -> 'dict[str, t.Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg_id` | `str` | `—` | pos/kw |
| `cell` | `NotebookNode \| None` | `None` | pos/kw |

**Returns:** `dict[str, t.Any] | None`

### `class_config_rst_doc`

Generate rST documentation for this class' config options.

Excludes traits defined on parent classes.

```python
papermill.clientwrap.PapermillNotebookClient.class_config_rst_doc() -> 'str'
```

**Returns:** `str`

### `class_config_section`

Get the config section for this class.

Parameters
----------
classes : list, optional
    The list of other classes in the config file.
    Used to reduce redundant information.

```python
papermill.clientwrap.PapermillNotebookClient.class_config_section(classes: 't.Sequence[type[HasTraits]] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classes` | `t.Sequence[type[HasTraits]] \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_help`

Get the help string for this class in ReST format.

If `inst` is given, its current trait values will be used in place of
class defaults.

```python
papermill.clientwrap.PapermillNotebookClient.class_get_help(inst: 'HasTraits | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_trait_help`

Get the helptext string for a single trait.

:param inst:
    If given, its current trait values will be used in place of
    the class default.
:param helptext:
    If not given, uses the `help` att…

```python
papermill.clientwrap.PapermillNotebookClient.class_get_trait_help(trait: 'TraitType[t.Any, t.Any]', inst: 'HasTraits | None' = None, helptext: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `trait` | `TraitType[t.Any, t.Any]` | `—` | pos/kw |
| `inst` | `HasTraits \| None` | `None` | pos/kw |
| `helptext` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
papermill.clientwrap.PapermillNotebookClient.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
papermill.clientwrap.PapermillNotebookClient.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_print_help`

Get the help string for a single trait and print it.

```python
papermill.clientwrap.PapermillNotebookClient.class_print_help(inst: 'HasTraits | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
papermill.clientwrap.PapermillNotebookClient.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
papermill.clientwrap.PapermillNotebookClient.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `clear_display_id_mapping`

Clear a display id mapping for a cell.

```python
papermill.clientwrap.PapermillNotebookClient.clear_display_id_mapping(self, cell_index: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

### `clear_output`

Clear output.

```python
papermill.clientwrap.PapermillNotebookClient.clear_output(self, outs: 'list[NotebookNode]', msg: 'dict[str, t.Any]', cell_index: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outs` | `list[NotebookNode]` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

### `create_kernel_manager`

Creates a new kernel manager.

Returns
-------
km : KernelManager
    Kernel manager whose client class is asynchronous.

```python
papermill.clientwrap.PapermillNotebookClient.create_kernel_manager(self) -> 'KernelManager'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `KernelManager`

### `execute`

Wraps the parent class process call slightly

```python
papermill.clientwrap.PapermillNotebookClient.execute(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `execute_cell`

Executes a single code cell.

To execute all cells see :meth:`execute`.

Parameters
----------
cell : nbformat.NotebookNode
    The cell which is currently being processed.
cell_index : int
    The p…

```python
papermill.clientwrap.PapermillNotebookClient.execute_cell(*args: 'Any', **kwargs: 'Any') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Any`

### `handle_comm_msg`

Handle a comm message.

```python
papermill.clientwrap.PapermillNotebookClient.handle_comm_msg(self, outs: 'list[NotebookNode]', msg: 'dict[str, t.Any]', cell_index: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outs` | `list[NotebookNode]` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
papermill.clientwrap.PapermillNotebookClient.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `hold_trait_notifications`

Context manager for bundling trait change notifications and cross
validation.

Use this when doing multiple trait assignments (init, config), to avoid
race conditions in trait notifiers requesting ot…

```python
papermill.clientwrap.PapermillNotebookClient.hold_trait_notifications(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `log_output_message`

Process a given output. May log it in the configured logger and/or write it into
the configured stdout/stderr files.

:param output: nbformat.notebooknode.NotebookNode
:return:

```python
papermill.clientwrap.PapermillNotebookClient.log_output_message(self, output)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `output` | `—` | `—` | pos/kw |

### `notify_change`

Notify observers of a change event

```python
papermill.clientwrap.PapermillNotebookClient.notify_change(self, change: 'Bunch') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `change` | `Bunch` | `—` | pos/kw |

### `observe`

Setup a handler to be called when a trait changes.

This is used to setup dynamic notifications of trait changes.

Parameters
----------
handler : callable
    A callable that is called when a trait…

```python
papermill.clientwrap.PapermillNotebookClient.observe(self, handler: 't.Callable[..., t.Any]', names: 'Sentinel | str | t.Iterable[Sentinel | str]' = traitlets.All, type: 'Sentinel | str' = 'change') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `t.Callable[..., t.Any]` | `—` | pos/kw |
| `names` | `Sentinel \| str \| t.Iterable[Sentinel \| str]` | `traitlets.All` | pos/kw |
| `type` | `Sentinel \| str` | `'change'` | pos/kw |

### `on_comm_open_jupyter_widget`

Handle a jupyter widget comm open.

```python
papermill.clientwrap.PapermillNotebookClient.on_comm_open_jupyter_widget(self, msg: 'dict[str, t.Any]') -> 't.Any | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |

**Returns:** `t.Any | None`

### `on_trait_change`

DEPRECATED: Setup a handler to be called when a trait changes.

This is used to setup dynamic notifications of trait changes.

Static handlers can be created by creating methods on a HasTraits
subcla…

```python
papermill.clientwrap.PapermillNotebookClient.on_trait_change(self, handler: 'EventHandler | None' = None, name: 'Sentinel | str | None' = None, remove: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `EventHandler \| None` | `None` | pos/kw |
| `name` | `Sentinel \| str \| None` | `None` | pos/kw |
| `remove` | `bool` | `False` | pos/kw |

### `output`

Handle output.

```python
papermill.clientwrap.PapermillNotebookClient.output(self, outs: 'list[NotebookNode]', msg: 'dict[str, t.Any]', display_id: 'str | None', cell_index: 'int') -> 'NotebookNode | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outs` | `list[NotebookNode]` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |
| `display_id` | `str \| None` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

**Returns:** `NotebookNode | None`

### `papermill.engines.Engine` methods

### `execute_managed_notebook`

An abstract method where implementation will be defined in a subclass.

```python
papermill.engines.Engine.execute_managed_notebook(nb_man, kernel_name, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_man` | `—` | `—` | pos/kw |
| `kernel_name` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `execute_notebook`

A wrapper to handle notebook execution tasks.

Wraps the notebook object in a `NotebookExecutionManager` in order to track
execution state in a uniform manner. This is meant to help simplify
engine i…

```python
papermill.engines.Engine.execute_notebook(nb, kernel_name, output_path=None, progress_bar=True, log_output=False, autosave_cell_every=30, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `kernel_name` | `—` | `—` | pos/kw |
| `output_path` | `—` | `None` | pos/kw |
| `progress_bar` | `—` | `True` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `autosave_cell_every` | `—` | `30` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `nb_kernel_name`

Use default implementation to fetch kernel name from the notebook object

```python
papermill.engines.Engine.nb_kernel_name(nb, name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

### `nb_language`

Use default implementation to fetch programming language from the notebook object

```python
papermill.engines.Engine.nb_language(nb, language=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `language` | `—` | `None` | pos/kw |

### `papermill.engines.NBClientEngine` methods

### `execute_managed_notebook`

Performs the actual execution of the parameterized notebook locally.

Args:
    nb_man (NotebookExecutionManager): Wrapper for execution state of a notebook.
    kernel_name (str): Name of kernel to…

```python
papermill.engines.NBClientEngine.execute_managed_notebook(nb_man, kernel_name, log_output=False, stdout_file=None, stderr_file=None, start_timeout=60, execution_timeout=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb_man` | `—` | `—` | pos/kw |
| `kernel_name` | `—` | `—` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `stdout_file` | `—` | `None` | pos/kw |
| `stderr_file` | `—` | `None` | pos/kw |
| `start_timeout` | `—` | `60` | pos/kw |
| `execution_timeout` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `execute_notebook`

A wrapper to handle notebook execution tasks.

Wraps the notebook object in a `NotebookExecutionManager` in order to track
execution state in a uniform manner. This is meant to help simplify
engine i…

```python
papermill.engines.NBClientEngine.execute_notebook(nb, kernel_name, output_path=None, progress_bar=True, log_output=False, autosave_cell_every=30, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `kernel_name` | `—` | `—` | pos/kw |
| `output_path` | `—` | `None` | pos/kw |
| `progress_bar` | `—` | `True` | pos/kw |
| `log_output` | `—` | `False` | pos/kw |
| `autosave_cell_every` | `—` | `30` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `nb_kernel_name`

Use default implementation to fetch kernel name from the notebook object

```python
papermill.engines.NBClientEngine.nb_kernel_name(nb, name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

### `nb_language`

Use default implementation to fetch programming language from the notebook object

```python
papermill.engines.NBClientEngine.nb_language(nb, language=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nb` | `—` | `—` | pos/kw |
| `language` | `—` | `None` | pos/kw |

### `papermill.engines.NotebookExecutionManager` methods

### `autosave_cell`

Saves the notebook if it's been more than self.autosave_cell_every seconds
since it was last saved.

```python
papermill.engines.NotebookExecutionManager.autosave_cell(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cell_complete`

Finalize metadata for a cell and save notebook.

Optionally called by engines during execution to finalize the
metadata for a cell and save the notebook to the output path.

```python
papermill.engines.NotebookExecutionManager.cell_complete(self, cell, cell_index=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |
| `cell_index` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `cell_exception`

Set metadata when an exception is raised.

Called by engines when an exception is raised within a notebook to
set the metadata on the notebook indicating the location of the
failure.

```python
papermill.engines.NotebookExecutionManager.cell_exception(self, cell, cell_index=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |
| `cell_index` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `cell_start`

Set and save a cell's start state.

Optionally called by engines during execution to initialize the
metadata for a cell and save the notebook to the output path.

```python
papermill.engines.NotebookExecutionManager.cell_start(self, cell, cell_index=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |
| `cell_index` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `cleanup_pbar`

Clean up a progress bar

```python
papermill.engines.NotebookExecutionManager.cleanup_pbar(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `complete_pbar`

Refresh progress bar

```python
papermill.engines.NotebookExecutionManager.complete_pbar(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_cell_description`

Fetches cell description if present

```python
papermill.engines.NotebookExecutionManager.get_cell_description(self, cell, escape_str='papermill_description=')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `—` | `—` | pos/kw |
| `escape_str` | `—` | `'papermill_description='` | pos/kw |

### `notebook_complete`

Finalize the metadata for a notebook and save the notebook to
the output path.

Called by Engine when execution concludes, regardless of exceptions.

```python
papermill.engines.NotebookExecutionManager.notebook_complete(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `notebook_start`

Initialize a notebook, clearing its metadata, and save it.

When starting a notebook, this initializes and clears the metadata for
the notebook and its cells, and saves the notebook to the given
outp…

```python
papermill.engines.NotebookExecutionManager.notebook_start(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `now`

Helper to return current UTC time

```python
papermill.engines.NotebookExecutionManager.now(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `save`

Saves the wrapped notebook state.

If an output path is known, this triggers a save of the wrapped
notebook state to the provided path.

Can be used outside of cell state changes if execution is taki…

```python
papermill.engines.NotebookExecutionManager.save(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `set_timer`

Initializes the execution timer for the notebook.

This is called automatically when a NotebookExecutionManager is
constructed.

```python
papermill.engines.NotebookExecutionManager.set_timer(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `papermill.engines.PapermillEngines` methods

### `execute_notebook_with_engine`

Fetch a named engine and execute the nb object against it.

```python
papermill.engines.PapermillEngines.execute_notebook_with_engine(self, engine_name, nb, kernel_name, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `engine_name` | `—` | `—` | pos/kw |
| `nb` | `—` | `—` | pos/kw |
| `kernel_name` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `get_engine`

Retrieves an engine by name.

```python
papermill.engines.PapermillEngines.get_engine(self, name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

### `nb_kernel_name`

Fetch kernel name from the document by dropping-down into the provided engine.

```python
papermill.engines.PapermillEngines.nb_kernel_name(self, engine_name, nb, name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `engine_name` | `—` | `—` | pos/kw |
| `nb` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

### `nb_language`

Fetch language from the document by dropping-down into the provided engine.

```python
papermill.engines.PapermillEngines.nb_language(self, engine_name, nb, language=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `engine_name` | `—` | `—` | pos/kw |
| `nb` | `—` | `—` | pos/kw |
| `language` | `—` | `None` | pos/kw |

### `register`

Register a named engine

```python
papermill.engines.PapermillEngines.register(self, name, engine)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `engine` | `—` | `—` | pos/kw |

### `register_entry_points`

Register entrypoints for an engine

Load handlers provided by other packages

```python
papermill.engines.PapermillEngines.register_entry_points(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `papermill.engines.PapermillNotebookClient` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
papermill.engines.PapermillNotebookClient.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `async_execute`

Executes each code cell.

Parameters
----------
kwargs :
    Any option for ``self.kernel_manager_class.start_kernel()``. Because
    that defaults to AsyncKernelManager, this will likely include opt…

```python
papermill.engines.PapermillNotebookClient.async_execute(self, reset_kc: 'bool' = False, **kwargs: 't.Any') -> 'NotebookNode'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `reset_kc` | `bool` | `False` | pos/kw |
| `kwargs` | `t.Any` | `—` | **kwargs |

**Returns:** `NotebookNode`

### `async_execute_cell`

Executes a single code cell.

To execute all cells see :meth:`execute`.

Parameters
----------
cell : nbformat.NotebookNode
    The cell which is currently being processed.
cell_index : int
    The p…

```python
papermill.engines.PapermillNotebookClient.async_execute_cell(self, cell: 'NotebookNode', cell_index: 'int', execution_count: 'int | None' = None, store_history: 'bool' = True) -> 'NotebookNode'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell` | `NotebookNode` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |
| `execution_count` | `int \| None` | `None` | pos/kw |
| `store_history` | `bool` | `True` | pos/kw |

**Returns:** `NotebookNode`

### `async_setup_kernel`

Context manager for setting up the kernel to execute a notebook.

This assigns the Kernel Manager (``self.km``) if missing and Kernel Client(``self.kc``).

When control returns from the yield it stop…

```python
papermill.engines.PapermillNotebookClient.async_setup_kernel(self, **kwargs: 't.Any') -> 't.AsyncGenerator[None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `t.Any` | `—` | **kwargs |

**Returns:** `t.AsyncGenerator[None, None]`

### `async_start_new_kernel`

Creates a new kernel.

Parameters
----------
kwargs :
    Any options for ``self.kernel_manager_class.start_kernel()``. Because
    that defaults to AsyncKernelManager, this will likely include optio…

```python
papermill.engines.PapermillNotebookClient.async_start_new_kernel(self, **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `t.Any` | `—` | **kwargs |

### `async_start_new_kernel_client`

Creates a new kernel client.

Returns
-------
kc : KernelClient
    Kernel client as created by the kernel manager ``km``.

```python
papermill.engines.PapermillNotebookClient.async_start_new_kernel_client(self) -> 'KernelClient'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `KernelClient`

### `async_wait_for_reply`

Wait for a message reply.

```python
papermill.engines.PapermillNotebookClient.async_wait_for_reply(self, msg_id: 'str', cell: 'NotebookNode | None' = None) -> 'dict[str, t.Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg_id` | `str` | `—` | pos/kw |
| `cell` | `NotebookNode \| None` | `None` | pos/kw |

**Returns:** `dict[str, t.Any] | None`

### `class_config_rst_doc`

Generate rST documentation for this class' config options.

Excludes traits defined on parent classes.

```python
papermill.engines.PapermillNotebookClient.class_config_rst_doc() -> 'str'
```

**Returns:** `str`

### `class_config_section`

Get the config section for this class.

Parameters
----------
classes : list, optional
    The list of other classes in the config file.
    Used to reduce redundant information.

```python
papermill.engines.PapermillNotebookClient.class_config_section(classes: 't.Sequence[type[HasTraits]] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classes` | `t.Sequence[type[HasTraits]] \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_help`

Get the help string for this class in ReST format.

If `inst` is given, its current trait values will be used in place of
class defaults.

```python
papermill.engines.PapermillNotebookClient.class_get_help(inst: 'HasTraits | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_trait_help`

Get the helptext string for a single trait.

:param inst:
    If given, its current trait values will be used in place of
    the class default.
:param helptext:
    If not given, uses the `help` att…

```python
papermill.engines.PapermillNotebookClient.class_get_trait_help(trait: 'TraitType[t.Any, t.Any]', inst: 'HasTraits | None' = None, helptext: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `trait` | `TraitType[t.Any, t.Any]` | `—` | pos/kw |
| `inst` | `HasTraits \| None` | `None` | pos/kw |
| `helptext` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
papermill.engines.PapermillNotebookClient.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
papermill.engines.PapermillNotebookClient.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_print_help`

Get the help string for a single trait and print it.

```python
papermill.engines.PapermillNotebookClient.class_print_help(inst: 'HasTraits | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
papermill.engines.PapermillNotebookClient.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
papermill.engines.PapermillNotebookClient.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `clear_display_id_mapping`

Clear a display id mapping for a cell.

```python
papermill.engines.PapermillNotebookClient.clear_display_id_mapping(self, cell_index: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

### `clear_output`

Clear output.

```python
papermill.engines.PapermillNotebookClient.clear_output(self, outs: 'list[NotebookNode]', msg: 'dict[str, t.Any]', cell_index: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outs` | `list[NotebookNode]` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

### `create_kernel_manager`

Creates a new kernel manager.

Returns
-------
km : KernelManager
    Kernel manager whose client class is asynchronous.

```python
papermill.engines.PapermillNotebookClient.create_kernel_manager(self) -> 'KernelManager'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `KernelManager`

### `execute`

Wraps the parent class process call slightly

```python
papermill.engines.PapermillNotebookClient.execute(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `execute_cell`

Executes a single code cell.

To execute all cells see :meth:`execute`.

Parameters
----------
cell : nbformat.NotebookNode
    The cell which is currently being processed.
cell_index : int
    The p…

```python
papermill.engines.PapermillNotebookClient.execute_cell(*args: 'Any', **kwargs: 'Any') -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `Any`

### `handle_comm_msg`

Handle a comm message.

```python
papermill.engines.PapermillNotebookClient.handle_comm_msg(self, outs: 'list[NotebookNode]', msg: 'dict[str, t.Any]', cell_index: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outs` | `list[NotebookNode]` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
papermill.engines.PapermillNotebookClient.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `hold_trait_notifications`

Context manager for bundling trait change notifications and cross
validation.

Use this when doing multiple trait assignments (init, config), to avoid
race conditions in trait notifiers requesting ot…

```python
papermill.engines.PapermillNotebookClient.hold_trait_notifications(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `log_output_message`

Process a given output. May log it in the configured logger and/or write it into
the configured stdout/stderr files.

:param output: nbformat.notebooknode.NotebookNode
:return:

```python
papermill.engines.PapermillNotebookClient.log_output_message(self, output)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `output` | `—` | `—` | pos/kw |

### `notify_change`

Notify observers of a change event

```python
papermill.engines.PapermillNotebookClient.notify_change(self, change: 'Bunch') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `change` | `Bunch` | `—` | pos/kw |

### `observe`

Setup a handler to be called when a trait changes.

This is used to setup dynamic notifications of trait changes.

Parameters
----------
handler : callable
    A callable that is called when a trait…

```python
papermill.engines.PapermillNotebookClient.observe(self, handler: 't.Callable[..., t.Any]', names: 'Sentinel | str | t.Iterable[Sentinel | str]' = traitlets.All, type: 'Sentinel | str' = 'change') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `t.Callable[..., t.Any]` | `—` | pos/kw |
| `names` | `Sentinel \| str \| t.Iterable[Sentinel \| str]` | `traitlets.All` | pos/kw |
| `type` | `Sentinel \| str` | `'change'` | pos/kw |

### `on_comm_open_jupyter_widget`

Handle a jupyter widget comm open.

```python
papermill.engines.PapermillNotebookClient.on_comm_open_jupyter_widget(self, msg: 'dict[str, t.Any]') -> 't.Any | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |

**Returns:** `t.Any | None`

### `on_trait_change`

DEPRECATED: Setup a handler to be called when a trait changes.

This is used to setup dynamic notifications of trait changes.

Static handlers can be created by creating methods on a HasTraits
subcla…

```python
papermill.engines.PapermillNotebookClient.on_trait_change(self, handler: 'EventHandler | None' = None, name: 'Sentinel | str | None' = None, remove: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `handler` | `EventHandler \| None` | `None` | pos/kw |
| `name` | `Sentinel \| str \| None` | `None` | pos/kw |
| `remove` | `bool` | `False` | pos/kw |

### `output`

Handle output.

```python
papermill.engines.PapermillNotebookClient.output(self, outs: 'list[NotebookNode]', msg: 'dict[str, t.Any]', display_id: 'str | None', cell_index: 'int') -> 'NotebookNode | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outs` | `list[NotebookNode]` | `—` | pos/kw |
| `msg` | `dict[str, t.Any]` | `—` | pos/kw |
| `display_id` | `str \| None` | `—` | pos/kw |
| `cell_index` | `int` | `—` | pos/kw |

**Returns:** `NotebookNode | None`

### `papermill.iorw.ABSHandler` methods

### `listdir`

```python
papermill.iorw.ABSHandler.listdir(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `pretty_path`

```python
papermill.iorw.ABSHandler.pretty_path(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `read`

```python
papermill.iorw.ABSHandler.read(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `write`

```python
papermill.iorw.ABSHandler.write(self, buf, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `buf` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `papermill.iorw.ADLHandler` methods

### `listdir`

```python
papermill.iorw.ADLHandler.listdir(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `pretty_path`

```python
papermill.iorw.ADLHandler.pretty_path(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `read`

```python
papermill.iorw.ADLHandler.read(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `write`

```python
papermill.iorw.ADLHandler.write(self, buf, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `buf` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `papermill.iorw.GCSHandler` methods

### `listdir`

```python
papermill.iorw.GCSHandler.listdir(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `pretty_path`

```python
papermill.iorw.GCSHandler.pretty_path(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `read`

```python
papermill.iorw.GCSHandler.read(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `write`

```python
papermill.iorw.GCSHandler.write(self, buf, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `buf` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `papermill.iorw.GithubHandler` methods

### `listdir`

```python
papermill.iorw.GithubHandler.listdir(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `pretty_path`

```python
papermill.iorw.GithubHandler.pretty_path(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `read`

```python
papermill.iorw.GithubHandler.read(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `write`

```python
papermill.iorw.GithubHandler.write(self, buf, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `buf` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `papermill.iorw.HDFSHandler` methods

### `listdir`

```python
papermill.iorw.HDFSHandler.listdir(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |


---
name: package
description: "Neptune package guide for Python experiment tracking with runs, auth, offline mode, and 2.x versus Neptune Scale docs"
metadata:
  languages: "python"
  versions: "1.14.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "neptune,python,experiment-tracking,mlops,metadata,logging,runs,run,init_run,stop,Version-Sensitive,Model,assign,define,exists,fetch,fetch_model_versions_table,get_attribute,get_root_object,get_state,get_structure,get_url,lock,ping,pop,print_structure,set_attribute,start,sync,wait,ModelVersion,change_stage,Project,fetch_models_table,fetch_runs_table,Run,apply_patches,init_model,init_model_version,init_project,load_extensions,FileEntry,from_dto,ensure_json_response,AttributeType,AttributeWithProperties,LeaderboardEntry,NQLAggregator,NQLAttributeOperator,NQLAttributeType,NQLEmptyQuery,eval,NQLQuery,NQLQueryAggregate,NQLQueryAttribute,NeptuneInvalidQueryException,NoLimit,construct_progress_bar,find_attribute,get_single_page,iter_over_pages,to_leaderboard_entry,Artifact,copy,download,fetch_files_list,fetch_hash,process_assignment,track_files,Boolean,create_assignment_operation"
---

# neptune — package

Log and organize all your ML model metadata with neptune.ai.

There are four kinds of Neptune objects: run, model, model version, and project.
They help you track, store, and visualize metadata related to your model-training experiments.
The package contains the functions and constructors needed to initialize the objects.
You can either create new objects or connect to existing ones (to, for example, fetch or add more metadata).

Functions:
    init_run()
    init_model()
    init_model_version()
    init_project()

Classes:
    Run
    Model
    ModelVersion
    Project

Constants:
    ANONYMOUS_API_TOKEN

Tracking runs
-------------
A Neptune run tracks some things automatically during the execution of your model training
script, such as hardware consumption, source code, and Git inform…

## Install

```bash
pip install neptune
```

## Imports

```python
import neptune
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Model` | Class | Initializes a Model object from an existing or new model.  You can use this to… |
| `assign` | Method | Assigns values to multiple fields from a dictionary.  You can use this method t… |
| `define` | Method |  |
| `exists` | Method | Checks if there is a field or namespace under the specified path. |
| `fetch` | Method | Fetch values of all non-File Atom fields as a dictionary.  You can use this met… |
| `fetch_model_versions_table` | Method | Retrieve all versions of the given model.  Args:     query: NQL query string. S… |
| `get_attribute` | Method |  |
| `get_root_object` | Method | Returns the same Neptune object. |
| `get_state` | Method | Returns the current state of the container as a string.  Examples:     >>> from… |
| `get_structure` | Method | Returns the object's metadata structure as a dictionary.  This method can be us… |
| `get_url` | Method | Returns the URL that can be accessed within the browser |
| `lock` | Method |  |
| `ping` | Method |  |
| `pop` | Method | Removes the field stored under the path and all data associated with it.  Args:… |
| `print_structure` | Method | Pretty-prints the structure of the object's metadata.  Paths are ordered lexico… |
| `set_attribute` | Method |  |
| `start` | Method |  |
| `stop` | Method | Stops the connection and ends the synchronization thread.  You should stop any… |
| `sync` | Method | Synchronizes the local representation of the object with the representation on… |
| `wait` | Method | Wait for all the queued metadata tracking calls to reach the Neptune servers.… |
| `ModelVersion` | Class | Initializes a ModelVersion object from an existing or new model version.  Befor… |
| `assign` | Method | Assigns values to multiple fields from a dictionary.  You can use this method t… |
| `change_stage` | Method | Changes the stage of the model version.  This method is always synchronous, whi… |
| `define` | Method |  |
| `exists` | Method | Checks if there is a field or namespace under the specified path. |
| `fetch` | Method | Fetch values of all non-File Atom fields as a dictionary.  You can use this met… |
| `get_attribute` | Method |  |
| `get_root_object` | Method | Returns the same Neptune object. |
| `get_state` | Method | Returns the current state of the container as a string.  Examples:     >>> from… |
| `get_structure` | Method | Returns the object's metadata structure as a dictionary.  This method can be us… |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `Model`

Initializes a Model object from an existing or new model.

You can use this to create a new model from code or to perform actions on existing models.

A Model object is suitable for storing model met…

```python
neptune.Model(self, with_id: Optional[str] = None, *, name: Optional[str] = None, key: Optional[str] = None, project: Optional[str] = None, api_token: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'read-only', 'debug']] = None, flush_period: float = 5, proxies: Optional[dict] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `with_id` | `Optional` | `None` | pos/kw |
| `name` | `Optional` | `None` | kw |
| `key` | `Optional` | `None` | kw |
| `project` | `Optional` | `None` | kw |
| `api_token` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |

### `ModelVersion`

Initializes a ModelVersion object from an existing or new model version.

Before creating model versions, you must first register a model by creating a Model object.

A ModelVersion object is suitabl…

```python
neptune.ModelVersion(self, with_id: Optional[str] = None, *, name: Optional[str] = None, model: Optional[str] = None, project: Optional[str] = None, api_token: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'read-only', 'debug']] = None, flush_period: float = 5, proxies: Optional[dict] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `with_id` | `Optional` | `None` | pos/kw |
| `name` | `Optional` | `None` | kw |
| `model` | `Optional` | `None` | kw |
| `project` | `Optional` | `None` | kw |
| `api_token` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |

### `Project`

Starts a connection to an existing Neptune project.

You can use the Project object to retrieve information about runs, models, and model versions
within the project.

You can also log (and fetch) me…

```python
neptune.Project(self, project: Optional[str] = None, *, api_token: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'read-only', 'debug']] = None, flush_period: float = 5, proxies: Optional[dict] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Optional` | `None` | pos/kw |
| `api_token` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |

### `Run`

Starts a new tracked run that logs ML model-building metadata to neptune.ai.

You can log metadata by assigning it to the initialized Run object:

```
run = neptune.init_run()
run["your/structure"] =…

```python
neptune.Run(self, with_id: Optional[str] = None, *, project: Optional[str] = None, api_token: Optional[str] = None, custom_run_id: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'offline', 'read-only', 'debug']] = None, name: Optional[str] = None, description: Optional[str] = None, tags: Union[List[str], str, NoneType] = None, source_files: Union[List[str], str, NoneType] = None, capture_stdout: Optional[bool] = None, capture_stderr: Optional[bool] = None, capture_hardware_metrics: Optional[bool] = None, fail_on_exception: bool = True, monitoring_namespace: Optional[str] = None, flush_period: float = 5, proxies: Optional[dict] = None, capture_traceback: bool = True, git_ref: Union[neptune.types.atoms.git_ref.GitRef, neptune.types.atoms.git_ref.GitRefDisabled, bool, NoneType] = None, dependencies: Union[str, os.PathLike, NoneType] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `with_id` | `Optional` | `None` | pos/kw |
| `project` | `Optional` | `None` | kw |
| `api_token` | `Optional` | `None` | kw |
| `custom_run_id` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `name` | `Optional` | `None` | kw |
| `description` | `Optional` | `None` | kw |
| `tags` | `Union` | `None` | kw |
| `source_files` | `Union` | `None` | kw |
| `capture_stdout` | `Optional` | `None` | kw |
| `capture_stderr` | `Optional` | `None` | kw |
| `capture_hardware_metrics` | `Optional` | `None` | kw |
| `fail_on_exception` | `bool` | `True` | kw |
| `monitoring_namespace` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `capture_traceback` | `bool` | `True` | kw |
| `git_ref` | `Union` | `None` | kw |
| `dependencies` | `Union` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `init_model`

Initializes a Model object from an existing or new model.

You can use this to create a new model from code or to perform actions on existing models.

A Model object is suitable for storing model met…

```python
neptune.init_model(self, with_id: Optional[str] = None, *, name: Optional[str] = None, key: Optional[str] = None, project: Optional[str] = None, api_token: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'read-only', 'debug']] = None, flush_period: float = 5, proxies: Optional[dict] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `with_id` | `Optional` | `None` | pos/kw |
| `name` | `Optional` | `None` | kw |
| `key` | `Optional` | `None` | kw |
| `project` | `Optional` | `None` | kw |
| `api_token` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |

### `init_model_version`

Initializes a ModelVersion object from an existing or new model version.

Before creating model versions, you must first register a model by creating a Model object.

A ModelVersion object is suitabl…

```python
neptune.init_model_version(self, with_id: Optional[str] = None, *, name: Optional[str] = None, model: Optional[str] = None, project: Optional[str] = None, api_token: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'read-only', 'debug']] = None, flush_period: float = 5, proxies: Optional[dict] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `with_id` | `Optional` | `None` | pos/kw |
| `name` | `Optional` | `None` | kw |
| `model` | `Optional` | `None` | kw |
| `project` | `Optional` | `None` | kw |
| `api_token` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |

### `init_project`

Starts a connection to an existing Neptune project.

You can use the Project object to retrieve information about runs, models, and model versions
within the project.

You can also log (and fetch) me…

```python
neptune.init_project(self, project: Optional[str] = None, *, api_token: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'read-only', 'debug']] = None, flush_period: float = 5, proxies: Optional[dict] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project` | `Optional` | `None` | pos/kw |
| `api_token` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |

### `init_run`

Starts a new tracked run that logs ML model-building metadata to neptune.ai.

You can log metadata by assigning it to the initialized Run object:

```
run = neptune.init_run()
run["your/structure"] =…

```python
neptune.init_run(self, with_id: Optional[str] = None, *, project: Optional[str] = None, api_token: Optional[str] = None, custom_run_id: Optional[str] = None, mode: Optional[Literal['async', 'sync', 'offline', 'read-only', 'debug']] = None, name: Optional[str] = None, description: Optional[str] = None, tags: Union[List[str], str, NoneType] = None, source_files: Union[List[str], str, NoneType] = None, capture_stdout: Optional[bool] = None, capture_stderr: Optional[bool] = None, capture_hardware_metrics: Optional[bool] = None, fail_on_exception: bool = True, monitoring_namespace: Optional[str] = None, flush_period: float = 5, proxies: Optional[dict] = None, capture_traceback: bool = True, git_ref: Union[neptune.types.atoms.git_ref.GitRef, neptune.types.atoms.git_ref.GitRefDisabled, bool, NoneType] = None, dependencies: Union[str, os.PathLike, NoneType] = None, async_lag_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_lag_threshold: float = 1800.0, async_no_progress_callback: Optional[Callable[[neptune.metadata_containers.abstract.NeptuneObject], NoneType]] = None, async_no_progress_threshold: float = 300.0, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `with_id` | `Optional` | `None` | pos/kw |
| `project` | `Optional` | `None` | kw |
| `api_token` | `Optional` | `None` | kw |
| `custom_run_id` | `Optional` | `None` | kw |
| `mode` | `Optional` | `None` | kw |
| `name` | `Optional` | `None` | kw |
| `description` | `Optional` | `None` | kw |
| `tags` | `Union` | `None` | kw |
| `source_files` | `Union` | `None` | kw |
| `capture_stdout` | `Optional` | `None` | kw |
| `capture_stderr` | `Optional` | `None` | kw |
| `capture_hardware_metrics` | `Optional` | `None` | kw |
| `fail_on_exception` | `bool` | `True` | kw |
| `monitoring_namespace` | `Optional` | `None` | kw |
| `flush_period` | `float` | `5` | kw |
| `proxies` | `Optional` | `None` | kw |
| `capture_traceback` | `bool` | `True` | kw |
| `git_ref` | `Union` | `None` | kw |
| `dependencies` | `Union` | `None` | kw |
| `async_lag_callback` | `Optional` | `None` | kw |
| `async_lag_threshold` | `float` | `1800.0` | kw |
| `async_no_progress_callback` | `Optional` | `None` | kw |
| `async_no_progress_threshold` | `float` | `300.0` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `FileEntry`

FileEntry(name: str, size: int, mtime: datetime.datetime, file_type: str)

```python
neptune.api.dtos.FileEntry(self, name: str, size: int, mtime: datetime.datetime, file_type: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `size` | `int` | `—` | pos/kw |
| `mtime` | `datetime` | `—` | pos/kw |
| `file_type` | `str` | `—` | pos/kw |

### `AttributeType`

Create a collection of name/value pairs.

Example enumeration:

>>> class Color(Enum):
...     RED = 1
...     BLUE = 2
...     GREEN = 3

Access them by:

- attribute access:

  >>> Color.RED
  <Col…

```python
neptune.api.searching_entries.AttributeType(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `AttributeWithProperties`

AttributeWithProperties(path: str, type: neptune.internal.backends.api_model.AttributeType, properties: Any)

```python
neptune.api.searching_entries.AttributeWithProperties(self, path: str, type: neptune.internal.backends.api_model.AttributeType, properties: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |
| `type` | `AttributeType` | `—` | pos/kw |
| `properties` | `Any` | `—` | pos/kw |

### `LeaderboardEntry`

LeaderboardEntry(id: str, attributes: List[neptune.internal.backends.api_model.AttributeWithProperties])

```python
neptune.api.searching_entries.LeaderboardEntry(self, id: str, attributes: List[neptune.internal.backends.api_model.AttributeWithProperties]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `str` | `—` | pos/kw |
| `attributes` | `List` | `—` | pos/kw |

### `NQLAggregator`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
neptune.api.searching_entries.NQLAggregator(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `NQLAttributeOperator`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
neptune.api.searching_entries.NQLAttributeOperator(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `NQLAttributeType`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
neptune.api.searching_entries.NQLAttributeType(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `NQLEmptyQuery`

NQLEmptyQuery()

```python
neptune.api.searching_entries.NQLEmptyQuery(self) -> None
```

### `NQLQuery`

NQLQuery()

```python
neptune.api.searching_entries.NQLQuery(self) -> None
```

### `NQLQueryAggregate`

NQLQueryAggregate(items: 'Iterable[NQLQuery]', aggregator: 'NQLAggregator')

```python
neptune.api.searching_entries.NQLQueryAggregate(self, items: 'Iterable[NQLQuery]', aggregator: 'NQLAggregator') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `items` | `Iterable[NQLQuery]` | `—` | pos/kw |
| `aggregator` | `NQLAggregator` | `—` | pos/kw |

### `NQLQueryAttribute`

NQLQueryAttribute(name: 'str', type: 'NQLAttributeType', operator: 'NQLAttributeOperator', value: 'typing.Union[str, bool]')

```python
neptune.api.searching_entries.NQLQueryAttribute(self, name: 'str', type: 'NQLAttributeType', operator: 'NQLAttributeOperator', value: 'typing.Union[str, bool]') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `type` | `NQLAttributeType` | `—` | pos/kw |
| `operator` | `NQLAttributeOperator` | `—` | pos/kw |
| `value` | `typing.Union[str, bool]` | `—` | pos/kw |

### `NeptuneInvalidQueryException`

Common base class for all non-exit exceptions.

```python
neptune.api.searching_entries.NeptuneInvalidQueryException(self, nql_query: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `nql_query` | `str` | `—` | pos/kw |

### `NoLimit`

int([x]) -> integer
int(x, base=10) -> integer

Convert a number or string to an integer, or return 0 if no arguments
are given.  If x is a number, return x.__int__().  For floating-point
numbers, th…

```python
neptune.api.searching_entries.NoLimit(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Artifact`

```python
neptune.attributes.Artifact(self, container: 'MetadataContainer', path: List[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `container` | `MetadataContainer` | `—` | pos/kw |
| `path` | `List` | `—` | pos/kw |

### `Boolean`

```python
neptune.attributes.Boolean(self, container: 'MetadataContainer', path: List[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `container` | `MetadataContainer` | `—` | pos/kw |
| `path` | `List` | `—` | pos/kw |

## Functions

### `apply_patches`

```python
neptune.apply_patches()
```

### `load_extensions`

```python
neptune.load_extensions() -> None
```

### `ensure_json_response`

```python
neptune.api.requests_utils.ensure_json_response(response: 'IncomingResponse') -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `response` | `IncomingResponse` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `construct_progress_bar`

```python
neptune.api.searching_entries.construct_progress_bar(progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType], description: str) -> neptune.typing.ProgressBarCallback
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `progress_bar` | `Union` | `—` | pos/kw |
| `description` | `str` | `—` | pos/kw |

**Returns:** `<class 'neptune.typing.ProgressBarCallback'>`

### `find_attribute`

```python
neptune.api.searching_entries.find_attribute(*, entry: neptune.internal.backends.api_model.LeaderboardEntry, path: str) -> Optional[neptune.internal.backends.api_model.AttributeWithProperties]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `entry` | `LeaderboardEntry` | `—` | kw |
| `path` | `str` | `—` | kw |

**Returns:** `typing.Optional[neptune.internal.backends.api_model.AttributeWithProperties]`

### `get_single_page`

```python
neptune.api.searching_entries.get_single_page(*, client: 'SwaggerClientWrapper', project_id: 'UniqueId', attributes_filter: Dict[str, Any], limit: int, offset: int, sort_by: str, sort_by_column_type: Literal['string', 'datetime', 'integer', 'boolean', 'float'], ascending: bool, types: Optional[Iterable[str]], query: Optional[ForwardRef('NQLQuery')], searching_after: Optional[str]) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `SwaggerClientWrapper` | `—` | kw |
| `project_id` | `UniqueId` | `—` | kw |
| `attributes_filter` | `Dict` | `—` | kw |
| `limit` | `int` | `—` | kw |
| `offset` | `int` | `—` | kw |
| `sort_by` | `str` | `—` | kw |
| `sort_by_column_type` | `Literal` | `—` | kw |
| `ascending` | `bool` | `—` | kw |
| `types` | `Optional` | `—` | kw |
| `query` | `Optional` | `—` | kw |
| `searching_after` | `Optional` | `—` | kw |

**Returns:** `typing.Any`

### `iter_over_pages`

```python
neptune.api.searching_entries.iter_over_pages(*, step_size: int, limit: Optional[int], sort_by: str, sort_by_column_type: Literal['string', 'datetime', 'integer', 'boolean', 'float'], ascending: bool, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType], max_offset: int = 10000, **kwargs: Any) -> Generator[Any, NoneType, NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `step_size` | `int` | `—` | kw |
| `limit` | `Optional` | `—` | kw |
| `sort_by` | `str` | `—` | kw |
| `sort_by_column_type` | `Literal` | `—` | kw |
| `ascending` | `bool` | `—` | kw |
| `progress_bar` | `Union` | `—` | kw |
| `max_offset` | `int` | `10000` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `typing.Generator[typing.Any, NoneType, NoneType]`

### `to_leaderboard_entry`

```python
neptune.api.searching_entries.to_leaderboard_entry(entry: Dict[str, Any]) -> neptune.internal.backends.api_model.LeaderboardEntry
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `entry` | `Dict` | `—` | pos/kw |

**Returns:** `<class 'neptune.internal.backends.api_model.LeaderboardEntry'>`

## Methods

### `neptune.Model` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.Model.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `define`

```python
neptune.Model.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.Model.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.Model.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `fetch_model_versions_table`

Retrieve all versions of the given model.

Args:
    query: NQL query string. Syntax: https://docs-legacy.neptune.ai/usage/nql/
        Example: `"(model_size: float > 100) AND (backbone: string = VG…

```python
neptune.Model.fetch_model_versions_table(self, *, query: Optional[str] = None, columns: Optional[Iterable[str]] = None, limit: Optional[int] = None, sort_by: str = 'sys/creation_time', ascending: bool = False, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None) -> neptune.table.Table
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Optional` | `None` | kw |
| `columns` | `Optional` | `None` | kw |
| `limit` | `Optional` | `None` | kw |
| `sort_by` | `str` | `'sys/creation_time'` | kw |
| `ascending` | `bool` | `False` | kw |
| `progress_bar` | `Union` | `None` | kw |

**Returns:** `<class 'neptune.table.Table'>`

### `get_attribute`

```python
neptune.Model.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.Model.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.Model.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.Model.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.Model.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.Model.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.Model.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.Model.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.Model.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.Model.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.Model.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.Model.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.Model.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.Model.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.ModelVersion` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.ModelVersion.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `change_stage`

Changes the stage of the model version.

This method is always synchronous, which means that Neptune will wait for all other calls to reach the Neptune
    servers before executing it.
Args:
    stag…

```python
neptune.ModelVersion.change_stage(self, stage: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stage` | `str` | `—` | pos/kw |

### `define`

```python
neptune.ModelVersion.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.ModelVersion.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.ModelVersion.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `get_attribute`

```python
neptune.ModelVersion.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.ModelVersion.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.ModelVersion.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.ModelVersion.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.ModelVersion.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.ModelVersion.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.ModelVersion.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.ModelVersion.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.ModelVersion.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.ModelVersion.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.ModelVersion.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.ModelVersion.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.ModelVersion.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.ModelVersion.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.Project` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.Project.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `define`

```python
neptune.Project.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.Project.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.Project.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `fetch_models_table`

Retrieve models stored in the project.

Args:
    query: NQL query string. Syntax: https://docs-legacy.neptune.ai/usage/nql/
        Example: `"(model_size: float > 100) AND (backbone: string = VGG)"…

```python
neptune.Project.fetch_models_table(self, *, query: Optional[str] = None, columns: Optional[Iterable[str]] = None, trashed: Optional[bool] = False, limit: Optional[int] = None, sort_by: str = 'sys/creation_time', ascending: bool = False, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None) -> neptune.table.Table
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Optional` | `None` | kw |
| `columns` | `Optional` | `None` | kw |
| `trashed` | `Optional` | `False` | kw |
| `limit` | `Optional` | `None` | kw |
| `sort_by` | `str` | `'sys/creation_time'` | kw |
| `ascending` | `bool` | `False` | kw |
| `progress_bar` | `Union` | `None` | kw |

**Returns:** `<class 'neptune.table.Table'>`

### `fetch_runs_table`

Retrieve runs matching the specified criteria.

All parameters are optional. Each of them specifies a single criterion.
Only runs matching all of the criteria will be returned.

Args:
    query: NQL…

```python
neptune.Project.fetch_runs_table(self, *, query: Optional[str] = None, id: Union[str, Iterable[str], NoneType] = None, state: Union[Literal['inactive', 'active'], Iterable[Literal['inactive', 'active']], NoneType] = None, owner: Union[str, Iterable[str], NoneType] = None, tag: Union[str, Iterable[str], NoneType] = None, columns: Optional[Iterable[str]] = None, trashed: Optional[bool] = False, limit: Optional[int] = None, sort_by: str = 'sys/creation_time', ascending: bool = False, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None) -> neptune.table.Table
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Optional` | `None` | kw |
| `id` | `Union` | `None` | kw |
| `state` | `Union` | `None` | kw |
| `owner` | `Union` | `None` | kw |
| `tag` | `Union` | `None` | kw |
| `columns` | `Optional` | `None` | kw |
| `trashed` | `Optional` | `False` | kw |
| `limit` | `Optional` | `None` | kw |
| `sort_by` | `str` | `'sys/creation_time'` | kw |
| `ascending` | `bool` | `False` | kw |
| `progress_bar` | `Union` | `None` | kw |

**Returns:** `<class 'neptune.table.Table'>`

### `get_attribute`

```python
neptune.Project.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.Project.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.Project.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.Project.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.Project.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.Project.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.Project.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.Project.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.Project.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.Project.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.Project.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.Project.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.Project.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.Project.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.Run` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.Run.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `define`

```python
neptune.Run.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.Run.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.Run.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `get_attribute`

```python
neptune.Run.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.Run.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.Run.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.Run.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.Run.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.Run.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.Run.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.Run.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.Run.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.Run.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.Run.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.Run.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.Run.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.Run.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.init_model` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.init_model.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `define`

```python
neptune.init_model.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.init_model.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.init_model.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `fetch_model_versions_table`

Retrieve all versions of the given model.

Args:
    query: NQL query string. Syntax: https://docs-legacy.neptune.ai/usage/nql/
        Example: `"(model_size: float > 100) AND (backbone: string = VG…

```python
neptune.init_model.fetch_model_versions_table(self, *, query: Optional[str] = None, columns: Optional[Iterable[str]] = None, limit: Optional[int] = None, sort_by: str = 'sys/creation_time', ascending: bool = False, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None) -> neptune.table.Table
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Optional` | `None` | kw |
| `columns` | `Optional` | `None` | kw |
| `limit` | `Optional` | `None` | kw |
| `sort_by` | `str` | `'sys/creation_time'` | kw |
| `ascending` | `bool` | `False` | kw |
| `progress_bar` | `Union` | `None` | kw |

**Returns:** `<class 'neptune.table.Table'>`

### `get_attribute`

```python
neptune.init_model.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.init_model.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.init_model.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.init_model.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.init_model.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.init_model.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.init_model.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.init_model.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.init_model.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.init_model.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.init_model.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.init_model.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.init_model.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.init_model.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.init_model_version` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.init_model_version.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `change_stage`

Changes the stage of the model version.

This method is always synchronous, which means that Neptune will wait for all other calls to reach the Neptune
    servers before executing it.
Args:
    stag…

```python
neptune.init_model_version.change_stage(self, stage: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stage` | `str` | `—` | pos/kw |

### `define`

```python
neptune.init_model_version.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.init_model_version.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.init_model_version.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `get_attribute`

```python
neptune.init_model_version.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.init_model_version.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.init_model_version.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.init_model_version.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.init_model_version.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.init_model_version.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.init_model_version.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.init_model_version.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.init_model_version.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.init_model_version.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.init_model_version.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.init_model_version.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.init_model_version.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.init_model_version.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.init_project` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.init_project.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `define`

```python
neptune.init_project.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.init_project.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.init_project.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `fetch_models_table`

Retrieve models stored in the project.

Args:
    query: NQL query string. Syntax: https://docs-legacy.neptune.ai/usage/nql/
        Example: `"(model_size: float > 100) AND (backbone: string = VGG)"…

```python
neptune.init_project.fetch_models_table(self, *, query: Optional[str] = None, columns: Optional[Iterable[str]] = None, trashed: Optional[bool] = False, limit: Optional[int] = None, sort_by: str = 'sys/creation_time', ascending: bool = False, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None) -> neptune.table.Table
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Optional` | `None` | kw |
| `columns` | `Optional` | `None` | kw |
| `trashed` | `Optional` | `False` | kw |
| `limit` | `Optional` | `None` | kw |
| `sort_by` | `str` | `'sys/creation_time'` | kw |
| `ascending` | `bool` | `False` | kw |
| `progress_bar` | `Union` | `None` | kw |

**Returns:** `<class 'neptune.table.Table'>`

### `fetch_runs_table`

Retrieve runs matching the specified criteria.

All parameters are optional. Each of them specifies a single criterion.
Only runs matching all of the criteria will be returned.

Args:
    query: NQL…

```python
neptune.init_project.fetch_runs_table(self, *, query: Optional[str] = None, id: Union[str, Iterable[str], NoneType] = None, state: Union[Literal['inactive', 'active'], Iterable[Literal['inactive', 'active']], NoneType] = None, owner: Union[str, Iterable[str], NoneType] = None, tag: Union[str, Iterable[str], NoneType] = None, columns: Optional[Iterable[str]] = None, trashed: Optional[bool] = False, limit: Optional[int] = None, sort_by: str = 'sys/creation_time', ascending: bool = False, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None) -> neptune.table.Table
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Optional` | `None` | kw |
| `id` | `Union` | `None` | kw |
| `state` | `Union` | `None` | kw |
| `owner` | `Union` | `None` | kw |
| `tag` | `Union` | `None` | kw |
| `columns` | `Optional` | `None` | kw |
| `trashed` | `Optional` | `False` | kw |
| `limit` | `Optional` | `None` | kw |
| `sort_by` | `str` | `'sys/creation_time'` | kw |
| `ascending` | `bool` | `False` | kw |
| `progress_bar` | `Union` | `None` | kw |

**Returns:** `<class 'neptune.table.Table'>`

### `get_attribute`

```python
neptune.init_project.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.init_project.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.init_project.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.init_project.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.init_project.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.init_project.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.init_project.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.init_project.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.init_project.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.init_project.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.init_project.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.init_project.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.init_project.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.init_project.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.init_run` methods

### `assign`

Assigns values to multiple fields from a dictionary.

You can use this method to quickly log all parameters at once.

Args:
    value (dict): A dictionary with values to assign, where keys become pat…

```python
neptune.init_run.assign(self, value, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `define`

```python
neptune.init_run.define(self, path: str, value: Any, *, wait: bool = False) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `exists`

Checks if there is a field or namespace under the specified path.

```python
neptune.init_run.exists(self, path: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `fetch`

Fetch values of all non-File Atom fields as a dictionary.

You can use this method to retrieve metadata from a started or resumed run.
The result preserves the hierarchical structure of the run's met…

```python
neptune.init_run.fetch(self) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `get_attribute`

```python
neptune.init_run.get_attribute(self, path: str) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `get_root_object`

Returns the same Neptune object.

```python
neptune.init_run.get_root_object(self) -> 'MetadataContainer'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MetadataContainer`

### `get_state`

Returns the current state of the container as a string.

Examples:
    >>> from neptune import init_run
    >>> run = init_run()
    >>> run.get_state()
    'started'
    >>> run.stop()
    >>> run.g…

```python
neptune.init_run.get_state(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_structure`

Returns the object's metadata structure as a dictionary.

This method can be used to programmatically traverse the metadata structure of a run, model,
or project object when using Neptune in automate…

```python
neptune.init_run.get_structure(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_url`

Returns the URL that can be accessed within the browser

```python
neptune.init_run.get_url(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lock`

```python
neptune.init_run.lock(self) -> <function RLock at 0x77502fd7e200>
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<function RLock at 0x77502fd7e200>`

### `ping`

```python
neptune.init_run.ping(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pop`

Removes the field stored under the path and all data associated with it.

Args:
    path: Path of the field to be removed.
    wait: If `True`, Neptune waits to send all tracked metadata to the serve…

```python
neptune.init_run.pop(self, path: str, *, wait: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `print_structure`

Pretty-prints the structure of the object's metadata.

Paths are ordered lexicographically and the whole structure is neatly colored.

See also: https://docs-legacy.neptune.ai/api/universal/#print_st…

```python
neptune.init_run.print_structure(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_attribute`

```python
neptune.init_run.set_attribute(self, path: str, attribute: neptune.attributes.attribute.Attribute) -> Optional[neptune.attributes.attribute.Attribute]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `attribute` | `Attribute` | `—` | pos/kw |

**Returns:** `typing.Optional[neptune.attributes.attribute.Attribute]`

### `start`

```python
neptune.init_run.start(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `stop`

Stops the connection and ends the synchronization thread.

You should stop any initialized runs or other objects when the connection to them is no longer needed.

This method is automatically called:…

```python
neptune.init_run.stop(self, *, seconds: Union[float, int, NoneType] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `seconds` | `Union` | `None` | kw |

### `sync`

Synchronizes the local representation of the object with the representation on the Neptune servers.

Args:
    wait: If `True`, the process will only wait for data to be saved
        locally from me…

```python
neptune.init_run.sync(self, *, wait: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `wait` | `bool` | `True` | kw |

### `wait`

Wait for all the queued metadata tracking calls to reach the Neptune servers.

Args:
    disk_only: If `True`, the process will only wait for data to be saved
        locally from memory, but will no…

```python
neptune.init_run.wait(self, *, disk_only=False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `disk_only` | `—` | `False` | kw |

### `neptune.api.dtos.FileEntry` methods

### `from_dto`

```python
neptune.api.dtos.FileEntry.from_dto(file_dto: Any) -> 'FileEntry'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `file_dto` | `Any` | `—` | pos/kw |

**Returns:** `FileEntry`

### `neptune.api.searching_entries.NQLEmptyQuery` methods

### `eval`

```python
neptune.api.searching_entries.NQLEmptyQuery.eval(self) -> 'NQLQuery'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `NQLQuery`

### `neptune.api.searching_entries.NQLQuery` methods

### `eval`

```python
neptune.api.searching_entries.NQLQuery.eval(self) -> 'NQLQuery'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `NQLQuery`

### `neptune.api.searching_entries.NQLQueryAggregate` methods

### `eval`

```python
neptune.api.searching_entries.NQLQueryAggregate.eval(self) -> 'NQLQuery'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `NQLQuery`

### `neptune.api.searching_entries.NQLQueryAttribute` methods

### `eval`

```python
neptune.api.searching_entries.NQLQueryAttribute.eval(self) -> 'NQLQuery'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `NQLQuery`

### `neptune.attributes.Artifact` methods

### `assign`

```python
neptune.attributes.Artifact.assign(self, value: neptune.types.atoms.artifact.Artifact, *, wait: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Artifact` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `copy`

```python
neptune.attributes.Artifact.copy(self, value: neptune.types.value_copy.ValueCopy, wait: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `ValueCopy` | `—` | pos/kw |
| `wait` | `bool` | `False` | pos/kw |

### `download`

```python
neptune.attributes.Artifact.download(self, destination: str = None, progress_bar: Union[bool, Type[neptune.typing.ProgressBarCallback], NoneType] = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `destination` | `str` | `None` | pos/kw |
| `progress_bar` | `Union` | `None` | pos/kw |

### `fetch`

```python
neptune.attributes.Artifact.fetch(self) -> neptune.types.atoms.artifact.Artifact
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'neptune.types.atoms.artifact.Artifact'>`

### `fetch_files_list`

```python
neptune.attributes.Artifact.fetch_files_list(self) -> List[neptune.internal.artifacts.types.ArtifactFileData]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[neptune.internal.artifacts.types.ArtifactFileData]`

### `fetch_hash`

```python
neptune.attributes.Artifact.fetch_hash(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `process_assignment`

```python
neptune.attributes.Artifact.process_assignment(self, value, wait=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `wait` | `—` | `False` | pos/kw |

### `track_files`

```python
neptune.attributes.Artifact.track_files(self, path: str, *, destination: str = None, wait: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `destination` | `str` | `None` | kw |
| `wait` | `bool` | `False` | kw |

### `neptune.attributes.Boolean` methods

### `assign`

```python
neptune.attributes.Boolean.assign(self, value: Union[neptune.types.atoms.boolean.Boolean, bool], *, wait: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `copy`

```python
neptune.attributes.Boolean.copy(self, value: neptune.types.value_copy.ValueCopy, *, wait: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `ValueCopy` | `—` | pos/kw |
| `wait` | `bool` | `False` | kw |

### `create_assignment_operation`

```python
neptune.attributes.Boolean.create_assignment_operation(path, value: bool)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `value` | `bool` | `—` | pos/kw |

### `fetch`

```python
neptune.attributes.Boolean.fetch(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |


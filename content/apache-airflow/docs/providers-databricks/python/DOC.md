---
name: providers-databricks
description: "Apache Airflow Databricks provider for submitting Jobs runs and triggering existing Databricks jobs from Python DAGs"
metadata:
  languages: "python"
  versions: "7.10.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "apache-airflow,python,airflow,databricks,jobs,dag,DatabricksRunNowOperator,datetime,annotations,One-Time,DatabricksSqlExecutionError,serialize,DatabricksSqlExecutionTimeout,get_provider_info,BaseDatabricksHook,aget_connection,get_conn,get_connection,get_connection_form_widgets,get_hook,get_ui_field_behaviour,logger,ClusterState,from_json,to_json,DatabricksHook,a_get_cluster_state,a_get_run,a_get_run_output,a_get_run_page_url,a_get_run_state,a_get_sql_statement_state,cancel_all_runs,cancel_run,cancel_sql_statement,create_job,create_repo,delete_repo,delete_run,find_job_id_by_name,find_pipeline_id_by_name,get_cluster_state,get_job_id,get_latest_repair_id,get_openlineage_database_dialect,get_openlineage_database_info,get_openlineage_default_schema,get_repo_by_path,get_run,get_run_output,get_run_page_url,RunLifeCycleState,RunState,SQLStatementState,BearerAuth,decode,encode,from_url,DatabricksSqlHook,bulk_dump,bulk_load,get_autocommit,get_conn_id,get_cursor,get_db_log_messages,get_df,get_df_by_chunks,get_first,get_openlineage_authority_part,get_openlineage_database_specific_lineage,get_pandas_df,get_pandas_df_by_chunks,get_records,get_sqlalchemy_engine,get_table_schema,get_uri,insert_rows,run,set_autocommit,create_timeout_thread,DatabricksCreateJobsOperator,add_inlets,add_outlets,as_setup,as_teardown,defer,dry_run,execute,expand_start_trigger_args,get_closest_mapped_task_group,get_dag,get_direct_relative_ids,get_direct_relatives,get_flat_relative_ids,get_flat_relatives,get_needs_expansion,get_serialized_fields,get_template_env,get_upstreams_follow_setups,get_upstreams_only_setups,get_upstreams_only_setups_and_teardowns,has_dag,iter_mapped_dependants,iter_mapped_task_groups,on_kill,partial,post_execute,pre_execute,prepare_for_execution,prepare_template,render_template,DatabricksExecutionTrigger,cleanup,repr,DatabricksJobRunLink,get_link,DatabricksNotebookOperator,execute_complete"
---

# apache-airflow — providers-databricks

## Install

```bash
pip install apache-airflow
```

## Imports

```python
import apache_airflow
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `DatabricksSqlExecutionError` | Class | Raised when there is an error in sql execution. |
| `serialize` | Method |  |
| `DatabricksSqlExecutionTimeout` | Class | Raised when a sql execution times out. |
| `serialize` | Method |  |
| `get_provider_info` | Function |  |
| `BaseDatabricksHook` | Class | Base for interaction with Databricks.  :param databricks_conn_id: Reference to… |
| `aget_connection` | Method | Get connection (async), given connection id.  :param conn_id: connection id :re… |
| `get_conn` | Method | Return connection for the hook. |
| `get_connection` | Method | Get connection, given connection id.  :param conn_id: connection id :return: co… |
| `get_connection_form_widgets` | Method |  |
| `get_hook` | Method | Return default hook for this connection id.  :param conn_id: connection id :par… |
| `get_ui_field_behaviour` | Method |  |
| `logger` | Method | Return a logger. |
| `ClusterState` | Class | Utility class for the cluster state concept of Databricks cluster. |
| `from_json` | Method |  |
| `to_json` | Method |  |
| `DatabricksHook` | Class | Interact with Databricks.  :param databricks_conn_id: Reference to the :ref:`Da… |
| `a_get_cluster_state` | Method | Async version of `get_cluster_state`.  :param cluster_id: id of the cluster :re… |
| `a_get_run` | Method | Async version of `get_run`.  :param run_id: id of the run :return: state of the… |
| `a_get_run_output` | Method | Async version of `get_run_output()`.  :param run_id: id of the run :return: out… |
| `a_get_run_page_url` | Method | Async version of `get_run_page_url()`.  :param run_id: id of the run :return: U… |
| `a_get_run_state` | Method | Async version of `get_run_state()`.  :param run_id: id of the run :return: stat… |
| `a_get_sql_statement_state` | Method | Async version of `get_sql_statement_state`.  :param statement_id: ID of the SQL… |
| `aget_connection` | Method | Get connection (async), given connection id.  :param conn_id: connection id :re… |
| `cancel_all_runs` | Method | Cancel all active runs of a job asynchronously.  :param job_id: The canonical i… |
| `cancel_run` | Method | Cancel the run.  :param run_id: id of the run |
| `cancel_sql_statement` | Method | Cancel the SQL statement.  :param statement_id: ID of the SQL statement |
| `create_job` | Method | Call the ``api/2.2/jobs/create`` endpoint.  :param json: The data used in the b… |
| `create_repo` | Method | Create a Databricks Repos.  :param json: payload :return: |
| `delete_repo` | Method | Delete given Databricks Repos.  :param repo_id: ID of Databricks Repos :return: |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `DatabricksSqlExecutionError`

Raised when there is an error in sql execution.

```python
airflow.providers.databricks.exceptions.DatabricksSqlExecutionError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DatabricksSqlExecutionTimeout`

Raised when a sql execution times out.

```python
airflow.providers.databricks.exceptions.DatabricksSqlExecutionTimeout(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BaseDatabricksHook`

Base for interaction with Databricks.

:param databricks_conn_id: Reference to the :ref:`Databricks connection <howto/connection:databricks>`.
:param timeout_seconds: The amount of time in seconds th…

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook(self, databricks_conn_id: 'str' = 'databricks_default', timeout_seconds: 'int' = 180, retry_limit: 'int' = 3, retry_delay: 'float' = 1.0, retry_args: 'dict[Any, Any] | None' = None, caller: 'str' = 'Unknown') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `timeout_seconds` | `int` | `180` | pos/kw |
| `retry_limit` | `int` | `3` | pos/kw |
| `retry_delay` | `float` | `1.0` | pos/kw |
| `retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `caller` | `str` | `'Unknown'` | pos/kw |

### `ClusterState`

Utility class for the cluster state concept of Databricks cluster.

```python
airflow.providers.databricks.hooks.databricks.ClusterState(self, state: 'str' = '', state_message: 'str' = '', *args, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `state` | `str` | `''` | pos/kw |
| `state_message` | `str` | `''` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DatabricksHook`

Interact with Databricks.

:param databricks_conn_id: Reference to the :ref:`Databricks connection <howto/connection:databricks>`.
:param timeout_seconds: The amount of time in seconds the requests l…

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook(self, databricks_conn_id: 'str' = 'databricks_default', timeout_seconds: 'int' = 180, retry_limit: 'int' = 3, retry_delay: 'float' = 1.0, retry_args: 'dict[Any, Any] | None' = None, caller: 'str' = 'DatabricksHook') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `timeout_seconds` | `int` | `180` | pos/kw |
| `retry_limit` | `int` | `3` | pos/kw |
| `retry_delay` | `float` | `1.0` | pos/kw |
| `retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `caller` | `str` | `'DatabricksHook'` | pos/kw |

### `RunLifeCycleState`

Enum for the run life cycle state concept of Databricks runs.

See more information at: https://docs.databricks.com/api/azure/workspace/jobs/listruns#runs-state-life_cycle_state

```python
airflow.providers.databricks.hooks.databricks.RunLifeCycleState(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `RunState`

Utility class for the run state concept of Databricks runs.

```python
airflow.providers.databricks.hooks.databricks.RunState(self, life_cycle_state: 'str', result_state: 'str' = '', state_message: 'str' = '', *args, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `life_cycle_state` | `str` | `—` | pos/kw |
| `result_state` | `str` | `''` | pos/kw |
| `state_message` | `str` | `''` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SQLStatementState`

Utility class for the SQL statement state concept of Databricks statements.

```python
airflow.providers.databricks.hooks.databricks.SQLStatementState(self, state: 'str' = '', error_code: 'str' = '', error_message: 'str' = '', *args, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `state` | `str` | `''` | pos/kw |
| `error_code` | `str` | `''` | pos/kw |
| `error_message` | `str` | `''` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BaseDatabricksHook`

Base for interaction with Databricks.

:param databricks_conn_id: Reference to the :ref:`Databricks connection <howto/connection:databricks>`.
:param timeout_seconds: The amount of time in seconds th…

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook(self, databricks_conn_id: 'str' = 'databricks_default', timeout_seconds: 'int' = 180, retry_limit: 'int' = 3, retry_delay: 'float' = 1.0, retry_args: 'dict[Any, Any] | None' = None, caller: 'str' = 'Unknown') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `timeout_seconds` | `int` | `180` | pos/kw |
| `retry_limit` | `int` | `3` | pos/kw |
| `retry_delay` | `float` | `1.0` | pos/kw |
| `retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `caller` | `str` | `'Unknown'` | pos/kw |

### `BearerAuth`

aiohttp only ships BasicAuth, for Bearer auth we need a subclass of BasicAuth.

```python
airflow.providers.databricks.hooks.databricks_base.BearerAuth(self, token: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `token` | `str` | `—` | pos/kw |

### `BaseDatabricksHook`

Base for interaction with Databricks.

:param databricks_conn_id: Reference to the :ref:`Databricks connection <howto/connection:databricks>`.
:param timeout_seconds: The amount of time in seconds th…

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook(self, databricks_conn_id: 'str' = 'databricks_default', timeout_seconds: 'int' = 180, retry_limit: 'int' = 3, retry_delay: 'float' = 1.0, retry_args: 'dict[Any, Any] | None' = None, caller: 'str' = 'Unknown') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `timeout_seconds` | `int` | `180` | pos/kw |
| `retry_limit` | `int` | `3` | pos/kw |
| `retry_delay` | `float` | `1.0` | pos/kw |
| `retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `caller` | `str` | `'Unknown'` | pos/kw |

### `DatabricksSqlExecutionError`

Raised when there is an error in sql execution.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlExecutionError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DatabricksSqlExecutionTimeout`

Raised when a sql execution times out.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlExecutionTimeout(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DatabricksSqlHook`

Hook to interact with Databricks SQL.

:param databricks_conn_id: Reference to the
    :ref:`Databricks connection <howto/connection:databricks>`.
:param http_path: Optional string specifying HTTP pa…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook(self, databricks_conn_id: 'str' = 'databricks_default', http_path: 'str | None' = None, sql_endpoint_name: 'str | None' = None, session_configuration: 'dict[str, str] | None' = None, http_headers: 'list[tuple[str, str]] | None' = None, catalog: 'str | None' = None, schema: 'str | None' = None, caller: 'str' = 'DatabricksSqlHook', **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `http_path` | `str \| None` | `None` | pos/kw |
| `sql_endpoint_name` | `str \| None` | `None` | pos/kw |
| `session_configuration` | `dict[str, str] \| None` | `None` | pos/kw |
| `http_headers` | `list[tuple[str, str]] \| None` | `None` | pos/kw |
| `catalog` | `str \| None` | `None` | pos/kw |
| `schema` | `str \| None` | `None` | pos/kw |
| `caller` | `str` | `'DatabricksSqlHook'` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `DatabricksCreateJobsOperator`

Creates (or resets) a Databricks job using the API endpoint.

.. seealso::
    https://docs.databricks.com/api/workspace/jobs/create
    https://docs.databricks.com/api/workspace/jobs/reset

:param j…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator(self, *, json: 'Any | None' = None, name: 'str | None' = None, description: 'str | None' = None, tags: 'dict[str, str] | None' = None, tasks: 'list[dict] | None' = None, job_clusters: 'list[dict] | None' = None, email_notifications: 'dict | None' = None, webhook_notifications: 'dict | None' = None, notification_settings: 'dict | None' = None, timeout_seconds: 'int | None' = None, schedule: 'dict | None' = None, max_concurrent_runs: 'int | None' = None, git_source: 'dict | None' = None, access_control_list: 'list[dict] | None' = None, databricks_conn_id: 'str' = 'databricks_default', polling_period_seconds: 'int' = 30, databricks_retry_limit: 'int' = 3, databricks_retry_delay: 'int' = 1, databricks_retry_args: 'dict[Any, Any] | None' = None, **kwargs) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `json` | `Any \| None` | `None` | kw |
| `name` | `str \| None` | `None` | kw |
| `description` | `str \| None` | `None` | kw |
| `tags` | `dict[str, str] \| None` | `None` | kw |
| `tasks` | `list[dict] \| None` | `None` | kw |
| `job_clusters` | `list[dict] \| None` | `None` | kw |
| `email_notifications` | `dict \| None` | `None` | kw |
| `webhook_notifications` | `dict \| None` | `None` | kw |
| `notification_settings` | `dict \| None` | `None` | kw |
| `timeout_seconds` | `int \| None` | `None` | kw |
| `schedule` | `dict \| None` | `None` | kw |
| `max_concurrent_runs` | `int \| None` | `None` | kw |
| `git_source` | `dict \| None` | `None` | kw |
| `access_control_list` | `list[dict] \| None` | `None` | kw |
| `databricks_conn_id` | `str` | `'databricks_default'` | kw |
| `polling_period_seconds` | `int` | `30` | kw |
| `databricks_retry_limit` | `int` | `3` | kw |
| `databricks_retry_delay` | `int` | `1` | kw |
| `databricks_retry_args` | `dict[Any, Any] \| None` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `DatabricksExecutionTrigger`

The trigger handles the logic of async communication with DataBricks API.

:param run_id: id of the run
:param databricks_conn_id: Reference to the :ref:`Databricks connection <howto/connection:datab…

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger(self, run_id: 'int', databricks_conn_id: 'str', polling_period_seconds: 'int' = 30, retry_limit: 'int' = 3, retry_delay: 'int' = 10, retry_args: 'dict[Any, Any] | None' = None, run_page_url: 'str | None' = None, repair_run: 'bool' = False, caller: 'str' = 'DatabricksExecutionTrigger') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `run_id` | `int` | `—` | pos/kw |
| `databricks_conn_id` | `str` | `—` | pos/kw |
| `polling_period_seconds` | `int` | `30` | pos/kw |
| `retry_limit` | `int` | `3` | pos/kw |
| `retry_delay` | `int` | `10` | pos/kw |
| `retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `run_page_url` | `str \| None` | `None` | pos/kw |
| `repair_run` | `bool` | `False` | pos/kw |
| `caller` | `str` | `'DatabricksExecutionTrigger'` | pos/kw |

### `DatabricksHook`

Interact with Databricks.

:param databricks_conn_id: Reference to the :ref:`Databricks connection <howto/connection:databricks>`.
:param timeout_seconds: The amount of time in seconds the requests l…

```python
airflow.providers.databricks.operators.databricks.DatabricksHook(self, databricks_conn_id: 'str' = 'databricks_default', timeout_seconds: 'int' = 180, retry_limit: 'int' = 3, retry_delay: 'float' = 1.0, retry_args: 'dict[Any, Any] | None' = None, caller: 'str' = 'DatabricksHook') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `timeout_seconds` | `int` | `180` | pos/kw |
| `retry_limit` | `int` | `3` | pos/kw |
| `retry_delay` | `float` | `1.0` | pos/kw |
| `retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `caller` | `str` | `'DatabricksHook'` | pos/kw |

### `DatabricksJobRunLink`

Constructs a link to monitor a Databricks Job Run.

```python
airflow.providers.databricks.operators.databricks.DatabricksJobRunLink(self) -> None
```

### `DatabricksNotebookOperator`

Runs a notebook on Databricks using an Airflow operator.

The DatabricksNotebookOperator allows users to launch and monitor notebook job runs on Databricks as
Airflow tasks. It can be used as a part…

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator(self, notebook_path: 'str', source: 'str', databricks_conn_id: 'str' = 'databricks_default', databricks_retry_args: 'dict[Any, Any] | None' = None, databricks_retry_delay: 'int' = 1, databricks_retry_limit: 'int' = 3, deferrable: 'bool' = False, existing_cluster_id: 'str' = '', job_cluster_key: 'str' = '', new_cluster: 'dict[str, Any] | None' = None, notebook_packages: 'list[dict[str, Any]] | None' = None, notebook_params: 'dict | None' = None, polling_period_seconds: 'int' = 5, wait_for_termination: 'bool' = True, workflow_run_metadata: 'dict | None' = None, **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `notebook_path` | `str` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `databricks_conn_id` | `str` | `'databricks_default'` | pos/kw |
| `databricks_retry_args` | `dict[Any, Any] \| None` | `None` | pos/kw |
| `databricks_retry_delay` | `int` | `1` | pos/kw |
| `databricks_retry_limit` | `int` | `3` | pos/kw |
| `deferrable` | `bool` | `False` | pos/kw |
| `existing_cluster_id` | `str` | `''` | pos/kw |
| `job_cluster_key` | `str` | `''` | pos/kw |
| `new_cluster` | `dict[str, Any] \| None` | `None` | pos/kw |
| `notebook_packages` | `list[dict[str, Any]] \| None` | `None` | pos/kw |
| `notebook_params` | `dict \| None` | `None` | pos/kw |
| `polling_period_seconds` | `int` | `5` | pos/kw |
| `wait_for_termination` | `bool` | `True` | pos/kw |
| `workflow_run_metadata` | `dict \| None` | `None` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

## Functions

### `get_provider_info`

```python
airflow.providers.databricks.get_provider_info.get_provider_info()
```

### `create_timeout_thread`

Create a timeout timer that cancels the connection and sets a timeout flag.

```python
airflow.providers.databricks.hooks.databricks_sql.create_timeout_thread(cur, execution_timeout: 'timedelta | None') -> 'tuple[threading.Timer | None, threading.Event | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cur` | `—` | `—` | pos/kw |
| `execution_timeout` | `timedelta \| None` | `—` | pos/kw |

**Returns:** `tuple[threading.Timer | None, threading.Event | None]`

## Methods

### `airflow.providers.databricks.exceptions.DatabricksSqlExecutionError` methods

### `serialize`

```python
airflow.providers.databricks.exceptions.DatabricksSqlExecutionError.serialize(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `airflow.providers.databricks.exceptions.DatabricksSqlExecutionTimeout` methods

### `serialize`

```python
airflow.providers.databricks.exceptions.DatabricksSqlExecutionTimeout.serialize(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `airflow.providers.databricks.hooks.databricks.BaseDatabricksHook` methods

### `aget_connection`

Get connection (async), given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.aget_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_conn`

Return connection for the hook.

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.get_conn(self) -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection`

Get connection, given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.get_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection_form_widgets`

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.get_connection_form_widgets() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_hook`

Return default hook for this connection id.

:param conn_id: connection id
:param hook_params: hook parameters
:return: default hook for this connection

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.get_hook(conn_id: 'str', hook_params: 'dict | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |
| `hook_params` | `dict \| None` | `None` | pos/kw |

### `get_ui_field_behaviour`

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.get_ui_field_behaviour() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `logger`

Return a logger.

```python
airflow.providers.databricks.hooks.databricks.BaseDatabricksHook.logger() -> 'Logger'
```

**Returns:** `Logger`

### `airflow.providers.databricks.hooks.databricks.ClusterState` methods

### `from_json`

```python
airflow.providers.databricks.hooks.databricks.ClusterState.from_json(data: 'str') -> 'ClusterState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `str` | `—` | pos/kw |

**Returns:** `ClusterState`

### `to_json`

```python
airflow.providers.databricks.hooks.databricks.ClusterState.to_json(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `airflow.providers.databricks.hooks.databricks.DatabricksHook` methods

### `a_get_cluster_state`

Async version of `get_cluster_state`.

:param cluster_id: id of the cluster
:return: state of the cluster

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.a_get_cluster_state(self, cluster_id: 'str') -> 'ClusterState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cluster_id` | `str` | `—` | pos/kw |

**Returns:** `ClusterState`

### `a_get_run`

Async version of `get_run`.

:param run_id: id of the run
:return: state of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.a_get_run(self, run_id: 'int') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `a_get_run_output`

Async version of `get_run_output()`.

:param run_id: id of the run
:return: output of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.a_get_run_output(self, run_id: 'int') -> 'dict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict`

### `a_get_run_page_url`

Async version of `get_run_page_url()`.

:param run_id: id of the run
:return: URL of the run page

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.a_get_run_page_url(self, run_id: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `str`

### `a_get_run_state`

Async version of `get_run_state()`.

:param run_id: id of the run
:return: state of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.a_get_run_state(self, run_id: 'int') -> 'RunState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `RunState`

### `a_get_sql_statement_state`

Async version of `get_sql_statement_state`.

:param statement_id: ID of the SQL statement
:return: state of the SQL statement

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.a_get_sql_statement_state(self, statement_id: 'str') -> 'SQLStatementState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `statement_id` | `str` | `—` | pos/kw |

**Returns:** `SQLStatementState`

### `aget_connection`

Get connection (async), given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.aget_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `cancel_all_runs`

Cancel all active runs of a job asynchronously.

:param job_id: The canonical identifier of the job to cancel all runs of

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.cancel_all_runs(self, job_id: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_id` | `int` | `—` | pos/kw |

### `cancel_run`

Cancel the run.

:param run_id: id of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.cancel_run(self, run_id: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

### `cancel_sql_statement`

Cancel the SQL statement.

:param statement_id: ID of the SQL statement

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.cancel_sql_statement(self, statement_id: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `statement_id` | `str` | `—` | pos/kw |

### `create_job`

Call the ``api/2.2/jobs/create`` endpoint.

:param json: The data used in the body of the request to the ``create`` endpoint.
:return: the job_id as an int

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.create_job(self, json: 'dict') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `json` | `dict` | `—` | pos/kw |

**Returns:** `int`

### `create_repo`

Create a Databricks Repos.

:param json: payload
:return:

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.create_repo(self, json: 'dict[str, Any]') -> 'dict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `json` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `dict`

### `delete_repo`

Delete given Databricks Repos.

:param repo_id: ID of Databricks Repos
:return:

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.delete_repo(self, repo_id: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo_id` | `str` | `—` | pos/kw |

### `delete_run`

Delete a non-active run.

:param run_id: id of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.delete_run(self, run_id: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

### `find_job_id_by_name`

Find job id by its name; if there are multiple jobs with the same name, raise AirflowException.

:param job_name: The name of the job to look up.
:return: The job_id as an int or None if no job was f…

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.find_job_id_by_name(self, job_name: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_name` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `find_pipeline_id_by_name`

Find pipeline id by its name; if multiple pipelines with the same name, raise AirflowException.

:param pipeline_name: The name of the pipeline to look up.
:return: The pipeline_id as a GUID string o…

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.find_pipeline_id_by_name(self, pipeline_name: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pipeline_name` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `get_cluster_state`

Retrieve run state of the cluster.

:param cluster_id: id of the cluster
:return: state of the cluster

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_cluster_state(self, cluster_id: 'str') -> 'ClusterState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cluster_id` | `str` | `—` | pos/kw |

**Returns:** `ClusterState`

### `get_conn`

Return connection for the hook.

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_conn(self) -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection`

Get connection, given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection_form_widgets`

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_connection_form_widgets() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_hook`

Return default hook for this connection id.

:param conn_id: connection id
:param hook_params: hook parameters
:return: default hook for this connection

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_hook(conn_id: 'str', hook_params: 'dict | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |
| `hook_params` | `dict \| None` | `None` | pos/kw |

### `get_job_id`

Retrieve job_id from run_id.

:param run_id: id of the run
:return: Job id for given Databricks run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_job_id(self, run_id: 'int') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `int`

### `get_latest_repair_id`

Get latest repair id if any exist for run_id else None.

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_latest_repair_id(self, run_id: 'int') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `int | None`

### `get_openlineage_database_dialect`

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_openlineage_database_dialect(self, _) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_openlineage_database_info`

Return Databricks-specific database info for OpenLineage namespace resolution.

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_openlineage_database_info(self, _)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `—` | `—` | pos/kw |

### `get_openlineage_default_schema`

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_openlineage_default_schema(self) -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str | None`

### `get_repo_by_path`

Obtain Repos ID by path.

:param path: path to a repository
:return: Repos ID if it exists, None if doesn't.

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_repo_by_path(self, path: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `get_run`

Retrieve run information.

:param run_id: id of the run
:return: state of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_run(self, run_id: 'int') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_run_output`

Retrieve run output of the run.

:param run_id: id of the run
:return: output of the run

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_run_output(self, run_id: 'int') -> 'dict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict`

### `get_run_page_url`

Retrieve run_page_url.

:param run_id: id of the run
:return: URL of the run page

```python
airflow.providers.databricks.hooks.databricks.DatabricksHook.get_run_page_url(self, run_id: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `str`

### `airflow.providers.databricks.hooks.databricks.RunState` methods

### `from_json`

```python
airflow.providers.databricks.hooks.databricks.RunState.from_json(data: 'str') -> 'RunState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `str` | `—` | pos/kw |

**Returns:** `RunState`

### `to_json`

```python
airflow.providers.databricks.hooks.databricks.RunState.to_json(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `airflow.providers.databricks.hooks.databricks.SQLStatementState` methods

### `from_json`

```python
airflow.providers.databricks.hooks.databricks.SQLStatementState.from_json(data: 'str') -> 'SQLStatementState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `str` | `—` | pos/kw |

**Returns:** `SQLStatementState`

### `to_json`

```python
airflow.providers.databricks.hooks.databricks.SQLStatementState.to_json(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook` methods

### `aget_connection`

Get connection (async), given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.aget_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_conn`

Return connection for the hook.

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.get_conn(self) -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection`

Get connection, given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.get_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection_form_widgets`

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.get_connection_form_widgets() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_hook`

Return default hook for this connection id.

:param conn_id: connection id
:param hook_params: hook parameters
:return: default hook for this connection

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.get_hook(conn_id: 'str', hook_params: 'dict | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |
| `hook_params` | `dict \| None` | `None` | pos/kw |

### `get_ui_field_behaviour`

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.get_ui_field_behaviour() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `logger`

Return a logger.

```python
airflow.providers.databricks.hooks.databricks_base.BaseDatabricksHook.logger() -> 'Logger'
```

**Returns:** `Logger`

### `airflow.providers.databricks.hooks.databricks_base.BearerAuth` methods

### `decode`

Create a BasicAuth object from an Authorization HTTP header.

```python
airflow.providers.databricks.hooks.databricks_base.BearerAuth.decode(auth_header: str, encoding: str = 'latin1') -> 'BasicAuth'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `auth_header` | `str` | `—` | pos/kw |
| `encoding` | `str` | `'latin1'` | pos/kw |

**Returns:** `BasicAuth`

### `encode`

Encode credentials.

```python
airflow.providers.databricks.hooks.databricks_base.BearerAuth.encode(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `from_url`

Create BasicAuth from url.

```python
airflow.providers.databricks.hooks.databricks_base.BearerAuth.from_url(url: yarl.URL, *, encoding: str = 'latin1') -> Optional[ForwardRef('BasicAuth')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `URL` | `—` | pos/kw |
| `encoding` | `str` | `'latin1'` | kw |

**Returns:** `typing.Optional[ForwardRef('BasicAuth')]`

### `airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook` methods

### `aget_connection`

Get connection (async), given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.aget_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_conn`

Return connection for the hook.

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.get_conn(self) -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection`

Get connection, given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.get_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection_form_widgets`

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.get_connection_form_widgets() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_hook`

Return default hook for this connection id.

:param conn_id: connection id
:param hook_params: hook parameters
:return: default hook for this connection

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.get_hook(conn_id: 'str', hook_params: 'dict | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |
| `hook_params` | `dict \| None` | `None` | pos/kw |

### `get_ui_field_behaviour`

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.get_ui_field_behaviour() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `logger`

Return a logger.

```python
airflow.providers.databricks.hooks.databricks_sql.BaseDatabricksHook.logger() -> 'Logger'
```

**Returns:** `Logger`

### `airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlExecutionError` methods

### `serialize`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlExecutionError.serialize(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlExecutionTimeout` methods

### `serialize`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlExecutionTimeout.serialize(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook` methods

### `aget_connection`

Get connection (async), given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.aget_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `bulk_dump`

Dump a database table into a tab-delimited file.

:param table: The name of the source table
:param tmp_file: The path of the target file

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.bulk_dump(self, table, tmp_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `table` | `—` | `—` | pos/kw |
| `tmp_file` | `—` | `—` | pos/kw |

### `bulk_load`

Load a tab-delimited file into a database table.

:param table: The name of the target table
:param tmp_file: The path of the file to load into the table

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.bulk_load(self, table, tmp_file)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `table` | `—` | `—` | pos/kw |
| `tmp_file` | `—` | `—` | pos/kw |

### `get_autocommit`

Get autocommit setting for the provided connection.

:param conn: Connection to get autocommit setting from.
:return: connection autocommit setting. True if ``autocommit`` is set
    to True on the c…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_autocommit(self, conn) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `get_conn`

Return a Databricks SQL connection object.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_conn(self) -> 'AirflowConnection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `AirflowConnection`

### `get_conn_id`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_conn_id(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_connection`

Get connection, given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection_form_widgets`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_connection_form_widgets() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_cursor`

Return a cursor.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_cursor(self) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Any`

### `get_db_log_messages`

Log all database messages sent to the client during the session.

:param conn: Connection object

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_db_log_messages(self, conn) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `—` | `—` | pos/kw |

### `get_df`

Execute the sql and returns a dataframe.

:param sql: the sql statement to be executed (str) or a list of sql statements to execute
:param parameters: The parameters to render the SQL query with.
:pa…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_df(self, sql: 'str | list[str]', parameters: 'list | tuple | Mapping[str, Any] | None' = None, *, df_type: "Literal['pandas', 'polars']" = 'pandas', **kwargs) -> 'PandasDataFrame | PolarsDataFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str \| list[str]` | `—` | pos/kw |
| `parameters` | `list \| tuple \| Mapping[str, Any] \| None` | `None` | pos/kw |
| `df_type` | `Literal['pandas', 'polars']` | `'pandas'` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `PandasDataFrame | PolarsDataFrame`

### `get_df_by_chunks`

Execute the sql and return a generator.

:param sql: the sql statement to be executed (str) or a list of sql statements to execute
:param parameters: The parameters to render the SQL query with
:para…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_df_by_chunks(self, sql: 'str | list[str]', parameters: 'list | tuple | Mapping[str, Any] | None' = None, *, chunksize: 'int', df_type: "Literal['pandas', 'polars']" = 'pandas', **kwargs) -> 'Generator[PandasDataFrame | PolarsDataFrame, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str \| list[str]` | `—` | pos/kw |
| `parameters` | `list \| tuple \| Mapping[str, Any] \| None` | `None` | pos/kw |
| `chunksize` | `int` | `—` | kw |
| `df_type` | `Literal['pandas', 'polars']` | `'pandas'` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `Generator[PandasDataFrame | PolarsDataFrame, None, None]`

### `get_first`

Execute the sql and return the first resulting row.

:param sql: the sql statement to be executed (str) or a list of sql statements to execute
:param parameters: The parameters to render the SQL quer…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_first(self, sql: 'str | list[str]', parameters: 'Iterable | Mapping[str, Any] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str \| list[str]` | `—` | pos/kw |
| `parameters` | `Iterable \| Mapping[str, Any] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `get_hook`

Return default hook for this connection id.

:param conn_id: connection id
:param hook_params: hook parameters
:return: default hook for this connection

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_hook(conn_id: 'str', hook_params: 'dict | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |
| `hook_params` | `dict \| None` | `None` | pos/kw |

### `get_openlineage_authority_part`

Get authority part from Airflow Connection.

The authority represents the hostname and port of the connection
and conforms OpenLineage naming convention for a number of databases (e.g. MySQL, Postgre…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_openlineage_authority_part(connection, default_port: 'int | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `connection` | `—` | `—` | pos/kw |
| `default_port` | `int \| None` | `None` | pos/kw |

**Returns:** `str`

### `get_openlineage_database_dialect`

Return database dialect used for SQL parsing.

For a list of supported dialects check: https://openlineage.io/docs/development/sql#sql-dialects

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_openlineage_database_dialect(self, _) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_openlineage_database_info`

Return database specific information needed to generate and parse lineage metadata.

This includes information helpful for constructing information schema query
and creating correct namespace.

:para…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_openlineage_database_info(self, connection) -> 'DatabaseInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `connection` | `—` | `—` | pos/kw |

**Returns:** `DatabaseInfo`

### `get_openlineage_database_specific_lineage`

Emit separate OpenLineage events for each Databricks query, based on executed query IDs.

If a single query ID is present, also add an `ExternalQueryRunFacet` to the returned lineage metadata.

Note…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_openlineage_database_specific_lineage(self, task_instance) -> 'OperatorLineage | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `task_instance` | `—` | `—` | pos/kw |

**Returns:** `OperatorLineage | None`

### `get_openlineage_default_schema`

Return default schema specific to database.

.. seealso::
    - :class:`airflow.providers.openlineage.sqlparser.SQLParser`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_openlineage_default_schema(self) -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str | None`

### `get_pandas_df`

Execute the sql and returns a pandas dataframe.

:param sql: the sql statement to be executed (str) or a list of sql statements to execute
:param parameters: The parameters to render the SQL query wi…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_pandas_df(self, sql, parameters: 'list | tuple | Mapping[str, Any] | None' = None, **kwargs) -> 'PandasDataFrame'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `—` | `—` | pos/kw |
| `parameters` | `list \| tuple \| Mapping[str, Any] \| None` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `PandasDataFrame`

### `get_pandas_df_by_chunks`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_pandas_df_by_chunks(self, sql, parameters: 'list | tuple | Mapping[str, Any] | None' = None, *, chunksize: 'int', **kwargs) -> 'Generator[PandasDataFrame, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `—` | `—` | pos/kw |
| `parameters` | `list \| tuple \| Mapping[str, Any] \| None` | `None` | pos/kw |
| `chunksize` | `int` | `—` | kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `Generator[PandasDataFrame, None, None]`

### `get_records`

Execute the sql and return a set of records.

:param sql: the sql statement to be executed (str) or a list of sql statements to execute
:param parameters: The parameters to render the SQL query with.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_records(self, sql: 'str | list[str]', parameters: 'Iterable | Mapping[str, Any] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str \| list[str]` | `—` | pos/kw |
| `parameters` | `Iterable \| Mapping[str, Any] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `get_sqlalchemy_engine`

Get an sqlalchemy_engine object.

:param engine_kwargs: Kwargs used in :func:`~sqlalchemy.create_engine`.
:return: the created engine.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_sqlalchemy_engine(self, engine_kwargs=None) -> 'Engine'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `engine_kwargs` | `—` | `None` | pos/kw |

**Returns:** `Engine`

### `get_table_schema`

Return column names and types for a table using SQLAlchemy Inspector.

:param table_name: Name of the table.
:param schema: Optional schema/namespace name.
:return: List of dicts with ``name`` and ``…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_table_schema(self, table_name: 'str', schema: 'str | None' = None) -> 'list[dict[str, str]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `table_name` | `str` | `—` | pos/kw |
| `schema` | `str \| None` | `None` | pos/kw |

**Returns:** `list[dict[str, str]]`

### `get_ui_field_behaviour`

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_ui_field_behaviour() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_uri`

Extract the URI from the connection.

:return: the extracted uri.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.get_uri(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `insert_rows`

Insert a collection of tuples into a table.

Rows are inserted in chunks, each chunk (of size ``commit_every``) is
done in a new transaction.

:param table: Name of the target table
:param rows: The…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.insert_rows(self, table, rows, target_fields=None, commit_every=1000, replace=False, *, executemany=False, fast_executemany=False, autocommit=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `table` | `—` | `—` | pos/kw |
| `rows` | `—` | `—` | pos/kw |
| `target_fields` | `—` | `None` | pos/kw |
| `commit_every` | `—` | `1000` | pos/kw |
| `replace` | `—` | `False` | pos/kw |
| `executemany` | `—` | `False` | kw |
| `fast_executemany` | `—` | `False` | kw |
| `autocommit` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `logger`

Return a logger.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.logger() -> 'Logger'
```

**Returns:** `Logger`

### `run`

Run a command or a list of commands.

Pass a list of SQL statements to the SQL parameter to get them to
execute sequentially.

:param sql: the sql statement to be executed (str) or a list of
    sql…

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.run(self, sql: 'str | Iterable[str]', autocommit: 'bool' = False, parameters: 'Iterable | Mapping[str, Any] | None' = None, handler: 'Callable[[Any], T] | None' = None, split_statements: 'bool' = True, return_last: 'bool' = True, execution_timeout: 'timedelta | None' = None) -> 'tuple | list[tuple] | list[list[tuple] | tuple] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str \| Iterable[str]` | `—` | pos/kw |
| `autocommit` | `bool` | `False` | pos/kw |
| `parameters` | `Iterable \| Mapping[str, Any] \| None` | `None` | pos/kw |
| `handler` | `Callable[[Any], T] \| None` | `None` | pos/kw |
| `split_statements` | `bool` | `True` | pos/kw |
| `return_last` | `bool` | `True` | pos/kw |
| `execution_timeout` | `timedelta \| None` | `None` | pos/kw |

**Returns:** `tuple | list[tuple] | list[list[tuple] | tuple] | None`

### `set_autocommit`

Set the autocommit flag on the connection.

```python
airflow.providers.databricks.hooks.databricks_sql.DatabricksSqlHook.set_autocommit(self, conn, autocommit)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `—` | `—` | pos/kw |
| `autocommit` | `—` | `—` | pos/kw |

### `airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator` methods

### `add_inlets`

Set inlets to this operator.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.add_inlets(self, inlets: 'Iterable[Any]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `inlets` | `Iterable[Any]` | `—` | pos/kw |

### `add_outlets`

Define the outlets of this operator.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.add_outlets(self, outlets: 'Iterable[Any]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outlets` | `Iterable[Any]` | `—` | pos/kw |

### `as_setup`

Mark a task as setup task.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.as_setup(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_teardown`

Mark a task as teardown and set its setups as direct relatives.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.as_teardown(self, *, setups: 'BaseOperator | Iterable[BaseOperator] | None' = None, on_failure_fail_dagrun: 'bool | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `setups` | `BaseOperator \| Iterable[BaseOperator] \| None` | `None` | kw |
| `on_failure_fail_dagrun` | `bool \| None` | `None` | kw |

### `defer`

Mark this Operator "deferred", suspending its execution until the provided trigger fires an event.

This is achieved by raising a special exception (TaskDeferred)
which is caught in the main _execute…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.defer(self, *, trigger: 'BaseTrigger', method_name: 'str', kwargs: 'dict[str, Any] | None' = None, timeout: 'timedelta | int | float | None' = None) -> 'NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `trigger` | `BaseTrigger` | `—` | kw |
| `method_name` | `str` | `—` | kw |
| `kwargs` | `dict[str, Any] \| None` | `None` | kw |
| `timeout` | `timedelta \| int \| float \| None` | `None` | kw |

**Returns:** `NoReturn`

### `dry_run`

Perform dry run for the operator - just render template fields.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.dry_run(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `execute`

Derive when creating an operator.

The main method to execute the task. Context is the same dictionary used
as when rendering jinja templates.

Refer to get_template_context for more context.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.execute(self, context: 'Context') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `Context` | `—` | pos/kw |

**Returns:** `int`

### `expand_start_trigger_args`

Get the start_trigger_args value of the current abstract operator.

Since a BaseOperator is not mapped to begin with, this simply returns
the original value of start_trigger_args.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.expand_start_trigger_args(self, *, context: 'Context') -> 'StartTriggerArgs | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `Context` | `—` | kw |

**Returns:** `StartTriggerArgs | None`

### `get_closest_mapped_task_group`

Get the mapped task group "closest" to this task in the Dag.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_closest_mapped_task_group(self) -> 'MappedTaskGroup | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MappedTaskGroup | None`

### `get_dag`

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_dag(self) -> 'DAG | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `DAG | None`

### `get_direct_relative_ids`

Get set of the direct relative ids to the current task, upstream or downstream.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_direct_relative_ids(self, upstream: 'bool' = False) -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | pos/kw |

**Returns:** `set[str]`

### `get_direct_relatives`

Get list of the direct relatives to the current task, upstream or downstream.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_direct_relatives(self, upstream: 'bool' = False) -> 'Iterable[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | pos/kw |

**Returns:** `Iterable[Task]`

### `get_flat_relative_ids`

Get a flat set of relative IDs, upstream or downstream.

Will recurse each relative found in the direction specified.

:param upstream: Whether to look for upstream or downstream relatives.
 :param d…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_flat_relative_ids(self, *, upstream: 'bool' = False, depth: 'int | None' = None) -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | kw |
| `depth` | `int \| None` | `None` | kw |

**Returns:** `set[str]`

### `get_flat_relatives`

Get a flat list of relatives, either upstream or downstream.

:param upstream: Whether to look for upstream or downstream relatives.
:param depth: Maximum number of levels to traverse. If None, trave…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_flat_relatives(self, upstream: 'bool' = False, depth: 'int | None' = None) -> 'Collection[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | pos/kw |
| `depth` | `int \| None` | `None` | pos/kw |

**Returns:** `Collection[Task]`

### `get_needs_expansion`

Return true if the task is MappedOperator or is in a mapped task group.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_needs_expansion(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `get_serialized_fields`

Stringified Dags and operators contain exactly these fields.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_serialized_fields()
```

### `get_template_env`

Get the template environment for rendering templates.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_template_env(self, dag: 'DAG | None' = None) -> 'jinja2.Environment'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dag` | `DAG \| None` | `None` | pos/kw |

**Returns:** `jinja2.Environment`

### `get_upstreams_follow_setups`

All upstreams and, for each upstream setup, its respective teardowns.

:param depth: Maximum number of levels to traverse. If None, traverses all levels.
    Must be non-negative.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_upstreams_follow_setups(self, depth: 'int | None' = None) -> 'Iterable[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `depth` | `int \| None` | `None` | pos/kw |

**Returns:** `Iterable[Task]`

### `get_upstreams_only_setups`

Return relevant upstream setups.

This method is meant to be used when we are checking task dependencies where we need
to wait for all the upstream setups to complete before we can run the task.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_upstreams_only_setups(self) -> 'Iterable[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterable[Task]`

### `get_upstreams_only_setups_and_teardowns`

Only *relevant* upstream setups and their teardowns.

This method is meant to be used when we are clearing the task (non-upstream) and we need
to add in the *relevant* setups and their teardowns.

Re…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.get_upstreams_only_setups_and_teardowns(self) -> 'Iterable[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterable[Task]`

### `has_dag`

Return True if the Operator has been assigned to a Dag.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.has_dag(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `iter_mapped_dependants`

Return mapped nodes that depend on the current task the expansion.

For now, this walks the entire Dag to find mapped nodes that has this
current task as an upstream. We cannot use ``downstream_list`…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.iter_mapped_dependants(self) -> 'Iterator[MappedOperator | MappedTaskGroup]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[MappedOperator | MappedTaskGroup]`

### `iter_mapped_task_groups`

Return mapped task groups this task belongs to.

Groups are returned from the innermost to the outmost.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.iter_mapped_task_groups(self) -> 'Iterator[MappedTaskGroup]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Iterator[MappedTaskGroup]`

### `on_kill`

Override this method to clean up subprocesses when a task instance gets killed.

Any use of the threading, subprocess or multiprocessing module within an
operator needs to be cleaned up, or it will l…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.on_kill(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `partial`

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.partial(*, task_id: 'str', dag: 'DAG | None' = None, task_group: 'TaskGroup | None' = None, params: 'collections.abc.MutableMapping | None' = None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `task_id` | `str` | `—` | kw |
| `dag` | `DAG \| None` | `None` | kw |
| `task_group` | `TaskGroup \| None` | `None` | kw |
| `params` | `collections.abc.MutableMapping \| None` | `None` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `post_execute`

Execute right after self.execute() is called.

It is passed the execution context and any results returned by the operator.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.post_execute(self, context: 'Any', result: 'Any' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `Any` | `—` | pos/kw |
| `result` | `Any` | `None` | pos/kw |

### `pre_execute`

Execute right before self.execute() is called.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.pre_execute(self, context: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `Any` | `—` | pos/kw |

### `prepare_for_execution`

Lock task for execution to disable custom action in ``__setattr__`` and return a copy.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.prepare_for_execution(self) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Self`

### `prepare_template`

Execute after the templated fields get replaced by their content.

If you need your object to alter the content of the file before the
template is rendered, it should override this method to do so.

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.prepare_template(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `render_template`

Render a templated string.

If *content* is a collection holding multiple templated strings, strings
in the collection will be templated recursively.

:param content: Content to template. Only string…

```python
airflow.providers.databricks.operators.databricks.DatabricksCreateJobsOperator.render_template(self, content: 'Any', context: 'Context', jinja_env: 'jinja2.Environment | None' = None, seen_oids: 'set[int] | None' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `Any` | `—` | pos/kw |
| `context` | `Context` | `—` | pos/kw |
| `jinja_env` | `jinja2.Environment \| None` | `None` | pos/kw |
| `seen_oids` | `set[int] \| None` | `None` | pos/kw |

**Returns:** `Any`

### `airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger` methods

### `cleanup`

Cleanup the trigger.

Called when the trigger is no longer needed, and it's being removed
from the active triggerer process.

This method follows the async/await pattern to allow to run the cleanup
i…

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger.cleanup(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `logger`

Return a logger.

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger.logger() -> 'Logger'
```

**Returns:** `Logger`

### `on_kill`

Cancel the Databricks run when the trigger is cancelled by a user action.

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger.on_kill(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `repr`

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger.repr(classpath: 'str', kwargs: 'dict[str, Any]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classpath` | `str` | `—` | pos/kw |
| `kwargs` | `dict[str, Any]` | `—` | pos/kw |

### `run`

Run the trigger in an asynchronous context.

The trigger should yield an Event whenever it wants to fire off
an event, and return None if it is finished. Single-event triggers
should thus yield and t…

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger.run(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `serialize`

Return the information needed to reconstruct this Trigger.

:return: Tuple of (class path, keyword arguments needed to re-instantiate).

```python
airflow.providers.databricks.operators.databricks.DatabricksExecutionTrigger.serialize(self) -> 'tuple[str, dict[str, Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str, dict[str, Any]]`

### `airflow.providers.databricks.operators.databricks.DatabricksHook` methods

### `a_get_cluster_state`

Async version of `get_cluster_state`.

:param cluster_id: id of the cluster
:return: state of the cluster

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.a_get_cluster_state(self, cluster_id: 'str') -> 'ClusterState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cluster_id` | `str` | `—` | pos/kw |

**Returns:** `ClusterState`

### `a_get_run`

Async version of `get_run`.

:param run_id: id of the run
:return: state of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.a_get_run(self, run_id: 'int') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `a_get_run_output`

Async version of `get_run_output()`.

:param run_id: id of the run
:return: output of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.a_get_run_output(self, run_id: 'int') -> 'dict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict`

### `a_get_run_page_url`

Async version of `get_run_page_url()`.

:param run_id: id of the run
:return: URL of the run page

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.a_get_run_page_url(self, run_id: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `str`

### `a_get_run_state`

Async version of `get_run_state()`.

:param run_id: id of the run
:return: state of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.a_get_run_state(self, run_id: 'int') -> 'RunState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `RunState`

### `a_get_sql_statement_state`

Async version of `get_sql_statement_state`.

:param statement_id: ID of the SQL statement
:return: state of the SQL statement

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.a_get_sql_statement_state(self, statement_id: 'str') -> 'SQLStatementState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `statement_id` | `str` | `—` | pos/kw |

**Returns:** `SQLStatementState`

### `aget_connection`

Get connection (async), given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.aget_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `cancel_all_runs`

Cancel all active runs of a job asynchronously.

:param job_id: The canonical identifier of the job to cancel all runs of

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.cancel_all_runs(self, job_id: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_id` | `int` | `—` | pos/kw |

### `cancel_run`

Cancel the run.

:param run_id: id of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.cancel_run(self, run_id: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

### `cancel_sql_statement`

Cancel the SQL statement.

:param statement_id: ID of the SQL statement

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.cancel_sql_statement(self, statement_id: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `statement_id` | `str` | `—` | pos/kw |

### `create_job`

Call the ``api/2.2/jobs/create`` endpoint.

:param json: The data used in the body of the request to the ``create`` endpoint.
:return: the job_id as an int

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.create_job(self, json: 'dict') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `json` | `dict` | `—` | pos/kw |

**Returns:** `int`

### `create_repo`

Create a Databricks Repos.

:param json: payload
:return:

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.create_repo(self, json: 'dict[str, Any]') -> 'dict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `json` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `dict`

### `delete_repo`

Delete given Databricks Repos.

:param repo_id: ID of Databricks Repos
:return:

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.delete_repo(self, repo_id: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo_id` | `str` | `—` | pos/kw |

### `delete_run`

Delete a non-active run.

:param run_id: id of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.delete_run(self, run_id: 'int') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

### `find_job_id_by_name`

Find job id by its name; if there are multiple jobs with the same name, raise AirflowException.

:param job_name: The name of the job to look up.
:return: The job_id as an int or None if no job was f…

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.find_job_id_by_name(self, job_name: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_name` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `find_pipeline_id_by_name`

Find pipeline id by its name; if multiple pipelines with the same name, raise AirflowException.

:param pipeline_name: The name of the pipeline to look up.
:return: The pipeline_id as a GUID string o…

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.find_pipeline_id_by_name(self, pipeline_name: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pipeline_name` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `get_cluster_state`

Retrieve run state of the cluster.

:param cluster_id: id of the cluster
:return: state of the cluster

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_cluster_state(self, cluster_id: 'str') -> 'ClusterState'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cluster_id` | `str` | `—` | pos/kw |

**Returns:** `ClusterState`

### `get_conn`

Return connection for the hook.

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_conn(self) -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection`

Get connection, given connection id.

:param conn_id: connection id
:return: connection

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_connection(conn_id: 'str') -> 'Connection'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |

**Returns:** `Connection`

### `get_connection_form_widgets`

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_connection_form_widgets() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_hook`

Return default hook for this connection id.

:param conn_id: connection id
:param hook_params: hook parameters
:return: default hook for this connection

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_hook(conn_id: 'str', hook_params: 'dict | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_id` | `str` | `—` | pos/kw |
| `hook_params` | `dict \| None` | `None` | pos/kw |

### `get_job_id`

Retrieve job_id from run_id.

:param run_id: id of the run
:return: Job id for given Databricks run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_job_id(self, run_id: 'int') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `int`

### `get_latest_repair_id`

Get latest repair id if any exist for run_id else None.

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_latest_repair_id(self, run_id: 'int') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `int | None`

### `get_openlineage_database_dialect`

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_openlineage_database_dialect(self, _) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_openlineage_database_info`

Return Databricks-specific database info for OpenLineage namespace resolution.

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_openlineage_database_info(self, _)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `_` | `—` | `—` | pos/kw |

### `get_openlineage_default_schema`

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_openlineage_default_schema(self) -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str | None`

### `get_repo_by_path`

Obtain Repos ID by path.

:param path: path to a repository
:return: Repos ID if it exists, None if doesn't.

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_repo_by_path(self, path: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `get_run`

Retrieve run information.

:param run_id: id of the run
:return: state of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_run(self, run_id: 'int') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_run_output`

Retrieve run output of the run.

:param run_id: id of the run
:return: output of the run

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_run_output(self, run_id: 'int') -> 'dict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `dict`

### `get_run_page_url`

Retrieve run_page_url.

:param run_id: id of the run
:return: URL of the run page

```python
airflow.providers.databricks.operators.databricks.DatabricksHook.get_run_page_url(self, run_id: 'int') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `int` | `—` | pos/kw |

**Returns:** `str`

### `airflow.providers.databricks.operators.databricks.DatabricksJobRunLink` methods

### `get_link`

Link to external system.

:param operator: The Airflow operator object this link is associated to.
:param ti_key: TaskInstance ID to return link for.
:return: link to external system

```python
airflow.providers.databricks.operators.databricks.DatabricksJobRunLink.get_link(self, operator: 'BaseOperator', *, ti_key: 'TaskInstanceKey') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `operator` | `BaseOperator` | `—` | pos/kw |
| `ti_key` | `TaskInstanceKey` | `—` | kw |

**Returns:** `str`

### `airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator` methods

### `add_inlets`

Set inlets to this operator.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.add_inlets(self, inlets: 'Iterable[Any]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `inlets` | `Iterable[Any]` | `—` | pos/kw |

### `add_outlets`

Define the outlets of this operator.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.add_outlets(self, outlets: 'Iterable[Any]')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `outlets` | `Iterable[Any]` | `—` | pos/kw |

### `as_setup`

Mark a task as setup task.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.as_setup(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_teardown`

Mark a task as teardown and set its setups as direct relatives.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.as_teardown(self, *, setups: 'BaseOperator | Iterable[BaseOperator] | None' = None, on_failure_fail_dagrun: 'bool | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `setups` | `BaseOperator \| Iterable[BaseOperator] \| None` | `None` | kw |
| `on_failure_fail_dagrun` | `bool \| None` | `None` | kw |

### `defer`

Mark this Operator "deferred", suspending its execution until the provided trigger fires an event.

This is achieved by raising a special exception (TaskDeferred)
which is caught in the main _execute…

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.defer(self, *, trigger: 'BaseTrigger', method_name: 'str', kwargs: 'dict[str, Any] | None' = None, timeout: 'timedelta | int | float | None' = None) -> 'NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `trigger` | `BaseTrigger` | `—` | kw |
| `method_name` | `str` | `—` | kw |
| `kwargs` | `dict[str, Any] \| None` | `None` | kw |
| `timeout` | `timedelta \| int \| float \| None` | `None` | kw |

**Returns:** `NoReturn`

### `dry_run`

Perform dry run for the operator - just render template fields.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.dry_run(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `execute`

Execute the operator. Launch the job and monitor it if wait_for_termination is set to True.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.execute(self, context: 'Context') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `Context` | `—` | pos/kw |

### `execute_complete`

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.execute_complete(self, context: 'dict | None', event: 'dict') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `dict \| None` | `—` | pos/kw |
| `event` | `dict` | `—` | pos/kw |

### `expand_start_trigger_args`

Get the start_trigger_args value of the current abstract operator.

Since a BaseOperator is not mapped to begin with, this simply returns
the original value of start_trigger_args.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.expand_start_trigger_args(self, *, context: 'Context') -> 'StartTriggerArgs | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `Context` | `—` | kw |

**Returns:** `StartTriggerArgs | None`

### `get_closest_mapped_task_group`

Get the mapped task group "closest" to this task in the Dag.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_closest_mapped_task_group(self) -> 'MappedTaskGroup | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `MappedTaskGroup | None`

### `get_dag`

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_dag(self) -> 'DAG | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `DAG | None`

### `get_direct_relative_ids`

Get set of the direct relative ids to the current task, upstream or downstream.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_direct_relative_ids(self, upstream: 'bool' = False) -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | pos/kw |

**Returns:** `set[str]`

### `get_direct_relatives`

Get list of the direct relatives to the current task, upstream or downstream.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_direct_relatives(self, upstream: 'bool' = False) -> 'Iterable[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | pos/kw |

**Returns:** `Iterable[Task]`

### `get_flat_relative_ids`

Get a flat set of relative IDs, upstream or downstream.

Will recurse each relative found in the direction specified.

:param upstream: Whether to look for upstream or downstream relatives.
 :param d…

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_flat_relative_ids(self, *, upstream: 'bool' = False, depth: 'int | None' = None) -> 'set[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | kw |
| `depth` | `int \| None` | `None` | kw |

**Returns:** `set[str]`

### `get_flat_relatives`

Get a flat list of relatives, either upstream or downstream.

:param upstream: Whether to look for upstream or downstream relatives.
:param depth: Maximum number of levels to traverse. If None, trave…

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_flat_relatives(self, upstream: 'bool' = False, depth: 'int | None' = None) -> 'Collection[Task]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `upstream` | `bool` | `False` | pos/kw |
| `depth` | `int \| None` | `None` | pos/kw |

**Returns:** `Collection[Task]`

### `get_needs_expansion`

Return true if the task is MappedOperator or is in a mapped task group.

:meta private:

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_needs_expansion(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `get_serialized_fields`

Stringified Dags and operators contain exactly these fields.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_serialized_fields()
```

### `get_template_env`

Get the template environment for rendering templates.

```python
airflow.providers.databricks.operators.databricks.DatabricksNotebookOperator.get_template_env(self, dag: 'DAG | None' = None) -> 'jinja2.Environment'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dag` | `DAG \| None` | `None` | pos/kw |

**Returns:** `jinja2.Environment`


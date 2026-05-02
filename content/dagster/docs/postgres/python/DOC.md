---
name: postgres
description: "Dagster PostgreSQL storage package for persistent run, event log, and schedule state in Dagster OSS"
metadata:
  languages: "python"
  versions: "0.28.18"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "dagster,python,postgres,postgresql,storage,orchestration,PostgresEventLogStorage,PostgresRunStorage,PostgresScheduleStorage,environ,per,DagsterPostgresStorage,config_type,from_config_value,register_instance,add_dynamic_partitions,add_pending_step,alembic_version,all_asset_keys,assign_pending_steps,can_claim_from_pending,can_read_asset_status_cache,can_write_asset_status_cache,check_concurrency_claim,claim_concurrency_slot,create_clean_storage,default_run_scoped_event_tailer_offset,delete_concurrency_limit,delete_dynamic_partition,delete_events,delete_events_for_run,dispose,enable_secondary_index,end_watch,fetch_failed_materializations,fetch_materializations,fetch_observations,fetch_run_status_changes,free_concurrency_slot_for_step,free_concurrency_slots_for_run,get_asset_check_execution_history,get_asset_check_partition_info,get_asset_check_state,add_backfill,add_daemon_heartbeat,add_execution_plan_snapshot,add_historical_run,add_job_snapshot,add_run,add_run_tags,add_run_telemetry,add_snapshot,connect,delete_run,fetchall,fetchone,get_backfill,get_backfills,get_backfills_count,get_cursor_values,get_daemon_heartbeats,get_execution_plan_snapshot,get_job_snapshot,get_run_group,get_run_ids,get_run_partition_data,get_run_records,get_run_storage_id,add_auto_materialize_asset_evaluations,add_instigator_state,all_instigator_state,create_tick,delete_instigator_state,execute,get_auto_materialize_asset_evaluations,get_auto_materialize_evaluations_for_evaluation_id,get_batch_ticks,get_instigator_state,get_tick,get_ticks,has_built_index,has_instigators_table,has_secondary_index_table,mark_index_built,migrate,optimize,optimize_for_webserver,purge_asset_evaluations,purge_ticks,update_instigator_state,update_tick,AwsWifTokenProvider,get_token,AzureWifTokenProvider,GcpWifTokenProvider,PgTokenProvider,create_token_provider,register_do_connect_hook,create_pg_connection,create_pg_engine,get_token_provider_from_config,pg_alembic_config,pg_url_from_config,retry_pg_connection_fn,retry_pg_creation_fn,set_pg_statement_timeout"
---

# dagster — postgres

## Install

```bash
pip install dagster
```

## Imports

```python
import dagster
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `DagsterPostgresStorage` | Class | Postgres-backed dagster storage.  Users should not directly instantiate this cl… |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `register_instance` | Method |  |
| `PostgresEventLogStorage` | Class | Postgres-backed event log storage.  Users should not directly instantiate this… |
| `add_dynamic_partitions` | Method | Add a partition for the specified dynamic partitions definition. |
| `add_pending_step` | Method |  |
| `alembic_version` | Method |  |
| `all_asset_keys` | Method |  |
| `assign_pending_steps` | Method |  |
| `can_claim_from_pending` | Method |  |
| `can_read_asset_status_cache` | Method | Whether the storage can access cached status information for each asset. |
| `can_write_asset_status_cache` | Method | Whether the storage is able to write to that cache. |
| `check_concurrency_claim` | Method | Claim concurrency slots for step. |
| `claim_concurrency_slot` | Method | Claim concurrency slot for step.  Args:     concurrency_keys (str): The concurr… |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `create_clean_storage` | Method |  |
| `default_run_scoped_event_tailer_offset` | Method |  |
| `delete_concurrency_limit` | Method | Delete a concurrency limit and its associated slots.  Args:     concurrency_key… |
| `delete_dynamic_partition` | Method | Delete a partition for the specified dynamic partitions definition. |
| `delete_events` | Method | Remove events for a given run id. |
| `delete_events_for_run` | Method |  |
| `dispose` | Method | Explicit lifecycle management. |
| `enable_secondary_index` | Method | This method marks an event_log data migration as complete, to indicate that a s… |
| `end_watch` | Method | Call this method to stop watching. |
| `fetch_failed_materializations` | Method |  |
| `fetch_materializations` | Method |  |
| `fetch_observations` | Method |  |
| `fetch_run_status_changes` | Method |  |
| `free_concurrency_slot_for_step` | Method | Frees concurrency slots for a given run/step. |
| `free_concurrency_slots_for_run` | Method | Frees concurrency slots for a given run. |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `get_asset_check_execution_history` | Method | Get executions for one asset check, sorted by recency. |
| `get_asset_check_partition_info` | Method | Get asset check partition records with execution status and planned run info. |
| `get_asset_check_state` | Method |  |
| `PostgresRunStorage` | Class | Postgres-backed run storage.  Users should not directly instantiate this class;… |
| `add_backfill` | Method | Add partition backfill to run storage. |
| `add_daemon_heartbeat` | Method | Called on a regular interval by the daemon. |
| `add_execution_plan_snapshot` | Method | Add an execution plan snapshot to the run store.  Execution plan snapshots are… |
| `add_historical_run` | Method | Add a historical run to storage. |
| `add_job_snapshot` | Method | Add a pipeline snapshot to the run store.  Pipeline snapshots are content-addre… |
| `add_run` | Method | Add a run to storage.  If a run already exists with the same ID, raise DagsterR… |
| `add_run_tags` | Method | Add additional tags for a pipeline run.  Args:     run_id (str)     new_tags (D… |
| `add_run_telemetry` | Method | Not implemented in base class. Should be implemented in subclasses that support… |
| `add_snapshot` | Method | Add a snapshot to the storage.  Args:     snapshot (Union[PipelineSnapshot, Exe… |
| `alembic_version` | Method |  |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `connect` | Method | Context manager yielding a sqlalchemy.engine.Connection. |
| `create_clean_storage` | Method |  |
| `delete_run` | Method | Remove a run from storage. |
| `dispose` | Method | Explicit lifecycle management. |
| `fetchall` | Method |  |
| `fetchone` | Method |  |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `get_backfill` | Method | Get the partition backfill of the given backfill id. |
| `get_backfills` | Method | Get a list of partition backfills. |
| `get_backfills_count` | Method | Return the number of backfills present in the storage that match the given filt… |
| `get_cursor_values` | Method | Retrieve the value for a given key in the current deployment. |
| `get_daemon_heartbeats` | Method | Latest heartbeats of all daemon types. |
| `get_execution_plan_snapshot` | Method | Fetch a snapshot by ID.  Args:     execution_plan_snapshot_id (str)  Returns:… |
| `get_job_snapshot` | Method | Fetch a snapshot by ID.  Args:     job_snapshot_id (str)  Returns:     Pipeline… |
| `get_run_group` | Method | Get the run group to which a given run belongs.  Args:     run_id (str): If the… |
| `get_run_ids` | Method | Return all the run IDs for runs present in the storage that match the given fil… |
| `get_run_partition_data` | Method | Get run partition data for a given partitioned job. |
| `get_run_records` | Method | Return a list of run records stored in the run storage, sorted by the given col… |
| `get_run_storage_id` | Method |  |
| `PostgresScheduleStorage` | Class | Postgres-backed run storage.  Users should not directly instantiate this class;… |
| `add_auto_materialize_asset_evaluations` | Method | Add asset policy evaluations to storage. |
| `add_instigator_state` | Method | Add an instigator state to storage.  Args:     state (InstigatorState): The sta… |
| `alembic_version` | Method |  |
| `all_instigator_state` | Method | Return all InstigationStates present in storage.  Args:     repository_origin_i… |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `connect` | Method | Context manager yielding a sqlalchemy.engine.Connection. |
| `create_clean_storage` | Method |  |
| `create_tick` | Method | Add a tick to storage.  Args:     tick_data (TickData): The tick to add |
| `delete_instigator_state` | Method | Delete a state in storage.  Args:     origin_id (str): The id of the instigator… |
| `dispose` | Method | Explicit lifecycle management. |
| `execute` | Method |  |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `get_auto_materialize_asset_evaluations` | Method | Get the policy evaluations for a given asset.  Args:     asset_key (AssetKey):… |
| `get_auto_materialize_evaluations_for_evaluation_id` | Method | Get all policy evaluations for a given evaluation ID.  Args:     evaluation_id… |
| `get_batch_ticks` | Method |  |
| `get_instigator_state` | Method | Return the instigator state for the given id.  Args:     origin_id (str): The u… |
| `get_tick` | Method | Get the tick for a given evaluation tick id.  Args:     tick_id (str): The id o… |
| `get_ticks` | Method | Get the ticks for a given instigator.  Args:     origin_id (str): The id of the… |
| `has_built_index` | Method |  |
| `has_instigators_table` | Method |  |
| `has_secondary_index_table` | Method |  |
| `mark_index_built` | Method |  |
| `migrate` | Method | Call this method to run any required data migrations. |
| `optimize` | Method | Call this method to run any optional data migrations for optimized reads. |
| `optimize_for_webserver` | Method | Allows for optimizing database connection / use in the context of a long lived… |
| `purge_asset_evaluations` | Method | Wipe evaluations before a certain timestamp.  Args:     before (datetime): All… |
| `purge_ticks` | Method | Wipe ticks for an instigator for a certain status and timestamp.  Args:     ori… |
| `register_instance` | Method |  |
| `update_instigator_state` | Method | Update an instigator state in storage.  Args:     state (InstigatorState): The… |
| `update_tick` | Method | Update a tick already in storage.  Args:     tick (InstigatorTick): The tick to… |
| `AwsWifTokenProvider` | Class | AWS IAM / IRSA token provider for RDS.  Uses ``boto3`` to generate an RDS auth… |
| `get_token` | Method | Return a valid token, refreshing if expired or about to expire. |
| `AzureWifTokenProvider` | Class | Azure Workload Identity Federation token provider.  Uses ``DefaultAzureCredenti… |
| `get_token` | Method | Return a valid token, refreshing if expired or about to expire. |
| `GcpWifTokenProvider` | Class | GCP Workload Identity Federation token provider.  Uses Application Default Cred… |
| `get_token` | Method | Return a valid token, refreshing if expired or about to expire. |
| `PgTokenProvider` | Class | Abstract base for providers that supply short-lived database access tokens.  Su… |
| `get_token` | Method | Return a valid token, refreshing if expired or about to expire. |
| `create_token_provider` | Function | Create a token provider from the ``auth_provider`` config block. |
| `register_do_connect_hook` | Function | Register a ``do_connect`` event listener that injects a fresh token as the pass… |
| `PostgresEventLogStorage` | Class | Postgres-backed event log storage.  Users should not directly instantiate this… |
| `add_dynamic_partitions` | Method | Add a partition for the specified dynamic partitions definition. |
| `add_pending_step` | Method |  |
| `alembic_version` | Method |  |
| `all_asset_keys` | Method |  |
| `assign_pending_steps` | Method |  |
| `can_claim_from_pending` | Method |  |
| `can_read_asset_status_cache` | Method | Whether the storage can access cached status information for each asset. |
| `can_write_asset_status_cache` | Method | Whether the storage is able to write to that cache. |
| `check_concurrency_claim` | Method | Claim concurrency slots for step. |
| `claim_concurrency_slot` | Method | Claim concurrency slot for step.  Args:     concurrency_keys (str): The concurr… |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `create_clean_storage` | Method |  |
| `default_run_scoped_event_tailer_offset` | Method |  |
| `delete_concurrency_limit` | Method | Delete a concurrency limit and its associated slots.  Args:     concurrency_key… |
| `delete_dynamic_partition` | Method | Delete a partition for the specified dynamic partitions definition. |
| `delete_events` | Method | Remove events for a given run id. |
| `delete_events_for_run` | Method |  |
| `dispose` | Method | Explicit lifecycle management. |
| `enable_secondary_index` | Method | This method marks an event_log data migration as complete, to indicate that a s… |
| `end_watch` | Method | Call this method to stop watching. |
| `fetch_failed_materializations` | Method |  |
| `fetch_materializations` | Method |  |
| `fetch_observations` | Method |  |
| `fetch_run_status_changes` | Method |  |
| `free_concurrency_slot_for_step` | Method | Frees concurrency slots for a given run/step. |
| `free_concurrency_slots_for_run` | Method | Frees concurrency slots for a given run. |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `get_asset_check_execution_history` | Method | Get executions for one asset check, sorted by recency. |
| `get_asset_check_partition_info` | Method | Get asset check partition records with execution status and planned run info. |
| `get_asset_check_state` | Method |  |
| `PostgresEventLogStorage` | Class | Postgres-backed event log storage.  Users should not directly instantiate this… |
| `add_dynamic_partitions` | Method | Add a partition for the specified dynamic partitions definition. |
| `add_pending_step` | Method |  |
| `alembic_version` | Method |  |
| `all_asset_keys` | Method |  |
| `assign_pending_steps` | Method |  |
| `can_claim_from_pending` | Method |  |
| `can_read_asset_status_cache` | Method | Whether the storage can access cached status information for each asset. |
| `can_write_asset_status_cache` | Method | Whether the storage is able to write to that cache. |
| `check_concurrency_claim` | Method | Claim concurrency slots for step. |
| `claim_concurrency_slot` | Method | Claim concurrency slot for step.  Args:     concurrency_keys (str): The concurr… |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `create_clean_storage` | Method |  |
| `default_run_scoped_event_tailer_offset` | Method |  |
| `delete_concurrency_limit` | Method | Delete a concurrency limit and its associated slots.  Args:     concurrency_key… |
| `delete_dynamic_partition` | Method | Delete a partition for the specified dynamic partitions definition. |
| `delete_events` | Method | Remove events for a given run id. |
| `delete_events_for_run` | Method |  |
| `dispose` | Method | Explicit lifecycle management. |
| `enable_secondary_index` | Method | This method marks an event_log data migration as complete, to indicate that a s… |
| `end_watch` | Method | Call this method to stop watching. |
| `fetch_failed_materializations` | Method |  |
| `fetch_materializations` | Method |  |
| `fetch_observations` | Method |  |
| `fetch_run_status_changes` | Method |  |
| `free_concurrency_slot_for_step` | Method | Frees concurrency slots for a given run/step. |
| `free_concurrency_slots_for_run` | Method | Frees concurrency slots for a given run. |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `get_asset_check_execution_history` | Method | Get executions for one asset check, sorted by recency. |
| `get_asset_check_partition_info` | Method | Get asset check partition records with execution status and planned run info. |
| `get_asset_check_state` | Method |  |
| `create_pg_connection` | Function |  |
| `create_pg_engine` | Function | Create a SQLAlchemy engine, optionally with WIF token injection via the ``do_co… |
| `get_token_provider_from_config` | Function | Extract and build a token provider from config, or return ``None`` for password… |
| `pg_alembic_config` | Function |  |
| `pg_url_from_config` | Function |  |
| `retry_pg_connection_fn` | Function | Reusable retry logic for any psycopg2/sqlalchemy PG connection functions that m… |
| `retry_pg_creation_fn` | Function |  |
| `set_pg_statement_timeout` | Function |  |
| `PostgresRunStorage` | Class | Postgres-backed run storage.  Users should not directly instantiate this class;… |
| `add_backfill` | Method | Add partition backfill to run storage. |
| `add_daemon_heartbeat` | Method | Called on a regular interval by the daemon. |
| `add_execution_plan_snapshot` | Method | Add an execution plan snapshot to the run store.  Execution plan snapshots are… |
| `add_historical_run` | Method | Add a historical run to storage. |
| `add_job_snapshot` | Method | Add a pipeline snapshot to the run store.  Pipeline snapshots are content-addre… |
| `add_run` | Method | Add a run to storage.  If a run already exists with the same ID, raise DagsterR… |
| `add_run_tags` | Method | Add additional tags for a pipeline run.  Args:     run_id (str)     new_tags (D… |
| `add_run_telemetry` | Method | Not implemented in base class. Should be implemented in subclasses that support… |
| `add_snapshot` | Method | Add a snapshot to the storage.  Args:     snapshot (Union[PipelineSnapshot, Exe… |
| `alembic_version` | Method |  |
| `config_type` | Method | Get the config type against which to validate a config yaml fragment.  The only… |
| `connect` | Method | Context manager yielding a sqlalchemy.engine.Connection. |
| `create_clean_storage` | Method |  |
| `delete_run` | Method | Remove a run from storage. |
| `dispose` | Method | Explicit lifecycle management. |
| `fetchall` | Method |  |
| `fetchone` | Method |  |
| `from_config_value` | Method | Create an instance of the ConfigurableClass from a validated config value.  The… |
| `get_backfill` | Method | Get the partition backfill of the given backfill id. |
| `get_backfills` | Method | Get a list of partition backfills. |
| `get_backfills_count` | Method | Return the number of backfills present in the storage that match the given filt… |
| `get_cursor_values` | Method | Retrieve the value for a given key in the current deployment. |

## Classes

### `DagsterPostgresStorage`

Postgres-backed dagster storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-daemon`` load, based on the value…

```python
dagster_postgres.DagsterPostgresStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

### `PostgresEventLogStorage`

Postgres-backed event log storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-graphql`` load, based on the va…

```python
dagster_postgres.PostgresEventLogStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

### `PostgresRunStorage`

Postgres-backed run storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-graphql`` load, based on the values i…

```python
dagster_postgres.PostgresRunStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

### `PostgresScheduleStorage`

Postgres-backed run storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-graphql`` load, based on the values i…

```python
dagster_postgres.PostgresScheduleStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

### `AwsWifTokenProvider`

AWS IAM / IRSA token provider for RDS.

Uses ``boto3`` to generate an RDS auth token.  Requires the hostname,
port, username, and AWS region from the connection config.

```python
dagster_postgres.auth.AwsWifTokenProvider(self, hostname: str, port: int, username: str, region: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hostname` | `str` | `—` | pos/kw |
| `port` | `int` | `—` | pos/kw |
| `username` | `str` | `—` | pos/kw |
| `region` | `str` | `—` | pos/kw |

### `AzureWifTokenProvider`

Azure Workload Identity Federation token provider.

Uses ``DefaultAzureCredential`` which automatically picks up the
``AZURE_CLIENT_ID``, ``AZURE_TENANT_ID``, and
``AZURE_FEDERATED_TOKEN_FILE`` envir…

```python
dagster_postgres.auth.AzureWifTokenProvider(self, scope: str = 'https://ossrdbms-aad.database.windows.net/.default') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `scope` | `str` | `'https://ossrdbms-aad.database.windows.net/.default'` | pos/kw |

### `GcpWifTokenProvider`

GCP Workload Identity Federation token provider.

Uses Application Default Credentials (ADC), which automatically picks up
the projected service account token on GKE pods.

```python
dagster_postgres.auth.GcpWifTokenProvider(self) -> None
```

### `PgTokenProvider`

Abstract base for providers that supply short-lived database access tokens.

Subclasses implement ``_fetch_token`` to obtain a fresh token from their
respective cloud provider.  Caching and thread-sa…

```python
dagster_postgres.auth.PgTokenProvider(self) -> None
```

### `PostgresEventLogStorage`

Postgres-backed event log storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-graphql`` load, based on the va…

```python
dagster_postgres.event_log.PostgresEventLogStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

### `PostgresEventLogStorage`

Postgres-backed event log storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-graphql`` load, based on the va…

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

### `PostgresRunStorage`

Postgres-backed run storage.

Users should not directly instantiate this class; it is instantiated by internal machinery when
``dagster-webserver`` and ``dagster-graphql`` load, based on the values i…

```python
dagster_postgres.run_storage.PostgresRunStorage(self, postgres_url: str, should_autocreate_tables: bool = True, inst_data: dagster._serdes.config_class.ConfigurableClassData | None = None, token_provider: 'PgTokenProvider | None' = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `None` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |

## Functions

### `create_token_provider`

Create a token provider from the ``auth_provider`` config block.

```python
dagster_postgres.auth.create_token_provider(auth_config: dict[str, typing.Any], db_config: dict[str, typing.Any] | None = None) -> dagster_postgres.auth.PgTokenProvider
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `auth_config` | `dict` | `—` | pos/kw |
| `db_config` | `dict[str, typing.Any] \| None` | `None` | pos/kw |

**Returns:** `<class 'dagster_postgres.auth.PgTokenProvider'>`

### `register_do_connect_hook`

Register a ``do_connect`` event listener that injects a fresh token as
the password before each DBAPI connection.

```python
dagster_postgres.auth.register_do_connect_hook(engine: sqlalchemy.engine.base.Engine, token_provider: dagster_postgres.auth.PgTokenProvider) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `engine` | `Engine` | `—` | pos/kw |
| `token_provider` | `PgTokenProvider` | `—` | pos/kw |

### `create_pg_connection`

```python
dagster_postgres.event_log.event_log.create_pg_connection(engine: sqlalchemy.engine.base.Engine) -> collections.abc.Iterator[sqlalchemy.engine.base.Connection]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `engine` | `Engine` | `—` | pos/kw |

**Returns:** `collections.abc.Iterator[sqlalchemy.engine.base.Connection]`

### `create_pg_engine`

Create a SQLAlchemy engine, optionally with WIF token injection via
the ``do_connect`` event hook.

```python
dagster_postgres.event_log.event_log.create_pg_engine(postgres_url: str, token_provider: 'PgTokenProvider | None' = None, **engine_kwargs: Any) -> sqlalchemy.engine.base.Engine
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `token_provider` | `PgTokenProvider \| None` | `None` | pos/kw |
| `engine_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `<class 'sqlalchemy.engine.base.Engine'>`

### `get_token_provider_from_config`

Extract and build a token provider from config, or return ``None`` for
password auth.

```python
dagster_postgres.event_log.event_log.get_token_provider_from_config(config_value: collections.abc.Mapping[str, typing.Any]) -> 'PgTokenProvider | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_value` | `Mapping` | `—` | pos/kw |

**Returns:** `PgTokenProvider | None`

### `pg_alembic_config`

```python
dagster_postgres.event_log.event_log.pg_alembic_config(dunder_file: str, script_location: str | None = None) -> alembic.config.Config
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dunder_file` | `str` | `—` | pos/kw |
| `script_location` | `str \| None` | `None` | pos/kw |

**Returns:** `<class 'alembic.config.Config'>`

### `pg_url_from_config`

```python
dagster_postgres.event_log.event_log.pg_url_from_config(config_value: collections.abc.Mapping[str, typing.Any]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_value` | `Mapping` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `retry_pg_connection_fn`

Reusable retry logic for any psycopg2/sqlalchemy PG connection functions that may fail.
Intended to be used anywhere we connect to PG, to gracefully handle transient connection issues.

```python
dagster_postgres.event_log.event_log.retry_pg_connection_fn(fn: collections.abc.Callable[[], ~T], retry_limit: int = 5, retry_wait: float = 0.2) -> ~T
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fn` | `Callable` | `—` | pos/kw |
| `retry_limit` | `int` | `5` | pos/kw |
| `retry_wait` | `float` | `0.2` | pos/kw |

**Returns:** `~T`

### `retry_pg_creation_fn`

```python
dagster_postgres.event_log.event_log.retry_pg_creation_fn(fn: collections.abc.Callable[[], ~T], retry_limit: int = 5, retry_wait: float = 0.2) -> ~T
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `fn` | `Callable` | `—` | pos/kw |
| `retry_limit` | `int` | `5` | pos/kw |
| `retry_wait` | `float` | `0.2` | pos/kw |

**Returns:** `~T`

### `set_pg_statement_timeout`

```python
dagster_postgres.event_log.event_log.set_pg_statement_timeout(conn: Any, millis: int)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn` | `Any` | `—` | pos/kw |
| `millis` | `int` | `—` | pos/kw |

## Methods

### `dagster_postgres.DagsterPostgresStorage` methods

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.DagsterPostgresStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.DagsterPostgresStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: dagster._core.storage.config.PostgresStorageConfig) -> 'DagsterPostgresStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `PostgresStorageConfig` | `—` | pos/kw |

**Returns:** `DagsterPostgresStorage`

### `register_instance`

```python
dagster_postgres.DagsterPostgresStorage.register_instance(self, instance: ~T_DagsterInstance) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `instance` | `T_DagsterInstance` | `—` | pos/kw |

### `dagster_postgres.PostgresEventLogStorage` methods

### `add_dynamic_partitions`

Add a partition for the specified dynamic partitions definition.

```python
dagster_postgres.PostgresEventLogStorage.add_dynamic_partitions(self, partitions_def_name: str, partition_keys: collections.abc.Sequence[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partitions_def_name` | `str` | `—` | pos/kw |
| `partition_keys` | `Sequence` | `—` | pos/kw |

### `add_pending_step`

```python
dagster_postgres.PostgresEventLogStorage.add_pending_step(self, concurrency_key: str, run_id: str, step_key: str, priority: int | None = None, should_assign: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |
| `priority` | `int \| None` | `None` | pos/kw |
| `should_assign` | `bool` | `False` | pos/kw |

### `alembic_version`

```python
dagster_postgres.PostgresEventLogStorage.alembic_version(self) -> tuple[str | None, str | tuple[str, ...] | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str | None, str | tuple[str, ...] | None]`

### `all_asset_keys`

```python
dagster_postgres.PostgresEventLogStorage.all_asset_keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `assign_pending_steps`

```python
dagster_postgres.PostgresEventLogStorage.assign_pending_steps(self, concurrency_keys: collections.abc.Sequence[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_keys` | `Sequence` | `—` | pos/kw |

### `can_claim_from_pending`

```python
dagster_postgres.PostgresEventLogStorage.can_claim_from_pending(self, concurrency_key: str, run_id: str, step_key: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

### `can_read_asset_status_cache`

Whether the storage can access cached status information for each asset.

```python
dagster_postgres.PostgresEventLogStorage.can_read_asset_status_cache(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `can_write_asset_status_cache`

Whether the storage is able to write to that cache.

```python
dagster_postgres.PostgresEventLogStorage.can_write_asset_status_cache(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_concurrency_claim`

Claim concurrency slots for step.

```python
dagster_postgres.PostgresEventLogStorage.check_concurrency_claim(self, concurrency_key: str, run_id: str, step_key: str) -> dagster._utils.concurrency.ConcurrencyClaimStatus
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

**Returns:** `<class 'dagster._utils.concurrency.ConcurrencyClaimStatus'>`

### `claim_concurrency_slot`

Claim concurrency slot for step.

Args:
    concurrency_keys (str): The concurrency key to claim.
    run_id (str): The run id to claim for.
    step_key (str): The step key to claim for.

```python
dagster_postgres.PostgresEventLogStorage.claim_concurrency_slot(self, concurrency_key: str, run_id: str, step_key: str, priority: int | None = None) -> dagster._utils.concurrency.ConcurrencyClaimStatus
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |
| `priority` | `int \| None` | `None` | pos/kw |

**Returns:** `<class 'dagster._utils.concurrency.ConcurrencyClaimStatus'>`

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.PostgresEventLogStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `create_clean_storage`

```python
dagster_postgres.PostgresEventLogStorage.create_clean_storage(conn_string: str, should_autocreate_tables: bool = True) -> 'PostgresEventLogStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_string` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |

**Returns:** `PostgresEventLogStorage`

### `default_run_scoped_event_tailer_offset`

```python
dagster_postgres.PostgresEventLogStorage.default_run_scoped_event_tailer_offset(self) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'int'>`

### `delete_concurrency_limit`

Delete a concurrency limit and its associated slots.

Args:
    concurrency_key (str): The key to delete.

```python
dagster_postgres.PostgresEventLogStorage.delete_concurrency_limit(self, concurrency_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |

### `delete_dynamic_partition`

Delete a partition for the specified dynamic partitions definition.

```python
dagster_postgres.PostgresEventLogStorage.delete_dynamic_partition(self, partitions_def_name: str, partition_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partitions_def_name` | `str` | `—` | pos/kw |
| `partition_key` | `str` | `—` | pos/kw |

### `delete_events`

Remove events for a given run id.

```python
dagster_postgres.PostgresEventLogStorage.delete_events(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `delete_events_for_run`

```python
dagster_postgres.PostgresEventLogStorage.delete_events_for_run(self, conn: sqlalchemy.engine.base.Connection, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `Connection` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `dispose`

Explicit lifecycle management.

```python
dagster_postgres.PostgresEventLogStorage.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `enable_secondary_index`

This method marks an event_log data migration as complete, to indicate that a summary
data migration is complete.

```python
dagster_postgres.PostgresEventLogStorage.enable_secondary_index(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `end_watch`

Call this method to stop watching.

```python
dagster_postgres.PostgresEventLogStorage.end_watch(self, run_id: str, handler: collections.abc.Callable[[dagster._core.events.log.EventLogEntry, str], None]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `handler` | `Callable` | `—` | pos/kw |

### `fetch_failed_materializations`

```python
dagster_postgres.PostgresEventLogStorage.fetch_failed_materializations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_materializations`

```python
dagster_postgres.PostgresEventLogStorage.fetch_materializations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_observations`

```python
dagster_postgres.PostgresEventLogStorage.fetch_observations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_run_status_changes`

```python
dagster_postgres.PostgresEventLogStorage.fetch_run_status_changes(self, records_filter: dagster._core.events.DagsterEventType | dagster._core.event_api.RunStatusChangeRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.events.DagsterEventType \| dagster._core.event_api.RunStatusChangeRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `free_concurrency_slot_for_step`

Frees concurrency slots for a given run/step.

```python
dagster_postgres.PostgresEventLogStorage.free_concurrency_slot_for_step(self, run_id: str, step_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

### `free_concurrency_slots_for_run`

Frees concurrency slots for a given run.

```python
dagster_postgres.PostgresEventLogStorage.free_concurrency_slots_for_run(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.PostgresEventLogStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: collections.abc.Mapping[str, typing.Any]) -> 'PostgresEventLogStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `Mapping` | `—` | pos/kw |

**Returns:** `PostgresEventLogStorage`

### `get_asset_check_execution_history`

Get executions for one asset check, sorted by recency.

```python
dagster_postgres.PostgresEventLogStorage.get_asset_check_execution_history(self, check_key: dagster._core.definitions.asset_key.AssetCheckKey, limit: int, cursor: int | None = None, status: Optional[AbstractSet[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecordStatus]] = None, partition_filter: dagster._core.event_api.PartitionKeyFilter | None = None) -> collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecord]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `check_key` | `AssetCheckKey` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `int \| None` | `None` | pos/kw |
| `status` | `Optional` | `None` | pos/kw |
| `partition_filter` | `dagster._core.event_api.PartitionKeyFilter \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecord]`

### `get_asset_check_partition_info`

Get asset check partition records with execution status and planned run info.

```python
dagster_postgres.PostgresEventLogStorage.get_asset_check_partition_info(self, keys: collections.abc.Sequence[dagster._core.definitions.asset_key.AssetCheckKey], after_storage_id: int | None = None, partition_keys: collections.abc.Sequence[str] | None = None) -> collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckPartitionInfo]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `Sequence` | `—` | pos/kw |
| `after_storage_id` | `int \| None` | `None` | pos/kw |
| `partition_keys` | `collections.abc.Sequence[str] \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckPartitionInfo]`

### `get_asset_check_state`

```python
dagster_postgres.PostgresEventLogStorage.get_asset_check_state(self, keys: collections.abc.Sequence[tuple[dagster._core.definitions.asset_key.AssetCheckKey, dagster._core.definitions.partitions.definition.partitions_definition.PartitionsDefinition | None]]) -> collections.abc.Mapping[dagster._core.definitions.asset_key.AssetCheckKey, 'AssetCheckState']
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `Sequence` | `—` | pos/kw |

**Returns:** `collections.abc.Mapping[dagster._core.definitions.asset_key.AssetCheckKey, 'AssetCheckState']`

### `dagster_postgres.PostgresRunStorage` methods

### `add_backfill`

Add partition backfill to run storage.

```python
dagster_postgres.PostgresRunStorage.add_backfill(self, partition_backfill: dagster._core.execution.backfill.PartitionBackfill) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partition_backfill` | `PartitionBackfill` | `—` | pos/kw |

### `add_daemon_heartbeat`

Called on a regular interval by the daemon.

```python
dagster_postgres.PostgresRunStorage.add_daemon_heartbeat(self, daemon_heartbeat: dagster._daemon.types.DaemonHeartbeat) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `daemon_heartbeat` | `DaemonHeartbeat` | `—` | pos/kw |

### `add_execution_plan_snapshot`

Add an execution plan snapshot to the run store.

Execution plan snapshots are content-addressable, meaning
that the ID for a snapshot is a hash based on the
body of the snapshot. This function retur…

```python
dagster_postgres.PostgresRunStorage.add_execution_plan_snapshot(self, execution_plan_snapshot: dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `execution_plan_snapshot` | `ExecutionPlanSnapshot` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `add_historical_run`

Add a historical run to storage.

```python
dagster_postgres.PostgresRunStorage.add_historical_run(self, dagster_run: dagster._core.storage.dagster_run.DagsterRun, run_creation_time: datetime.datetime) -> dagster._core.storage.dagster_run.DagsterRun
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dagster_run` | `DagsterRun` | `—` | pos/kw |
| `run_creation_time` | `datetime` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.storage.dagster_run.DagsterRun'>`

### `add_job_snapshot`

Add a pipeline snapshot to the run store.

Pipeline snapshots are content-addressable, meaning
that the ID for a snapshot is a hash based on the
body of the snapshot. This function returns
that snaps…

```python
dagster_postgres.PostgresRunStorage.add_job_snapshot(self, job_snapshot: dagster._core.snap.job_snapshot.JobSnap) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_snapshot` | `JobSnap` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `add_run`

Add a run to storage.

If a run already exists with the same ID, raise DagsterRunAlreadyExists
If the run's snapshot ID does not exist raise DagsterSnapshotDoesNotExist

Args:
    dagster_run (Dagste…

```python
dagster_postgres.PostgresRunStorage.add_run(self, dagster_run: dagster._core.storage.dagster_run.DagsterRun) -> dagster._core.storage.dagster_run.DagsterRun
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dagster_run` | `DagsterRun` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.storage.dagster_run.DagsterRun'>`

### `add_run_tags`

Add additional tags for a pipeline run.

Args:
    run_id (str)
    new_tags (Dict[string, string])

```python
dagster_postgres.PostgresRunStorage.add_run_tags(self, run_id: str, new_tags: collections.abc.Mapping[str, str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `new_tags` | `Mapping` | `—` | pos/kw |

### `add_run_telemetry`

Not implemented in base class. Should be implemented in subclasses that support telemetry.

```python
dagster_postgres.PostgresRunStorage.add_run_telemetry(self, run_telemetry: dagster._core.execution.telemetry.RunTelemetryData, tags: dict[str, str] | None = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_telemetry` | `RunTelemetryData` | `—` | pos/kw |
| `tags` | `dict[str, str] \| None` | `None` | pos/kw |

### `add_snapshot`

Add a snapshot to the storage.

Args:
    snapshot (Union[PipelineSnapshot, ExecutionPlanSnapshot])

```python
dagster_postgres.PostgresRunStorage.add_snapshot(self, snapshot: dagster._core.snap.job_snapshot.JobSnap | dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `snapshot` | `dagster._core.snap.job_snapshot.JobSnap \| dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot` | `—` | pos/kw |

### `alembic_version`

```python
dagster_postgres.PostgresRunStorage.alembic_version(self) -> tuple[str | None, str | tuple[str, ...] | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str | None, str | tuple[str, ...] | None]`

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.PostgresRunStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `connect`

Context manager yielding a sqlalchemy.engine.Connection.

```python
dagster_postgres.PostgresRunStorage.connect(self) -> ContextManager[sqlalchemy.engine.base.Connection, bool | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.ContextManager[sqlalchemy.engine.base.Connection, bool | None]`

### `create_clean_storage`

```python
dagster_postgres.PostgresRunStorage.create_clean_storage(postgres_url: str, should_autocreate_tables: bool = True) -> 'PostgresRunStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |

**Returns:** `PostgresRunStorage`

### `delete_run`

Remove a run from storage.

```python
dagster_postgres.PostgresRunStorage.delete_run(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `dispose`

Explicit lifecycle management.

```python
dagster_postgres.PostgresRunStorage.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fetchall`

```python
dagster_postgres.PostgresRunStorage.fetchall(self, query: Any) -> collections.abc.Sequence[typing.Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Any` | `—` | pos/kw |

**Returns:** `collections.abc.Sequence[typing.Any]`

### `fetchone`

```python
dagster_postgres.PostgresRunStorage.fetchone(self, query: Any) -> typing.Any | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Any` | `—` | pos/kw |

**Returns:** `typing.Any | None`

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.PostgresRunStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: dagster._core.storage.config.PostgresStorageConfig)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `PostgresStorageConfig` | `—` | pos/kw |

### `get_backfill`

Get the partition backfill of the given backfill id.

```python
dagster_postgres.PostgresRunStorage.get_backfill(self, backfill_id: str) -> dagster._core.execution.backfill.PartitionBackfill | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `backfill_id` | `str` | `—` | pos/kw |

**Returns:** `dagster._core.execution.backfill.PartitionBackfill | None`

### `get_backfills`

Get a list of partition backfills.

```python
dagster_postgres.PostgresRunStorage.get_backfills(self, filters: dagster._core.execution.backfill.BulkActionsFilter | None = None, cursor: str | None = None, limit: int | None = None, status: dagster._core.execution.backfill.BulkActionStatus | None = None) -> collections.abc.Sequence[dagster._core.execution.backfill.PartitionBackfill]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filters` | `dagster._core.execution.backfill.BulkActionsFilter \| None` | `None` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |
| `status` | `dagster._core.execution.backfill.BulkActionStatus \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.execution.backfill.PartitionBackfill]`

### `get_backfills_count`

Return the number of backfills present in the storage that match the given filters.

Args:
    filters (Optional[BulkActionsFilter]) -- The filter by which to filter backfills

Returns:
    int: The…

```python
dagster_postgres.PostgresRunStorage.get_backfills_count(self, filters: dagster._core.execution.backfill.BulkActionsFilter | None = None) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filters` | `dagster._core.execution.backfill.BulkActionsFilter \| None` | `None` | pos/kw |

**Returns:** `<class 'int'>`

### `get_cursor_values`

Retrieve the value for a given key in the current deployment.

```python
dagster_postgres.PostgresRunStorage.get_cursor_values(self, keys: set[str]) -> collections.abc.Mapping[str, str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `set` | `—` | pos/kw |

**Returns:** `collections.abc.Mapping[str, str]`

### `get_daemon_heartbeats`

Latest heartbeats of all daemon types.

```python
dagster_postgres.PostgresRunStorage.get_daemon_heartbeats(self) -> collections.abc.Mapping[str, dagster._daemon.types.DaemonHeartbeat]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `collections.abc.Mapping[str, dagster._daemon.types.DaemonHeartbeat]`

### `get_execution_plan_snapshot`

Fetch a snapshot by ID.

Args:
    execution_plan_snapshot_id (str)

Returns:
    ExecutionPlanSnapshot

```python
dagster_postgres.PostgresRunStorage.get_execution_plan_snapshot(self, execution_plan_snapshot_id: str) -> dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `execution_plan_snapshot_id` | `str` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot'>`

### `get_job_snapshot`

Fetch a snapshot by ID.

Args:
    job_snapshot_id (str)

Returns:
    PipelineSnapshot

```python
dagster_postgres.PostgresRunStorage.get_job_snapshot(self, job_snapshot_id: str) -> dagster._core.snap.job_snapshot.JobSnap
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_snapshot_id` | `str` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.snap.job_snapshot.JobSnap'>`

### `get_run_group`

Get the run group to which a given run belongs.

Args:
    run_id (str): If the corresponding run is the descendant of some root run (i.e., there
        is a root_run_id on the :py:class:`PipelineRu…

```python
dagster_postgres.PostgresRunStorage.get_run_group(self, run_id: str) -> tuple[str, collections.abc.Sequence[dagster._core.storage.dagster_run.DagsterRun]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

**Returns:** `tuple[str, collections.abc.Sequence[dagster._core.storage.dagster_run.DagsterRun]]`

### `get_run_ids`

Return all the run IDs for runs present in the storage that match the given filters.

Args:
    filters (Optional[RunsFilter]) -- The
        :py:class:`~dagster._core.storage.pipeline_run.RunsFilter…

```python
dagster_postgres.PostgresRunStorage.get_run_ids(self, filters: dagster._core.storage.dagster_run.RunsFilter | None = None, cursor: str | None = None, limit: int | None = None) -> collections.abc.Sequence[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filters` | `dagster._core.storage.dagster_run.RunsFilter \| None` | `None` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[str]`

### `get_run_partition_data`

Get run partition data for a given partitioned job.

```python
dagster_postgres.PostgresRunStorage.get_run_partition_data(self, runs_filter: dagster._core.storage.dagster_run.RunsFilter) -> collections.abc.Sequence[dagster._core.storage.dagster_run.RunPartitionData]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `runs_filter` | `RunsFilter` | `—` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.dagster_run.RunPartitionData]`

### `get_run_records`

Return a list of run records stored in the run storage, sorted by the given column in given order.

Args:
    filters (Optional[RunsFilter]): the filter by which to filter runs.
    limit (Optional[i…

```python
dagster_postgres.PostgresRunStorage.get_run_records(self, filters: dagster._core.storage.dagster_run.RunsFilter | None = None, limit: int | None = None, order_by: str | None = None, ascending: bool = False, cursor: str | None = None, bucket_by: dagster._core.storage.dagster_run.JobBucket | dagster._core.storage.dagster_run.TagBucket | None = None) -> collections.abc.Sequence[dagster._core.storage.dagster_run.RunRecord]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filters` | `dagster._core.storage.dagster_run.RunsFilter \| None` | `None` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |
| `order_by` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `bucket_by` | `dagster._core.storage.dagster_run.JobBucket \| dagster._core.storage.dagster_run.TagBucket \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.dagster_run.RunRecord]`

### `get_run_storage_id`

```python
dagster_postgres.PostgresRunStorage.get_run_storage_id(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dagster_postgres.PostgresScheduleStorage` methods

### `add_auto_materialize_asset_evaluations`

Add asset policy evaluations to storage.

```python
dagster_postgres.PostgresScheduleStorage.add_auto_materialize_asset_evaluations(self, evaluation_id: int, asset_evaluations: collections.abc.Sequence[dagster._core.definitions.declarative_automation.serialized_objects.AutomationConditionEvaluationWithRunIds[dagster._core.definitions.asset_key.AssetKey | dagster._core.definitions.asset_key.AssetCheckKey]])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `evaluation_id` | `int` | `—` | pos/kw |
| `asset_evaluations` | `Sequence` | `—` | pos/kw |

### `add_instigator_state`

Add an instigator state to storage.

Args:
    state (InstigatorState): The state to add

```python
dagster_postgres.PostgresScheduleStorage.add_instigator_state(self, state: dagster._core.scheduler.instigation.InstigatorState) -> dagster._core.scheduler.instigation.InstigatorState
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `state` | `InstigatorState` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.scheduler.instigation.InstigatorState'>`

### `alembic_version`

```python
dagster_postgres.PostgresScheduleStorage.alembic_version(self) -> tuple[str | None, str | tuple[str, ...] | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str | None, str | tuple[str, ...] | None]`

### `all_instigator_state`

Return all InstigationStates present in storage.

Args:
    repository_origin_id (Optional[str]): The ExternalRepository target id to scope results to
    repository_selector_id (Optional[str]): The…

```python
dagster_postgres.PostgresScheduleStorage.all_instigator_state(self, repository_origin_id: str | None = None, repository_selector_id: str | None = None, instigator_type: dagster._core.definitions.run_request.InstigatorType | None = None, instigator_statuses: set[dagster._core.scheduler.instigation.InstigatorStatus] | None = None) -> collections.abc.Sequence[dagster._core.scheduler.instigation.InstigatorState]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repository_origin_id` | `str \| None` | `None` | pos/kw |
| `repository_selector_id` | `str \| None` | `None` | pos/kw |
| `instigator_type` | `dagster._core.definitions.run_request.InstigatorType \| None` | `None` | pos/kw |
| `instigator_statuses` | `set[dagster._core.scheduler.instigation.InstigatorStatus] \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.scheduler.instigation.InstigatorState]`

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.PostgresScheduleStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `connect`

Context manager yielding a sqlalchemy.engine.Connection.

```python
dagster_postgres.PostgresScheduleStorage.connect(self, run_id: str | None = None) -> ContextManager[sqlalchemy.engine.base.Connection, bool | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str \| None` | `None` | pos/kw |

**Returns:** `typing.ContextManager[sqlalchemy.engine.base.Connection, bool | None]`

### `create_clean_storage`

```python
dagster_postgres.PostgresScheduleStorage.create_clean_storage(postgres_url: str, should_autocreate_tables: bool = True) -> 'PostgresScheduleStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |

**Returns:** `PostgresScheduleStorage`

### `create_tick`

Add a tick to storage.

Args:
    tick_data (TickData): The tick to add

```python
dagster_postgres.PostgresScheduleStorage.create_tick(self, tick_data: dagster._core.scheduler.instigation.TickData) -> dagster._core.scheduler.instigation.InstigatorTick
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tick_data` | `TickData` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.scheduler.instigation.InstigatorTick'>`

### `delete_instigator_state`

Delete a state in storage.

Args:
    origin_id (str): The id of the instigator target to delete
    selector_id (str): The logical instigator identifier

```python
dagster_postgres.PostgresScheduleStorage.delete_instigator_state(self, origin_id: str, selector_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_id` | `str` | `—` | pos/kw |
| `selector_id` | `str` | `—` | pos/kw |

### `dispose`

Explicit lifecycle management.

```python
dagster_postgres.PostgresScheduleStorage.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `execute`

```python
dagster_postgres.PostgresScheduleStorage.execute(self, query: Any) -> collections.abc.Sequence[typing.Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Any` | `—` | pos/kw |

**Returns:** `collections.abc.Sequence[typing.Any]`

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.PostgresScheduleStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: dagster._core.storage.config.PostgresStorageConfig) -> 'PostgresScheduleStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `PostgresStorageConfig` | `—` | pos/kw |

**Returns:** `PostgresScheduleStorage`

### `get_auto_materialize_asset_evaluations`

Get the policy evaluations for a given asset.

Args:
    asset_key (AssetKey): The asset key to query
    limit (Optional[int]): The maximum number of evaluations to return
    cursor (Optional[int])…

```python
dagster_postgres.PostgresScheduleStorage.get_auto_materialize_asset_evaluations(self, key: dagster._core.definitions.asset_key.AssetKey | dagster._core.definitions.asset_key.AssetCheckKey, limit: int, cursor: int | None = None) -> collections.abc.Sequence[dagster._core.scheduler.instigation.AutoMaterializeAssetEvaluationRecord]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.definitions.asset_key.AssetCheckKey` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `int \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.scheduler.instigation.AutoMaterializeAssetEvaluationRecord]`

### `get_auto_materialize_evaluations_for_evaluation_id`

Get all policy evaluations for a given evaluation ID.

Args:
    evaluation_id (int): The evaluation ID to query.

```python
dagster_postgres.PostgresScheduleStorage.get_auto_materialize_evaluations_for_evaluation_id(self, evaluation_id: int) -> collections.abc.Sequence[dagster._core.scheduler.instigation.AutoMaterializeAssetEvaluationRecord]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `evaluation_id` | `int` | `—` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.scheduler.instigation.AutoMaterializeAssetEvaluationRecord]`

### `get_batch_ticks`

```python
dagster_postgres.PostgresScheduleStorage.get_batch_ticks(self, selector_ids: collections.abc.Sequence[str], limit: int | None = None, statuses: collections.abc.Sequence[dagster._core.scheduler.instigation.TickStatus] | None = None) -> collections.abc.Mapping[str, collections.abc.Sequence[dagster._core.scheduler.instigation.InstigatorTick]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `selector_ids` | `Sequence` | `—` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |
| `statuses` | `collections.abc.Sequence[dagster._core.scheduler.instigation.TickStatus] \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Mapping[str, collections.abc.Sequence[dagster._core.scheduler.instigation.InstigatorTick]]`

### `get_instigator_state`

Return the instigator state for the given id.

Args:
    origin_id (str): The unique instigator identifier
    selector_id (str): The logical instigator identifier

```python
dagster_postgres.PostgresScheduleStorage.get_instigator_state(self, origin_id: str, selector_id: str) -> dagster._core.scheduler.instigation.InstigatorState | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_id` | `str` | `—` | pos/kw |
| `selector_id` | `str` | `—` | pos/kw |

**Returns:** `dagster._core.scheduler.instigation.InstigatorState | None`

### `get_tick`

Get the tick for a given evaluation tick id.

Args:
    tick_id (str): The id of the tick to query.

Returns:
    InstigatorTick: The tick for the given id.

```python
dagster_postgres.PostgresScheduleStorage.get_tick(self, tick_id: int) -> dagster._core.scheduler.instigation.InstigatorTick
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tick_id` | `int` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.scheduler.instigation.InstigatorTick'>`

### `get_ticks`

Get the ticks for a given instigator.

Args:
    origin_id (str): The id of the instigator target
    selector_id (str): The logical instigator identifier

```python
dagster_postgres.PostgresScheduleStorage.get_ticks(self, origin_id: str, selector_id: str, before: float | None = None, after: float | None = None, limit: int | None = None, statuses: collections.abc.Sequence[dagster._core.scheduler.instigation.TickStatus] | None = None) -> collections.abc.Sequence[dagster._core.scheduler.instigation.InstigatorTick]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_id` | `str` | `—` | pos/kw |
| `selector_id` | `str` | `—` | pos/kw |
| `before` | `float \| None` | `None` | pos/kw |
| `after` | `float \| None` | `None` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |
| `statuses` | `collections.abc.Sequence[dagster._core.scheduler.instigation.TickStatus] \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.scheduler.instigation.InstigatorTick]`

### `has_built_index`

```python
dagster_postgres.PostgresScheduleStorage.has_built_index(self, migration_name: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `migration_name` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `has_instigators_table`

```python
dagster_postgres.PostgresScheduleStorage.has_instigators_table(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `has_secondary_index_table`

```python
dagster_postgres.PostgresScheduleStorage.has_secondary_index_table(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `mark_index_built`

```python
dagster_postgres.PostgresScheduleStorage.mark_index_built(self, migration_name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `migration_name` | `str` | `—` | pos/kw |

### `migrate`

Call this method to run any required data migrations.

```python
dagster_postgres.PostgresScheduleStorage.migrate(self, print_fn: Optional[Callable[[Any], NoneType]] = None, force_rebuild_all: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `print_fn` | `Optional` | `None` | pos/kw |
| `force_rebuild_all` | `bool` | `False` | pos/kw |

### `optimize`

Call this method to run any optional data migrations for optimized reads.

```python
dagster_postgres.PostgresScheduleStorage.optimize(self, print_fn: Optional[Callable[[Any], NoneType]] = None, force_rebuild_all: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `print_fn` | `Optional` | `None` | pos/kw |
| `force_rebuild_all` | `bool` | `False` | pos/kw |

### `optimize_for_webserver`

Allows for optimizing database connection / use in the context of a long lived webserver process.

```python
dagster_postgres.PostgresScheduleStorage.optimize_for_webserver(self, statement_timeout: int, pool_recycle: int, max_overflow: int) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `statement_timeout` | `int` | `—` | pos/kw |
| `pool_recycle` | `int` | `—` | pos/kw |
| `max_overflow` | `int` | `—` | pos/kw |

### `purge_asset_evaluations`

Wipe evaluations before a certain timestamp.

Args:
    before (datetime): All evaluations before this datetime will get purged

```python
dagster_postgres.PostgresScheduleStorage.purge_asset_evaluations(self, before: float)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `before` | `float` | `—` | pos/kw |

### `purge_ticks`

Wipe ticks for an instigator for a certain status and timestamp.

Args:
    origin_id (str): The id of the instigator target to delete
    selector_id (str): The logical instigator identifier
    bef…

```python
dagster_postgres.PostgresScheduleStorage.purge_ticks(self, origin_id: str, selector_id: str, before: float, tick_statuses: collections.abc.Sequence[dagster._core.scheduler.instigation.TickStatus] | None = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_id` | `str` | `—` | pos/kw |
| `selector_id` | `str` | `—` | pos/kw |
| `before` | `float` | `—` | pos/kw |
| `tick_statuses` | `collections.abc.Sequence[dagster._core.scheduler.instigation.TickStatus] \| None` | `None` | pos/kw |

### `register_instance`

```python
dagster_postgres.PostgresScheduleStorage.register_instance(self, instance: ~T_DagsterInstance) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `instance` | `T_DagsterInstance` | `—` | pos/kw |

### `update_instigator_state`

Update an instigator state in storage.

Args:
    state (InstigatorState): The state to update

```python
dagster_postgres.PostgresScheduleStorage.update_instigator_state(self, state: dagster._core.scheduler.instigation.InstigatorState) -> dagster._core.scheduler.instigation.InstigatorState
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `state` | `InstigatorState` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.scheduler.instigation.InstigatorState'>`

### `update_tick`

Update a tick already in storage.

Args:
    tick (InstigatorTick): The tick to update

```python
dagster_postgres.PostgresScheduleStorage.update_tick(self, tick: dagster._core.scheduler.instigation.InstigatorTick) -> dagster._core.scheduler.instigation.InstigatorTick
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tick` | `InstigatorTick` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.scheduler.instigation.InstigatorTick'>`

### `dagster_postgres.auth.AwsWifTokenProvider` methods

### `get_token`

Return a valid token, refreshing if expired or about to expire.

```python
dagster_postgres.auth.AwsWifTokenProvider.get_token(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dagster_postgres.auth.AzureWifTokenProvider` methods

### `get_token`

Return a valid token, refreshing if expired or about to expire.

```python
dagster_postgres.auth.AzureWifTokenProvider.get_token(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dagster_postgres.auth.GcpWifTokenProvider` methods

### `get_token`

Return a valid token, refreshing if expired or about to expire.

```python
dagster_postgres.auth.GcpWifTokenProvider.get_token(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dagster_postgres.auth.PgTokenProvider` methods

### `get_token`

Return a valid token, refreshing if expired or about to expire.

```python
dagster_postgres.auth.PgTokenProvider.get_token(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dagster_postgres.event_log.PostgresEventLogStorage` methods

### `add_dynamic_partitions`

Add a partition for the specified dynamic partitions definition.

```python
dagster_postgres.event_log.PostgresEventLogStorage.add_dynamic_partitions(self, partitions_def_name: str, partition_keys: collections.abc.Sequence[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partitions_def_name` | `str` | `—` | pos/kw |
| `partition_keys` | `Sequence` | `—` | pos/kw |

### `add_pending_step`

```python
dagster_postgres.event_log.PostgresEventLogStorage.add_pending_step(self, concurrency_key: str, run_id: str, step_key: str, priority: int | None = None, should_assign: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |
| `priority` | `int \| None` | `None` | pos/kw |
| `should_assign` | `bool` | `False` | pos/kw |

### `alembic_version`

```python
dagster_postgres.event_log.PostgresEventLogStorage.alembic_version(self) -> tuple[str | None, str | tuple[str, ...] | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str | None, str | tuple[str, ...] | None]`

### `all_asset_keys`

```python
dagster_postgres.event_log.PostgresEventLogStorage.all_asset_keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `assign_pending_steps`

```python
dagster_postgres.event_log.PostgresEventLogStorage.assign_pending_steps(self, concurrency_keys: collections.abc.Sequence[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_keys` | `Sequence` | `—` | pos/kw |

### `can_claim_from_pending`

```python
dagster_postgres.event_log.PostgresEventLogStorage.can_claim_from_pending(self, concurrency_key: str, run_id: str, step_key: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

### `can_read_asset_status_cache`

Whether the storage can access cached status information for each asset.

```python
dagster_postgres.event_log.PostgresEventLogStorage.can_read_asset_status_cache(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `can_write_asset_status_cache`

Whether the storage is able to write to that cache.

```python
dagster_postgres.event_log.PostgresEventLogStorage.can_write_asset_status_cache(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_concurrency_claim`

Claim concurrency slots for step.

```python
dagster_postgres.event_log.PostgresEventLogStorage.check_concurrency_claim(self, concurrency_key: str, run_id: str, step_key: str) -> dagster._utils.concurrency.ConcurrencyClaimStatus
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

**Returns:** `<class 'dagster._utils.concurrency.ConcurrencyClaimStatus'>`

### `claim_concurrency_slot`

Claim concurrency slot for step.

Args:
    concurrency_keys (str): The concurrency key to claim.
    run_id (str): The run id to claim for.
    step_key (str): The step key to claim for.

```python
dagster_postgres.event_log.PostgresEventLogStorage.claim_concurrency_slot(self, concurrency_key: str, run_id: str, step_key: str, priority: int | None = None) -> dagster._utils.concurrency.ConcurrencyClaimStatus
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |
| `priority` | `int \| None` | `None` | pos/kw |

**Returns:** `<class 'dagster._utils.concurrency.ConcurrencyClaimStatus'>`

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.event_log.PostgresEventLogStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `create_clean_storage`

```python
dagster_postgres.event_log.PostgresEventLogStorage.create_clean_storage(conn_string: str, should_autocreate_tables: bool = True) -> 'PostgresEventLogStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_string` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |

**Returns:** `PostgresEventLogStorage`

### `default_run_scoped_event_tailer_offset`

```python
dagster_postgres.event_log.PostgresEventLogStorage.default_run_scoped_event_tailer_offset(self) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'int'>`

### `delete_concurrency_limit`

Delete a concurrency limit and its associated slots.

Args:
    concurrency_key (str): The key to delete.

```python
dagster_postgres.event_log.PostgresEventLogStorage.delete_concurrency_limit(self, concurrency_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |

### `delete_dynamic_partition`

Delete a partition for the specified dynamic partitions definition.

```python
dagster_postgres.event_log.PostgresEventLogStorage.delete_dynamic_partition(self, partitions_def_name: str, partition_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partitions_def_name` | `str` | `—` | pos/kw |
| `partition_key` | `str` | `—` | pos/kw |

### `delete_events`

Remove events for a given run id.

```python
dagster_postgres.event_log.PostgresEventLogStorage.delete_events(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `delete_events_for_run`

```python
dagster_postgres.event_log.PostgresEventLogStorage.delete_events_for_run(self, conn: sqlalchemy.engine.base.Connection, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `Connection` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `dispose`

Explicit lifecycle management.

```python
dagster_postgres.event_log.PostgresEventLogStorage.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `enable_secondary_index`

This method marks an event_log data migration as complete, to indicate that a summary
data migration is complete.

```python
dagster_postgres.event_log.PostgresEventLogStorage.enable_secondary_index(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `end_watch`

Call this method to stop watching.

```python
dagster_postgres.event_log.PostgresEventLogStorage.end_watch(self, run_id: str, handler: collections.abc.Callable[[dagster._core.events.log.EventLogEntry, str], None]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `handler` | `Callable` | `—` | pos/kw |

### `fetch_failed_materializations`

```python
dagster_postgres.event_log.PostgresEventLogStorage.fetch_failed_materializations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_materializations`

```python
dagster_postgres.event_log.PostgresEventLogStorage.fetch_materializations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_observations`

```python
dagster_postgres.event_log.PostgresEventLogStorage.fetch_observations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_run_status_changes`

```python
dagster_postgres.event_log.PostgresEventLogStorage.fetch_run_status_changes(self, records_filter: dagster._core.events.DagsterEventType | dagster._core.event_api.RunStatusChangeRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.events.DagsterEventType \| dagster._core.event_api.RunStatusChangeRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `free_concurrency_slot_for_step`

Frees concurrency slots for a given run/step.

```python
dagster_postgres.event_log.PostgresEventLogStorage.free_concurrency_slot_for_step(self, run_id: str, step_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

### `free_concurrency_slots_for_run`

Frees concurrency slots for a given run.

```python
dagster_postgres.event_log.PostgresEventLogStorage.free_concurrency_slots_for_run(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.event_log.PostgresEventLogStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: collections.abc.Mapping[str, typing.Any]) -> 'PostgresEventLogStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `Mapping` | `—` | pos/kw |

**Returns:** `PostgresEventLogStorage`

### `get_asset_check_execution_history`

Get executions for one asset check, sorted by recency.

```python
dagster_postgres.event_log.PostgresEventLogStorage.get_asset_check_execution_history(self, check_key: dagster._core.definitions.asset_key.AssetCheckKey, limit: int, cursor: int | None = None, status: Optional[AbstractSet[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecordStatus]] = None, partition_filter: dagster._core.event_api.PartitionKeyFilter | None = None) -> collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecord]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `check_key` | `AssetCheckKey` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `int \| None` | `None` | pos/kw |
| `status` | `Optional` | `None` | pos/kw |
| `partition_filter` | `dagster._core.event_api.PartitionKeyFilter \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecord]`

### `get_asset_check_partition_info`

Get asset check partition records with execution status and planned run info.

```python
dagster_postgres.event_log.PostgresEventLogStorage.get_asset_check_partition_info(self, keys: collections.abc.Sequence[dagster._core.definitions.asset_key.AssetCheckKey], after_storage_id: int | None = None, partition_keys: collections.abc.Sequence[str] | None = None) -> collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckPartitionInfo]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `Sequence` | `—` | pos/kw |
| `after_storage_id` | `int \| None` | `None` | pos/kw |
| `partition_keys` | `collections.abc.Sequence[str] \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckPartitionInfo]`

### `get_asset_check_state`

```python
dagster_postgres.event_log.PostgresEventLogStorage.get_asset_check_state(self, keys: collections.abc.Sequence[tuple[dagster._core.definitions.asset_key.AssetCheckKey, dagster._core.definitions.partitions.definition.partitions_definition.PartitionsDefinition | None]]) -> collections.abc.Mapping[dagster._core.definitions.asset_key.AssetCheckKey, 'AssetCheckState']
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `Sequence` | `—` | pos/kw |

**Returns:** `collections.abc.Mapping[dagster._core.definitions.asset_key.AssetCheckKey, 'AssetCheckState']`

### `dagster_postgres.event_log.event_log.PostgresEventLogStorage` methods

### `add_dynamic_partitions`

Add a partition for the specified dynamic partitions definition.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.add_dynamic_partitions(self, partitions_def_name: str, partition_keys: collections.abc.Sequence[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partitions_def_name` | `str` | `—` | pos/kw |
| `partition_keys` | `Sequence` | `—` | pos/kw |

### `add_pending_step`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.add_pending_step(self, concurrency_key: str, run_id: str, step_key: str, priority: int | None = None, should_assign: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |
| `priority` | `int \| None` | `None` | pos/kw |
| `should_assign` | `bool` | `False` | pos/kw |

### `alembic_version`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.alembic_version(self) -> tuple[str | None, str | tuple[str, ...] | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str | None, str | tuple[str, ...] | None]`

### `all_asset_keys`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.all_asset_keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `assign_pending_steps`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.assign_pending_steps(self, concurrency_keys: collections.abc.Sequence[str])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_keys` | `Sequence` | `—` | pos/kw |

### `can_claim_from_pending`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.can_claim_from_pending(self, concurrency_key: str, run_id: str, step_key: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

### `can_read_asset_status_cache`

Whether the storage can access cached status information for each asset.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.can_read_asset_status_cache(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `can_write_asset_status_cache`

Whether the storage is able to write to that cache.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.can_write_asset_status_cache(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_concurrency_claim`

Claim concurrency slots for step.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.check_concurrency_claim(self, concurrency_key: str, run_id: str, step_key: str) -> dagster._utils.concurrency.ConcurrencyClaimStatus
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

**Returns:** `<class 'dagster._utils.concurrency.ConcurrencyClaimStatus'>`

### `claim_concurrency_slot`

Claim concurrency slot for step.

Args:
    concurrency_keys (str): The concurrency key to claim.
    run_id (str): The run id to claim for.
    step_key (str): The step key to claim for.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.claim_concurrency_slot(self, concurrency_key: str, run_id: str, step_key: str, priority: int | None = None) -> dagster._utils.concurrency.ConcurrencyClaimStatus
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |
| `priority` | `int \| None` | `None` | pos/kw |

**Returns:** `<class 'dagster._utils.concurrency.ConcurrencyClaimStatus'>`

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `create_clean_storage`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.create_clean_storage(conn_string: str, should_autocreate_tables: bool = True) -> 'PostgresEventLogStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conn_string` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |

**Returns:** `PostgresEventLogStorage`

### `default_run_scoped_event_tailer_offset`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.default_run_scoped_event_tailer_offset(self) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'int'>`

### `delete_concurrency_limit`

Delete a concurrency limit and its associated slots.

Args:
    concurrency_key (str): The key to delete.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.delete_concurrency_limit(self, concurrency_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `concurrency_key` | `str` | `—` | pos/kw |

### `delete_dynamic_partition`

Delete a partition for the specified dynamic partitions definition.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.delete_dynamic_partition(self, partitions_def_name: str, partition_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partitions_def_name` | `str` | `—` | pos/kw |
| `partition_key` | `str` | `—` | pos/kw |

### `delete_events`

Remove events for a given run id.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.delete_events(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `delete_events_for_run`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.delete_events_for_run(self, conn: sqlalchemy.engine.base.Connection, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `Connection` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `dispose`

Explicit lifecycle management.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `enable_secondary_index`

This method marks an event_log data migration as complete, to indicate that a summary
data migration is complete.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.enable_secondary_index(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `end_watch`

Call this method to stop watching.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.end_watch(self, run_id: str, handler: collections.abc.Callable[[dagster._core.events.log.EventLogEntry, str], None]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `handler` | `Callable` | `—` | pos/kw |

### `fetch_failed_materializations`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.fetch_failed_materializations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_materializations`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.fetch_materializations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_observations`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.fetch_observations(self, records_filter: dagster._core.definitions.asset_key.AssetKey | dagster._core.event_api.AssetRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.definitions.asset_key.AssetKey \| dagster._core.event_api.AssetRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `fetch_run_status_changes`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.fetch_run_status_changes(self, records_filter: dagster._core.events.DagsterEventType | dagster._core.event_api.RunStatusChangeRecordsFilter, limit: int, cursor: str | None = None, ascending: bool = False) -> dagster._core.event_api.EventRecordsResult
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `records_filter` | `dagster._core.events.DagsterEventType \| dagster._core.event_api.RunStatusChangeRecordsFilter` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `ascending` | `bool` | `False` | pos/kw |

**Returns:** `<class 'dagster._core.event_api.EventRecordsResult'>`

### `free_concurrency_slot_for_step`

Frees concurrency slots for a given run/step.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.free_concurrency_slot_for_step(self, run_id: str, step_key: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `step_key` | `str` | `—` | pos/kw |

### `free_concurrency_slots_for_run`

Frees concurrency slots for a given run.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.free_concurrency_slots_for_run(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: collections.abc.Mapping[str, typing.Any]) -> 'PostgresEventLogStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `Mapping` | `—` | pos/kw |

**Returns:** `PostgresEventLogStorage`

### `get_asset_check_execution_history`

Get executions for one asset check, sorted by recency.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.get_asset_check_execution_history(self, check_key: dagster._core.definitions.asset_key.AssetCheckKey, limit: int, cursor: int | None = None, status: Optional[AbstractSet[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecordStatus]] = None, partition_filter: dagster._core.event_api.PartitionKeyFilter | None = None) -> collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecord]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `check_key` | `AssetCheckKey` | `—` | pos/kw |
| `limit` | `int` | `—` | pos/kw |
| `cursor` | `int \| None` | `None` | pos/kw |
| `status` | `Optional` | `None` | pos/kw |
| `partition_filter` | `dagster._core.event_api.PartitionKeyFilter \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckExecutionRecord]`

### `get_asset_check_partition_info`

Get asset check partition records with execution status and planned run info.

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.get_asset_check_partition_info(self, keys: collections.abc.Sequence[dagster._core.definitions.asset_key.AssetCheckKey], after_storage_id: int | None = None, partition_keys: collections.abc.Sequence[str] | None = None) -> collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckPartitionInfo]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `Sequence` | `—` | pos/kw |
| `after_storage_id` | `int \| None` | `None` | pos/kw |
| `partition_keys` | `collections.abc.Sequence[str] \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.storage.asset_check_execution_record.AssetCheckPartitionInfo]`

### `get_asset_check_state`

```python
dagster_postgres.event_log.event_log.PostgresEventLogStorage.get_asset_check_state(self, keys: collections.abc.Sequence[tuple[dagster._core.definitions.asset_key.AssetCheckKey, dagster._core.definitions.partitions.definition.partitions_definition.PartitionsDefinition | None]]) -> collections.abc.Mapping[dagster._core.definitions.asset_key.AssetCheckKey, 'AssetCheckState']
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `Sequence` | `—` | pos/kw |

**Returns:** `collections.abc.Mapping[dagster._core.definitions.asset_key.AssetCheckKey, 'AssetCheckState']`

### `dagster_postgres.run_storage.PostgresRunStorage` methods

### `add_backfill`

Add partition backfill to run storage.

```python
dagster_postgres.run_storage.PostgresRunStorage.add_backfill(self, partition_backfill: dagster._core.execution.backfill.PartitionBackfill) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `partition_backfill` | `PartitionBackfill` | `—` | pos/kw |

### `add_daemon_heartbeat`

Called on a regular interval by the daemon.

```python
dagster_postgres.run_storage.PostgresRunStorage.add_daemon_heartbeat(self, daemon_heartbeat: dagster._daemon.types.DaemonHeartbeat) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `daemon_heartbeat` | `DaemonHeartbeat` | `—` | pos/kw |

### `add_execution_plan_snapshot`

Add an execution plan snapshot to the run store.

Execution plan snapshots are content-addressable, meaning
that the ID for a snapshot is a hash based on the
body of the snapshot. This function retur…

```python
dagster_postgres.run_storage.PostgresRunStorage.add_execution_plan_snapshot(self, execution_plan_snapshot: dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `execution_plan_snapshot` | `ExecutionPlanSnapshot` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `add_historical_run`

Add a historical run to storage.

```python
dagster_postgres.run_storage.PostgresRunStorage.add_historical_run(self, dagster_run: dagster._core.storage.dagster_run.DagsterRun, run_creation_time: datetime.datetime) -> dagster._core.storage.dagster_run.DagsterRun
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dagster_run` | `DagsterRun` | `—` | pos/kw |
| `run_creation_time` | `datetime` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.storage.dagster_run.DagsterRun'>`

### `add_job_snapshot`

Add a pipeline snapshot to the run store.

Pipeline snapshots are content-addressable, meaning
that the ID for a snapshot is a hash based on the
body of the snapshot. This function returns
that snaps…

```python
dagster_postgres.run_storage.PostgresRunStorage.add_job_snapshot(self, job_snapshot: dagster._core.snap.job_snapshot.JobSnap) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `job_snapshot` | `JobSnap` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `add_run`

Add a run to storage.

If a run already exists with the same ID, raise DagsterRunAlreadyExists
If the run's snapshot ID does not exist raise DagsterSnapshotDoesNotExist

Args:
    dagster_run (Dagste…

```python
dagster_postgres.run_storage.PostgresRunStorage.add_run(self, dagster_run: dagster._core.storage.dagster_run.DagsterRun) -> dagster._core.storage.dagster_run.DagsterRun
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dagster_run` | `DagsterRun` | `—` | pos/kw |

**Returns:** `<class 'dagster._core.storage.dagster_run.DagsterRun'>`

### `add_run_tags`

Add additional tags for a pipeline run.

Args:
    run_id (str)
    new_tags (Dict[string, string])

```python
dagster_postgres.run_storage.PostgresRunStorage.add_run_tags(self, run_id: str, new_tags: collections.abc.Mapping[str, str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |
| `new_tags` | `Mapping` | `—` | pos/kw |

### `add_run_telemetry`

Not implemented in base class. Should be implemented in subclasses that support telemetry.

```python
dagster_postgres.run_storage.PostgresRunStorage.add_run_telemetry(self, run_telemetry: dagster._core.execution.telemetry.RunTelemetryData, tags: dict[str, str] | None = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_telemetry` | `RunTelemetryData` | `—` | pos/kw |
| `tags` | `dict[str, str] \| None` | `None` | pos/kw |

### `add_snapshot`

Add a snapshot to the storage.

Args:
    snapshot (Union[PipelineSnapshot, ExecutionPlanSnapshot])

```python
dagster_postgres.run_storage.PostgresRunStorage.add_snapshot(self, snapshot: dagster._core.snap.job_snapshot.JobSnap | dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `snapshot` | `dagster._core.snap.job_snapshot.JobSnap \| dagster._core.snap.execution_plan_snapshot.ExecutionPlanSnapshot` | `—` | pos/kw |

### `alembic_version`

```python
dagster_postgres.run_storage.PostgresRunStorage.alembic_version(self) -> tuple[str | None, str | tuple[str, ...] | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[str | None, str | tuple[str, ...] | None]`

### `config_type`

Get the config type against which to validate a config yaml fragment.

The only place config values matching this type are used is inside `from_config_value`. This
is an alternative constructor for a…

```python
dagster_postgres.run_storage.PostgresRunStorage.config_type() -> Union[type[bool | float | int | str], type[dict[Any, Any] | list[Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, Any], collections.abc.Sequence[Any]]
```

**Returns:** `typing.Union[type[bool | float | int | str], type[dict[typing.Any, typing.Any] | list[typing.Any]], ForwardRef('ConfigType'), ForwardRef('Field'), collections.abc.Mapping[str, typing.Any], collections.abc.Sequence[typing.Any]]`

### `connect`

Context manager yielding a sqlalchemy.engine.Connection.

```python
dagster_postgres.run_storage.PostgresRunStorage.connect(self) -> ContextManager[sqlalchemy.engine.base.Connection, bool | None]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.ContextManager[sqlalchemy.engine.base.Connection, bool | None]`

### `create_clean_storage`

```python
dagster_postgres.run_storage.PostgresRunStorage.create_clean_storage(postgres_url: str, should_autocreate_tables: bool = True) -> 'PostgresRunStorage'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `postgres_url` | `str` | `—` | pos/kw |
| `should_autocreate_tables` | `bool` | `True` | pos/kw |

**Returns:** `PostgresRunStorage`

### `delete_run`

Remove a run from storage.

```python
dagster_postgres.run_storage.PostgresRunStorage.delete_run(self, run_id: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_id` | `str` | `—` | pos/kw |

### `dispose`

Explicit lifecycle management.

```python
dagster_postgres.run_storage.PostgresRunStorage.dispose(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `fetchall`

```python
dagster_postgres.run_storage.PostgresRunStorage.fetchall(self, query: Any) -> collections.abc.Sequence[typing.Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Any` | `—` | pos/kw |

**Returns:** `collections.abc.Sequence[typing.Any]`

### `fetchone`

```python
dagster_postgres.run_storage.PostgresRunStorage.fetchone(self, query: Any) -> typing.Any | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query` | `Any` | `—` | pos/kw |

**Returns:** `typing.Any | None`

### `from_config_value`

Create an instance of the ConfigurableClass from a validated config value.

The config value used here should be derived from the accompanying `inst_data` argument.
`inst_data` contains the yaml-seri…

```python
dagster_postgres.run_storage.PostgresRunStorage.from_config_value(inst_data: dagster._serdes.config_class.ConfigurableClassData | None, config_value: dagster._core.storage.config.PostgresStorageConfig)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst_data` | `dagster._serdes.config_class.ConfigurableClassData \| None` | `—` | pos/kw |
| `config_value` | `PostgresStorageConfig` | `—` | pos/kw |

### `get_backfill`

Get the partition backfill of the given backfill id.

```python
dagster_postgres.run_storage.PostgresRunStorage.get_backfill(self, backfill_id: str) -> dagster._core.execution.backfill.PartitionBackfill | None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `backfill_id` | `str` | `—` | pos/kw |

**Returns:** `dagster._core.execution.backfill.PartitionBackfill | None`

### `get_backfills`

Get a list of partition backfills.

```python
dagster_postgres.run_storage.PostgresRunStorage.get_backfills(self, filters: dagster._core.execution.backfill.BulkActionsFilter | None = None, cursor: str | None = None, limit: int | None = None, status: dagster._core.execution.backfill.BulkActionStatus | None = None) -> collections.abc.Sequence[dagster._core.execution.backfill.PartitionBackfill]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filters` | `dagster._core.execution.backfill.BulkActionsFilter \| None` | `None` | pos/kw |
| `cursor` | `str \| None` | `None` | pos/kw |
| `limit` | `int \| None` | `None` | pos/kw |
| `status` | `dagster._core.execution.backfill.BulkActionStatus \| None` | `None` | pos/kw |

**Returns:** `collections.abc.Sequence[dagster._core.execution.backfill.PartitionBackfill]`

### `get_backfills_count`

Return the number of backfills present in the storage that match the given filters.

Args:
    filters (Optional[BulkActionsFilter]) -- The filter by which to filter backfills

Returns:
    int: The…

```python
dagster_postgres.run_storage.PostgresRunStorage.get_backfills_count(self, filters: dagster._core.execution.backfill.BulkActionsFilter | None = None) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filters` | `dagster._core.execution.backfill.BulkActionsFilter \| None` | `None` | pos/kw |

**Returns:** `<class 'int'>`

### `get_cursor_values`

Retrieve the value for a given key in the current deployment.

```python
dagster_postgres.run_storage.PostgresRunStorage.get_cursor_values(self, keys: set[str]) -> collections.abc.Mapping[str, str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keys` | `set` | `—` | pos/kw |

**Returns:** `collections.abc.Mapping[str, str]`


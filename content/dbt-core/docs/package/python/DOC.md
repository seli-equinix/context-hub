---
name: package
description: "dbt Core package guide for Python projects using the dbt CLI, project config, profiles, and adapters"
metadata:
  languages: "python"
  versions: "1.11.7"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "dbt-core,python,dbt,analytics-engineering,sql,etl,cli,warehouse,Version-Sensitive,AdapterConfig,compare_key,finalize_and_validate,from_dict,from_msgpack,get,json_schema,meta_get,replace,same_contents,to_dict,to_msgpack,update_from,validate,AdapterPlugin,AdapterTrackingRelationInfo,incorporate,items,keys,values,BaseAdapter,acquire_connection,add_catalog_integration,already_exists,assert_valid_snapshot_target_given_strategy,build_catalog_relation,builtin_incremental_strategies,cache_added,cache_dropped,cache_renamed,calculate_freshness,calculate_freshness_from_custom_sql,calculate_freshness_from_metadata,calculate_freshness_from_metadata_batch,cancel_open_connections,capabilities,check_schema_exists,cleanup_connections,clear_macro_resolver,clear_transaction,commit_if_has_connection,connection_named,convert_agate_type,convert_boolean_type,convert_date_type,convert_datetime_type,convert_integer_type,convert_number_type,convert_text_type,convert_time_type,convert_type,BaseConnectionManager,add_select_query,begin,cancel_open,cleanup_all,clear_thread_connection,close,commit,data_type_code_to_name,exception_handler,execute,get_if_exists,get_thread_connection,get_thread_identifier,open,release,retry_connection,rollback_if_open,set_connection_name,set_query_header,set_thread_connection,BaseRelation,add_ephemeral_prefix,create,create_ephemeral_from,create_from,get_default_include_policy,get_default_quote_policy,get_function_config,get_function_macro_name,include,information_schema,information_schema_only,matches,quote,quoted,render,render_event_time_filtered,render_limited,replace_path,scd_args,Column,can_expand_to,from_description,is_float,is_integer,is_number,is_numeric,is_string,literal,numeric_type,string_size,string_type,translate_type,ConstraintSupport,PythonJobHelper,submit,PythonSubmissionResult,RelationType,SchemaSearchMap,add,flatten,search,CacheAction,code,format_ref_key,level_tag,message,to_json,CacheDumpGraph,DependentLinkNotCachedError,data,process_stack,NewNameAlreadyInCacheError,NoneRelationFoundError,ReferencedLinkNotCachedError,RelationsCache,add_link,add_schema,clear,drop,drop_schema,dump_graph,get_relations,rename,update_schemas,TruncatedModelNameCausedCollisionError,get_message,dot_separated,fire_event,fire_event_if,lowercase,Capability,CapabilityDict,CapabilitySupport,Support,CatalogIntegration,build_relation,CatalogIntegrationClient,CatalogIntegrationConfig,CatalogRelation,DbtCatalogIntegrationAlreadyExistsError,add_node,node_to_string,validator_error_message,DbtCatalogIntegrationNotFoundError"
---

# dbt-core — package

## Install

```bash
pip install dbt-core
```

## Imports

```python
import dbt_core
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `AdapterConfig` | Class | AdapterConfig(_extra: Dict[str, Any] = <factory>) |
| `compare_key` | Method |  |
| `finalize_and_validate` | Method |  |
| `from_dict` | Method |  |
| `from_msgpack` | Method |  |
| `get` | Method |  |
| `json_schema` | Method |  |
| `meta_get` | Method |  |
| `replace` | Method |  |
| `same_contents` | Method | This is like __eq__, except it ignores some fields. |
| `to_dict` | Method |  |
| `to_msgpack` | Method |  |
| `update_from` | Method | Update and validate config given a dict.  Given a dict of keys, update the curr… |
| `validate` | Method |  |
| `AdapterPlugin` | Class | Defines the basic requirements for a dbt adapter plugin.  :param include_path:… |
| `AdapterTrackingRelationInfo` | Class | AdapterTrackingRelationInfo(adapter_name: str, base_adapter_version: str, adapt… |
| `from_dict` | Method |  |
| `from_msgpack` | Method |  |
| `get` | Method | D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None. |
| `incorporate` | Method |  |
| `items` | Method | D.items() -> a set-like object providing a view on D's items |
| `json_schema` | Method |  |
| `keys` | Method | D.keys() -> a set-like object providing a view on D's keys |
| `replace` | Method |  |
| `to_dict` | Method |  |
| `to_msgpack` | Method |  |
| `validate` | Method |  |
| `values` | Method | D.values() -> an object providing a view on D's values |
| `BaseAdapter` | Class | The BaseAdapter provides an abstract base class for adapters.  Adapters must im… |
| `acquire_connection` | Method |  |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `AdapterConfig`

AdapterConfig(_extra: Dict[str, Any] = <factory>)

```python
dbt.adapters.base.AdapterConfig(self, _extra: Dict[str, Any] = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_extra` | `Dict` | `<factory>` | pos/kw |

### `AdapterPlugin`

Defines the basic requirements for a dbt adapter plugin.

:param include_path: The path to this adapter plugin's root
:param dependencies: A list of adapter names that this adapter depends
    upon.

```python
dbt.adapters.base.AdapterPlugin(self, adapter: Type[dbt.adapters.protocol.AdapterProtocol], credentials: Type[dbt.adapters.contracts.connection.Credentials], include_path: str, dependencies: Optional[List[str]] = None, project_name: Optional[str] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `adapter` | `Type` | `—` | pos/kw |
| `credentials` | `Type` | `—` | pos/kw |
| `include_path` | `str` | `—` | pos/kw |
| `dependencies` | `Optional` | `None` | pos/kw |
| `project_name` | `Optional` | `None` | pos/kw |

### `AdapterTrackingRelationInfo`

AdapterTrackingRelationInfo(adapter_name: str, base_adapter_version: str, adapter_version: str, model_adapter_details: Any)

```python
dbt.adapters.base.AdapterTrackingRelationInfo(self, adapter_name: str, base_adapter_version: str, adapter_version: str, model_adapter_details: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `adapter_name` | `str` | `—` | pos/kw |
| `base_adapter_version` | `str` | `—` | pos/kw |
| `adapter_version` | `str` | `—` | pos/kw |
| `model_adapter_details` | `Any` | `—` | pos/kw |

### `BaseAdapter`

The BaseAdapter provides an abstract base class for adapters.

Adapters must implement the following methods and macros. Some of the
methods can be safely overridden as a noop, where it makes sense
(…

```python
dbt.adapters.base.BaseAdapter(self, config, mp_context: multiprocessing.context.SpawnContext) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `—` | `—` | pos/kw |
| `mp_context` | `SpawnContext` | `—` | pos/kw |

### `BaseConnectionManager`

Methods to implement:
    - exception_handler
    - cancel_open
    - open
    - begin
    - commit
    - clear_transaction
    - execute

You must also set the 'TYPE' class attribute with a class-un…

```python
dbt.adapters.base.BaseConnectionManager(self, profile: dbt.adapters.contracts.connection.AdapterRequiredConfig, mp_context: multiprocessing.context.SpawnContext) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `profile` | `AdapterRequiredConfig` | `—` | pos/kw |
| `mp_context` | `SpawnContext` | `—` | pos/kw |

### `BaseRelation`

BaseRelation(path: dbt.adapters.contracts.relation.Path, type: Optional[dbt.adapters.contracts.relation.RelationType] = None, quote_character: str = '"', include_policy: dbt.adapters.contracts.relati…

```python
dbt.adapters.base.BaseRelation(self, path: dbt.adapters.contracts.relation.Path, type: Optional[dbt.adapters.contracts.relation.RelationType] = None, quote_character: str = '"', include_policy: dbt.adapters.contracts.relation.Policy = <factory>, quote_policy: dbt.adapters.contracts.relation.Policy = <factory>, dbt_created: bool = False, limit: Optional[int] = None, event_time_filter: Optional[dbt.adapters.base.relation.EventTimeFilter] = None, require_alias: bool = True, catalog: Optional[str] = None, renameable_relations: Union[Tuple, FrozenSet] = <factory>, replaceable_relations: Union[Tuple, FrozenSet] = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path` | `—` | pos/kw |
| `type` | `Optional` | `None` | pos/kw |
| `quote_character` | `str` | `'"'` | pos/kw |
| `include_policy` | `Policy` | `<factory>` | pos/kw |
| `quote_policy` | `Policy` | `<factory>` | pos/kw |
| `dbt_created` | `bool` | `False` | pos/kw |
| `limit` | `Optional` | `None` | pos/kw |
| `event_time_filter` | `Optional` | `None` | pos/kw |
| `require_alias` | `bool` | `True` | pos/kw |
| `catalog` | `Optional` | `None` | pos/kw |
| `renameable_relations` | `Union` | `<factory>` | pos/kw |
| `replaceable_relations` | `Union` | `<factory>` | pos/kw |

### `Column`

Column(column: str, dtype: str, char_size: Optional[int] = None, numeric_precision: Optional[Any] = None, numeric_scale: Optional[Any] = None)

```python
dbt.adapters.base.Column(self, column: str, dtype: str, char_size: Optional[int] = None, numeric_precision: Optional[Any] = None, numeric_scale: Optional[Any] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `column` | `str` | `—` | pos/kw |
| `dtype` | `str` | `—` | pos/kw |
| `char_size` | `Optional` | `None` | pos/kw |
| `numeric_precision` | `Optional` | `None` | pos/kw |
| `numeric_scale` | `Optional` | `None` | pos/kw |

### `ConstraintSupport`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
dbt.adapters.base.ConstraintSupport(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `PythonJobHelper`

```python
dbt.adapters.base.PythonJobHelper(self, parsed_model: Dict, credential: dbt.adapters.contracts.connection.Credentials) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parsed_model` | `Dict` | `—` | pos/kw |
| `credential` | `Credentials` | `—` | pos/kw |

### `PythonSubmissionResult`

Result from submitting a Python job.

```python
dbt.adapters.base.PythonSubmissionResult(self, run_id: str, compiled_code: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `run_id` | `str` | `—` | pos/kw |
| `compiled_code` | `str` | `—` | pos/kw |

### `RelationType`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
dbt.adapters.base.RelationType(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `SchemaSearchMap`

A utility class to keep track of what information_schema tables to
search for what schemas. The schema values are all lowercased to avoid
duplication.

```python
dbt.adapters.base.SchemaSearchMap(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CacheAction`

BaseEvent for proto message generated python events.

```python
dbt.adapters.cache.CacheAction(self, *args, **kwargs) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CacheDumpGraph`

BaseEvent for proto message generated python events.

```python
dbt.adapters.cache.CacheDumpGraph(self, *args, **kwargs) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DependentLinkNotCachedError`

Common base class for all non-exit exceptions.

```python
dbt.adapters.cache.DependentLinkNotCachedError(self, dependent_key: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dependent_key` | `str` | `—` | pos/kw |

### `NewNameAlreadyInCacheError`

Common base class for all non-exit exceptions.

```python
dbt.adapters.cache.NewNameAlreadyInCacheError(self, old_key: str, new_key: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `old_key` | `str` | `—` | pos/kw |
| `new_key` | `str` | `—` | pos/kw |

### `NoneRelationFoundError`

Common base class for all non-exit exceptions.

```python
dbt.adapters.cache.NoneRelationFoundError(self)
```

### `ReferencedLinkNotCachedError`

Common base class for all non-exit exceptions.

```python
dbt.adapters.cache.ReferencedLinkNotCachedError(self, referenced_key: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `referenced_key` | `str` | `—` | pos/kw |

### `RelationsCache`

A cache of the relations known to dbt. Keeps track of relationships
declared between tables and handles renames/drops as a real database would.

:attr Dict[_ReferenceKey, _CachedRelation] relations:…

```python
dbt.adapters.cache.RelationsCache(self, log_cache_events: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `log_cache_events` | `bool` | `False` | pos/kw |

### `TruncatedModelNameCausedCollisionError`

Common base class for all non-exit exceptions.

```python
dbt.adapters.cache.TruncatedModelNameCausedCollisionError(self, new_key, relations: Dict)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `new_key` | `—` | `—` | pos/kw |
| `relations` | `Dict` | `—` | pos/kw |

### `Capability`

Enumeration of optional adapter features which can be probed using BaseAdapter.capabilities()

```python
dbt.adapters.capability.Capability(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `CapabilityDict`

defaultdict(default_factory=None, /, [...]) --> dict with default factory

The default factory is called without arguments to produce
a new value when a key is not present, in __getitem__ only.
A def…

```python
dbt.adapters.capability.CapabilityDict(self, vals: Mapping[dbt.adapters.capability.Capability, dbt.adapters.capability.CapabilitySupport])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vals` | `Mapping` | `—` | pos/kw |

### `CapabilitySupport`

CapabilitySupport(support: dbt.adapters.capability.Support, first_version: Optional[str] = None)

```python
dbt.adapters.capability.CapabilitySupport(self, support: dbt.adapters.capability.Support, first_version: Optional[str] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `support` | `Support` | `—` | pos/kw |
| `first_version` | `Optional` | `None` | pos/kw |

### `Support`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
dbt.adapters.capability.Support(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `CatalogIntegration`

Represent a catalog integration for a given user config

This class should be implemented by specific catalog integration types in an adapter.
A catalog integration is a specific platform's way of in…

```python
dbt.adapters.catalogs.CatalogIntegration(self, config: dbt.adapters.catalogs._integration.CatalogIntegrationConfig) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `CatalogIntegrationConfig` | `—` | pos/kw |

### `CatalogIntegrationClient`

A repository class that manages catalog integrations

This class manages all types of catalog integrations,
supporting operations like registering new integrations and retrieving existing ones.
There…

```python
dbt.adapters.catalogs.CatalogIntegrationClient(self, supported_catalogs: Iterable[Type[dbt.adapters.catalogs._integration.CatalogIntegration]])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `supported_catalogs` | `Iterable` | `—` | pos/kw |

### `CatalogIntegrationConfig`

Represents the user configuration required to describe a catalog integration

This class serves as a blueprint for catalog integration configurations,
providing details about the catalog type, name,…

```python
dbt.adapters.catalogs.CatalogIntegrationConfig(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CatalogRelation`

Base class for protocol classes.

Protocol classes are defined as::

    class Proto(Protocol):
        def meth(self) -> int:
            ...

Such classes are primarily used with static type checke…

```python
dbt.adapters.catalogs.CatalogRelation(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DbtCatalogIntegrationAlreadyExistsError`

Unspecified run-time error.

```python
dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError(self, catalog_name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `catalog_name` | `str` | `—` | pos/kw |

### `DbtCatalogIntegrationNotFoundError`

Unspecified run-time error.

```python
dbt.adapters.catalogs.DbtCatalogIntegrationNotFoundError(self, catalog_name: str, existing_catalog_names: Iterable[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `catalog_name` | `str` | `—` | pos/kw |
| `existing_catalog_names` | `Iterable` | `—` | pos/kw |

## Functions

### `dot_separated`

Return the key in dot-separated string form.

:param _ReferenceKey key: The key to stringify.

```python
dbt.adapters.cache.dot_separated(key: dbt.adapters.reference_keys._ReferenceKey) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `_ReferenceKey` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `fire_event`

```python
dbt.adapters.cache.fire_event(e: dbt_common.events.base_types.BaseEvent, level: Optional[dbt_common.events.base_types.EventLevel] = None, node: Any = None, force_warn_or_error_handling: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `e` | `BaseEvent` | `—` | pos/kw |
| `level` | `Optional` | `None` | pos/kw |
| `node` | `Any` | `None` | pos/kw |
| `force_warn_or_error_handling` | `bool` | `False` | pos/kw |

### `fire_event_if`

```python
dbt.adapters.cache.fire_event_if(conditional: bool, lazy_e: Callable[[], dbt_common.events.base_types.BaseEvent], level: Optional[dbt_common.events.base_types.EventLevel] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `conditional` | `bool` | `—` | pos/kw |
| `lazy_e` | `Callable` | `—` | pos/kw |
| `level` | `Optional` | `None` | pos/kw |

### `lowercase`

```python
dbt.adapters.cache.lowercase(value: Optional[str]) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `Optional` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

## Methods

### `dbt.adapters.base.AdapterConfig` methods

### `compare_key`

```python
dbt.adapters.base.AdapterConfig.compare_key(unrendered: 'Dict[str, Any]', other: 'Dict[str, Any]', key: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `unrendered` | `Dict[str, Any]` | `—` | pos/kw |
| `other` | `Dict[str, Any]` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `finalize_and_validate`

```python
dbt.adapters.base.AdapterConfig.finalize_and_validate(self: 'T') -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |

**Returns:** `T`

### `from_dict`

```python
dbt.adapters.base.AdapterConfig.from_dict(d, *, dialect=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `dialect` | `—` | `None` | kw |

### `from_msgpack`

```python
dbt.adapters.base.AdapterConfig.from_msgpack(d, decoder=<function default_decoder at 0x7cbc2732c900>, *, dialect=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `decoder` | `—` | `<function default_decoder at 0x7cbc2732c900>` | pos/kw |
| `dialect` | `—` | `None` | kw |

### `get`

```python
dbt.adapters.base.AdapterConfig.get(self, key: 'str', default: 'Any' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `default` | `Any` | `None` | pos/kw |

**Returns:** `Any`

### `json_schema`

```python
dbt.adapters.base.AdapterConfig.json_schema()
```

### `meta_get`

```python
dbt.adapters.base.AdapterConfig.meta_get(self, key: 'str', default: 'Any' = None) -> 'Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `default` | `Any` | `None` | pos/kw |

**Returns:** `Any`

### `replace`

```python
dbt.adapters.base.AdapterConfig.replace(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `same_contents`

This is like __eq__, except it ignores some fields.

```python
dbt.adapters.base.AdapterConfig.same_contents(unrendered: 'Dict[str, Any]', other: 'Dict[str, Any]') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `unrendered` | `Dict[str, Any]` | `—` | pos/kw |
| `other` | `Dict[str, Any]` | `—` | pos/kw |

**Returns:** `bool`

### `to_dict`

```python
dbt.adapters.base.AdapterConfig.to_dict(self, *, omit_none=False, context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `omit_none` | `—` | `False` | kw |
| `context` | `—` | `None` | kw |

### `to_msgpack`

```python
dbt.adapters.base.AdapterConfig.to_msgpack(self, encoder=<function default_encoder at 0x7cbc272c3240>, *, omit_none=False, context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `encoder` | `—` | `<function default_encoder at 0x7cbc272c3240>` | pos/kw |
| `omit_none` | `—` | `False` | kw |
| `context` | `—` | `None` | kw |

### `update_from`

Update and validate config given a dict.

Given a dict of keys, update the current config from them, validate
it, and return a new config with the updated values

```python
dbt.adapters.base.AdapterConfig.update_from(self: 'T', data: 'Dict[str, Any]', config_cls: 'Type[BaseConfig]', validate: 'bool' = True) -> 'T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `T` | `—` | pos/kw |
| `data` | `Dict[str, Any]` | `—` | pos/kw |
| `config_cls` | `Type[BaseConfig]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |

**Returns:** `T`

### `validate`

```python
dbt.adapters.base.AdapterConfig.validate(data: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Any` | `—` | pos/kw |

### `dbt.adapters.base.AdapterTrackingRelationInfo` methods

### `from_dict`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.from_dict(d, *, dialect=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `dialect` | `—` | `None` | kw |

### `from_msgpack`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.from_msgpack(d, decoder=<function default_decoder at 0x7cbc2732c900>, *, dialect=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `decoder` | `—` | `<function default_decoder at 0x7cbc2732c900>` | pos/kw |
| `dialect` | `—` | `None` | kw |

### `get`

D.get(k[,d]) -> D[k] if k in D, else d.  d defaults to None.

```python
dbt.adapters.base.AdapterTrackingRelationInfo.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `incorporate`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.incorporate(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `items`

D.items() -> a set-like object providing a view on D's items

```python
dbt.adapters.base.AdapterTrackingRelationInfo.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `json_schema`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.json_schema()
```

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
dbt.adapters.base.AdapterTrackingRelationInfo.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `replace`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.replace(self: ~_R, **kwargs: Any) -> ~_R
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `_R` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `~_R`

### `to_dict`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.to_dict(self, *, omit_none=False, context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `omit_none` | `—` | `False` | kw |
| `context` | `—` | `None` | kw |

### `to_msgpack`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.to_msgpack(self, encoder=<function default_encoder at 0x7cbc272c3240>, *, omit_none=False, context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `encoder` | `—` | `<function default_encoder at 0x7cbc272c3240>` | pos/kw |
| `omit_none` | `—` | `False` | kw |
| `context` | `—` | `None` | kw |

### `validate`

```python
dbt.adapters.base.AdapterTrackingRelationInfo.validate(data: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Any` | `—` | pos/kw |

### `values`

D.values() -> an object providing a view on D's values

```python
dbt.adapters.base.AdapterTrackingRelationInfo.values(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `dbt.adapters.base.BaseAdapter` methods

### `acquire_connection`

```python
dbt.adapters.base.BaseAdapter.acquire_connection(self, name=None) -> dbt.adapters.contracts.connection.Connection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `None` | pos/kw |

**Returns:** `<class 'dbt.adapters.contracts.connection.Connection'>`

### `add_catalog_integration`

```python
dbt.adapters.base.BaseAdapter.add_catalog_integration(self, catalog_integration: dbt.adapters.catalogs._integration.CatalogIntegrationConfig) -> dbt.adapters.catalogs._integration.CatalogIntegration
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `catalog_integration` | `CatalogIntegrationConfig` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.catalogs._integration.CatalogIntegration'>`

### `already_exists`

DEPRECATED: Return if a model already exists in the database

```python
dbt.adapters.base.BaseAdapter.already_exists(self, schema: str, name: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `schema` | `str` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `assert_valid_snapshot_target_given_strategy`

```python
dbt.adapters.base.BaseAdapter.assert_valid_snapshot_target_given_strategy(self, relation: dbt.adapters.base.relation.BaseRelation, column_names: Dict[str, str], strategy: dbt.adapters.base.impl.SnapshotStrategy) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `relation` | `BaseRelation` | `—` | pos/kw |
| `column_names` | `Dict` | `—` | pos/kw |
| `strategy` | `SnapshotStrategy` | `—` | pos/kw |

### `build_catalog_relation`

```python
dbt.adapters.base.BaseAdapter.build_catalog_relation(self, config: dbt.adapters.contracts.relation.RelationConfig) -> Optional[dbt.adapters.catalogs._integration.CatalogRelation]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `RelationConfig` | `—` | pos/kw |

**Returns:** `typing.Optional[dbt.adapters.catalogs._integration.CatalogRelation]`

### `builtin_incremental_strategies`

List of possible builtin strategies for adapters

Microbatch is added by _default_. It is only not added when the behavior flag
`require_batched_execution_for_custom_microbatch_strategy` is True.

```python
dbt.adapters.base.BaseAdapter.builtin_incremental_strategies(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cache_added`

Cache a new relation in dbt. It will show up in `list relations`.

```python
dbt.adapters.base.BaseAdapter.cache_added(self, relation: Optional[dbt.adapters.base.relation.BaseRelation]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `relation` | `Optional` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `cache_dropped`

Drop a relation in dbt. It will no longer show up in
`list relations`, and any bound views will be dropped from the cache

```python
dbt.adapters.base.BaseAdapter.cache_dropped(self, relation: Optional[dbt.adapters.base.relation.BaseRelation]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `relation` | `Optional` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `cache_renamed`

Rename a relation in dbt. It will show up with a new name in
`list_relations`, but bound views will remain bound.

```python
dbt.adapters.base.BaseAdapter.cache_renamed(self, from_relation: Optional[dbt.adapters.base.relation.BaseRelation], to_relation: Optional[dbt.adapters.base.relation.BaseRelation]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `from_relation` | `Optional` | `—` | pos/kw |
| `to_relation` | `Optional` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `calculate_freshness`

Calculate the freshness of sources in dbt, and return it

```python
dbt.adapters.base.BaseAdapter.calculate_freshness(self, source: dbt.adapters.base.relation.BaseRelation, loaded_at_field: str, filter: Optional[str], macro_resolver: Optional[dbt.adapters.contracts.macros.MacroResolverProtocol] = None) -> Tuple[Optional[dbt.adapters.contracts.connection.AdapterResponse], dbt.adapters.base.impl.FreshnessResponse]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `BaseRelation` | `—` | pos/kw |
| `loaded_at_field` | `str` | `—` | pos/kw |
| `filter` | `Optional` | `—` | pos/kw |
| `macro_resolver` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[typing.Optional[dbt.adapters.contracts.connection.AdapterResponse], dbt.adapters.base.impl.FreshnessResponse]`

### `calculate_freshness_from_custom_sql`

```python
dbt.adapters.base.BaseAdapter.calculate_freshness_from_custom_sql(self, source: dbt.adapters.base.relation.BaseRelation, sql: str, macro_resolver: Optional[dbt.adapters.contracts.macros.MacroResolverProtocol] = None) -> Tuple[Optional[dbt.adapters.contracts.connection.AdapterResponse], dbt.adapters.base.impl.FreshnessResponse]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `BaseRelation` | `—` | pos/kw |
| `sql` | `str` | `—` | pos/kw |
| `macro_resolver` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[typing.Optional[dbt.adapters.contracts.connection.AdapterResponse], dbt.adapters.base.impl.FreshnessResponse]`

### `calculate_freshness_from_metadata`

```python
dbt.adapters.base.BaseAdapter.calculate_freshness_from_metadata(self, source: dbt.adapters.base.relation.BaseRelation, macro_resolver: Optional[dbt.adapters.contracts.macros.MacroResolverProtocol] = None) -> Tuple[Optional[dbt.adapters.contracts.connection.AdapterResponse], dbt.adapters.base.impl.FreshnessResponse]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `BaseRelation` | `—` | pos/kw |
| `macro_resolver` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[typing.Optional[dbt.adapters.contracts.connection.AdapterResponse], dbt.adapters.base.impl.FreshnessResponse]`

### `calculate_freshness_from_metadata_batch`

Given a list of sources (BaseRelations), calculate the metadata-based freshness in batch.
This method should _not_ execute a warehouse query per source, but rather batch up
the sources into as few re…

```python
dbt.adapters.base.BaseAdapter.calculate_freshness_from_metadata_batch(self, sources: List[dbt.adapters.base.relation.BaseRelation], macro_resolver: Optional[dbt.adapters.contracts.macros.MacroResolverProtocol] = None) -> Tuple[List[Optional[dbt.adapters.contracts.connection.AdapterResponse]], Dict[dbt.adapters.base.relation.BaseRelation, dbt.adapters.base.impl.FreshnessResponse]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sources` | `List` | `—` | pos/kw |
| `macro_resolver` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[typing.List[typing.Optional[dbt.adapters.contracts.connection.AdapterResponse]], typing.Dict[dbt.adapters.base.relation.BaseRelation, dbt.adapters.base.impl.FreshnessResponse]]`

### `cancel_open_connections`

Cancel all open connections.

```python
dbt.adapters.base.BaseAdapter.cancel_open_connections(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `capabilities`

```python
dbt.adapters.base.BaseAdapter.capabilities() -> dbt.adapters.capability.CapabilityDict
```

**Returns:** `<class 'dbt.adapters.capability.CapabilityDict'>`

### `check_schema_exists`

Check if a schema exists.

The default implementation of this is potentially unnecessarily slow,
and adapters should implement it if there is an optimized path (and
there probably is)

```python
dbt.adapters.base.BaseAdapter.check_schema_exists(self, database: str, schema: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `database` | `str` | `—` | pos/kw |
| `schema` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `cleanup_connections`

```python
dbt.adapters.base.BaseAdapter.cleanup_connections(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_macro_resolver`

```python
dbt.adapters.base.BaseAdapter.clear_macro_resolver(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_transaction`

```python
dbt.adapters.base.BaseAdapter.clear_transaction(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `commit_if_has_connection`

```python
dbt.adapters.base.BaseAdapter.commit_if_has_connection(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `connection_named`

```python
dbt.adapters.base.BaseAdapter.connection_named(self, name: str, query_header_context: Any = None, should_release_connection=True) -> Iterator[NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `query_header_context` | `Any` | `None` | pos/kw |
| `should_release_connection` | `—` | `True` | pos/kw |

**Returns:** `typing.Iterator[NoneType]`

### `convert_agate_type`

```python
dbt.adapters.base.BaseAdapter.convert_agate_type(agate_table: 'agate.Table', col_idx: int) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `convert_boolean_type`

Return the type in the database that best maps to the agate.Boolean
type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table for…

```python
dbt.adapters.base.BaseAdapter.convert_boolean_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_date_type`

Return the type in the database that best maps to the agate.Date
type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table for the…

```python
dbt.adapters.base.BaseAdapter.convert_date_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_datetime_type`

Return the type in the database that best maps to the agate.DateTime
type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table for…

```python
dbt.adapters.base.BaseAdapter.convert_datetime_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_integer_type`

Return the type in the database that best maps to the agate.Number
type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table for t…

```python
dbt.adapters.base.BaseAdapter.convert_integer_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_number_type`

Return the type in the database that best maps to the agate.Number
type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table for t…

```python
dbt.adapters.base.BaseAdapter.convert_number_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_text_type`

Return the type in the database that best maps to the agate.Text
type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table for the…

```python
dbt.adapters.base.BaseAdapter.convert_text_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_time_type`

Return the type in the database that best maps to the
agate.TimeDelta type for the given agate table and column index.

:param agate_table: The table
:param col_idx: The index into the agate table fo…

```python
dbt.adapters.base.BaseAdapter.convert_time_type(agate_table: 'agate.Table', col_idx: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `convert_type`

```python
dbt.adapters.base.BaseAdapter.convert_type(agate_table: 'agate.Table', col_idx: int) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `agate_table` | `agate.Table` | `—` | pos/kw |
| `col_idx` | `int` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `dbt.adapters.base.BaseConnectionManager` methods

### `add_select_query`

This was added here because base.impl.BaseAdapter.get_column_schema_from_query expects it to be here.
That method wouldn't work unless the adapter used sql.impl.SQLAdapter, sql.connections.SQLConnect…

```python
dbt.adapters.base.BaseConnectionManager.add_select_query(self, sql: str) -> Tuple[dbt.adapters.contracts.connection.Connection, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str` | `—` | pos/kw |

**Returns:** `typing.Tuple[dbt.adapters.contracts.connection.Connection, typing.Any]`

### `begin`

Begin a transaction. (passable)

```python
dbt.adapters.base.BaseConnectionManager.begin(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cancel_open`

Cancel all open connections on the adapter. (passable)

```python
dbt.adapters.base.BaseConnectionManager.cancel_open(self) -> Optional[List[str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.List[str]]`

### `cleanup_all`

```python
dbt.adapters.base.BaseConnectionManager.cleanup_all(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_thread_connection`

```python
dbt.adapters.base.BaseConnectionManager.clear_thread_connection(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_transaction`

Clear any existing transactions.

```python
dbt.adapters.base.BaseConnectionManager.clear_transaction(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `close`

```python
dbt.adapters.base.BaseConnectionManager.close(connection: dbt.adapters.contracts.connection.Connection) -> dbt.adapters.contracts.connection.Connection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `connection` | `Connection` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.contracts.connection.Connection'>`

### `commit`

Commit a transaction. (passable)

```python
dbt.adapters.base.BaseConnectionManager.commit(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `commit_if_has_connection`

If the named connection exists, commit the current transaction.

```python
dbt.adapters.base.BaseConnectionManager.commit_if_has_connection(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `data_type_code_to_name`

Get the string representation of the data type from the type_code.

```python
dbt.adapters.base.BaseConnectionManager.data_type_code_to_name(type_code: Union[int, str]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type_code` | `Union` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `exception_handler`

Create a context manager that handles exceptions caused by database
interactions.

:param str sql: The SQL string that the block inside the context
    manager is executing.
:return: A context manage…

```python
dbt.adapters.base.BaseConnectionManager.exception_handler(self, sql: str) -> ContextManager
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str` | `—` | pos/kw |

**Returns:** `typing.ContextManager`

### `execute`

Execute the given SQL.

:param str sql: The sql to execute.
:param bool auto_begin: If set, and dbt is not currently inside a
    transaction, automatically begin one.
:param bool fetch: If set, fetc…

```python
dbt.adapters.base.BaseConnectionManager.execute(self, sql: str, auto_begin: bool = False, fetch: bool = False, limit: Optional[int] = None) -> Tuple[dbt.adapters.contracts.connection.AdapterResponse, ForwardRef('agate.Table')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sql` | `str` | `—` | pos/kw |
| `auto_begin` | `bool` | `False` | pos/kw |
| `fetch` | `bool` | `False` | pos/kw |
| `limit` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[dbt.adapters.contracts.connection.AdapterResponse, ForwardRef('agate.Table')]`

### `get_if_exists`

```python
dbt.adapters.base.BaseConnectionManager.get_if_exists(self) -> Optional[dbt.adapters.contracts.connection.Connection]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[dbt.adapters.contracts.connection.Connection]`

### `get_thread_connection`

```python
dbt.adapters.base.BaseConnectionManager.get_thread_connection(self) -> dbt.adapters.contracts.connection.Connection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.contracts.connection.Connection'>`

### `get_thread_identifier`

```python
dbt.adapters.base.BaseConnectionManager.get_thread_identifier() -> Hashable
```

**Returns:** `typing.Hashable`

### `open`

Open the given connection on the adapter and return it.

This may mutate the given connection (in particular, its state and its
handle).

This should be thread-safe, or hold the lock if necessary. Th…

```python
dbt.adapters.base.BaseConnectionManager.open(connection: dbt.adapters.contracts.connection.Connection) -> dbt.adapters.contracts.connection.Connection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `connection` | `Connection` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.contracts.connection.Connection'>`

### `release`

```python
dbt.adapters.base.BaseConnectionManager.release(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `retry_connection`

Given a Connection, set its handle by calling connect.

The calls to connect will be retried up to retry_limit times to deal with transient
connection errors. By default, one retry will be attempted…

```python
dbt.adapters.base.BaseConnectionManager.retry_connection(connection: dbt.adapters.contracts.connection.Connection, connect: Callable[[], Any], logger: dbt.adapters.events.logging.AdapterLogger, retryable_exceptions: Iterable[Type[Exception]], retry_limit: int = 1, retry_timeout: Union[Callable[[int], Union[int, float]], int, float] = 1, _attempts: int = 0) -> dbt.adapters.contracts.connection.Connection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `connection` | `Connection` | `—` | pos/kw |
| `connect` | `Callable` | `—` | pos/kw |
| `logger` | `AdapterLogger` | `—` | pos/kw |
| `retryable_exceptions` | `Iterable` | `—` | pos/kw |
| `retry_limit` | `int` | `1` | pos/kw |
| `retry_timeout` | `Union` | `1` | pos/kw |
| `_attempts` | `int` | `0` | pos/kw |

**Returns:** `<class 'dbt.adapters.contracts.connection.Connection'>`

### `rollback_if_open`

```python
dbt.adapters.base.BaseConnectionManager.rollback_if_open(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_connection_name`

Called by 'acquire_connection' in BaseAdapter, which is called by
'connection_named'.
Creates a connection for this thread if one doesn't already
exist, and will rename an existing connection.

```python
dbt.adapters.base.BaseConnectionManager.set_connection_name(self, name: Optional[str] = None) -> dbt.adapters.contracts.connection.Connection
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'dbt.adapters.contracts.connection.Connection'>`

### `set_query_header`

```python
dbt.adapters.base.BaseConnectionManager.set_query_header(self, query_header_context: Dict[str, Any]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query_header_context` | `Dict` | `—` | pos/kw |

### `set_thread_connection`

```python
dbt.adapters.base.BaseConnectionManager.set_thread_connection(self, conn: dbt.adapters.contracts.connection.Connection) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `Connection` | `—` | pos/kw |

### `dbt.adapters.base.BaseRelation` methods

### `add_ephemeral_prefix`

```python
dbt.adapters.base.BaseRelation.add_ephemeral_prefix(name: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

### `create`

```python
dbt.adapters.base.BaseRelation.create(database: Optional[str] = None, schema: Optional[str] = None, identifier: Optional[str] = None, type: Optional[dbt.adapters.contracts.relation.RelationType] = None, **kwargs) -> ~Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `database` | `Optional` | `None` | pos/kw |
| `schema` | `Optional` | `None` | pos/kw |
| `identifier` | `Optional` | `None` | pos/kw |
| `type` | `Optional` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `~Self`

### `create_ephemeral_from`

```python
dbt.adapters.base.BaseRelation.create_ephemeral_from(relation_config: dbt.adapters.contracts.relation.RelationConfig, limit: Optional[int] = None, event_time_filter: Optional[dbt.adapters.base.relation.EventTimeFilter] = None) -> ~Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `relation_config` | `RelationConfig` | `—` | pos/kw |
| `limit` | `Optional` | `None` | pos/kw |
| `event_time_filter` | `Optional` | `None` | pos/kw |

**Returns:** `~Self`

### `create_from`

```python
dbt.adapters.base.BaseRelation.create_from(quoting: dbt.adapters.contracts.relation.HasQuoting, relation_config: dbt.adapters.contracts.relation.RelationConfig, **kwargs: Any) -> ~Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `quoting` | `HasQuoting` | `—` | pos/kw |
| `relation_config` | `RelationConfig` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `~Self`

### `from_dict`

```python
dbt.adapters.base.BaseRelation.from_dict(d, *, dialect=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `dialect` | `—` | `None` | kw |

### `from_msgpack`

```python
dbt.adapters.base.BaseRelation.from_msgpack(d, decoder=<function default_decoder at 0x7cbc2732c900>, *, dialect=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `d` | `—` | `—` | pos/kw |
| `decoder` | `—` | `<function default_decoder at 0x7cbc2732c900>` | pos/kw |
| `dialect` | `—` | `None` | kw |

### `get`

Override `.get` to return a metadata object so we don't break
dbt_utils.

```python
dbt.adapters.base.BaseRelation.get(self, key, default=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

### `get_default_include_policy`

```python
dbt.adapters.base.BaseRelation.get_default_include_policy() -> dbt.adapters.contracts.relation.Policy
```

**Returns:** `<class 'dbt.adapters.contracts.relation.Policy'>`

### `get_default_quote_policy`

```python
dbt.adapters.base.BaseRelation.get_default_quote_policy() -> dbt.adapters.contracts.relation.Policy
```

**Returns:** `<class 'dbt.adapters.contracts.relation.Policy'>`

### `get_function_config`

```python
dbt.adapters.base.BaseRelation.get_function_config(self, model: Dict[str, Any]) -> Optional[dbt.adapters.base.relation.FunctionConfig]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `model` | `Dict` | `—` | pos/kw |

**Returns:** `typing.Optional[dbt.adapters.base.relation.FunctionConfig]`

### `get_function_macro_name`

```python
dbt.adapters.base.BaseRelation.get_function_macro_name(self, config: dbt.adapters.base.relation.FunctionConfig) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `FunctionConfig` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `include`

```python
dbt.adapters.base.BaseRelation.include(self: ~Self, database: Optional[bool] = None, schema: Optional[bool] = None, identifier: Optional[bool] = None) -> ~Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `Self` | `—` | pos/kw |
| `database` | `Optional` | `None` | pos/kw |
| `schema` | `Optional` | `None` | pos/kw |
| `identifier` | `Optional` | `None` | pos/kw |

**Returns:** `~Self`

### `incorporate`

```python
dbt.adapters.base.BaseRelation.incorporate(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `information_schema`

```python
dbt.adapters.base.BaseRelation.information_schema(self, view_name=None) -> 'InformationSchema'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `view_name` | `—` | `None` | pos/kw |

**Returns:** `InformationSchema`

### `information_schema_only`

```python
dbt.adapters.base.BaseRelation.information_schema_only(self) -> 'InformationSchema'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `InformationSchema`

### `items`

D.items() -> a set-like object providing a view on D's items

```python
dbt.adapters.base.BaseRelation.items(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `json_schema`

```python
dbt.adapters.base.BaseRelation.json_schema()
```

### `keys`

D.keys() -> a set-like object providing a view on D's keys

```python
dbt.adapters.base.BaseRelation.keys(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `matches`

```python
dbt.adapters.base.BaseRelation.matches(self, database: Optional[str] = None, schema: Optional[str] = None, identifier: Optional[str] = None) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `database` | `Optional` | `None` | pos/kw |
| `schema` | `Optional` | `None` | pos/kw |
| `identifier` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'bool'>`

### `quote`

```python
dbt.adapters.base.BaseRelation.quote(self: ~Self, database: Optional[bool] = None, schema: Optional[bool] = None, identifier: Optional[bool] = None) -> ~Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `Self` | `—` | pos/kw |
| `database` | `Optional` | `None` | pos/kw |
| `schema` | `Optional` | `None` | pos/kw |
| `identifier` | `Optional` | `None` | pos/kw |

**Returns:** `~Self`

### `quoted`

```python
dbt.adapters.base.BaseRelation.quoted(self, identifier)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `identifier` | `—` | `—` | pos/kw |

### `render`

```python
dbt.adapters.base.BaseRelation.render(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `render_event_time_filtered`

```python
dbt.adapters.base.BaseRelation.render_event_time_filtered(self, rendered: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `rendered` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `render_limited`

```python
dbt.adapters.base.BaseRelation.render_limited(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `replace`

```python
dbt.adapters.base.BaseRelation.replace(self: ~_R, **kwargs: Any) -> ~_R
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `_R` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `~_R`

### `replace_path`

```python
dbt.adapters.base.BaseRelation.replace_path(self, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `scd_args`

```python
dbt.adapters.base.BaseRelation.scd_args(primary_key: Union[str, List[str]], updated_at) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `primary_key` | `Union` | `—` | pos/kw |
| `updated_at` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `to_dict`

```python
dbt.adapters.base.BaseRelation.to_dict(self, *, omit_none=False, context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `omit_none` | `—` | `False` | kw |
| `context` | `—` | `None` | kw |

### `to_msgpack`

```python
dbt.adapters.base.BaseRelation.to_msgpack(self, encoder=<function default_encoder at 0x7cbc272c3240>, *, omit_none=False, context=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `encoder` | `—` | `<function default_encoder at 0x7cbc272c3240>` | pos/kw |
| `omit_none` | `—` | `False` | kw |
| `context` | `—` | `None` | kw |

### `validate`

```python
dbt.adapters.base.BaseRelation.validate(data: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `Any` | `—` | pos/kw |

### `dbt.adapters.base.Column` methods

### `can_expand_to`

returns True if this column can be expanded to the size of the
other column

```python
dbt.adapters.base.Column.can_expand_to(self, other_column: 'Column') -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other_column` | `Column` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `create`

```python
dbt.adapters.base.Column.create(name, label_or_dtype: str) -> 'Column'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `label_or_dtype` | `str` | `—` | pos/kw |

**Returns:** `Column`

### `from_description`

```python
dbt.adapters.base.Column.from_description(name: str, raw_data_type: str) -> 'Column'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `raw_data_type` | `str` | `—` | pos/kw |

**Returns:** `Column`

### `is_float`

```python
dbt.adapters.base.Column.is_float(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_integer`

```python
dbt.adapters.base.Column.is_integer(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `is_number`

```python
dbt.adapters.base.Column.is_number(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_numeric`

```python
dbt.adapters.base.Column.is_numeric(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `is_string`

```python
dbt.adapters.base.Column.is_string(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `literal`

```python
dbt.adapters.base.Column.literal(self, value: Any) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `numeric_type`

```python
dbt.adapters.base.Column.numeric_type(dtype: str, precision: Any, scale: Any) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dtype` | `str` | `—` | pos/kw |
| `precision` | `Any` | `—` | pos/kw |
| `scale` | `Any` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `string_size`

```python
dbt.adapters.base.Column.string_size(self) -> int
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'int'>`

### `string_type`

```python
dbt.adapters.base.Column.string_type(size: int) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `size` | `int` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `translate_type`

```python
dbt.adapters.base.Column.translate_type(dtype: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dtype` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dbt.adapters.base.PythonJobHelper` methods

### `submit`

```python
dbt.adapters.base.PythonJobHelper.submit(self, compiled_code: str) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `compiled_code` | `str` | `—` | pos/kw |

**Returns:** `typing.Any`

### `dbt.adapters.base.SchemaSearchMap` methods

### `add`

```python
dbt.adapters.base.SchemaSearchMap.add(self, relation: dbt.adapters.base.relation.BaseRelation)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `relation` | `BaseRelation` | `—` | pos/kw |

### `flatten`

```python
dbt.adapters.base.SchemaSearchMap.flatten(self, allow_multiple_databases: bool = False) -> 'SchemaSearchMap'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `allow_multiple_databases` | `bool` | `False` | pos/kw |

**Returns:** `SchemaSearchMap`

### `search`

```python
dbt.adapters.base.SchemaSearchMap.search(self) -> Iterator[Tuple[dbt.adapters.base.relation.InformationSchema, Optional[str]]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Iterator[typing.Tuple[dbt.adapters.base.relation.InformationSchema, typing.Optional[str]]]`

### `dbt.adapters.cache.CacheAction` methods

### `code`

```python
dbt.adapters.cache.CacheAction.code(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `format_ref_key`

```python
dbt.adapters.cache.CacheAction.format_ref_key(self, ref_key) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ref_key` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `level_tag`

```python
dbt.adapters.cache.CacheAction.level_tag(self) -> dbt_common.events.base_types.EventLevel
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<enum 'EventLevel'>`

### `message`

```python
dbt.adapters.cache.CacheAction.message(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `to_dict`

```python
dbt.adapters.cache.CacheAction.to_dict(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `to_json`

```python
dbt.adapters.cache.CacheAction.to_json(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dbt.adapters.cache.CacheDumpGraph` methods

### `code`

```python
dbt.adapters.cache.CacheDumpGraph.code(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `level_tag`

```python
dbt.adapters.cache.CacheDumpGraph.level_tag(self) -> dbt_common.events.base_types.EventLevel
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<enum 'EventLevel'>`

### `message`

```python
dbt.adapters.cache.CacheDumpGraph.message(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `to_dict`

```python
dbt.adapters.cache.CacheDumpGraph.to_dict(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `to_json`

```python
dbt.adapters.cache.CacheDumpGraph.to_json(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dbt.adapters.cache.DependentLinkNotCachedError` methods

### `data`

```python
dbt.adapters.cache.DependentLinkNotCachedError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `process_stack`

```python
dbt.adapters.cache.DependentLinkNotCachedError.process_stack(self) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `dbt.adapters.cache.NewNameAlreadyInCacheError` methods

### `data`

```python
dbt.adapters.cache.NewNameAlreadyInCacheError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `process_stack`

```python
dbt.adapters.cache.NewNameAlreadyInCacheError.process_stack(self) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `dbt.adapters.cache.NoneRelationFoundError` methods

### `data`

```python
dbt.adapters.cache.NoneRelationFoundError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `process_stack`

```python
dbt.adapters.cache.NoneRelationFoundError.process_stack(self) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `dbt.adapters.cache.ReferencedLinkNotCachedError` methods

### `data`

```python
dbt.adapters.cache.ReferencedLinkNotCachedError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `process_stack`

```python
dbt.adapters.cache.ReferencedLinkNotCachedError.process_stack(self) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `dbt.adapters.cache.RelationsCache` methods

### `add`

Add the relation inner to the cache, under the schema schema and
identifier identifier

:param BaseRelation relation: The underlying relation.

```python
dbt.adapters.cache.RelationsCache.add(self, relation)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `relation` | `—` | `—` | pos/kw |

### `add_link`

Add a link between two relations to the database. If either relation
does not exist, it will be added as an "external" relation.

The dependent model refers _to_ the referenced model. So, given
argum…

```python
dbt.adapters.cache.RelationsCache.add_link(self, referenced, dependent)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `referenced` | `—` | `—` | pos/kw |
| `dependent` | `—` | `—` | pos/kw |

### `add_schema`

Add a schema to the set of known schemas (case-insensitive)

:param database: The database name to add.
:param schema: The schema name to add.

```python
dbt.adapters.cache.RelationsCache.add_schema(self, database: Optional[str], schema: Optional[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `database` | `Optional` | `—` | pos/kw |
| `schema` | `Optional` | `—` | pos/kw |

### `clear`

Clear the cache

```python
dbt.adapters.cache.RelationsCache.clear(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `drop`

Drop the named relation and cascade it appropriately to all
dependent relations.

Because dbt proactively does many `drop relation if exist ... cascade`
that are noops, nonexistent relation drops cau…

```python
dbt.adapters.cache.RelationsCache.drop(self, relation)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `relation` | `—` | `—` | pos/kw |

### `drop_schema`

Drop the given schema and remove it from the set of known schemas.

Then remove all its contents (and their dependents, etc) as well.

```python
dbt.adapters.cache.RelationsCache.drop_schema(self, database: Optional[str], schema: Optional[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `database` | `Optional` | `—` | pos/kw |
| `schema` | `Optional` | `—` | pos/kw |

### `dump_graph`

Dump a key-only representation of the schema to a dictionary. Every
known relation is a key with a value of a list of keys it is referenced
by.

```python
dbt.adapters.cache.RelationsCache.dump_graph(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_relations`

Case-insensitively yield all relations matching the given schema.

:param str schema: The case-insensitive schema name to list from.
:return List[BaseRelation]: The list of relations with the given…

```python
dbt.adapters.cache.RelationsCache.get_relations(self, database: Optional[str], schema: Optional[str]) -> List[Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `database` | `Optional` | `—` | pos/kw |
| `schema` | `Optional` | `—` | pos/kw |

**Returns:** `typing.List[typing.Any]`

### `rename`

Rename the old schema/identifier to the new schema/identifier and
update references.

If the new schema/identifier is already present, that is an error.
If the schema/identifier key is absent, we onl…

```python
dbt.adapters.cache.RelationsCache.rename(self, old, new)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `old` | `—` | `—` | pos/kw |
| `new` | `—` | `—` | pos/kw |

### `update_schemas`

Add multiple schemas to the set of known schemas (case-insensitive)

:param schemas: An iterable of the schema names to add.

```python
dbt.adapters.cache.RelationsCache.update_schemas(self, schemas: Iterable[Tuple[Optional[str], str]])
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `schemas` | `Iterable` | `—` | pos/kw |

### `dbt.adapters.cache.TruncatedModelNameCausedCollisionError` methods

### `data`

```python
dbt.adapters.cache.TruncatedModelNameCausedCollisionError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `get_message`

```python
dbt.adapters.cache.TruncatedModelNameCausedCollisionError.get_message(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `process_stack`

```python
dbt.adapters.cache.TruncatedModelNameCausedCollisionError.process_stack(self) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `dbt.adapters.catalogs.CatalogIntegration` methods

### `build_relation`

Builds relation configuration within the context of this catalog integration.

This method is a placeholder and must be implemented in subclasses to provide
custom logic for building a relation.

Arg…

```python
dbt.adapters.catalogs.CatalogIntegration.build_relation(self, config: dbt.adapters.contracts.relation.RelationConfig) -> dbt.adapters.catalogs._integration.CatalogRelation
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `RelationConfig` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.catalogs._integration.CatalogRelation'>`

### `dbt.adapters.catalogs.CatalogIntegrationClient` methods

### `add`

```python
dbt.adapters.catalogs.CatalogIntegrationClient.add(self, config: dbt.adapters.catalogs._integration.CatalogIntegrationConfig) -> dbt.adapters.catalogs._integration.CatalogIntegration
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `CatalogIntegrationConfig` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.catalogs._integration.CatalogIntegration'>`

### `get`

```python
dbt.adapters.catalogs.CatalogIntegrationClient.get(self, name: str) -> dbt.adapters.catalogs._integration.CatalogIntegration
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `<class 'dbt.adapters.catalogs._integration.CatalogIntegration'>`

### `dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError` methods

### `add_node`

```python
dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError.add_node(self, node=None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `None` | pos/kw |

### `data`

```python
dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `node_to_string`

Given a node-like object we attempt to create the best identifier we can.

```python
dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError.node_to_string(self, node: Any) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `Any` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `process_stack`

```python
dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError.process_stack(self) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.List[str]`

### `validator_error_message`

Given a dbt.dataclass_schema.ValidationError return the relevant parts as a string.

dbt.dataclass_schema.ValidationError is basically a jsonschema.ValidationError)

```python
dbt.adapters.catalogs.DbtCatalogIntegrationAlreadyExistsError.validator_error_message(self, exc: Exception) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `exc` | `Exception` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `dbt.adapters.catalogs.DbtCatalogIntegrationNotFoundError` methods

### `add_node`

```python
dbt.adapters.catalogs.DbtCatalogIntegrationNotFoundError.add_node(self, node=None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `None` | pos/kw |

### `data`

```python
dbt.adapters.catalogs.DbtCatalogIntegrationNotFoundError.data(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`


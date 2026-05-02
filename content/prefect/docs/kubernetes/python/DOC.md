---
name: kubernetes
description: "Prefect Kubernetes integration for deploying Prefect flows to Kubernetes-backed work pools and workers"
metadata:
  languages: "python"
  versions: "0.7.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "prefect,python,kubernetes,workflow,orchestration,workers,deployment,flow,deploy,sync_customers,KubernetesClusterConfig,adelete,aload,aload_from_ref,annotation_refers_to_block_class,aregister_type_and_schema,asave,block_initialization,configure_client,construct,copy,delete,dict,from_file,from_orm,get_api_client,get_block_capabilities,get_block_class_from_key,get_block_class_from_schema,get_block_placeholder,get_block_schema_version,get_block_type_name,get_block_type_slug,get_code_example,get_description,is_block_class,json,load,load_from_ref,model_construct,model_copy,KubernetesCredentials,get_client,get_resource_specific_client,model_dump,KubernetesJob,atrigger,from_yaml_file,KubernetesWorker,get_all_available_worker_types,get_and_submit_flow_runs,get_default_base_job_template,get_documentation_url,get_flow_run_logger,get_logo_url,get_name_slug,get_status,get_worker_class_from_type,is_worker_still_polling,kill_infrastructure,run,setup,start,submit,sync_with_backend,teardown"
---

# prefect — kubernetes

## Install

```bash
pip install prefect
```

## Imports

```python
import prefect
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `KubernetesClusterConfig` | Class | Stores configuration for interaction with Kubernetes clusters.  See `from_file`… |
| `adelete` | Method | Asynchronously deletes the block document with the specified name.  Args:     n… |
| `aload` | Method | Retrieves data from the block document with the given name for the block type t… |
| `aload_from_ref` | Method | Asynchronously retrieves data from the block document by given reference for th… |
| `annotation_refers_to_block_class` | Method |  |
| `aregister_type_and_schema` | Method | Asynchronously makes block available for configuration with current Prefect API… |
| `asave` | Method | Asynchronously saves the values of a block as a block document.  Args:     name… |
| `block_initialization` | Method |  |
| `configure_client` | Method | Activates this cluster configuration by loading the configuration into the Kube… |
| `construct` | Method |  |
| `copy` | Method | Returns a copy of the model.  !!! warning "Deprecated"     This method is now d… |
| `delete` | Method | Deletes the block document with the specified name.  This function will dispatc… |
| `dict` | Method |  |
| `from_file` | Method | Create a cluster config from the a Kubernetes config file.  By default, the cur… |
| `from_orm` | Method |  |
| `get_api_client` | Method | Returns a Kubernetes API client for this cluster config. |
| `get_block_capabilities` | Method | Returns the block capabilities for this Block. Recursively collects all block c… |
| `get_block_class_from_key` | Method | Retrieve the block class implementation given a key. |
| `get_block_class_from_schema` | Method | Retrieve the block class implementation given a schema. |
| `get_block_placeholder` | Method | Returns the block placeholder for the current block which can be used for templ… |
| `get_block_schema_version` | Method |  |
| `get_block_type_name` | Method |  |
| `get_block_type_slug` | Method |  |
| `get_code_example` | Method | Returns the code example for the given block. Attempts to parse code example fr… |
| `get_description` | Method | Returns the description for the current block. Attempts to parse description fr… |
| `is_block_class` | Method |  |
| `json` | Method |  |
| `load` | Method | Retrieves data from the block document with the given name for the block type t… |
| `load_from_ref` | Method | Retrieves data from the block document by given reference for the block type th… |
| `model_construct` | Method | Creates a new instance of the `Model` class with validated data.  Creates a new… |
| `model_copy` | Method | !!! abstract "Usage Documentation"     [`model_copy`](../concepts/models.md#mod… |
| `KubernetesCredentials` | Class | Credentials block for generating configured Kubernetes API clients.  Attributes… |
| `adelete` | Method | Asynchronously deletes the block document with the specified name.  Args:     n… |
| `aload` | Method | Retrieves data from the block document with the given name for the block type t… |
| `aload_from_ref` | Method | Asynchronously retrieves data from the block document by given reference for th… |
| `annotation_refers_to_block_class` | Method |  |
| `aregister_type_and_schema` | Method | Asynchronously makes block available for configuration with current Prefect API… |
| `asave` | Method | Asynchronously saves the values of a block as a block document.  Args:     name… |
| `block_initialization` | Method |  |
| `construct` | Method |  |
| `copy` | Method | Returns a copy of the model.  !!! warning "Deprecated"     This method is now d… |
| `delete` | Method | Deletes the block document with the specified name.  This function will dispatc… |
| `dict` | Method |  |
| `from_orm` | Method |  |
| `get_block_capabilities` | Method | Returns the block capabilities for this Block. Recursively collects all block c… |
| `get_block_class_from_key` | Method | Retrieve the block class implementation given a key. |
| `get_block_class_from_schema` | Method | Retrieve the block class implementation given a schema. |
| `get_block_placeholder` | Method | Returns the block placeholder for the current block which can be used for templ… |
| `get_block_schema_version` | Method |  |
| `get_block_type_name` | Method |  |
| `get_block_type_slug` | Method |  |
| `get_client` | Method | Convenience method for retrieving a Kubernetes API client for deployment resour… |
| `get_code_example` | Method | Returns the code example for the given block. Attempts to parse code example fr… |
| `get_description` | Method | Returns the description for the current block. Attempts to parse description fr… |
| `get_resource_specific_client` | Method | Utility function for configuring a generic Kubernetes client. It will attempt t… |
| `is_block_class` | Method |  |
| `json` | Method |  |
| `load` | Method | Retrieves data from the block document with the given name for the block type t… |
| `load_from_ref` | Method | Retrieves data from the block document by given reference for the block type th… |
| `model_construct` | Method | Creates a new instance of the `Model` class with validated data.  Creates a new… |
| `model_copy` | Method | !!! abstract "Usage Documentation"     [`model_copy`](../concepts/models.md#mod… |
| `model_dump` | Method | !!! abstract "Usage Documentation"     [`model_dump`](../concepts/serialization… |
| `KubernetesJob` | Class | A block representing a Kubernetes job configuration. |
| `adelete` | Method | Asynchronously deletes the block document with the specified name.  Args:     n… |
| `aload` | Method | Retrieves data from the block document with the given name for the block type t… |
| `aload_from_ref` | Method | Asynchronously retrieves data from the block document by given reference for th… |
| `annotation_refers_to_block_class` | Method |  |
| `aregister_type_and_schema` | Method | Asynchronously makes block available for configuration with current Prefect API… |
| `asave` | Method | Asynchronously saves the values of a block as a block document.  Args:     name… |
| `atrigger` | Method | Async implementation: create a Kubernetes job and return a `KubernetesJobRun` o… |
| `block_initialization` | Method |  |
| `construct` | Method |  |
| `copy` | Method | Returns a copy of the model.  !!! warning "Deprecated"     This method is now d… |
| `delete` | Method | Deletes the block document with the specified name.  This function will dispatc… |
| `dict` | Method |  |
| `from_orm` | Method |  |
| `from_yaml_file` | Method | Create a `KubernetesJob` from a YAML file.  Args:     manifest_path: The YAML f… |
| `get_block_capabilities` | Method | Returns the block capabilities for this Block. Recursively collects all block c… |
| `get_block_class_from_key` | Method | Retrieve the block class implementation given a key. |
| `get_block_class_from_schema` | Method | Retrieve the block class implementation given a schema. |
| `get_block_placeholder` | Method | Returns the block placeholder for the current block which can be used for templ… |
| `get_block_schema_version` | Method |  |
| `get_block_type_name` | Method |  |
| `get_block_type_slug` | Method |  |
| `get_code_example` | Method | Returns the code example for the given block. Attempts to parse code example fr… |
| `get_description` | Method | Returns the description for the current block. Attempts to parse description fr… |
| `is_block_class` | Method |  |
| `json` | Method |  |
| `load` | Method | Retrieves data from the block document with the given name for the block type t… |
| `load_from_ref` | Method | Retrieves data from the block document by given reference for the block type th… |
| `model_construct` | Method | Creates a new instance of the `Model` class with validated data.  Creates a new… |
| `model_copy` | Method | !!! abstract "Usage Documentation"     [`model_copy`](../concepts/models.md#mod… |
| `model_dump` | Method | !!! abstract "Usage Documentation"     [`model_dump`](../concepts/serialization… |
| `KubernetesWorker` | Class | Prefect worker that executes flow runs within Kubernetes Jobs. |
| `get_all_available_worker_types` | Method | Returns all worker types available in the local registry. |
| `get_and_submit_flow_runs` | Method |  |
| `get_default_base_job_template` | Method |  |
| `get_description` | Method |  |
| `get_documentation_url` | Method |  |
| `get_flow_run_logger` | Method |  |
| `get_logo_url` | Method |  |
| `get_name_slug` | Method |  |
| `get_status` | Method | Retrieves the status of the current worker including its name, current worker p… |
| `get_worker_class_from_type` | Method | Returns the worker class for a given worker type. If the worker type is not rec… |
| `is_worker_still_polling` | Method | This method is invoked by a webserver healthcheck handler and returns a boolean… |
| `kill_infrastructure` | Method | Kill a Kubernetes job by deleting it.  Args:     infrastructure_pid: The infras… |
| `run` | Method | Executes a flow run within a Kubernetes Job and waits for the flow run to compl… |
| `setup` | Method | Prepares the worker to run. |
| `start` | Method | Starts the worker and runs the main worker loops.  By default, the worker will… |
| `submit` | Method | EXPERIMENTAL: The interface for this method is subject to change.  Submits a fl… |
| `sync_with_backend` | Method | Updates the worker's local information about it's current work pool and queues.… |
| `teardown` | Method | Cleans up resources after the worker is stopped. |
| `KubernetesClusterConfig` | Class | Stores configuration for interaction with Kubernetes clusters.  See `from_file`… |
| `adelete` | Method | Asynchronously deletes the block document with the specified name.  Args:     n… |
| `aload` | Method | Retrieves data from the block document with the given name for the block type t… |
| `aload_from_ref` | Method | Asynchronously retrieves data from the block document by given reference for th… |
| `annotation_refers_to_block_class` | Method |  |
| `aregister_type_and_schema` | Method | Asynchronously makes block available for configuration with current Prefect API… |
| `asave` | Method | Asynchronously saves the values of a block as a block document.  Args:     name… |
| `block_initialization` | Method |  |
| `configure_client` | Method | Activates this cluster configuration by loading the configuration into the Kube… |
| `construct` | Method |  |
| `copy` | Method | Returns a copy of the model.  !!! warning "Deprecated"     This method is now d… |
| `delete` | Method | Deletes the block document with the specified name.  This function will dispatc… |
| `dict` | Method |  |
| `from_file` | Method | Create a cluster config from the a Kubernetes config file.  By default, the cur… |
| `from_orm` | Method |  |
| `get_api_client` | Method | Returns a Kubernetes API client for this cluster config. |
| `get_block_capabilities` | Method | Returns the block capabilities for this Block. Recursively collects all block c… |
| `get_block_class_from_key` | Method | Retrieve the block class implementation given a key. |
| `get_block_class_from_schema` | Method | Retrieve the block class implementation given a schema. |
| `get_block_placeholder` | Method | Returns the block placeholder for the current block which can be used for templ… |
| `get_block_schema_version` | Method |  |
| `get_block_type_name` | Method |  |
| `get_block_type_slug` | Method |  |
| `get_code_example` | Method | Returns the code example for the given block. Attempts to parse code example fr… |
| `get_description` | Method | Returns the description for the current block. Attempts to parse description fr… |
| `is_block_class` | Method |  |
| `json` | Method |  |
| `load` | Method | Retrieves data from the block document with the given name for the block type t… |
| `load_from_ref` | Method | Retrieves data from the block document by given reference for the block type th… |
| `model_construct` | Method | Creates a new instance of the `Model` class with validated data.  Creates a new… |
| `model_copy` | Method | !!! abstract "Usage Documentation"     [`model_copy`](../concepts/models.md#mod… |
| `KubernetesCredentials` | Class | Credentials block for generating configured Kubernetes API clients.  Attributes… |
| `adelete` | Method | Asynchronously deletes the block document with the specified name.  Args:     n… |
| `aload` | Method | Retrieves data from the block document with the given name for the block type t… |
| `aload_from_ref` | Method | Asynchronously retrieves data from the block document by given reference for th… |
| `annotation_refers_to_block_class` | Method |  |
| `aregister_type_and_schema` | Method | Asynchronously makes block available for configuration with current Prefect API… |
| `asave` | Method | Asynchronously saves the values of a block as a block document.  Args:     name… |
| `block_initialization` | Method |  |
| `construct` | Method |  |
| `copy` | Method | Returns a copy of the model.  !!! warning "Deprecated"     This method is now d… |
| `delete` | Method | Deletes the block document with the specified name.  This function will dispatc… |
| `dict` | Method |  |
| `from_orm` | Method |  |
| `get_block_capabilities` | Method | Returns the block capabilities for this Block. Recursively collects all block c… |
| `get_block_class_from_key` | Method | Retrieve the block class implementation given a key. |
| `get_block_class_from_schema` | Method | Retrieve the block class implementation given a schema. |
| `get_block_placeholder` | Method | Returns the block placeholder for the current block which can be used for templ… |
| `get_block_schema_version` | Method |  |
| `get_block_type_name` | Method |  |
| `get_block_type_slug` | Method |  |
| `get_client` | Method | Convenience method for retrieving a Kubernetes API client for deployment resour… |
| `get_code_example` | Method | Returns the code example for the given block. Attempts to parse code example fr… |
| `get_description` | Method | Returns the description for the current block. Attempts to parse description fr… |
| `get_resource_specific_client` | Method | Utility function for configuring a generic Kubernetes client. It will attempt t… |
| `is_block_class` | Method |  |
| `json` | Method |  |
| `load` | Method | Retrieves data from the block document with the given name for the block type t… |
| `load_from_ref` | Method | Retrieves data from the block document by given reference for the block type th… |
| `model_construct` | Method | Creates a new instance of the `Model` class with validated data.  Creates a new… |
| `model_copy` | Method | !!! abstract "Usage Documentation"     [`model_copy`](../concepts/models.md#mod… |
| `model_dump` | Method | !!! abstract "Usage Documentation"     [`model_dump`](../concepts/serialization… |
| `KubernetesCredentials` | Class | Credentials block for generating configured Kubernetes API clients.  Attributes… |
| `adelete` | Method | Asynchronously deletes the block document with the specified name.  Args:     n… |
| `aload` | Method | Retrieves data from the block document with the given name for the block type t… |
| `aload_from_ref` | Method | Asynchronously retrieves data from the block document by given reference for th… |
| `annotation_refers_to_block_class` | Method |  |
| `aregister_type_and_schema` | Method | Asynchronously makes block available for configuration with current Prefect API… |
| `asave` | Method | Asynchronously saves the values of a block as a block document.  Args:     name… |
| `block_initialization` | Method |  |
| `construct` | Method |  |
| `copy` | Method | Returns a copy of the model.  !!! warning "Deprecated"     This method is now d… |
| `delete` | Method | Deletes the block document with the specified name.  This function will dispatc… |
| `dict` | Method |  |
| `from_orm` | Method |  |
| `get_block_capabilities` | Method | Returns the block capabilities for this Block. Recursively collects all block c… |
| `get_block_class_from_key` | Method | Retrieve the block class implementation given a key. |
| `get_block_class_from_schema` | Method | Retrieve the block class implementation given a schema. |
| `get_block_placeholder` | Method | Returns the block placeholder for the current block which can be used for templ… |
| `get_block_schema_version` | Method |  |
| `get_block_type_name` | Method |  |
| `get_block_type_slug` | Method |  |
| `get_client` | Method | Convenience method for retrieving a Kubernetes API client for deployment resour… |
| `get_code_example` | Method | Returns the code example for the given block. Attempts to parse code example fr… |
| `get_description` | Method | Returns the description for the current block. Attempts to parse description fr… |
| `get_resource_specific_client` | Method | Utility function for configuring a generic Kubernetes client. It will attempt t… |
| `is_block_class` | Method |  |
| `json` | Method |  |

## Classes

### `KubernetesClusterConfig`

Stores configuration for interaction with Kubernetes clusters.

See `from_file` for creation.

Attributes:
    config: The entire loaded YAML contents of a kubectl config file
    context_name: The n…

```python
prefect_kubernetes.KubernetesClusterConfig(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `KubernetesCredentials`

Credentials block for generating configured Kubernetes API clients.

Attributes:
    cluster_config: A `KubernetesClusterConfig` block holding a JSON kube
        config for a specific kubernetes con…

```python
prefect_kubernetes.KubernetesCredentials(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `KubernetesJob`

A block representing a Kubernetes job configuration.

```python
prefect_kubernetes.KubernetesJob(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `KubernetesWorker`

Prefect worker that executes flow runs within Kubernetes Jobs.

```python
prefect_kubernetes.KubernetesWorker(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `KubernetesClusterConfig`

Stores configuration for interaction with Kubernetes clusters.

See `from_file` for creation.

Attributes:
    config: The entire loaded YAML contents of a kubectl config file
    context_name: The n…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `KubernetesCredentials`

Credentials block for generating configured Kubernetes API clients.

Attributes:
    cluster_config: A `KubernetesClusterConfig` block holding a JSON kube
        config for a specific kubernetes con…

```python
prefect_kubernetes.credentials.KubernetesCredentials(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `KubernetesCredentials`

Credentials block for generating configured Kubernetes API clients.

Attributes:
    cluster_config: A `KubernetesClusterConfig` block holding a JSON kube
        config for a specific kubernetes con…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials(self, *args: 'Any', **kwargs: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

## Methods

### `prefect_kubernetes.KubernetesClusterConfig` methods

### `adelete`

Asynchronously deletes the block document with the specified name.

Args:
    name: The name of the block document to delete.
    client: The client to use to delete the block document. If not provid…

```python
prefect_kubernetes.KubernetesClusterConfig.adelete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `aload`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.KubernetesClusterConfig.aload(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `aload_from_ref`

Asynchronously retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the d…

```python
prefect_kubernetes.KubernetesClusterConfig.aload_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `annotation_refers_to_block_class`

```python
prefect_kubernetes.KubernetesClusterConfig.annotation_refers_to_block_class(annotation: 'Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotation` | `Any` | `—` | pos/kw |

**Returns:** `bool`

### `aregister_type_and_schema`

Asynchronously makes block available for configuration with current Prefect API.
Recursively registers all nested blocks. Registration is idempotent.

Args:
    client: Optional client to use for reg…

```python
prefect_kubernetes.KubernetesClusterConfig.aregister_type_and_schema(client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `asave`

Asynchronously saves the values of a block as a block document.

Args:
    name: User specified name to give saved block document which can later be used to load the
        block document.
    overw…

```python
prefect_kubernetes.KubernetesClusterConfig.asave(self, name: 'Optional[str]' = None, overwrite: 'bool' = False, client: "Optional['PrefectClient']" = None) -> 'UUID'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional[str]` | `None` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `UUID`

### `block_initialization`

```python
prefect_kubernetes.KubernetesClusterConfig.block_initialization(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `configure_client`

Activates this cluster configuration by loading the configuration into the
Kubernetes Python client. After calling this, Kubernetes API clients can use
this config's context.

```python
prefect_kubernetes.KubernetesClusterConfig.configure_client(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `construct`

```python
prefect_kubernetes.KubernetesClusterConfig.construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `copy`

Returns a copy of the model.

!!! warning "Deprecated"
    This method is now deprecated; use `model_copy` instead.

If you need `include` or `exclude`, use:

```python {test="skip" lint="skip"}
data…

```python
prefect_kubernetes.KubernetesClusterConfig.copy(self, *, include: 'AbstractSetIntStr | MappingIntStrAny | None' = None, exclude: 'AbstractSetIntStr | MappingIntStrAny | None' = None, update: 'Dict[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `exclude` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `update` | `Dict[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `delete`

Deletes the block document with the specified name.

This function will dispatch to `adelete` when called from an async context.

Args:
    name: The name of the block document to delete.
    client:…

```python
prefect_kubernetes.KubernetesClusterConfig.delete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `dict`

```python
prefect_kubernetes.KubernetesClusterConfig.dict(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False) -> 'Dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |

**Returns:** `Dict[str, Any]`

### `from_file`

Create a cluster config from the a Kubernetes config file.

By default, the current context in the default Kubernetes config file will be
used.

An alternative file or context may be specified.

The…

```python
prefect_kubernetes.KubernetesClusterConfig.from_file(path: Optional[pathlib._local.Path] = None, context_name: Optional[str] = None) -> Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Optional` | `None` | pos/kw |
| `context_name` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Self`

### `from_orm`

```python
prefect_kubernetes.KubernetesClusterConfig.from_orm(obj: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `Self`

### `get_api_client`

Returns a Kubernetes API client for this cluster config.

```python
prefect_kubernetes.KubernetesClusterConfig.get_api_client(self) -> 'ApiClient'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `ApiClient`

### `get_block_capabilities`

Returns the block capabilities for this Block. Recursively collects all block
capabilities of all parent classes into a single frozenset.

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_capabilities() -> 'FrozenSet[str]'
```

**Returns:** `FrozenSet[str]`

### `get_block_class_from_key`

Retrieve the block class implementation given a key.

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_class_from_key(key: 'str') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_class_from_schema`

Retrieve the block class implementation given a schema.

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_class_from_schema(schema: 'BlockSchema') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `BlockSchema` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_placeholder`

Returns the block placeholder for the current block which can be used for
templating.

Returns:
    str: The block placeholder for the current block in the format
        `prefect.blocks.{block_type_…

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_placeholder(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_block_schema_version`

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_schema_version() -> 'str'
```

**Returns:** `str`

### `get_block_type_name`

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_type_name() -> 'str'
```

**Returns:** `str`

### `get_block_type_slug`

```python
prefect_kubernetes.KubernetesClusterConfig.get_block_type_slug() -> 'str'
```

**Returns:** `str`

### `get_code_example`

Returns the code example for the given block. Attempts to parse
code example from the class docstring if an override is not provided.

```python
prefect_kubernetes.KubernetesClusterConfig.get_code_example() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_description`

Returns the description for the current block. Attempts to parse
description from class docstring if an override is not defined.

```python
prefect_kubernetes.KubernetesClusterConfig.get_description() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `is_block_class`

```python
prefect_kubernetes.KubernetesClusterConfig.is_block_class(block: 'Any') -> "TypeGuard[type['Block']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `block` | `Any` | `—` | pos/kw |

**Returns:** `TypeGuard[type['Block']]`

### `json`

```python
prefect_kubernetes.KubernetesClusterConfig.json(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, encoder: 'Callable[[Any], Any] | None' = PydanticUndefined, models_as_dict: 'bool' = PydanticUndefined, **dumps_kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `encoder` | `Callable[[Any], Any] \| None` | `PydanticUndefined` | kw |
| `models_as_dict` | `bool` | `PydanticUndefined` | kw |
| `dumps_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `load`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.KubernetesClusterConfig.load(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `load_from_ref`

Retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in t…

```python
prefect_kubernetes.KubernetesClusterConfig.load_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `model_construct`

Creates a new instance of the `Model` class with validated data.

Creates a new model setting `__dict__` and `__pydantic_fields_set__` from trusted or pre-validated data.
Default values are respected…

```python
prefect_kubernetes.KubernetesClusterConfig.model_construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `model_copy`

!!! abstract "Usage Documentation"
    [`model_copy`](../concepts/models.md#model-copy)

Returns a copy of the model.

!!! note
    The underlying instance's [`__dict__`][object.__dict__] attribute i…

```python
prefect_kubernetes.KubernetesClusterConfig.model_copy(self, *, update: 'Mapping[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `update` | `Mapping[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `prefect_kubernetes.KubernetesCredentials` methods

### `adelete`

Asynchronously deletes the block document with the specified name.

Args:
    name: The name of the block document to delete.
    client: The client to use to delete the block document. If not provid…

```python
prefect_kubernetes.KubernetesCredentials.adelete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `aload`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.KubernetesCredentials.aload(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `aload_from_ref`

Asynchronously retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the d…

```python
prefect_kubernetes.KubernetesCredentials.aload_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `annotation_refers_to_block_class`

```python
prefect_kubernetes.KubernetesCredentials.annotation_refers_to_block_class(annotation: 'Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotation` | `Any` | `—` | pos/kw |

**Returns:** `bool`

### `aregister_type_and_schema`

Asynchronously makes block available for configuration with current Prefect API.
Recursively registers all nested blocks. Registration is idempotent.

Args:
    client: Optional client to use for reg…

```python
prefect_kubernetes.KubernetesCredentials.aregister_type_and_schema(client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `asave`

Asynchronously saves the values of a block as a block document.

Args:
    name: User specified name to give saved block document which can later be used to load the
        block document.
    overw…

```python
prefect_kubernetes.KubernetesCredentials.asave(self, name: 'Optional[str]' = None, overwrite: 'bool' = False, client: "Optional['PrefectClient']" = None) -> 'UUID'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional[str]` | `None` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `UUID`

### `block_initialization`

```python
prefect_kubernetes.KubernetesCredentials.block_initialization(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `construct`

```python
prefect_kubernetes.KubernetesCredentials.construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `copy`

Returns a copy of the model.

!!! warning "Deprecated"
    This method is now deprecated; use `model_copy` instead.

If you need `include` or `exclude`, use:

```python {test="skip" lint="skip"}
data…

```python
prefect_kubernetes.KubernetesCredentials.copy(self, *, include: 'AbstractSetIntStr | MappingIntStrAny | None' = None, exclude: 'AbstractSetIntStr | MappingIntStrAny | None' = None, update: 'Dict[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `exclude` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `update` | `Dict[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `delete`

Deletes the block document with the specified name.

This function will dispatch to `adelete` when called from an async context.

Args:
    name: The name of the block document to delete.
    client:…

```python
prefect_kubernetes.KubernetesCredentials.delete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `dict`

```python
prefect_kubernetes.KubernetesCredentials.dict(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False) -> 'Dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |

**Returns:** `Dict[str, Any]`

### `from_orm`

```python
prefect_kubernetes.KubernetesCredentials.from_orm(obj: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `Self`

### `get_block_capabilities`

Returns the block capabilities for this Block. Recursively collects all block
capabilities of all parent classes into a single frozenset.

```python
prefect_kubernetes.KubernetesCredentials.get_block_capabilities() -> 'FrozenSet[str]'
```

**Returns:** `FrozenSet[str]`

### `get_block_class_from_key`

Retrieve the block class implementation given a key.

```python
prefect_kubernetes.KubernetesCredentials.get_block_class_from_key(key: 'str') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_class_from_schema`

Retrieve the block class implementation given a schema.

```python
prefect_kubernetes.KubernetesCredentials.get_block_class_from_schema(schema: 'BlockSchema') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `BlockSchema` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_placeholder`

Returns the block placeholder for the current block which can be used for
templating.

Returns:
    str: The block placeholder for the current block in the format
        `prefect.blocks.{block_type_…

```python
prefect_kubernetes.KubernetesCredentials.get_block_placeholder(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_block_schema_version`

```python
prefect_kubernetes.KubernetesCredentials.get_block_schema_version() -> 'str'
```

**Returns:** `str`

### `get_block_type_name`

```python
prefect_kubernetes.KubernetesCredentials.get_block_type_name() -> 'str'
```

**Returns:** `str`

### `get_block_type_slug`

```python
prefect_kubernetes.KubernetesCredentials.get_block_type_slug() -> 'str'
```

**Returns:** `str`

### `get_client`

Convenience method for retrieving a Kubernetes API client for deployment resources.

Args:
    client_type: The resource-specific type of Kubernetes client to retrieve.

Yields:
    An authenticated,…

```python
prefect_kubernetes.KubernetesCredentials.get_client(self, client_type: Literal['apps', 'batch', 'core', 'custom_objects'], configuration: Optional[kubernetes_asyncio.client.configuration.Configuration] = None) -> AsyncGenerator[Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api], NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `client_type` | `Literal` | `—` | pos/kw |
| `configuration` | `Optional` | `None` | pos/kw |

**Returns:** `typing.AsyncGenerator[typing.Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api], NoneType]`

### `get_code_example`

Returns the code example for the given block. Attempts to parse
code example from the class docstring if an override is not provided.

```python
prefect_kubernetes.KubernetesCredentials.get_code_example() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_description`

Returns the description for the current block. Attempts to parse
description from class docstring if an override is not defined.

```python
prefect_kubernetes.KubernetesCredentials.get_description() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_resource_specific_client`

Utility function for configuring a generic Kubernetes client.
It will attempt to connect to a Kubernetes cluster in three steps with
the first successful connection attempt becoming the mode of commu…

```python
prefect_kubernetes.KubernetesCredentials.get_resource_specific_client(self, client_type: str, api_client: kubernetes_asyncio.client.api_client.ApiClient) -> Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `client_type` | `str` | `—` | pos/kw |
| `api_client` | `ApiClient` | `—` | pos/kw |

**Returns:** `typing.Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api]`

### `is_block_class`

```python
prefect_kubernetes.KubernetesCredentials.is_block_class(block: 'Any') -> "TypeGuard[type['Block']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `block` | `Any` | `—` | pos/kw |

**Returns:** `TypeGuard[type['Block']]`

### `json`

```python
prefect_kubernetes.KubernetesCredentials.json(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, encoder: 'Callable[[Any], Any] | None' = PydanticUndefined, models_as_dict: 'bool' = PydanticUndefined, **dumps_kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `encoder` | `Callable[[Any], Any] \| None` | `PydanticUndefined` | kw |
| `models_as_dict` | `bool` | `PydanticUndefined` | kw |
| `dumps_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `load`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.KubernetesCredentials.load(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `load_from_ref`

Retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in t…

```python
prefect_kubernetes.KubernetesCredentials.load_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `model_construct`

Creates a new instance of the `Model` class with validated data.

Creates a new model setting `__dict__` and `__pydantic_fields_set__` from trusted or pre-validated data.
Default values are respected…

```python
prefect_kubernetes.KubernetesCredentials.model_construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `model_copy`

!!! abstract "Usage Documentation"
    [`model_copy`](../concepts/models.md#model-copy)

Returns a copy of the model.

!!! note
    The underlying instance's [`__dict__`][object.__dict__] attribute i…

```python
prefect_kubernetes.KubernetesCredentials.model_copy(self, *, update: 'Mapping[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `update` | `Mapping[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `model_dump`

!!! abstract "Usage Documentation"
    [`model_dump`](../concepts/serialization.md#python-mode)

Generate a dictionary representation of the model, optionally specifying which fields to include or ex…

```python
prefect_kubernetes.KubernetesCredentials.model_dump(self, *, mode: "Literal['json', 'python'] | str" = 'python', include: "'IncEx | None'" = None, exclude: "'IncEx | None'" = None, context: 'dict[str, Any] | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, round_trip: 'bool' = False, warnings: "bool | Literal['none', 'warn', 'error']" = True, serialize_as_any: 'bool' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `mode` | `Literal['json', 'python'] \| str` | `'python'` | kw |
| `include` | `'IncEx \| None'` | `None` | kw |
| `exclude` | `'IncEx \| None'` | `None` | kw |
| `context` | `dict[str, Any] \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `round_trip` | `bool` | `False` | kw |
| `warnings` | `bool \| Literal['none', 'warn', 'error']` | `True` | kw |
| `serialize_as_any` | `bool` | `False` | kw |

**Returns:** `dict[str, Any]`

### `prefect_kubernetes.KubernetesJob` methods

### `adelete`

Asynchronously deletes the block document with the specified name.

Args:
    name: The name of the block document to delete.
    client: The client to use to delete the block document. If not provid…

```python
prefect_kubernetes.KubernetesJob.adelete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `aload`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.KubernetesJob.aload(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `aload_from_ref`

Asynchronously retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the d…

```python
prefect_kubernetes.KubernetesJob.aload_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `annotation_refers_to_block_class`

```python
prefect_kubernetes.KubernetesJob.annotation_refers_to_block_class(annotation: 'Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotation` | `Any` | `—` | pos/kw |

**Returns:** `bool`

### `aregister_type_and_schema`

Asynchronously makes block available for configuration with current Prefect API.
Recursively registers all nested blocks. Registration is idempotent.

Args:
    client: Optional client to use for reg…

```python
prefect_kubernetes.KubernetesJob.aregister_type_and_schema(client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `asave`

Asynchronously saves the values of a block as a block document.

Args:
    name: User specified name to give saved block document which can later be used to load the
        block document.
    overw…

```python
prefect_kubernetes.KubernetesJob.asave(self, name: 'Optional[str]' = None, overwrite: 'bool' = False, client: "Optional['PrefectClient']" = None) -> 'UUID'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional[str]` | `None` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `UUID`

### `atrigger`

Async implementation: create a Kubernetes job and return a
`KubernetesJobRun` object.

```python
prefect_kubernetes.KubernetesJob.atrigger(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `block_initialization`

```python
prefect_kubernetes.KubernetesJob.block_initialization(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `construct`

```python
prefect_kubernetes.KubernetesJob.construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `copy`

Returns a copy of the model.

!!! warning "Deprecated"
    This method is now deprecated; use `model_copy` instead.

If you need `include` or `exclude`, use:

```python {test="skip" lint="skip"}
data…

```python
prefect_kubernetes.KubernetesJob.copy(self, *, include: 'AbstractSetIntStr | MappingIntStrAny | None' = None, exclude: 'AbstractSetIntStr | MappingIntStrAny | None' = None, update: 'Dict[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `exclude` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `update` | `Dict[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `delete`

Deletes the block document with the specified name.

This function will dispatch to `adelete` when called from an async context.

Args:
    name: The name of the block document to delete.
    client:…

```python
prefect_kubernetes.KubernetesJob.delete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `dict`

```python
prefect_kubernetes.KubernetesJob.dict(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False) -> 'Dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |

**Returns:** `Dict[str, Any]`

### `from_orm`

```python
prefect_kubernetes.KubernetesJob.from_orm(obj: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `Self`

### `from_yaml_file`

Create a `KubernetesJob` from a YAML file.

Args:
    manifest_path: The YAML file to create the `KubernetesJob` from.

Returns:
    A KubernetesJob object.

```python
prefect_kubernetes.KubernetesJob.from_yaml_file(manifest_path: Union[pathlib._local.Path, str], **kwargs) -> Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `manifest_path` | `Union` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

**Returns:** `typing.Self`

### `get_block_capabilities`

Returns the block capabilities for this Block. Recursively collects all block
capabilities of all parent classes into a single frozenset.

```python
prefect_kubernetes.KubernetesJob.get_block_capabilities() -> 'FrozenSet[str]'
```

**Returns:** `FrozenSet[str]`

### `get_block_class_from_key`

Retrieve the block class implementation given a key.

```python
prefect_kubernetes.KubernetesJob.get_block_class_from_key(key: 'str') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_class_from_schema`

Retrieve the block class implementation given a schema.

```python
prefect_kubernetes.KubernetesJob.get_block_class_from_schema(schema: 'BlockSchema') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `BlockSchema` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_placeholder`

Returns the block placeholder for the current block which can be used for
templating.

Returns:
    str: The block placeholder for the current block in the format
        `prefect.blocks.{block_type_…

```python
prefect_kubernetes.KubernetesJob.get_block_placeholder(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_block_schema_version`

```python
prefect_kubernetes.KubernetesJob.get_block_schema_version() -> 'str'
```

**Returns:** `str`

### `get_block_type_name`

```python
prefect_kubernetes.KubernetesJob.get_block_type_name() -> 'str'
```

**Returns:** `str`

### `get_block_type_slug`

```python
prefect_kubernetes.KubernetesJob.get_block_type_slug() -> 'str'
```

**Returns:** `str`

### `get_code_example`

Returns the code example for the given block. Attempts to parse
code example from the class docstring if an override is not provided.

```python
prefect_kubernetes.KubernetesJob.get_code_example() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_description`

Returns the description for the current block. Attempts to parse
description from class docstring if an override is not defined.

```python
prefect_kubernetes.KubernetesJob.get_description() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `is_block_class`

```python
prefect_kubernetes.KubernetesJob.is_block_class(block: 'Any') -> "TypeGuard[type['Block']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `block` | `Any` | `—` | pos/kw |

**Returns:** `TypeGuard[type['Block']]`

### `json`

```python
prefect_kubernetes.KubernetesJob.json(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, encoder: 'Callable[[Any], Any] | None' = PydanticUndefined, models_as_dict: 'bool' = PydanticUndefined, **dumps_kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `encoder` | `Callable[[Any], Any] \| None` | `PydanticUndefined` | kw |
| `models_as_dict` | `bool` | `PydanticUndefined` | kw |
| `dumps_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `load`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.KubernetesJob.load(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `load_from_ref`

Retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in t…

```python
prefect_kubernetes.KubernetesJob.load_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `model_construct`

Creates a new instance of the `Model` class with validated data.

Creates a new model setting `__dict__` and `__pydantic_fields_set__` from trusted or pre-validated data.
Default values are respected…

```python
prefect_kubernetes.KubernetesJob.model_construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `model_copy`

!!! abstract "Usage Documentation"
    [`model_copy`](../concepts/models.md#model-copy)

Returns a copy of the model.

!!! note
    The underlying instance's [`__dict__`][object.__dict__] attribute i…

```python
prefect_kubernetes.KubernetesJob.model_copy(self, *, update: 'Mapping[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `update` | `Mapping[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `model_dump`

!!! abstract "Usage Documentation"
    [`model_dump`](../concepts/serialization.md#python-mode)

Generate a dictionary representation of the model, optionally specifying which fields to include or ex…

```python
prefect_kubernetes.KubernetesJob.model_dump(self, *, mode: "Literal['json', 'python'] | str" = 'python', include: "'IncEx | None'" = None, exclude: "'IncEx | None'" = None, context: 'dict[str, Any] | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, round_trip: 'bool' = False, warnings: "bool | Literal['none', 'warn', 'error']" = True, serialize_as_any: 'bool' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `mode` | `Literal['json', 'python'] \| str` | `'python'` | kw |
| `include` | `'IncEx \| None'` | `None` | kw |
| `exclude` | `'IncEx \| None'` | `None` | kw |
| `context` | `dict[str, Any] \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `round_trip` | `bool` | `False` | kw |
| `warnings` | `bool \| Literal['none', 'warn', 'error']` | `True` | kw |
| `serialize_as_any` | `bool` | `False` | kw |

**Returns:** `dict[str, Any]`

### `prefect_kubernetes.KubernetesWorker` methods

### `get_all_available_worker_types`

Returns all worker types available in the local registry.

```python
prefect_kubernetes.KubernetesWorker.get_all_available_worker_types() -> 'list[str]'
```

**Returns:** `list[str]`

### `get_and_submit_flow_runs`

```python
prefect_kubernetes.KubernetesWorker.get_and_submit_flow_runs(self) -> "list['FlowRun']"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list['FlowRun']`

### `get_default_base_job_template`

```python
prefect_kubernetes.KubernetesWorker.get_default_base_job_template() -> 'dict[str, Any]'
```

**Returns:** `dict[str, Any]`

### `get_description`

```python
prefect_kubernetes.KubernetesWorker.get_description() -> 'str'
```

**Returns:** `str`

### `get_documentation_url`

```python
prefect_kubernetes.KubernetesWorker.get_documentation_url() -> 'str'
```

**Returns:** `str`

### `get_flow_run_logger`

```python
prefect_kubernetes.KubernetesWorker.get_flow_run_logger(self, flow_run: "'FlowRun'") -> 'PrefectLogAdapter'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `flow_run` | `'FlowRun'` | `—` | pos/kw |

**Returns:** `PrefectLogAdapter`

### `get_logo_url`

```python
prefect_kubernetes.KubernetesWorker.get_logo_url() -> 'str'
```

**Returns:** `str`

### `get_name_slug`

```python
prefect_kubernetes.KubernetesWorker.get_name_slug(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_status`

Retrieves the status of the current worker including its name, current worker
pool, the work pool queues it is polling, and its local settings.

```python
prefect_kubernetes.KubernetesWorker.get_status(self) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_worker_class_from_type`

Returns the worker class for a given worker type. If the worker type
is not recognized, returns None.

```python
prefect_kubernetes.KubernetesWorker.get_worker_class_from_type(type: 'str') -> "Optional[Type['BaseWorker[Any, Any, Any]']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `type` | `str` | `—` | pos/kw |

**Returns:** `Optional[Type['BaseWorker[Any, Any, Any]']]`

### `is_worker_still_polling`

This method is invoked by a webserver healthcheck handler
and returns a boolean indicating if the worker has recorded a
scheduled flow run poll within a variable amount of time.

The `query_interval_…

```python
prefect_kubernetes.KubernetesWorker.is_worker_still_polling(self, query_interval_seconds: 'float') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `query_interval_seconds` | `float` | `—` | pos/kw |

**Returns:** `bool`

### `kill_infrastructure`

Kill a Kubernetes job by deleting it.

Args:
    infrastructure_pid: The infrastructure identifier in format "namespace:job_name".
    configuration: The job configuration used to connect to the clus…

```python
prefect_kubernetes.KubernetesWorker.kill_infrastructure(self, infrastructure_pid: 'str', configuration: 'KubernetesWorkerJobConfiguration', grace_seconds: 'int' = 30) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `infrastructure_pid` | `str` | `—` | pos/kw |
| `configuration` | `KubernetesWorkerJobConfiguration` | `—` | pos/kw |
| `grace_seconds` | `int` | `30` | pos/kw |

### `run`

Executes a flow run within a Kubernetes Job and waits for the flow run
to complete.

Args:
    flow_run: The flow run to execute
    configuration: The configuration to use when executing the flow ru…

```python
prefect_kubernetes.KubernetesWorker.run(self, flow_run: "'FlowRun'", configuration: 'KubernetesWorkerJobConfiguration', task_status: 'anyio.abc.TaskStatus[int] | None' = None) -> 'KubernetesWorkerResult'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `flow_run` | `'FlowRun'` | `—` | pos/kw |
| `configuration` | `KubernetesWorkerJobConfiguration` | `—` | pos/kw |
| `task_status` | `anyio.abc.TaskStatus[int] \| None` | `None` | pos/kw |

**Returns:** `KubernetesWorkerResult`

### `setup`

Prepares the worker to run.

```python
prefect_kubernetes.KubernetesWorker.setup(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `start`

Starts the worker and runs the main worker loops.

By default, the worker will run loops to poll for scheduled/cancelled flow
runs and sync with the Prefect API server.

If `run_once` is set, the wor…

```python
prefect_kubernetes.KubernetesWorker.start(self, run_once: 'bool' = False, with_healthcheck: 'bool' = False, printer: 'Callable[..., None]' = <built-in function print>) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `run_once` | `bool` | `False` | pos/kw |
| `with_healthcheck` | `bool` | `False` | pos/kw |
| `printer` | `Callable[..., None]` | `<built-in function print>` | pos/kw |

### `submit`

EXPERIMENTAL: The interface for this method is subject to change.

Submits a flow to run via the worker.

Args:
    flow: The flow to submit
    parameters: The parameters to pass to the flow
    job…

```python
prefect_kubernetes.KubernetesWorker.submit(self, flow: "'Flow[..., FR]'", parameters: 'dict[str, Any] | None' = None, job_variables: 'dict[str, Any] | None' = None, flow_run: "'FlowRun | None'" = None) -> "'PrefectFlowRunFuture[FR]'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `flow` | `'Flow[..., FR]'` | `—` | pos/kw |
| `parameters` | `dict[str, Any] \| None` | `None` | pos/kw |
| `job_variables` | `dict[str, Any] \| None` | `None` | pos/kw |
| `flow_run` | `'FlowRun \| None'` | `None` | pos/kw |

**Returns:** `'PrefectFlowRunFuture[FR]'`

### `sync_with_backend`

Updates the worker's local information about it's current work pool and
queues. Sends a worker heartbeat to the API.

```python
prefect_kubernetes.KubernetesWorker.sync_with_backend(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `teardown`

Cleans up resources after the worker is stopped.

```python
prefect_kubernetes.KubernetesWorker.teardown(self, *exc_info: 'Any')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `exc_info` | `Any` | `—` | *args |

### `prefect_kubernetes.credentials.KubernetesClusterConfig` methods

### `adelete`

Asynchronously deletes the block document with the specified name.

Args:
    name: The name of the block document to delete.
    client: The client to use to delete the block document. If not provid…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.adelete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `aload`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.aload(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `aload_from_ref`

Asynchronously retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the d…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.aload_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `annotation_refers_to_block_class`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.annotation_refers_to_block_class(annotation: 'Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotation` | `Any` | `—` | pos/kw |

**Returns:** `bool`

### `aregister_type_and_schema`

Asynchronously makes block available for configuration with current Prefect API.
Recursively registers all nested blocks. Registration is idempotent.

Args:
    client: Optional client to use for reg…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.aregister_type_and_schema(client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `asave`

Asynchronously saves the values of a block as a block document.

Args:
    name: User specified name to give saved block document which can later be used to load the
        block document.
    overw…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.asave(self, name: 'Optional[str]' = None, overwrite: 'bool' = False, client: "Optional['PrefectClient']" = None) -> 'UUID'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional[str]` | `None` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `UUID`

### `block_initialization`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.block_initialization(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `configure_client`

Activates this cluster configuration by loading the configuration into the
Kubernetes Python client. After calling this, Kubernetes API clients can use
this config's context.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.configure_client(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `construct`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `copy`

Returns a copy of the model.

!!! warning "Deprecated"
    This method is now deprecated; use `model_copy` instead.

If you need `include` or `exclude`, use:

```python {test="skip" lint="skip"}
data…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.copy(self, *, include: 'AbstractSetIntStr | MappingIntStrAny | None' = None, exclude: 'AbstractSetIntStr | MappingIntStrAny | None' = None, update: 'Dict[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `exclude` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `update` | `Dict[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `delete`

Deletes the block document with the specified name.

This function will dispatch to `adelete` when called from an async context.

Args:
    name: The name of the block document to delete.
    client:…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.delete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `dict`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.dict(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False) -> 'Dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |

**Returns:** `Dict[str, Any]`

### `from_file`

Create a cluster config from the a Kubernetes config file.

By default, the current context in the default Kubernetes config file will be
used.

An alternative file or context may be specified.

The…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.from_file(path: Optional[pathlib._local.Path] = None, context_name: Optional[str] = None) -> Self
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Optional` | `None` | pos/kw |
| `context_name` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Self`

### `from_orm`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.from_orm(obj: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `Self`

### `get_api_client`

Returns a Kubernetes API client for this cluster config.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_api_client(self) -> 'ApiClient'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `ApiClient`

### `get_block_capabilities`

Returns the block capabilities for this Block. Recursively collects all block
capabilities of all parent classes into a single frozenset.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_capabilities() -> 'FrozenSet[str]'
```

**Returns:** `FrozenSet[str]`

### `get_block_class_from_key`

Retrieve the block class implementation given a key.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_class_from_key(key: 'str') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_class_from_schema`

Retrieve the block class implementation given a schema.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_class_from_schema(schema: 'BlockSchema') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `BlockSchema` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_placeholder`

Returns the block placeholder for the current block which can be used for
templating.

Returns:
    str: The block placeholder for the current block in the format
        `prefect.blocks.{block_type_…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_placeholder(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_block_schema_version`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_schema_version() -> 'str'
```

**Returns:** `str`

### `get_block_type_name`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_type_name() -> 'str'
```

**Returns:** `str`

### `get_block_type_slug`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_block_type_slug() -> 'str'
```

**Returns:** `str`

### `get_code_example`

Returns the code example for the given block. Attempts to parse
code example from the class docstring if an override is not provided.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_code_example() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_description`

Returns the description for the current block. Attempts to parse
description from class docstring if an override is not defined.

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.get_description() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `is_block_class`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.is_block_class(block: 'Any') -> "TypeGuard[type['Block']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `block` | `Any` | `—` | pos/kw |

**Returns:** `TypeGuard[type['Block']]`

### `json`

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.json(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, encoder: 'Callable[[Any], Any] | None' = PydanticUndefined, models_as_dict: 'bool' = PydanticUndefined, **dumps_kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `encoder` | `Callable[[Any], Any] \| None` | `PydanticUndefined` | kw |
| `models_as_dict` | `bool` | `PydanticUndefined` | kw |
| `dumps_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `load`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.load(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `load_from_ref`

Retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in t…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.load_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `model_construct`

Creates a new instance of the `Model` class with validated data.

Creates a new model setting `__dict__` and `__pydantic_fields_set__` from trusted or pre-validated data.
Default values are respected…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.model_construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `model_copy`

!!! abstract "Usage Documentation"
    [`model_copy`](../concepts/models.md#model-copy)

Returns a copy of the model.

!!! note
    The underlying instance's [`__dict__`][object.__dict__] attribute i…

```python
prefect_kubernetes.credentials.KubernetesClusterConfig.model_copy(self, *, update: 'Mapping[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `update` | `Mapping[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `prefect_kubernetes.credentials.KubernetesCredentials` methods

### `adelete`

Asynchronously deletes the block document with the specified name.

Args:
    name: The name of the block document to delete.
    client: The client to use to delete the block document. If not provid…

```python
prefect_kubernetes.credentials.KubernetesCredentials.adelete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `aload`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.credentials.KubernetesCredentials.aload(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `aload_from_ref`

Asynchronously retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the d…

```python
prefect_kubernetes.credentials.KubernetesCredentials.aload_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `annotation_refers_to_block_class`

```python
prefect_kubernetes.credentials.KubernetesCredentials.annotation_refers_to_block_class(annotation: 'Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotation` | `Any` | `—` | pos/kw |

**Returns:** `bool`

### `aregister_type_and_schema`

Asynchronously makes block available for configuration with current Prefect API.
Recursively registers all nested blocks. Registration is idempotent.

Args:
    client: Optional client to use for reg…

```python
prefect_kubernetes.credentials.KubernetesCredentials.aregister_type_and_schema(client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `asave`

Asynchronously saves the values of a block as a block document.

Args:
    name: User specified name to give saved block document which can later be used to load the
        block document.
    overw…

```python
prefect_kubernetes.credentials.KubernetesCredentials.asave(self, name: 'Optional[str]' = None, overwrite: 'bool' = False, client: "Optional['PrefectClient']" = None) -> 'UUID'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional[str]` | `None` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `UUID`

### `block_initialization`

```python
prefect_kubernetes.credentials.KubernetesCredentials.block_initialization(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `construct`

```python
prefect_kubernetes.credentials.KubernetesCredentials.construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `copy`

Returns a copy of the model.

!!! warning "Deprecated"
    This method is now deprecated; use `model_copy` instead.

If you need `include` or `exclude`, use:

```python {test="skip" lint="skip"}
data…

```python
prefect_kubernetes.credentials.KubernetesCredentials.copy(self, *, include: 'AbstractSetIntStr | MappingIntStrAny | None' = None, exclude: 'AbstractSetIntStr | MappingIntStrAny | None' = None, update: 'Dict[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `exclude` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `update` | `Dict[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `delete`

Deletes the block document with the specified name.

This function will dispatch to `adelete` when called from an async context.

Args:
    name: The name of the block document to delete.
    client:…

```python
prefect_kubernetes.credentials.KubernetesCredentials.delete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `dict`

```python
prefect_kubernetes.credentials.KubernetesCredentials.dict(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False) -> 'Dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |

**Returns:** `Dict[str, Any]`

### `from_orm`

```python
prefect_kubernetes.credentials.KubernetesCredentials.from_orm(obj: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `Self`

### `get_block_capabilities`

Returns the block capabilities for this Block. Recursively collects all block
capabilities of all parent classes into a single frozenset.

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_capabilities() -> 'FrozenSet[str]'
```

**Returns:** `FrozenSet[str]`

### `get_block_class_from_key`

Retrieve the block class implementation given a key.

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_class_from_key(key: 'str') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_class_from_schema`

Retrieve the block class implementation given a schema.

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_class_from_schema(schema: 'BlockSchema') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `BlockSchema` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_placeholder`

Returns the block placeholder for the current block which can be used for
templating.

Returns:
    str: The block placeholder for the current block in the format
        `prefect.blocks.{block_type_…

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_placeholder(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_block_schema_version`

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_schema_version() -> 'str'
```

**Returns:** `str`

### `get_block_type_name`

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_type_name() -> 'str'
```

**Returns:** `str`

### `get_block_type_slug`

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_block_type_slug() -> 'str'
```

**Returns:** `str`

### `get_client`

Convenience method for retrieving a Kubernetes API client for deployment resources.

Args:
    client_type: The resource-specific type of Kubernetes client to retrieve.

Yields:
    An authenticated,…

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_client(self, client_type: Literal['apps', 'batch', 'core', 'custom_objects'], configuration: Optional[kubernetes_asyncio.client.configuration.Configuration] = None) -> AsyncGenerator[Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api], NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `client_type` | `Literal` | `—` | pos/kw |
| `configuration` | `Optional` | `None` | pos/kw |

**Returns:** `typing.AsyncGenerator[typing.Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api], NoneType]`

### `get_code_example`

Returns the code example for the given block. Attempts to parse
code example from the class docstring if an override is not provided.

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_code_example() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_description`

Returns the description for the current block. Attempts to parse
description from class docstring if an override is not defined.

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_description() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_resource_specific_client`

Utility function for configuring a generic Kubernetes client.
It will attempt to connect to a Kubernetes cluster in three steps with
the first successful connection attempt becoming the mode of commu…

```python
prefect_kubernetes.credentials.KubernetesCredentials.get_resource_specific_client(self, client_type: str, api_client: kubernetes_asyncio.client.api_client.ApiClient) -> Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `client_type` | `str` | `—` | pos/kw |
| `api_client` | `ApiClient` | `—` | pos/kw |

**Returns:** `typing.Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api]`

### `is_block_class`

```python
prefect_kubernetes.credentials.KubernetesCredentials.is_block_class(block: 'Any') -> "TypeGuard[type['Block']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `block` | `Any` | `—` | pos/kw |

**Returns:** `TypeGuard[type['Block']]`

### `json`

```python
prefect_kubernetes.credentials.KubernetesCredentials.json(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, encoder: 'Callable[[Any], Any] | None' = PydanticUndefined, models_as_dict: 'bool' = PydanticUndefined, **dumps_kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `encoder` | `Callable[[Any], Any] \| None` | `PydanticUndefined` | kw |
| `models_as_dict` | `bool` | `PydanticUndefined` | kw |
| `dumps_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `load`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.credentials.KubernetesCredentials.load(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `load_from_ref`

Retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in t…

```python
prefect_kubernetes.credentials.KubernetesCredentials.load_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `model_construct`

Creates a new instance of the `Model` class with validated data.

Creates a new model setting `__dict__` and `__pydantic_fields_set__` from trusted or pre-validated data.
Default values are respected…

```python
prefect_kubernetes.credentials.KubernetesCredentials.model_construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `model_copy`

!!! abstract "Usage Documentation"
    [`model_copy`](../concepts/models.md#model-copy)

Returns a copy of the model.

!!! note
    The underlying instance's [`__dict__`][object.__dict__] attribute i…

```python
prefect_kubernetes.credentials.KubernetesCredentials.model_copy(self, *, update: 'Mapping[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `update` | `Mapping[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `model_dump`

!!! abstract "Usage Documentation"
    [`model_dump`](../concepts/serialization.md#python-mode)

Generate a dictionary representation of the model, optionally specifying which fields to include or ex…

```python
prefect_kubernetes.credentials.KubernetesCredentials.model_dump(self, *, mode: "Literal['json', 'python'] | str" = 'python', include: "'IncEx | None'" = None, exclude: "'IncEx | None'" = None, context: 'dict[str, Any] | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, round_trip: 'bool' = False, warnings: "bool | Literal['none', 'warn', 'error']" = True, serialize_as_any: 'bool' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `mode` | `Literal['json', 'python'] \| str` | `'python'` | kw |
| `include` | `'IncEx \| None'` | `None` | kw |
| `exclude` | `'IncEx \| None'` | `None` | kw |
| `context` | `dict[str, Any] \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `round_trip` | `bool` | `False` | kw |
| `warnings` | `bool \| Literal['none', 'warn', 'error']` | `True` | kw |
| `serialize_as_any` | `bool` | `False` | kw |

**Returns:** `dict[str, Any]`

### `prefect_kubernetes.custom_objects.KubernetesCredentials` methods

### `adelete`

Asynchronously deletes the block document with the specified name.

Args:
    name: The name of the block document to delete.
    client: The client to use to delete the block document. If not provid…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.adelete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `aload`

Retrieves data from the block document with the given name for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the data stored in…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.aload(name: 'str', validate: 'bool' = True, client: "Optional['PrefectClient']" = None) -> "'Self'"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `'Self'`

### `aload_from_ref`

Asynchronously retrieves data from the block document by given reference for the block type
that corresponds with the current class and returns an instantiated version of
the current class with the d…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.aload_from_ref(ref: 'Union[str, UUID, dict[str, Any]]', validate: 'bool' = True, client: "'PrefectClient | None'" = None) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ref` | `Union[str, UUID, dict[str, Any]]` | `—` | pos/kw |
| `validate` | `bool` | `True` | pos/kw |
| `client` | `'PrefectClient \| None'` | `None` | pos/kw |

**Returns:** `Self`

### `annotation_refers_to_block_class`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.annotation_refers_to_block_class(annotation: 'Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `annotation` | `Any` | `—` | pos/kw |

**Returns:** `bool`

### `aregister_type_and_schema`

Asynchronously makes block available for configuration with current Prefect API.
Recursively registers all nested blocks. Registration is idempotent.

Args:
    client: Optional client to use for reg…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.aregister_type_and_schema(client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `asave`

Asynchronously saves the values of a block as a block document.

Args:
    name: User specified name to give saved block document which can later be used to load the
        block document.
    overw…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.asave(self, name: 'Optional[str]' = None, overwrite: 'bool' = False, client: "Optional['PrefectClient']" = None) -> 'UUID'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Optional[str]` | `None` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

**Returns:** `UUID`

### `block_initialization`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.block_initialization(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `construct`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.construct(_fields_set: 'set[str] | None' = None, **values: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_fields_set` | `set[str] \| None` | `None` | pos/kw |
| `values` | `Any` | `—` | **kwargs |

**Returns:** `Self`

### `copy`

Returns a copy of the model.

!!! warning "Deprecated"
    This method is now deprecated; use `model_copy` instead.

If you need `include` or `exclude`, use:

```python {test="skip" lint="skip"}
data…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.copy(self, *, include: 'AbstractSetIntStr | MappingIntStrAny | None' = None, exclude: 'AbstractSetIntStr | MappingIntStrAny | None' = None, update: 'Dict[str, Any] | None' = None, deep: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `exclude` | `AbstractSetIntStr \| MappingIntStrAny \| None` | `None` | kw |
| `update` | `Dict[str, Any] \| None` | `None` | kw |
| `deep` | `bool` | `False` | kw |

**Returns:** `Self`

### `delete`

Deletes the block document with the specified name.

This function will dispatch to `adelete` when called from an async context.

Args:
    name: The name of the block document to delete.
    client:…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.delete(name: 'str', client: "Optional['PrefectClient']" = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `client` | `Optional['PrefectClient']` | `None` | pos/kw |

### `dict`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.dict(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False) -> 'Dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |

**Returns:** `Dict[str, Any]`

### `from_orm`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.from_orm(obj: 'Any') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `Any` | `—` | pos/kw |

**Returns:** `Self`

### `get_block_capabilities`

Returns the block capabilities for this Block. Recursively collects all block
capabilities of all parent classes into a single frozenset.

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_capabilities() -> 'FrozenSet[str]'
```

**Returns:** `FrozenSet[str]`

### `get_block_class_from_key`

Retrieve the block class implementation given a key.

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_class_from_key(key: 'str') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_class_from_schema`

Retrieve the block class implementation given a schema.

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_class_from_schema(schema: 'BlockSchema') -> 'type[Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `schema` | `BlockSchema` | `—` | pos/kw |

**Returns:** `type[Self]`

### `get_block_placeholder`

Returns the block placeholder for the current block which can be used for
templating.

Returns:
    str: The block placeholder for the current block in the format
        `prefect.blocks.{block_type_…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_placeholder(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_block_schema_version`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_schema_version() -> 'str'
```

**Returns:** `str`

### `get_block_type_name`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_type_name() -> 'str'
```

**Returns:** `str`

### `get_block_type_slug`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_block_type_slug() -> 'str'
```

**Returns:** `str`

### `get_client`

Convenience method for retrieving a Kubernetes API client for deployment resources.

Args:
    client_type: The resource-specific type of Kubernetes client to retrieve.

Yields:
    An authenticated,…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_client(self, client_type: Literal['apps', 'batch', 'core', 'custom_objects'], configuration: Optional[kubernetes_asyncio.client.configuration.Configuration] = None) -> AsyncGenerator[Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api], NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `client_type` | `Literal` | `—` | pos/kw |
| `configuration` | `Optional` | `None` | pos/kw |

**Returns:** `typing.AsyncGenerator[typing.Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api], NoneType]`

### `get_code_example`

Returns the code example for the given block. Attempts to parse
code example from the class docstring if an override is not provided.

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_code_example() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_description`

Returns the description for the current block. Attempts to parse
description from class docstring if an override is not defined.

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_description() -> 'Optional[str]'
```

**Returns:** `Optional[str]`

### `get_resource_specific_client`

Utility function for configuring a generic Kubernetes client.
It will attempt to connect to a Kubernetes cluster in three steps with
the first successful connection attempt becoming the mode of commu…

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.get_resource_specific_client(self, client_type: str, api_client: kubernetes_asyncio.client.api_client.ApiClient) -> Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `client_type` | `str` | `—` | pos/kw |
| `api_client` | `ApiClient` | `—` | pos/kw |

**Returns:** `typing.Union[kubernetes_asyncio.client.api.apps_v1_api.AppsV1Api, kubernetes_asyncio.client.api.batch_v1_api.BatchV1Api, kubernetes_asyncio.client.api.core_v1_api.CoreV1Api]`

### `is_block_class`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.is_block_class(block: 'Any') -> "TypeGuard[type['Block']]"
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `block` | `Any` | `—` | pos/kw |

**Returns:** `TypeGuard[type['Block']]`

### `json`

```python
prefect_kubernetes.custom_objects.KubernetesCredentials.json(self, *, include: 'IncEx | None' = None, exclude: 'IncEx | None' = None, by_alias: 'bool' = False, exclude_unset: 'bool' = False, exclude_defaults: 'bool' = False, exclude_none: 'bool' = False, encoder: 'Callable[[Any], Any] | None' = PydanticUndefined, models_as_dict: 'bool' = PydanticUndefined, **dumps_kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include` | `IncEx \| None` | `None` | kw |
| `exclude` | `IncEx \| None` | `None` | kw |
| `by_alias` | `bool` | `False` | kw |
| `exclude_unset` | `bool` | `False` | kw |
| `exclude_defaults` | `bool` | `False` | kw |
| `exclude_none` | `bool` | `False` | kw |
| `encoder` | `Callable[[Any], Any] \| None` | `PydanticUndefined` | kw |
| `models_as_dict` | `bool` | `PydanticUndefined` | kw |
| `dumps_kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`


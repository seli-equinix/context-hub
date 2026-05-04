---
name: source-context
description: "google-cloud-source-context message types for describing Git, Gerrit, Cloud Repo, and Cloud Workspace source revisions in Python"
metadata:
  languages: "python"
  versions: "1.9.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "google,python,google-cloud,source-context,gcp,protobuf,git,gerrit,SourceContext,GitSourceContext,GerritSourceContext,labels,Version-Sensitive,AliasContext,copy_from,deserialize,from_json,pb,serialize,to_dict,to_json,wrap,CloudRepoSourceContext,CloudWorkspaceId,CloudWorkspaceSourceContext,ExtendedSourceContext,ProjectRepoId,RepoId"
---

# google — source-context

## Install

```bash
pip install google
```

## Imports

```python
import google
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `AliasContext` | Class | An alias to a repo revision.  Attributes:     kind (google.cloud.source_context… |
| `copy_from` | Method | Equivalent for protobuf.Message.CopyFrom  Args:     instance: An instance of th… |
| `deserialize` | Method | Given a serialized proto, deserialize it into a Message instance.  Args:     pa… |
| `from_json` | Method | Given a json string representing an instance, parse it into a message.  Args:… |
| `pb` | Method | Return the underlying protobuf Message class or instance.  Args:     obj: If pr… |
| `serialize` | Method | Return the serialized proto.  Args:     instance: An instance of this message t… |
| `to_dict` | Method | Given a message instance, return its representation as a python dict.  Args:… |
| `to_json` | Method | Given a message instance, serialize it to json  Args:     instance: An instance… |
| `wrap` | Method | Return a Message object that shallowly wraps the descriptor.  Args:     pb: A p… |
| `CloudRepoSourceContext` | Class | A CloudRepoSourceContext denotes a particular revision in a cloud repo (a repo… |
| `copy_from` | Method | Equivalent for protobuf.Message.CopyFrom  Args:     instance: An instance of th… |
| `deserialize` | Method | Given a serialized proto, deserialize it into a Message instance.  Args:     pa… |
| `from_json` | Method | Given a json string representing an instance, parse it into a message.  Args:… |
| `pb` | Method | Return the underlying protobuf Message class or instance.  Args:     obj: If pr… |
| `serialize` | Method | Return the serialized proto.  Args:     instance: An instance of this message t… |
| `to_dict` | Method | Given a message instance, return its representation as a python dict.  Args:… |
| `to_json` | Method | Given a message instance, serialize it to json  Args:     instance: An instance… |
| `wrap` | Method | Return a Message object that shallowly wraps the descriptor.  Args:     pb: A p… |
| `CloudWorkspaceId` | Class | A CloudWorkspaceId is a unique identifier for a cloud workspace. A cloud worksp… |
| `copy_from` | Method | Equivalent for protobuf.Message.CopyFrom  Args:     instance: An instance of th… |
| `deserialize` | Method | Given a serialized proto, deserialize it into a Message instance.  Args:     pa… |
| `from_json` | Method | Given a json string representing an instance, parse it into a message.  Args:… |
| `pb` | Method | Return the underlying protobuf Message class or instance.  Args:     obj: If pr… |
| `serialize` | Method | Return the serialized proto.  Args:     instance: An instance of this message t… |
| `to_dict` | Method | Given a message instance, return its representation as a python dict.  Args:… |
| `to_json` | Method | Given a message instance, serialize it to json  Args:     instance: An instance… |
| `wrap` | Method | Return a Message object that shallowly wraps the descriptor.  Args:     pb: A p… |
| `CloudWorkspaceSourceContext` | Class | A CloudWorkspaceSourceContext denotes a workspace at a particular snapshot.  At… |
| `copy_from` | Method | Equivalent for protobuf.Message.CopyFrom  Args:     instance: An instance of th… |
| `deserialize` | Method | Given a serialized proto, deserialize it into a Message instance.  Args:     pa… |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `AliasContext`

An alias to a repo revision.

Attributes:
    kind (google.cloud.source_context_v1.types.AliasContext.Kind):
        The alias kind.
    name (str):
        The alias name.

```python
google.cloud.source_context_v1.AliasContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudRepoSourceContext`

A CloudRepoSourceContext denotes a particular revision in a
cloud repo (a repo hosted by the Google Cloud Platform).

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at…

```python
google.cloud.source_context_v1.CloudRepoSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudWorkspaceId`

A CloudWorkspaceId is a unique identifier for a cloud
workspace. A cloud workspace is a place associated with a repo
where modified files can be stored before they are committed.

Attributes:
    rep…

```python
google.cloud.source_context_v1.CloudWorkspaceId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudWorkspaceSourceContext`

A CloudWorkspaceSourceContext denotes a workspace at a
particular snapshot.

Attributes:
    workspace_id (google.cloud.source_context_v1.types.CloudWorkspaceId):
        The ID of the workspace.…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ExtendedSourceContext`

An ExtendedSourceContext is a SourceContext combined with
additional details describing the context.

Attributes:
    context (google.cloud.source_context_v1.types.SourceContext):
        Any source…

```python
google.cloud.source_context_v1.ExtendedSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `GerritSourceContext`

A SourceContext referring to a Gerrit project.

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at most one member field can be set at the same time.
Setting any member…

```python
google.cloud.source_context_v1.GerritSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `GitSourceContext`

A GitSourceContext denotes a particular revision in a third
party Git repository (e.g. GitHub).

Attributes:
    url (str):
        Git repository URL.
    revision_id (str):
        Git commit hash.…

```python
google.cloud.source_context_v1.GitSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ProjectRepoId`

Selects a repo using a Google Cloud Platform project ID
(e.g. winged-cargo-31) and a repo name within that project.

Attributes:
    project_id (str):
        The ID of the project.
    repo_name (st…

```python
google.cloud.source_context_v1.ProjectRepoId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `RepoId`

A unique identifier for a cloud repo.

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at most one member field can be set at the same time.
Setting any member of the on…

```python
google.cloud.source_context_v1.RepoId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `SourceContext`

A SourceContext is a reference to a tree of files. A
SourceContext together with a path point to a unique revision of
a single file or directory.

This message has `oneof`_ fields (mutually exclusive…

```python
google.cloud.source_context_v1.SourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `AliasContext`

An alias to a repo revision.

Attributes:
    kind (google.cloud.source_context_v1.types.AliasContext.Kind):
        The alias kind.
    name (str):
        The alias name.

```python
google.cloud.source_context_v1.types.AliasContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudRepoSourceContext`

A CloudRepoSourceContext denotes a particular revision in a
cloud repo (a repo hosted by the Google Cloud Platform).

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudWorkspaceId`

A CloudWorkspaceId is a unique identifier for a cloud
workspace. A cloud workspace is a place associated with a repo
where modified files can be stored before they are committed.

Attributes:
    rep…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudWorkspaceSourceContext`

A CloudWorkspaceSourceContext denotes a workspace at a
particular snapshot.

Attributes:
    workspace_id (google.cloud.source_context_v1.types.CloudWorkspaceId):
        The ID of the workspace.…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ExtendedSourceContext`

An ExtendedSourceContext is a SourceContext combined with
additional details describing the context.

Attributes:
    context (google.cloud.source_context_v1.types.SourceContext):
        Any source…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `GerritSourceContext`

A SourceContext referring to a Gerrit project.

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at most one member field can be set at the same time.
Setting any member…

```python
google.cloud.source_context_v1.types.GerritSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `GitSourceContext`

A GitSourceContext denotes a particular revision in a third
party Git repository (e.g. GitHub).

Attributes:
    url (str):
        Git repository URL.
    revision_id (str):
        Git commit hash.…

```python
google.cloud.source_context_v1.types.GitSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `ProjectRepoId`

Selects a repo using a Google Cloud Platform project ID
(e.g. winged-cargo-31) and a repo name within that project.

Attributes:
    project_id (str):
        The ID of the project.
    repo_name (st…

```python
google.cloud.source_context_v1.types.ProjectRepoId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `RepoId`

A unique identifier for a cloud repo.

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at most one member field can be set at the same time.
Setting any member of the on…

```python
google.cloud.source_context_v1.types.RepoId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `SourceContext`

A SourceContext is a reference to a tree of files. A
SourceContext together with a path point to a unique revision of
a single file or directory.

This message has `oneof`_ fields (mutually exclusive…

```python
google.cloud.source_context_v1.types.SourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `AliasContext`

An alias to a repo revision.

Attributes:
    kind (google.cloud.source_context_v1.types.AliasContext.Kind):
        The alias kind.
    name (str):
        The alias name.

```python
google.cloud.source_context_v1.types.source_context.AliasContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudRepoSourceContext`

A CloudRepoSourceContext denotes a particular revision in a
cloud repo (a repo hosted by the Google Cloud Platform).

This message has `oneof`_ fields (mutually exclusive fields).
For each oneof, at…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

### `CloudWorkspaceId`

A CloudWorkspaceId is a unique identifier for a cloud
workspace. A cloud workspace is a place associated with a repo
where modified files can be stored before they are committed.

Attributes:
    rep…

```python
google.cloud.source_context_v1.types.source_context.CloudWorkspaceId(self, mapping=None, *, ignore_unknown_fields=False, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mapping` | `—` | `None` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |
| `kwargs` | `—` | `—` | **kwargs |

## Methods

### `google.cloud.source_context_v1.AliasContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.AliasContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.AliasContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.AliasContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.AliasContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.AliasContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.AliasContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.AliasContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.AliasContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.CloudRepoSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.CloudRepoSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.CloudRepoSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.CloudWorkspaceId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.CloudWorkspaceId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.CloudWorkspaceId.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.CloudWorkspaceId.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.CloudWorkspaceId.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.CloudWorkspaceId.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.CloudWorkspaceId.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.CloudWorkspaceId.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.CloudWorkspaceId.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.CloudWorkspaceSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.CloudWorkspaceSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.ExtendedSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.ExtendedSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.ExtendedSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.ExtendedSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.ExtendedSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.ExtendedSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.ExtendedSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.ExtendedSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.ExtendedSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.GerritSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.GerritSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.GerritSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.GerritSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.GerritSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.GerritSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.GerritSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.GerritSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.GerritSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.GitSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.GitSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.GitSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.GitSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.GitSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.GitSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.GitSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.GitSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.GitSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.ProjectRepoId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.ProjectRepoId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.ProjectRepoId.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.ProjectRepoId.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.ProjectRepoId.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.ProjectRepoId.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.ProjectRepoId.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.ProjectRepoId.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.ProjectRepoId.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.RepoId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.RepoId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.RepoId.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.RepoId.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.RepoId.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.RepoId.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.RepoId.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.RepoId.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.RepoId.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.SourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.SourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.SourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.SourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.SourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.SourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.SourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.SourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.SourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.AliasContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.AliasContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.AliasContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.AliasContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.AliasContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.AliasContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.AliasContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.AliasContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.AliasContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.CloudRepoSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.CloudRepoSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.CloudWorkspaceId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.CloudWorkspaceId.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.CloudWorkspaceSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.CloudWorkspaceSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.ExtendedSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.ExtendedSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.GerritSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.GerritSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.GerritSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.GerritSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.GerritSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.GerritSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.GerritSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.GerritSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.GerritSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.GitSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.GitSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.GitSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.GitSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.GitSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.GitSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.GitSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.GitSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.GitSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.ProjectRepoId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.ProjectRepoId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.ProjectRepoId.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.ProjectRepoId.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.ProjectRepoId.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.ProjectRepoId.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.ProjectRepoId.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.ProjectRepoId.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.ProjectRepoId.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.RepoId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.RepoId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.RepoId.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.RepoId.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.RepoId.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.RepoId.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.RepoId.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.RepoId.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.RepoId.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.SourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.SourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.SourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.SourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.SourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.SourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.SourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.SourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.SourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.source_context.AliasContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.source_context.AliasContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.source_context.AliasContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `deserialize`

Given a serialized proto, deserialize it into a Message instance.

Args:
    payload (bytes): The serialized proto.

Returns:
    ~.Message: An instance of the message class against which this
    me…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.deserialize(payload: bytes) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `bytes` | `—` | pos/kw |

**Returns:** `Message`

### `from_json`

Given a json string representing an instance,
parse it into a message.

Args:
    payload: A json string representing a message.
    ignore_unknown_fields (Optional(bool)): If True, do not raise erro…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.from_json(payload, *, ignore_unknown_fields=False) -> 'Message'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `payload` | `—` | `—` | pos/kw |
| `ignore_unknown_fields` | `—` | `False` | kw |

**Returns:** `Message`

### `pb`

Return the underlying protobuf Message class or instance.

Args:
    obj: If provided, and an instance of ``cls``, return the
        underlying protobuf instance.
    coerce (bool): If provided, wil…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.pb(obj=None, *, coerce: bool = False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `None` | pos/kw |
| `coerce` | `bool` | `False` | kw |

### `serialize`

Return the serialized proto.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).

Returns:
    bytes: The serialized represent…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.serialize(instance) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `to_dict`

Given a message instance, return its representation as a python dict.

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.to_dict(instance, *, use_integers_for_enums=True, preserving_proto_field_name=True, including_default_value_fields=None, float_precision=None, always_print_fields_with_no_presence=None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `preserving_proto_field_name` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `to_json`

Given a message instance, serialize it to json

Args:
    instance: An instance of this message type, or something
        compatible (accepted by the type's constructor).
    use_integers_for_enums…

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.to_json(instance, *, use_integers_for_enums=True, including_default_value_fields=None, preserving_proto_field_name=False, sort_keys=False, indent=2, float_precision=None, always_print_fields_with_no_presence=None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `use_integers_for_enums` | `—` | `True` | kw |
| `including_default_value_fields` | `—` | `None` | kw |
| `preserving_proto_field_name` | `—` | `False` | kw |
| `sort_keys` | `—` | `False` | kw |
| `indent` | `—` | `2` | kw |
| `float_precision` | `—` | `None` | kw |
| `always_print_fields_with_no_presence` | `—` | `None` | kw |

**Returns:** `<class 'str'>`

### `wrap`

Return a Message object that shallowly wraps the descriptor.

Args:
    pb: A protocol buffer object, such as would be returned by
        :meth:`pb`.

```python
google.cloud.source_context_v1.types.source_context.CloudRepoSourceContext.wrap(pb)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pb` | `—` | `—` | pos/kw |

### `google.cloud.source_context_v1.types.source_context.CloudWorkspaceId` methods

### `copy_from`

Equivalent for protobuf.Message.CopyFrom

Args:
    instance: An instance of this message type
    other: (Union[dict, ~.Message):
        A dictionary or message to reinitialize the values for this…

```python
google.cloud.source_context_v1.types.source_context.CloudWorkspaceId.copy_from(instance, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `instance` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |


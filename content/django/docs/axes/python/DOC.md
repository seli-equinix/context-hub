---
name: axes
description: "django-axes login lockout and failed-auth tracking for Django projects"
metadata:
  languages: "python"
  versions: "8.3.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "django,python,axes,authentication,security,login,lockout,AppConfig,create,initialize,ready,AxesBackendPermissionDenied,AxesBackendRequestParameterRequired,Migration,apply,unapply,deduplicate_attempts"
---

# django — axes

## Install

```bash
pip install django
```

## Imports

```python
import django
```

## Symbols (60)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `AppConfig` | Class | Class representing a Django application and its configuration. |
| `create` | Method | Factory that creates an app config from an entry in INSTALLED_APPS. |
| `get_model` | Method | Return the model with the given case-insensitive model_name.  Raise LookupError… |
| `get_models` | Method | Return an iterable of models.  By default, the following models aren't included… |
| `import_models` | Method |  |
| `initialize` | Method | Initialize Axes logging and show version information.  This method is re-entran… |
| `ready` | Method | Override this method in subclasses to run code when Django starts. |
| `AxesBackendPermissionDenied` | Class | Raised by authentication backend on locked out requests to stop the Django auth… |
| `AxesBackendRequestParameterRequired` | Class | Raised by authentication backend on invalid or missing request parameter value. |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `deduplicate_attempts` | Function |  |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `Migration` | Class | The base class for all migrations.  Migration files will import this from djang… |
| `apply` | Method | Take a project_state representing all migrations prior to this one and a schema… |
| `mutate_state` | Method | Take a ProjectState and return a new one with the migration's operations applie… |
| `suggest_name` | Method | Suggest a name for the operations this migration might represent. Names are not… |
| `unapply` | Method | Take a project_state representing all migrations prior to this one and a schema… |

## Classes

### `AppConfig`

Class representing a Django application and its configuration.

```python
axes.apps.AppConfig(self, app_name, app_module)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `app_name` | `—` | `—` | pos/kw |
| `app_module` | `—` | `—` | pos/kw |

### `AxesBackendPermissionDenied`

Raised by authentication backend on locked out requests to stop the Django authentication flow.

```python
axes.exceptions.AxesBackendPermissionDenied(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `AxesBackendRequestParameterRequired`

Raised by authentication backend on invalid or missing request parameter value.

```python
axes.exceptions.AxesBackendRequestParameterRequired(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0001_initial.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0002_auto_20151217_2044.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0003_auto_20160322_0929.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0004_auto_20181024_1538.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0005_remove_accessattempt_trusted.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0006_remove_accesslog_trusted.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0007_alter_accessattempt_unique_together.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0008_accessfailurelog.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0009_add_session_hash.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

### `Migration`

The base class for all migrations.

Migration files will import this from django.db.migrations.Migration
and subclass it as a class called Migration. It will have one or more
of the following attribu…

```python
axes.migrations.0010_accessattemptexpiration.Migration(self, name, app_label)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `app_label` | `—` | `—` | pos/kw |

## Functions

### `deduplicate_attempts`

```python
axes.migrations.0007_alter_accessattempt_unique_together.deduplicate_attempts(apps, schema_editor)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `apps` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |

## Methods

### `axes.apps.AppConfig` methods

### `create`

Factory that creates an app config from an entry in INSTALLED_APPS.

```python
axes.apps.AppConfig.create(entry)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `entry` | `—` | `—` | pos/kw |

### `get_model`

Return the model with the given case-insensitive model_name.

Raise LookupError if no model exists with this name.

```python
axes.apps.AppConfig.get_model(self, model_name, require_ready=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `model_name` | `—` | `—` | pos/kw |
| `require_ready` | `—` | `True` | pos/kw |

### `get_models`

Return an iterable of models.

By default, the following models aren't included:

- auto-created models for many-to-many relations without
  an explicit intermediate table,
- models that have been sw…

```python
axes.apps.AppConfig.get_models(self, include_auto_created=False, include_swapped=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include_auto_created` | `—` | `False` | pos/kw |
| `include_swapped` | `—` | `False` | pos/kw |

### `import_models`

```python
axes.apps.AppConfig.import_models(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `initialize`

Initialize Axes logging and show version information.

This method is re-entrant and can be called multiple times.
It displays version information exactly once at application startup.

```python
axes.apps.AppConfig.initialize()
```

### `ready`

Override this method in subclasses to run code when Django starts.

```python
axes.apps.AppConfig.ready(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `axes.migrations.0001_initial.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0001_initial.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0001_initial.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0001_initial.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0001_initial.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0002_auto_20151217_2044.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0002_auto_20151217_2044.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0002_auto_20151217_2044.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0002_auto_20151217_2044.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0002_auto_20151217_2044.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0003_auto_20160322_0929.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0003_auto_20160322_0929.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0003_auto_20160322_0929.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0003_auto_20160322_0929.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0003_auto_20160322_0929.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0004_auto_20181024_1538.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0004_auto_20181024_1538.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0004_auto_20181024_1538.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0004_auto_20181024_1538.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0004_auto_20181024_1538.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0005_remove_accessattempt_trusted.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0005_remove_accessattempt_trusted.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0005_remove_accessattempt_trusted.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0005_remove_accessattempt_trusted.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0005_remove_accessattempt_trusted.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0006_remove_accesslog_trusted.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0006_remove_accesslog_trusted.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0006_remove_accesslog_trusted.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0006_remove_accesslog_trusted.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0006_remove_accesslog_trusted.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0007_alter_accessattempt_unique_together.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0007_alter_accessattempt_unique_together.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0007_alter_accessattempt_unique_together.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0007_alter_accessattempt_unique_together.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0007_alter_accessattempt_unique_together.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0008_accessfailurelog.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0008_accessfailurelog.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0008_accessfailurelog.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0008_accessfailurelog.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0008_accessfailurelog.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0009_add_session_hash.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0009_add_session_hash.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0009_add_session_hash.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0009_add_session_hash.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0009_add_session_hash.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `axes.migrations.0010_accessattemptexpiration.Migration` methods

### `apply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a forwards order.

Return the resulting project state for efficie…

```python
axes.migrations.0010_accessattemptexpiration.Migration.apply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

### `mutate_state`

Take a ProjectState and return a new one with the migration's
operations applied to it. Preserve the original object state by
default and return a mutated state from a copy.

```python
axes.migrations.0010_accessattemptexpiration.Migration.mutate_state(self, project_state, preserve=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `preserve` | `—` | `True` | pos/kw |

### `suggest_name`

Suggest a name for the operations this migration might represent. Names
are not guaranteed to be unique, but put some effort into the fallback
name to avoid VCS conflicts if possible.

```python
axes.migrations.0010_accessattemptexpiration.Migration.suggest_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unapply`

Take a project_state representing all migrations prior to this one
and a schema_editor for a live database and apply the migration
in a reverse order.

The backwards migration process consists of two…

```python
axes.migrations.0010_accessattemptexpiration.Migration.unapply(self, project_state, schema_editor, collect_sql=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `project_state` | `—` | `—` | pos/kw |
| `schema_editor` | `—` | `—` | pos/kw |
| `collect_sql` | `—` | `False` | pos/kw |

## API surface — verifiable top-level exports of `django-axes`

Each name below is a real top-level export of `axes`, verified via `dir(__import__('axes'))` against `django-axes` installed from PyPI.

```python
import axes

# Public classes
class AppConfig: pass
class AxesBackendPermissionDenied: pass
class AxesBackendRequestParameterRequired: pass
class Migration: pass

# Public functions
def deduplicate_attempts(): pass
```

```python
# Verified call shapes — every name resolves in axes.dir()
axes.deduplicate_attempts()
```

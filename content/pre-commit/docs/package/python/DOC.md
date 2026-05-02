---
name: package
description: "pre-commit package guide for managing and running multi-language Git hooks in Python projects"
metadata:
  languages: "python"
  versions: "4.5.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pre-commit,python,git,hooks,linting,formatting,ci,Version-Sensitive,Language,get_default_version,health_check,in_env,install_environment,run_hook,DeprecatedDefaultStagesWarning,apply_default,check,remove_default,DeprecatedStagesWarning,FatalError,InvalidConfigError,InvalidManifestError,LanguageMigration,LanguageMigrationRequired,NotAllowed,OptionalSensibleRegexAtHook,OptionalSensibleRegexAtTop,StagesMigration,StagesMigrationNoDefault,WarnMutableRev,check_min_version,check_type_tag,parse_version,transform_stage,warn_for_stages_on_repo_init,warn_unknown_keys_repo,warn_unknown_keys_root,add_color_option,format_color,use_color,CalledProcessError,RepositoryCannotBeUpdatedError,RevInfo,from_config,update,autoupdate,cmd_output,cmd_output_b,migrate_config,yaml_dump,Store,clone,connect,db_repo_name,exclusive_lock,get_default_directory,make_local,mark_config_used,clean,rmtree,gc,add_parsers,cd,ignore_exit_code,impl,main,n1,normalize_cmd,envcontext,hook_impl,run,init_templatedir,install,all_hooks,install_hook_envs,install_hooks,is_our_script,make_executable,resource_text,uninstall,MappingKey,match,MappingValue,SequenceItem,Classifier,by_types,filenames_for_hook,Hook,create,filter_by_include_exclude,staged_files_only,sample_config,try_repo,xargs,validate_config,validate_manifest,Var,format_env,error_handler,force_bytes"
---

# pre-commit — package

## Install

```bash
pip install pre-commit
```

## Imports

```python
import pre_commit
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Language` | Class | Base class for protocol classes.  Protocol classes are defined as::      class… |
| `get_default_version` | Method |  |
| `health_check` | Method |  |
| `in_env` | Method |  |
| `install_environment` | Method |  |
| `run_hook` | Method |  |
| `DeprecatedDefaultStagesWarning` | Class | DeprecatedDefaultStagesWarning(key,) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `DeprecatedStagesWarning` | Class | DeprecatedStagesWarning(key,) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `FatalError` | Class | Unspecified run-time error. |
| `InvalidConfigError` | Class | Unspecified run-time error. |
| `InvalidManifestError` | Class | Unspecified run-time error. |
| `LanguageMigration` | Class | LanguageMigration(key, check_fn) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `LanguageMigrationRequired` | Class | LanguageMigration(key, check_fn) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `NotAllowed` | Class | OptionalNoDefault(key, check_fn) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `OptionalSensibleRegexAtHook` | Class | OptionalNoDefault(key, check_fn) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `OptionalSensibleRegexAtTop` | Class | OptionalNoDefault(key, check_fn) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `StagesMigration` | Class | StagesMigrationNoDefault(key, default) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `StagesMigrationNoDefault` | Class | StagesMigrationNoDefault(key, default) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `WarnMutableRev` | Class | Conditional(key, check_fn, condition_key, condition_value, ensure_absent) |
| `apply_default` | Method |  |
| `check` | Method |  |
| `remove_default` | Method |  |
| `check_min_version` | Function |  |
| `check_type_tag` | Function |  |
| `parse_version` | Function | poor man's version comparison |
| `transform_stage` | Function |  |
| `warn_for_stages_on_repo_init` | Function |  |
| `warn_unknown_keys_repo` | Function |  |
| `warn_unknown_keys_root` | Function |  |
| `add_color_option` | Function |  |
| `format_color` | Function | Format text with color.  Args:     text - Text to be formatted with color if `u… |
| `use_color` | Function | Choose whether to use color based on the command argument.  Args:     setting -… |
| `CalledProcessError` | Class | Unspecified run-time error. |
| `InvalidManifestError` | Class | Unspecified run-time error. |
| `RepositoryCannotBeUpdatedError` | Class | Unspecified run-time error. |
| `RevInfo` | Class | RevInfo(repo, rev, frozen, hook_ids) |
| `from_config` | Method |  |
| `update` | Method |  |
| `autoupdate` | Function | Auto-update the pre-commit config to the latest versions of repos. |
| `cmd_output` | Function |  |
| `cmd_output_b` | Function |  |
| `migrate_config` | Function |  |
| `yaml_dump` | Function |  |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `clean` | Function |  |
| `rmtree` | Function | On windows, rmtree fails for readonly dirs. |
| `InvalidConfigError` | Class | Unspecified run-time error. |
| `InvalidManifestError` | Class | Unspecified run-time error. |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `gc` | Function |  |
| `rmtree` | Function | On windows, rmtree fails for readonly dirs. |
| `add_parsers` | Function |  |
| `cd` | Function |  |
| `ignore_exit_code` | Function |  |
| `impl` | Function |  |
| `main` | Function |  |
| `n1` | Function |  |
| `normalize_cmd` | Function | Fixes for the following issues on windows - https://bugs.python.org/issue8557 -… |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `envcontext` | Function | In this context, `os.environ` is modified according to `patch`.  `patch` is an… |
| `hook_impl` | Function |  |
| `normalize_cmd` | Function | Fixes for the following issues on windows - https://bugs.python.org/issue8557 -… |
| `run` | Function |  |
| `CalledProcessError` | Class | Unspecified run-time error. |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `cmd_output` | Function |  |
| `init_templatedir` | Function |  |
| `install` | Function |  |
| `InvalidConfigError` | Class | Unspecified run-time error. |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `all_hooks` | Function |  |
| `install` | Function |  |
| `install_hook_envs` | Function |  |
| `install_hooks` | Function |  |
| `is_our_script` | Function |  |
| `make_executable` | Function |  |
| `resource_text` | Function |  |
| `uninstall` | Function |  |
| `InvalidConfigError` | Class | Unspecified run-time error. |
| `MappingKey` | Class | MappingKey(k,) |
| `match` | Method |  |
| `MappingValue` | Class | MappingValue(k,) |
| `match` | Method |  |
| `SequenceItem` | Class | SequenceItem() |
| `match` | Method |  |
| `match` | Function |  |
| `migrate_config` | Function |  |
| `Classifier` | Class |  |
| `by_types` | Method |  |
| `filenames_for_hook` | Method |  |
| `from_config` | Method |  |
| `Hook` | Class | Hook(src, prefix, id, name, entry, language, alias, files, exclude, types, type… |
| `create` | Method |  |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `all_hooks` | Function |  |
| `cmd_output_b` | Function |  |
| `filter_by_include_exclude` | Function |  |
| `install_hook_envs` | Function |  |
| `run` | Function |  |
| `staged_files_only` | Function | Clear any unstaged changes from the git working directory inside this context. |
| `sample_config` | Function |  |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `cmd_output_b` | Function |  |
| `run` | Function |  |
| `try_repo` | Function |  |
| `xargs` | Function | A simplified implementation of xargs.  color: Make a pty if on a platform that… |
| `yaml_dump` | Function |  |
| `validate_config` | Function |  |
| `validate_manifest` | Function |  |
| `Var` | Class | Var(name, default) |
| `envcontext` | Function | In this context, `os.environ` is modified according to `patch`.  `patch` is an… |
| `format_env` | Function |  |
| `FatalError` | Class | Unspecified run-time error. |
| `Store` | Class |  |
| `clone` | Method | Clone the given url and checkout the specific ref. |
| `connect` | Method |  |
| `db_repo_name` | Method |  |
| `exclusive_lock` | Method |  |
| `get_default_directory` | Method | Returns the default directory for the Store.  This is intentionally underscored… |
| `make_local` | Method |  |
| `mark_config_used` | Method |  |
| `cmd_output_b` | Function |  |
| `error_handler` | Function |  |
| `force_bytes` | Function |  |

## Classes

### `Language`

Base class for protocol classes.

Protocol classes are defined as::

    class Proto(Protocol):
        def meth(self) -> int:
            ...

Such classes are primarily used with static type checke…

```python
pre_commit.all_languages.Language(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DeprecatedDefaultStagesWarning`

DeprecatedDefaultStagesWarning(key,)

```python
pre_commit.clientlib.DeprecatedDefaultStagesWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DeprecatedStagesWarning`

DeprecatedStagesWarning(key,)

```python
pre_commit.clientlib.DeprecatedStagesWarning(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FatalError`

Unspecified run-time error.

```python
pre_commit.clientlib.FatalError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidConfigError`

Unspecified run-time error.

```python
pre_commit.clientlib.InvalidConfigError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidManifestError`

Unspecified run-time error.

```python
pre_commit.clientlib.InvalidManifestError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LanguageMigration`

LanguageMigration(key, check_fn)

```python
pre_commit.clientlib.LanguageMigration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `LanguageMigrationRequired`

LanguageMigration(key, check_fn)

```python
pre_commit.clientlib.LanguageMigrationRequired(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NotAllowed`

OptionalNoDefault(key, check_fn)

```python
pre_commit.clientlib.NotAllowed(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OptionalSensibleRegexAtHook`

OptionalNoDefault(key, check_fn)

```python
pre_commit.clientlib.OptionalSensibleRegexAtHook(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OptionalSensibleRegexAtTop`

OptionalNoDefault(key, check_fn)

```python
pre_commit.clientlib.OptionalSensibleRegexAtTop(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StagesMigration`

StagesMigrationNoDefault(key, default)

```python
pre_commit.clientlib.StagesMigration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StagesMigrationNoDefault`

StagesMigrationNoDefault(key, default)

```python
pre_commit.clientlib.StagesMigrationNoDefault(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `WarnMutableRev`

Conditional(key, check_fn, condition_key, condition_value, ensure_absent)

```python
pre_commit.clientlib.WarnMutableRev(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CalledProcessError`

Unspecified run-time error.

```python
pre_commit.commands.autoupdate.CalledProcessError(self, returncode: 'int', cmd: 'tuple[str, ...]', stdout: 'bytes', stderr: 'bytes | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `returncode` | `int` | `—` | pos/kw |
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |
| `stdout` | `bytes` | `—` | pos/kw |
| `stderr` | `bytes \| None` | `—` | pos/kw |

### `InvalidManifestError`

Unspecified run-time error.

```python
pre_commit.commands.autoupdate.InvalidManifestError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RepositoryCannotBeUpdatedError`

Unspecified run-time error.

```python
pre_commit.commands.autoupdate.RepositoryCannotBeUpdatedError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RevInfo`

RevInfo(repo, rev, frozen, hook_ids)

```python
pre_commit.commands.autoupdate.RevInfo(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Store`

```python
pre_commit.commands.clean.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `InvalidConfigError`

Unspecified run-time error.

```python
pre_commit.commands.gc.InvalidConfigError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidManifestError`

Unspecified run-time error.

```python
pre_commit.commands.gc.InvalidManifestError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Store`

```python
pre_commit.commands.gc.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `Store`

```python
pre_commit.commands.hook_impl.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `CalledProcessError`

Unspecified run-time error.

```python
pre_commit.commands.init_templatedir.CalledProcessError(self, returncode: 'int', cmd: 'tuple[str, ...]', stdout: 'bytes', stderr: 'bytes | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `returncode` | `int` | `—` | pos/kw |
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |
| `stdout` | `bytes` | `—` | pos/kw |
| `stderr` | `bytes \| None` | `—` | pos/kw |

### `Store`

```python
pre_commit.commands.init_templatedir.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `InvalidConfigError`

Unspecified run-time error.

```python
pre_commit.commands.install_uninstall.InvalidConfigError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Store`

```python
pre_commit.commands.install_uninstall.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `InvalidConfigError`

Unspecified run-time error.

```python
pre_commit.commands.migrate_config.InvalidConfigError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MappingKey`

MappingKey(k,)

```python
pre_commit.commands.migrate_config.MappingKey(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MappingValue`

MappingValue(k,)

```python
pre_commit.commands.migrate_config.MappingValue(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SequenceItem`

SequenceItem()

```python
pre_commit.commands.migrate_config.SequenceItem(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Classifier`

```python
pre_commit.commands.run.Classifier(self, filenames: 'Iterable[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filenames` | `Iterable[str]` | `—` | pos/kw |

### `Hook`

Hook(src, prefix, id, name, entry, language, alias, files, exclude, types, types_or, exclude_types, additional_dependencies, args, always_run, fail_fast, pass_filenames, description, language_version…

```python
pre_commit.commands.run.Hook(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Store`

```python
pre_commit.commands.run.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `Store`

```python
pre_commit.commands.try_repo.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

### `Var`

Var(name, default)

```python
pre_commit.envcontext.Var(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FatalError`

Unspecified run-time error.

```python
pre_commit.error_handler.FatalError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Store`

```python
pre_commit.error_handler.Store(self, directory: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `directory` | `str \| None` | `None` | pos/kw |

## Functions

### `check_min_version`

```python
pre_commit.clientlib.check_min_version(version: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

### `check_type_tag`

```python
pre_commit.clientlib.check_type_tag(tag: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tag` | `str` | `—` | pos/kw |

### `parse_version`

poor man's version comparison

```python
pre_commit.clientlib.parse_version(s: 'str') -> 'tuple[int, ...]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `str` | `—` | pos/kw |

**Returns:** `tuple[int, ...]`

### `transform_stage`

```python
pre_commit.clientlib.transform_stage(stage: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stage` | `str` | `—` | pos/kw |

**Returns:** `str`

### `warn_for_stages_on_repo_init`

```python
pre_commit.clientlib.warn_for_stages_on_repo_init(repo: 'str', directory: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `directory` | `str` | `—` | pos/kw |

### `warn_unknown_keys_repo`

```python
pre_commit.clientlib.warn_unknown_keys_repo(extra: 'Sequence[str]', orig_keys: 'Sequence[str]', dct: 'dict[str, str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extra` | `Sequence[str]` | `—` | pos/kw |
| `orig_keys` | `Sequence[str]` | `—` | pos/kw |
| `dct` | `dict[str, str]` | `—` | pos/kw |

### `warn_unknown_keys_root`

```python
pre_commit.clientlib.warn_unknown_keys_root(extra: 'Sequence[str]', orig_keys: 'Sequence[str]', dct: 'dict[str, str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `extra` | `Sequence[str]` | `—` | pos/kw |
| `orig_keys` | `Sequence[str]` | `—` | pos/kw |
| `dct` | `dict[str, str]` | `—` | pos/kw |

### `add_color_option`

```python
pre_commit.color.add_color_option(parser: 'argparse.ArgumentParser') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `argparse.ArgumentParser` | `—` | pos/kw |

### `format_color`

Format text with color.

Args:
    text - Text to be formatted with color if `use_color`
    color - The color start string
    use_color_setting - Whether or not to color

```python
pre_commit.color.format_color(text: 'str', color: 'str', use_color_setting: 'bool') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `str` | `—` | pos/kw |
| `color` | `str` | `—` | pos/kw |
| `use_color_setting` | `bool` | `—` | pos/kw |

**Returns:** `str`

### `use_color`

Choose whether to use color based on the command argument.

Args:
    setting - Either `auto`, `always`, or `never`

```python
pre_commit.color.use_color(setting: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `setting` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `autoupdate`

Auto-update the pre-commit config to the latest versions of repos.

```python
pre_commit.commands.autoupdate.autoupdate(config_file: 'str', tags_only: 'bool', freeze: 'bool', repos: 'Sequence[str]' = (), jobs: 'int' = 1) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `tags_only` | `bool` | `—` | pos/kw |
| `freeze` | `bool` | `—` | pos/kw |
| `repos` | `Sequence[str]` | `()` | pos/kw |
| `jobs` | `int` | `1` | pos/kw |

**Returns:** `int`

### `cmd_output`

```python
pre_commit.commands.autoupdate.cmd_output(*cmd: 'str', **kwargs: 'Any') -> 'tuple[int, str, str | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, str, str | None]`

### `cmd_output_b`

```python
pre_commit.commands.autoupdate.cmd_output_b(*cmd: 'str', check: 'bool' = True, **kwargs: 'Any') -> 'tuple[int, bytes, bytes | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | *args |
| `check` | `bool` | `True` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, bytes, bytes | None]`

### `migrate_config`

```python
pre_commit.commands.autoupdate.migrate_config(config_file: 'str', quiet: 'bool' = False) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |

**Returns:** `int`

### `yaml_dump`

```python
pre_commit.commands.autoupdate.yaml_dump(o: 'Any', **kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `o` | `Any` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `clean`

```python
pre_commit.commands.clean.clean(store: 'Store') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `store` | `Store` | `—` | pos/kw |

**Returns:** `int`

### `rmtree`

On windows, rmtree fails for readonly dirs.

```python
pre_commit.commands.clean.rmtree(path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

### `gc`

```python
pre_commit.commands.gc.gc(store: 'Store') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `store` | `Store` | `—` | pos/kw |

**Returns:** `int`

### `rmtree`

On windows, rmtree fails for readonly dirs.

```python
pre_commit.commands.gc.rmtree(path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

### `add_parsers`

```python
pre_commit.commands.hazmat.add_parsers(parser: 'argparse.ArgumentParser') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `argparse.ArgumentParser` | `—` | pos/kw |

### `cd`

```python
pre_commit.commands.hazmat.cd(subdir: 'str', cmd: 'tuple[str, ...]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `subdir` | `str` | `—` | pos/kw |
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |

**Returns:** `int`

### `ignore_exit_code`

```python
pre_commit.commands.hazmat.ignore_exit_code(cmd: 'tuple[str, ...]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |

**Returns:** `int`

### `impl`

```python
pre_commit.commands.hazmat.impl(args: 'argparse.Namespace') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `argparse.Namespace` | `—` | pos/kw |

**Returns:** `int`

### `main`

```python
pre_commit.commands.hazmat.main(argv: 'Sequence[str] | None' = None) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `Sequence[str] \| None` | `None` | pos/kw |

**Returns:** `int`

### `n1`

```python
pre_commit.commands.hazmat.n1(cmd: 'tuple[str, ...]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |

**Returns:** `int`

### `normalize_cmd`

Fixes for the following issues on windows
- https://bugs.python.org/issue8557
- windows does not parse shebangs

This function also makes deep-path shebangs work just fine

```python
pre_commit.commands.hazmat.normalize_cmd(cmd: 'tuple[str, ...]', *, env: 'Mapping[str, str] | None' = None) -> 'tuple[str, ...]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |
| `env` | `Mapping[str, str] \| None` | `None` | kw |

**Returns:** `tuple[str, ...]`

### `envcontext`

In this context, `os.environ` is modified according to `patch`.

`patch` is an iterable of 2-tuples (key, value):
    `key`: string
    `value`:
        - string: `environ[key] == value` inside the c…

```python
pre_commit.commands.hook_impl.envcontext(patch: 'PatchesT', _env: 'MutableMapping[str, str] | None' = None) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `patch` | `PatchesT` | `—` | pos/kw |
| `_env` | `MutableMapping[str, str] \| None` | `None` | pos/kw |

**Returns:** `Generator[None]`

### `hook_impl`

```python
pre_commit.commands.hook_impl.hook_impl(store: 'Store', *, config: 'str', color: 'bool', hook_type: 'str', hook_dir: 'str | None', skip_on_missing_config: 'bool', args: 'Sequence[str]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `store` | `Store` | `—` | pos/kw |
| `config` | `str` | `—` | kw |
| `color` | `bool` | `—` | kw |
| `hook_type` | `str` | `—` | kw |
| `hook_dir` | `str \| None` | `—` | kw |
| `skip_on_missing_config` | `bool` | `—` | kw |
| `args` | `Sequence[str]` | `—` | kw |

**Returns:** `int`

### `normalize_cmd`

Fixes for the following issues on windows
- https://bugs.python.org/issue8557
- windows does not parse shebangs

This function also makes deep-path shebangs work just fine

```python
pre_commit.commands.hook_impl.normalize_cmd(cmd: 'tuple[str, ...]', *, env: 'Mapping[str, str] | None' = None) -> 'tuple[str, ...]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |
| `env` | `Mapping[str, str] \| None` | `None` | kw |

**Returns:** `tuple[str, ...]`

### `run`

```python
pre_commit.commands.hook_impl.run(config_file: 'str', store: 'Store', args: 'argparse.Namespace', environ: 'MutableMapping[str, str]' = environ({'SHELL': '/bin/bash', 'COREPACK_ENABLE_AUTO_PIN': '0', 'QT_ACCESSIBILITY': '1', 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg', 'XDG_MENU_PREFIX': 'gnome-', 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated', 'APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL': '1', 'QT_IM_MODULES': 'wayland;ibus', 'AI_AGENT': 'claude-code/2.1.123/agent', 'CLAUDE_CODE_ENABLE_SDK_FILE_CHECKPOINTING': 'true', 'GNOME_SHELL_SESSION_MODE': 'ubuntu', 'SSH_AUTH_SOCK': '/run/user/1000/gcr/ssh', 'NODE_EXTRA_CA_CERTS': '/mnt/glusterfs/portainer/data/step-ca/certs/root_ca.crt', 'MEMORY_PRESSURE_WRITE': 'c29tZSAyMDAwMDAgMjAwMDAwMAA=', 'ELECTRON_RUN_AS_NODE': '1', 'XMODIFIERS': '@im=ibus', 'DESKTOP_SESSION': 'ubuntu', 'GTK_MODULES': 'gail:atk-bridge', 'PWD': '/home/seli/docker-swarm-stacks/nvidia-dgx-spark/cca', 'LOGNAME': 'seli', 'XDG_SESSION_DESKTOP': 'ubuntu', 'XDG_SESSION_TYPE': 'wayland', 'COPILOT_OTEL_FILE_EXPORTER_PATH': '/dev/null', 'VSCODE_ESM_ENTRYPOINT': 'vs/workbench/api/node/extensionHostProcess', 'GPG_AGENT_INFO': '/run/user/1000/gnupg/S.gpg-agent:0:1', 'SYSTEMD_EXEC_PID': '31692', 'VSCODE_CODE_CACHE_PATH': '/home/seli/.config/Code/CachedData/10c8e557c8b9f9ed0a87f61f1c9a44bde731c409', 'XAUTHORITY': '/run/user/1000/.mutter-Xwaylandauth.24AUM3', 'NoDefaultCurrentDirectoryInExePath': '1', 'IM_CONFIG_CHECK_ENV': '1', 'GJS_DEBUG_TOPICS': 'JS ERROR;JS LOG', 'CLAUDECODE': '1', 'HOME': '/home/seli', 'USERNAME': 'seli', 'CLAUDE_AGENT_SDK_VERSION': '0.2.123', 'IM_CONFIG_PHASE': '1', 'LANG': 'en_US.UTF-8', 'LS_COLORS': 'rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:', 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME', 'VSCODE_DOTNET_INSTALL_TOOL_ORIGINAL_HOME': '/home/seli', 'VIRTUAL_ENV': '/home/seli/docker-swarm-stacks/.venv', 'MEMORY_PRESSURE_WATCH': '/sys/fs/cgroup/user.slice/user-1000.slice/user@1000.service/session.slice/org.gnome.Shell@wayland.service/memory.pressure', 'VSCODE_IPC_HOOK': '/run/user/1000/vscode-58cce40e-1.11-main.sock', 'WAYLAND_DISPLAY': 'wayland-0', 'VSCODE_L10N_BUNDLE_LOCATION': '', 'INVOCATION_ID': 'b5cdc512716f4a58a458467da4b54ecc', 'MANAGERPID': '31372', 'CHROME_DESKTOP': 'code.desktop', 'GJS_DEBUG_OUTPUT': 'stderr', 'GNOME_SETUP_DISPLAY': ':1', 'LESSCLOSE': '/usr/bin/lesspipe %s %s', 'XDG_SESSION_CLASS': 'user', 'COPILOT_OTEL_ENABLED': 'true', 'LESSOPEN': '| /usr/bin/lesspipe %s', 'USER': 'seli', 'DISPLAY': ':0', 'VSCODE_PID': '554786', 'SHLVL': '2', 'GIT_EDITOR': 'true', 'QT_IM_MODULE': 'ibus', 'APPLICATIONINSIGHTS_CONFIGURATION_CONTENT': '{}', 'VSCODE_CWD': '/home/seli', 'OTEL_EXPORTER_OTLP_METRICS_TEMPORALITY_PREFERENCE': 'delta', 'FC_FONTATIONS': '1', 'VSCODE_CRASH_REPORTER_PROCESS_TYPE': 'extensionHost', 'XDG_RUNTIME_DIR': '/run/user/1000', 'CLAUDE_CODE_ENTRYPOINT': 'claude-vscode', 'DEBUGINFOD_URLS': 'https://debuginfod.ubuntu.com ', 'OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT': 'true', 'MCP_CONNECTION_NONBLOCKING': 'true', 'JOURNAL_STREAM': '9:114118', 'XDG_DATA_DIRS': '/usr/share/ubuntu:/usr/share/gnome:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop', 'GDK_BACKEND': 'wayland', 'CLAUDE_CODE_EXECPATH': '/home/seli/.vscode/extensions/anthropic.claude-code-2.1.123-linux-x64/resources/native-binary/claude', 'PATH': '/home/seli/docker-swarm-stacks/.venv/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin', 'GDMSESSION': 'ubuntu', 'APPLICATION_INSIGHTS_NO_STATSBEAT': 'true', 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus', 'VSCODE_NLS_CONFIG': '{"userLocale":"en-us","osLocale":"en-us","resolvedLanguage":"en","defaultMessagesFile":"/usr/share/code/resources/app/out/nls.messages.json","locale":"en-us","availableLanguages":{}}', 'GIO_LAUNCHED_DESKTOP_FILE_PID': '554786', 'GIO_LAUNCHED_DESKTOP_FILE': '/home/seli/.local/share/applications/code.desktop', 'VSCODE_HANDLES_UNCAUGHT_ERRORS': 'true', 'OLDPWD': '/tmp/js-extract-test', 'COPILOT_OTEL_EXPORTER_TYPE': 'file', '_': '/home/seli/docker-swarm-stacks/.venv/bin/python'})) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |
| `args` | `argparse.Namespace` | `—` | pos/kw |
| `environ` | `MutableMapping[str, str]` | `environ({'SHELL': '/bin/bash', 'COREPACK_ENABLE_AUTO_PIN': '0', 'QT_ACCESSIBILITY': '1', 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg', 'XDG_MENU_PREFIX': 'gnome-', 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated', 'APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL': '1', 'QT_IM_MODULES': 'wayland;ibus', 'AI_AGENT': 'claude-code/2.1.123/agent', 'CLAUDE_CODE_ENABLE_SDK_FILE_CHECKPOINTING': 'true', 'GNOME_SHELL_SESSION_MODE': 'ubuntu', 'SSH_AUTH_SOCK': '/run/user/1000/gcr/ssh', 'NODE_EXTRA_CA_CERTS': '/mnt/glusterfs/portainer/data/step-ca/certs/root_ca.crt', 'MEMORY_PRESSURE_WRITE': 'c29tZSAyMDAwMDAgMjAwMDAwMAA=', 'ELECTRON_RUN_AS_NODE': '1', 'XMODIFIERS': '@im=ibus', 'DESKTOP_SESSION': 'ubuntu', 'GTK_MODULES': 'gail:atk-bridge', 'PWD': '/home/seli/docker-swarm-stacks/nvidia-dgx-spark/cca', 'LOGNAME': 'seli', 'XDG_SESSION_DESKTOP': 'ubuntu', 'XDG_SESSION_TYPE': 'wayland', 'COPILOT_OTEL_FILE_EXPORTER_PATH': '/dev/null', 'VSCODE_ESM_ENTRYPOINT': 'vs/workbench/api/node/extensionHostProcess', 'GPG_AGENT_INFO': '/run/user/1000/gnupg/S.gpg-agent:0:1', 'SYSTEMD_EXEC_PID': '31692', 'VSCODE_CODE_CACHE_PATH': '/home/seli/.config/Code/CachedData/10c8e557c8b9f9ed0a87f61f1c9a44bde731c409', 'XAUTHORITY': '/run/user/1000/.mutter-Xwaylandauth.24AUM3', 'NoDefaultCurrentDirectoryInExePath': '1', 'IM_CONFIG_CHECK_ENV': '1', 'GJS_DEBUG_TOPICS': 'JS ERROR;JS LOG', 'CLAUDECODE': '1', 'HOME': '/home/seli', 'USERNAME': 'seli', 'CLAUDE_AGENT_SDK_VERSION': '0.2.123', 'IM_CONFIG_PHASE': '1', 'LANG': 'en_US.UTF-8', 'LS_COLORS': 'rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:', 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME', 'VSCODE_DOTNET_INSTALL_TOOL_ORIGINAL_HOME': '/home/seli', 'VIRTUAL_ENV': '/home/seli/docker-swarm-stacks/.venv', 'MEMORY_PRESSURE_WATCH': '/sys/fs/cgroup/user.slice/user-1000.slice/user@1000.service/session.slice/org.gnome.Shell@wayland.service/memory.pressure', 'VSCODE_IPC_HOOK': '/run/user/1000/vscode-58cce40e-1.11-main.sock', 'WAYLAND_DISPLAY': 'wayland-0', 'VSCODE_L10N_BUNDLE_LOCATION': '', 'INVOCATION_ID': 'b5cdc512716f4a58a458467da4b54ecc', 'MANAGERPID': '31372', 'CHROME_DESKTOP': 'code.desktop', 'GJS_DEBUG_OUTPUT': 'stderr', 'GNOME_SETUP_DISPLAY': ':1', 'LESSCLOSE': '/usr/bin/lesspipe %s %s', 'XDG_SESSION_CLASS': 'user', 'COPILOT_OTEL_ENABLED': 'true', 'LESSOPEN': '\| /usr/bin/lesspipe %s', 'USER': 'seli', 'DISPLAY': ':0', 'VSCODE_PID': '554786', 'SHLVL': '2', 'GIT_EDITOR': 'true', 'QT_IM_MODULE': 'ibus', 'APPLICATIONINSIGHTS_CONFIGURATION_CONTENT': '{}', 'VSCODE_CWD': '/home/seli', 'OTEL_EXPORTER_OTLP_METRICS_TEMPORALITY_PREFERENCE': 'delta', 'FC_FONTATIONS': '1', 'VSCODE_CRASH_REPORTER_PROCESS_TYPE': 'extensionHost', 'XDG_RUNTIME_DIR': '/run/user/1000', 'CLAUDE_CODE_ENTRYPOINT': 'claude-vscode', 'DEBUGINFOD_URLS': 'https://debuginfod.ubuntu.com ', 'OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT': 'true', 'MCP_CONNECTION_NONBLOCKING': 'true', 'JOURNAL_STREAM': '9:114118', 'XDG_DATA_DIRS': '/usr/share/ubuntu:/usr/share/gnome:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop', 'GDK_BACKEND': 'wayland', 'CLAUDE_CODE_EXECPATH': '/home/seli/.vscode/extensions/anthropic.claude-code-2.1.123-linux-x64/resources/native-binary/claude', 'PATH': '/home/seli/docker-swarm-stacks/.venv/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin', 'GDMSESSION': 'ubuntu', 'APPLICATION_INSIGHTS_NO_STATSBEAT': 'true', 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus', 'VSCODE_NLS_CONFIG': '{"userLocale":"en-us","osLocale":"en-us","resolvedLanguage":"en","defaultMessagesFile":"/usr/share/code/resources/app/out/nls.messages.json","locale":"en-us","availableLanguages":{}}', 'GIO_LAUNCHED_DESKTOP_FILE_PID': '554786', 'GIO_LAUNCHED_DESKTOP_FILE': '/home/seli/.local/share/applications/code.desktop', 'VSCODE_HANDLES_UNCAUGHT_ERRORS': 'true', 'OLDPWD': '/tmp/js-extract-test', 'COPILOT_OTEL_EXPORTER_TYPE': 'file', '_': '/home/seli/docker-swarm-stacks/.venv/bin/python'})` | pos/kw |

**Returns:** `int`

### `cmd_output`

```python
pre_commit.commands.init_templatedir.cmd_output(*cmd: 'str', **kwargs: 'Any') -> 'tuple[int, str, str | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, str, str | None]`

### `init_templatedir`

```python
pre_commit.commands.init_templatedir.init_templatedir(config_file: 'str', store: 'Store', directory: 'str', hook_types: 'list[str] | None', skip_on_missing_config: 'bool' = True) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |
| `directory` | `str` | `—` | pos/kw |
| `hook_types` | `list[str] \| None` | `—` | pos/kw |
| `skip_on_missing_config` | `bool` | `True` | pos/kw |

**Returns:** `int`

### `install`

```python
pre_commit.commands.init_templatedir.install(config_file: 'str', store: 'Store', hook_types: 'list[str] | None', overwrite: 'bool' = False, hooks: 'bool' = False, skip_on_missing_config: 'bool' = False, git_dir: 'str | None' = None) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |
| `hook_types` | `list[str] \| None` | `—` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `hooks` | `bool` | `False` | pos/kw |
| `skip_on_missing_config` | `bool` | `False` | pos/kw |
| `git_dir` | `str \| None` | `None` | pos/kw |

**Returns:** `int`

### `all_hooks`

```python
pre_commit.commands.install_uninstall.all_hooks(root_config: 'dict[str, Any]', store: 'Store') -> 'tuple[Hook, ...]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root_config` | `dict[str, Any]` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |

**Returns:** `tuple[Hook, ...]`

### `install`

```python
pre_commit.commands.install_uninstall.install(config_file: 'str', store: 'Store', hook_types: 'list[str] | None', overwrite: 'bool' = False, hooks: 'bool' = False, skip_on_missing_config: 'bool' = False, git_dir: 'str | None' = None) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |
| `hook_types` | `list[str] \| None` | `—` | pos/kw |
| `overwrite` | `bool` | `False` | pos/kw |
| `hooks` | `bool` | `False` | pos/kw |
| `skip_on_missing_config` | `bool` | `False` | pos/kw |
| `git_dir` | `str \| None` | `None` | pos/kw |

**Returns:** `int`

### `install_hook_envs`

```python
pre_commit.commands.install_uninstall.install_hook_envs(hooks: 'Sequence[Hook]', store: 'Store') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hooks` | `Sequence[Hook]` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |

### `install_hooks`

```python
pre_commit.commands.install_uninstall.install_hooks(config_file: 'str', store: 'Store') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |

**Returns:** `int`

### `is_our_script`

```python
pre_commit.commands.install_uninstall.is_our_script(filename: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `make_executable`

```python
pre_commit.commands.install_uninstall.make_executable(filename: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `resource_text`

```python
pre_commit.commands.install_uninstall.resource_text(filename: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `str`

### `uninstall`

```python
pre_commit.commands.install_uninstall.uninstall(config_file: 'str', hook_types: 'list[str] | None') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `hook_types` | `list[str] \| None` | `—` | pos/kw |

**Returns:** `int`

### `match`

```python
pre_commit.commands.migrate_config.match(n: 'Node', matcher: 'tuple[_Matcher, ...]') -> 'Generator[ScalarNode]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `n` | `Node` | `—` | pos/kw |
| `matcher` | `tuple[_Matcher, ...]` | `—` | pos/kw |

**Returns:** `Generator[ScalarNode]`

### `migrate_config`

```python
pre_commit.commands.migrate_config.migrate_config(config_file: 'str', quiet: 'bool' = False) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `quiet` | `bool` | `False` | pos/kw |

**Returns:** `int`

### `all_hooks`

```python
pre_commit.commands.run.all_hooks(root_config: 'dict[str, Any]', store: 'Store') -> 'tuple[Hook, ...]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root_config` | `dict[str, Any]` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |

**Returns:** `tuple[Hook, ...]`

### `cmd_output_b`

```python
pre_commit.commands.run.cmd_output_b(*cmd: 'str', check: 'bool' = True, **kwargs: 'Any') -> 'tuple[int, bytes, bytes | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | *args |
| `check` | `bool` | `True` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, bytes, bytes | None]`

### `filter_by_include_exclude`

```python
pre_commit.commands.run.filter_by_include_exclude(names: 'Iterable[str]', include: 'str', exclude: 'str') -> 'Generator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `names` | `Iterable[str]` | `—` | pos/kw |
| `include` | `str` | `—` | pos/kw |
| `exclude` | `str` | `—` | pos/kw |

**Returns:** `Generator[str]`

### `install_hook_envs`

```python
pre_commit.commands.run.install_hook_envs(hooks: 'Sequence[Hook]', store: 'Store') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hooks` | `Sequence[Hook]` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |

### `run`

```python
pre_commit.commands.run.run(config_file: 'str', store: 'Store', args: 'argparse.Namespace', environ: 'MutableMapping[str, str]' = environ({'SHELL': '/bin/bash', 'COREPACK_ENABLE_AUTO_PIN': '0', 'QT_ACCESSIBILITY': '1', 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg', 'XDG_MENU_PREFIX': 'gnome-', 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated', 'APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL': '1', 'QT_IM_MODULES': 'wayland;ibus', 'AI_AGENT': 'claude-code/2.1.123/agent', 'CLAUDE_CODE_ENABLE_SDK_FILE_CHECKPOINTING': 'true', 'GNOME_SHELL_SESSION_MODE': 'ubuntu', 'SSH_AUTH_SOCK': '/run/user/1000/gcr/ssh', 'NODE_EXTRA_CA_CERTS': '/mnt/glusterfs/portainer/data/step-ca/certs/root_ca.crt', 'MEMORY_PRESSURE_WRITE': 'c29tZSAyMDAwMDAgMjAwMDAwMAA=', 'ELECTRON_RUN_AS_NODE': '1', 'XMODIFIERS': '@im=ibus', 'DESKTOP_SESSION': 'ubuntu', 'GTK_MODULES': 'gail:atk-bridge', 'PWD': '/home/seli/docker-swarm-stacks/nvidia-dgx-spark/cca', 'LOGNAME': 'seli', 'XDG_SESSION_DESKTOP': 'ubuntu', 'XDG_SESSION_TYPE': 'wayland', 'COPILOT_OTEL_FILE_EXPORTER_PATH': '/dev/null', 'VSCODE_ESM_ENTRYPOINT': 'vs/workbench/api/node/extensionHostProcess', 'GPG_AGENT_INFO': '/run/user/1000/gnupg/S.gpg-agent:0:1', 'SYSTEMD_EXEC_PID': '31692', 'VSCODE_CODE_CACHE_PATH': '/home/seli/.config/Code/CachedData/10c8e557c8b9f9ed0a87f61f1c9a44bde731c409', 'XAUTHORITY': '/run/user/1000/.mutter-Xwaylandauth.24AUM3', 'NoDefaultCurrentDirectoryInExePath': '1', 'IM_CONFIG_CHECK_ENV': '1', 'GJS_DEBUG_TOPICS': 'JS ERROR;JS LOG', 'CLAUDECODE': '1', 'HOME': '/home/seli', 'USERNAME': 'seli', 'CLAUDE_AGENT_SDK_VERSION': '0.2.123', 'IM_CONFIG_PHASE': '1', 'LANG': 'en_US.UTF-8', 'LS_COLORS': 'rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:', 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME', 'VSCODE_DOTNET_INSTALL_TOOL_ORIGINAL_HOME': '/home/seli', 'VIRTUAL_ENV': '/home/seli/docker-swarm-stacks/.venv', 'MEMORY_PRESSURE_WATCH': '/sys/fs/cgroup/user.slice/user-1000.slice/user@1000.service/session.slice/org.gnome.Shell@wayland.service/memory.pressure', 'VSCODE_IPC_HOOK': '/run/user/1000/vscode-58cce40e-1.11-main.sock', 'WAYLAND_DISPLAY': 'wayland-0', 'VSCODE_L10N_BUNDLE_LOCATION': '', 'INVOCATION_ID': 'b5cdc512716f4a58a458467da4b54ecc', 'MANAGERPID': '31372', 'CHROME_DESKTOP': 'code.desktop', 'GJS_DEBUG_OUTPUT': 'stderr', 'GNOME_SETUP_DISPLAY': ':1', 'LESSCLOSE': '/usr/bin/lesspipe %s %s', 'XDG_SESSION_CLASS': 'user', 'COPILOT_OTEL_ENABLED': 'true', 'LESSOPEN': '| /usr/bin/lesspipe %s', 'USER': 'seli', 'DISPLAY': ':0', 'VSCODE_PID': '554786', 'SHLVL': '2', 'GIT_EDITOR': 'true', 'QT_IM_MODULE': 'ibus', 'APPLICATIONINSIGHTS_CONFIGURATION_CONTENT': '{}', 'VSCODE_CWD': '/home/seli', 'OTEL_EXPORTER_OTLP_METRICS_TEMPORALITY_PREFERENCE': 'delta', 'FC_FONTATIONS': '1', 'VSCODE_CRASH_REPORTER_PROCESS_TYPE': 'extensionHost', 'XDG_RUNTIME_DIR': '/run/user/1000', 'CLAUDE_CODE_ENTRYPOINT': 'claude-vscode', 'DEBUGINFOD_URLS': 'https://debuginfod.ubuntu.com ', 'OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT': 'true', 'MCP_CONNECTION_NONBLOCKING': 'true', 'JOURNAL_STREAM': '9:114118', 'XDG_DATA_DIRS': '/usr/share/ubuntu:/usr/share/gnome:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop', 'GDK_BACKEND': 'wayland', 'CLAUDE_CODE_EXECPATH': '/home/seli/.vscode/extensions/anthropic.claude-code-2.1.123-linux-x64/resources/native-binary/claude', 'PATH': '/home/seli/docker-swarm-stacks/.venv/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin', 'GDMSESSION': 'ubuntu', 'APPLICATION_INSIGHTS_NO_STATSBEAT': 'true', 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus', 'VSCODE_NLS_CONFIG': '{"userLocale":"en-us","osLocale":"en-us","resolvedLanguage":"en","defaultMessagesFile":"/usr/share/code/resources/app/out/nls.messages.json","locale":"en-us","availableLanguages":{}}', 'GIO_LAUNCHED_DESKTOP_FILE_PID': '554786', 'GIO_LAUNCHED_DESKTOP_FILE': '/home/seli/.local/share/applications/code.desktop', 'VSCODE_HANDLES_UNCAUGHT_ERRORS': 'true', 'OLDPWD': '/tmp/js-extract-test', 'COPILOT_OTEL_EXPORTER_TYPE': 'file', '_': '/home/seli/docker-swarm-stacks/.venv/bin/python'})) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |
| `args` | `argparse.Namespace` | `—` | pos/kw |
| `environ` | `MutableMapping[str, str]` | `environ({'SHELL': '/bin/bash', 'COREPACK_ENABLE_AUTO_PIN': '0', 'QT_ACCESSIBILITY': '1', 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg', 'XDG_MENU_PREFIX': 'gnome-', 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated', 'APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL': '1', 'QT_IM_MODULES': 'wayland;ibus', 'AI_AGENT': 'claude-code/2.1.123/agent', 'CLAUDE_CODE_ENABLE_SDK_FILE_CHECKPOINTING': 'true', 'GNOME_SHELL_SESSION_MODE': 'ubuntu', 'SSH_AUTH_SOCK': '/run/user/1000/gcr/ssh', 'NODE_EXTRA_CA_CERTS': '/mnt/glusterfs/portainer/data/step-ca/certs/root_ca.crt', 'MEMORY_PRESSURE_WRITE': 'c29tZSAyMDAwMDAgMjAwMDAwMAA=', 'ELECTRON_RUN_AS_NODE': '1', 'XMODIFIERS': '@im=ibus', 'DESKTOP_SESSION': 'ubuntu', 'GTK_MODULES': 'gail:atk-bridge', 'PWD': '/home/seli/docker-swarm-stacks/nvidia-dgx-spark/cca', 'LOGNAME': 'seli', 'XDG_SESSION_DESKTOP': 'ubuntu', 'XDG_SESSION_TYPE': 'wayland', 'COPILOT_OTEL_FILE_EXPORTER_PATH': '/dev/null', 'VSCODE_ESM_ENTRYPOINT': 'vs/workbench/api/node/extensionHostProcess', 'GPG_AGENT_INFO': '/run/user/1000/gnupg/S.gpg-agent:0:1', 'SYSTEMD_EXEC_PID': '31692', 'VSCODE_CODE_CACHE_PATH': '/home/seli/.config/Code/CachedData/10c8e557c8b9f9ed0a87f61f1c9a44bde731c409', 'XAUTHORITY': '/run/user/1000/.mutter-Xwaylandauth.24AUM3', 'NoDefaultCurrentDirectoryInExePath': '1', 'IM_CONFIG_CHECK_ENV': '1', 'GJS_DEBUG_TOPICS': 'JS ERROR;JS LOG', 'CLAUDECODE': '1', 'HOME': '/home/seli', 'USERNAME': 'seli', 'CLAUDE_AGENT_SDK_VERSION': '0.2.123', 'IM_CONFIG_PHASE': '1', 'LANG': 'en_US.UTF-8', 'LS_COLORS': 'rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:', 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME', 'VSCODE_DOTNET_INSTALL_TOOL_ORIGINAL_HOME': '/home/seli', 'VIRTUAL_ENV': '/home/seli/docker-swarm-stacks/.venv', 'MEMORY_PRESSURE_WATCH': '/sys/fs/cgroup/user.slice/user-1000.slice/user@1000.service/session.slice/org.gnome.Shell@wayland.service/memory.pressure', 'VSCODE_IPC_HOOK': '/run/user/1000/vscode-58cce40e-1.11-main.sock', 'WAYLAND_DISPLAY': 'wayland-0', 'VSCODE_L10N_BUNDLE_LOCATION': '', 'INVOCATION_ID': 'b5cdc512716f4a58a458467da4b54ecc', 'MANAGERPID': '31372', 'CHROME_DESKTOP': 'code.desktop', 'GJS_DEBUG_OUTPUT': 'stderr', 'GNOME_SETUP_DISPLAY': ':1', 'LESSCLOSE': '/usr/bin/lesspipe %s %s', 'XDG_SESSION_CLASS': 'user', 'COPILOT_OTEL_ENABLED': 'true', 'LESSOPEN': '\| /usr/bin/lesspipe %s', 'USER': 'seli', 'DISPLAY': ':0', 'VSCODE_PID': '554786', 'SHLVL': '2', 'GIT_EDITOR': 'true', 'QT_IM_MODULE': 'ibus', 'APPLICATIONINSIGHTS_CONFIGURATION_CONTENT': '{}', 'VSCODE_CWD': '/home/seli', 'OTEL_EXPORTER_OTLP_METRICS_TEMPORALITY_PREFERENCE': 'delta', 'FC_FONTATIONS': '1', 'VSCODE_CRASH_REPORTER_PROCESS_TYPE': 'extensionHost', 'XDG_RUNTIME_DIR': '/run/user/1000', 'CLAUDE_CODE_ENTRYPOINT': 'claude-vscode', 'DEBUGINFOD_URLS': 'https://debuginfod.ubuntu.com ', 'OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT': 'true', 'MCP_CONNECTION_NONBLOCKING': 'true', 'JOURNAL_STREAM': '9:114118', 'XDG_DATA_DIRS': '/usr/share/ubuntu:/usr/share/gnome:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop', 'GDK_BACKEND': 'wayland', 'CLAUDE_CODE_EXECPATH': '/home/seli/.vscode/extensions/anthropic.claude-code-2.1.123-linux-x64/resources/native-binary/claude', 'PATH': '/home/seli/docker-swarm-stacks/.venv/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin', 'GDMSESSION': 'ubuntu', 'APPLICATION_INSIGHTS_NO_STATSBEAT': 'true', 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus', 'VSCODE_NLS_CONFIG': '{"userLocale":"en-us","osLocale":"en-us","resolvedLanguage":"en","defaultMessagesFile":"/usr/share/code/resources/app/out/nls.messages.json","locale":"en-us","availableLanguages":{}}', 'GIO_LAUNCHED_DESKTOP_FILE_PID': '554786', 'GIO_LAUNCHED_DESKTOP_FILE': '/home/seli/.local/share/applications/code.desktop', 'VSCODE_HANDLES_UNCAUGHT_ERRORS': 'true', 'OLDPWD': '/tmp/js-extract-test', 'COPILOT_OTEL_EXPORTER_TYPE': 'file', '_': '/home/seli/docker-swarm-stacks/.venv/bin/python'})` | pos/kw |

**Returns:** `int`

### `staged_files_only`

Clear any unstaged changes from the git working directory inside this
context.

```python
pre_commit.commands.run.staged_files_only(patch_dir: 'str') -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `patch_dir` | `str` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `sample_config`

```python
pre_commit.commands.sample_config.sample_config() -> 'int'
```

**Returns:** `int`

### `cmd_output_b`

```python
pre_commit.commands.try_repo.cmd_output_b(*cmd: 'str', check: 'bool' = True, **kwargs: 'Any') -> 'tuple[int, bytes, bytes | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | *args |
| `check` | `bool` | `True` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, bytes, bytes | None]`

### `run`

```python
pre_commit.commands.try_repo.run(config_file: 'str', store: 'Store', args: 'argparse.Namespace', environ: 'MutableMapping[str, str]' = environ({'SHELL': '/bin/bash', 'COREPACK_ENABLE_AUTO_PIN': '0', 'QT_ACCESSIBILITY': '1', 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg', 'XDG_MENU_PREFIX': 'gnome-', 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated', 'APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL': '1', 'QT_IM_MODULES': 'wayland;ibus', 'AI_AGENT': 'claude-code/2.1.123/agent', 'CLAUDE_CODE_ENABLE_SDK_FILE_CHECKPOINTING': 'true', 'GNOME_SHELL_SESSION_MODE': 'ubuntu', 'SSH_AUTH_SOCK': '/run/user/1000/gcr/ssh', 'NODE_EXTRA_CA_CERTS': '/mnt/glusterfs/portainer/data/step-ca/certs/root_ca.crt', 'MEMORY_PRESSURE_WRITE': 'c29tZSAyMDAwMDAgMjAwMDAwMAA=', 'ELECTRON_RUN_AS_NODE': '1', 'XMODIFIERS': '@im=ibus', 'DESKTOP_SESSION': 'ubuntu', 'GTK_MODULES': 'gail:atk-bridge', 'PWD': '/home/seli/docker-swarm-stacks/nvidia-dgx-spark/cca', 'LOGNAME': 'seli', 'XDG_SESSION_DESKTOP': 'ubuntu', 'XDG_SESSION_TYPE': 'wayland', 'COPILOT_OTEL_FILE_EXPORTER_PATH': '/dev/null', 'VSCODE_ESM_ENTRYPOINT': 'vs/workbench/api/node/extensionHostProcess', 'GPG_AGENT_INFO': '/run/user/1000/gnupg/S.gpg-agent:0:1', 'SYSTEMD_EXEC_PID': '31692', 'VSCODE_CODE_CACHE_PATH': '/home/seli/.config/Code/CachedData/10c8e557c8b9f9ed0a87f61f1c9a44bde731c409', 'XAUTHORITY': '/run/user/1000/.mutter-Xwaylandauth.24AUM3', 'NoDefaultCurrentDirectoryInExePath': '1', 'IM_CONFIG_CHECK_ENV': '1', 'GJS_DEBUG_TOPICS': 'JS ERROR;JS LOG', 'CLAUDECODE': '1', 'HOME': '/home/seli', 'USERNAME': 'seli', 'CLAUDE_AGENT_SDK_VERSION': '0.2.123', 'IM_CONFIG_PHASE': '1', 'LANG': 'en_US.UTF-8', 'LS_COLORS': 'rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:', 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME', 'VSCODE_DOTNET_INSTALL_TOOL_ORIGINAL_HOME': '/home/seli', 'VIRTUAL_ENV': '/home/seli/docker-swarm-stacks/.venv', 'MEMORY_PRESSURE_WATCH': '/sys/fs/cgroup/user.slice/user-1000.slice/user@1000.service/session.slice/org.gnome.Shell@wayland.service/memory.pressure', 'VSCODE_IPC_HOOK': '/run/user/1000/vscode-58cce40e-1.11-main.sock', 'WAYLAND_DISPLAY': 'wayland-0', 'VSCODE_L10N_BUNDLE_LOCATION': '', 'INVOCATION_ID': 'b5cdc512716f4a58a458467da4b54ecc', 'MANAGERPID': '31372', 'CHROME_DESKTOP': 'code.desktop', 'GJS_DEBUG_OUTPUT': 'stderr', 'GNOME_SETUP_DISPLAY': ':1', 'LESSCLOSE': '/usr/bin/lesspipe %s %s', 'XDG_SESSION_CLASS': 'user', 'COPILOT_OTEL_ENABLED': 'true', 'LESSOPEN': '| /usr/bin/lesspipe %s', 'USER': 'seli', 'DISPLAY': ':0', 'VSCODE_PID': '554786', 'SHLVL': '2', 'GIT_EDITOR': 'true', 'QT_IM_MODULE': 'ibus', 'APPLICATIONINSIGHTS_CONFIGURATION_CONTENT': '{}', 'VSCODE_CWD': '/home/seli', 'OTEL_EXPORTER_OTLP_METRICS_TEMPORALITY_PREFERENCE': 'delta', 'FC_FONTATIONS': '1', 'VSCODE_CRASH_REPORTER_PROCESS_TYPE': 'extensionHost', 'XDG_RUNTIME_DIR': '/run/user/1000', 'CLAUDE_CODE_ENTRYPOINT': 'claude-vscode', 'DEBUGINFOD_URLS': 'https://debuginfod.ubuntu.com ', 'OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT': 'true', 'MCP_CONNECTION_NONBLOCKING': 'true', 'JOURNAL_STREAM': '9:114118', 'XDG_DATA_DIRS': '/usr/share/ubuntu:/usr/share/gnome:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop', 'GDK_BACKEND': 'wayland', 'CLAUDE_CODE_EXECPATH': '/home/seli/.vscode/extensions/anthropic.claude-code-2.1.123-linux-x64/resources/native-binary/claude', 'PATH': '/home/seli/docker-swarm-stacks/.venv/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin', 'GDMSESSION': 'ubuntu', 'APPLICATION_INSIGHTS_NO_STATSBEAT': 'true', 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus', 'VSCODE_NLS_CONFIG': '{"userLocale":"en-us","osLocale":"en-us","resolvedLanguage":"en","defaultMessagesFile":"/usr/share/code/resources/app/out/nls.messages.json","locale":"en-us","availableLanguages":{}}', 'GIO_LAUNCHED_DESKTOP_FILE_PID': '554786', 'GIO_LAUNCHED_DESKTOP_FILE': '/home/seli/.local/share/applications/code.desktop', 'VSCODE_HANDLES_UNCAUGHT_ERRORS': 'true', 'OLDPWD': '/tmp/js-extract-test', 'COPILOT_OTEL_EXPORTER_TYPE': 'file', '_': '/home/seli/docker-swarm-stacks/.venv/bin/python'})) -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `store` | `Store` | `—` | pos/kw |
| `args` | `argparse.Namespace` | `—` | pos/kw |
| `environ` | `MutableMapping[str, str]` | `environ({'SHELL': '/bin/bash', 'COREPACK_ENABLE_AUTO_PIN': '0', 'QT_ACCESSIBILITY': '1', 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg', 'XDG_MENU_PREFIX': 'gnome-', 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated', 'APPLICATION_INSIGHTS_NO_DIAGNOSTIC_CHANNEL': '1', 'QT_IM_MODULES': 'wayland;ibus', 'AI_AGENT': 'claude-code/2.1.123/agent', 'CLAUDE_CODE_ENABLE_SDK_FILE_CHECKPOINTING': 'true', 'GNOME_SHELL_SESSION_MODE': 'ubuntu', 'SSH_AUTH_SOCK': '/run/user/1000/gcr/ssh', 'NODE_EXTRA_CA_CERTS': '/mnt/glusterfs/portainer/data/step-ca/certs/root_ca.crt', 'MEMORY_PRESSURE_WRITE': 'c29tZSAyMDAwMDAgMjAwMDAwMAA=', 'ELECTRON_RUN_AS_NODE': '1', 'XMODIFIERS': '@im=ibus', 'DESKTOP_SESSION': 'ubuntu', 'GTK_MODULES': 'gail:atk-bridge', 'PWD': '/home/seli/docker-swarm-stacks/nvidia-dgx-spark/cca', 'LOGNAME': 'seli', 'XDG_SESSION_DESKTOP': 'ubuntu', 'XDG_SESSION_TYPE': 'wayland', 'COPILOT_OTEL_FILE_EXPORTER_PATH': '/dev/null', 'VSCODE_ESM_ENTRYPOINT': 'vs/workbench/api/node/extensionHostProcess', 'GPG_AGENT_INFO': '/run/user/1000/gnupg/S.gpg-agent:0:1', 'SYSTEMD_EXEC_PID': '31692', 'VSCODE_CODE_CACHE_PATH': '/home/seli/.config/Code/CachedData/10c8e557c8b9f9ed0a87f61f1c9a44bde731c409', 'XAUTHORITY': '/run/user/1000/.mutter-Xwaylandauth.24AUM3', 'NoDefaultCurrentDirectoryInExePath': '1', 'IM_CONFIG_CHECK_ENV': '1', 'GJS_DEBUG_TOPICS': 'JS ERROR;JS LOG', 'CLAUDECODE': '1', 'HOME': '/home/seli', 'USERNAME': 'seli', 'CLAUDE_AGENT_SDK_VERSION': '0.2.123', 'IM_CONFIG_PHASE': '1', 'LANG': 'en_US.UTF-8', 'LS_COLORS': 'rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.swp=00;90:*.tmp=00;90:*.dpkg-dist=00;90:*.dpkg-old=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:', 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME', 'VSCODE_DOTNET_INSTALL_TOOL_ORIGINAL_HOME': '/home/seli', 'VIRTUAL_ENV': '/home/seli/docker-swarm-stacks/.venv', 'MEMORY_PRESSURE_WATCH': '/sys/fs/cgroup/user.slice/user-1000.slice/user@1000.service/session.slice/org.gnome.Shell@wayland.service/memory.pressure', 'VSCODE_IPC_HOOK': '/run/user/1000/vscode-58cce40e-1.11-main.sock', 'WAYLAND_DISPLAY': 'wayland-0', 'VSCODE_L10N_BUNDLE_LOCATION': '', 'INVOCATION_ID': 'b5cdc512716f4a58a458467da4b54ecc', 'MANAGERPID': '31372', 'CHROME_DESKTOP': 'code.desktop', 'GJS_DEBUG_OUTPUT': 'stderr', 'GNOME_SETUP_DISPLAY': ':1', 'LESSCLOSE': '/usr/bin/lesspipe %s %s', 'XDG_SESSION_CLASS': 'user', 'COPILOT_OTEL_ENABLED': 'true', 'LESSOPEN': '\| /usr/bin/lesspipe %s', 'USER': 'seli', 'DISPLAY': ':0', 'VSCODE_PID': '554786', 'SHLVL': '2', 'GIT_EDITOR': 'true', 'QT_IM_MODULE': 'ibus', 'APPLICATIONINSIGHTS_CONFIGURATION_CONTENT': '{}', 'VSCODE_CWD': '/home/seli', 'OTEL_EXPORTER_OTLP_METRICS_TEMPORALITY_PREFERENCE': 'delta', 'FC_FONTATIONS': '1', 'VSCODE_CRASH_REPORTER_PROCESS_TYPE': 'extensionHost', 'XDG_RUNTIME_DIR': '/run/user/1000', 'CLAUDE_CODE_ENTRYPOINT': 'claude-vscode', 'DEBUGINFOD_URLS': 'https://debuginfod.ubuntu.com ', 'OTEL_INSTRUMENTATION_GENAI_CAPTURE_MESSAGE_CONTENT': 'true', 'MCP_CONNECTION_NONBLOCKING': 'true', 'JOURNAL_STREAM': '9:114118', 'XDG_DATA_DIRS': '/usr/share/ubuntu:/usr/share/gnome:/usr/local/share/:/usr/share/:/var/lib/snapd/desktop', 'GDK_BACKEND': 'wayland', 'CLAUDE_CODE_EXECPATH': '/home/seli/.vscode/extensions/anthropic.claude-code-2.1.123-linux-x64/resources/native-binary/claude', 'PATH': '/home/seli/docker-swarm-stacks/.venv/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/home/seli/.npm-global/bin:/home/seli/.local/bin:/home/seli/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/snap/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin:/home/seli/.local/bin', 'GDMSESSION': 'ubuntu', 'APPLICATION_INSIGHTS_NO_STATSBEAT': 'true', 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus', 'VSCODE_NLS_CONFIG': '{"userLocale":"en-us","osLocale":"en-us","resolvedLanguage":"en","defaultMessagesFile":"/usr/share/code/resources/app/out/nls.messages.json","locale":"en-us","availableLanguages":{}}', 'GIO_LAUNCHED_DESKTOP_FILE_PID': '554786', 'GIO_LAUNCHED_DESKTOP_FILE': '/home/seli/.local/share/applications/code.desktop', 'VSCODE_HANDLES_UNCAUGHT_ERRORS': 'true', 'OLDPWD': '/tmp/js-extract-test', 'COPILOT_OTEL_EXPORTER_TYPE': 'file', '_': '/home/seli/docker-swarm-stacks/.venv/bin/python'})` | pos/kw |

**Returns:** `int`

### `try_repo`

```python
pre_commit.commands.try_repo.try_repo(args: 'argparse.Namespace') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `argparse.Namespace` | `—` | pos/kw |

**Returns:** `int`

### `xargs`

A simplified implementation of xargs.

color: Make a pty if on a platform that supports it
target_concurrency: Target number of partitions to run concurrently

```python
pre_commit.commands.try_repo.xargs(cmd: 'tuple[str, ...]', varargs: 'Sequence[str]', *, color: 'bool' = False, target_concurrency: 'int' = 1, _max_length: 'int' = 131072, **kwargs: 'Any') -> 'tuple[int, bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `tuple[str, ...]` | `—` | pos/kw |
| `varargs` | `Sequence[str]` | `—` | pos/kw |
| `color` | `bool` | `False` | kw |
| `target_concurrency` | `int` | `1` | kw |
| `_max_length` | `int` | `131072` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, bytes]`

### `yaml_dump`

```python
pre_commit.commands.try_repo.yaml_dump(o: 'Any', **kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `o` | `Any` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `validate_config`

```python
pre_commit.commands.validate_config.validate_config(filenames: 'Sequence[str]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filenames` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `int`

### `validate_manifest`

```python
pre_commit.commands.validate_manifest.validate_manifest(filenames: 'Sequence[str]') -> 'int'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filenames` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `int`

### `envcontext`

In this context, `os.environ` is modified according to `patch`.

`patch` is an iterable of 2-tuples (key, value):
    `key`: string
    `value`:
        - string: `environ[key] == value` inside the c…

```python
pre_commit.envcontext.envcontext(patch: 'PatchesT', _env: 'MutableMapping[str, str] | None' = None) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `patch` | `PatchesT` | `—` | pos/kw |
| `_env` | `MutableMapping[str, str] \| None` | `None` | pos/kw |

**Returns:** `Generator[None]`

### `format_env`

```python
pre_commit.envcontext.format_env(parts: 'SubstitutionT', env: 'MutableMapping[str, str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parts` | `SubstitutionT` | `—` | pos/kw |
| `env` | `MutableMapping[str, str]` | `—` | pos/kw |

**Returns:** `str`

### `cmd_output_b`

```python
pre_commit.error_handler.cmd_output_b(*cmd: 'str', check: 'bool' = True, **kwargs: 'Any') -> 'tuple[int, bytes, bytes | None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | *args |
| `check` | `bool` | `True` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `tuple[int, bytes, bytes | None]`

### `error_handler`

```python
pre_commit.error_handler.error_handler() -> 'Generator[None]'
```

**Returns:** `Generator[None]`

### `force_bytes`

```python
pre_commit.error_handler.force_bytes(exc: 'Any') -> 'bytes'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exc` | `Any` | `—` | pos/kw |

**Returns:** `bytes`

## Methods

### `pre_commit.all_languages.Language` methods

### `get_default_version`

```python
pre_commit.all_languages.Language.get_default_version(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `health_check`

```python
pre_commit.all_languages.Language.health_check(self, prefix: 'Prefix', version: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `prefix` | `Prefix` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `in_env`

```python
pre_commit.all_languages.Language.in_env(self, prefix: 'Prefix', version: 'str') -> 'ContextManager[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `prefix` | `Prefix` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

**Returns:** `ContextManager[None]`

### `install_environment`

```python
pre_commit.all_languages.Language.install_environment(self, prefix: 'Prefix', version: 'str', additional_dependencies: 'Sequence[str]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `prefix` | `Prefix` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |
| `additional_dependencies` | `Sequence[str]` | `—` | pos/kw |

### `run_hook`

```python
pre_commit.all_languages.Language.run_hook(self, prefix: 'Prefix', entry: 'str', args: 'Sequence[str]', file_args: 'Sequence[str]', *, is_local: 'bool', require_serial: 'bool', color: 'bool') -> 'tuple[int, bytes]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `prefix` | `Prefix` | `—` | pos/kw |
| `entry` | `str` | `—` | pos/kw |
| `args` | `Sequence[str]` | `—` | pos/kw |
| `file_args` | `Sequence[str]` | `—` | pos/kw |
| `is_local` | `bool` | `—` | kw |
| `require_serial` | `bool` | `—` | kw |
| `color` | `bool` | `—` | kw |

**Returns:** `tuple[int, bytes]`

### `pre_commit.clientlib.DeprecatedDefaultStagesWarning` methods

### `apply_default`

```python
pre_commit.clientlib.DeprecatedDefaultStagesWarning.apply_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.DeprecatedDefaultStagesWarning.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.DeprecatedDefaultStagesWarning.remove_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `pre_commit.clientlib.DeprecatedStagesWarning` methods

### `apply_default`

```python
pre_commit.clientlib.DeprecatedStagesWarning.apply_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.DeprecatedStagesWarning.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.DeprecatedStagesWarning.remove_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `pre_commit.clientlib.LanguageMigration` methods

### `apply_default`

```python
pre_commit.clientlib.LanguageMigration.apply_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.LanguageMigration.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.LanguageMigration.remove_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `pre_commit.clientlib.LanguageMigrationRequired` methods

### `apply_default`

```python
pre_commit.clientlib.LanguageMigrationRequired.apply_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.LanguageMigrationRequired.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.LanguageMigrationRequired.remove_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `pre_commit.clientlib.NotAllowed` methods

### `apply_default`

```python
pre_commit.clientlib.NotAllowed.apply_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.NotAllowed.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.NotAllowed.remove_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `pre_commit.clientlib.OptionalSensibleRegexAtHook` methods

### `apply_default`

```python
pre_commit.clientlib.OptionalSensibleRegexAtHook.apply_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.OptionalSensibleRegexAtHook.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.OptionalSensibleRegexAtHook.remove_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `pre_commit.clientlib.OptionalSensibleRegexAtTop` methods

### `apply_default`

```python
pre_commit.clientlib.OptionalSensibleRegexAtTop.apply_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.OptionalSensibleRegexAtTop.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.OptionalSensibleRegexAtTop.remove_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `pre_commit.clientlib.StagesMigration` methods

### `apply_default`

```python
pre_commit.clientlib.StagesMigration.apply_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.StagesMigration.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.StagesMigration.remove_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `pre_commit.clientlib.StagesMigrationNoDefault` methods

### `apply_default`

```python
pre_commit.clientlib.StagesMigrationNoDefault.apply_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.StagesMigrationNoDefault.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.StagesMigrationNoDefault.remove_default(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `pre_commit.clientlib.WarnMutableRev` methods

### `apply_default`

```python
pre_commit.clientlib.WarnMutableRev.apply_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `check`

```python
pre_commit.clientlib.WarnMutableRev.check(self, dct: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

### `remove_default`

```python
pre_commit.clientlib.WarnMutableRev.remove_default(self, dct)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `dct` | `—` | `—` | pos/kw |

### `pre_commit.commands.autoupdate.RevInfo` methods

### `from_config`

```python
pre_commit.commands.autoupdate.RevInfo.from_config(config: 'dict[str, Any]') -> 'RevInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `RevInfo`

### `update`

```python
pre_commit.commands.autoupdate.RevInfo.update(self, tags_only: 'bool', freeze: 'bool') -> 'RevInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags_only` | `bool` | `—` | pos/kw |
| `freeze` | `bool` | `—` | pos/kw |

**Returns:** `RevInfo`

### `pre_commit.commands.clean.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.clean.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.clean.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.clean.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.clean.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.clean.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.clean.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.clean.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.commands.gc.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.gc.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.gc.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.gc.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.gc.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.gc.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.gc.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.gc.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.commands.hook_impl.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.hook_impl.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.hook_impl.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.hook_impl.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.hook_impl.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.hook_impl.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.hook_impl.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.hook_impl.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.commands.init_templatedir.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.init_templatedir.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.init_templatedir.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.init_templatedir.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.init_templatedir.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.init_templatedir.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.init_templatedir.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.init_templatedir.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.commands.install_uninstall.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.install_uninstall.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.install_uninstall.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.install_uninstall.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.install_uninstall.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.install_uninstall.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.install_uninstall.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.install_uninstall.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.commands.migrate_config.MappingKey` methods

### `match`

```python
pre_commit.commands.migrate_config.MappingKey.match(self, n: 'Node') -> 'Generator[Node]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `n` | `Node` | `—` | pos/kw |

**Returns:** `Generator[Node]`

### `pre_commit.commands.migrate_config.MappingValue` methods

### `match`

```python
pre_commit.commands.migrate_config.MappingValue.match(self, n: 'Node') -> 'Generator[Node]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `n` | `Node` | `—` | pos/kw |

**Returns:** `Generator[Node]`

### `pre_commit.commands.migrate_config.SequenceItem` methods

### `match`

```python
pre_commit.commands.migrate_config.SequenceItem.match(self, n: 'Node') -> 'Generator[Node]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `n` | `Node` | `—` | pos/kw |

**Returns:** `Generator[Node]`

### `pre_commit.commands.run.Classifier` methods

### `by_types`

```python
pre_commit.commands.run.Classifier.by_types(self, names: 'Iterable[str]', types: 'Iterable[str]', types_or: 'Iterable[str]', exclude_types: 'Iterable[str]') -> 'Generator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `names` | `Iterable[str]` | `—` | pos/kw |
| `types` | `Iterable[str]` | `—` | pos/kw |
| `types_or` | `Iterable[str]` | `—` | pos/kw |
| `exclude_types` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `Generator[str]`

### `filenames_for_hook`

```python
pre_commit.commands.run.Classifier.filenames_for_hook(self, hook: 'Hook') -> 'Generator[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `hook` | `Hook` | `—` | pos/kw |

**Returns:** `Generator[str]`

### `from_config`

```python
pre_commit.commands.run.Classifier.from_config(filenames: 'Iterable[str]', include: 'str', exclude: 'str') -> 'Classifier'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filenames` | `Iterable[str]` | `—` | pos/kw |
| `include` | `str` | `—` | pos/kw |
| `exclude` | `str` | `—` | pos/kw |

**Returns:** `Classifier`

### `pre_commit.commands.run.Hook` methods

### `create`

```python
pre_commit.commands.run.Hook.create(src: 'str', prefix: 'Prefix', dct: 'dict[str, Any]') -> 'Hook'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `src` | `str` | `—` | pos/kw |
| `prefix` | `Prefix` | `—` | pos/kw |
| `dct` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `Hook`

### `pre_commit.commands.run.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.run.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.run.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.run.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.run.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.run.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.run.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.run.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.commands.try_repo.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.commands.try_repo.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.commands.try_repo.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.commands.try_repo.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.commands.try_repo.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.commands.try_repo.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.commands.try_repo.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.commands.try_repo.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

### `pre_commit.error_handler.Store` methods

### `clone`

Clone the given url and checkout the specific ref.

```python
pre_commit.error_handler.Store.clone(self, repo: 'str', ref: 'str', deps: 'Sequence[str]' = ()) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `repo` | `str` | `—` | pos/kw |
| `ref` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `()` | pos/kw |

**Returns:** `str`

### `connect`

```python
pre_commit.error_handler.Store.connect(self, db_path: 'str | None' = None) -> 'Generator[sqlite3.Connection]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `db_path` | `str \| None` | `None` | pos/kw |

**Returns:** `Generator[sqlite3.Connection]`

### `db_repo_name`

```python
pre_commit.error_handler.Store.db_repo_name(repo: 'str', deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `str` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `exclusive_lock`

```python
pre_commit.error_handler.Store.exclusive_lock(self) -> 'Generator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `Generator[None]`

### `get_default_directory`

Returns the default directory for the Store.  This is intentionally
underscored to indicate that `Store.get_default_directory` is the intended
way to get this information.  This is also done so
`Stor…

```python
pre_commit.error_handler.Store.get_default_directory() -> 'str'
```

**Returns:** `str`

### `make_local`

```python
pre_commit.error_handler.Store.make_local(self, deps: 'Sequence[str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `deps` | `Sequence[str]` | `—` | pos/kw |

**Returns:** `str`

### `mark_config_used`

```python
pre_commit.error_handler.Store.mark_config_used(self, path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |


---
name: package
description: "Ansible community package guide for Python-based automation with inventories, playbooks, collections, and vault"
metadata:
  languages: "python"
  versions: "13.4.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "ansible,python,automation,devops,playbooks,inventory,ssh,vault,yaml,Version-Sensitive,ini,AnsibleCollectionConfig,AnsibleError,CLI,ask_passwords,build_vault_ids,cli_executor,get_host_list,get_password_from_file,init_parser,pager,pager_pipe,parse,post_process_args,run,setup_vault_secrets,show_devel_warning,split_vault_id,validate_conflicts,version_info,DataLoader,cleanup_all_tmp_files,cleanup_tmp_file,find_vars_files,get_basedir,get_real_file,get_text_file_contents,is_directory,is_executable,is_file,list_directory,load,load_from_file,path_dwim,path_dwim_relative,path_dwim_relative_stack,path_exists,set_basedir,set_vault_secrets,Display,banner,banner_cowsay,debug,deprecated,display,do_var_prompt,error,error_as_warning,get_deprecation_message,prompt,prompt_until,set_cowsay_info,set_queue,system_warning,v,verbose,vv,vvv,vvvv,vvvvv,vvvvvv,warning,ExitCode,InventoryManager,add_dynamic_group,add_dynamic_host,add_group,add_host,clear_caches,clear_pattern_cache,get_groups_dict,get_host,get_hosts,list_groups,list_hosts,parse_source,parse_sources,reconcile_inventory,refresh_inventory,remove_restriction,restrict_to_hosts,subset,PromptVaultSecret,ask_vault_passwords,confirm,VariableManager,clear_facts,get_delegated_vars_and_hostname,get_vars,set_host_facts,set_host_variable,set_inventory,set_nonpersistent_facts,VaultSecretsContext,current,initialize,add_all_plugin_dirs,check_blocking_io,get_file_vault_secret,init_plugin_loader,initialize_locale,is_sequence,to_bytes,to_text,unfrackpath,AdHocCLI,AnsibleEndPlay,AnsibleOptionsError,AnsibleParserError,Origin,first_tagged_on,get_or_create_tag,get_required_tag,get_tag,is_tagged_on,replace,tag,try_tag,untag,Play,compile,compile_roles_handlers,copy,dump_attrs,dump_me,evaluate_tags,from_attrs,get_dep_chain,get_ds,get_handlers,get_loader,get_name,get_path,get_roles,get_search_path,get_tasks,get_validated_value,get_variable_manager,get_vars_files,load_data"
---

# ansible — package

## Install

```bash
pip install ansible
```

## Imports

```python
import ansible
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `AnsibleCollectionConfig` | Class |  |
| `AnsibleError` | Class | This is the base class for all errors raised from Ansible code, and can be inst… |
| `CLI` | Class | code behind bin/ansible* programs |
| `ask_passwords` | Method | prompt for connection and become passwords if needed |
| `build_vault_ids` | Method |  |
| `cli_executor` | Method |  |
| `get_host_list` | Method |  |
| `get_password_from_file` | Method |  |
| `init_parser` | Method | Create an options parser for most ansible scripts  Subclasses need to implement… |
| `pager` | Method | find reasonable way to display text |
| `pager_pipe` | Method | pipe text through a pager |
| `parse` | Method | Parse the command line args  This method parses the command line arguments.  It… |
| `post_process_args` | Method | Process the command line args  Subclasses need to implement this method.  This… |
| `run` | Method | Run the ansible command  Subclasses must implement this method.  It does the ac… |
| `setup_vault_secrets` | Method |  |
| `show_devel_warning` | Method |  |
| `split_vault_id` | Method |  |
| `validate_conflicts` | Method | check for conflicting options |
| `version_info` | Method | return full ansible version info |
| `DataLoader` | Class | The DataLoader class is used to load and parse YAML or JSON content, either fro… |
| `cleanup_all_tmp_files` | Method | Removes all temporary files that DataLoader has created NOTE: not thread safe,… |
| `cleanup_tmp_file` | Method | Removes any temporary files created from a previous call to get_real_file. file… |
| `find_vars_files` | Method | Find vars files in a given path with specified name. This will find files in a… |
| `get_basedir` | Method | returns the current basedir |
| `get_real_file` | Method | If the file is vault encrypted return a path to a temporary decrypted file If t… |
| `get_text_file_contents` | Method | Returns an `Origin` tagged string with the content of the specified (DWIM-expan… |
| `is_directory` | Method |  |
| `is_executable` | Method | is the given path executable? |
| `is_file` | Method |  |
| `list_directory` | Method |  |
| `load` | Method | Backwards compat for now |
| `load_from_file` | Method | Loads data from a file, which can contain either JSON or YAML.  :param file_nam… |
| `path_dwim` | Method | make relative paths work like folks expect. |
| `path_dwim_relative` | Method | find one file in either a role or playbook dir with or without explicitly named… |
| `path_dwim_relative_stack` | Method | find one file in first path in stack taking roles into account and adding play… |
| `path_exists` | Method |  |
| `set_basedir` | Method | sets the base directory, used to find files when a relative path is given |
| `set_vault_secrets` | Method |  |
| `Display` | Class |  |
| `banner` | Method | Prints a header-looking line with cowsay or stars with length depending on term… |
| `banner_cowsay` | Method |  |
| `debug` | Method |  |
| `deprecated` | Method | Display a deprecation warning message, if enabled. Most callers do not need to… |
| `display` | Method | Display a message to the user  Note: msg *must* be a unicode string to prevent… |
| `do_var_prompt` | Method |  |
| `error` | Method | Display an error message. |
| `error_as_warning` | Method | Display an exception as a warning. |
| `get_deprecation_message` | Method | Return a deprecation message and help text for non-display purposes (e.g., exce… |
| `prompt` | Method |  |
| `prompt_until` | Method |  |
| `set_cowsay_info` | Method |  |
| `set_queue` | Method | Set the _final_q on Display, so that we know to proxy display over the queue in… |
| `system_warning` | Method |  |
| `v` | Method |  |
| `verbose` | Method |  |
| `vv` | Method |  |
| `vvv` | Method |  |
| `vvvv` | Method |  |
| `vvvvv` | Method |  |
| `vvvvvv` | Method |  |
| `warning` | Method | Display a warning message. |
| `ExitCode` | Class | Enum where members are also (and must be) ints |
| `InventoryManager` | Class | Creates and manages inventory |
| `add_dynamic_group` | Method | Helper function to add a group (if it does not exist), and to assign the specif… |
| `add_dynamic_host` | Method | Helper function to add a new host to inventory based on a task result. |
| `add_group` | Method |  |
| `add_host` | Method |  |
| `clear_caches` | Method | clear all caches |
| `clear_pattern_cache` | Method |  |
| `get_groups_dict` | Method |  |
| `get_host` | Method |  |
| `get_hosts` | Method | Takes a pattern or list of patterns and returns a list of matching inventory ho… |
| `list_groups` | Method |  |
| `list_hosts` | Method | return a list of hostnames for a pattern |
| `parse_source` | Method | Generate or update inventory for the source provided |
| `parse_sources` | Method | iterate over inventory sources and parse each one to populate it |
| `reconcile_inventory` | Method |  |
| `refresh_inventory` | Method | recalculate inventory |
| `remove_restriction` | Method | Do not restrict list operations |
| `restrict_to_hosts` | Method | Restrict list operations to the hosts given in restriction.  This is used to ba… |
| `subset` | Method | Limits inventory results to a subset of inventory that matches a given pattern,… |
| `PromptVaultSecret` | Class | Opaque/abstract objects for a single vault secret. ie, a password or a key. |
| `ask_vault_passwords` | Method |  |
| `confirm` | Method |  |
| `load` | Method |  |
| `VariableManager` | Class |  |
| `clear_facts` | Method | Clears the facts for a host |
| `get_delegated_vars_and_hostname` | Method | Get the delegated_vars for an individual task invocation, which may be in the c… |
| `get_vars` | Method | Returns the variables, with optional "context" given via the parameters for the… |
| `set_host_facts` | Method | Sets or updates the given facts for a host in the fact cache. |
| `set_host_variable` | Method | Sets a value in the vars_cache for a host. |
| `set_inventory` | Method |  |
| `set_nonpersistent_facts` | Method | Sets or updates the given facts for a host in the fact cache. |
| `VaultSecretsContext` | Class | Provides context-style access to vault secrets. |
| `current` | Method | Access vault secrets, if initialized, ala `AmbientContextBase.current()`. |
| `initialize` | Method | Initialize VaultSecretsContext with the specified instance and secrets (since i… |
| `add_all_plugin_dirs` | Function | add any existing plugin dirs in the path provided |
| `check_blocking_io` | Function | Check stdin/stdout/stderr to make sure they are using blocking IO. |
| `get_file_vault_secret` | Function | Get secret from file content or execute file and get secret from stdout |
| `init_plugin_loader` | Function | Initialize the plugin filters and the collection loaders  This method must be c… |
| `initialize_locale` | Function | Set the locale to the users default setting and ensure the locale and filesyste… |
| `is_executable` | Function | is_executable(path)  is the given path executable?  :arg path: The path of the… |
| `is_sequence` | Function | Identify whether the input is a sequence.  Strings and bytes are not sequences… |
| `to_bytes` | Function | Make sure that a string is a byte string  :arg obj: An object to make sure is a… |
| `to_text` | Function | Make sure that a string is a text string  :arg obj: An object to make sure is a… |
| `unfrackpath` | Function | Returns a path that is free of symlinks (if follow=True), environment variables… |
| `AdHocCLI` | Class | is an extra-simple tool/framework/API for doing 'remote things'. this command a… |
| `ask_passwords` | Method | prompt for connection and become passwords if needed |
| `build_vault_ids` | Method |  |
| `cli_executor` | Method |  |
| `get_host_list` | Method |  |
| `get_password_from_file` | Method |  |
| `init_parser` | Method | create an options parser for bin/ansible |
| `pager` | Method | find reasonable way to display text |
| `pager_pipe` | Method | pipe text through a pager |
| `parse` | Method | Parse the command line args  This method parses the command line arguments.  It… |
| `post_process_args` | Method | Post process and validate options for bin/ansible |
| `run` | Method | create and execute the single task playbook |
| `setup_vault_secrets` | Method |  |
| `show_devel_warning` | Method |  |
| `split_vault_id` | Method |  |
| `validate_conflicts` | Method | check for conflicting options |
| `version_info` | Method | return full ansible version info |
| `AnsibleEndPlay` | Class | Common base class for all non-exit exceptions. |
| `AnsibleError` | Class | This is the base class for all errors raised from Ansible code, and can be inst… |
| `AnsibleOptionsError` | Class | Invalid options were passed. |
| `AnsibleParserError` | Class | A playbook or data file could not be parsed. |
| `CLI` | Class | code behind bin/ansible* programs |
| `ask_passwords` | Method | prompt for connection and become passwords if needed |
| `build_vault_ids` | Method |  |
| `cli_executor` | Method |  |
| `get_host_list` | Method |  |
| `get_password_from_file` | Method |  |
| `init_parser` | Method | Create an options parser for most ansible scripts  Subclasses need to implement… |
| `pager` | Method | find reasonable way to display text |
| `pager_pipe` | Method | pipe text through a pager |
| `parse` | Method | Parse the command line args  This method parses the command line arguments.  It… |
| `post_process_args` | Method | Process the command line args  Subclasses need to implement this method.  This… |
| `run` | Method | Run the ansible command  Subclasses must implement this method.  It does the ac… |
| `setup_vault_secrets` | Method |  |
| `show_devel_warning` | Method |  |
| `split_vault_id` | Method |  |
| `validate_conflicts` | Method | check for conflicting options |
| `version_info` | Method | return full ansible version info |
| `Display` | Class |  |
| `banner` | Method | Prints a header-looking line with cowsay or stars with length depending on term… |
| `banner_cowsay` | Method |  |
| `debug` | Method |  |
| `deprecated` | Method | Display a deprecation warning message, if enabled. Most callers do not need to… |
| `display` | Method | Display a message to the user  Note: msg *must* be a unicode string to prevent… |
| `do_var_prompt` | Method |  |
| `error` | Method | Display an error message. |
| `error_as_warning` | Method | Display an exception as a warning. |
| `get_deprecation_message` | Method | Return a deprecation message and help text for non-display purposes (e.g., exce… |
| `prompt` | Method |  |
| `prompt_until` | Method |  |
| `set_cowsay_info` | Method |  |
| `set_queue` | Method | Set the _final_q on Display, so that we know to proxy display over the queue in… |
| `system_warning` | Method |  |
| `v` | Method |  |
| `verbose` | Method |  |
| `vv` | Method |  |
| `vvv` | Method |  |
| `vvvv` | Method |  |
| `vvvvv` | Method |  |
| `vvvvvv` | Method |  |
| `warning` | Method | Display a warning message. |
| `Origin` | Class | A tag that stores origin metadata for a tagged value, intended for forensic/dia… |
| `first_tagged_on` | Method | Return the first value which is tagged with this type, or None if no match is f… |
| `get_or_create_tag` | Method | Return the tag from the given value, creating a tag from the provided path if n… |
| `get_required_tag` | Method |  |
| `get_tag` | Method |  |
| `is_tagged_on` | Method |  |
| `replace` | Method | Return a new origin based on an existing one, with the given fields replaced. |
| `tag` | Method | Return a copy of `value` with this tag applied, overwriting any existing tag of… |
| `try_tag` | Method | Return a copy of `value` with this tag applied, overwriting any existing tag of… |
| `untag` | Method | If this tag type is present on `value`, return a copy with that tag removed. Ot… |
| `Play` | Class | A play is a language feature that represents a list of roles and/or task/handle… |
| `compile` | Method | Compiles and returns the task list for this play, compiled from the roles (whic… |
| `compile_roles_handlers` | Method | Handles the role handler compilation step, returning a flat list of Handlers Th… |
| `copy` | Method | Create a copy of this object and return it. |
| `dump_attrs` | Method | Dumps all attributes to a dictionary |
| `dump_me` | Method | this is never called from production code, it is here to be used when debugging… |
| `evaluate_tags` | Method | Check if the current item should be executed depending on the specified tags.… |
| `from_attrs` | Method | Loads attributes from a dictionary |
| `get_dep_chain` | Method |  |
| `get_ds` | Method |  |
| `get_handlers` | Method |  |
| `get_loader` | Method |  |
| `get_name` | Method | return the name of the Play |
| `get_path` | Method | return the absolute path of the playbook object and its line number |
| `get_roles` | Method |  |
| `get_search_path` | Method | Return the list of paths you should search for files, in order. This follows ro… |
| `get_tasks` | Method |  |
| `get_validated_value` | Method |  |
| `get_variable_manager` | Method |  |
| `get_vars` | Method |  |
| `get_vars_files` | Method |  |
| `load` | Method |  |
| `load_data` | Method | walk the input datastructure and assign any values |

## Classes

### `AnsibleCollectionConfig`

```python
ansible.cli.AnsibleCollectionConfig(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `AnsibleError`

This is the base class for all errors raised from Ansible code,
and can be instantiated with two optional parameters beyond the
error message to control whether detailed information is displayed
when…

```python
ansible.cli.AnsibleError(self, message: 'str' = '', obj: 't.Any' = None, show_content: 'bool' = True, suppress_extended_error: 'bool | types.EllipsisType' = Ellipsis, orig_exc: 'BaseException | None' = None, help_text: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `''` | pos/kw |
| `obj` | `t.Any` | `None` | pos/kw |
| `show_content` | `bool` | `True` | pos/kw |
| `suppress_extended_error` | `bool \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `orig_exc` | `BaseException \| None` | `None` | pos/kw |
| `help_text` | `str \| None` | `None` | pos/kw |

### `CLI`

code behind bin/ansible* programs

```python
ansible.cli.CLI(self, args, callback=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |
| `callback` | `—` | `None` | pos/kw |

### `DataLoader`

The DataLoader class is used to load and parse YAML or JSON content,
either from a given file name or from a string that was previously
read in through other means. A Vault password can be specified,…

```python
ansible.cli.DataLoader(self) -> 'None'
```

### `Display`

```python
ansible.cli.Display(self, verbosity: 'int' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `verbosity` | `int` | `0` | pos/kw |

### `ExitCode`

Enum where members are also (and must be) ints

```python
ansible.cli.ExitCode(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `InventoryManager`

Creates and manages inventory

```python
ansible.cli.InventoryManager(self, loader, sources=None, parse=True, cache=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loader` | `—` | `—` | pos/kw |
| `sources` | `—` | `None` | pos/kw |
| `parse` | `—` | `True` | pos/kw |
| `cache` | `—` | `True` | pos/kw |

### `PromptVaultSecret`

Opaque/abstract objects for a single vault secret. ie, a password or a key.

```python
ansible.cli.PromptVaultSecret(self, _bytes=None, vault_id=None, prompt_formats=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_bytes` | `—` | `None` | pos/kw |
| `vault_id` | `—` | `None` | pos/kw |
| `prompt_formats` | `—` | `None` | pos/kw |

### `VariableManager`

```python
ansible.cli.VariableManager(self, loader: 'DataLoader | None' = None, inventory: 'InventoryManager | None' = None, version_info: 'dict[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loader` | `DataLoader \| None` | `None` | pos/kw |
| `inventory` | `InventoryManager \| None` | `None` | pos/kw |
| `version_info` | `dict[str, str] \| None` | `None` | pos/kw |

### `VaultSecretsContext`

Provides context-style access to vault secrets.

```python
ansible.cli.VaultSecretsContext(self, secrets: 'list[tuple[str, VaultSecret]]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `secrets` | `list[tuple[str, VaultSecret]]` | `—` | pos/kw |

### `AdHocCLI`

is an extra-simple tool/framework/API for doing 'remote things'.
this command allows you to define and run a single task 'playbook' against a set of hosts

```python
ansible.cli.adhoc.AdHocCLI(self, args, callback=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |
| `callback` | `—` | `None` | pos/kw |

### `AnsibleEndPlay`

Common base class for all non-exit exceptions.

```python
ansible.cli.adhoc.AnsibleEndPlay(self, result)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `result` | `—` | `—` | pos/kw |

### `AnsibleError`

This is the base class for all errors raised from Ansible code,
and can be instantiated with two optional parameters beyond the
error message to control whether detailed information is displayed
when…

```python
ansible.cli.adhoc.AnsibleError(self, message: 'str' = '', obj: 't.Any' = None, show_content: 'bool' = True, suppress_extended_error: 'bool | types.EllipsisType' = Ellipsis, orig_exc: 'BaseException | None' = None, help_text: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `''` | pos/kw |
| `obj` | `t.Any` | `None` | pos/kw |
| `show_content` | `bool` | `True` | pos/kw |
| `suppress_extended_error` | `bool \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `orig_exc` | `BaseException \| None` | `None` | pos/kw |
| `help_text` | `str \| None` | `None` | pos/kw |

### `AnsibleOptionsError`

Invalid options were passed.

```python
ansible.cli.adhoc.AnsibleOptionsError(self, message: 'str' = '', obj: 't.Any' = None, show_content: 'bool' = True, suppress_extended_error: 'bool | types.EllipsisType' = Ellipsis, orig_exc: 'BaseException | None' = None, help_text: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `''` | pos/kw |
| `obj` | `t.Any` | `None` | pos/kw |
| `show_content` | `bool` | `True` | pos/kw |
| `suppress_extended_error` | `bool \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `orig_exc` | `BaseException \| None` | `None` | pos/kw |
| `help_text` | `str \| None` | `None` | pos/kw |

### `AnsibleParserError`

A playbook or data file could not be parsed.

```python
ansible.cli.adhoc.AnsibleParserError(self, message: 'str' = '', obj: 't.Any' = None, show_content: 'bool' = True, suppress_extended_error: 'bool | types.EllipsisType' = Ellipsis, orig_exc: 'BaseException | None' = None, help_text: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `''` | pos/kw |
| `obj` | `t.Any` | `None` | pos/kw |
| `show_content` | `bool` | `True` | pos/kw |
| `suppress_extended_error` | `bool \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `orig_exc` | `BaseException \| None` | `None` | pos/kw |
| `help_text` | `str \| None` | `None` | pos/kw |

### `CLI`

code behind bin/ansible* programs

```python
ansible.cli.adhoc.CLI(self, args, callback=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | pos/kw |
| `callback` | `—` | `None` | pos/kw |

### `Display`

```python
ansible.cli.adhoc.Display(self, verbosity: 'int' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `verbosity` | `int` | `0` | pos/kw |

### `Origin`

A tag that stores origin metadata for a tagged value, intended for forensic/diagnostic use.
Origin metadata should not be used to make runtime decisions, as it is not guaranteed to be present or accu…

```python
ansible.cli.adhoc.Origin(self, *, path: 'str | None' = None, description: 'str | None' = None, line_num: 'int | None' = None, col_num: 'int | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str \| None` | `None` | kw |
| `description` | `str \| None` | `None` | kw |
| `line_num` | `int \| None` | `None` | kw |
| `col_num` | `int \| None` | `None` | kw |

### `Play`

A play is a language feature that represents a list of roles and/or
task/handler blocks to execute on a given set of hosts.

Usage:

   Play.load(datastructure) -> Play
   Play.something(...)

```python
ansible.cli.adhoc.Play(self)
```

## Functions

### `add_all_plugin_dirs`

add any existing plugin dirs in the path provided

```python
ansible.cli.add_all_plugin_dirs(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `check_blocking_io`

Check stdin/stdout/stderr to make sure they are using blocking IO.

```python
ansible.cli.check_blocking_io()
```

### `get_file_vault_secret`

Get secret from file content or execute file and get secret from stdout

```python
ansible.cli.get_file_vault_secret(filename=None, vault_id=None, encoding=None, loader=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `None` | pos/kw |
| `vault_id` | `—` | `None` | pos/kw |
| `encoding` | `—` | `None` | pos/kw |
| `loader` | `—` | `None` | pos/kw |

### `init_plugin_loader`

Initialize the plugin filters and the collection loaders

This method must be called to configure and insert the collection python loaders
into ``sys.meta_path`` and ``sys.path_hooks``.

This method…

```python
ansible.cli.init_plugin_loader(prefix_collections_path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prefix_collections_path` | `—` | `None` | pos/kw |

### `initialize_locale`

Set the locale to the users default setting and ensure
the locale and filesystem encoding are UTF-8.

```python
ansible.cli.initialize_locale()
```

### `is_executable`

is_executable(path)

is the given path executable?

:arg path: The path of the file to check.

Limitations:

* Does not account for FSACLs.
* Most times we really want to know "Can the current user e…

```python
ansible.cli.is_executable(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `is_sequence`

Identify whether the input is a sequence.

Strings and bytes are not sequences here,
unless ``include_string`` is ``True``.

Non-indexable things are never of a sequence type.

```python
ansible.cli.is_sequence(seq, include_strings=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `seq` | `—` | `—` | pos/kw |
| `include_strings` | `—` | `False` | pos/kw |

### `to_bytes`

Make sure that a string is a byte string

:arg obj: An object to make sure is a byte string.  In most cases this
    will be either a text string or a byte string.  However, with
    ``nonstring='sim…

```python
ansible.cli.to_bytes(obj: '_T', encoding: 'str' = 'utf-8', errors: 'str | None' = None, nonstring: '_NonStringAll' = 'simplerepr') -> '_T | bytes'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `_T` | `—` | pos/kw |
| `encoding` | `str` | `'utf-8'` | pos/kw |
| `errors` | `str \| None` | `None` | pos/kw |
| `nonstring` | `_NonStringAll` | `'simplerepr'` | pos/kw |

**Returns:** `_T | bytes`

### `to_text`

Make sure that a string is a text string

:arg obj: An object to make sure is a text string.  In most cases this
    will be either a text string or a byte string.  However, with
    ``nonstring='sim…

```python
ansible.cli.to_text(obj: '_T', encoding: 'str' = 'utf-8', errors: 'str | None' = None, nonstring: '_NonStringAll' = 'simplerepr') -> '_T | str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `_T` | `—` | pos/kw |
| `encoding` | `str` | `'utf-8'` | pos/kw |
| `errors` | `str \| None` | `None` | pos/kw |
| `nonstring` | `_NonStringAll` | `'simplerepr'` | pos/kw |

**Returns:** `_T | str`

### `unfrackpath`

Returns a path that is free of symlinks (if follow=True), environment variables, relative path traversals and symbols (~)

:arg path: A byte or text string representing a path to be canonicalized
:ar…

```python
ansible.cli.unfrackpath(path, follow=True, basedir=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |
| `follow` | `—` | `True` | pos/kw |
| `basedir` | `—` | `None` | pos/kw |

## Methods

### `ansible.cli.CLI` methods

### `ask_passwords`

prompt for connection and become passwords if needed

```python
ansible.cli.CLI.ask_passwords()
```

### `build_vault_ids`

```python
ansible.cli.CLI.build_vault_ids(vault_ids, vault_password_files=None, ask_vault_pass=None, auto_prompt=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vault_ids` | `—` | `—` | pos/kw |
| `vault_password_files` | `—` | `None` | pos/kw |
| `ask_vault_pass` | `—` | `None` | pos/kw |
| `auto_prompt` | `—` | `True` | pos/kw |

### `cli_executor`

```python
ansible.cli.CLI.cli_executor(args=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `None` | pos/kw |

### `get_host_list`

```python
ansible.cli.CLI.get_host_list(inventory, subset, pattern='all')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inventory` | `—` | `—` | pos/kw |
| `subset` | `—` | `—` | pos/kw |
| `pattern` | `—` | `'all'` | pos/kw |

### `get_password_from_file`

```python
ansible.cli.CLI.get_password_from_file(pwd_file: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pwd_file` | `str` | `—` | pos/kw |

**Returns:** `str`

### `init_parser`

Create an options parser for most ansible scripts

Subclasses need to implement this method.  They will usually call the base class's
init_parser to create a basic version and then add their own opti…

```python
ansible.cli.CLI.init_parser(self, desc=None, epilog=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `desc` | `—` | `None` | pos/kw |
| `epilog` | `—` | `None` | pos/kw |

### `pager`

find reasonable way to display text

```python
ansible.cli.CLI.pager(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `pager_pipe`

pipe text through a pager

```python
ansible.cli.CLI.pager_pipe(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `parse`

Parse the command line args

This method parses the command line arguments.  It uses the parser
stored in the self.parser attribute and saves the args and options in
context.CLIARGS.

Subclasses need…

```python
ansible.cli.CLI.parse(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `post_process_args`

Process the command line args

Subclasses need to implement this method.  This method validates and transforms the command
line arguments.  It can be used to check whether conflicting values were giv…

```python
ansible.cli.CLI.post_process_args(self, options)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |

### `run`

Run the ansible command

Subclasses must implement this method.  It does the actual work of
running an Ansible command.

```python
ansible.cli.CLI.run(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setup_vault_secrets`

```python
ansible.cli.CLI.setup_vault_secrets(loader, vault_ids, vault_password_files=None, ask_vault_pass=None, create_new_password=False, auto_prompt=True, initialize_context=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loader` | `—` | `—` | pos/kw |
| `vault_ids` | `—` | `—` | pos/kw |
| `vault_password_files` | `—` | `None` | pos/kw |
| `ask_vault_pass` | `—` | `None` | pos/kw |
| `create_new_password` | `—` | `False` | pos/kw |
| `auto_prompt` | `—` | `True` | pos/kw |
| `initialize_context` | `—` | `True` | pos/kw |

### `show_devel_warning`

```python
ansible.cli.CLI.show_devel_warning(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `split_vault_id`

```python
ansible.cli.CLI.split_vault_id(vault_id)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vault_id` | `—` | `—` | pos/kw |

### `validate_conflicts`

check for conflicting options

```python
ansible.cli.CLI.validate_conflicts(self, op, runas_opts=False, fork_opts=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `op` | `—` | `—` | pos/kw |
| `runas_opts` | `—` | `False` | pos/kw |
| `fork_opts` | `—` | `False` | pos/kw |

### `version_info`

return full ansible version info

```python
ansible.cli.CLI.version_info(gitinfo=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `gitinfo` | `—` | `False` | pos/kw |

### `ansible.cli.DataLoader` methods

### `cleanup_all_tmp_files`

Removes all temporary files that DataLoader has created
NOTE: not thread safe, forks also need special handling see __init__ for details.

```python
ansible.cli.DataLoader.cleanup_all_tmp_files(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `cleanup_tmp_file`

Removes any temporary files created from a previous call to
get_real_file. file_path must be the path returned from a
previous call to get_real_file.

```python
ansible.cli.DataLoader.cleanup_tmp_file(self, file_path: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file_path` | `str` | `—` | pos/kw |

### `find_vars_files`

Find vars files in a given path with specified name. This will find
files in a dir named <name>/ or a file called <name> ending in known
extensions.

```python
ansible.cli.DataLoader.find_vars_files(self, path: 'str', name: 'str', extensions: 'list[str] | None' = None, allow_dir: 'bool' = True) -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `extensions` | `list[str] \| None` | `None` | pos/kw |
| `allow_dir` | `bool` | `True` | pos/kw |

**Returns:** `list[str]`

### `get_basedir`

returns the current basedir

```python
ansible.cli.DataLoader.get_basedir(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_real_file`

If the file is vault encrypted return a path to a temporary decrypted file
If the file is not encrypted then the path is returned
Temporary files are cleanup in the destructor

```python
ansible.cli.DataLoader.get_real_file(self, file_path: 'str', decrypt: 'bool' = True) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file_path` | `str` | `—` | pos/kw |
| `decrypt` | `bool` | `True` | pos/kw |

**Returns:** `str`

### `get_text_file_contents`

Returns an `Origin` tagged string with the content of the specified (DWIM-expanded for relative) file path, decrypting if necessary.
Callers must only specify `encoding` when the user can configure i…

```python
ansible.cli.DataLoader.get_text_file_contents(self, file_name: 'str', encoding: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file_name` | `str` | `—` | pos/kw |
| `encoding` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `is_directory`

```python
ansible.cli.DataLoader.is_directory(self, path: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `is_executable`

is the given path executable?

```python
ansible.cli.DataLoader.is_executable(self, path: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `is_file`

```python
ansible.cli.DataLoader.is_file(self, path: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `list_directory`

```python
ansible.cli.DataLoader.list_directory(self, path: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `list[str]`

### `load`

Backwards compat for now

```python
ansible.cli.DataLoader.load(self, data: 'str', file_name: 'str | None' = None, show_content: 'bool' = True, json_only: 'bool' = False) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `str` | `—` | pos/kw |
| `file_name` | `str \| None` | `None` | pos/kw |
| `show_content` | `bool` | `True` | pos/kw |
| `json_only` | `bool` | `False` | pos/kw |

**Returns:** `t.Any`

### `load_from_file`

Loads data from a file, which can contain either JSON or YAML.

:param file_name: The name of the file to load data from.
:param cache: Options for caching: none|all|vaulted
:param unsafe: If True, r…

```python
ansible.cli.DataLoader.load_from_file(self, file_name: 'str', cache: 'str' = 'all', unsafe: 'bool' = False, json_only: 'bool' = False, trusted_as_template: 'bool' = False) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file_name` | `str` | `—` | pos/kw |
| `cache` | `str` | `'all'` | pos/kw |
| `unsafe` | `bool` | `False` | pos/kw |
| `json_only` | `bool` | `False` | pos/kw |
| `trusted_as_template` | `bool` | `False` | pos/kw |

**Returns:** `t.Any`

### `path_dwim`

make relative paths work like folks expect.

```python
ansible.cli.DataLoader.path_dwim(self, given: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `given` | `str` | `—` | pos/kw |

**Returns:** `str`

### `path_dwim_relative`

find one file in either a role or playbook dir with or without
explicitly named dirname subdirs

Used in action plugins and lookups to find supplemental files that
could be in either place.

```python
ansible.cli.DataLoader.path_dwim_relative(self, path: 'str', dirname: 'str', source: 'str', is_role: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |
| `dirname` | `str` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `is_role` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `path_dwim_relative_stack`

find one file in first path in stack taking roles into account and adding play basedir as fallback

:arg paths: A list of text strings which are the paths to look for the filename in.
:arg dirname: A…

```python
ansible.cli.DataLoader.path_dwim_relative_stack(self, paths: 'list[str]', dirname: 'str', source: 'str', is_role: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `paths` | `list[str]` | `—` | pos/kw |
| `dirname` | `str` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `is_role` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `path_exists`

```python
ansible.cli.DataLoader.path_exists(self, path: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `set_basedir`

sets the base directory, used to find files when a relative path is given

```python
ansible.cli.DataLoader.set_basedir(self, basedir: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `basedir` | `str` | `—` | pos/kw |

### `set_vault_secrets`

```python
ansible.cli.DataLoader.set_vault_secrets(self, vault_secrets: 'list[tuple[str, PromptVaultSecret]] | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `vault_secrets` | `list[tuple[str, PromptVaultSecret]] \| None` | `—` | pos/kw |

### `ansible.cli.Display` methods

### `banner`

Prints a header-looking line with cowsay or stars with length depending on terminal width (3 minimum)

```python
ansible.cli.Display.banner(self, msg: 'str', color: 'str | None' = None, cows: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |
| `cows` | `bool` | `True` | pos/kw |

### `banner_cowsay`

```python
ansible.cli.Display.banner_cowsay(self, msg: 'str', color: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |

### `debug`

```python
ansible.cli.Display.debug(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `deprecated`

Display a deprecation warning message, if enabled.
Most callers do not need to provide `collection_name` or `deprecator` -- but provide only one if needed.
Specify `version` or `date`, but not both.…

```python
ansible.cli.Display.deprecated(self, msg: 'str', version: 'str | None' = None, removed: 'bool' = False, date: 'str | None' = None, collection_name: 'str | None' = None, *, deprecator: '_messages.PluginInfo | None' = None, help_text: 'str | None' = None, obj: 't.Any' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `version` | `str \| None` | `None` | pos/kw |
| `removed` | `bool` | `False` | pos/kw |
| `date` | `str \| None` | `None` | pos/kw |
| `collection_name` | `str \| None` | `None` | pos/kw |
| `deprecator` | `_messages.PluginInfo \| None` | `None` | kw |
| `help_text` | `str \| None` | `None` | kw |
| `obj` | `t.Any` | `None` | kw |

### `display`

Display a message to the user

Note: msg *must* be a unicode string to prevent UnicodeError tracebacks.

```python
ansible.cli.Display.display(self, msg: 'str', color: 'str | None' = None, stderr: 'bool' = False, screen_only: 'bool' = False, log_only: 'bool' = False, newline: 'bool' = True, caplevel: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |
| `stderr` | `bool` | `False` | pos/kw |
| `screen_only` | `bool` | `False` | pos/kw |
| `log_only` | `bool` | `False` | pos/kw |
| `newline` | `bool` | `True` | pos/kw |
| `caplevel` | `int \| None` | `None` | pos/kw |

### `do_var_prompt`

```python
ansible.cli.Display.do_var_prompt(self, varname: 'str', private: 'bool' = True, prompt: 'str | None' = None, encrypt: 'str | None' = None, confirm: 'bool' = False, salt_size: 'int | None' = None, salt: 'str | None' = None, default: 'str | None' = None, unsafe: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `varname` | `str` | `—` | pos/kw |
| `private` | `bool` | `True` | pos/kw |
| `prompt` | `str \| None` | `None` | pos/kw |
| `encrypt` | `str \| None` | `None` | pos/kw |
| `confirm` | `bool` | `False` | pos/kw |
| `salt_size` | `int \| None` | `None` | pos/kw |
| `salt` | `str \| None` | `None` | pos/kw |
| `default` | `str \| None` | `None` | pos/kw |
| `unsafe` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `error`

Display an error message.

```python
ansible.cli.Display.error(self, msg: 'str | BaseException', wrap_text: 'bool' = True, stderr: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str \| BaseException` | `—` | pos/kw |
| `wrap_text` | `bool` | `True` | pos/kw |
| `stderr` | `bool` | `True` | pos/kw |

### `error_as_warning`

Display an exception as a warning.

```python
ansible.cli.Display.error_as_warning(self, msg: 'str | None', exception: 'BaseException', *, help_text: 'str | None' = None, obj: 't.Any' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str \| None` | `—` | pos/kw |
| `exception` | `BaseException` | `—` | pos/kw |
| `help_text` | `str \| None` | `None` | kw |
| `obj` | `t.Any` | `None` | kw |

### `get_deprecation_message`

Return a deprecation message and help text for non-display purposes (e.g., exception messages).

```python
ansible.cli.Display.get_deprecation_message(self, msg: 'str', version: 'str | None' = None, removed: 'bool' = False, date: 'str | None' = None, collection_name: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `version` | `str \| None` | `None` | pos/kw |
| `removed` | `bool` | `False` | pos/kw |
| `date` | `str \| None` | `None` | pos/kw |
| `collection_name` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `prompt`

```python
ansible.cli.Display.prompt(msg: 'str', private: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `msg` | `str` | `—` | pos/kw |
| `private` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `prompt_until`

```python
ansible.cli.Display.prompt_until(self, msg: 'str', private: 'bool' = False, seconds: 'int | None' = None, interrupt_input: 'c.Iterable[bytes] | None' = None, complete_input: 'c.Iterable[bytes] | None' = None) -> 'bytes'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `private` | `bool` | `False` | pos/kw |
| `seconds` | `int \| None` | `None` | pos/kw |
| `interrupt_input` | `c.Iterable[bytes] \| None` | `None` | pos/kw |
| `complete_input` | `c.Iterable[bytes] \| None` | `None` | pos/kw |

**Returns:** `bytes`

### `set_cowsay_info`

```python
ansible.cli.Display.set_cowsay_info(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_queue`

Set the _final_q on Display, so that we know to proxy display over the queue
instead of directly writing to stdout/stderr from forks

This is only needed in ansible.executor.process.worker:WorkerProc…

```python
ansible.cli.Display.set_queue(self, queue: 'FinalQueue') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `queue` | `FinalQueue` | `—` | pos/kw |

### `system_warning`

```python
ansible.cli.Display.system_warning(self, msg: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |

### `v`

```python
ansible.cli.Display.v(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `verbose`

```python
ansible.cli.Display.verbose(self, msg: 'str', host: 'str | None' = None, caplevel: 'int' = 2) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |
| `caplevel` | `int` | `2` | pos/kw |

### `vv`

```python
ansible.cli.Display.vv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvv`

```python
ansible.cli.Display.vvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvvv`

```python
ansible.cli.Display.vvvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvvvv`

```python
ansible.cli.Display.vvvvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvvvvv`

```python
ansible.cli.Display.vvvvvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `warning`

Display a warning message.

```python
ansible.cli.Display.warning(self, msg: 'str', formatted: 'bool' = False, *, help_text: 'str | None' = None, obj: 't.Any' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `formatted` | `bool` | `False` | pos/kw |
| `help_text` | `str \| None` | `None` | kw |
| `obj` | `t.Any` | `None` | kw |

### `ansible.cli.InventoryManager` methods

### `add_dynamic_group`

Helper function to add a group (if it does not exist), and to assign the
specified host to that group.

```python
ansible.cli.InventoryManager.add_dynamic_group(self, host, result_item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `host` | `—` | `—` | pos/kw |
| `result_item` | `—` | `—` | pos/kw |

### `add_dynamic_host`

Helper function to add a new host to inventory based on a task result.

```python
ansible.cli.InventoryManager.add_dynamic_host(self, host_info, result_item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `host_info` | `—` | `—` | pos/kw |
| `result_item` | `—` | `—` | pos/kw |

### `add_group`

```python
ansible.cli.InventoryManager.add_group(self, group)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `group` | `—` | `—` | pos/kw |

### `add_host`

```python
ansible.cli.InventoryManager.add_host(self, host, group=None, port=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `host` | `—` | `—` | pos/kw |
| `group` | `—` | `None` | pos/kw |
| `port` | `—` | `None` | pos/kw |

### `clear_caches`

clear all caches

```python
ansible.cli.InventoryManager.clear_caches(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_pattern_cache`

```python
ansible.cli.InventoryManager.clear_pattern_cache(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_groups_dict`

```python
ansible.cli.InventoryManager.get_groups_dict(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_host`

```python
ansible.cli.InventoryManager.get_host(self, hostname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `hostname` | `—` | `—` | pos/kw |

### `get_hosts`

Takes a pattern or list of patterns and returns a list of matching
inventory host names, taking into account any active restrictions
or applied subsets

```python
ansible.cli.InventoryManager.get_hosts(self, pattern='all', ignore_limits=False, ignore_restrictions=False, order=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `'all'` | pos/kw |
| `ignore_limits` | `—` | `False` | pos/kw |
| `ignore_restrictions` | `—` | `False` | pos/kw |
| `order` | `—` | `None` | pos/kw |

### `list_groups`

```python
ansible.cli.InventoryManager.list_groups(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `list_hosts`

return a list of hostnames for a pattern

```python
ansible.cli.InventoryManager.list_hosts(self, pattern='all')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `'all'` | pos/kw |

### `parse_source`

Generate or update inventory for the source provided

```python
ansible.cli.InventoryManager.parse_source(self, source, cache=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `cache` | `—` | `False` | pos/kw |

### `parse_sources`

iterate over inventory sources and parse each one to populate it

```python
ansible.cli.InventoryManager.parse_sources(self, cache=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cache` | `—` | `False` | pos/kw |

### `reconcile_inventory`

```python
ansible.cli.InventoryManager.reconcile_inventory(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `refresh_inventory`

recalculate inventory

```python
ansible.cli.InventoryManager.refresh_inventory(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `remove_restriction`

Do not restrict list operations

```python
ansible.cli.InventoryManager.remove_restriction(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `restrict_to_hosts`

Restrict list operations to the hosts given in restriction.  This is used
to batch serial operations in main playbook code, don't use this for other
reasons.

```python
ansible.cli.InventoryManager.restrict_to_hosts(self, restriction)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `restriction` | `—` | `—` | pos/kw |

### `subset`

Limits inventory results to a subset of inventory that matches a given
pattern, such as to select a given geographic of numeric slice amongst
a previous 'hosts' selection that only select roles, or v…

```python
ansible.cli.InventoryManager.subset(self, subset_pattern)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `subset_pattern` | `—` | `—` | pos/kw |

### `ansible.cli.PromptVaultSecret` methods

### `ask_vault_passwords`

```python
ansible.cli.PromptVaultSecret.ask_vault_passwords(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `confirm`

```python
ansible.cli.PromptVaultSecret.confirm(self, b_vault_pass_1, b_vault_pass_2)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `b_vault_pass_1` | `—` | `—` | pos/kw |
| `b_vault_pass_2` | `—` | `—` | pos/kw |

### `load`

```python
ansible.cli.PromptVaultSecret.load(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `ansible.cli.VariableManager` methods

### `clear_facts`

Clears the facts for a host

```python
ansible.cli.VariableManager.clear_facts(self, hostname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `hostname` | `—` | `—` | pos/kw |

### `get_delegated_vars_and_hostname`

Get the delegated_vars for an individual task invocation, which may be in the context
of an individual loop iteration.

Not used directly be VariableManager, but used primarily within TaskExecutor

```python
ansible.cli.VariableManager.get_delegated_vars_and_hostname(self, templar, task, variables)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `templar` | `—` | `—` | pos/kw |
| `task` | `—` | `—` | pos/kw |
| `variables` | `—` | `—` | pos/kw |

### `get_vars`

Returns the variables, with optional "context" given via the parameters
for the play, host, and task (which could possibly result in different
sets of variables being returned due to the additional c…

```python
ansible.cli.VariableManager.get_vars(self, play: 'Play | None' = None, host: 'Host | None' = None, task: 'Task | None' = None, include_hostvars: 'bool' = True, use_cache: 'bool' = True, _hosts: 'list[str] | None' = None, _hosts_all: 'list[str] | None' = None, stage: 'str' = 'task') -> 'dict[str, t.Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `play` | `Play \| None` | `None` | pos/kw |
| `host` | `Host \| None` | `None` | pos/kw |
| `task` | `Task \| None` | `None` | pos/kw |
| `include_hostvars` | `bool` | `True` | pos/kw |
| `use_cache` | `bool` | `True` | pos/kw |
| `_hosts` | `list[str] \| None` | `None` | pos/kw |
| `_hosts_all` | `list[str] \| None` | `None` | pos/kw |
| `stage` | `str` | `'task'` | pos/kw |

**Returns:** `dict[str, t.Any]`

### `set_host_facts`

Sets or updates the given facts for a host in the fact cache.

```python
ansible.cli.VariableManager.set_host_facts(self, host, facts)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `host` | `—` | `—` | pos/kw |
| `facts` | `—` | `—` | pos/kw |

### `set_host_variable`

Sets a value in the vars_cache for a host.

```python
ansible.cli.VariableManager.set_host_variable(self, host, varname, value)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `host` | `—` | `—` | pos/kw |
| `varname` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |

### `set_inventory`

```python
ansible.cli.VariableManager.set_inventory(self, inventory)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `inventory` | `—` | `—` | pos/kw |

### `set_nonpersistent_facts`

Sets or updates the given facts for a host in the fact cache.

```python
ansible.cli.VariableManager.set_nonpersistent_facts(self, host, facts)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `host` | `—` | `—` | pos/kw |
| `facts` | `—` | `—` | pos/kw |

### `ansible.cli.VaultSecretsContext` methods

### `current`

Access vault secrets, if initialized, ala `AmbientContextBase.current()`.

```python
ansible.cli.VaultSecretsContext.current(optional: 'bool' = False) -> 't.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `optional` | `bool` | `False` | pos/kw |

**Returns:** `t.Self`

### `initialize`

Initialize VaultSecretsContext with the specified instance and secrets (since it's not a lazy or per-thread context).
This method will fail if called more than once.

```python
ansible.cli.VaultSecretsContext.initialize(value: 't.Self') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `t.Self` | `—` | pos/kw |

### `ansible.cli.adhoc.AdHocCLI` methods

### `ask_passwords`

prompt for connection and become passwords if needed

```python
ansible.cli.adhoc.AdHocCLI.ask_passwords()
```

### `build_vault_ids`

```python
ansible.cli.adhoc.AdHocCLI.build_vault_ids(vault_ids, vault_password_files=None, ask_vault_pass=None, auto_prompt=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vault_ids` | `—` | `—` | pos/kw |
| `vault_password_files` | `—` | `None` | pos/kw |
| `ask_vault_pass` | `—` | `None` | pos/kw |
| `auto_prompt` | `—` | `True` | pos/kw |

### `cli_executor`

```python
ansible.cli.adhoc.AdHocCLI.cli_executor(args=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `None` | pos/kw |

### `get_host_list`

```python
ansible.cli.adhoc.AdHocCLI.get_host_list(inventory, subset, pattern='all')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inventory` | `—` | `—` | pos/kw |
| `subset` | `—` | `—` | pos/kw |
| `pattern` | `—` | `'all'` | pos/kw |

### `get_password_from_file`

```python
ansible.cli.adhoc.AdHocCLI.get_password_from_file(pwd_file: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pwd_file` | `str` | `—` | pos/kw |

**Returns:** `str`

### `init_parser`

create an options parser for bin/ansible

```python
ansible.cli.adhoc.AdHocCLI.init_parser(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pager`

find reasonable way to display text

```python
ansible.cli.adhoc.AdHocCLI.pager(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `pager_pipe`

pipe text through a pager

```python
ansible.cli.adhoc.AdHocCLI.pager_pipe(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `parse`

Parse the command line args

This method parses the command line arguments.  It uses the parser
stored in the self.parser attribute and saves the args and options in
context.CLIARGS.

Subclasses need…

```python
ansible.cli.adhoc.AdHocCLI.parse(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `post_process_args`

Post process and validate options for bin/ansible

```python
ansible.cli.adhoc.AdHocCLI.post_process_args(self, options)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |

### `run`

create and execute the single task playbook

```python
ansible.cli.adhoc.AdHocCLI.run(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setup_vault_secrets`

```python
ansible.cli.adhoc.AdHocCLI.setup_vault_secrets(loader, vault_ids, vault_password_files=None, ask_vault_pass=None, create_new_password=False, auto_prompt=True, initialize_context=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loader` | `—` | `—` | pos/kw |
| `vault_ids` | `—` | `—` | pos/kw |
| `vault_password_files` | `—` | `None` | pos/kw |
| `ask_vault_pass` | `—` | `None` | pos/kw |
| `create_new_password` | `—` | `False` | pos/kw |
| `auto_prompt` | `—` | `True` | pos/kw |
| `initialize_context` | `—` | `True` | pos/kw |

### `show_devel_warning`

```python
ansible.cli.adhoc.AdHocCLI.show_devel_warning(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `split_vault_id`

```python
ansible.cli.adhoc.AdHocCLI.split_vault_id(vault_id)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vault_id` | `—` | `—` | pos/kw |

### `validate_conflicts`

check for conflicting options

```python
ansible.cli.adhoc.AdHocCLI.validate_conflicts(self, op, runas_opts=False, fork_opts=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `op` | `—` | `—` | pos/kw |
| `runas_opts` | `—` | `False` | pos/kw |
| `fork_opts` | `—` | `False` | pos/kw |

### `version_info`

return full ansible version info

```python
ansible.cli.adhoc.AdHocCLI.version_info(gitinfo=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `gitinfo` | `—` | `False` | pos/kw |

### `ansible.cli.adhoc.CLI` methods

### `ask_passwords`

prompt for connection and become passwords if needed

```python
ansible.cli.adhoc.CLI.ask_passwords()
```

### `build_vault_ids`

```python
ansible.cli.adhoc.CLI.build_vault_ids(vault_ids, vault_password_files=None, ask_vault_pass=None, auto_prompt=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vault_ids` | `—` | `—` | pos/kw |
| `vault_password_files` | `—` | `None` | pos/kw |
| `ask_vault_pass` | `—` | `None` | pos/kw |
| `auto_prompt` | `—` | `True` | pos/kw |

### `cli_executor`

```python
ansible.cli.adhoc.CLI.cli_executor(args=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `None` | pos/kw |

### `get_host_list`

```python
ansible.cli.adhoc.CLI.get_host_list(inventory, subset, pattern='all')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inventory` | `—` | `—` | pos/kw |
| `subset` | `—` | `—` | pos/kw |
| `pattern` | `—` | `'all'` | pos/kw |

### `get_password_from_file`

```python
ansible.cli.adhoc.CLI.get_password_from_file(pwd_file: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pwd_file` | `str` | `—` | pos/kw |

**Returns:** `str`

### `init_parser`

Create an options parser for most ansible scripts

Subclasses need to implement this method.  They will usually call the base class's
init_parser to create a basic version and then add their own opti…

```python
ansible.cli.adhoc.CLI.init_parser(self, desc=None, epilog=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `desc` | `—` | `None` | pos/kw |
| `epilog` | `—` | `None` | pos/kw |

### `pager`

find reasonable way to display text

```python
ansible.cli.adhoc.CLI.pager(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `pager_pipe`

pipe text through a pager

```python
ansible.cli.adhoc.CLI.pager_pipe(text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `text` | `—` | `—` | pos/kw |

### `parse`

Parse the command line args

This method parses the command line arguments.  It uses the parser
stored in the self.parser attribute and saves the args and options in
context.CLIARGS.

Subclasses need…

```python
ansible.cli.adhoc.CLI.parse(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `post_process_args`

Process the command line args

Subclasses need to implement this method.  This method validates and transforms the command
line arguments.  It can be used to check whether conflicting values were giv…

```python
ansible.cli.adhoc.CLI.post_process_args(self, options)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |

### `run`

Run the ansible command

Subclasses must implement this method.  It does the actual work of
running an Ansible command.

```python
ansible.cli.adhoc.CLI.run(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `setup_vault_secrets`

```python
ansible.cli.adhoc.CLI.setup_vault_secrets(loader, vault_ids, vault_password_files=None, ask_vault_pass=None, create_new_password=False, auto_prompt=True, initialize_context=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loader` | `—` | `—` | pos/kw |
| `vault_ids` | `—` | `—` | pos/kw |
| `vault_password_files` | `—` | `None` | pos/kw |
| `ask_vault_pass` | `—` | `None` | pos/kw |
| `create_new_password` | `—` | `False` | pos/kw |
| `auto_prompt` | `—` | `True` | pos/kw |
| `initialize_context` | `—` | `True` | pos/kw |

### `show_devel_warning`

```python
ansible.cli.adhoc.CLI.show_devel_warning(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `split_vault_id`

```python
ansible.cli.adhoc.CLI.split_vault_id(vault_id)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vault_id` | `—` | `—` | pos/kw |

### `validate_conflicts`

check for conflicting options

```python
ansible.cli.adhoc.CLI.validate_conflicts(self, op, runas_opts=False, fork_opts=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `op` | `—` | `—` | pos/kw |
| `runas_opts` | `—` | `False` | pos/kw |
| `fork_opts` | `—` | `False` | pos/kw |

### `version_info`

return full ansible version info

```python
ansible.cli.adhoc.CLI.version_info(gitinfo=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `gitinfo` | `—` | `False` | pos/kw |

### `ansible.cli.adhoc.Display` methods

### `banner`

Prints a header-looking line with cowsay or stars with length depending on terminal width (3 minimum)

```python
ansible.cli.adhoc.Display.banner(self, msg: 'str', color: 'str | None' = None, cows: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |
| `cows` | `bool` | `True` | pos/kw |

### `banner_cowsay`

```python
ansible.cli.adhoc.Display.banner_cowsay(self, msg: 'str', color: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |

### `debug`

```python
ansible.cli.adhoc.Display.debug(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `deprecated`

Display a deprecation warning message, if enabled.
Most callers do not need to provide `collection_name` or `deprecator` -- but provide only one if needed.
Specify `version` or `date`, but not both.…

```python
ansible.cli.adhoc.Display.deprecated(self, msg: 'str', version: 'str | None' = None, removed: 'bool' = False, date: 'str | None' = None, collection_name: 'str | None' = None, *, deprecator: '_messages.PluginInfo | None' = None, help_text: 'str | None' = None, obj: 't.Any' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `version` | `str \| None` | `None` | pos/kw |
| `removed` | `bool` | `False` | pos/kw |
| `date` | `str \| None` | `None` | pos/kw |
| `collection_name` | `str \| None` | `None` | pos/kw |
| `deprecator` | `_messages.PluginInfo \| None` | `None` | kw |
| `help_text` | `str \| None` | `None` | kw |
| `obj` | `t.Any` | `None` | kw |

### `display`

Display a message to the user

Note: msg *must* be a unicode string to prevent UnicodeError tracebacks.

```python
ansible.cli.adhoc.Display.display(self, msg: 'str', color: 'str | None' = None, stderr: 'bool' = False, screen_only: 'bool' = False, log_only: 'bool' = False, newline: 'bool' = True, caplevel: 'int | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `color` | `str \| None` | `None` | pos/kw |
| `stderr` | `bool` | `False` | pos/kw |
| `screen_only` | `bool` | `False` | pos/kw |
| `log_only` | `bool` | `False` | pos/kw |
| `newline` | `bool` | `True` | pos/kw |
| `caplevel` | `int \| None` | `None` | pos/kw |

### `do_var_prompt`

```python
ansible.cli.adhoc.Display.do_var_prompt(self, varname: 'str', private: 'bool' = True, prompt: 'str | None' = None, encrypt: 'str | None' = None, confirm: 'bool' = False, salt_size: 'int | None' = None, salt: 'str | None' = None, default: 'str | None' = None, unsafe: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `varname` | `str` | `—` | pos/kw |
| `private` | `bool` | `True` | pos/kw |
| `prompt` | `str \| None` | `None` | pos/kw |
| `encrypt` | `str \| None` | `None` | pos/kw |
| `confirm` | `bool` | `False` | pos/kw |
| `salt_size` | `int \| None` | `None` | pos/kw |
| `salt` | `str \| None` | `None` | pos/kw |
| `default` | `str \| None` | `None` | pos/kw |
| `unsafe` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `error`

Display an error message.

```python
ansible.cli.adhoc.Display.error(self, msg: 'str | BaseException', wrap_text: 'bool' = True, stderr: 'bool' = True) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str \| BaseException` | `—` | pos/kw |
| `wrap_text` | `bool` | `True` | pos/kw |
| `stderr` | `bool` | `True` | pos/kw |

### `error_as_warning`

Display an exception as a warning.

```python
ansible.cli.adhoc.Display.error_as_warning(self, msg: 'str | None', exception: 'BaseException', *, help_text: 'str | None' = None, obj: 't.Any' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str \| None` | `—` | pos/kw |
| `exception` | `BaseException` | `—` | pos/kw |
| `help_text` | `str \| None` | `None` | kw |
| `obj` | `t.Any` | `None` | kw |

### `get_deprecation_message`

Return a deprecation message and help text for non-display purposes (e.g., exception messages).

```python
ansible.cli.adhoc.Display.get_deprecation_message(self, msg: 'str', version: 'str | None' = None, removed: 'bool' = False, date: 'str | None' = None, collection_name: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `version` | `str \| None` | `None` | pos/kw |
| `removed` | `bool` | `False` | pos/kw |
| `date` | `str \| None` | `None` | pos/kw |
| `collection_name` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `prompt`

```python
ansible.cli.adhoc.Display.prompt(msg: 'str', private: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `msg` | `str` | `—` | pos/kw |
| `private` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `prompt_until`

```python
ansible.cli.adhoc.Display.prompt_until(self, msg: 'str', private: 'bool' = False, seconds: 'int | None' = None, interrupt_input: 'c.Iterable[bytes] | None' = None, complete_input: 'c.Iterable[bytes] | None' = None) -> 'bytes'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `private` | `bool` | `False` | pos/kw |
| `seconds` | `int \| None` | `None` | pos/kw |
| `interrupt_input` | `c.Iterable[bytes] \| None` | `None` | pos/kw |
| `complete_input` | `c.Iterable[bytes] \| None` | `None` | pos/kw |

**Returns:** `bytes`

### `set_cowsay_info`

```python
ansible.cli.adhoc.Display.set_cowsay_info(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_queue`

Set the _final_q on Display, so that we know to proxy display over the queue
instead of directly writing to stdout/stderr from forks

This is only needed in ansible.executor.process.worker:WorkerProc…

```python
ansible.cli.adhoc.Display.set_queue(self, queue: 'FinalQueue') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `queue` | `FinalQueue` | `—` | pos/kw |

### `system_warning`

```python
ansible.cli.adhoc.Display.system_warning(self, msg: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |

### `v`

```python
ansible.cli.adhoc.Display.v(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `verbose`

```python
ansible.cli.adhoc.Display.verbose(self, msg: 'str', host: 'str | None' = None, caplevel: 'int' = 2) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |
| `caplevel` | `int` | `2` | pos/kw |

### `vv`

```python
ansible.cli.adhoc.Display.vv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvv`

```python
ansible.cli.adhoc.Display.vvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvvv`

```python
ansible.cli.adhoc.Display.vvvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvvvv`

```python
ansible.cli.adhoc.Display.vvvvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `vvvvvv`

```python
ansible.cli.adhoc.Display.vvvvvv(self, msg: 'str', host: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `host` | `str \| None` | `None` | pos/kw |

### `warning`

Display a warning message.

```python
ansible.cli.adhoc.Display.warning(self, msg: 'str', formatted: 'bool' = False, *, help_text: 'str | None' = None, obj: 't.Any' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `msg` | `str` | `—` | pos/kw |
| `formatted` | `bool` | `False` | pos/kw |
| `help_text` | `str \| None` | `None` | kw |
| `obj` | `t.Any` | `None` | kw |

### `ansible.cli.adhoc.Origin` methods

### `first_tagged_on`

Return the first value which is tagged with this type, or None if no match is found.

```python
ansible.cli.adhoc.Origin.first_tagged_on(*values: 't.Any') -> 't.Any | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `values` | `t.Any` | `—` | *args |

**Returns:** `t.Any | None`

### `get_or_create_tag`

Return the tag from the given value, creating a tag from the provided path if no tag was found.

```python
ansible.cli.adhoc.Origin.get_or_create_tag(value: 't.Any', path: 'str | os.PathLike | None') -> 'Origin'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `t.Any` | `—` | pos/kw |
| `path` | `str \| os.PathLike \| None` | `—` | pos/kw |

**Returns:** `Origin`

### `get_required_tag`

```python
ansible.cli.adhoc.Origin.get_required_tag(value: 't.Any') -> 't.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `t.Any` | `—` | pos/kw |

**Returns:** `t.Self`

### `get_tag`

```python
ansible.cli.adhoc.Origin.get_tag(value: 't.Any') -> 't.Optional[t.Self]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `t.Any` | `—` | pos/kw |

**Returns:** `t.Optional[t.Self]`

### `is_tagged_on`

```python
ansible.cli.adhoc.Origin.is_tagged_on(value: 't.Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `t.Any` | `—` | pos/kw |

**Returns:** `bool`

### `replace`

Return a new origin based on an existing one, with the given fields replaced.

```python
ansible.cli.adhoc.Origin.replace(self, path: 'str | types.EllipsisType' = Ellipsis, description: 'str | types.EllipsisType' = Ellipsis, line_num: 'int | None | types.EllipsisType' = Ellipsis, col_num: 'int | None | types.EllipsisType' = Ellipsis) -> 't.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `description` | `str \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `line_num` | `int \| None \| types.EllipsisType` | `Ellipsis` | pos/kw |
| `col_num` | `int \| None \| types.EllipsisType` | `Ellipsis` | pos/kw |

**Returns:** `t.Self`

### `tag`

Return a copy of `value` with this tag applied, overwriting any existing tag of the same type.
If `value` is an ignored type, the original `value` will be returned.
If `value` is not taggable, a `Not…

```python
ansible.cli.adhoc.Origin.tag(self, value: '_T') -> '_T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `_T` | `—` | pos/kw |

**Returns:** `_T`

### `try_tag`

Return a copy of `value` with this tag applied, overwriting any existing tag of the same type.
If `value` is not taggable, the original `value` will be returned.

```python
ansible.cli.adhoc.Origin.try_tag(self, value: '_T') -> '_T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `_T` | `—` | pos/kw |

**Returns:** `_T`

### `untag`

If this tag type is present on `value`, return a copy with that tag removed.
Otherwise, the original `value` is returned.

```python
ansible.cli.adhoc.Origin.untag(value: '_T') -> '_T'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `_T` | `—` | pos/kw |

**Returns:** `_T`

### `ansible.cli.adhoc.Play` methods

### `compile`

Compiles and returns the task list for this play, compiled from the
roles (which are themselves compiled recursively) and/or the list of
tasks specified in the play.

```python
ansible.cli.adhoc.Play.compile(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compile_roles_handlers`

Handles the role handler compilation step, returning a flat list of Handlers
This is done for all roles in the Play.

```python
ansible.cli.adhoc.Play.compile_roles_handlers(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `copy`

Create a copy of this object and return it.

```python
ansible.cli.adhoc.Play.copy(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `dump_attrs`

Dumps all attributes to a dictionary

```python
ansible.cli.adhoc.Play.dump_attrs(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `dump_me`

this is never called from production code, it is here to be used when debugging as a 'complex print'

```python
ansible.cli.adhoc.Play.dump_me(self, depth=0)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `depth` | `—` | `0` | pos/kw |

### `evaluate_tags`

Check if the current item should be executed depending on the specified tags.

NOTE this method is assumed to be called only on Task objects.

```python
ansible.cli.adhoc.Play.evaluate_tags(self, only_tags, skip_tags, all_vars)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `only_tags` | `—` | `—` | pos/kw |
| `skip_tags` | `—` | `—` | pos/kw |
| `all_vars` | `—` | `—` | pos/kw |

### `from_attrs`

Loads attributes from a dictionary

```python
ansible.cli.adhoc.Play.from_attrs(self, attrs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attrs` | `—` | `—` | pos/kw |

### `get_dep_chain`

```python
ansible.cli.adhoc.Play.get_dep_chain(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_ds`

```python
ansible.cli.adhoc.Play.get_ds(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_handlers`

```python
ansible.cli.adhoc.Play.get_handlers(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_loader`

```python
ansible.cli.adhoc.Play.get_loader(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_name`

return the name of the Play

```python
ansible.cli.adhoc.Play.get_name(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_path`

return the absolute path of the playbook object and its line number

```python
ansible.cli.adhoc.Play.get_path(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_roles`

```python
ansible.cli.adhoc.Play.get_roles(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_search_path`

Return the list of paths you should search for files, in order.
This follows role/playbook dependency chain.

```python
ansible.cli.adhoc.Play.get_search_path(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_tasks`

```python
ansible.cli.adhoc.Play.get_tasks(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_validated_value`

```python
ansible.cli.adhoc.Play.get_validated_value(self, name, attribute, value, templar)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `attribute` | `—` | `—` | pos/kw |
| `value` | `—` | `—` | pos/kw |
| `templar` | `—` | `—` | pos/kw |

### `get_variable_manager`

```python
ansible.cli.adhoc.Play.get_variable_manager(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_vars`

```python
ansible.cli.adhoc.Play.get_vars(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_vars_files`

```python
ansible.cli.adhoc.Play.get_vars_files(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `load`

```python
ansible.cli.adhoc.Play.load(data, variable_manager=None, loader=None, vars=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `data` | `—` | `—` | pos/kw |
| `variable_manager` | `—` | `None` | pos/kw |
| `loader` | `—` | `None` | pos/kw |
| `vars` | `—` | `None` | pos/kw |

### `load_data`

walk the input datastructure and assign any values

```python
ansible.cli.adhoc.Play.load_data(self, ds, variable_manager=None, loader=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ds` | `—` | `—` | pos/kw |
| `variable_manager` | `—` | `None` | pos/kw |
| `loader` | `—` | `None` | pos/kw |


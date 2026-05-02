---
name: package
description: "Cookiecutter Python package guide for generating projects from reusable templates"
metadata:
  languages: "python"
  versions: "2.7.1"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "cookiecutter,python,scaffolding,templates,cli,project-generation,jinja2,main,Non-Interactive,Version-Sensitive,example.com,ContextDecodingException,EmptyDirNameException,FailedHookException,InvalidModeException,InvalidZipRepository,OutputDirExistsException,RepositoryCloneFailed,RepositoryNotFound,UndefinedVariableInTemplate,UnknownExtension,configure_logger,get_user_config,list_installed_templates,validate_extra_context,version_msg,ConfigDoesNotExistException,InvalidConfiguration,get_config,merge_configs,ExtensionLoaderMixin,StrictEnvironment,add_extension,call_filter,call_test,compile,compile_expression,compile_templates,extend,from_string,get_or_select_template,get_template,getattr,getitem,handle_exception,iter_extensions,join_path,lex,list_templates,make_globals,overlay,parse,preprocess,select_template,CookiecutterException,MissingProjectDir,NonTemplatedInputDirException,UnknownRepoType,UnknownTemplateDirException,VCSNotInstalled,JsonifyExtension,attr,bind,call_method,filter_stream,RandomStringExtension,SlugifyExtension,TimeExtension,UUIDExtension,find_template,YesNoPrompt,ask,check_choice,get_input,make_prompt,on_validate_error,pre_prompt,process_response,render_default,apply_overwrites_to_context,create_env_with_context,generate_context,generate_file,generate_files,is_copy_only_path,make_sure_path_exists,render_and_create_dir,rmtree,run_hook_from_repo_dir,work_in,create_tmp_repo_dir,find_hook,run_hook,run_pre_prompt_hook,run_script,run_script_with_context,valid_hook,choose_nested_template,determine_repo_dir,dump,load,prompt_for_config,JsonPrompt,process_json,prompt_and_delete,prompt_choice_for_config,prompt_choice_for_template,read_repo_password,read_user_choice,read_user_dict,read_user_variable,read_user_yes_no,render_variable,get_file_name,clone,expand_abbreviations,is_repo_url,is_zip_file,repository_has_cookiecutter_json,unzip"
---

# cookiecutter — package

Main package for Cookiecutter.

## Install

```bash
pip install cookiecutter
```

## Imports

```python
import cookiecutter
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `ContextDecodingException` | Class | Exception for failed JSON decoding.  Raised when a project's JSON context file… |
| `EmptyDirNameException` | Class | Exception for a empty directory name.  Raised when the directory name provided… |
| `FailedHookException` | Class | Exception for hook failures.  Raised when a hook script fails. |
| `InvalidModeException` | Class | Exception for incompatible modes.  Raised when cookiecutter is called with both… |
| `InvalidZipRepository` | Class | Exception for bad zip repo.  Raised when the specified cookiecutter repository… |
| `OutputDirExistsException` | Class | Exception for existing output directory.  Raised when the output directory of t… |
| `RepositoryCloneFailed` | Class | Exception for un-cloneable repo.  Raised when a cookiecutter template can't be… |
| `RepositoryNotFound` | Class | Exception for missing repo.  Raised when the specified cookiecutter repository… |
| `UndefinedVariableInTemplate` | Class | Exception for out-of-scope variables.  Raised when a template uses a variable w… |
| `UnknownExtension` | Class | Exception for un-importable extension.  Raised when an environment is unable to… |
| `configure_logger` | Function | Configure logging for cookiecutter.  Set up logging to stdout with given level.… |
| `cookiecutter` | Function | Run Cookiecutter just as if using it from the command line.  :param template: A… |
| `get_user_config` | Function | Return the user config as a dict.  If ``default_config`` is True, ignore ``conf… |
| `list_installed_templates` | Function | List installed (locally cloned) templates. Use cookiecutter --list-installed. |
| `validate_extra_context` | Function | Validate extra context. |
| `version_msg` | Function | Return the Cookiecutter version, location and Python powering it. |
| `ConfigDoesNotExistException` | Class | Exception for missing config file.  Raised when get_config() is passed a path t… |
| `InvalidConfiguration` | Class | Exception for invalid configuration file.  Raised if the global configuration f… |
| `get_config` | Function | Retrieve the config from the specified path, returning a config dict. |
| `get_user_config` | Function | Return the user config as a dict.  If ``default_config`` is True, ignore ``conf… |
| `merge_configs` | Function | Recursively update a dict with the key/value pair of another.  Dict values that… |
| `ExtensionLoaderMixin` | Class | Mixin providing sane loading of extensions specified in a given context.  The c… |
| `StrictEnvironment` | Class | Create strict Jinja2 environment.  Jinja2 environment will raise error on undef… |
| `add_extension` | Method | Adds an extension after the environment was created.  .. versionadded:: 2.5 |
| `call_filter` | Method | Invoke a filter on a value the same way the compiler does.  This might return a… |
| `call_test` | Method | Invoke a test on a value the same way the compiler does.  This might return a c… |
| `compile` | Method | Compile a node or template source code.  The `name` parameter is the load name… |
| `compile_expression` | Method | A handy helper method that returns a callable that accepts keyword arguments th… |
| `compile_templates` | Method | Finds all the templates the loader can find, compiles them and stores them in `… |
| `extend` | Method | Add the items to the instance of the environment if they do not exist yet.  Thi… |
| `from_string` | Method | Load a template from a source string without using :attr:`loader`.  :param sour… |
| `get_or_select_template` | Method | Use :meth:`select_template` if an iterable of template names is given, or :meth… |
| `get_template` | Method | Load a template by name with :attr:`loader` and return a :class:`Template`. If… |
| `getattr` | Method | Get an item or attribute of an object but prefer the attribute. Unlike :meth:`g… |
| `getitem` | Method | Get an item or attribute of an object but prefer the item. |
| `handle_exception` | Method | Exception handling helper.  This is used internally to either raise rewritten e… |
| `iter_extensions` | Method | Iterates over the extensions by priority. |
| `join_path` | Method | Join a template with the parent.  By default all the lookups are relative to th… |
| `lex` | Method | Lex the given sourcecode and return a generator that yields tokens as tuples in… |
| `list_templates` | Method | Returns a list of templates for this environment.  This requires that the loade… |
| `make_globals` | Method | Make the globals map for a template. Any given template globals overlay the env… |
| `overlay` | Method | Create a new overlay environment that shares all the data with the current envi… |
| `parse` | Method | Parse the sourcecode and return the abstract syntax tree.  This tree of nodes i… |
| `preprocess` | Method | Preprocesses the source with all extensions.  This is automatically called for… |
| `select_template` | Method | Like :meth:`get_template`, but tries loading multiple names. If none of the nam… |
| `UnknownExtension` | Class | Exception for un-importable extension.  Raised when an environment is unable to… |
| `ConfigDoesNotExistException` | Class | Exception for missing config file.  Raised when get_config() is passed a path t… |
| `ContextDecodingException` | Class | Exception for failed JSON decoding.  Raised when a project's JSON context file… |
| `CookiecutterException` | Class | Base exception class.  All Cookiecutter-specific exceptions should subclass thi… |
| `EmptyDirNameException` | Class | Exception for a empty directory name.  Raised when the directory name provided… |
| `FailedHookException` | Class | Exception for hook failures.  Raised when a hook script fails. |
| `InvalidConfiguration` | Class | Exception for invalid configuration file.  Raised if the global configuration f… |
| `InvalidModeException` | Class | Exception for incompatible modes.  Raised when cookiecutter is called with both… |
| `InvalidZipRepository` | Class | Exception for bad zip repo.  Raised when the specified cookiecutter repository… |
| `MissingProjectDir` | Class | Exception for missing generated project directory.  Raised during cleanup when… |
| `NonTemplatedInputDirException` | Class | Exception for when a project's input dir is not templated.  The name of the inp… |
| `OutputDirExistsException` | Class | Exception for existing output directory.  Raised when the output directory of t… |
| `RepositoryCloneFailed` | Class | Exception for un-cloneable repo.  Raised when a cookiecutter template can't be… |
| `RepositoryNotFound` | Class | Exception for missing repo.  Raised when the specified cookiecutter repository… |
| `UndefinedVariableInTemplate` | Class | Exception for out-of-scope variables.  Raised when a template uses a variable w… |
| `UnknownExtension` | Class | Exception for un-importable extension.  Raised when an environment is unable to… |
| `UnknownRepoType` | Class | Exception for unknown repo types.  Raised if a repo's type cannot be determined. |
| `UnknownTemplateDirException` | Class | Exception for ambiguous project template directory.  Raised when Cookiecutter c… |
| `VCSNotInstalled` | Class | Exception when version control is unavailable.  Raised if the version control s… |
| `JsonifyExtension` | Class | Jinja2 extension to convert a Python object to JSON. |
| `attr` | Method | Return an attribute node for the current extension.  This is useful to pass con… |
| `bind` | Method | Create a copy of this extension bound to another environment. |
| `call_method` | Method | Call a method of the extension.  This is a shortcut for :meth:`attr` + :class:`… |
| `filter_stream` | Method | It's passed a :class:`~jinja2.lexer.TokenStream` that can be used to filter tok… |
| `parse` | Method | If any of the :attr:`tags` matched this method is called with the parser as fir… |
| `preprocess` | Method | This method is called before the actual lexing and can be used to preprocess th… |
| `RandomStringExtension` | Class | Jinja2 extension to create a random string. |
| `attr` | Method | Return an attribute node for the current extension.  This is useful to pass con… |
| `bind` | Method | Create a copy of this extension bound to another environment. |
| `call_method` | Method | Call a method of the extension.  This is a shortcut for :meth:`attr` + :class:`… |
| `filter_stream` | Method | It's passed a :class:`~jinja2.lexer.TokenStream` that can be used to filter tok… |
| `parse` | Method | If any of the :attr:`tags` matched this method is called with the parser as fir… |
| `preprocess` | Method | This method is called before the actual lexing and can be used to preprocess th… |
| `SlugifyExtension` | Class | Jinja2 Extension to slugify string. |
| `attr` | Method | Return an attribute node for the current extension.  This is useful to pass con… |
| `bind` | Method | Create a copy of this extension bound to another environment. |
| `call_method` | Method | Call a method of the extension.  This is a shortcut for :meth:`attr` + :class:`… |
| `filter_stream` | Method | It's passed a :class:`~jinja2.lexer.TokenStream` that can be used to filter tok… |
| `parse` | Method | If any of the :attr:`tags` matched this method is called with the parser as fir… |
| `preprocess` | Method | This method is called before the actual lexing and can be used to preprocess th… |
| `TimeExtension` | Class | Jinja2 Extension for dates and times. |
| `attr` | Method | Return an attribute node for the current extension.  This is useful to pass con… |
| `bind` | Method | Create a copy of this extension bound to another environment. |
| `call_method` | Method | Call a method of the extension.  This is a shortcut for :meth:`attr` + :class:`… |
| `filter_stream` | Method | It's passed a :class:`~jinja2.lexer.TokenStream` that can be used to filter tok… |
| `parse` | Method | Parse datetime template and add datetime value. |
| `preprocess` | Method | This method is called before the actual lexing and can be used to preprocess th… |
| `UUIDExtension` | Class | Jinja2 Extension to generate uuid4 string. |
| `attr` | Method | Return an attribute node for the current extension.  This is useful to pass con… |
| `bind` | Method | Create a copy of this extension bound to another environment. |
| `call_method` | Method | Call a method of the extension.  This is a shortcut for :meth:`attr` + :class:`… |
| `filter_stream` | Method | It's passed a :class:`~jinja2.lexer.TokenStream` that can be used to filter tok… |
| `parse` | Method | If any of the :attr:`tags` matched this method is called with the parser as fir… |
| `preprocess` | Method | This method is called before the actual lexing and can be used to preprocess th… |
| `NonTemplatedInputDirException` | Class | Exception for when a project's input dir is not templated.  The name of the inp… |
| `find_template` | Function | Determine which child directory of ``repo_dir`` is the project template.  :para… |
| `ContextDecodingException` | Class | Exception for failed JSON decoding.  Raised when a project's JSON context file… |
| `EmptyDirNameException` | Class | Exception for a empty directory name.  Raised when the directory name provided… |
| `OutputDirExistsException` | Class | Exception for existing output directory.  Raised when the output directory of t… |
| `UndefinedVariableInTemplate` | Class | Exception for out-of-scope variables.  Raised when a template uses a variable w… |
| `YesNoPrompt` | Class | A prompt that returns a boolean for yes/no questions. |
| `ask` | Method | Shortcut to construct and run a prompt loop and return the result.  Example:… |
| `check_choice` | Method | Check value is in the list of valid choices.  Args:     value (str): Value ente… |
| `get_input` | Method | Get input from user.  Args:     console (Console): Console instance.     prompt… |
| `make_prompt` | Method | Make prompt text.  Args:     default (DefaultType): Default value.  Returns:… |
| `on_validate_error` | Method | Called to handle validation error.  Args:     value (str): String entered by us… |
| `pre_prompt` | Method | Hook to display something before the prompt. |
| `process_response` | Method | Convert choices to a bool. |
| `render_default` | Method | Render the default as (y) or (n) rather than True/False. |
| `apply_overwrites_to_context` | Function | Modify the given context in place based on the overwrite_context. |
| `create_env_with_context` | Function | Create a jinja environment using the provided context. |
| `find_template` | Function | Determine which child directory of ``repo_dir`` is the project template.  :para… |
| `generate_context` | Function | Generate the context for a Cookiecutter project template.  Loads the JSON file… |
| `generate_file` | Function | Render filename of infile as name of outfile, handle infile correctly.  Dealing… |
| `generate_files` | Function | Render the templates and saves them to files.  :param repo_dir: Project templat… |
| `is_copy_only_path` | Function | Check whether the given `path` should only be copied and not rendered.  Returns… |
| `make_sure_path_exists` | Function | Ensure that a directory exists.  :param path: A directory tree path for creatio… |
| `render_and_create_dir` | Function | Render name of a directory, create the directory, return its path. |
| `rmtree` | Function | Remove a directory and all its contents. Like rm -rf on Unix.  :param path: A d… |
| `run_hook_from_repo_dir` | Function | Run hook from repo directory, clean project directory if hook fails.  :param re… |
| `work_in` | Function | Context manager version of os.chdir.  When exited, returns to the working direc… |
| `FailedHookException` | Class | Exception for hook failures.  Raised when a hook script fails. |
| `create_env_with_context` | Function | Create a jinja environment using the provided context. |
| `create_tmp_repo_dir` | Function | Create a temporary dir with a copy of the contents of repo_dir. |
| `find_hook` | Function | Return a dict of all hook scripts provided.  Must be called with the project te… |
| `rmtree` | Function | Remove a directory and all its contents. Like rm -rf on Unix.  :param path: A d… |
| `run_hook` | Function | Try to find and execute a hook from the specified project directory.  :param ho… |
| `run_hook_from_repo_dir` | Function | Run hook from repo directory, clean project directory if hook fails.  :param re… |
| `run_pre_prompt_hook` | Function | Run pre_prompt hook from repo directory.  :param repo_dir: Project template inp… |
| `run_script` | Function | Execute a script from a working directory.  :param script_path: Absolute path t… |
| `run_script_with_context` | Function | Execute a script after rendering it with Jinja.  :param script_path: Absolute p… |
| `valid_hook` | Function | Determine if a hook file is valid.  :param hook_file: The hook file to consider… |
| `work_in` | Function | Context manager version of os.chdir.  When exited, returns to the working direc… |
| `configure_logger` | Function | Configure logging for cookiecutter.  Set up logging to stdout with given level.… |
| `InvalidModeException` | Class | Exception for incompatible modes.  Raised when cookiecutter is called with both… |
| `choose_nested_template` | Function | Prompt user to select the nested template to use.  :param context: Source for f… |
| `cookiecutter` | Function | Run Cookiecutter just as if using it from the command line.  :param template: A… |
| `determine_repo_dir` | Function | Locate the repository directory from a template reference.  Applies repository… |
| `dump` | Function | Write json data to file. |
| `generate_context` | Function | Generate the context for a Cookiecutter project template.  Loads the JSON file… |
| `generate_files` | Function | Render the templates and saves them to files.  :param repo_dir: Project templat… |
| `get_user_config` | Function | Return the user config as a dict.  If ``default_config`` is True, ignore ``conf… |
| `load` | Function | Read json data from file. |
| `prompt_for_config` | Function | Prompt user to enter a new config.  :param dict context: Source for field names… |
| `rmtree` | Function | Remove a directory and all its contents. Like rm -rf on Unix.  :param path: A d… |
| `run_pre_prompt_hook` | Function | Run pre_prompt hook from repo directory.  :param repo_dir: Project template inp… |
| `JsonPrompt` | Class | A prompt that returns a dict from JSON string. |
| `ask` | Method | Shortcut to construct and run a prompt loop and return the result.  Example:… |
| `check_choice` | Method | Check value is in the list of valid choices.  Args:     value (str): Value ente… |
| `get_input` | Method | Get input from user.  Args:     console (Console): Console instance.     prompt… |
| `make_prompt` | Method | Make prompt text.  Args:     default (DefaultType): Default value.  Returns:… |
| `on_validate_error` | Method | Called to handle validation error.  Args:     value (str): String entered by us… |
| `pre_prompt` | Method | Hook to display something before the prompt. |
| `process_response` | Method | Convert choices to a dict. |
| `render_default` | Method | Turn the supplied default in to a Text instance.  Args:     default (DefaultTyp… |
| `UndefinedVariableInTemplate` | Class | Exception for out-of-scope variables.  Raised when a template uses a variable w… |
| `YesNoPrompt` | Class | A prompt that returns a boolean for yes/no questions. |
| `ask` | Method | Shortcut to construct and run a prompt loop and return the result.  Example:… |
| `check_choice` | Method | Check value is in the list of valid choices.  Args:     value (str): Value ente… |
| `get_input` | Method | Get input from user.  Args:     console (Console): Console instance.     prompt… |
| `make_prompt` | Method | Make prompt text.  Args:     default (DefaultType): Default value.  Returns:… |
| `on_validate_error` | Method | Called to handle validation error.  Args:     value (str): String entered by us… |
| `pre_prompt` | Method | Hook to display something before the prompt. |
| `process_response` | Method | Convert choices to a bool. |
| `render_default` | Method | Render the default as (y) or (n) rather than True/False. |
| `choose_nested_template` | Function | Prompt user to select the nested template to use.  :param context: Source for f… |
| `create_env_with_context` | Function | Create a jinja environment using the provided context. |
| `process_json` | Function | Load user-supplied value as a JSON dict.  :param user_value: User-supplied valu… |
| `prompt_and_delete` | Function | Ask user if it's okay to delete the previously-downloaded file/directory.  If y… |
| `prompt_choice_for_config` | Function | Prompt user with a set of options to choose from.  :param no_input: Do not prom… |
| `prompt_choice_for_template` | Function | Prompt user with a set of options to choose from.  :param no_input: Do not prom… |
| `prompt_for_config` | Function | Prompt user to enter a new config.  :param dict context: Source for field names… |
| `read_repo_password` | Function | Prompt the user to enter a password.  :param question: Question to the user |
| `read_user_choice` | Function | Prompt the user to choose from several options for the given variable.  The fir… |
| `read_user_dict` | Function | Prompt the user to provide a dictionary of data.  :param var_name: Variable as… |
| `read_user_variable` | Function | Prompt user for variable and return the entered value or given default.  :param… |
| `read_user_yes_no` | Function | Prompt the user to reply with 'yes' or 'no' (or equivalent values).  - These in… |
| `render_variable` | Function | Render the next variable to be displayed in the user prompt.  Inside the prompt… |
| `rmtree` | Function | Remove a directory and all its contents. Like rm -rf on Unix.  :param path: A d… |
| `dump` | Function | Write json data to file. |
| `get_file_name` | Function | Get the name of file. |
| `load` | Function | Read json data from file. |
| `make_sure_path_exists` | Function | Ensure that a directory exists.  :param path: A directory tree path for creatio… |
| `RepositoryNotFound` | Class | Exception for missing repo.  Raised when the specified cookiecutter repository… |
| `clone` | Function | Clone a repo to the current directory.  :param repo_url: Repo URL of unknown ty… |
| `determine_repo_dir` | Function | Locate the repository directory from a template reference.  Applies repository… |
| `expand_abbreviations` | Function | Expand abbreviations in a template name.  :param template: The project template… |
| `is_repo_url` | Function | Return True if value is a repository URL. |
| `is_zip_file` | Function | Return True if value is a zip file. |
| `repository_has_cookiecutter_json` | Function | Determine if `repo_directory` contains a `cookiecutter.json` file.  :param repo… |
| `unzip` | Function | Download and unpack a zipfile at a given URI.  This will download the zipfile t… |
| `StrictEnvironment` | Class | Create strict Jinja2 environment.  Jinja2 environment will raise error on undef… |
| `add_extension` | Method | Adds an extension after the environment was created.  .. versionadded:: 2.5 |
| `call_filter` | Method | Invoke a filter on a value the same way the compiler does.  This might return a… |
| `call_test` | Method | Invoke a test on a value the same way the compiler does.  This might return a c… |

## Classes

### `ContextDecodingException`

Exception for failed JSON decoding.

Raised when a project's JSON context file can not be decoded.

```python
cookiecutter.cli.ContextDecodingException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `EmptyDirNameException`

Exception for a empty directory name.

Raised when the directory name provided is empty.

```python
cookiecutter.cli.EmptyDirNameException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FailedHookException`

Exception for hook failures.

Raised when a hook script fails.

```python
cookiecutter.cli.FailedHookException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidModeException`

Exception for incompatible modes.

Raised when cookiecutter is called with both `no_input==True` and
`replay==True` at the same time.

```python
cookiecutter.cli.InvalidModeException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidZipRepository`

Exception for bad zip repo.

Raised when the specified cookiecutter repository isn't a valid
Zip archive.

```python
cookiecutter.cli.InvalidZipRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OutputDirExistsException`

Exception for existing output directory.

Raised when the output directory of the project exists already.

```python
cookiecutter.cli.OutputDirExistsException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RepositoryCloneFailed`

Exception for un-cloneable repo.

Raised when a cookiecutter template can't be cloned.

```python
cookiecutter.cli.RepositoryCloneFailed(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RepositoryNotFound`

Exception for missing repo.

Raised when the specified cookiecutter repository doesn't exist.

```python
cookiecutter.cli.RepositoryNotFound(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UndefinedVariableInTemplate`

Exception for out-of-scope variables.

Raised when a template uses a variable which is not defined in the
context.

```python
cookiecutter.cli.UndefinedVariableInTemplate(self, message: 'str', error: 'TemplateError', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |
| `error` | `TemplateError` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `UnknownExtension`

Exception for un-importable extension.

Raised when an environment is unable to import a required extension.

```python
cookiecutter.cli.UnknownExtension(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigDoesNotExistException`

Exception for missing config file.

Raised when get_config() is passed a path to a config file, but no file
is found at that path.

```python
cookiecutter.config.ConfigDoesNotExistException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidConfiguration`

Exception for invalid configuration file.

Raised if the global configuration file is not valid YAML or is
badly constructed.

```python
cookiecutter.config.InvalidConfiguration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ExtensionLoaderMixin`

Mixin providing sane loading of extensions specified in a given context.

The context is being extracted from the keyword arguments before calling
the next parent class in line of the child.

```python
cookiecutter.environment.ExtensionLoaderMixin(self, *, context: 'dict[str, Any] | None' = None, **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any] \| None` | `None` | kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `StrictEnvironment`

Create strict Jinja2 environment.

Jinja2 environment will raise error on undefined variable in template-
rendering context.

```python
cookiecutter.environment.StrictEnvironment(self, **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `Any` | `—` | **kwargs |

### `UnknownExtension`

Exception for un-importable extension.

Raised when an environment is unable to import a required extension.

```python
cookiecutter.environment.UnknownExtension(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ConfigDoesNotExistException`

Exception for missing config file.

Raised when get_config() is passed a path to a config file, but no file
is found at that path.

```python
cookiecutter.exceptions.ConfigDoesNotExistException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ContextDecodingException`

Exception for failed JSON decoding.

Raised when a project's JSON context file can not be decoded.

```python
cookiecutter.exceptions.ContextDecodingException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `CookiecutterException`

Base exception class.

All Cookiecutter-specific exceptions should subclass this class.

```python
cookiecutter.exceptions.CookiecutterException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `EmptyDirNameException`

Exception for a empty directory name.

Raised when the directory name provided is empty.

```python
cookiecutter.exceptions.EmptyDirNameException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FailedHookException`

Exception for hook failures.

Raised when a hook script fails.

```python
cookiecutter.exceptions.FailedHookException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidConfiguration`

Exception for invalid configuration file.

Raised if the global configuration file is not valid YAML or is
badly constructed.

```python
cookiecutter.exceptions.InvalidConfiguration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidModeException`

Exception for incompatible modes.

Raised when cookiecutter is called with both `no_input==True` and
`replay==True` at the same time.

```python
cookiecutter.exceptions.InvalidModeException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidZipRepository`

Exception for bad zip repo.

Raised when the specified cookiecutter repository isn't a valid
Zip archive.

```python
cookiecutter.exceptions.InvalidZipRepository(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MissingProjectDir`

Exception for missing generated project directory.

Raised during cleanup when remove_repo() can't find a generated project
directory inside of a repo.

```python
cookiecutter.exceptions.MissingProjectDir(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NonTemplatedInputDirException`

Exception for when a project's input dir is not templated.

The name of the input directory should always contain a string that is
rendered to something else, so that input_dir != output_dir.

```python
cookiecutter.exceptions.NonTemplatedInputDirException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OutputDirExistsException`

Exception for existing output directory.

Raised when the output directory of the project exists already.

```python
cookiecutter.exceptions.OutputDirExistsException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RepositoryCloneFailed`

Exception for un-cloneable repo.

Raised when a cookiecutter template can't be cloned.

```python
cookiecutter.exceptions.RepositoryCloneFailed(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RepositoryNotFound`

Exception for missing repo.

Raised when the specified cookiecutter repository doesn't exist.

```python
cookiecutter.exceptions.RepositoryNotFound(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UndefinedVariableInTemplate`

Exception for out-of-scope variables.

Raised when a template uses a variable which is not defined in the
context.

```python
cookiecutter.exceptions.UndefinedVariableInTemplate(self, message: 'str', error: 'TemplateError', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |
| `error` | `TemplateError` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `UnknownExtension`

Exception for un-importable extension.

Raised when an environment is unable to import a required extension.

```python
cookiecutter.exceptions.UnknownExtension(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnknownRepoType`

Exception for unknown repo types.

Raised if a repo's type cannot be determined.

```python
cookiecutter.exceptions.UnknownRepoType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnknownTemplateDirException`

Exception for ambiguous project template directory.

Raised when Cookiecutter cannot determine which directory is the project
template, e.g. more than one dir appears to be a template dir.

```python
cookiecutter.exceptions.UnknownTemplateDirException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `VCSNotInstalled`

Exception when version control is unavailable.

Raised if the version control system (git or hg) is not installed.

```python
cookiecutter.exceptions.VCSNotInstalled(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `JsonifyExtension`

Jinja2 extension to convert a Python object to JSON.

```python
cookiecutter.extensions.JsonifyExtension(self, environment: 'Environment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `RandomStringExtension`

Jinja2 extension to create a random string.

```python
cookiecutter.extensions.RandomStringExtension(self, environment: 'Environment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `SlugifyExtension`

Jinja2 Extension to slugify string.

```python
cookiecutter.extensions.SlugifyExtension(self, environment: 'Environment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `TimeExtension`

Jinja2 Extension for dates and times.

```python
cookiecutter.extensions.TimeExtension(self, environment: 'Environment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `UUIDExtension`

Jinja2 Extension to generate uuid4 string.

```python
cookiecutter.extensions.UUIDExtension(self, environment: 'Environment') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `environment` | `Environment` | `—` | pos/kw |

### `NonTemplatedInputDirException`

Exception for when a project's input dir is not templated.

The name of the input directory should always contain a string that is
rendered to something else, so that input_dir != output_dir.

```python
cookiecutter.find.NonTemplatedInputDirException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ContextDecodingException`

Exception for failed JSON decoding.

Raised when a project's JSON context file can not be decoded.

```python
cookiecutter.generate.ContextDecodingException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `EmptyDirNameException`

Exception for a empty directory name.

Raised when the directory name provided is empty.

```python
cookiecutter.generate.EmptyDirNameException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `OutputDirExistsException`

Exception for existing output directory.

Raised when the output directory of the project exists already.

```python
cookiecutter.generate.OutputDirExistsException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UndefinedVariableInTemplate`

Exception for out-of-scope variables.

Raised when a template uses a variable which is not defined in the
context.

```python
cookiecutter.generate.UndefinedVariableInTemplate(self, message: 'str', error: 'TemplateError', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |
| `error` | `TemplateError` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `YesNoPrompt`

A prompt that returns a boolean for yes/no questions.

```python
cookiecutter.generate.YesNoPrompt(self, prompt: Union[str, ForwardRef('Text')] = '', *, console: Optional[rich.console.Console] = None, password: bool = False, choices: Optional[List[str]] = None, case_sensitive: bool = True, show_default: bool = True, show_choices: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt` | `Union` | `''` | pos/kw |
| `console` | `Optional` | `None` | kw |
| `password` | `bool` | `False` | kw |
| `choices` | `Optional` | `None` | kw |
| `case_sensitive` | `bool` | `True` | kw |
| `show_default` | `bool` | `True` | kw |
| `show_choices` | `bool` | `True` | kw |

### `FailedHookException`

Exception for hook failures.

Raised when a hook script fails.

```python
cookiecutter.hooks.FailedHookException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidModeException`

Exception for incompatible modes.

Raised when cookiecutter is called with both `no_input==True` and
`replay==True` at the same time.

```python
cookiecutter.main.InvalidModeException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `JsonPrompt`

A prompt that returns a dict from JSON string.

```python
cookiecutter.prompt.JsonPrompt(self, prompt: Union[str, ForwardRef('Text')] = '', *, console: Optional[rich.console.Console] = None, password: bool = False, choices: Optional[List[str]] = None, case_sensitive: bool = True, show_default: bool = True, show_choices: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt` | `Union` | `''` | pos/kw |
| `console` | `Optional` | `None` | kw |
| `password` | `bool` | `False` | kw |
| `choices` | `Optional` | `None` | kw |
| `case_sensitive` | `bool` | `True` | kw |
| `show_default` | `bool` | `True` | kw |
| `show_choices` | `bool` | `True` | kw |

### `UndefinedVariableInTemplate`

Exception for out-of-scope variables.

Raised when a template uses a variable which is not defined in the
context.

```python
cookiecutter.prompt.UndefinedVariableInTemplate(self, message: 'str', error: 'TemplateError', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `str` | `—` | pos/kw |
| `error` | `TemplateError` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `YesNoPrompt`

A prompt that returns a boolean for yes/no questions.

```python
cookiecutter.prompt.YesNoPrompt(self, prompt: Union[str, ForwardRef('Text')] = '', *, console: Optional[rich.console.Console] = None, password: bool = False, choices: Optional[List[str]] = None, case_sensitive: bool = True, show_default: bool = True, show_choices: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt` | `Union` | `''` | pos/kw |
| `console` | `Optional` | `None` | kw |
| `password` | `bool` | `False` | kw |
| `choices` | `Optional` | `None` | kw |
| `case_sensitive` | `bool` | `True` | kw |
| `show_default` | `bool` | `True` | kw |
| `show_choices` | `bool` | `True` | kw |

### `RepositoryNotFound`

Exception for missing repo.

Raised when the specified cookiecutter repository doesn't exist.

```python
cookiecutter.repository.RepositoryNotFound(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StrictEnvironment`

Create strict Jinja2 environment.

Jinja2 environment will raise error on undefined variable in template-
rendering context.

```python
cookiecutter.utils.StrictEnvironment(self, **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `Any` | `—` | **kwargs |

## Functions

### `configure_logger`

Configure logging for cookiecutter.

Set up logging to stdout with given level. If ``debug_file`` is given set
up logging to file with DEBUG level.

```python
cookiecutter.cli.configure_logger(stream_level: 'str' = 'DEBUG', debug_file: 'str | None' = None) -> 'logging.Logger'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stream_level` | `str` | `'DEBUG'` | pos/kw |
| `debug_file` | `str \| None` | `None` | pos/kw |

**Returns:** `logging.Logger`

### `cookiecutter`

Run Cookiecutter just as if using it from the command line.

:param template: A directory containing a project template directory,
    or a URL to a git repository.
:param checkout: The branch, tag o…

```python
cookiecutter.cli.cookiecutter(template: 'str', checkout: 'str | None' = None, no_input: 'bool' = False, extra_context: 'dict[str, Any] | None' = None, replay: 'bool | str | None' = None, overwrite_if_exists: 'bool' = False, output_dir: 'str' = '.', config_file: 'str | None' = None, default_config: 'bool' = False, password: 'str | None' = None, directory: 'str | None' = None, skip_if_file_exists: 'bool' = False, accept_hooks: 'bool' = True, keep_project_on_failure: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `template` | `str` | `—` | pos/kw |
| `checkout` | `str \| None` | `None` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |
| `extra_context` | `dict[str, Any] \| None` | `None` | pos/kw |
| `replay` | `bool \| str \| None` | `None` | pos/kw |
| `overwrite_if_exists` | `bool` | `False` | pos/kw |
| `output_dir` | `str` | `'.'` | pos/kw |
| `config_file` | `str \| None` | `None` | pos/kw |
| `default_config` | `bool` | `False` | pos/kw |
| `password` | `str \| None` | `None` | pos/kw |
| `directory` | `str \| None` | `None` | pos/kw |
| `skip_if_file_exists` | `bool` | `False` | pos/kw |
| `accept_hooks` | `bool` | `True` | pos/kw |
| `keep_project_on_failure` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `get_user_config`

Return the user config as a dict.

If ``default_config`` is True, ignore ``config_file`` and return default
values for the config parameters.

If ``default_config`` is a dict, merge values with defau…

```python
cookiecutter.cli.get_user_config(config_file: 'str | None' = None, default_config: 'bool | dict[str, Any]' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| None` | `None` | pos/kw |
| `default_config` | `bool \| dict[str, Any]` | `False` | pos/kw |

**Returns:** `dict[str, Any]`

### `list_installed_templates`

List installed (locally cloned) templates. Use cookiecutter --list-installed.

```python
cookiecutter.cli.list_installed_templates(default_config: 'bool | dict[str, Any]', passed_config_file: 'str | None') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `default_config` | `bool \| dict[str, Any]` | `—` | pos/kw |
| `passed_config_file` | `str \| None` | `—` | pos/kw |

### `validate_extra_context`

Validate extra context.

```python
cookiecutter.cli.validate_extra_context(_ctx: 'Context', _param: 'Parameter', value: 'Iterable[str]') -> 'OrderedDict[str, str] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `_ctx` | `Context` | `—` | pos/kw |
| `_param` | `Parameter` | `—` | pos/kw |
| `value` | `Iterable[str]` | `—` | pos/kw |

**Returns:** `OrderedDict[str, str] | None`

### `version_msg`

Return the Cookiecutter version, location and Python powering it.

```python
cookiecutter.cli.version_msg() -> 'str'
```

**Returns:** `str`

### `get_config`

Retrieve the config from the specified path, returning a config dict.

```python
cookiecutter.config.get_config(config_path: 'Path | str') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_path` | `Path \| str` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `get_user_config`

Return the user config as a dict.

If ``default_config`` is True, ignore ``config_file`` and return default
values for the config parameters.

If ``default_config`` is a dict, merge values with defau…

```python
cookiecutter.config.get_user_config(config_file: 'str | None' = None, default_config: 'bool | dict[str, Any]' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| None` | `None` | pos/kw |
| `default_config` | `bool \| dict[str, Any]` | `False` | pos/kw |

**Returns:** `dict[str, Any]`

### `merge_configs`

Recursively update a dict with the key/value pair of another.

Dict values that are dictionaries themselves will be updated, whilst
preserving existing keys.

```python
cookiecutter.config.merge_configs(default: 'dict[str, Any]', overwrite: 'dict[str, Any]') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `default` | `dict[str, Any]` | `—` | pos/kw |
| `overwrite` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `find_template`

Determine which child directory of ``repo_dir`` is the project template.

:param repo_dir: Local directory of newly cloned repo.
:return: Relative path to project template.

```python
cookiecutter.find.find_template(repo_dir: 'Path | str', env: 'Environment') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `env` | `Environment` | `—` | pos/kw |

**Returns:** `Path`

### `apply_overwrites_to_context`

Modify the given context in place based on the overwrite_context.

```python
cookiecutter.generate.apply_overwrites_to_context(context: 'dict[str, Any]', overwrite_context: 'dict[str, Any]', *, in_dictionary_variable: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `overwrite_context` | `dict[str, Any]` | `—` | pos/kw |
| `in_dictionary_variable` | `bool` | `False` | kw |

### `create_env_with_context`

Create a jinja environment using the provided context.

```python
cookiecutter.generate.create_env_with_context(context: 'dict[str, Any]') -> 'StrictEnvironment'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `StrictEnvironment`

### `find_template`

Determine which child directory of ``repo_dir`` is the project template.

:param repo_dir: Local directory of newly cloned repo.
:return: Relative path to project template.

```python
cookiecutter.generate.find_template(repo_dir: 'Path | str', env: 'Environment') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `env` | `Environment` | `—` | pos/kw |

**Returns:** `Path`

### `generate_context`

Generate the context for a Cookiecutter project template.

Loads the JSON file as a Python object, with key being the JSON filename.

:param context_file: JSON file containing key/value pairs for pop…

```python
cookiecutter.generate.generate_context(context_file: 'str' = 'cookiecutter.json', default_context: 'dict[str, Any] | None' = None, extra_context: 'dict[str, Any] | None' = None) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context_file` | `str` | `'cookiecutter.json'` | pos/kw |
| `default_context` | `dict[str, Any] \| None` | `None` | pos/kw |
| `extra_context` | `dict[str, Any] \| None` | `None` | pos/kw |

**Returns:** `dict[str, Any]`

### `generate_file`

Render filename of infile as name of outfile, handle infile correctly.

Dealing with infile appropriately:

    a. If infile is a binary file, copy it over without rendering.
    b. If infile is a te…

```python
cookiecutter.generate.generate_file(project_dir: 'str', infile: 'str', context: 'dict[str, Any]', env: 'Environment', skip_if_file_exists: 'bool' = False) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `project_dir` | `str` | `—` | pos/kw |
| `infile` | `str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `env` | `Environment` | `—` | pos/kw |
| `skip_if_file_exists` | `bool` | `False` | pos/kw |

### `generate_files`

Render the templates and saves them to files.

:param repo_dir: Project template input directory.
:param context: Dict for populating the template's variables.
:param output_dir: Where to output the…

```python
cookiecutter.generate.generate_files(repo_dir: 'Path | str', context: 'dict[str, Any] | None' = None, output_dir: 'Path | str' = '.', overwrite_if_exists: 'bool' = False, skip_if_file_exists: 'bool' = False, accept_hooks: 'bool' = True, keep_project_on_failure: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `context` | `dict[str, Any] \| None` | `None` | pos/kw |
| `output_dir` | `Path \| str` | `'.'` | pos/kw |
| `overwrite_if_exists` | `bool` | `False` | pos/kw |
| `skip_if_file_exists` | `bool` | `False` | pos/kw |
| `accept_hooks` | `bool` | `True` | pos/kw |
| `keep_project_on_failure` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `is_copy_only_path`

Check whether the given `path` should only be copied and not rendered.

Returns True if `path` matches a pattern in the given `context` dict,
otherwise False.

:param path: A file-system path referri…

```python
cookiecutter.generate.is_copy_only_path(path: 'str', context: 'dict[str, Any]') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `bool`

### `make_sure_path_exists`

Ensure that a directory exists.

:param path: A directory tree path for creation.

```python
cookiecutter.generate.make_sure_path_exists(path: 'Path | str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |

### `render_and_create_dir`

Render name of a directory, create the directory, return its path.

```python
cookiecutter.generate.render_and_create_dir(dirname: 'str', context: 'dict[str, Any]', output_dir: 'Path | str', environment: 'Environment', overwrite_if_exists: 'bool' = False) -> 'tuple[Path, bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dirname` | `str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `output_dir` | `Path \| str` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |
| `overwrite_if_exists` | `bool` | `False` | pos/kw |

**Returns:** `tuple[Path, bool]`

### `rmtree`

Remove a directory and all its contents. Like rm -rf on Unix.

:param path: A directory path.

```python
cookiecutter.generate.rmtree(path: 'Path | str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |

### `run_hook_from_repo_dir`

Run hook from repo directory, clean project directory if hook fails.

:param repo_dir: Project template input directory.
:param hook_name: The hook to execute.
:param project_dir: The directory to ex…

```python
cookiecutter.generate.run_hook_from_repo_dir(repo_dir: 'Path | str', hook_name: 'str', project_dir: 'Path | str', context: 'dict[str, Any]', delete_project_on_failure: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `hook_name` | `str` | `—` | pos/kw |
| `project_dir` | `Path \| str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `delete_project_on_failure` | `bool` | `—` | pos/kw |

### `work_in`

Context manager version of os.chdir.

When exited, returns to the working directory prior to entering.

```python
cookiecutter.generate.work_in(dirname: 'Path | str | None' = None) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dirname` | `Path \| str \| None` | `None` | pos/kw |

**Returns:** `Iterator[None]`

### `create_env_with_context`

Create a jinja environment using the provided context.

```python
cookiecutter.hooks.create_env_with_context(context: 'dict[str, Any]') -> 'StrictEnvironment'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `StrictEnvironment`

### `create_tmp_repo_dir`

Create a temporary dir with a copy of the contents of repo_dir.

```python
cookiecutter.hooks.create_tmp_repo_dir(repo_dir: 'Path | str') -> 'Path'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |

**Returns:** `Path`

### `find_hook`

Return a dict of all hook scripts provided.

Must be called with the project template as the current working directory.
Dict's key will be the hook/script's name, without extension, while values
will…

```python
cookiecutter.hooks.find_hook(hook_name: 'str', hooks_dir: 'str' = 'hooks') -> 'list[str] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hook_name` | `str` | `—` | pos/kw |
| `hooks_dir` | `str` | `'hooks'` | pos/kw |

**Returns:** `list[str] | None`

### `rmtree`

Remove a directory and all its contents. Like rm -rf on Unix.

:param path: A directory path.

```python
cookiecutter.hooks.rmtree(path: 'Path | str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |

### `run_hook`

Try to find and execute a hook from the specified project directory.

:param hook_name: The hook to execute.
:param project_dir: The directory to execute the script from.
:param context: Cookiecutter…

```python
cookiecutter.hooks.run_hook(hook_name: 'str', project_dir: 'Path | str', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hook_name` | `str` | `—` | pos/kw |
| `project_dir` | `Path \| str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `run_hook_from_repo_dir`

Run hook from repo directory, clean project directory if hook fails.

:param repo_dir: Project template input directory.
:param hook_name: The hook to execute.
:param project_dir: The directory to ex…

```python
cookiecutter.hooks.run_hook_from_repo_dir(repo_dir: 'Path | str', hook_name: 'str', project_dir: 'Path | str', context: 'dict[str, Any]', delete_project_on_failure: 'bool') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `hook_name` | `str` | `—` | pos/kw |
| `project_dir` | `Path \| str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `delete_project_on_failure` | `bool` | `—` | pos/kw |

### `run_pre_prompt_hook`

Run pre_prompt hook from repo directory.

:param repo_dir: Project template input directory.

```python
cookiecutter.hooks.run_pre_prompt_hook(repo_dir: 'Path | str') -> 'Path | str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |

**Returns:** `Path | str`

### `run_script`

Execute a script from a working directory.

:param script_path: Absolute path to the script to run.
:param cwd: The directory to run the script from.

```python
cookiecutter.hooks.run_script(script_path: 'str', cwd: 'Path | str' = '.') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `script_path` | `str` | `—` | pos/kw |
| `cwd` | `Path \| str` | `'.'` | pos/kw |

### `run_script_with_context`

Execute a script after rendering it with Jinja.

:param script_path: Absolute path to the script to run.
:param cwd: The directory to run the script from.
:param context: Cookiecutter project templat…

```python
cookiecutter.hooks.run_script_with_context(script_path: 'Path | str', cwd: 'Path | str', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `script_path` | `Path \| str` | `—` | pos/kw |
| `cwd` | `Path \| str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `valid_hook`

Determine if a hook file is valid.

:param hook_file: The hook file to consider for validity
:param hook_name: The hook to find
:return: The hook file validity

```python
cookiecutter.hooks.valid_hook(hook_file: 'str', hook_name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hook_file` | `str` | `—` | pos/kw |
| `hook_name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `work_in`

Context manager version of os.chdir.

When exited, returns to the working directory prior to entering.

```python
cookiecutter.hooks.work_in(dirname: 'Path | str | None' = None) -> 'Iterator[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dirname` | `Path \| str \| None` | `None` | pos/kw |

**Returns:** `Iterator[None]`

### `configure_logger`

Configure logging for cookiecutter.

Set up logging to stdout with given level. If ``debug_file`` is given set
up logging to file with DEBUG level.

```python
cookiecutter.log.configure_logger(stream_level: 'str' = 'DEBUG', debug_file: 'str | None' = None) -> 'logging.Logger'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stream_level` | `str` | `'DEBUG'` | pos/kw |
| `debug_file` | `str \| None` | `None` | pos/kw |

**Returns:** `logging.Logger`

### `choose_nested_template`

Prompt user to select the nested template to use.

:param context: Source for field names and sample values.
:param repo_dir: Repository directory.
:param no_input: Do not prompt for user input and u…

```python
cookiecutter.main.choose_nested_template(context: 'dict[str, Any]', repo_dir: 'Path | str', no_input: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `cookiecutter`

Run Cookiecutter just as if using it from the command line.

:param template: A directory containing a project template directory,
    or a URL to a git repository.
:param checkout: The branch, tag o…

```python
cookiecutter.main.cookiecutter(template: 'str', checkout: 'str | None' = None, no_input: 'bool' = False, extra_context: 'dict[str, Any] | None' = None, replay: 'bool | str | None' = None, overwrite_if_exists: 'bool' = False, output_dir: 'str' = '.', config_file: 'str | None' = None, default_config: 'bool' = False, password: 'str | None' = None, directory: 'str | None' = None, skip_if_file_exists: 'bool' = False, accept_hooks: 'bool' = True, keep_project_on_failure: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `template` | `str` | `—` | pos/kw |
| `checkout` | `str \| None` | `None` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |
| `extra_context` | `dict[str, Any] \| None` | `None` | pos/kw |
| `replay` | `bool \| str \| None` | `None` | pos/kw |
| `overwrite_if_exists` | `bool` | `False` | pos/kw |
| `output_dir` | `str` | `'.'` | pos/kw |
| `config_file` | `str \| None` | `None` | pos/kw |
| `default_config` | `bool` | `False` | pos/kw |
| `password` | `str \| None` | `None` | pos/kw |
| `directory` | `str \| None` | `None` | pos/kw |
| `skip_if_file_exists` | `bool` | `False` | pos/kw |
| `accept_hooks` | `bool` | `True` | pos/kw |
| `keep_project_on_failure` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `determine_repo_dir`

Locate the repository directory from a template reference.

Applies repository abbreviations to the template reference.
If the template refers to a repository URL, clone it.
If the template is a path…

```python
cookiecutter.main.determine_repo_dir(template: 'str', abbreviations: 'dict[str, str]', clone_to_dir: 'Path | str', checkout: 'str | None', no_input: 'bool', password: 'str | None' = None, directory: 'str | None' = None) -> 'tuple[str, bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `template` | `str` | `—` | pos/kw |
| `abbreviations` | `dict[str, str]` | `—` | pos/kw |
| `clone_to_dir` | `Path \| str` | `—` | pos/kw |
| `checkout` | `str \| None` | `—` | pos/kw |
| `no_input` | `bool` | `—` | pos/kw |
| `password` | `str \| None` | `None` | pos/kw |
| `directory` | `str \| None` | `None` | pos/kw |

**Returns:** `tuple[str, bool]`

### `dump`

Write json data to file.

```python
cookiecutter.main.dump(replay_dir: 'Path | str', template_name: 'str', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `replay_dir` | `Path \| str` | `—` | pos/kw |
| `template_name` | `str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `generate_context`

Generate the context for a Cookiecutter project template.

Loads the JSON file as a Python object, with key being the JSON filename.

:param context_file: JSON file containing key/value pairs for pop…

```python
cookiecutter.main.generate_context(context_file: 'str' = 'cookiecutter.json', default_context: 'dict[str, Any] | None' = None, extra_context: 'dict[str, Any] | None' = None) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context_file` | `str` | `'cookiecutter.json'` | pos/kw |
| `default_context` | `dict[str, Any] \| None` | `None` | pos/kw |
| `extra_context` | `dict[str, Any] \| None` | `None` | pos/kw |

**Returns:** `dict[str, Any]`

### `generate_files`

Render the templates and saves them to files.

:param repo_dir: Project template input directory.
:param context: Dict for populating the template's variables.
:param output_dir: Where to output the…

```python
cookiecutter.main.generate_files(repo_dir: 'Path | str', context: 'dict[str, Any] | None' = None, output_dir: 'Path | str' = '.', overwrite_if_exists: 'bool' = False, skip_if_file_exists: 'bool' = False, accept_hooks: 'bool' = True, keep_project_on_failure: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `context` | `dict[str, Any] \| None` | `None` | pos/kw |
| `output_dir` | `Path \| str` | `'.'` | pos/kw |
| `overwrite_if_exists` | `bool` | `False` | pos/kw |
| `skip_if_file_exists` | `bool` | `False` | pos/kw |
| `accept_hooks` | `bool` | `True` | pos/kw |
| `keep_project_on_failure` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `get_user_config`

Return the user config as a dict.

If ``default_config`` is True, ignore ``config_file`` and return default
values for the config parameters.

If ``default_config`` is a dict, merge values with defau…

```python
cookiecutter.main.get_user_config(config_file: 'str | None' = None, default_config: 'bool | dict[str, Any]' = False) -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str \| None` | `None` | pos/kw |
| `default_config` | `bool \| dict[str, Any]` | `False` | pos/kw |

**Returns:** `dict[str, Any]`

### `load`

Read json data from file.

```python
cookiecutter.main.load(replay_dir: 'Path | str', template_name: 'str') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `replay_dir` | `Path \| str` | `—` | pos/kw |
| `template_name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `prompt_for_config`

Prompt user to enter a new config.

:param dict context: Source for field names and sample values.
:param no_input: Do not prompt for user input and use only values from context.

```python
cookiecutter.main.prompt_for_config(context: 'dict[str, Any]', no_input: 'bool' = False) -> 'OrderedDict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |

**Returns:** `OrderedDict[str, Any]`

### `rmtree`

Remove a directory and all its contents. Like rm -rf on Unix.

:param path: A directory path.

```python
cookiecutter.main.rmtree(path: 'Path | str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |

### `run_pre_prompt_hook`

Run pre_prompt hook from repo directory.

:param repo_dir: Project template input directory.

```python
cookiecutter.main.run_pre_prompt_hook(repo_dir: 'Path | str') -> 'Path | str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_dir` | `Path \| str` | `—` | pos/kw |

**Returns:** `Path | str`

### `choose_nested_template`

Prompt user to select the nested template to use.

:param context: Source for field names and sample values.
:param repo_dir: Repository directory.
:param no_input: Do not prompt for user input and u…

```python
cookiecutter.prompt.choose_nested_template(context: 'dict[str, Any]', repo_dir: 'Path | str', no_input: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `repo_dir` | `Path \| str` | `—` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `create_env_with_context`

Create a jinja environment using the provided context.

```python
cookiecutter.prompt.create_env_with_context(context: 'dict[str, Any]') -> 'StrictEnvironment'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `StrictEnvironment`

### `process_json`

Load user-supplied value as a JSON dict.

:param user_value: User-supplied value to load as a JSON dict

```python
cookiecutter.prompt.process_json(user_value: 'str')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `user_value` | `str` | `—` | pos/kw |

### `prompt_and_delete`

Ask user if it's okay to delete the previously-downloaded file/directory.

If yes, delete it. If no, checks to see if the old version should be
reused. If yes, it's reused; otherwise, Cookiecutter ex…

```python
cookiecutter.prompt.prompt_and_delete(path: 'Path | str', no_input: 'bool' = False) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |

**Returns:** `bool`

### `prompt_choice_for_config`

Prompt user with a set of options to choose from.

:param no_input: Do not prompt for user input and return the first available option.

```python
cookiecutter.prompt.prompt_choice_for_config(cookiecutter_dict: 'dict[str, Any]', env: 'Environment', key: 'str', options, no_input: 'bool', prompts=None, prefix: 'str' = '') -> 'OrderedDict[str, Any] | str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cookiecutter_dict` | `dict[str, Any]` | `—` | pos/kw |
| `env` | `Environment` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `options` | `—` | `—` | pos/kw |
| `no_input` | `bool` | `—` | pos/kw |
| `prompts` | `—` | `None` | pos/kw |
| `prefix` | `str` | `''` | pos/kw |

**Returns:** `OrderedDict[str, Any] | str`

### `prompt_choice_for_template`

Prompt user with a set of options to choose from.

:param no_input: Do not prompt for user input and return the first available option.

```python
cookiecutter.prompt.prompt_choice_for_template(key: 'str', options: 'dict', no_input: 'bool') -> 'OrderedDict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key` | `str` | `—` | pos/kw |
| `options` | `dict` | `—` | pos/kw |
| `no_input` | `bool` | `—` | pos/kw |

**Returns:** `OrderedDict[str, Any]`

### `prompt_for_config`

Prompt user to enter a new config.

:param dict context: Source for field names and sample values.
:param no_input: Do not prompt for user input and use only values from context.

```python
cookiecutter.prompt.prompt_for_config(context: 'dict[str, Any]', no_input: 'bool' = False) -> 'OrderedDict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `context` | `dict[str, Any]` | `—` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |

**Returns:** `OrderedDict[str, Any]`

### `read_repo_password`

Prompt the user to enter a password.

:param question: Question to the user

```python
cookiecutter.prompt.read_repo_password(question: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `question` | `str` | `—` | pos/kw |

**Returns:** `str`

### `read_user_choice`

Prompt the user to choose from several options for the given variable.

The first item will be returned if no input happens.

:param var_name: Variable as specified in the context
:param list options…

```python
cookiecutter.prompt.read_user_choice(var_name: 'str', options: 'list', prompts=None, prefix: 'str' = '')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var_name` | `str` | `—` | pos/kw |
| `options` | `list` | `—` | pos/kw |
| `prompts` | `—` | `None` | pos/kw |
| `prefix` | `str` | `''` | pos/kw |

### `read_user_dict`

Prompt the user to provide a dictionary of data.

:param var_name: Variable as specified in the context
:param default_value: Value that will be returned if no input is provided
:return: A Python dic…

```python
cookiecutter.prompt.read_user_dict(var_name: 'str', default_value, prompts=None, prefix: 'str' = '')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var_name` | `str` | `—` | pos/kw |
| `default_value` | `—` | `—` | pos/kw |
| `prompts` | `—` | `None` | pos/kw |
| `prefix` | `str` | `''` | pos/kw |

### `read_user_variable`

Prompt user for variable and return the entered value or given default.

:param str var_name: Variable of the context to query the user
:param default_value: Value that will be returned if no input h…

```python
cookiecutter.prompt.read_user_variable(var_name: 'str', default_value, prompts=None, prefix: 'str' = '')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var_name` | `str` | `—` | pos/kw |
| `default_value` | `—` | `—` | pos/kw |
| `prompts` | `—` | `None` | pos/kw |
| `prefix` | `str` | `''` | pos/kw |

### `read_user_yes_no`

Prompt the user to reply with 'yes' or 'no' (or equivalent values).

- These input values will be converted to ``True``:
  "1", "true", "t", "yes", "y", "on"
- These input values will be converted to…

```python
cookiecutter.prompt.read_user_yes_no(var_name, default_value, prompts=None, prefix: 'str' = '')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `var_name` | `—` | `—` | pos/kw |
| `default_value` | `—` | `—` | pos/kw |
| `prompts` | `—` | `None` | pos/kw |
| `prefix` | `str` | `''` | pos/kw |

### `render_variable`

Render the next variable to be displayed in the user prompt.

Inside the prompting taken from the cookiecutter.json file, this renders
the next variable. For example, if a project_name is "Peanut But…

```python
cookiecutter.prompt.render_variable(env: 'Environment', raw: '_Raw', cookiecutter_dict: 'dict[str, Any]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `Environment` | `—` | pos/kw |
| `raw` | `_Raw` | `—` | pos/kw |
| `cookiecutter_dict` | `dict[str, Any]` | `—` | pos/kw |

**Returns:** `str`

### `rmtree`

Remove a directory and all its contents. Like rm -rf on Unix.

:param path: A directory path.

```python
cookiecutter.prompt.rmtree(path: 'Path | str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |

### `dump`

Write json data to file.

```python
cookiecutter.replay.dump(replay_dir: 'Path | str', template_name: 'str', context: 'dict[str, Any]') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `replay_dir` | `Path \| str` | `—` | pos/kw |
| `template_name` | `str` | `—` | pos/kw |
| `context` | `dict[str, Any]` | `—` | pos/kw |

### `get_file_name`

Get the name of file.

```python
cookiecutter.replay.get_file_name(replay_dir: 'Path | str', template_name: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `replay_dir` | `Path \| str` | `—` | pos/kw |
| `template_name` | `str` | `—` | pos/kw |

**Returns:** `str`

### `load`

Read json data from file.

```python
cookiecutter.replay.load(replay_dir: 'Path | str', template_name: 'str') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `replay_dir` | `Path \| str` | `—` | pos/kw |
| `template_name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `make_sure_path_exists`

Ensure that a directory exists.

:param path: A directory tree path for creation.

```python
cookiecutter.replay.make_sure_path_exists(path: 'Path | str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `Path \| str` | `—` | pos/kw |

### `clone`

Clone a repo to the current directory.

:param repo_url: Repo URL of unknown type.
:param checkout: The branch, tag or commit ID to checkout after clone.
:param clone_to_dir: The directory to clone t…

```python
cookiecutter.repository.clone(repo_url: 'str', checkout: 'str | None' = None, clone_to_dir: 'Path | str' = '.', no_input: 'bool' = False) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_url` | `str` | `—` | pos/kw |
| `checkout` | `str \| None` | `None` | pos/kw |
| `clone_to_dir` | `Path \| str` | `'.'` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |

**Returns:** `str`

### `determine_repo_dir`

Locate the repository directory from a template reference.

Applies repository abbreviations to the template reference.
If the template refers to a repository URL, clone it.
If the template is a path…

```python
cookiecutter.repository.determine_repo_dir(template: 'str', abbreviations: 'dict[str, str]', clone_to_dir: 'Path | str', checkout: 'str | None', no_input: 'bool', password: 'str | None' = None, directory: 'str | None' = None) -> 'tuple[str, bool]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `template` | `str` | `—` | pos/kw |
| `abbreviations` | `dict[str, str]` | `—` | pos/kw |
| `clone_to_dir` | `Path \| str` | `—` | pos/kw |
| `checkout` | `str \| None` | `—` | pos/kw |
| `no_input` | `bool` | `—` | pos/kw |
| `password` | `str \| None` | `None` | pos/kw |
| `directory` | `str \| None` | `None` | pos/kw |

**Returns:** `tuple[str, bool]`

### `expand_abbreviations`

Expand abbreviations in a template name.

:param template: The project template name.
:param abbreviations: Abbreviation definitions.

```python
cookiecutter.repository.expand_abbreviations(template: 'str', abbreviations: 'dict[str, str]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `template` | `str` | `—` | pos/kw |
| `abbreviations` | `dict[str, str]` | `—` | pos/kw |

**Returns:** `str`

### `is_repo_url`

Return True if value is a repository URL.

```python
cookiecutter.repository.is_repo_url(value: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `is_zip_file`

Return True if value is a zip file.

```python
cookiecutter.repository.is_zip_file(value: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `repository_has_cookiecutter_json`

Determine if `repo_directory` contains a `cookiecutter.json` file.

:param repo_directory: The candidate repository directory.
:return: True if the `repo_directory` is valid, else False.

```python
cookiecutter.repository.repository_has_cookiecutter_json(repo_directory: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo_directory` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `unzip`

Download and unpack a zipfile at a given URI.

This will download the zipfile to the cookiecutter repository,
and unpack into a temporary directory.

:param zip_uri: The URI for the zipfile.
:param i…

```python
cookiecutter.repository.unzip(zip_uri: 'str', is_url: 'bool', clone_to_dir: 'Path | str' = '.', no_input: 'bool' = False, password: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `zip_uri` | `str` | `—` | pos/kw |
| `is_url` | `bool` | `—` | pos/kw |
| `clone_to_dir` | `Path \| str` | `'.'` | pos/kw |
| `no_input` | `bool` | `False` | pos/kw |
| `password` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

## Methods

### `cookiecutter.environment.StrictEnvironment` methods

### `add_extension`

Adds an extension after the environment was created.

.. versionadded:: 2.5

```python
cookiecutter.environment.StrictEnvironment.add_extension(self, extension: Union[str, Type[ForwardRef('Extension')]]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `extension` | `Union` | `—` | pos/kw |

### `call_filter`

Invoke a filter on a value the same way the compiler does.

This might return a coroutine if the filter is running from an
environment in async mode and the filter supports async
execution. It's your…

```python
cookiecutter.environment.StrictEnvironment.call_filter(self, name: str, value: Any, args: Optional[Sequence[Any]] = None, kwargs: Optional[Mapping[str, Any]] = None, context: Optional[jinja2.runtime.Context] = None, eval_ctx: Optional[jinja2.nodes.EvalContext] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `context` | `Optional` | `None` | pos/kw |
| `eval_ctx` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Any`

### `call_test`

Invoke a test on a value the same way the compiler does.

This might return a coroutine if the test is running from an
environment in async mode and the test supports async execution.
It's your respo…

```python
cookiecutter.environment.StrictEnvironment.call_test(self, name: str, value: Any, args: Optional[Sequence[Any]] = None, kwargs: Optional[Mapping[str, Any]] = None, context: Optional[jinja2.runtime.Context] = None, eval_ctx: Optional[jinja2.nodes.EvalContext] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `context` | `Optional` | `None` | pos/kw |
| `eval_ctx` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Any`

### `compile`

Compile a node or template source code.  The `name` parameter is
the load name of the template after it was joined using
:meth:`join_path` if necessary, not the filename on the file system.
the `file…

```python
cookiecutter.environment.StrictEnvironment.compile(self, source: Union[str, jinja2.nodes.Template], name: Optional[str] = None, filename: Optional[str] = None, raw: bool = False, defer_init: bool = False) -> Union[str, code]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `Union` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |
| `raw` | `bool` | `False` | pos/kw |
| `defer_init` | `bool` | `False` | pos/kw |

**Returns:** `typing.Union[str, code]`

### `compile_expression`

A handy helper method that returns a callable that accepts keyword
arguments that appear as variables in the expression.  If called it
returns the result of the expression.

This is useful if applica…

```python
cookiecutter.environment.StrictEnvironment.compile_expression(self, source: str, undefined_to_none: bool = True) -> 'TemplateExpression'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `undefined_to_none` | `bool` | `True` | pos/kw |

**Returns:** `TemplateExpression`

### `compile_templates`

Finds all the templates the loader can find, compiles them
and stores them in `target`.  If `zip` is `None`, instead of in a
zipfile, the templates will be stored in a directory.
By default a deflate…

```python
cookiecutter.environment.StrictEnvironment.compile_templates(self, target: Union[str, ForwardRef('os.PathLike[str]')], extensions: Optional[Collection[str]] = None, filter_func: Optional[Callable[[str], bool]] = None, zip: Optional[str] = 'deflated', log_function: Optional[Callable[[str], NoneType]] = None, ignore_errors: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `target` | `Union` | `—` | pos/kw |
| `extensions` | `Optional` | `None` | pos/kw |
| `filter_func` | `Optional` | `None` | pos/kw |
| `zip` | `Optional` | `'deflated'` | pos/kw |
| `log_function` | `Optional` | `None` | pos/kw |
| `ignore_errors` | `bool` | `True` | pos/kw |

### `extend`

Add the items to the instance of the environment if they do not exist
yet.  This is used by :ref:`extensions <writing-extensions>` to register
callbacks and configuration values without breaking inhe…

```python
cookiecutter.environment.StrictEnvironment.extend(self, **attributes: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attributes` | `Any` | `—` | **kwargs |

### `from_string`

Load a template from a source string without using
:attr:`loader`.

:param source: Jinja source to compile into a template.
:param globals: Extend the environment :attr:`globals` with
    these extra…

```python
cookiecutter.environment.StrictEnvironment.from_string(self, source: Union[str, jinja2.nodes.Template], globals: Optional[MutableMapping[str, Any]] = None, template_class: Optional[Type[ForwardRef('Template')]] = None) -> 'Template'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `Union` | `—` | pos/kw |
| `globals` | `Optional` | `None` | pos/kw |
| `template_class` | `Optional` | `None` | pos/kw |

**Returns:** `Template`

### `get_or_select_template`

Use :meth:`select_template` if an iterable of template names
is given, or :meth:`get_template` if one name is given.

.. versionadded:: 2.3

```python
cookiecutter.environment.StrictEnvironment.get_or_select_template(self, template_name_or_list: Union[str, ForwardRef('Template'), List[Union[str, ForwardRef('Template')]]], parent: Optional[str] = None, globals: Optional[MutableMapping[str, Any]] = None) -> 'Template'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template_name_or_list` | `Union` | `—` | pos/kw |
| `parent` | `Optional` | `None` | pos/kw |
| `globals` | `Optional` | `None` | pos/kw |

**Returns:** `Template`

### `get_template`

Load a template by name with :attr:`loader` and return a
:class:`Template`. If the template does not exist a
:exc:`TemplateNotFound` exception is raised.

:param name: Name of the template to load. W…

```python
cookiecutter.environment.StrictEnvironment.get_template(self, name: Union[str, ForwardRef('Template')], parent: Optional[str] = None, globals: Optional[MutableMapping[str, Any]] = None) -> 'Template'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `Union` | `—` | pos/kw |
| `parent` | `Optional` | `None` | pos/kw |
| `globals` | `Optional` | `None` | pos/kw |

**Returns:** `Template`

### `getattr`

Get an item or attribute of an object but prefer the attribute.
Unlike :meth:`getitem` the attribute *must* be a string.

```python
cookiecutter.environment.StrictEnvironment.getattr(self, obj: Any, attribute: str) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `Any` | `—` | pos/kw |
| `attribute` | `str` | `—` | pos/kw |

**Returns:** `typing.Any`

### `getitem`

Get an item or attribute of an object but prefer the item.

```python
cookiecutter.environment.StrictEnvironment.getitem(self, obj: Any, argument: Union[str, Any]) -> Union[Any, jinja2.runtime.Undefined]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `Any` | `—` | pos/kw |
| `argument` | `Union` | `—` | pos/kw |

**Returns:** `typing.Union[typing.Any, jinja2.runtime.Undefined]`

### `handle_exception`

Exception handling helper.  This is used internally to either raise
rewritten exceptions or return a rendered traceback for the template.

```python
cookiecutter.environment.StrictEnvironment.handle_exception(self, source: Optional[str] = None) -> 'te.NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `Optional` | `None` | pos/kw |

**Returns:** `te.NoReturn`

### `iter_extensions`

Iterates over the extensions by priority.

```python
cookiecutter.environment.StrictEnvironment.iter_extensions(self) -> Iterator[ForwardRef('Extension')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Iterator[ForwardRef('Extension')]`

### `join_path`

Join a template with the parent.  By default all the lookups are
relative to the loader root so this method returns the `template`
parameter unchanged, but if the paths should be relative to the
pare…

```python
cookiecutter.environment.StrictEnvironment.join_path(self, template: str, parent: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `parent` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `lex`

Lex the given sourcecode and return a generator that yields
tokens as tuples in the form ``(lineno, token_type, value)``.
This can be useful for :ref:`extension development <writing-extensions>`
and…

```python
cookiecutter.environment.StrictEnvironment.lex(self, source: str, name: Optional[str] = None, filename: Optional[str] = None) -> Iterator[Tuple[int, str, str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Iterator[typing.Tuple[int, str, str]]`

### `list_templates`

Returns a list of templates for this environment.  This requires
that the loader supports the loader's
:meth:`~BaseLoader.list_templates` method.

If there are other files in the template folder besi…

```python
cookiecutter.environment.StrictEnvironment.list_templates(self, extensions: Optional[Collection[str]] = None, filter_func: Optional[Callable[[str], bool]] = None) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `extensions` | `Optional` | `None` | pos/kw |
| `filter_func` | `Optional` | `None` | pos/kw |

**Returns:** `typing.List[str]`

### `make_globals`

Make the globals map for a template. Any given template
globals overlay the environment :attr:`globals`.

Returns a :class:`collections.ChainMap`. This allows any changes
to a template's globals to o…

```python
cookiecutter.environment.StrictEnvironment.make_globals(self, d: Optional[MutableMapping[str, Any]]) -> MutableMapping[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `d` | `Optional` | `—` | pos/kw |

**Returns:** `typing.MutableMapping[str, typing.Any]`

### `overlay`

Create a new overlay environment that shares all the data with the
current environment except for cache and the overridden attributes.
Extensions cannot be removed for an overlayed environment.  An o…

```python
cookiecutter.environment.StrictEnvironment.overlay(self, block_start_string: str = missing, block_end_string: str = missing, variable_start_string: str = missing, variable_end_string: str = missing, comment_start_string: str = missing, comment_end_string: str = missing, line_statement_prefix: Optional[str] = missing, line_comment_prefix: Optional[str] = missing, trim_blocks: bool = missing, lstrip_blocks: bool = missing, newline_sequence: "te.Literal['\\n', '\\r\\n', '\\r']" = missing, keep_trailing_newline: bool = missing, extensions: Sequence[Union[str, Type[ForwardRef('Extension')]]] = missing, optimized: bool = missing, undefined: Type[jinja2.runtime.Undefined] = missing, finalize: Optional[Callable[..., Any]] = missing, autoescape: Union[bool, Callable[[Optional[str]], bool]] = missing, loader: Optional[ForwardRef('BaseLoader')] = missing, cache_size: int = missing, auto_reload: bool = missing, bytecode_cache: Optional[ForwardRef('BytecodeCache')] = missing, enable_async: bool = missing) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `block_start_string` | `str` | `missing` | pos/kw |
| `block_end_string` | `str` | `missing` | pos/kw |
| `variable_start_string` | `str` | `missing` | pos/kw |
| `variable_end_string` | `str` | `missing` | pos/kw |
| `comment_start_string` | `str` | `missing` | pos/kw |
| `comment_end_string` | `str` | `missing` | pos/kw |
| `line_statement_prefix` | `Optional` | `missing` | pos/kw |
| `line_comment_prefix` | `Optional` | `missing` | pos/kw |
| `trim_blocks` | `bool` | `missing` | pos/kw |
| `lstrip_blocks` | `bool` | `missing` | pos/kw |
| `newline_sequence` | `te.Literal['\n', '\r\n', '\r']` | `missing` | pos/kw |
| `keep_trailing_newline` | `bool` | `missing` | pos/kw |
| `extensions` | `Sequence` | `missing` | pos/kw |
| `optimized` | `bool` | `missing` | pos/kw |
| `undefined` | `Type` | `missing` | pos/kw |
| `finalize` | `Optional` | `missing` | pos/kw |
| `autoescape` | `Union` | `missing` | pos/kw |
| `loader` | `Optional` | `missing` | pos/kw |
| `cache_size` | `int` | `missing` | pos/kw |
| `auto_reload` | `bool` | `missing` | pos/kw |
| `bytecode_cache` | `Optional` | `missing` | pos/kw |
| `enable_async` | `bool` | `missing` | pos/kw |

**Returns:** `te.Self`

### `parse`

Parse the sourcecode and return the abstract syntax tree.  This
tree of nodes is used by the compiler to convert the template into
executable source- or bytecode.  This is useful for debugging or to…

```python
cookiecutter.environment.StrictEnvironment.parse(self, source: str, name: Optional[str] = None, filename: Optional[str] = None) -> jinja2.nodes.Template
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Template'>`

### `preprocess`

Preprocesses the source with all extensions.  This is automatically
called for all parsing and compiling methods but *not* for :meth:`lex`
because there you usually only want the actual source tokeni…

```python
cookiecutter.environment.StrictEnvironment.preprocess(self, source: str, name: Optional[str] = None, filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `select_template`

Like :meth:`get_template`, but tries loading multiple names.
If none of the names can be loaded a :exc:`TemplatesNotFound`
exception is raised.

:param names: List of template names to try loading in…

```python
cookiecutter.environment.StrictEnvironment.select_template(self, names: Iterable[Union[str, ForwardRef('Template')]], parent: Optional[str] = None, globals: Optional[MutableMapping[str, Any]] = None) -> 'Template'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `names` | `Iterable` | `—` | pos/kw |
| `parent` | `Optional` | `None` | pos/kw |
| `globals` | `Optional` | `None` | pos/kw |

**Returns:** `Template`

### `cookiecutter.extensions.JsonifyExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
cookiecutter.extensions.JsonifyExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
cookiecutter.extensions.JsonifyExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
cookiecutter.extensions.JsonifyExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
cookiecutter.extensions.JsonifyExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

If any of the :attr:`tags` matched this method is called with the
parser as first argument.  The token the parser stream is pointing at
is the name token that matched.  This method has to return one…

```python
cookiecutter.extensions.JsonifyExtension.parse(self, parser: 'Parser') -> Union[jinja2.nodes.Node, List[jinja2.nodes.Node]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `Parser` | `—` | pos/kw |

**Returns:** `typing.Union[jinja2.nodes.Node, typing.List[jinja2.nodes.Node]]`

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
cookiecutter.extensions.JsonifyExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `cookiecutter.extensions.RandomStringExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
cookiecutter.extensions.RandomStringExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
cookiecutter.extensions.RandomStringExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
cookiecutter.extensions.RandomStringExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
cookiecutter.extensions.RandomStringExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

If any of the :attr:`tags` matched this method is called with the
parser as first argument.  The token the parser stream is pointing at
is the name token that matched.  This method has to return one…

```python
cookiecutter.extensions.RandomStringExtension.parse(self, parser: 'Parser') -> Union[jinja2.nodes.Node, List[jinja2.nodes.Node]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `Parser` | `—` | pos/kw |

**Returns:** `typing.Union[jinja2.nodes.Node, typing.List[jinja2.nodes.Node]]`

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
cookiecutter.extensions.RandomStringExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `cookiecutter.extensions.SlugifyExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
cookiecutter.extensions.SlugifyExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
cookiecutter.extensions.SlugifyExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
cookiecutter.extensions.SlugifyExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
cookiecutter.extensions.SlugifyExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

If any of the :attr:`tags` matched this method is called with the
parser as first argument.  The token the parser stream is pointing at
is the name token that matched.  This method has to return one…

```python
cookiecutter.extensions.SlugifyExtension.parse(self, parser: 'Parser') -> Union[jinja2.nodes.Node, List[jinja2.nodes.Node]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `Parser` | `—` | pos/kw |

**Returns:** `typing.Union[jinja2.nodes.Node, typing.List[jinja2.nodes.Node]]`

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
cookiecutter.extensions.SlugifyExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `cookiecutter.extensions.TimeExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
cookiecutter.extensions.TimeExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
cookiecutter.extensions.TimeExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
cookiecutter.extensions.TimeExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
cookiecutter.extensions.TimeExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

Parse datetime template and add datetime value.

```python
cookiecutter.extensions.TimeExtension.parse(self, parser: 'Parser') -> 'nodes.Output'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `Parser` | `—` | pos/kw |

**Returns:** `nodes.Output`

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
cookiecutter.extensions.TimeExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `cookiecutter.extensions.UUIDExtension` methods

### `attr`

Return an attribute node for the current extension.  This is useful
to pass constants on extensions to generated template code.

::

    self.attr('_my_attribute', lineno=lineno)

```python
cookiecutter.extensions.UUIDExtension.attr(self, name: str, lineno: Optional[int] = None) -> jinja2.nodes.ExtensionAttribute
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.ExtensionAttribute'>`

### `bind`

Create a copy of this extension bound to another environment.

```python
cookiecutter.extensions.UUIDExtension.bind(self, environment: jinja2.environment.Environment) -> 'te.Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `environment` | `Environment` | `—` | pos/kw |

**Returns:** `te.Self`

### `call_method`

Call a method of the extension.  This is a shortcut for
:meth:`attr` + :class:`jinja2.nodes.Call`.

```python
cookiecutter.extensions.UUIDExtension.call_method(self, name: str, args: Optional[List[jinja2.nodes.Expr]] = None, kwargs: Optional[List[jinja2.nodes.Keyword]] = None, dyn_args: Optional[jinja2.nodes.Expr] = None, dyn_kwargs: Optional[jinja2.nodes.Expr] = None, lineno: Optional[int] = None) -> jinja2.nodes.Call
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `dyn_args` | `Optional` | `None` | pos/kw |
| `dyn_kwargs` | `Optional` | `None` | pos/kw |
| `lineno` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'jinja2.nodes.Call'>`

### `filter_stream`

It's passed a :class:`~jinja2.lexer.TokenStream` that can be used
to filter tokens returned.  This method has to return an iterable of
:class:`~jinja2.lexer.Token`\s, but it doesn't have to return a…

```python
cookiecutter.extensions.UUIDExtension.filter_stream(self, stream: 'TokenStream') -> Union[ForwardRef('TokenStream'), Iterable[ForwardRef('Token')]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `stream` | `TokenStream` | `—` | pos/kw |

**Returns:** `typing.Union[ForwardRef('TokenStream'), typing.Iterable[ForwardRef('Token')]]`

### `parse`

If any of the :attr:`tags` matched this method is called with the
parser as first argument.  The token the parser stream is pointing at
is the name token that matched.  This method has to return one…

```python
cookiecutter.extensions.UUIDExtension.parse(self, parser: 'Parser') -> Union[jinja2.nodes.Node, List[jinja2.nodes.Node]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `Parser` | `—` | pos/kw |

**Returns:** `typing.Union[jinja2.nodes.Node, typing.List[jinja2.nodes.Node]]`

### `preprocess`

This method is called before the actual lexing and can be used to
preprocess the source.  The `filename` is optional.  The return value
must be the preprocessed source.

```python
cookiecutter.extensions.UUIDExtension.preprocess(self, source: str, name: Optional[str], filename: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `source` | `str` | `—` | pos/kw |
| `name` | `Optional` | `—` | pos/kw |
| `filename` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `cookiecutter.generate.YesNoPrompt` methods

### `ask`

Shortcut to construct and run a prompt loop and return the result.

Example:
    >>> filename = Prompt.ask("Enter a filename")

Args:
    prompt (TextType, optional): Prompt text. Defaults to "".…

```python
cookiecutter.generate.YesNoPrompt.ask(prompt: Union[str, ForwardRef('Text')] = '', *, console: Optional[rich.console.Console] = None, password: bool = False, choices: Optional[List[str]] = None, case_sensitive: bool = True, show_default: bool = True, show_choices: bool = True, default: Any = Ellipsis, stream: Optional[TextIO] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt` | `Union` | `''` | pos/kw |
| `console` | `Optional` | `None` | kw |
| `password` | `bool` | `False` | kw |
| `choices` | `Optional` | `None` | kw |
| `case_sensitive` | `bool` | `True` | kw |
| `show_default` | `bool` | `True` | kw |
| `show_choices` | `bool` | `True` | kw |
| `default` | `Any` | `Ellipsis` | kw |
| `stream` | `Optional` | `None` | kw |

**Returns:** `typing.Any`

### `check_choice`

Check value is in the list of valid choices.

Args:
    value (str): Value entered by user.

Returns:
    bool: True if choice was valid, otherwise False.

```python
cookiecutter.generate.YesNoPrompt.check_choice(self, value: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `get_input`

Get input from user.

Args:
    console (Console): Console instance.
    prompt (TextType): Prompt text.
    password (bool): Enable password entry.

Returns:
    str: String from user.

```python
cookiecutter.generate.YesNoPrompt.get_input(console: rich.console.Console, prompt: Union[str, ForwardRef('Text')], password: bool, stream: Optional[TextIO] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `console` | `Console` | `—` | pos/kw |
| `prompt` | `Union` | `—` | pos/kw |
| `password` | `bool` | `—` | pos/kw |
| `stream` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `make_prompt`

Make prompt text.

Args:
    default (DefaultType): Default value.

Returns:
    Text: Text to display in prompt.

```python
cookiecutter.generate.YesNoPrompt.make_prompt(self, default: ~DefaultType) -> rich.text.Text
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `DefaultType` | `—` | pos/kw |

**Returns:** `<class 'rich.text.Text'>`

### `on_validate_error`

Called to handle validation error.

Args:
    value (str): String entered by user.
    error (InvalidResponse): Exception instance the initiated the error.

```python
cookiecutter.generate.YesNoPrompt.on_validate_error(self, value: str, error: rich.prompt.InvalidResponse) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |
| `error` | `InvalidResponse` | `—` | pos/kw |

### `pre_prompt`

Hook to display something before the prompt.

```python
cookiecutter.generate.YesNoPrompt.pre_prompt(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_response`

Convert choices to a bool.

```python
cookiecutter.generate.YesNoPrompt.process_response(self, value: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `render_default`

Render the default as (y) or (n) rather than True/False.

```python
cookiecutter.generate.YesNoPrompt.render_default(self, default: ~DefaultType) -> rich.text.Text
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `DefaultType` | `—` | pos/kw |

**Returns:** `<class 'rich.text.Text'>`

### `cookiecutter.prompt.JsonPrompt` methods

### `ask`

Shortcut to construct and run a prompt loop and return the result.

Example:
    >>> filename = Prompt.ask("Enter a filename")

Args:
    prompt (TextType, optional): Prompt text. Defaults to "".…

```python
cookiecutter.prompt.JsonPrompt.ask(prompt: Union[str, ForwardRef('Text')] = '', *, console: Optional[rich.console.Console] = None, password: bool = False, choices: Optional[List[str]] = None, case_sensitive: bool = True, show_default: bool = True, show_choices: bool = True, default: Any = Ellipsis, stream: Optional[TextIO] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt` | `Union` | `''` | pos/kw |
| `console` | `Optional` | `None` | kw |
| `password` | `bool` | `False` | kw |
| `choices` | `Optional` | `None` | kw |
| `case_sensitive` | `bool` | `True` | kw |
| `show_default` | `bool` | `True` | kw |
| `show_choices` | `bool` | `True` | kw |
| `default` | `Any` | `Ellipsis` | kw |
| `stream` | `Optional` | `None` | kw |

**Returns:** `typing.Any`

### `check_choice`

Check value is in the list of valid choices.

Args:
    value (str): Value entered by user.

Returns:
    bool: True if choice was valid, otherwise False.

```python
cookiecutter.prompt.JsonPrompt.check_choice(self, value: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `get_input`

Get input from user.

Args:
    console (Console): Console instance.
    prompt (TextType): Prompt text.
    password (bool): Enable password entry.

Returns:
    str: String from user.

```python
cookiecutter.prompt.JsonPrompt.get_input(console: rich.console.Console, prompt: Union[str, ForwardRef('Text')], password: bool, stream: Optional[TextIO] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `console` | `Console` | `—` | pos/kw |
| `prompt` | `Union` | `—` | pos/kw |
| `password` | `bool` | `—` | pos/kw |
| `stream` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `make_prompt`

Make prompt text.

Args:
    default (DefaultType): Default value.

Returns:
    Text: Text to display in prompt.

```python
cookiecutter.prompt.JsonPrompt.make_prompt(self, default: ~DefaultType) -> rich.text.Text
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `DefaultType` | `—` | pos/kw |

**Returns:** `<class 'rich.text.Text'>`

### `on_validate_error`

Called to handle validation error.

Args:
    value (str): String entered by user.
    error (InvalidResponse): Exception instance the initiated the error.

```python
cookiecutter.prompt.JsonPrompt.on_validate_error(self, value: str, error: rich.prompt.InvalidResponse) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |
| `error` | `InvalidResponse` | `—` | pos/kw |

### `pre_prompt`

Hook to display something before the prompt.

```python
cookiecutter.prompt.JsonPrompt.pre_prompt(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_response`

Convert choices to a dict.

```python
cookiecutter.prompt.JsonPrompt.process_response(value: 'str') -> 'dict[str, Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `str` | `—` | pos/kw |

**Returns:** `dict[str, Any]`

### `render_default`

Turn the supplied default in to a Text instance.

Args:
    default (DefaultType): Default value.

Returns:
    Text: Text containing rendering of default value.

```python
cookiecutter.prompt.JsonPrompt.render_default(self, default: ~DefaultType) -> rich.text.Text
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `DefaultType` | `—` | pos/kw |

**Returns:** `<class 'rich.text.Text'>`

### `cookiecutter.prompt.YesNoPrompt` methods

### `ask`

Shortcut to construct and run a prompt loop and return the result.

Example:
    >>> filename = Prompt.ask("Enter a filename")

Args:
    prompt (TextType, optional): Prompt text. Defaults to "".…

```python
cookiecutter.prompt.YesNoPrompt.ask(prompt: Union[str, ForwardRef('Text')] = '', *, console: Optional[rich.console.Console] = None, password: bool = False, choices: Optional[List[str]] = None, case_sensitive: bool = True, show_default: bool = True, show_choices: bool = True, default: Any = Ellipsis, stream: Optional[TextIO] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prompt` | `Union` | `''` | pos/kw |
| `console` | `Optional` | `None` | kw |
| `password` | `bool` | `False` | kw |
| `choices` | `Optional` | `None` | kw |
| `case_sensitive` | `bool` | `True` | kw |
| `show_default` | `bool` | `True` | kw |
| `show_choices` | `bool` | `True` | kw |
| `default` | `Any` | `Ellipsis` | kw |
| `stream` | `Optional` | `None` | kw |

**Returns:** `typing.Any`

### `check_choice`

Check value is in the list of valid choices.

Args:
    value (str): Value entered by user.

Returns:
    bool: True if choice was valid, otherwise False.

```python
cookiecutter.prompt.YesNoPrompt.check_choice(self, value: str) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `get_input`

Get input from user.

Args:
    console (Console): Console instance.
    prompt (TextType): Prompt text.
    password (bool): Enable password entry.

Returns:
    str: String from user.

```python
cookiecutter.prompt.YesNoPrompt.get_input(console: rich.console.Console, prompt: Union[str, ForwardRef('Text')], password: bool, stream: Optional[TextIO] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `console` | `Console` | `—` | pos/kw |
| `prompt` | `Union` | `—` | pos/kw |
| `password` | `bool` | `—` | pos/kw |
| `stream` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `make_prompt`

Make prompt text.

Args:
    default (DefaultType): Default value.

Returns:
    Text: Text to display in prompt.

```python
cookiecutter.prompt.YesNoPrompt.make_prompt(self, default: ~DefaultType) -> rich.text.Text
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `DefaultType` | `—` | pos/kw |

**Returns:** `<class 'rich.text.Text'>`

### `on_validate_error`

Called to handle validation error.

Args:
    value (str): String entered by user.
    error (InvalidResponse): Exception instance the initiated the error.

```python
cookiecutter.prompt.YesNoPrompt.on_validate_error(self, value: str, error: rich.prompt.InvalidResponse) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |
| `error` | `InvalidResponse` | `—` | pos/kw |

### `pre_prompt`

Hook to display something before the prompt.

```python
cookiecutter.prompt.YesNoPrompt.pre_prompt(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `process_response`

Convert choices to a bool.

```python
cookiecutter.prompt.YesNoPrompt.process_response(self, value: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `render_default`

Render the default as (y) or (n) rather than True/False.

```python
cookiecutter.prompt.YesNoPrompt.render_default(self, default: ~DefaultType) -> rich.text.Text
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `DefaultType` | `—` | pos/kw |

**Returns:** `<class 'rich.text.Text'>`

### `cookiecutter.utils.StrictEnvironment` methods

### `add_extension`

Adds an extension after the environment was created.

.. versionadded:: 2.5

```python
cookiecutter.utils.StrictEnvironment.add_extension(self, extension: Union[str, Type[ForwardRef('Extension')]]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `extension` | `Union` | `—` | pos/kw |

### `call_filter`

Invoke a filter on a value the same way the compiler does.

This might return a coroutine if the filter is running from an
environment in async mode and the filter supports async
execution. It's your…

```python
cookiecutter.utils.StrictEnvironment.call_filter(self, name: str, value: Any, args: Optional[Sequence[Any]] = None, kwargs: Optional[Mapping[str, Any]] = None, context: Optional[jinja2.runtime.Context] = None, eval_ctx: Optional[jinja2.nodes.EvalContext] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `context` | `Optional` | `None` | pos/kw |
| `eval_ctx` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Any`

### `call_test`

Invoke a test on a value the same way the compiler does.

This might return a coroutine if the test is running from an
environment in async mode and the test supports async execution.
It's your respo…

```python
cookiecutter.utils.StrictEnvironment.call_test(self, name: str, value: Any, args: Optional[Sequence[Any]] = None, kwargs: Optional[Mapping[str, Any]] = None, context: Optional[jinja2.runtime.Context] = None, eval_ctx: Optional[jinja2.nodes.EvalContext] = None) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `args` | `Optional` | `None` | pos/kw |
| `kwargs` | `Optional` | `None` | pos/kw |
| `context` | `Optional` | `None` | pos/kw |
| `eval_ctx` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Any`


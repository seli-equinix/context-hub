---
name: package
description: "Safety CLI for scanning Python dependencies for vulnerabilities and license issues"
metadata:
  languages: "python"
  versions: "3.7.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "safety,python,security,vulnerability-scanning,license-compliance,cli,dependencies,Version-Sensitive,Alert,SafetyPolicyFile,convert,fail,fail_if_unrecognized_keys,fail_if_wrong_bool_value,get_metavar,get_missing_message,shell_complete,split_envvar_value,to_info_dict,get_context_settings,get_safety_cli_legacy_group,create_branch,delete_branch,Requirement,convert_semver,get_hashes,parse,update_version,RequirementFile,iter_lines,parse_dependencies,parse_index_server,resolve_file,get_meta_http_headers,cvss3_score_to_label,fetch_changelog,generate_body,generate_branch_name,generate_commit_message,generate_issue_body,generate_issue_title,generate_title,get_fix_hint_for_unpinned,get_hint,get_specifier_range_info,get_unpinned_hint,git_sha1,highest_base_score,is_pinned_requirement,require_files_report,apply_asyncio_patch,auth,auth_options,build_client_session,inject_session,proxy_options,Auth,get_auth_method,is_valid,refresh_from,SafetyCLISubGroup,add_command,collect_usage_pieces,command,format_commands,format_epilog,format_help,format_help_text,format_options,format_usage,get_command,get_help,get_help_option,get_help_option_names,get_params,get_short_help_str,get_usage,group,invoke,list_commands,main,make_context,make_parser,parse_args,resolve_command,result_callback,clean_session,emit_auth_completed,emit_auth_started,fail_if_authenticated,get_auth_info,get_authorization_data,get_command_for,get_token,get_version,handle_cmd_exception,initialize,initialize_event_bus,is_email_verified,login,logout,notify,pass_safety_cli_obj,process_browser_callback,register,render_email_note,render_successful_login,status,DependentOption,add_to_parser,consume_value,get_default,get_error_hint,get_help_extra,get_help_record,get_usage_pieces,handle_parse_result,make_metavar,process_value,prompt_for_value,resolve_envvar_value,type_cast_value,value_from_envvar,value_is_missing,Organization,to_dict,S3PresignedAdapter,add_headers,build_connection_pool_key_attributes,build_response,cert_verify,close,get_connection,get_connection_with_tls_context,init_poolmanager,proxy_headers,proxy_manager_for,request_url,send,SafetyAuthSession,audit_packages,check_project,check_updates,client_auth,create_authorization_url,delete,download_policy,ensure_active_token,fetch_access_token,fetch_openid_config,fetch_token,fetch_user_info,get,get_adapter,get_authentication_type,get_credential,get_redirect_target,head,introspect_token,is_using_auth_credentials,merge_environment_settings,mount,options,parse_response_token,patch,post,prepare_request,project,SafetyCLI,SafetyContext,Stage,get_host_config,get_keys,get_organization,get_proxy_config,get_proxy_dict,get_redirect_url,get_token_data,load_auth_session,save_auth_config,get_config_setting"
---

# safety — package

## Install

```bash
pip install safety
```

## Imports

```python
import safety
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `Alert` | Class | Data class for storing alert details.  Attributes:     report (Any): The report… |
| `SafetyPolicyFile` | Class | Custom Safety Policy file to hold validations. |
| `convert` | Method | Convert the parameter value to a Safety policy file.  Args:     value (Any): Th… |
| `fail` | Method | Helper method to fail with an invalid value message. |
| `fail_if_unrecognized_keys` | Method | Fail if unrecognized keys are found in the policy file.  Args:     used_keys (L… |
| `fail_if_wrong_bool_value` | Method | Fail if a boolean value is invalid.  Args:     keyword (str): The keyword.… |
| `get_metavar` | Method | Returns the metavar default for this param if it provides one. |
| `get_missing_message` | Method | Optionally might return extra information about a missing parameter.  .. versio… |
| `shell_complete` | Method | Return a special completion marker that tells the completion system to use the… |
| `split_envvar_value` | Method | Given a value from an environment variable this splits it up into small chunks… |
| `to_info_dict` | Method | Convert the object to an info dictionary.  Returns:     Dict[str, Any]: The inf… |
| `get_context_settings` | Function |  |
| `get_safety_cli_legacy_group` | Function |  |
| `create_branch` | Function | Create a new branch in the given GitHub repository.  Args:     repo (Any): The… |
| `delete_branch` | Function | Delete a branch from the given GitHub repository.  Args:     repo (Any): The Gi… |
| `Requirement` | Class | Class representing a single requirement.  Attributes:     name (str): The name… |
| `convert_semver` | Method | Converts a version string to a semantic version dictionary.  Args:     version… |
| `get_hashes` | Method | Retrieves the hashes for a specific version from PyPI.  Args:     version (str)… |
| `parse` | Method | Parses a requirement from a line of text.  Args:     s (str): The line of text.… |
| `update_version` | Method | Updates the version of the requirement in the content.  Args:     content (str)… |
| `RequirementFile` | Class | Class representing a requirements file with its content and metadata.  Attribut… |
| `iter_lines` | Method | Iterates over lines in the content starting from a specific line number.  Args:… |
| `parse_dependencies` | Method | Parses the dependencies from the content based on the file type.  Args:     fil… |
| `parse_index_server` | Method | Parses the index server from a given line.  Args:     line (str): The line to p… |
| `resolve_file` | Method | Resolves a file path from a given line.  Args:     file_path (str): The file pa… |
| `get_meta_http_headers` | Function | Get the metadata headers for the client.  Returns:   Dict[str, str]: The metada… |
| `cvss3_score_to_label` | Function | Converts a CVSS v3 score to a severity label.  Args:     score (float): The CVS… |
| `fetch_changelog` | Function | Fetches the changelog for a package from a specified version to another version… |
| `generate_body` | Function | Generates the body content for a pull request.  Args:     pkg (str): The packag… |
| `generate_branch_name` | Function | Generates a branch name for a given package and remediation.  Args:     pkg (st… |
| `generate_commit_message` | Function | Generates a commit message for a given package and remediation.  Args:     pkg… |
| `generate_issue_body` | Function | Generates the body content for an issue.  Args:     pkg (str): The package name… |
| `generate_issue_title` | Function | Generates an issue title for a given package and remediation.  Args:     pkg (s… |
| `generate_title` | Function | Generates a title for a pull request or issue.  Args:     pkg (str): The packag… |
| `get_fix_hint_for_unpinned` | Function | Get the fix hint for unpinned dependencies.  Args:     remediation (Dict[str, A… |
| `get_hint` | Function | Generates a hint for a given remediation.  Args:     remediation (Dict[str, Any… |
| `get_meta_http_headers` | Function | Get the metadata headers for the client.  Returns:   Dict[str, str]: The metada… |
| `get_specifier_range_info` | Function | Get the specifier range information.  Args:     style (bool, optional): Whether… |
| `get_unpinned_hint` | Function | Get the hint for unpinned packages.  Args:     pkg (str): The package name.  Re… |
| `git_sha1` | Function | Calculates the SHA-1 hash of the given raw contents.  Args:     raw_contents (b… |
| `highest_base_score` | Function | Calculates the highest CVSS base score from a list of vulnerabilities.  Args:… |
| `is_pinned_requirement` | Function | Check if a requirement is pinned.  Args:     spec (SpecifierSet): The specifier… |
| `require_files_report` | Function |  |
| `apply_asyncio_patch` | Function | Apply a patch to asyncio's exception handling for subprocesses.  There are some… |
| `auth` | Function | Authenticate Safety CLI with your account.  Args:     ctx (typer.Context): The… |
| `auth_options` | Function | Decorator that defines authentication options for Click commands.  Args:     st… |
| `build_client_session` | Function | Builds and configures the client session for authentication.  Args:     api_key… |
| `inject_session` | Function |  |
| `proxy_options` | Function | Decorator that defines proxy options for Click commands.  Options defined per c… |
| `Auth` | Class | Auth(org: Optional[safety.auth.models.Organization], keys: Any, client: Any, co… |
| `get_auth_method` | Method | Get the authentication method.  Returns:     str: The authentication method. |
| `is_valid` | Method | Check if the authentication information is valid.  Returns:     bool: True if v… |
| `refresh_from` | Method | Refresh the authentication information from the provided info.  Args:     info… |
| `SafetyCLISubGroup` | Class | Custom TyperGroup with additional functionality for Safety CLI. |
| `add_command` | Method | Registers another :class:`Command` with this group.  If the name is not provide… |
| `collect_usage_pieces` | Method | Returns all the pieces that go into the usage line and returns it as a list of… |
| `command` | Method | Create a new command.  Args:     *args: Variable length argument list.     **kw… |
| `format_commands` | Method | Extra format methods for multi methods that adds all the commands after the opt… |
| `format_epilog` | Method | Writes the epilog into the formatter if it exists. |
| `format_help` | Method | Format help message with rich formatting.  Args:     ctx (click.Context): Click… |
| `format_help_text` | Method | Writes the help text to the formatter if it exists. |
| `format_options` | Method | Writes all the options into the formatter if they exist. |
| `format_usage` | Method | Format usage message.  Args:     ctx (click.Context): Click context.     format… |
| `get_command` | Method | Given a context and a command name, this returns a :class:`Command` object if i… |
| `get_help` | Method | Formats the help into a string and returns it.  Calls :meth:`format_help` inter… |
| `get_help_option` | Method | Returns the help option object.  Skipped if :attr:`add_help_option` is ``False`… |
| `get_help_option_names` | Method | Returns the names for the help option. |
| `get_params` | Method |  |
| `get_short_help_str` | Method | Gets short help for the command or makes it by shortening the long help string. |
| `get_usage` | Method | Formats the usage line into a string and returns it.  Calls :meth:`format_usage… |
| `group` | Method | A shortcut decorator for declaring and attaching a group to the group. This tak… |
| `invoke` | Method | Given a context, this invokes the attached callback (if it exists) in the right… |
| `list_commands` | Method | Returns a list of subcommand names. Note that in Click's Group class, these are… |
| `main` | Method | This is the way to invoke a script with all the bells and whistles as a command… |
| `make_context` | Method | This function when given an info name and arguments will kick off the parsing a… |
| `make_parser` | Method | Creates the underlying option parser for this command. |
| `parse_args` | Method |  |
| `resolve_command` | Method |  |
| `result_callback` | Method | Adds a result callback to the command.  By default if a result callback is alre… |
| `shell_complete` | Method | Return a list of completions for the incomplete value. Looks at the names of op… |
| `to_info_dict` | Method |  |
| `auth` | Function | Authenticate Safety CLI with your account.  Args:     ctx (typer.Context): The… |
| `clean_session` | Function | Clean the authentication session.  Args:     client: The authentication client.… |
| `emit_auth_completed` | Function | Emit an AuthCompletedEvent and submit all pending events together.  Args:     e… |
| `emit_auth_started` | Function | Emit an AuthStartedEvent and store it as a pending event in SafetyCLI object.… |
| `fail_if_authenticated` | Function | Exits the command if the user is already authenticated.  Args:     ctx (typer.C… |
| `get_auth_info` | Function | Retrieve the authentication information.  Args:     ctx: The context object con… |
| `get_authorization_data` | Function | Generate the authorization URL for the authentication process.  Args:     clien… |
| `get_command_for` | Function | Retrieve a command by name from a Typer instance.  Args:     name (str): The na… |
| `get_token` | Function | " Retrieve a token from the local authentication configuration.  This returns t… |
| `get_version` | Function | Get the version of the Safety package.  Returns:   Optional[str]: The Safety ve… |
| `handle_cmd_exception` | Function | Decorator to handle exceptions in command functions.  Args:     func: The comma… |
| `initialize` | Function | Initializes the run by loading settings.  Args:     ctx (Any): The context obje… |
| `initialize_event_bus` | Function | Initializes the event bus for the given context. This should be called one time… |
| `is_email_verified` | Function | Check if the email is verified.  Args:     info (Dict[str, Any]): The user info… |
| `login` | Function | Authenticate Safety CLI with your safetycli.com account using your default brow… |
| `logout` | Function | Log out of your current session.  Args:     ctx (typer.Context): The Typer cont… |
| `notify` | Function | A decorator that wraps a function to emit events.  Args:   func (callable): The… |
| `pass_safety_cli_obj` | Function | Decorator to ensure the SafetyCLI object exists for a command. |
| `process_browser_callback` | Function | Process the browser callback for authentication.  Args:     uri (str): The auth… |
| `register` | Function | Create a new user account for the safetycli.com service.  Args:     ctx (typer.… |
| `render_email_note` | Function | Renders a note indicating whether email verification is required.  Args:     au… |
| `render_successful_login` | Function | Renders a message indicating a successful login.  Args:     auth (Auth): The Au… |
| `status` | Function | Display Safety CLI's current authentication status.  Args:     ctx (typer.Conte… |
| `Auth` | Class | Auth(org: Optional[safety.auth.models.Organization], keys: Any, client: Any, co… |
| `get_auth_method` | Method | Get the authentication method.  Returns:     str: The authentication method. |
| `is_valid` | Method | Check if the authentication information is valid.  Returns:     bool: True if v… |
| `refresh_from` | Method | Refresh the authentication information from the provided info.  Args:     info… |
| `DependentOption` | Class | A click option that depends on other options. |
| `add_to_parser` | Method |  |
| `consume_value` | Method | For :class:`Option`, the value can be collected from an interactive prompt if t… |
| `get_default` | Method | Return the default value for this option.  For non-boolean flag options, ``defa… |
| `get_error_hint` | Method | Get a stringified version of the param for use in error messages to indicate wh… |
| `get_help_extra` | Method |  |
| `get_help_record` | Method |  |
| `get_usage_pieces` | Method |  |
| `handle_parse_result` | Method | Handle the parse result for dependent options.  Args:     ctx (click.Context):… |
| `make_metavar` | Method |  |
| `process_value` | Method | Process the value of this parameter:  1. Type cast the value using :meth:`type_… |
| `prompt_for_value` | Method | This is an alternative flow that can be activated in the full value processing… |
| `resolve_envvar_value` | Method | :class:`Option` resolves its environment variable the same way as :func:`Parame… |
| `shell_complete` | Method | Return a list of completions for the incomplete value. If a ``shell_complete``… |
| `to_info_dict` | Method | .. versionchanged:: 8.3.0     Returns ``None`` for the :attr:`flag_value` if it… |
| `type_cast_value` | Method | Convert and validate a value against the parameter's :attr:`type`, :attr:`multi… |
| `value_from_envvar` | Method | For :class:`Option`, this method processes the raw environment variable string… |
| `value_is_missing` | Method | A value is considered missing if:  - it is :attr:`UNSET`, - or if it is an empt… |
| `Organization` | Class | Organization(id: str, name: str) |
| `to_dict` | Method | Convert the Organization instance to a dictionary.  Returns:     dict: The dict… |
| `S3PresignedAdapter` | Class | The built-in HTTP Adapter for urllib3.  Provides a general-case interface for R… |
| `add_headers` | Method | Add any headers needed by the connection. As of v2.0 this does nothing by defau… |
| `build_connection_pool_key_attributes` | Method | Build the PoolKey attributes used by urllib3 to return a connection.  This look… |
| `build_response` | Method | Builds a :class:`Response <requests.Response>` object from a urllib3 response.… |
| `cert_verify` | Method | Verify a SSL certificate. This method should not be called from user code, and… |
| `close` | Method | Disposes of any internal state.  Currently, this closes the PoolManager and any… |
| `get_connection` | Method | DEPRECATED: Users should move to `get_connection_with_tls_context` for all subc… |
| `get_connection_with_tls_context` | Method | Returns a urllib3 connection for the given request and TLS settings. This shoul… |
| `init_poolmanager` | Method | Initializes a urllib3 PoolManager.  This method should not be called from user… |
| `proxy_headers` | Method | Returns a dictionary of the headers to add to any request sent through a proxy.… |
| `proxy_manager_for` | Method | Return urllib3 ProxyManager for the given proxy.  This method should not be cal… |
| `request_url` | Method | Obtain the url to use when making the final request.  If the message is being s… |
| `send` | Method | Send a request, removing the Authorization header.  Args:     request (requests… |
| `SafetyAuthSession` | Class | Construct a new OAuth 2 client requests session.  :param client_id: Client ID,… |
| `audit_packages` | Method |  |
| `check_project` | Method |  |
| `check_updates` | Method |  |
| `client_auth` | Method |  |
| `close` | Method | Closes all adapters and as such the session |
| `create_authorization_url` | Method | Generate an authorization URL and state.  :param url: Authorization endpoint ur… |
| `delete` | Method | Sends a DELETE request. Returns :class:`Response` object.  :param url: URL for… |
| `download_policy` | Method |  |
| `ensure_active_token` | Method |  |
| `fetch_access_token` | Method | Alias for fetch_token. |
| `fetch_openid_config` | Method | Fetch the OpenID configuration from the authorization server.  Returns:     Any… |
| `fetch_token` | Method | Generic method for fetching an access token from the token endpoint.  :param ur… |
| `fetch_user_info` | Method |  |
| `get` | Method | Sends a GET request. Returns :class:`Response` object.  :param url: URL for the… |
| `get_adapter` | Method | Returns the appropriate connection adapter for the given URL.  :rtype: requests… |
| `get_authentication_type` | Method | Get the type of authentication being used.  Returns:     AuthenticationType: Th… |
| `get_credential` | Method | Get the current authentication credential.  Returns:     Optional[str]: The API… |
| `get_redirect_target` | Method | Receives a Response. Returns a redirect URI or ``None`` |
| `head` | Method | Sends a HEAD request. Returns :class:`Response` object.  :param url: URL for th… |
| `initialize` | Method |  |
| `introspect_token` | Method | Implementation of OAuth 2.0 Token Introspection defined via `RFC7662`_.  :param… |
| `is_using_auth_credentials` | Method | Check if the session is using authentication credentials.  This does NOT check… |
| `merge_environment_settings` | Method | Check the environment and merge it with some settings.  :rtype: dict |
| `mount` | Method | Registers a connection adapter to a prefix.  Adapters are sorted in descending… |
| `options` | Method | Sends a OPTIONS request. Returns :class:`Response` object.  :param url: URL for… |
| `parse_response_token` | Method |  |
| `patch` | Method | Sends a PATCH request. Returns :class:`Response` object.  :param url: URL for t… |
| `post` | Method | Sends a POST request. Returns :class:`Response` object.  :param url: URL for th… |
| `prepare_request` | Method | Constructs a :class:`PreparedRequest <PreparedRequest>` for transmission and re… |
| `project` | Method |  |
| `SafetyCLI` | Class | A class representing Safety CLI settings. |
| `SafetyContext` | Class | A singleton class to hold the Safety context. |
| `Stage` | Class | str(object='') -> str str(bytes_or_buffer[, encoding[, errors]]) -> str  Create… |
| `auth_options` | Function | Decorator that defines authentication options for Click commands.  Args:     st… |
| `build_client_session` | Function | Builds and configures the client session for authentication.  Args:     api_key… |
| `clean_session` | Function | Clean the authentication session.  Args:     client: The authentication client.… |
| `get_auth_info` | Function | Retrieve the authentication information.  Args:     ctx: The context object con… |
| `get_host_config` | Function | Retrieve a configuration value from the host configuration.  Args:     key_name… |
| `get_keys` | Function | Retrieve the keys from the OpenID configuration.  Args:     client_session (OAu… |
| `get_organization` | Function | Retrieve the organization configuration.  Returns:     Optional[Organization]:… |
| `get_proxy_config` | Function | Retrieve the proxy configuration.  Returns:     Tuple[Optional[Dict[str, str]],… |
| `get_proxy_dict` | Function | Get the proxy dictionary for requests.  Args:     proxy_protocol (str): The pro… |
| `get_redirect_url` | Function | Get the redirect URL for the authentication callback.  Returns:     str: The re… |
| `get_token` | Function | " Retrieve a token from the local authentication configuration.  This returns t… |
| `get_token_data` | Function | Decode and validate the token data.  Args:     token (str): The token to decode… |
| `inject_session` | Function |  |
| `is_email_verified` | Function | Check if the email is verified.  Args:     info (Dict[str, Any]): The user info… |
| `load_auth_session` | Function | Loads the authentication session from the context.  Args:     click_ctx (click.… |
| `proxy_options` | Function | Decorator that defines proxy options for Click commands.  Options defined per c… |
| `save_auth_config` | Function | Save the authentication configuration.  Args:     access_token (Optional[str]):… |
| `get_config_setting` | Function | Get the configuration setting from the config file or defaults.  Args:     name… |
| `Organization` | Class | Organization(id: str, name: str) |
| `to_dict` | Method | Convert the Organization instance to a dictionary.  Returns:     dict: The dict… |
| `Stage` | Class | str(object='') -> str str(bytes_or_buffer[, encoding[, errors]]) -> str  Create… |
| `clean_session` | Function | Clean the authentication session.  Args:     client: The authentication client.… |
| `get_auth_info` | Function | Retrieve the authentication information.  Args:     ctx: The context object con… |
| `get_authorization_data` | Function | Generate the authorization URL for the authentication process.  Args:     clien… |
| `get_host_config` | Function | Retrieve a configuration value from the host configuration.  Args:     key_name… |

## Classes

### `Alert`

Data class for storing alert details.

Attributes:
    report (Any): The report data.
    key (str): The API key for the safetycli.com vulnerability database.
    policy (Any): The policy data.
    r…

```python
safety.alerts.Alert(self, report: Any, key: str, policy: Any = None, requirements_files: Any = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `report` | `Any` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `policy` | `Any` | `None` | pos/kw |
| `requirements_files` | `Any` | `None` | pos/kw |

### `SafetyPolicyFile`

Custom Safety Policy file to hold validations.

```python
safety.alerts.SafetyPolicyFile(self, mode: str = 'r', encoding: Optional[str] = None, errors: str = 'strict', pure: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `mode` | `str` | `'r'` | pos/kw |
| `encoding` | `Optional` | `None` | pos/kw |
| `errors` | `str` | `'strict'` | pos/kw |
| `pure` | `bool` | `False` | pos/kw |

### `Requirement`

Class representing a single requirement.

Attributes:
    name (str): The name of the requirement.
    specs (SpecifierSet): The version specifiers for the requirement.
    line (str): The line conta…

```python
safety.alerts.requirements.Requirement(self, name: str, specs: packaging.specifiers.SpecifierSet, line: str, lineno: int, extras: List, file_type: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `specs` | `SpecifierSet` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |
| `lineno` | `int` | `—` | pos/kw |
| `extras` | `List` | `—` | pos/kw |
| `file_type` | `str` | `—` | pos/kw |

### `RequirementFile`

Class representing a requirements file with its content and metadata.

Attributes:
    path (str): The file path.
    content (str): The content of the file.
    sha (Optional[str]): The SHA of the f…

```python
safety.alerts.requirements.RequirementFile(self, path: str, content: str, sha: Optional[str] = None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |
| `sha` | `Optional` | `None` | pos/kw |

### `Auth`

Auth(org: Optional[safety.auth.models.Organization], keys: Any, client: Any, code_verifier: str, client_id: str, stage: Optional[safety_schemas.models.base.Stage] = <Stage.development: 'development'>…

```python
safety.auth.cli.Auth(self, org: Optional[safety.auth.models.Organization], keys: Any, client: Any, code_verifier: str, client_id: str, stage: Optional[safety_schemas.models.base.Stage] = <Stage.development: 'development'>, email: Optional[str] = None, name: Optional[str] = None, email_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `org` | `Optional` | `—` | pos/kw |
| `keys` | `Any` | `—` | pos/kw |
| `client` | `Any` | `—` | pos/kw |
| `code_verifier` | `str` | `—` | pos/kw |
| `client_id` | `str` | `—` | pos/kw |
| `stage` | `Optional` | `<Stage.development: 'development'>` | pos/kw |
| `email` | `Optional` | `None` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |
| `email_verified` | `bool` | `False` | pos/kw |

### `SafetyCLISubGroup`

Custom TyperGroup with additional functionality for Safety CLI.

```python
safety.auth.cli.SafetyCLISubGroup(self, *, name: str | None = None, commands: dict[str, click.core.Command] | collections.abc.Sequence[click.core.Command] | None = None, rich_markup_mode: Literal['markdown', 'rich', None] = 'rich', rich_help_panel: str | None = None, suggest_commands: bool = True, **attrs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str \| None` | `None` | kw |
| `commands` | `dict[str, click.core.Command] \| collections.abc.Sequence[click.core.Command] \| None` | `None` | kw |
| `rich_markup_mode` | `Literal` | `'rich'` | kw |
| `rich_help_panel` | `str \| None` | `None` | kw |
| `suggest_commands` | `bool` | `True` | kw |
| `attrs` | `Any` | `—` | **kwargs |

### `Auth`

Auth(org: Optional[safety.auth.models.Organization], keys: Any, client: Any, code_verifier: str, client_id: str, stage: Optional[safety_schemas.models.base.Stage] = <Stage.development: 'development'>…

```python
safety.auth.cli_utils.Auth(self, org: Optional[safety.auth.models.Organization], keys: Any, client: Any, code_verifier: str, client_id: str, stage: Optional[safety_schemas.models.base.Stage] = <Stage.development: 'development'>, email: Optional[str] = None, name: Optional[str] = None, email_verified: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `org` | `Optional` | `—` | pos/kw |
| `keys` | `Any` | `—` | pos/kw |
| `client` | `Any` | `—` | pos/kw |
| `code_verifier` | `str` | `—` | pos/kw |
| `client_id` | `str` | `—` | pos/kw |
| `stage` | `Optional` | `<Stage.development: 'development'>` | pos/kw |
| `email` | `Optional` | `None` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |
| `email_verified` | `bool` | `False` | pos/kw |

### `DependentOption`

A click option that depends on other options.

```python
safety.auth.cli_utils.DependentOption(self, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Organization`

Organization(id: str, name: str)

```python
safety.auth.cli_utils.Organization(self, id: str, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `str` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `S3PresignedAdapter`

The built-in HTTP Adapter for urllib3.

Provides a general-case interface for Requests sessions to contact HTTP and
HTTPS urls by implementing the Transport Adapter interface. This class will
usually…

```python
safety.auth.cli_utils.S3PresignedAdapter(self, pool_connections=10, pool_maxsize=10, max_retries=0, pool_block=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pool_connections` | `—` | `10` | pos/kw |
| `pool_maxsize` | `—` | `10` | pos/kw |
| `max_retries` | `—` | `0` | pos/kw |
| `pool_block` | `—` | `False` | pos/kw |

### `SafetyAuthSession`

Construct a new OAuth 2 client requests session.

:param client_id: Client ID, which you get from client registration.
:param client_secret: Client Secret, which you get from registration.
:param aut…

```python
safety.auth.cli_utils.SafetyAuthSession(self, *args: Any, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `SafetyCLI`

A class representing Safety CLI settings.

```python
safety.auth.cli_utils.SafetyCLI(self, auth: Optional[ForwardRef('Auth')] = None, telemetry: Optional[ForwardRef('TelemetryModel')] = None, metadata: Optional[ForwardRef('MetadataModel')] = None, schema: Optional[ForwardRef('ReportSchemaVersion')] = None, config: Optional[ForwardRef('ConfigModel')] = None, console: Optional[ForwardRef('Console')] = None, system_scan_policy: Optional[ForwardRef('PolicyFileModel')] = None, platform_enabled: bool = False, firewall_enabled: bool = False, events_enabled: bool = False, event_bus: Optional[ForwardRef('EventBus')] = None, security_events_handler: Optional[ForwardRef('SecurityEventsHandler')] = None, correlation_id: Optional[str] = None, pending_events: List[ForwardRef('Event')] = <factory>) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `auth` | `Optional` | `None` | pos/kw |
| `telemetry` | `Optional` | `None` | pos/kw |
| `metadata` | `Optional` | `None` | pos/kw |
| `schema` | `Optional` | `None` | pos/kw |
| `config` | `Optional` | `None` | pos/kw |
| `console` | `Optional` | `None` | pos/kw |
| `system_scan_policy` | `Optional` | `None` | pos/kw |
| `platform_enabled` | `bool` | `False` | pos/kw |
| `firewall_enabled` | `bool` | `False` | pos/kw |
| `events_enabled` | `bool` | `False` | pos/kw |
| `event_bus` | `Optional` | `None` | pos/kw |
| `security_events_handler` | `Optional` | `None` | pos/kw |
| `correlation_id` | `Optional` | `None` | pos/kw |
| `pending_events` | `List` | `<factory>` | pos/kw |

### `SafetyContext`

A singleton class to hold the Safety context.

```python
safety.auth.cli_utils.SafetyContext(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Stage`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
safety.auth.cli_utils.Stage(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `Organization`

Organization(id: str, name: str)

```python
safety.auth.main.Organization(self, id: str, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `id` | `str` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `Stage`

str(object='') -> str
str(bytes_or_buffer[, encoding[, errors]]) -> str

Create a new string object from the given object. If encoding or
errors is specified, then the object must expose a data buffe…

```python
safety.auth.main.Stage(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

## Functions

### `get_context_settings`

```python
safety.alerts.get_context_settings()
```

### `get_safety_cli_legacy_group`

```python
safety.alerts.get_safety_cli_legacy_group()
```

### `create_branch`

Create a new branch in the given GitHub repository.

Args:
    repo (Any): The GitHub repository object.
    base_branch (str): The name of the base branch.
    new_branch (str): The name of the new…

```python
safety.alerts.github.create_branch(repo: Any, base_branch: str, new_branch: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `Any` | `—` | pos/kw |
| `base_branch` | `str` | `—` | pos/kw |
| `new_branch` | `str` | `—` | pos/kw |

### `delete_branch`

Delete a branch from the given GitHub repository.

Args:
    repo (Any): The GitHub repository object.
    branch (str): The name of the branch to delete.

```python
safety.alerts.github.delete_branch(repo: Any, branch: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repo` | `Any` | `—` | pos/kw |
| `branch` | `str` | `—` | pos/kw |

### `get_meta_http_headers`

Get the metadata headers for the client.

Returns:
  Dict[str, str]: The metadata headers.

```python
safety.alerts.requirements.get_meta_http_headers() -> Dict[str, str]
```

**Returns:** `typing.Dict[str, str]`

### `cvss3_score_to_label`

Converts a CVSS v3 score to a severity label.

Args:
    score (float): The CVSS v3 score.

Returns:
    Optional[str]: The severity label.

```python
safety.alerts.utils.cvss3_score_to_label(score: float) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `score` | `float` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `fetch_changelog`

Fetches the changelog for a package from a specified version to another version.

Args:
    package (str): The package name.
    from_version (Optional[str]): The starting version.
    to_version (st…

```python
safety.alerts.utils.fetch_changelog(package: str, from_version: Optional[str], to_version: str, *, api_key: str, from_spec: Optional[str] = None) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `package` | `str` | `—` | pos/kw |
| `from_version` | `Optional` | `—` | pos/kw |
| `to_version` | `str` | `—` | pos/kw |
| `api_key` | `str` | `—` | kw |
| `from_spec` | `Optional` | `None` | kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `generate_body`

Generates the body content for a pull request.

Args:
    pkg (str): The package name.
    remediation (Dict[str, Any]): The remediation data.
    vulns (List[Dict[str, Any]]): The list of vulnerabil…

```python
safety.alerts.utils.generate_body(pkg: str, remediation: Dict[str, Any], vulns: List[Dict[str, Any]], *, api_key: str) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |
| `remediation` | `Dict` | `—` | pos/kw |
| `vulns` | `List` | `—` | pos/kw |
| `api_key` | `str` | `—` | kw |

**Returns:** `typing.Optional[str]`

### `generate_branch_name`

Generates a branch name for a given package and remediation.

Args:
    pkg (str): The package name.
    remediation (Dict[str, Any]): The remediation data.

Returns:
    str: The generated branch na…

```python
safety.alerts.utils.generate_branch_name(pkg: str, remediation: Dict[str, Any]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |
| `remediation` | `Dict` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `generate_commit_message`

Generates a commit message for a given package and remediation.

Args:
    pkg (str): The package name.
    remediation (Dict[str, Any]): The remediation data.

Returns:
    str: The generated commit…

```python
safety.alerts.utils.generate_commit_message(pkg: str, remediation: Dict[str, Any]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |
| `remediation` | `Dict` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `generate_issue_body`

Generates the body content for an issue.

Args:
    pkg (str): The package name.
    remediation (Dict[str, Any]): The remediation data.
    vulns (List[Dict[str, Any]]): The list of vulnerabilities.…

```python
safety.alerts.utils.generate_issue_body(pkg: str, remediation: Dict[str, Any], vulns: List[Dict[str, Any]], *, api_key: str) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |
| `remediation` | `Dict` | `—` | pos/kw |
| `vulns` | `List` | `—` | pos/kw |
| `api_key` | `str` | `—` | kw |

**Returns:** `typing.Optional[str]`

### `generate_issue_title`

Generates an issue title for a given package and remediation.

Args:
    pkg (str): The package name.
    remediation (Dict[str, Any]): The remediation data.

Returns:
    str: The generated issue ti…

```python
safety.alerts.utils.generate_issue_title(pkg: str, remediation: Dict[str, Any]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |
| `remediation` | `Dict` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `generate_title`

Generates a title for a pull request or issue.

Args:
    pkg (str): The package name.
    remediation (Dict[str, Any]): The remediation data.
    vulns (List[Dict[str, Any]]): The list of vulnerabil…

```python
safety.alerts.utils.generate_title(pkg: str, remediation: Dict[str, Any], vulns: List[Dict[str, Any]]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |
| `remediation` | `Dict` | `—` | pos/kw |
| `vulns` | `List` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_fix_hint_for_unpinned`

Get the fix hint for unpinned dependencies.

Args:
    remediation (Dict[str, Any]): The remediation details.

Returns:
    str: The fix hint.

```python
safety.alerts.utils.get_fix_hint_for_unpinned(remediation: Dict[str, Any]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `remediation` | `Dict` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_hint`

Generates a hint for a given remediation.

Args:
    remediation (Dict[str, Any]): The remediation data.

Returns:
    str: The generated hint.

```python
safety.alerts.utils.get_hint(remediation: Dict[str, Any]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `remediation` | `Dict` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_meta_http_headers`

Get the metadata headers for the client.

Returns:
  Dict[str, str]: The metadata headers.

```python
safety.alerts.utils.get_meta_http_headers() -> Dict[str, str]
```

**Returns:** `typing.Dict[str, str]`

### `get_specifier_range_info`

Get the specifier range information.

Args:
    style (bool, optional): Whether to apply styling. Defaults to True.
    pin_hint (bool, optional): Whether to include a pin hint. Defaults to False.

R…

```python
safety.alerts.utils.get_specifier_range_info(style: bool = True, pin_hint: bool = False) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `style` | `bool` | `True` | pos/kw |
| `pin_hint` | `bool` | `False` | pos/kw |

**Returns:** `<class 'str'>`

### `get_unpinned_hint`

Get the hint for unpinned packages.

Args:
    pkg (str): The package name.

Returns:
    str: The hint for unpinned packages.

```python
safety.alerts.utils.get_unpinned_hint(pkg: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `pkg` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `git_sha1`

Calculates the SHA-1 hash of the given raw contents.

Args:
    raw_contents (bytes): The raw contents to hash.

Returns:
    str: The SHA-1 hash.

```python
safety.alerts.utils.git_sha1(raw_contents: bytes) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `raw_contents` | `bytes` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `highest_base_score`

Calculates the highest CVSS base score from a list of vulnerabilities.

Args:
    vulns (List[Dict[str, Any]]): The list of vulnerabilities.

Returns:
    float: The highest CVSS base score.

```python
safety.alerts.utils.highest_base_score(vulns: List[Dict[str, Any]]) -> float
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `vulns` | `List` | `—` | pos/kw |

**Returns:** `<class 'float'>`

### `is_pinned_requirement`

Check if a requirement is pinned.

Args:
    spec (SpecifierSet): The specifier set of the requirement.

Returns:
    bool: True if the requirement is pinned, False otherwise.

```python
safety.alerts.utils.is_pinned_requirement(spec: packaging.specifiers.SpecifierSet) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `spec` | `SpecifierSet` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `require_files_report`

```python
safety.alerts.utils.require_files_report(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `apply_asyncio_patch`

Apply a patch to asyncio's exception handling for subprocesses.

There are some issues with asyncio's exception handling for subprocesses,
which causes a RuntimeError to be raised when the event loop…

```python
safety.asyncio_patch.apply_asyncio_patch()
```

### `auth`

Authenticate Safety CLI with your account.

Args:
    ctx (typer.Context): The Typer context object.

```python
safety.auth.auth(ctx: typer.models.Context) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |

### `auth_options`

Decorator that defines authentication options for Click commands.

Args:
    stage (bool): Whether to include the stage option.

Returns:
    Callable: The decorator function.

```python
safety.auth.auth_options(stage: bool = True) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stage` | `bool` | `True` | pos/kw |

**Returns:** `typing.Callable`

### `build_client_session`

Builds and configures the client session for authentication.

Args:
    api_key (Optional[str]): The API key for authentication.
    proxies (Optional[Dict[str, str]]): Proxy configuration.
    heade…

```python
safety.auth.build_client_session(api_key: Optional[str] = None, proxies: Optional[Dict[str, str]] = None, headers: Optional[Dict[str, str]] = None) -> Tuple[safety.auth.utils.SafetyAuthSession, Dict[str, Any]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `api_key` | `Optional` | `None` | pos/kw |
| `proxies` | `Optional` | `None` | pos/kw |
| `headers` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[safety.auth.utils.SafetyAuthSession, typing.Dict[str, typing.Any]]`

### `inject_session`

```python
safety.auth.inject_session(ctx: click.core.Context, proxy_protocol: Optional[str] = None, proxy_host: Optional[str] = None, proxy_port: Optional[str] = None, key: Optional[str] = None, stage: Optional[safety_schemas.models.base.Stage] = None, invoked_command: str = '') -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |
| `proxy_protocol` | `Optional` | `None` | pos/kw |
| `proxy_host` | `Optional` | `None` | pos/kw |
| `proxy_port` | `Optional` | `None` | pos/kw |
| `key` | `Optional` | `None` | pos/kw |
| `stage` | `Optional` | `None` | pos/kw |
| `invoked_command` | `str` | `''` | pos/kw |

**Returns:** `typing.Any`

### `proxy_options`

Decorator that defines proxy options for Click commands.

Options defined per command, this will override the proxy settings defined in the
config.ini file.

Args:
    func (Callable): The Click comm…

```python
safety.auth.proxy_options(func: Callable) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Callable` | `—` | pos/kw |

**Returns:** `typing.Callable`

### `auth`

Authenticate Safety CLI with your account.

Args:
    ctx (typer.Context): The Typer context object.

```python
safety.auth.cli.auth(ctx: typer.models.Context) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |

### `clean_session`

Clean the authentication session.

Args:
    client: The authentication client.

Returns:
    bool: Always returns True.

```python
safety.auth.cli.clean_session(client) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `emit_auth_completed`

Emit an AuthCompletedEvent and submit all pending events together.

Args:
    event_bus: The event bus to emit on
    ctx: The Click context containing the SafetyCLI object
    success: Whether authe…

```python
safety.auth.cli.emit_auth_completed(event_bus: 'EventBus', ctx: 'CustomContext', *, success: bool = True, error_message: Optional[str] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `event_bus` | `EventBus` | `—` | pos/kw |
| `ctx` | `CustomContext` | `—` | pos/kw |
| `success` | `bool` | `True` | kw |
| `error_message` | `Optional` | `None` | kw |

### `emit_auth_started`

Emit an AuthStartedEvent and store it as a pending event in SafetyCLI object.

Args:
    event_bus: The event bus to emit on
    ctx: The Click context containing the SafetyCLI object

```python
safety.auth.cli.emit_auth_started(event_bus: 'EventBus', ctx: 'CustomContext') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `event_bus` | `EventBus` | `—` | pos/kw |
| `ctx` | `CustomContext` | `—` | pos/kw |

### `fail_if_authenticated`

Exits the command if the user is already authenticated.

Args:
    ctx (typer.Context): The Typer context object.
    with_msg (str): The message to display if authenticated.

```python
safety.auth.cli.fail_if_authenticated(ctx: typer.models.Context, with_msg: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |
| `with_msg` | `str` | `—` | pos/kw |

### `get_auth_info`

Retrieve the authentication information.

Args:
    ctx: The context object containing authentication data.

Returns:
    Optional[Dict]: The authentication information, or None if not authenticated.

```python
safety.auth.cli.get_auth_info(ctx) -> Optional[Dict]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Dict]`

### `get_authorization_data`

Generate the authorization URL for the authentication process.

Args:
    client: The authentication client.
    code_verifier (str): The code verifier for the PKCE flow.
    organization (Optional[O…

```python
safety.auth.cli.get_authorization_data(client, code_verifier: str, organization: Optional[safety.auth.models.Organization] = None, sign_up: bool = False, ensure_auth: bool = False, headless: bool = False) -> Tuple[str, str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `—` | `—` | pos/kw |
| `code_verifier` | `str` | `—` | pos/kw |
| `organization` | `Optional` | `None` | pos/kw |
| `sign_up` | `bool` | `False` | pos/kw |
| `ensure_auth` | `bool` | `False` | pos/kw |
| `headless` | `bool` | `False` | pos/kw |

**Returns:** `typing.Tuple[str, str]`

### `get_command_for`

Retrieve a command by name from a Typer instance.

Args:
    name (str): The name of the command.
    typer_instance (typer.Typer): The Typer instance.

Returns:
    click.Command: The found command.

```python
safety.auth.cli.get_command_for(name: str, typer_instance: typer.main.Typer) -> click.core.Command
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `typer_instance` | `Typer` | `—` | pos/kw |

**Returns:** `<class 'click.core.Command'>`

### `get_token`

"
Retrieve a token from the local authentication configuration.

This returns tokens saved in the local auth configuration.
There are two types of tokens: access_token and id_token

Args:
    name (s…

```python
safety.auth.cli.get_token(name: str = 'access_token') -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `'access_token'` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_version`

Get the version of the Safety package.

Returns:
  Optional[str]: The Safety version if found, otherwise None.

```python
safety.auth.cli.get_version() -> Optional[str]
```

**Returns:** `typing.Optional[str]`

### `handle_cmd_exception`

Decorator to handle exceptions in command functions.

Args:
    func: The command function to wrap.

Returns:
    The wrapped function.

```python
safety.auth.cli.handle_cmd_exception(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `initialize`

Initializes the run by loading settings.

Args:
    ctx (Any): The context object.
    refresh (bool): Whether to refresh settings from the server. Defaults to True.

```python
safety.auth.cli.initialize(ctx: Any, refresh: bool = True) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Any` | `—` | pos/kw |
| `refresh` | `bool` | `True` | pos/kw |

### `initialize_event_bus`

Initializes the event bus for the given context. This should be called one
time only per command run.
The event bus requires the following conditions to be met:
- Platform OR Platform and Firewall fe…

```python
safety.auth.cli.initialize_event_bus(ctx: Union[ForwardRef('CustomContext'), ForwardRef('typer.Context')]) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Union` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `is_email_verified`

Check if the email is verified.

Args:
    info (Dict[str, Any]): The user information.

Returns:
    bool: True

```python
safety.auth.cli.is_email_verified(info: Dict[str, Any]) -> Optional[bool]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `info` | `Dict` | `—` | pos/kw |

**Returns:** `typing.Optional[bool]`

### `login`

Authenticate Safety CLI with your safetycli.com account using your default browser.

Args:
    ctx (typer.Context): The Typer context object.
    headless (bool): Whether to run in headless mode.

```python
safety.auth.cli.login(ctx: typer.models.Context, headless: Annotated[Optional[bool], <typer.models.OptionInfo object at 0x772086f88410>] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |
| `headless` | `Annotated` | `None` | pos/kw |

### `logout`

Log out of your current session.

Args:
    ctx (typer.Context): The Typer context object.

```python
safety.auth.cli.logout(ctx: typer.models.Context) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |

### `notify`

A decorator that wraps a function to emit events.

Args:
  func (callable): The function to be wrapped by the decorator.

Returns:
  callable: The wrapped function with notification logic.

The decor…

```python
safety.auth.cli.notify(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `pass_safety_cli_obj`

Decorator to ensure the SafetyCLI object exists for a command.

```python
safety.auth.cli.pass_safety_cli_obj(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `process_browser_callback`

Process the browser callback for authentication.

Args:
    uri (str): The authorization URL.
    **kwargs (Any): Additional keyword arguments.

Returns:
    Any: The user information.

Raises:
    S…

```python
safety.auth.cli.process_browser_callback(uri: str, **kwargs: Any) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `uri` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `typing.Any`

### `register`

Create a new user account for the safetycli.com service.

Args:
    ctx (typer.Context): The Typer context object.

```python
safety.auth.cli.register(ctx: typer.models.Context) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |

### `render_email_note`

Renders a note indicating whether email verification is required.

Args:
    auth (Auth): The Auth object.

Returns:
    str: The rendered email note.

```python
safety.auth.cli.render_email_note(auth: safety.auth.models.Auth) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `auth` | `Auth` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `render_successful_login`

Renders a message indicating a successful login.

Args:
    auth (Auth): The Auth object.
    organization (Optional[str]): The organization name.

```python
safety.auth.cli.render_successful_login(auth: safety.auth.models.Auth, organization: Optional[str] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `auth` | `Auth` | `—` | pos/kw |
| `organization` | `Optional` | `None` | pos/kw |

### `status`

Display Safety CLI's current authentication status.

Args:
    ctx (typer.Context): The Typer context object.
    ensure_auth (bool): Whether to keep running until authentication is made.
    login_t…

```python
safety.auth.cli.status(ctx: typer.models.Context, ensure_auth: bool = False, login_timeout: int = 600) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |
| `ensure_auth` | `bool` | `False` | pos/kw |
| `login_timeout` | `int` | `600` | pos/kw |

### `auth_options`

Decorator that defines authentication options for Click commands.

Args:
    stage (bool): Whether to include the stage option.

Returns:
    Callable: The decorator function.

```python
safety.auth.cli_utils.auth_options(stage: bool = True) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `stage` | `bool` | `True` | pos/kw |

**Returns:** `typing.Callable`

### `build_client_session`

Builds and configures the client session for authentication.

Args:
    api_key (Optional[str]): The API key for authentication.
    proxies (Optional[Dict[str, str]]): Proxy configuration.
    heade…

```python
safety.auth.cli_utils.build_client_session(api_key: Optional[str] = None, proxies: Optional[Dict[str, str]] = None, headers: Optional[Dict[str, str]] = None) -> Tuple[safety.auth.utils.SafetyAuthSession, Dict[str, Any]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `api_key` | `Optional` | `None` | pos/kw |
| `proxies` | `Optional` | `None` | pos/kw |
| `headers` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Tuple[safety.auth.utils.SafetyAuthSession, typing.Dict[str, typing.Any]]`

### `clean_session`

Clean the authentication session.

Args:
    client: The authentication client.

Returns:
    bool: Always returns True.

```python
safety.auth.cli_utils.clean_session(client) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `get_auth_info`

Retrieve the authentication information.

Args:
    ctx: The context object containing authentication data.

Returns:
    Optional[Dict]: The authentication information, or None if not authenticated.

```python
safety.auth.cli_utils.get_auth_info(ctx) -> Optional[Dict]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Dict]`

### `get_host_config`

Retrieve a configuration value from the host configuration.

Args:
    key_name (str): The name of the configuration key.

Returns:
    Optional[Any]: The configuration value, or None if not found.

```python
safety.auth.cli_utils.get_host_config(key_name: str) -> Optional[Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key_name` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Any]`

### `get_keys`

Retrieve the keys from the OpenID configuration.

Args:
    client_session (OAuth2Session): The OAuth2 session.
    openid_config (Dict[str, Any]): The OpenID configuration.

Returns:
    Optional[Di…

```python
safety.auth.cli_utils.get_keys(client_session: authlib.integrations.requests_client.oauth2_session.OAuth2Session, openid_config: Dict[str, Any]) -> Optional[Dict[str, Any]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client_session` | `OAuth2Session` | `—` | pos/kw |
| `openid_config` | `Dict` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Dict[str, typing.Any]]`

### `get_organization`

Retrieve the organization configuration.

Returns:
    Optional[Organization]: The organization object, or None if not configured.

```python
safety.auth.cli_utils.get_organization() -> Optional[safety.auth.models.Organization]
```

**Returns:** `typing.Optional[safety.auth.models.Organization]`

### `get_proxy_config`

Retrieve the proxy configuration.

Returns:
    Tuple[Optional[Dict[str, str]], Optional[int], bool]: The proxy configuration, timeout, and whether it is required.

```python
safety.auth.cli_utils.get_proxy_config() -> Tuple[Optional[Dict[str, str]], Optional[int], bool]
```

**Returns:** `typing.Tuple[typing.Optional[typing.Dict[str, str]], typing.Optional[int], bool]`

### `get_proxy_dict`

Get the proxy dictionary for requests.

Args:
    proxy_protocol (str): The proxy protocol.
    proxy_host (str): The proxy host.
    proxy_port (int): The proxy port.

Returns:
    Optional[Dict[str…

```python
safety.auth.cli_utils.get_proxy_dict(proxy_protocol: str, proxy_host: str, proxy_port: int) -> Optional[Dict[str, str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `proxy_protocol` | `str` | `—` | pos/kw |
| `proxy_host` | `str` | `—` | pos/kw |
| `proxy_port` | `int` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Dict[str, str]]`

### `get_redirect_url`

Get the redirect URL for the authentication callback.

Returns:
    str: The redirect URL.

```python
safety.auth.cli_utils.get_redirect_url() -> str
```

**Returns:** `<class 'str'>`

### `get_token`

"
Retrieve a token from the local authentication configuration.

This returns tokens saved in the local auth configuration.
There are two types of tokens: access_token and id_token

Args:
    name (s…

```python
safety.auth.cli_utils.get_token(name: str = 'access_token') -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `'access_token'` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_token_data`

Decode and validate the token data.

Args:
    token (str): The token to decode.
    keys (Any): The keys to use for decoding.
    silent_if_expired (bool): Whether to silently ignore expired tokens.…

```python
safety.auth.cli_utils.get_token_data(token: str, keys: Any, silent_if_expired: bool = False) -> Optional[Dict]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `token` | `str` | `—` | pos/kw |
| `keys` | `Any` | `—` | pos/kw |
| `silent_if_expired` | `bool` | `False` | pos/kw |

**Returns:** `typing.Optional[typing.Dict]`

### `inject_session`

```python
safety.auth.cli_utils.inject_session(ctx: click.core.Context, proxy_protocol: Optional[str] = None, proxy_host: Optional[str] = None, proxy_port: Optional[str] = None, key: Optional[str] = None, stage: Optional[safety_schemas.models.base.Stage] = None, invoked_command: str = '') -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `Context` | `—` | pos/kw |
| `proxy_protocol` | `Optional` | `None` | pos/kw |
| `proxy_host` | `Optional` | `None` | pos/kw |
| `proxy_port` | `Optional` | `None` | pos/kw |
| `key` | `Optional` | `None` | pos/kw |
| `stage` | `Optional` | `None` | pos/kw |
| `invoked_command` | `str` | `''` | pos/kw |

**Returns:** `typing.Any`

### `is_email_verified`

Check if the email is verified.

Args:
    info (Dict[str, Any]): The user information.

Returns:
    bool: True

```python
safety.auth.cli_utils.is_email_verified(info: Dict[str, Any]) -> Optional[bool]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `info` | `Dict` | `—` | pos/kw |

**Returns:** `typing.Optional[bool]`

### `load_auth_session`

Loads the authentication session from the context.

Args:
    click_ctx (click.Context): The Click context object.

```python
safety.auth.cli_utils.load_auth_session(click_ctx: click.core.Context) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `click_ctx` | `Context` | `—` | pos/kw |

### `proxy_options`

Decorator that defines proxy options for Click commands.

Options defined per command, this will override the proxy settings defined in the
config.ini file.

Args:
    func (Callable): The Click comm…

```python
safety.auth.cli_utils.proxy_options(func: Callable) -> Callable
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `Callable` | `—` | pos/kw |

**Returns:** `typing.Callable`

### `save_auth_config`

Save the authentication configuration.

Args:
    access_token (Optional[str]): The access token.
    id_token (Optional[str]): The ID token.
    refresh_token (Optional[str]): The refresh token.

```python
safety.auth.cli_utils.save_auth_config(access_token: Optional[str] = None, id_token: Optional[str] = None, refresh_token: Optional[str] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `access_token` | `Optional` | `None` | pos/kw |
| `id_token` | `Optional` | `None` | pos/kw |
| `refresh_token` | `Optional` | `None` | pos/kw |

### `get_config_setting`

Get the configuration setting from the config file or defaults.

Args:
    name (str): The name of the setting to retrieve.

Returns:
    Optional[str]: The value of the setting if found, otherwise N…

```python
safety.auth.constants.get_config_setting(name: str, default=None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `default` | `—` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `clean_session`

Clean the authentication session.

Args:
    client: The authentication client.

Returns:
    bool: Always returns True.

```python
safety.auth.main.clean_session(client) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `get_auth_info`

Retrieve the authentication information.

Args:
    ctx: The context object containing authentication data.

Returns:
    Optional[Dict]: The authentication information, or None if not authenticated.

```python
safety.auth.main.get_auth_info(ctx) -> Optional[Dict]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `ctx` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Dict]`

### `get_authorization_data`

Generate the authorization URL for the authentication process.

Args:
    client: The authentication client.
    code_verifier (str): The code verifier for the PKCE flow.
    organization (Optional[O…

```python
safety.auth.main.get_authorization_data(client, code_verifier: str, organization: Optional[safety.auth.models.Organization] = None, sign_up: bool = False, ensure_auth: bool = False, headless: bool = False) -> Tuple[str, str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `client` | `—` | `—` | pos/kw |
| `code_verifier` | `str` | `—` | pos/kw |
| `organization` | `Optional` | `None` | pos/kw |
| `sign_up` | `bool` | `False` | pos/kw |
| `ensure_auth` | `bool` | `False` | pos/kw |
| `headless` | `bool` | `False` | pos/kw |

**Returns:** `typing.Tuple[str, str]`

### `get_host_config`

Retrieve a configuration value from the host configuration.

Args:
    key_name (str): The name of the configuration key.

Returns:
    Optional[Any]: The configuration value, or None if not found.

```python
safety.auth.main.get_host_config(key_name: str) -> Optional[Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `key_name` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Any]`

## Methods

### `safety.alerts.SafetyPolicyFile` methods

### `convert`

Convert the parameter value to a Safety policy file.

Args:
    value (Any): The parameter value.
    param (Optional[click.Parameter]): The click parameter.
    ctx (Optional[click.Context]): The cl…

```python
safety.alerts.SafetyPolicyFile.convert(self, value: Any, param: Optional[click.core.Parameter], ctx: Optional[click.core.Context]) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `param` | `Optional` | `—` | pos/kw |
| `ctx` | `Optional` | `—` | pos/kw |

**Returns:** `typing.Any`

### `fail`

Helper method to fail with an invalid value message.

```python
safety.alerts.SafetyPolicyFile.fail(self, message: 'str', param: 'Parameter | None' = None, ctx: 'Context | None' = None) -> 't.NoReturn'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |
| `param` | `Parameter \| None` | `None` | pos/kw |
| `ctx` | `Context \| None` | `None` | pos/kw |

**Returns:** `t.NoReturn`

### `fail_if_unrecognized_keys`

Fail if unrecognized keys are found in the policy file.

Args:
    used_keys (List[str]): The used keys.
    valid_keys (List[str]): The valid keys.
    param (Optional[click.Parameter]): The click p…

```python
safety.alerts.SafetyPolicyFile.fail_if_unrecognized_keys(self, used_keys: List[str], valid_keys: List[str], param: Optional[click.core.Parameter] = None, ctx: Optional[click.core.Context] = None, msg: str = '{hint}', context_hint: str = '') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `used_keys` | `List` | `—` | pos/kw |
| `valid_keys` | `List` | `—` | pos/kw |
| `param` | `Optional` | `None` | pos/kw |
| `ctx` | `Optional` | `None` | pos/kw |
| `msg` | `str` | `'{hint}'` | pos/kw |
| `context_hint` | `str` | `''` | pos/kw |

### `fail_if_wrong_bool_value`

Fail if a boolean value is invalid.

Args:
    keyword (str): The keyword.
    value (Any): The value.
    msg (str): The error message template.

Raises:
    click.UsageError: If the boolean value i…

```python
safety.alerts.SafetyPolicyFile.fail_if_wrong_bool_value(self, keyword: str, value: Any, msg: str = '{hint}') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `keyword` | `str` | `—` | pos/kw |
| `value` | `Any` | `—` | pos/kw |
| `msg` | `str` | `'{hint}'` | pos/kw |

### `get_metavar`

Returns the metavar default for this param if it provides one.

```python
safety.alerts.SafetyPolicyFile.get_metavar(self, param: 'Parameter', ctx: 'Context') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `param` | `Parameter` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `str | None`

### `get_missing_message`

Optionally might return extra information about a missing
parameter.

.. versionadded:: 2.0

```python
safety.alerts.SafetyPolicyFile.get_missing_message(self, param: 'Parameter', ctx: 'Context | None') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `param` | `Parameter` | `—` | pos/kw |
| `ctx` | `Context \| None` | `—` | pos/kw |

**Returns:** `str | None`

### `shell_complete`

Return a special completion marker that tells the completion
system to use the shell to provide file path completions.

Args:
    ctx (click.Context): The click context.
    param (click.Parameter):…

```python
safety.alerts.SafetyPolicyFile.shell_complete(self, ctx: click.core.Context, param: click.core.Parameter, incomplete: str)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `param` | `Parameter` | `—` | pos/kw |
| `incomplete` | `str` | `—` | pos/kw |

### `split_envvar_value`

Given a value from an environment variable this splits it up
into small chunks depending on the defined envvar list splitter.

If the splitter is set to `None`, which means that whitespace splits,
th…

```python
safety.alerts.SafetyPolicyFile.split_envvar_value(self, rv: 'str') -> 'cabc.Sequence[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `rv` | `str` | `—` | pos/kw |

**Returns:** `cabc.Sequence[str]`

### `to_info_dict`

Convert the object to an info dictionary.

Returns:
    Dict[str, Any]: The info dictionary.

```python
safety.alerts.SafetyPolicyFile.to_info_dict(self) -> Dict[str, Any]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Any]`

### `safety.alerts.requirements.Requirement` methods

### `convert_semver`

Converts a version string to a semantic version dictionary.

Args:
    version (str): The version string.

Returns:
    dict: The semantic version dictionary.

```python
safety.alerts.requirements.Requirement.convert_semver(version: str) -> dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

**Returns:** `<class 'dict'>`

### `get_hashes`

Retrieves the hashes for a specific version from PyPI.

Args:
    version (str): The version to retrieve hashes for.

Returns:
    List: A list of hashes for the specified version.

```python
safety.alerts.requirements.Requirement.get_hashes(self, version: str) -> List
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

**Returns:** `typing.List`

### `parse`

Parses a requirement from a line of text.

Args:
    s (str): The line of text.
    lineno (int): The line number.
    file_type (str): The type of the file containing the requirement.

Returns:…

```python
safety.alerts.requirements.Requirement.parse(s: str, lineno: int, file_type: str = 'requirements.txt') -> 'Requirement'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `str` | `—` | pos/kw |
| `lineno` | `int` | `—` | pos/kw |
| `file_type` | `str` | `'requirements.txt'` | pos/kw |

**Returns:** `Requirement`

### `update_version`

Updates the version of the requirement in the content.

Args:
    content (str): The original content.
    version (str): The new version to update to.
    update_hashes (bool): Whether to update the…

```python
safety.alerts.requirements.Requirement.update_version(self, content: str, version: str, update_hashes: bool = True) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `content` | `str` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |
| `update_hashes` | `bool` | `True` | pos/kw |

**Returns:** `<class 'str'>`

### `safety.alerts.requirements.RequirementFile` methods

### `iter_lines`

Iterates over lines in the content starting from a specific line number.

Args:
    lineno (int): The line number to start from.

Yields:
    str: The next line in the content.

```python
safety.alerts.requirements.RequirementFile.iter_lines(self, lineno: int = 0) -> Generator[str, NoneType, NoneType]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `lineno` | `int` | `0` | pos/kw |

**Returns:** `typing.Generator[str, NoneType, NoneType]`

### `parse_dependencies`

Parses the dependencies from the content based on the file type.

Args:
    file_type (str): The type of the file.

```python
safety.alerts.requirements.RequirementFile.parse_dependencies(self, file_type: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file_type` | `str` | `—` | pos/kw |

### `parse_index_server`

Parses the index server from a given line.

Args:
    line (str): The line to parse.

Returns:
    str: The parsed index server.

```python
safety.alerts.requirements.RequirementFile.parse_index_server(line: str) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `str` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `resolve_file`

Resolves a file path from a given line.

Args:
    file_path (str): The file path to resolve.
    line (str): The line containing the file path.

Returns:
    str: The resolved file path.

```python
safety.alerts.requirements.RequirementFile.resolve_file(file_path: str, line: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `file_path` | `str` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `safety.auth.cli.Auth` methods

### `get_auth_method`

Get the authentication method.

Returns:
    str: The authentication method.

```python
safety.auth.cli.Auth.get_auth_method(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `is_valid`

Check if the authentication information is valid.

Returns:
    bool: True if valid, False otherwise.

```python
safety.auth.cli.Auth.is_valid(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `refresh_from`

Refresh the authentication information from the provided info.

Args:
    info (dict): The information to refresh from.

```python
safety.auth.cli.Auth.refresh_from(self, info: Dict) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `info` | `Dict` | `—` | pos/kw |

### `safety.auth.cli.SafetyCLISubGroup` methods

### `add_command`

Registers another :class:`Command` with this group.  If the name
is not provided, the name of the command is used.

```python
safety.auth.cli.SafetyCLISubGroup.add_command(self, cmd: 'Command', name: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cmd` | `Command` | `—` | pos/kw |
| `name` | `str \| None` | `None` | pos/kw |

### `collect_usage_pieces`

Returns all the pieces that go into the usage line and returns
it as a list of strings.

```python
safety.auth.cli.SafetyCLISubGroup.collect_usage_pieces(self, ctx: 'Context') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `list[str]`

### `command`

Create a new command.

Args:
    *args: Variable length argument list.
    **kwargs: Arbitrary keyword arguments.

Returns:
    click.Command: The created command.

```python
safety.auth.cli.SafetyCLISubGroup.command(self, *args: Any, **kwargs: Any) -> click.core.Command
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `Any` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `<class 'click.core.Command'>`

### `format_commands`

Extra format methods for multi methods that adds all the commands
after the options.

```python
safety.auth.cli.SafetyCLISubGroup.format_commands(self, ctx: 'Context', formatter: 'HelpFormatter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `formatter` | `HelpFormatter` | `—` | pos/kw |

### `format_epilog`

Writes the epilog into the formatter if it exists.

```python
safety.auth.cli.SafetyCLISubGroup.format_epilog(self, ctx: 'Context', formatter: 'HelpFormatter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `formatter` | `HelpFormatter` | `—` | pos/kw |

### `format_help`

Format help message with rich formatting.

Args:
    ctx (click.Context): Click context.
    formatter (click.HelpFormatter): Click help formatter.

```python
safety.auth.cli.SafetyCLISubGroup.format_help(self, ctx: click.core.Context, formatter: click.formatting.HelpFormatter) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `formatter` | `HelpFormatter` | `—` | pos/kw |

### `format_help_text`

Writes the help text to the formatter if it exists.

```python
safety.auth.cli.SafetyCLISubGroup.format_help_text(self, ctx: 'Context', formatter: 'HelpFormatter') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `formatter` | `HelpFormatter` | `—` | pos/kw |

### `format_options`

Writes all the options into the formatter if they exist.

```python
safety.auth.cli.SafetyCLISubGroup.format_options(self, ctx: click.core.Context, formatter: click.formatting.HelpFormatter) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `formatter` | `HelpFormatter` | `—` | pos/kw |

### `format_usage`

Format usage message.

Args:
    ctx (click.Context): Click context.
    formatter (click.HelpFormatter): Click help formatter.

```python
safety.auth.cli.SafetyCLISubGroup.format_usage(self, ctx: click.core.Context, formatter: click.formatting.HelpFormatter) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `formatter` | `HelpFormatter` | `—` | pos/kw |

### `get_command`

Given a context and a command name, this returns a :class:`Command`
object if it exists or returns ``None``.

```python
safety.auth.cli.SafetyCLISubGroup.get_command(self, ctx: 'Context', cmd_name: 'str') -> 'Command | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `cmd_name` | `str` | `—` | pos/kw |

**Returns:** `Command | None`

### `get_help`

Formats the help into a string and returns it.

Calls :meth:`format_help` internally.

```python
safety.auth.cli.SafetyCLISubGroup.get_help(self, ctx: 'Context') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `str`

### `get_help_option`

Returns the help option object.

Skipped if :attr:`add_help_option` is ``False``.

.. versionchanged:: 8.1.8
    The help option is now cached to avoid creating it multiple times.

```python
safety.auth.cli.SafetyCLISubGroup.get_help_option(self, ctx: 'Context') -> 'Option | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `Option | None`

### `get_help_option_names`

Returns the names for the help option.

```python
safety.auth.cli.SafetyCLISubGroup.get_help_option_names(self, ctx: 'Context') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `list[str]`

### `get_params`

```python
safety.auth.cli.SafetyCLISubGroup.get_params(self, ctx: 'Context') -> 'list[Parameter]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `list[Parameter]`

### `get_short_help_str`

Gets short help for the command or makes it by shortening the
long help string.

```python
safety.auth.cli.SafetyCLISubGroup.get_short_help_str(self, limit: 'int' = 45) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `limit` | `int` | `45` | pos/kw |

**Returns:** `str`

### `get_usage`

Formats the usage line into a string and returns it.

Calls :meth:`format_usage` internally.

```python
safety.auth.cli.SafetyCLISubGroup.get_usage(self, ctx: 'Context') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `str`

### `group`

A shortcut decorator for declaring and attaching a group to
the group. This takes the same arguments as :func:`group` and
immediately registers the created group with this group by
calling :meth:`add…

```python
safety.auth.cli.SafetyCLISubGroup.group(self, *args: 't.Any', **kwargs: 't.Any') -> 't.Callable[[t.Callable[..., t.Any]], Group] | Group'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `t.Any` | `—` | *args |
| `kwargs` | `t.Any` | `—` | **kwargs |

**Returns:** `t.Callable[[t.Callable[..., t.Any]], Group] | Group`

### `invoke`

Given a context, this invokes the attached callback (if it exists)
in the right way.

```python
safety.auth.cli.SafetyCLISubGroup.invoke(self, ctx: 'Context') -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `t.Any`

### `list_commands`

Returns a list of subcommand names.
Note that in Click's Group class, these are sorted.
In Typer, we wish to maintain the original order of creation (cf Issue #933)

```python
safety.auth.cli.SafetyCLISubGroup.list_commands(self, ctx: click.core.Context) -> list[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `list[str]`

### `main`

This is the way to invoke a script with all the bells and
whistles as a command line application.  This will always terminate
the application after a call.  If this is not wanted, ``SystemExit``
need…

```python
safety.auth.cli.SafetyCLISubGroup.main(self, args: collections.abc.Sequence[str] | None = None, prog_name: str | None = None, complete_var: str | None = None, standalone_mode: bool = True, windows_expand_args: bool = True, **extra: Any) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `collections.abc.Sequence[str] \| None` | `None` | pos/kw |
| `prog_name` | `str \| None` | `None` | pos/kw |
| `complete_var` | `str \| None` | `None` | pos/kw |
| `standalone_mode` | `bool` | `True` | pos/kw |
| `windows_expand_args` | `bool` | `True` | pos/kw |
| `extra` | `Any` | `—` | **kwargs |

**Returns:** `typing.Any`

### `make_context`

This function when given an info name and arguments will kick
off the parsing and create a new :class:`Context`.  It does not
invoke the actual command callback though.

To quickly customize the cont…

```python
safety.auth.cli.SafetyCLISubGroup.make_context(self, info_name: 'str | None', args: 'list[str]', parent: 'Context | None' = None, **extra: 't.Any') -> 'Context'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `info_name` | `str \| None` | `—` | pos/kw |
| `args` | `list[str]` | `—` | pos/kw |
| `parent` | `Context \| None` | `None` | pos/kw |
| `extra` | `t.Any` | `—` | **kwargs |

**Returns:** `Context`

### `make_parser`

Creates the underlying option parser for this command.

```python
safety.auth.cli.SafetyCLISubGroup.make_parser(self, ctx: 'Context') -> '_OptionParser'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `_OptionParser`

### `parse_args`

```python
safety.auth.cli.SafetyCLISubGroup.parse_args(self, ctx: 'Context', args: 'list[str]') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `args` | `list[str]` | `—` | pos/kw |

**Returns:** `list[str]`

### `resolve_command`

```python
safety.auth.cli.SafetyCLISubGroup.resolve_command(self, ctx: click.core.Context, args: list[str]) -> tuple[str | None, click.core.Command | None, list[str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `args` | `list` | `—` | pos/kw |

**Returns:** `tuple[str | None, click.core.Command | None, list[str]]`

### `result_callback`

Adds a result callback to the command.  By default if a
result callback is already registered this will chain them but
this can be disabled with the `replace` parameter.  The result
callback is invok…

```python
safety.auth.cli.SafetyCLISubGroup.result_callback(self, replace: 'bool' = False) -> 't.Callable[[F], F]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `replace` | `bool` | `False` | pos/kw |

**Returns:** `t.Callable[[F], F]`

### `shell_complete`

Return a list of completions for the incomplete value. Looks
at the names of options, subcommands, and chained
multi-commands.

:param ctx: Invocation context for this command.
:param incomplete: Val…

```python
safety.auth.cli.SafetyCLISubGroup.shell_complete(self, ctx: 'Context', incomplete: 'str') -> 'list[CompletionItem]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `incomplete` | `str` | `—` | pos/kw |

**Returns:** `list[CompletionItem]`

### `to_info_dict`

```python
safety.auth.cli.SafetyCLISubGroup.to_info_dict(self, ctx: 'Context') -> 'dict[str, t.Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `dict[str, t.Any]`

### `safety.auth.cli_utils.Auth` methods

### `get_auth_method`

Get the authentication method.

Returns:
    str: The authentication method.

```python
safety.auth.cli_utils.Auth.get_auth_method(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `is_valid`

Check if the authentication information is valid.

Returns:
    bool: True if valid, False otherwise.

```python
safety.auth.cli_utils.Auth.is_valid(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `refresh_from`

Refresh the authentication information from the provided info.

Args:
    info (dict): The information to refresh from.

```python
safety.auth.cli_utils.Auth.refresh_from(self, info: Dict) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `info` | `Dict` | `—` | pos/kw |

### `safety.auth.cli_utils.DependentOption` methods

### `add_to_parser`

```python
safety.auth.cli_utils.DependentOption.add_to_parser(self, parser: '_OptionParser', ctx: 'Context') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `parser` | `_OptionParser` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

### `consume_value`

For :class:`Option`, the value can be collected from an interactive prompt
if the option is a flag that needs a value (and the :attr:`prompt` property is
set).

Additionally, this method handles flag…

```python
safety.auth.cli_utils.DependentOption.consume_value(self, ctx: 'Context', opts: 'cabc.Mapping[str, Parameter]') -> 'tuple[t.Any, ParameterSource]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `opts` | `cabc.Mapping[str, Parameter]` | `—` | pos/kw |

**Returns:** `tuple[t.Any, ParameterSource]`

### `get_default`

Return the default value for this option.

For non-boolean flag options, ``default=True`` is treated as a sentinel
meaning "activate this flag by default" and is resolved to
:attr:`flag_value`.  For…

```python
safety.auth.cli_utils.DependentOption.get_default(self, ctx: 'Context', call: 'bool' = True) -> 't.Any | t.Callable[[], t.Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `call` | `bool` | `True` | pos/kw |

**Returns:** `t.Any | t.Callable[[], t.Any] | None`

### `get_error_hint`

Get a stringified version of the param for use in error messages to
indicate which param caused the error.

```python
safety.auth.cli_utils.DependentOption.get_error_hint(self, ctx: 'Context') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `str`

### `get_help_extra`

```python
safety.auth.cli_utils.DependentOption.get_help_extra(self, ctx: 'Context') -> 'types.OptionHelpExtra'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `types.OptionHelpExtra`

### `get_help_record`

```python
safety.auth.cli_utils.DependentOption.get_help_record(self, ctx: 'Context') -> 'tuple[str, str] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `tuple[str, str] | None`

### `get_usage_pieces`

```python
safety.auth.cli_utils.DependentOption.get_usage_pieces(self, ctx: 'Context') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `list[str]`

### `handle_parse_result`

Handle the parse result for dependent options.

Args:
    ctx (click.Context): The click context.
    opts (Dict[str, Any]): The options dictionary.
    args (List[str]): The arguments list.

Returns…

```python
safety.auth.cli_utils.DependentOption.handle_parse_result(self, ctx: click.core.Context, opts: Dict[str, Any], args: List[str]) -> Tuple[Any, List[str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `opts` | `Dict` | `—` | pos/kw |
| `args` | `List` | `—` | pos/kw |

**Returns:** `typing.Tuple[typing.Any, typing.List[str]]`

### `make_metavar`

```python
safety.auth.cli_utils.DependentOption.make_metavar(self, ctx: 'Context') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `str`

### `process_value`

Process the value of this parameter:

1. Type cast the value using :meth:`type_cast_value`.
2. Check if the value is missing (see: :meth:`value_is_missing`), and raise
   :exc:`MissingParameter` if i…

```python
safety.auth.cli_utils.DependentOption.process_value(self, ctx: 'Context', value: 't.Any') -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `value` | `t.Any` | `—` | pos/kw |

**Returns:** `t.Any`

### `prompt_for_value`

This is an alternative flow that can be activated in the full
value processing if a value does not exist.  It will prompt the
user until a valid value exists and then returns the processed
value as r…

```python
safety.auth.cli_utils.DependentOption.prompt_for_value(self, ctx: 'Context') -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `t.Any`

### `resolve_envvar_value`

:class:`Option` resolves its environment variable the same way as
:func:`Parameter.resolve_envvar_value`, but it also supports
:attr:`Context.auto_envvar_prefix`. If we could not find an environment…

```python
safety.auth.cli_utils.DependentOption.resolve_envvar_value(self, ctx: 'Context') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `str | None`

### `shell_complete`

Return a list of completions for the incomplete value. If a
``shell_complete`` function was given during init, it is used.
Otherwise, the :attr:`type`
:meth:`~click.types.ParamType.shell_complete` fu…

```python
safety.auth.cli_utils.DependentOption.shell_complete(self, ctx: 'Context', incomplete: 'str') -> 'list[CompletionItem]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `incomplete` | `str` | `—` | pos/kw |

**Returns:** `list[CompletionItem]`

### `to_info_dict`

.. versionchanged:: 8.3.0
    Returns ``None`` for the :attr:`flag_value` if it was not set.

```python
safety.auth.cli_utils.DependentOption.to_info_dict(self) -> 'dict[str, t.Any]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, t.Any]`

### `type_cast_value`

Convert and validate a value against the parameter's
:attr:`type`, :attr:`multiple`, and :attr:`nargs`.

```python
safety.auth.cli_utils.DependentOption.type_cast_value(self, ctx: 'Context', value: 't.Any') -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |
| `value` | `t.Any` | `—` | pos/kw |

**Returns:** `t.Any`

### `value_from_envvar`

For :class:`Option`, this method processes the raw environment variable
string the same way as :func:`Parameter.value_from_envvar` does.

But in the case of non-boolean flags, the value is analyzed t…

```python
safety.auth.cli_utils.DependentOption.value_from_envvar(self, ctx: 'Context') -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `ctx` | `Context` | `—` | pos/kw |

**Returns:** `t.Any`

### `value_is_missing`

A value is considered missing if:

- it is :attr:`UNSET`,
- or if it is an empty sequence while the parameter is suppose to have
  non-single value (i.e. :attr:`nargs` is not ``1`` or :attr:`multiple…

```python
safety.auth.cli_utils.DependentOption.value_is_missing(self, value: 't.Any') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `t.Any` | `—` | pos/kw |

**Returns:** `bool`

### `safety.auth.cli_utils.Organization` methods

### `to_dict`

Convert the Organization instance to a dictionary.

Returns:
    dict: The dictionary representation of the organization.

```python
safety.auth.cli_utils.Organization.to_dict(self) -> Dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict`

### `safety.auth.cli_utils.S3PresignedAdapter` methods

### `add_headers`

Add any headers needed by the connection. As of v2.0 this does
nothing by default, but is left for overriding by users that subclass
the :class:`HTTPAdapter <requests.adapters.HTTPAdapter>`.

This sh…

```python
safety.auth.cli_utils.S3PresignedAdapter.add_headers(self, request, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `build_connection_pool_key_attributes`

Build the PoolKey attributes used by urllib3 to return a connection.

This looks at the PreparedRequest, the user-specified verify value,
and the value of the cert parameter to determine what PoolKey…

```python
safety.auth.cli_utils.S3PresignedAdapter.build_connection_pool_key_attributes(self, request, verify, cert=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `verify` | `—` | `—` | pos/kw |
| `cert` | `—` | `None` | pos/kw |

### `build_response`

Builds a :class:`Response <requests.Response>` object from a urllib3
response. This should not be called from user code, and is only exposed
for use when subclassing the
:class:`HTTPAdapter <requests…

```python
safety.auth.cli_utils.S3PresignedAdapter.build_response(self, req, resp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `req` | `—` | `—` | pos/kw |
| `resp` | `—` | `—` | pos/kw |

### `cert_verify`

Verify a SSL certificate. This method should not be called from user
code, and is only exposed for use when subclassing the
:class:`HTTPAdapter <requests.adapters.HTTPAdapter>`.

:param conn: The url…

```python
safety.auth.cli_utils.S3PresignedAdapter.cert_verify(self, conn, url, verify, cert)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `conn` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `verify` | `—` | `—` | pos/kw |
| `cert` | `—` | `—` | pos/kw |

### `close`

Disposes of any internal state.

Currently, this closes the PoolManager and any active ProxyManager,
which closes any pooled connections.

```python
safety.auth.cli_utils.S3PresignedAdapter.close(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `get_connection`

DEPRECATED: Users should move to `get_connection_with_tls_context`
for all subclasses of HTTPAdapter using Requests>=2.32.2.

Returns a urllib3 connection for the given URL. This should not be
called…

```python
safety.auth.cli_utils.S3PresignedAdapter.get_connection(self, url, proxies=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `proxies` | `—` | `None` | pos/kw |

### `get_connection_with_tls_context`

Returns a urllib3 connection for the given request and TLS settings.
This should not be called from user code, and is only exposed for use
when subclassing the :class:`HTTPAdapter <requests.adapters.…

```python
safety.auth.cli_utils.S3PresignedAdapter.get_connection_with_tls_context(self, request, verify, proxies=None, cert=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `verify` | `—` | `—` | pos/kw |
| `proxies` | `—` | `None` | pos/kw |
| `cert` | `—` | `None` | pos/kw |

### `init_poolmanager`

Initializes a urllib3 PoolManager.

This method should not be called from user code, and is only
exposed for use when subclassing the
:class:`HTTPAdapter <requests.adapters.HTTPAdapter>`.

:param con…

```python
safety.auth.cli_utils.S3PresignedAdapter.init_poolmanager(self, connections, maxsize, block=False, **pool_kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `connections` | `—` | `—` | pos/kw |
| `maxsize` | `—` | `—` | pos/kw |
| `block` | `—` | `False` | pos/kw |
| `pool_kwargs` | `—` | `—` | **kwargs |

### `proxy_headers`

Returns a dictionary of the headers to add to any request sent
through a proxy. This works with urllib3 magic to ensure that they are
correctly sent to the proxy, rather than in a tunnelled request i…

```python
safety.auth.cli_utils.S3PresignedAdapter.proxy_headers(self, proxy)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `proxy` | `—` | `—` | pos/kw |

### `proxy_manager_for`

Return urllib3 ProxyManager for the given proxy.

This method should not be called from user code, and is only
exposed for use when subclassing the
:class:`HTTPAdapter <requests.adapters.HTTPAdapter>…

```python
safety.auth.cli_utils.S3PresignedAdapter.proxy_manager_for(self, proxy, **proxy_kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `proxy` | `—` | `—` | pos/kw |
| `proxy_kwargs` | `—` | `—` | **kwargs |

### `request_url`

Obtain the url to use when making the final request.

If the message is being sent through a HTTP proxy, the full URL has to
be used. Otherwise, we should only use the path portion of the URL.

This…

```python
safety.auth.cli_utils.S3PresignedAdapter.request_url(self, request, proxies)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |
| `proxies` | `—` | `—` | pos/kw |

### `send`

Send a request, removing the Authorization header.

Args:
    request (requests.PreparedRequest): The prepared request.
    **kwargs (Any): Additional keyword arguments.

Returns:
    requests.Respon…

```python
safety.auth.cli_utils.S3PresignedAdapter.send(self, request: requests.models.PreparedRequest, **kwargs: Any) -> requests.models.Response
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `PreparedRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `<class 'requests.models.Response'>`

### `safety.auth.cli_utils.SafetyAuthSession` methods

### `audit_packages`

```python
safety.auth.cli_utils.SafetyAuthSession.audit_packages(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `check_project`

```python
safety.auth.cli_utils.SafetyAuthSession.check_project(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `check_updates`

```python
safety.auth.cli_utils.SafetyAuthSession.check_updates(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `client_auth`

```python
safety.auth.cli_utils.SafetyAuthSession.client_auth(self, auth_method)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `auth_method` | `—` | `—` | pos/kw |

### `close`

Closes all adapters and as such the session

```python
safety.auth.cli_utils.SafetyAuthSession.close(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_authorization_url`

Generate an authorization URL and state.

:param url: Authorization endpoint url, must be HTTPS.
:param state: An optional state string for CSRF protection. If not
              given it will be gene…

```python
safety.auth.cli_utils.SafetyAuthSession.create_authorization_url(self, url, state=None, code_verifier=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `state` | `—` | `None` | pos/kw |
| `code_verifier` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `delete`

Sends a DELETE request. Returns :class:`Response` object.

:param url: URL for the new :class:`Request` object.
:param \*\*kwargs: Optional arguments that ``request`` takes.
:rtype: requests.Response

```python
safety.auth.cli_utils.SafetyAuthSession.delete(self, url, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `download_policy`

```python
safety.auth.cli_utils.SafetyAuthSession.download_policy(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ensure_active_token`

```python
safety.auth.cli_utils.SafetyAuthSession.ensure_active_token(self, token=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `token` | `—` | `None` | pos/kw |

### `fetch_access_token`

Alias for fetch_token.

```python
safety.auth.cli_utils.SafetyAuthSession.fetch_access_token(self, url=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `fetch_openid_config`

Fetch the OpenID configuration from the authorization server.

Returns:
    Any: The OpenID configuration.

```python
safety.auth.cli_utils.SafetyAuthSession.fetch_openid_config(self) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Any`

### `fetch_token`

Generic method for fetching an access token from the token endpoint.

:param url: Access Token endpoint URL, if not configured,
            ``authorization_response`` is used to extract token from…

```python
safety.auth.cli_utils.SafetyAuthSession.fetch_token(self, url=None, body='', method='POST', headers=None, auth=None, grant_type=None, state=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `None` | pos/kw |
| `body` | `—` | `''` | pos/kw |
| `method` | `—` | `'POST'` | pos/kw |
| `headers` | `—` | `None` | pos/kw |
| `auth` | `—` | `None` | pos/kw |
| `grant_type` | `—` | `None` | pos/kw |
| `state` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `fetch_user_info`

```python
safety.auth.cli_utils.SafetyAuthSession.fetch_user_info(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `get`

Sends a GET request. Returns :class:`Response` object.

:param url: URL for the new :class:`Request` object.
:param \*\*kwargs: Optional arguments that ``request`` takes.
:rtype: requests.Response

```python
safety.auth.cli_utils.SafetyAuthSession.get(self, url, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `get_adapter`

Returns the appropriate connection adapter for the given URL.

:rtype: requests.adapters.BaseAdapter

```python
safety.auth.cli_utils.SafetyAuthSession.get_adapter(self, url)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |

### `get_authentication_type`

Get the type of authentication being used.

Returns:
    AuthenticationType: The type of authentication.

```python
safety.auth.cli_utils.SafetyAuthSession.get_authentication_type(self) -> safety.scan.util.AuthenticationType
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<enum 'AuthenticationType'>`

### `get_credential`

Get the current authentication credential.

Returns:
    Optional[str]: The API key, token, or None.

```python
safety.auth.cli_utils.SafetyAuthSession.get_credential(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_redirect_target`

Receives a Response. Returns a redirect URI or ``None``

```python
safety.auth.cli_utils.SafetyAuthSession.get_redirect_target(self, resp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `resp` | `—` | `—` | pos/kw |

### `head`

Sends a HEAD request. Returns :class:`Response` object.

:param url: URL for the new :class:`Request` object.
:param \*\*kwargs: Optional arguments that ``request`` takes.
:rtype: requests.Response

```python
safety.auth.cli_utils.SafetyAuthSession.head(self, url, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `initialize`

```python
safety.auth.cli_utils.SafetyAuthSession.initialize(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `introspect_token`

Implementation of OAuth 2.0 Token Introspection defined via `RFC7662`_.

:param url: Introspection Endpoint, must be HTTPS.
:param token: The token to be introspected.
:param token_type_hint: The typ…

```python
safety.auth.cli_utils.SafetyAuthSession.introspect_token(self, url, token=None, token_type_hint=None, body=None, auth=None, headers=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `token` | `—` | `None` | pos/kw |
| `token_type_hint` | `—` | `None` | pos/kw |
| `body` | `—` | `None` | pos/kw |
| `auth` | `—` | `None` | pos/kw |
| `headers` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `is_using_auth_credentials`

Check if the session is using authentication credentials.

This does NOT check if the client is authenticated.

Returns:
    bool: True if using authentication credentials, False otherwise.

```python
safety.auth.cli_utils.SafetyAuthSession.is_using_auth_credentials(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `merge_environment_settings`

Check the environment and merge it with some settings.

:rtype: dict

```python
safety.auth.cli_utils.SafetyAuthSession.merge_environment_settings(self, url, proxies, stream, verify, cert)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `proxies` | `—` | `—` | pos/kw |
| `stream` | `—` | `—` | pos/kw |
| `verify` | `—` | `—` | pos/kw |
| `cert` | `—` | `—` | pos/kw |

### `mount`

Registers a connection adapter to a prefix.

Adapters are sorted in descending order by prefix length.

```python
safety.auth.cli_utils.SafetyAuthSession.mount(self, prefix, adapter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `prefix` | `—` | `—` | pos/kw |
| `adapter` | `—` | `—` | pos/kw |

### `options`

Sends a OPTIONS request. Returns :class:`Response` object.

:param url: URL for the new :class:`Request` object.
:param \*\*kwargs: Optional arguments that ``request`` takes.
:rtype: requests.Response

```python
safety.auth.cli_utils.SafetyAuthSession.options(self, url, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `parse_response_token`

```python
safety.auth.cli_utils.SafetyAuthSession.parse_response_token(self, resp)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `resp` | `—` | `—` | pos/kw |

### `patch`

Sends a PATCH request. Returns :class:`Response` object.

:param url: URL for the new :class:`Request` object.
:param data: (optional) Dictionary, list of tuples, bytes, or file-like
    object to se…

```python
safety.auth.cli_utils.SafetyAuthSession.patch(self, url, data=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `data` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `post`

Sends a POST request. Returns :class:`Response` object.

:param url: URL for the new :class:`Request` object.
:param data: (optional) Dictionary, list of tuples, bytes, or file-like
    object to sen…

```python
safety.auth.cli_utils.SafetyAuthSession.post(self, url, data=None, json=None, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `url` | `—` | `—` | pos/kw |
| `data` | `—` | `None` | pos/kw |
| `json` | `—` | `None` | pos/kw |
| `kwargs` | `—` | `—` | **kwargs |

### `prepare_request`

Constructs a :class:`PreparedRequest <PreparedRequest>` for
transmission and returns it. The :class:`PreparedRequest` has settings
merged from the :class:`Request <Request>` instance and those of the…

```python
safety.auth.cli_utils.SafetyAuthSession.prepare_request(self, request)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `request` | `—` | `—` | pos/kw |

### `project`

```python
safety.auth.cli_utils.SafetyAuthSession.project(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `safety.auth.main.Organization` methods

### `to_dict`

Convert the Organization instance to a dictionary.

Returns:
    dict: The dictionary representation of the organization.

```python
safety.auth.main.Organization.to_dict(self) -> Dict
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Dict`


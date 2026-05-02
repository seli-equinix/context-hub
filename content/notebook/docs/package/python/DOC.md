---
name: package
description: "Jupyter Notebook package guide for Python with install, launch, configuration, security, extensions, and Notebook 7 migration notes"
metadata:
  languages: "python"
  versions: "7.5.5"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "notebook,python,jupyter,server,ipynb,interactive,development,passwd,Version-Sensitive,serverapp,ConsoleHandler,add_header,check_etag_header,check_host,check_origin,check_referer,check_xsrf_cookie,clear,clear_all_cookies,clear_cookie,clear_header,clear_login_cookie,compute_etag,create_signed_value,create_template_loader,data_received,decode_argument,delete,detach,finish,flush,force_clear_cookie,get,get_argument,get_arguments,get_body_argument,get_body_arguments,get_browser_locale,get_cookie,get_current_user,get_json_body,CustomCssHandler,FileHandler,JupyterNotebookApp,add_traits,class_config_rst_doc,class_config_section,class_get_help,class_get_trait_help,class_own_trait_events,class_own_traits,class_print_help,class_trait_names,class_traits,clear_instance,close_handlers,current_activity,document_config_options,emit_alias_help,emit_description,emit_examples,emit_flag_help,emit_help,emit_help_epilogue,emit_options_help,emit_subcommands_help,exit,flatten_flags,generate_config_file,get_default_logging_config,get_extension_package,get_extension_point,has_trait,hold_trait_notifications,NotebookBaseHandler,NotebookConfigShimMixin,shim_config_from_notebook_to_jupyter_server,update_config,NotebookHandler,TerminalHandler"
---

# notebook — package

## Install

```bash
pip install notebook
```

## Imports

```python
import notebook
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `ConsoleHandler` | Class | A console page handler. |
| `add_header` | Method | Adds the given response header and value.  Unlike `set_header`, `add_header` ma… |
| `check_etag_header` | Method | Checks the ``Etag`` header against requests's ``If-None-Match``.  Returns ``Tru… |
| `check_host` | Method | Check the host header if remote access disallowed.  Returns True if the request… |
| `check_origin` | Method | Check Origin for cross-site API requests, including websockets  Copied from Web… |
| `check_referer` | Method | Check Referer for cross-site requests. Disables requests to certain endpoints w… |
| `check_xsrf_cookie` | Method | Bypass xsrf cookie checks when token-authenticated |
| `clear` | Method | Resets all headers and content for this response. |
| `clear_all_cookies` | Method | Attempt to delete all the cookies the user sent with this request.  See `clear_… |
| `clear_cookie` | Method | Deletes the cookie with the given name.  This method accepts the same arguments… |
| `clear_header` | Method | Clears an outgoing header, undoing a previous `set_header` call.  Note that thi… |
| `clear_login_cookie` | Method | Clear a login cookie. |
| `compute_etag` | Method | Computes the etag header to be used for this request.  By default uses a hash o… |
| `create_signed_value` | Method | Signs and timestamps a string so it cannot be forged.  Normally used via set_si… |
| `create_template_loader` | Method | Returns a new template loader for the given path.  May be overridden by subclas… |
| `data_received` | Method | Implement this method to handle streamed request data.  Requires the `.stream_r… |
| `decode_argument` | Method | Decodes an argument from the request.  The argument has been percent-decoded an… |
| `delete` | Method |  |
| `detach` | Method | Take control of the underlying stream.  Returns the underlying `.IOStream` obje… |
| `finish` | Method | Finishes this response, ending the HTTP request.  Passing a ``chunk`` to ``fini… |
| `flush` | Method | Flushes the current output buffer to the network.  .. versionchanged:: 4.0    N… |
| `force_clear_cookie` | Method | Force a cookie clear. |
| `get` | Method | Get the console page. |
| `get_argument` | Method | Returns the value of the argument with the given name.  If default is not provi… |
| `get_arguments` | Method | Returns a list of the arguments with the given name.  If the argument is not pr… |
| `get_body_argument` | Method | Returns the value of the argument with the given name from the request body.  I… |
| `get_body_arguments` | Method | Returns a list of the body arguments with the given name.  If the argument is n… |
| `get_browser_locale` | Method | Determines the user's locale from ``Accept-Language`` header.  See http://www.w… |
| `get_cookie` | Method | Returns the value of the request cookie with the given name.  If the named cook… |
| `get_current_user` | Method | Get the current user. |
| `get_json_body` | Method | Return the body of the request as JSON data. |
| `CustomCssHandler` | Class | A custom CSS handler. |
| `add_header` | Method | Adds the given response header and value.  Unlike `set_header`, `add_header` ma… |
| `check_etag_header` | Method | Checks the ``Etag`` header against requests's ``If-None-Match``.  Returns ``Tru… |
| `check_host` | Method | Check the host header if remote access disallowed.  Returns True if the request… |
| `check_origin` | Method | Check Origin for cross-site API requests, including websockets  Copied from Web… |
| `check_referer` | Method | Check Referer for cross-site requests. Disables requests to certain endpoints w… |
| `check_xsrf_cookie` | Method | Bypass xsrf cookie checks when token-authenticated |
| `clear` | Method | Resets all headers and content for this response. |
| `clear_all_cookies` | Method | Attempt to delete all the cookies the user sent with this request.  See `clear_… |
| `clear_cookie` | Method | Deletes the cookie with the given name.  This method accepts the same arguments… |
| `clear_header` | Method | Clears an outgoing header, undoing a previous `set_header` call.  Note that thi… |
| `clear_login_cookie` | Method | Clear a login cookie. |
| `compute_etag` | Method | Computes the etag header to be used for this request.  By default uses a hash o… |
| `create_signed_value` | Method | Signs and timestamps a string so it cannot be forged.  Normally used via set_si… |
| `create_template_loader` | Method | Returns a new template loader for the given path.  May be overridden by subclas… |
| `data_received` | Method | Implement this method to handle streamed request data.  Requires the `.stream_r… |
| `decode_argument` | Method | Decodes an argument from the request.  The argument has been percent-decoded an… |
| `delete` | Method |  |
| `detach` | Method | Take control of the underlying stream.  Returns the underlying `.IOStream` obje… |
| `finish` | Method | Finishes this response, ending the HTTP request.  Passing a ``chunk`` to ``fini… |
| `flush` | Method | Flushes the current output buffer to the network.  .. versionchanged:: 4.0    N… |
| `force_clear_cookie` | Method | Force a cookie clear. |
| `get` | Method | Get the custom css file. |
| `get_argument` | Method | Returns the value of the argument with the given name.  If default is not provi… |
| `get_arguments` | Method | Returns a list of the arguments with the given name.  If the argument is not pr… |
| `get_body_argument` | Method | Returns the value of the argument with the given name from the request body.  I… |
| `get_body_arguments` | Method | Returns a list of the body arguments with the given name.  If the argument is n… |
| `get_browser_locale` | Method | Determines the user's locale from ``Accept-Language`` header.  See http://www.w… |
| `get_cookie` | Method | Returns the value of the request cookie with the given name.  If the named cook… |
| `get_current_user` | Method | Get the current user. |
| `get_json_body` | Method | Return the body of the request as JSON data. |
| `FileHandler` | Class | A file page handler. |
| `add_header` | Method | Adds the given response header and value.  Unlike `set_header`, `add_header` ma… |
| `check_etag_header` | Method | Checks the ``Etag`` header against requests's ``If-None-Match``.  Returns ``Tru… |
| `check_host` | Method | Check the host header if remote access disallowed.  Returns True if the request… |
| `check_origin` | Method | Check Origin for cross-site API requests, including websockets  Copied from Web… |
| `check_referer` | Method | Check Referer for cross-site requests. Disables requests to certain endpoints w… |
| `check_xsrf_cookie` | Method | Bypass xsrf cookie checks when token-authenticated |
| `clear` | Method | Resets all headers and content for this response. |
| `clear_all_cookies` | Method | Attempt to delete all the cookies the user sent with this request.  See `clear_… |
| `clear_cookie` | Method | Deletes the cookie with the given name.  This method accepts the same arguments… |
| `clear_header` | Method | Clears an outgoing header, undoing a previous `set_header` call.  Note that thi… |
| `clear_login_cookie` | Method | Clear a login cookie. |
| `compute_etag` | Method | Computes the etag header to be used for this request.  By default uses a hash o… |
| `create_signed_value` | Method | Signs and timestamps a string so it cannot be forged.  Normally used via set_si… |
| `create_template_loader` | Method | Returns a new template loader for the given path.  May be overridden by subclas… |
| `data_received` | Method | Implement this method to handle streamed request data.  Requires the `.stream_r… |
| `decode_argument` | Method | Decodes an argument from the request.  The argument has been percent-decoded an… |
| `delete` | Method |  |
| `detach` | Method | Take control of the underlying stream.  Returns the underlying `.IOStream` obje… |
| `finish` | Method | Finishes this response, ending the HTTP request.  Passing a ``chunk`` to ``fini… |
| `flush` | Method | Flushes the current output buffer to the network.  .. versionchanged:: 4.0    N… |
| `force_clear_cookie` | Method | Force a cookie clear. |
| `get` | Method | Get the file page. |
| `get_argument` | Method | Returns the value of the argument with the given name.  If default is not provi… |
| `get_arguments` | Method | Returns a list of the arguments with the given name.  If the argument is not pr… |
| `get_body_argument` | Method | Returns the value of the argument with the given name from the request body.  I… |
| `get_body_arguments` | Method | Returns a list of the body arguments with the given name.  If the argument is n… |
| `get_browser_locale` | Method | Determines the user's locale from ``Accept-Language`` header.  See http://www.w… |
| `get_cookie` | Method | Returns the value of the request cookie with the given name.  If the named cook… |
| `get_current_user` | Method | Get the current user. |
| `get_json_body` | Method | Return the body of the request as JSON data. |
| `JupyterNotebookApp` | Class | The notebook server extension app. |
| `add_traits` | Method | Dynamically add trait attributes to the HasTraits instance. |
| `class_config_rst_doc` | Method | Generate rST documentation for this class' config options.  Excludes traits def… |
| `class_config_section` | Method | Get the config section for this class.  Parameters ---------- classes : list, o… |
| `class_get_help` | Method | Get the help string for this class in ReST format.  If `inst` is given, its cur… |
| `class_get_trait_help` | Method | Get the helptext string for a single trait.  :param inst:     If given, its cur… |
| `class_own_trait_events` | Method | Get a dict of all event handlers defined on this class, not a parent.  Works li… |
| `class_own_traits` | Method | Get a dict of all the traitlets defined on this class, not a parent.  Works lik… |
| `class_print_help` | Method | Get the help string for a single trait and print it. |
| `class_trait_names` | Method | Get a list of all the names of this class' traits.  This method is just like th… |
| `class_traits` | Method | Get a ``dict`` of all the traits of this class.  The dictionary is keyed on the… |
| `clear_instance` | Method | unset _instance for this class and singleton parents. |
| `close_handlers` | Method |  |
| `current_activity` | Method | Return a list of activity happening in this extension. |
| `document_config_options` | Method | Generate rST format documentation for the config options this application  Retu… |
| `emit_alias_help` | Method | Yield the lines for alias part of the help. |
| `emit_description` | Method | Yield lines with the application description. |
| `emit_examples` | Method | Yield lines with the usage and examples.  This usage string goes at the end of… |
| `emit_flag_help` | Method | Yield the lines for the flag part of the help. |
| `emit_help` | Method | Yield the help-lines for each Configurable class in self.classes.  If classes=F… |
| `emit_help_epilogue` | Method | Yield the very bottom lines of the help message.  If classes=False (the default… |
| `emit_options_help` | Method | Yield the lines for the options part of the help. |
| `emit_subcommands_help` | Method | Yield the lines for the subcommand part of the help. |
| `exit` | Method |  |
| `flatten_flags` | Method | Flatten flags and aliases for loaders, so cl-args override as expected.  This p… |
| `generate_config_file` | Method | generate default config file from Configurables |
| `get_default_logging_config` | Method | Return the base logging configuration.  The default is to log to stderr using a… |
| `get_extension_package` | Method | Get an extension package. |
| `get_extension_point` | Method | Get an extension point. |
| `has_trait` | Method | Returns True if the object has a trait with the specified name. |
| `hold_trait_notifications` | Method | Context manager for bundling trait change notifications and cross validation.… |
| `NotebookBaseHandler` | Class | The base notebook API handler. |
| `add_header` | Method | Adds the given response header and value.  Unlike `set_header`, `add_header` ma… |
| `check_etag_header` | Method | Checks the ``Etag`` header against requests's ``If-None-Match``.  Returns ``Tru… |
| `check_host` | Method | Check the host header if remote access disallowed.  Returns True if the request… |
| `check_origin` | Method | Check Origin for cross-site API requests, including websockets  Copied from Web… |
| `check_referer` | Method | Check Referer for cross-site requests. Disables requests to certain endpoints w… |
| `check_xsrf_cookie` | Method | Bypass xsrf cookie checks when token-authenticated |
| `clear` | Method | Resets all headers and content for this response. |
| `clear_all_cookies` | Method | Attempt to delete all the cookies the user sent with this request.  See `clear_… |
| `clear_cookie` | Method | Deletes the cookie with the given name.  This method accepts the same arguments… |
| `clear_header` | Method | Clears an outgoing header, undoing a previous `set_header` call.  Note that thi… |
| `clear_login_cookie` | Method | Clear a login cookie. |
| `compute_etag` | Method | Computes the etag header to be used for this request.  By default uses a hash o… |
| `create_signed_value` | Method | Signs and timestamps a string so it cannot be forged.  Normally used via set_si… |
| `create_template_loader` | Method | Returns a new template loader for the given path.  May be overridden by subclas… |
| `data_received` | Method | Implement this method to handle streamed request data.  Requires the `.stream_r… |
| `decode_argument` | Method | Decodes an argument from the request.  The argument has been percent-decoded an… |
| `delete` | Method |  |
| `detach` | Method | Take control of the underlying stream.  Returns the underlying `.IOStream` obje… |
| `finish` | Method | Finishes this response, ending the HTTP request.  Passing a ``chunk`` to ``fini… |
| `flush` | Method | Flushes the current output buffer to the network.  .. versionchanged:: 4.0    N… |
| `force_clear_cookie` | Method | Force a cookie clear. |
| `get` | Method |  |
| `get_argument` | Method | Returns the value of the argument with the given name.  If default is not provi… |
| `get_arguments` | Method | Returns a list of the arguments with the given name.  If the argument is not pr… |
| `get_body_argument` | Method | Returns the value of the argument with the given name from the request body.  I… |
| `get_body_arguments` | Method | Returns a list of the body arguments with the given name.  If the argument is n… |
| `get_browser_locale` | Method | Determines the user's locale from ``Accept-Language`` header.  See http://www.w… |
| `get_cookie` | Method | Returns the value of the request cookie with the given name.  If the named cook… |
| `get_current_user` | Method | Get the current user. |
| `get_json_body` | Method | Return the body of the request as JSON data. |
| `NotebookConfigShimMixin` | Class | A Mixin class for shimming configuration from NotebookApp to ServerApp. This cl… |
| `shim_config_from_notebook_to_jupyter_server` | Method | Reorganizes a config object to reroute traits to their expected destinations af… |
| `update_config` | Method | Update config and load the new values |
| `NotebookHandler` | Class | A notebook page handler. |
| `add_header` | Method | Adds the given response header and value.  Unlike `set_header`, `add_header` ma… |
| `check_etag_header` | Method | Checks the ``Etag`` header against requests's ``If-None-Match``.  Returns ``Tru… |
| `check_host` | Method | Check the host header if remote access disallowed.  Returns True if the request… |
| `check_origin` | Method | Check Origin for cross-site API requests, including websockets  Copied from Web… |
| `check_referer` | Method | Check Referer for cross-site requests. Disables requests to certain endpoints w… |
| `check_xsrf_cookie` | Method | Bypass xsrf cookie checks when token-authenticated |
| `clear` | Method | Resets all headers and content for this response. |
| `clear_all_cookies` | Method | Attempt to delete all the cookies the user sent with this request.  See `clear_… |
| `clear_cookie` | Method | Deletes the cookie with the given name.  This method accepts the same arguments… |
| `clear_header` | Method | Clears an outgoing header, undoing a previous `set_header` call.  Note that thi… |
| `clear_login_cookie` | Method | Clear a login cookie. |
| `compute_etag` | Method | Computes the etag header to be used for this request.  By default uses a hash o… |
| `create_signed_value` | Method | Signs and timestamps a string so it cannot be forged.  Normally used via set_si… |
| `create_template_loader` | Method | Returns a new template loader for the given path.  May be overridden by subclas… |
| `data_received` | Method | Implement this method to handle streamed request data.  Requires the `.stream_r… |
| `decode_argument` | Method | Decodes an argument from the request.  The argument has been percent-decoded an… |
| `delete` | Method |  |
| `detach` | Method | Take control of the underlying stream.  Returns the underlying `.IOStream` obje… |
| `finish` | Method | Finishes this response, ending the HTTP request.  Passing a ``chunk`` to ``fini… |
| `flush` | Method | Flushes the current output buffer to the network.  .. versionchanged:: 4.0    N… |
| `force_clear_cookie` | Method | Force a cookie clear. |
| `get` | Method | Get the notebook page. Redirect if it's a directory. |
| `get_argument` | Method | Returns the value of the argument with the given name.  If default is not provi… |
| `get_arguments` | Method | Returns a list of the arguments with the given name.  If the argument is not pr… |
| `get_body_argument` | Method | Returns the value of the argument with the given name from the request body.  I… |
| `get_body_arguments` | Method | Returns a list of the body arguments with the given name.  If the argument is n… |
| `get_browser_locale` | Method | Determines the user's locale from ``Accept-Language`` header.  See http://www.w… |
| `get_cookie` | Method | Returns the value of the request cookie with the given name.  If the named cook… |
| `get_current_user` | Method | Get the current user. |
| `get_json_body` | Method | Return the body of the request as JSON data. |
| `TerminalHandler` | Class | A terminal page handler. |
| `add_header` | Method | Adds the given response header and value.  Unlike `set_header`, `add_header` ma… |
| `check_etag_header` | Method | Checks the ``Etag`` header against requests's ``If-None-Match``.  Returns ``Tru… |
| `check_host` | Method | Check the host header if remote access disallowed.  Returns True if the request… |
| `check_origin` | Method | Check Origin for cross-site API requests, including websockets  Copied from Web… |
| `check_referer` | Method | Check Referer for cross-site requests. Disables requests to certain endpoints w… |
| `check_xsrf_cookie` | Method | Bypass xsrf cookie checks when token-authenticated |
| `clear` | Method | Resets all headers and content for this response. |
| `clear_all_cookies` | Method | Attempt to delete all the cookies the user sent with this request.  See `clear_… |
| `clear_cookie` | Method | Deletes the cookie with the given name.  This method accepts the same arguments… |
| `clear_header` | Method | Clears an outgoing header, undoing a previous `set_header` call.  Note that thi… |

## Classes

### `ConsoleHandler`

A console page handler.

```python
notebook.app.ConsoleHandler(self, application: 'Application', request: tornado.httputil.HTTPServerRequest, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `application` | `Application` | `—` | pos/kw |
| `request` | `HTTPServerRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `CustomCssHandler`

A custom CSS handler.

```python
notebook.app.CustomCssHandler(self, application: 'Application', request: tornado.httputil.HTTPServerRequest, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `application` | `Application` | `—` | pos/kw |
| `request` | `HTTPServerRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `FileHandler`

A file page handler.

```python
notebook.app.FileHandler(self, application: 'Application', request: tornado.httputil.HTTPServerRequest, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `application` | `Application` | `—` | pos/kw |
| `request` | `HTTPServerRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `JupyterNotebookApp`

The notebook server extension app.

```python
notebook.app.JupyterNotebookApp(self, **kwargs: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `t.Any` | `—` | **kwargs |

### `NotebookBaseHandler`

The base notebook API handler.

```python
notebook.app.NotebookBaseHandler(self, application: 'Application', request: tornado.httputil.HTTPServerRequest, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `application` | `Application` | `—` | pos/kw |
| `request` | `HTTPServerRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `NotebookConfigShimMixin`

A Mixin class for shimming configuration from
NotebookApp to ServerApp. This class handles warnings, errors,
etc.

This class should be used during a transition period for apps
that are switching fro…

```python
notebook.app.NotebookConfigShimMixin(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NotebookHandler`

A notebook page handler.

```python
notebook.app.NotebookHandler(self, application: 'Application', request: tornado.httputil.HTTPServerRequest, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `application` | `Application` | `—` | pos/kw |
| `request` | `HTTPServerRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `TerminalHandler`

A terminal page handler.

```python
notebook.app.TerminalHandler(self, application: 'Application', request: tornado.httputil.HTTPServerRequest, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `application` | `Application` | `—` | pos/kw |
| `request` | `HTTPServerRequest` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

## Methods

### `notebook.app.ConsoleHandler` methods

### `add_header`

Adds the given response header and value.

Unlike `set_header`, `add_header` may be called multiple times
to return multiple values for the same header.

```python
notebook.app.ConsoleHandler.add_header(self, name: str, value: Union[bytes, str, int, numbers.Integral, datetime.datetime]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |

### `check_etag_header`

Checks the ``Etag`` header against requests's ``If-None-Match``.

Returns ``True`` if the request's Etag matches and a 304 should be
returned. For example::

    self.set_etag_header()
    if self.ch…

```python
notebook.app.ConsoleHandler.check_etag_header(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_host`

Check the host header if remote access disallowed.

Returns True if the request should continue, False otherwise.

```python
notebook.app.ConsoleHandler.check_host(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_origin`

Check Origin for cross-site API requests, including websockets

Copied from WebSocket with changes:

- allow unspecified host/origin (e.g. scripts)
- allow token-authenticated requests

```python
notebook.app.ConsoleHandler.check_origin(self, origin_to_satisfy_tornado: 'str' = '') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_to_satisfy_tornado` | `str` | `''` | pos/kw |

**Returns:** `bool`

### `check_referer`

Check Referer for cross-site requests.
Disables requests to certain endpoints with
external or missing Referer.
If set, allow_origin settings are applied to the Referer
to whitelist specific cross-or…

```python
notebook.app.ConsoleHandler.check_referer(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_xsrf_cookie`

Bypass xsrf cookie checks when token-authenticated

```python
notebook.app.ConsoleHandler.check_xsrf_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear`

Resets all headers and content for this response.

```python
notebook.app.ConsoleHandler.clear(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_all_cookies`

Attempt to delete all the cookies the user sent with this request.

See `clear_cookie` for more information on keyword arguments. Due to
limitations of the cookie protocol, it is impossible to determ…

```python
notebook.app.ConsoleHandler.clear_all_cookies(self, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_cookie`

Deletes the cookie with the given name.

This method accepts the same arguments as `set_cookie`, except for
``expires`` and ``max_age``. Clearing a cookie requires the same
``domain`` and ``path`` ar…

```python
notebook.app.ConsoleHandler.clear_cookie(self, name: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_header`

Clears an outgoing header, undoing a previous `set_header` call.

Note that this method does not apply to multi-valued headers
set by `add_header`.

```python
notebook.app.ConsoleHandler.clear_header(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `clear_login_cookie`

Clear a login cookie.

```python
notebook.app.ConsoleHandler.clear_login_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compute_etag`

Computes the etag header to be used for this request.

By default uses a hash of the content written so far.

May be overridden to provide custom etag implementations,
or may return None to disable t…

```python
notebook.app.ConsoleHandler.compute_etag(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `create_signed_value`

Signs and timestamps a string so it cannot be forged.

Normally used via set_signed_cookie, but provided as a separate
method for non-cookie uses.  To decode a value not stored
as a cookie use the op…

```python
notebook.app.ConsoleHandler.create_signed_value(self, name: str, value: Union[str, bytes], version: Optional[int] = None) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |
| `version` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'bytes'>`

### `create_template_loader`

Returns a new template loader for the given path.

May be overridden by subclasses.  By default returns a
directory-based loader on the given path, using the
``autoescape`` and ``template_whitespace`…

```python
notebook.app.ConsoleHandler.create_template_loader(self, template_path: str) -> tornado.template.BaseLoader
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template_path` | `str` | `—` | pos/kw |

**Returns:** `<class 'tornado.template.BaseLoader'>`

### `data_received`

Implement this method to handle streamed request data.

Requires the `.stream_request_body` decorator.

May be a coroutine for flow control.

```python
notebook.app.ConsoleHandler.data_received(self, chunk: bytes) -> Optional[Awaitable[NoneType]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `bytes` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Awaitable[NoneType]]`

### `decode_argument`

Decodes an argument from the request.

The argument has been percent-decoded and is now a byte string.
By default, this method decodes the argument as utf-8 and returns
a unicode string, but this may…

```python
notebook.app.ConsoleHandler.decode_argument(self, value: bytes, name: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `bytes` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `delete`

```python
notebook.app.ConsoleHandler.delete(self, *args: str, **kwargs: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `str` | `—` | *args |
| `kwargs` | `str` | `—` | **kwargs |

### `detach`

Take control of the underlying stream.

Returns the underlying `.IOStream` object and stops all
further HTTP processing. Intended for implementing protocols
like websockets that tunnel over an HTTP h…

```python
notebook.app.ConsoleHandler.detach(self) -> tornado.iostream.IOStream
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'tornado.iostream.IOStream'>`

### `finish`

Finishes this response, ending the HTTP request.

Passing a ``chunk`` to ``finish()`` is equivalent to passing that
chunk to ``write()`` and then calling ``finish()`` with no arguments.

Returns a `.…

```python
notebook.app.ConsoleHandler.finish(self, chunk: Union[str, bytes, dict, NoneType] = None) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `Union` | `None` | pos/kw |

**Returns:** `Future[None]`

### `flush`

Flushes the current output buffer to the network.

.. versionchanged:: 4.0
   Now returns a `.Future` if no callback is given.

.. versionchanged:: 6.0

   The ``callback`` argument was removed.

```python
notebook.app.ConsoleHandler.flush(self, include_footers: bool = False) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include_footers` | `bool` | `False` | pos/kw |

**Returns:** `Future[None]`

### `force_clear_cookie`

Force a cookie clear.

```python
notebook.app.ConsoleHandler.force_clear_cookie(self, name: 'str', path: 'str' = '/', domain: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `path` | `str` | `'/'` | pos/kw |
| `domain` | `str \| None` | `None` | pos/kw |

### `get`

Get the console page.

```python
notebook.app.ConsoleHandler.get(self, path: 'str | None' = None) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str \| None` | `None` | pos/kw |

**Returns:** `t.Any`

### `get_argument`

Returns the value of the argument with the given name.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is missing.

If the argument…

```python
notebook.app.ConsoleHandler.get_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_arguments`

Returns a list of the arguments with the given name.

If the argument is not present, returns an empty list.

This method searches both the query and body arguments.

```python
notebook.app.ConsoleHandler.get_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_body_argument`

Returns the value of the argument with the given name
from the request body.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is mis…

```python
notebook.app.ConsoleHandler.get_body_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_body_arguments`

Returns a list of the body arguments with the given name.

If the argument is not present, returns an empty list.

.. versionadded:: 3.2

```python
notebook.app.ConsoleHandler.get_body_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_browser_locale`

Determines the user's locale from ``Accept-Language`` header.

See http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4

```python
notebook.app.ConsoleHandler.get_browser_locale(self, default: str = 'en_US') -> tornado.locale.Locale
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `str` | `'en_US'` | pos/kw |

**Returns:** `<class 'tornado.locale.Locale'>`

### `get_cookie`

Returns the value of the request cookie with the given name.

If the named cookie is not present, returns ``default``.

This method only returns cookies that were present in the request.
It does not…

```python
notebook.app.ConsoleHandler.get_cookie(self, name: str, default: Optional[str] = None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_current_user`

Get the current user.

```python
notebook.app.ConsoleHandler.get_current_user(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_json_body`

Return the body of the request as JSON data.

```python
notebook.app.ConsoleHandler.get_json_body(self) -> 'dict[str, Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any] | None`

### `notebook.app.CustomCssHandler` methods

### `add_header`

Adds the given response header and value.

Unlike `set_header`, `add_header` may be called multiple times
to return multiple values for the same header.

```python
notebook.app.CustomCssHandler.add_header(self, name: str, value: Union[bytes, str, int, numbers.Integral, datetime.datetime]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |

### `check_etag_header`

Checks the ``Etag`` header against requests's ``If-None-Match``.

Returns ``True`` if the request's Etag matches and a 304 should be
returned. For example::

    self.set_etag_header()
    if self.ch…

```python
notebook.app.CustomCssHandler.check_etag_header(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_host`

Check the host header if remote access disallowed.

Returns True if the request should continue, False otherwise.

```python
notebook.app.CustomCssHandler.check_host(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_origin`

Check Origin for cross-site API requests, including websockets

Copied from WebSocket with changes:

- allow unspecified host/origin (e.g. scripts)
- allow token-authenticated requests

```python
notebook.app.CustomCssHandler.check_origin(self, origin_to_satisfy_tornado: 'str' = '') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_to_satisfy_tornado` | `str` | `''` | pos/kw |

**Returns:** `bool`

### `check_referer`

Check Referer for cross-site requests.
Disables requests to certain endpoints with
external or missing Referer.
If set, allow_origin settings are applied to the Referer
to whitelist specific cross-or…

```python
notebook.app.CustomCssHandler.check_referer(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_xsrf_cookie`

Bypass xsrf cookie checks when token-authenticated

```python
notebook.app.CustomCssHandler.check_xsrf_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear`

Resets all headers and content for this response.

```python
notebook.app.CustomCssHandler.clear(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_all_cookies`

Attempt to delete all the cookies the user sent with this request.

See `clear_cookie` for more information on keyword arguments. Due to
limitations of the cookie protocol, it is impossible to determ…

```python
notebook.app.CustomCssHandler.clear_all_cookies(self, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_cookie`

Deletes the cookie with the given name.

This method accepts the same arguments as `set_cookie`, except for
``expires`` and ``max_age``. Clearing a cookie requires the same
``domain`` and ``path`` ar…

```python
notebook.app.CustomCssHandler.clear_cookie(self, name: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_header`

Clears an outgoing header, undoing a previous `set_header` call.

Note that this method does not apply to multi-valued headers
set by `add_header`.

```python
notebook.app.CustomCssHandler.clear_header(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `clear_login_cookie`

Clear a login cookie.

```python
notebook.app.CustomCssHandler.clear_login_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compute_etag`

Computes the etag header to be used for this request.

By default uses a hash of the content written so far.

May be overridden to provide custom etag implementations,
or may return None to disable t…

```python
notebook.app.CustomCssHandler.compute_etag(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `create_signed_value`

Signs and timestamps a string so it cannot be forged.

Normally used via set_signed_cookie, but provided as a separate
method for non-cookie uses.  To decode a value not stored
as a cookie use the op…

```python
notebook.app.CustomCssHandler.create_signed_value(self, name: str, value: Union[str, bytes], version: Optional[int] = None) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |
| `version` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'bytes'>`

### `create_template_loader`

Returns a new template loader for the given path.

May be overridden by subclasses.  By default returns a
directory-based loader on the given path, using the
``autoescape`` and ``template_whitespace`…

```python
notebook.app.CustomCssHandler.create_template_loader(self, template_path: str) -> tornado.template.BaseLoader
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template_path` | `str` | `—` | pos/kw |

**Returns:** `<class 'tornado.template.BaseLoader'>`

### `data_received`

Implement this method to handle streamed request data.

Requires the `.stream_request_body` decorator.

May be a coroutine for flow control.

```python
notebook.app.CustomCssHandler.data_received(self, chunk: bytes) -> Optional[Awaitable[NoneType]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `bytes` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Awaitable[NoneType]]`

### `decode_argument`

Decodes an argument from the request.

The argument has been percent-decoded and is now a byte string.
By default, this method decodes the argument as utf-8 and returns
a unicode string, but this may…

```python
notebook.app.CustomCssHandler.decode_argument(self, value: bytes, name: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `bytes` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `delete`

```python
notebook.app.CustomCssHandler.delete(self, *args: str, **kwargs: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `str` | `—` | *args |
| `kwargs` | `str` | `—` | **kwargs |

### `detach`

Take control of the underlying stream.

Returns the underlying `.IOStream` object and stops all
further HTTP processing. Intended for implementing protocols
like websockets that tunnel over an HTTP h…

```python
notebook.app.CustomCssHandler.detach(self) -> tornado.iostream.IOStream
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'tornado.iostream.IOStream'>`

### `finish`

Finishes this response, ending the HTTP request.

Passing a ``chunk`` to ``finish()`` is equivalent to passing that
chunk to ``write()`` and then calling ``finish()`` with no arguments.

Returns a `.…

```python
notebook.app.CustomCssHandler.finish(self, chunk: Union[str, bytes, dict, NoneType] = None) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `Union` | `None` | pos/kw |

**Returns:** `Future[None]`

### `flush`

Flushes the current output buffer to the network.

.. versionchanged:: 4.0
   Now returns a `.Future` if no callback is given.

.. versionchanged:: 6.0

   The ``callback`` argument was removed.

```python
notebook.app.CustomCssHandler.flush(self, include_footers: bool = False) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include_footers` | `bool` | `False` | pos/kw |

**Returns:** `Future[None]`

### `force_clear_cookie`

Force a cookie clear.

```python
notebook.app.CustomCssHandler.force_clear_cookie(self, name: 'str', path: 'str' = '/', domain: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `path` | `str` | `'/'` | pos/kw |
| `domain` | `str \| None` | `None` | pos/kw |

### `get`

Get the custom css file.

```python
notebook.app.CustomCssHandler.get(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `get_argument`

Returns the value of the argument with the given name.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is missing.

If the argument…

```python
notebook.app.CustomCssHandler.get_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_arguments`

Returns a list of the arguments with the given name.

If the argument is not present, returns an empty list.

This method searches both the query and body arguments.

```python
notebook.app.CustomCssHandler.get_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_body_argument`

Returns the value of the argument with the given name
from the request body.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is mis…

```python
notebook.app.CustomCssHandler.get_body_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_body_arguments`

Returns a list of the body arguments with the given name.

If the argument is not present, returns an empty list.

.. versionadded:: 3.2

```python
notebook.app.CustomCssHandler.get_body_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_browser_locale`

Determines the user's locale from ``Accept-Language`` header.

See http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4

```python
notebook.app.CustomCssHandler.get_browser_locale(self, default: str = 'en_US') -> tornado.locale.Locale
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `str` | `'en_US'` | pos/kw |

**Returns:** `<class 'tornado.locale.Locale'>`

### `get_cookie`

Returns the value of the request cookie with the given name.

If the named cookie is not present, returns ``default``.

This method only returns cookies that were present in the request.
It does not…

```python
notebook.app.CustomCssHandler.get_cookie(self, name: str, default: Optional[str] = None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_current_user`

Get the current user.

```python
notebook.app.CustomCssHandler.get_current_user(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_json_body`

Return the body of the request as JSON data.

```python
notebook.app.CustomCssHandler.get_json_body(self) -> 'dict[str, Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any] | None`

### `notebook.app.FileHandler` methods

### `add_header`

Adds the given response header and value.

Unlike `set_header`, `add_header` may be called multiple times
to return multiple values for the same header.

```python
notebook.app.FileHandler.add_header(self, name: str, value: Union[bytes, str, int, numbers.Integral, datetime.datetime]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |

### `check_etag_header`

Checks the ``Etag`` header against requests's ``If-None-Match``.

Returns ``True`` if the request's Etag matches and a 304 should be
returned. For example::

    self.set_etag_header()
    if self.ch…

```python
notebook.app.FileHandler.check_etag_header(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_host`

Check the host header if remote access disallowed.

Returns True if the request should continue, False otherwise.

```python
notebook.app.FileHandler.check_host(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_origin`

Check Origin for cross-site API requests, including websockets

Copied from WebSocket with changes:

- allow unspecified host/origin (e.g. scripts)
- allow token-authenticated requests

```python
notebook.app.FileHandler.check_origin(self, origin_to_satisfy_tornado: 'str' = '') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_to_satisfy_tornado` | `str` | `''` | pos/kw |

**Returns:** `bool`

### `check_referer`

Check Referer for cross-site requests.
Disables requests to certain endpoints with
external or missing Referer.
If set, allow_origin settings are applied to the Referer
to whitelist specific cross-or…

```python
notebook.app.FileHandler.check_referer(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_xsrf_cookie`

Bypass xsrf cookie checks when token-authenticated

```python
notebook.app.FileHandler.check_xsrf_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear`

Resets all headers and content for this response.

```python
notebook.app.FileHandler.clear(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_all_cookies`

Attempt to delete all the cookies the user sent with this request.

See `clear_cookie` for more information on keyword arguments. Due to
limitations of the cookie protocol, it is impossible to determ…

```python
notebook.app.FileHandler.clear_all_cookies(self, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_cookie`

Deletes the cookie with the given name.

This method accepts the same arguments as `set_cookie`, except for
``expires`` and ``max_age``. Clearing a cookie requires the same
``domain`` and ``path`` ar…

```python
notebook.app.FileHandler.clear_cookie(self, name: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_header`

Clears an outgoing header, undoing a previous `set_header` call.

Note that this method does not apply to multi-valued headers
set by `add_header`.

```python
notebook.app.FileHandler.clear_header(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `clear_login_cookie`

Clear a login cookie.

```python
notebook.app.FileHandler.clear_login_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compute_etag`

Computes the etag header to be used for this request.

By default uses a hash of the content written so far.

May be overridden to provide custom etag implementations,
or may return None to disable t…

```python
notebook.app.FileHandler.compute_etag(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `create_signed_value`

Signs and timestamps a string so it cannot be forged.

Normally used via set_signed_cookie, but provided as a separate
method for non-cookie uses.  To decode a value not stored
as a cookie use the op…

```python
notebook.app.FileHandler.create_signed_value(self, name: str, value: Union[str, bytes], version: Optional[int] = None) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |
| `version` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'bytes'>`

### `create_template_loader`

Returns a new template loader for the given path.

May be overridden by subclasses.  By default returns a
directory-based loader on the given path, using the
``autoescape`` and ``template_whitespace`…

```python
notebook.app.FileHandler.create_template_loader(self, template_path: str) -> tornado.template.BaseLoader
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template_path` | `str` | `—` | pos/kw |

**Returns:** `<class 'tornado.template.BaseLoader'>`

### `data_received`

Implement this method to handle streamed request data.

Requires the `.stream_request_body` decorator.

May be a coroutine for flow control.

```python
notebook.app.FileHandler.data_received(self, chunk: bytes) -> Optional[Awaitable[NoneType]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `bytes` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Awaitable[NoneType]]`

### `decode_argument`

Decodes an argument from the request.

The argument has been percent-decoded and is now a byte string.
By default, this method decodes the argument as utf-8 and returns
a unicode string, but this may…

```python
notebook.app.FileHandler.decode_argument(self, value: bytes, name: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `bytes` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `delete`

```python
notebook.app.FileHandler.delete(self, *args: str, **kwargs: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `str` | `—` | *args |
| `kwargs` | `str` | `—` | **kwargs |

### `detach`

Take control of the underlying stream.

Returns the underlying `.IOStream` object and stops all
further HTTP processing. Intended for implementing protocols
like websockets that tunnel over an HTTP h…

```python
notebook.app.FileHandler.detach(self) -> tornado.iostream.IOStream
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'tornado.iostream.IOStream'>`

### `finish`

Finishes this response, ending the HTTP request.

Passing a ``chunk`` to ``finish()`` is equivalent to passing that
chunk to ``write()`` and then calling ``finish()`` with no arguments.

Returns a `.…

```python
notebook.app.FileHandler.finish(self, chunk: Union[str, bytes, dict, NoneType] = None) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `Union` | `None` | pos/kw |

**Returns:** `Future[None]`

### `flush`

Flushes the current output buffer to the network.

.. versionchanged:: 4.0
   Now returns a `.Future` if no callback is given.

.. versionchanged:: 6.0

   The ``callback`` argument was removed.

```python
notebook.app.FileHandler.flush(self, include_footers: bool = False) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include_footers` | `bool` | `False` | pos/kw |

**Returns:** `Future[None]`

### `force_clear_cookie`

Force a cookie clear.

```python
notebook.app.FileHandler.force_clear_cookie(self, name: 'str', path: 'str' = '/', domain: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `path` | `str` | `'/'` | pos/kw |
| `domain` | `str \| None` | `None` | pos/kw |

### `get`

Get the file page.

```python
notebook.app.FileHandler.get(self, path: 'str | None' = None) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str \| None` | `None` | pos/kw |

**Returns:** `t.Any`

### `get_argument`

Returns the value of the argument with the given name.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is missing.

If the argument…

```python
notebook.app.FileHandler.get_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_arguments`

Returns a list of the arguments with the given name.

If the argument is not present, returns an empty list.

This method searches both the query and body arguments.

```python
notebook.app.FileHandler.get_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_body_argument`

Returns the value of the argument with the given name
from the request body.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is mis…

```python
notebook.app.FileHandler.get_body_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_body_arguments`

Returns a list of the body arguments with the given name.

If the argument is not present, returns an empty list.

.. versionadded:: 3.2

```python
notebook.app.FileHandler.get_body_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_browser_locale`

Determines the user's locale from ``Accept-Language`` header.

See http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4

```python
notebook.app.FileHandler.get_browser_locale(self, default: str = 'en_US') -> tornado.locale.Locale
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `str` | `'en_US'` | pos/kw |

**Returns:** `<class 'tornado.locale.Locale'>`

### `get_cookie`

Returns the value of the request cookie with the given name.

If the named cookie is not present, returns ``default``.

This method only returns cookies that were present in the request.
It does not…

```python
notebook.app.FileHandler.get_cookie(self, name: str, default: Optional[str] = None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_current_user`

Get the current user.

```python
notebook.app.FileHandler.get_current_user(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_json_body`

Return the body of the request as JSON data.

```python
notebook.app.FileHandler.get_json_body(self) -> 'dict[str, Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any] | None`

### `notebook.app.JupyterNotebookApp` methods

### `add_traits`

Dynamically add trait attributes to the HasTraits instance.

```python
notebook.app.JupyterNotebookApp.add_traits(self, **traits: 't.Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `traits` | `t.Any` | `—` | **kwargs |

### `class_config_rst_doc`

Generate rST documentation for this class' config options.

Excludes traits defined on parent classes.

```python
notebook.app.JupyterNotebookApp.class_config_rst_doc() -> 'str'
```

**Returns:** `str`

### `class_config_section`

Get the config section for this class.

Parameters
----------
classes : list, optional
    The list of other classes in the config file.
    Used to reduce redundant information.

```python
notebook.app.JupyterNotebookApp.class_config_section(classes: 't.Sequence[type[HasTraits]] | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `classes` | `t.Sequence[type[HasTraits]] \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_help`

Get the help string for this class in ReST format.

If `inst` is given, its current trait values will be used in place of
class defaults.

```python
notebook.app.JupyterNotebookApp.class_get_help(inst: 'HasTraits | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_get_trait_help`

Get the helptext string for a single trait.

:param inst:
    If given, its current trait values will be used in place of
    the class default.
:param helptext:
    If not given, uses the `help` att…

```python
notebook.app.JupyterNotebookApp.class_get_trait_help(trait: 'TraitType[t.Any, t.Any]', inst: 'HasTraits | None' = None, helptext: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `trait` | `TraitType[t.Any, t.Any]` | `—` | pos/kw |
| `inst` | `HasTraits \| None` | `None` | pos/kw |
| `helptext` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `class_own_trait_events`

Get a dict of all event handlers defined on this class, not a parent.

Works like ``event_handlers``, except for excluding traits from parents.

```python
notebook.app.JupyterNotebookApp.class_own_trait_events(name: 'str') -> 'dict[str, EventHandler]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |

**Returns:** `dict[str, EventHandler]`

### `class_own_traits`

Get a dict of all the traitlets defined on this class, not a parent.

Works like `class_traits`, except for excluding traits from parents.

```python
notebook.app.JupyterNotebookApp.class_own_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `class_print_help`

Get the help string for a single trait and print it.

```python
notebook.app.JupyterNotebookApp.class_print_help(inst: 'HasTraits | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `inst` | `HasTraits \| None` | `None` | pos/kw |

### `class_trait_names`

Get a list of all the names of this class' traits.

This method is just like the :meth:`trait_names` method,
but is unbound.

```python
notebook.app.JupyterNotebookApp.class_trait_names(**metadata: 't.Any') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `list[str]`

### `class_traits`

Get a ``dict`` of all the traits of this class.  The dictionary
is keyed on the name and the values are the TraitType objects.

This method is just like the :meth:`traits` method, but is unbound.

Th…

```python
notebook.app.JupyterNotebookApp.class_traits(**metadata: 't.Any') -> 'dict[str, TraitType[t.Any, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `metadata` | `t.Any` | `—` | **kwargs |

**Returns:** `dict[str, TraitType[t.Any, t.Any]]`

### `clear_instance`

unset _instance for this class and singleton parents.

```python
notebook.app.JupyterNotebookApp.clear_instance() -> 'None'
```

### `close_handlers`

```python
notebook.app.JupyterNotebookApp.close_handlers(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `current_activity`

Return a list of activity happening in this extension.

```python
notebook.app.JupyterNotebookApp.current_activity(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `document_config_options`

Generate rST format documentation for the config options this application

Returns a multiline string.

```python
notebook.app.JupyterNotebookApp.document_config_options(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `emit_alias_help`

Yield the lines for alias part of the help.

```python
notebook.app.JupyterNotebookApp.emit_alias_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_description`

Yield lines with the application description.

```python
notebook.app.JupyterNotebookApp.emit_description(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_examples`

Yield lines with the usage and examples.

This usage string goes at the end of the command line help string
and should contain examples of the application's usage.

```python
notebook.app.JupyterNotebookApp.emit_examples(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_flag_help`

Yield the lines for the flag part of the help.

```python
notebook.app.JupyterNotebookApp.emit_flag_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_help`

Yield the help-lines for each Configurable class in self.classes.

If classes=False (the default), only flags and aliases are printed.

```python
notebook.app.JupyterNotebookApp.emit_help(self, classes: 'bool' = False) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `bool` | `False` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_help_epilogue`

Yield the very bottom lines of the help message.

If classes=False (the default), print `--help-all` msg.

```python
notebook.app.JupyterNotebookApp.emit_help_epilogue(self, classes: 'bool') -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `bool` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_options_help`

Yield the lines for the options part of the help.

```python
notebook.app.JupyterNotebookApp.emit_options_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `emit_subcommands_help`

Yield the lines for the subcommand part of the help.

```python
notebook.app.JupyterNotebookApp.emit_subcommands_help(self) -> 't.Generator[str, None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Generator[str, None, None]`

### `exit`

```python
notebook.app.JupyterNotebookApp.exit(self, exit_status: 'int | str | None' = 0) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `exit_status` | `int \| str \| None` | `0` | pos/kw |

### `flatten_flags`

Flatten flags and aliases for loaders, so cl-args override as expected.

This prevents issues such as an alias pointing to InteractiveShell,
but a config file setting the same trait in TerminalIntera…

```python
notebook.app.JupyterNotebookApp.flatten_flags(self) -> 'tuple[dict[str, t.Any], dict[str, t.Any]]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `tuple[dict[str, t.Any], dict[str, t.Any]]`

### `generate_config_file`

generate default config file from Configurables

```python
notebook.app.JupyterNotebookApp.generate_config_file(self, classes: 'ClassesType | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `classes` | `ClassesType \| None` | `None` | pos/kw |

**Returns:** `str`

### `get_default_logging_config`

Return the base logging configuration.

The default is to log to stderr using a StreamHandler, if no default
handler already exists.

The log handler level starts at logging.WARN, but this can be adj…

```python
notebook.app.JupyterNotebookApp.get_default_logging_config(self) -> 'StrDict'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `StrDict`

### `get_extension_package`

Get an extension package.

```python
notebook.app.JupyterNotebookApp.get_extension_package()
```

### `get_extension_point`

Get an extension point.

```python
notebook.app.JupyterNotebookApp.get_extension_point()
```

### `has_trait`

Returns True if the object has a trait with the specified name.

```python
notebook.app.JupyterNotebookApp.has_trait(self, name: 'str') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

**Returns:** `bool`

### `hold_trait_notifications`

Context manager for bundling trait change notifications and cross
validation.

Use this when doing multiple trait assignments (init, config), to avoid
race conditions in trait notifiers requesting ot…

```python
notebook.app.JupyterNotebookApp.hold_trait_notifications(self) -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `t.Any`

### `notebook.app.NotebookBaseHandler` methods

### `add_header`

Adds the given response header and value.

Unlike `set_header`, `add_header` may be called multiple times
to return multiple values for the same header.

```python
notebook.app.NotebookBaseHandler.add_header(self, name: str, value: Union[bytes, str, int, numbers.Integral, datetime.datetime]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |

### `check_etag_header`

Checks the ``Etag`` header against requests's ``If-None-Match``.

Returns ``True`` if the request's Etag matches and a 304 should be
returned. For example::

    self.set_etag_header()
    if self.ch…

```python
notebook.app.NotebookBaseHandler.check_etag_header(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_host`

Check the host header if remote access disallowed.

Returns True if the request should continue, False otherwise.

```python
notebook.app.NotebookBaseHandler.check_host(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_origin`

Check Origin for cross-site API requests, including websockets

Copied from WebSocket with changes:

- allow unspecified host/origin (e.g. scripts)
- allow token-authenticated requests

```python
notebook.app.NotebookBaseHandler.check_origin(self, origin_to_satisfy_tornado: 'str' = '') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_to_satisfy_tornado` | `str` | `''` | pos/kw |

**Returns:** `bool`

### `check_referer`

Check Referer for cross-site requests.
Disables requests to certain endpoints with
external or missing Referer.
If set, allow_origin settings are applied to the Referer
to whitelist specific cross-or…

```python
notebook.app.NotebookBaseHandler.check_referer(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_xsrf_cookie`

Bypass xsrf cookie checks when token-authenticated

```python
notebook.app.NotebookBaseHandler.check_xsrf_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear`

Resets all headers and content for this response.

```python
notebook.app.NotebookBaseHandler.clear(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_all_cookies`

Attempt to delete all the cookies the user sent with this request.

See `clear_cookie` for more information on keyword arguments. Due to
limitations of the cookie protocol, it is impossible to determ…

```python
notebook.app.NotebookBaseHandler.clear_all_cookies(self, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_cookie`

Deletes the cookie with the given name.

This method accepts the same arguments as `set_cookie`, except for
``expires`` and ``max_age``. Clearing a cookie requires the same
``domain`` and ``path`` ar…

```python
notebook.app.NotebookBaseHandler.clear_cookie(self, name: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_header`

Clears an outgoing header, undoing a previous `set_header` call.

Note that this method does not apply to multi-valued headers
set by `add_header`.

```python
notebook.app.NotebookBaseHandler.clear_header(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `clear_login_cookie`

Clear a login cookie.

```python
notebook.app.NotebookBaseHandler.clear_login_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compute_etag`

Computes the etag header to be used for this request.

By default uses a hash of the content written so far.

May be overridden to provide custom etag implementations,
or may return None to disable t…

```python
notebook.app.NotebookBaseHandler.compute_etag(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `create_signed_value`

Signs and timestamps a string so it cannot be forged.

Normally used via set_signed_cookie, but provided as a separate
method for non-cookie uses.  To decode a value not stored
as a cookie use the op…

```python
notebook.app.NotebookBaseHandler.create_signed_value(self, name: str, value: Union[str, bytes], version: Optional[int] = None) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |
| `version` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'bytes'>`

### `create_template_loader`

Returns a new template loader for the given path.

May be overridden by subclasses.  By default returns a
directory-based loader on the given path, using the
``autoescape`` and ``template_whitespace`…

```python
notebook.app.NotebookBaseHandler.create_template_loader(self, template_path: str) -> tornado.template.BaseLoader
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template_path` | `str` | `—` | pos/kw |

**Returns:** `<class 'tornado.template.BaseLoader'>`

### `data_received`

Implement this method to handle streamed request data.

Requires the `.stream_request_body` decorator.

May be a coroutine for flow control.

```python
notebook.app.NotebookBaseHandler.data_received(self, chunk: bytes) -> Optional[Awaitable[NoneType]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `bytes` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Awaitable[NoneType]]`

### `decode_argument`

Decodes an argument from the request.

The argument has been percent-decoded and is now a byte string.
By default, this method decodes the argument as utf-8 and returns
a unicode string, but this may…

```python
notebook.app.NotebookBaseHandler.decode_argument(self, value: bytes, name: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `bytes` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `delete`

```python
notebook.app.NotebookBaseHandler.delete(self, *args: str, **kwargs: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `str` | `—` | *args |
| `kwargs` | `str` | `—` | **kwargs |

### `detach`

Take control of the underlying stream.

Returns the underlying `.IOStream` object and stops all
further HTTP processing. Intended for implementing protocols
like websockets that tunnel over an HTTP h…

```python
notebook.app.NotebookBaseHandler.detach(self) -> tornado.iostream.IOStream
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'tornado.iostream.IOStream'>`

### `finish`

Finishes this response, ending the HTTP request.

Passing a ``chunk`` to ``finish()`` is equivalent to passing that
chunk to ``write()`` and then calling ``finish()`` with no arguments.

Returns a `.…

```python
notebook.app.NotebookBaseHandler.finish(self, chunk: Union[str, bytes, dict, NoneType] = None) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `Union` | `None` | pos/kw |

**Returns:** `Future[None]`

### `flush`

Flushes the current output buffer to the network.

.. versionchanged:: 4.0
   Now returns a `.Future` if no callback is given.

.. versionchanged:: 6.0

   The ``callback`` argument was removed.

```python
notebook.app.NotebookBaseHandler.flush(self, include_footers: bool = False) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include_footers` | `bool` | `False` | pos/kw |

**Returns:** `Future[None]`

### `force_clear_cookie`

Force a cookie clear.

```python
notebook.app.NotebookBaseHandler.force_clear_cookie(self, name: 'str', path: 'str' = '/', domain: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `path` | `str` | `'/'` | pos/kw |
| `domain` | `str \| None` | `None` | pos/kw |

### `get`

```python
notebook.app.NotebookBaseHandler.get(self, *args: str, **kwargs: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `str` | `—` | *args |
| `kwargs` | `str` | `—` | **kwargs |

### `get_argument`

Returns the value of the argument with the given name.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is missing.

If the argument…

```python
notebook.app.NotebookBaseHandler.get_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_arguments`

Returns a list of the arguments with the given name.

If the argument is not present, returns an empty list.

This method searches both the query and body arguments.

```python
notebook.app.NotebookBaseHandler.get_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_body_argument`

Returns the value of the argument with the given name
from the request body.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is mis…

```python
notebook.app.NotebookBaseHandler.get_body_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_body_arguments`

Returns a list of the body arguments with the given name.

If the argument is not present, returns an empty list.

.. versionadded:: 3.2

```python
notebook.app.NotebookBaseHandler.get_body_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_browser_locale`

Determines the user's locale from ``Accept-Language`` header.

See http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4

```python
notebook.app.NotebookBaseHandler.get_browser_locale(self, default: str = 'en_US') -> tornado.locale.Locale
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `str` | `'en_US'` | pos/kw |

**Returns:** `<class 'tornado.locale.Locale'>`

### `get_cookie`

Returns the value of the request cookie with the given name.

If the named cookie is not present, returns ``default``.

This method only returns cookies that were present in the request.
It does not…

```python
notebook.app.NotebookBaseHandler.get_cookie(self, name: str, default: Optional[str] = None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_current_user`

Get the current user.

```python
notebook.app.NotebookBaseHandler.get_current_user(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_json_body`

Return the body of the request as JSON data.

```python
notebook.app.NotebookBaseHandler.get_json_body(self) -> 'dict[str, Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any] | None`

### `notebook.app.NotebookConfigShimMixin` methods

### `shim_config_from_notebook_to_jupyter_server`

Reorganizes a config object to reroute traits to their expected destinations
after the transition from NotebookApp to ServerApp.

A detailed explanation of how traits are handled:

1. If the argument…

```python
notebook.app.NotebookConfigShimMixin.shim_config_from_notebook_to_jupyter_server(self, config)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `—` | `—` | pos/kw |

### `update_config`

Update config and load the new values

```python
notebook.app.NotebookConfigShimMixin.update_config(self, config: 'Config') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `config` | `Config` | `—` | pos/kw |

### `notebook.app.NotebookHandler` methods

### `add_header`

Adds the given response header and value.

Unlike `set_header`, `add_header` may be called multiple times
to return multiple values for the same header.

```python
notebook.app.NotebookHandler.add_header(self, name: str, value: Union[bytes, str, int, numbers.Integral, datetime.datetime]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |

### `check_etag_header`

Checks the ``Etag`` header against requests's ``If-None-Match``.

Returns ``True`` if the request's Etag matches and a 304 should be
returned. For example::

    self.set_etag_header()
    if self.ch…

```python
notebook.app.NotebookHandler.check_etag_header(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_host`

Check the host header if remote access disallowed.

Returns True if the request should continue, False otherwise.

```python
notebook.app.NotebookHandler.check_host(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_origin`

Check Origin for cross-site API requests, including websockets

Copied from WebSocket with changes:

- allow unspecified host/origin (e.g. scripts)
- allow token-authenticated requests

```python
notebook.app.NotebookHandler.check_origin(self, origin_to_satisfy_tornado: 'str' = '') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_to_satisfy_tornado` | `str` | `''` | pos/kw |

**Returns:** `bool`

### `check_referer`

Check Referer for cross-site requests.
Disables requests to certain endpoints with
external or missing Referer.
If set, allow_origin settings are applied to the Referer
to whitelist specific cross-or…

```python
notebook.app.NotebookHandler.check_referer(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_xsrf_cookie`

Bypass xsrf cookie checks when token-authenticated

```python
notebook.app.NotebookHandler.check_xsrf_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear`

Resets all headers and content for this response.

```python
notebook.app.NotebookHandler.clear(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_all_cookies`

Attempt to delete all the cookies the user sent with this request.

See `clear_cookie` for more information on keyword arguments. Due to
limitations of the cookie protocol, it is impossible to determ…

```python
notebook.app.NotebookHandler.clear_all_cookies(self, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_cookie`

Deletes the cookie with the given name.

This method accepts the same arguments as `set_cookie`, except for
``expires`` and ``max_age``. Clearing a cookie requires the same
``domain`` and ``path`` ar…

```python
notebook.app.NotebookHandler.clear_cookie(self, name: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_header`

Clears an outgoing header, undoing a previous `set_header` call.

Note that this method does not apply to multi-valued headers
set by `add_header`.

```python
notebook.app.NotebookHandler.clear_header(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |

### `clear_login_cookie`

Clear a login cookie.

```python
notebook.app.NotebookHandler.clear_login_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `compute_etag`

Computes the etag header to be used for this request.

By default uses a hash of the content written so far.

May be overridden to provide custom etag implementations,
or may return None to disable t…

```python
notebook.app.NotebookHandler.compute_etag(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `create_signed_value`

Signs and timestamps a string so it cannot be forged.

Normally used via set_signed_cookie, but provided as a separate
method for non-cookie uses.  To decode a value not stored
as a cookie use the op…

```python
notebook.app.NotebookHandler.create_signed_value(self, name: str, value: Union[str, bytes], version: Optional[int] = None) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |
| `version` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'bytes'>`

### `create_template_loader`

Returns a new template loader for the given path.

May be overridden by subclasses.  By default returns a
directory-based loader on the given path, using the
``autoescape`` and ``template_whitespace`…

```python
notebook.app.NotebookHandler.create_template_loader(self, template_path: str) -> tornado.template.BaseLoader
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `template_path` | `str` | `—` | pos/kw |

**Returns:** `<class 'tornado.template.BaseLoader'>`

### `data_received`

Implement this method to handle streamed request data.

Requires the `.stream_request_body` decorator.

May be a coroutine for flow control.

```python
notebook.app.NotebookHandler.data_received(self, chunk: bytes) -> Optional[Awaitable[NoneType]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `bytes` | `—` | pos/kw |

**Returns:** `typing.Optional[typing.Awaitable[NoneType]]`

### `decode_argument`

Decodes an argument from the request.

The argument has been percent-decoded and is now a byte string.
By default, this method decodes the argument as utf-8 and returns
a unicode string, but this may…

```python
notebook.app.NotebookHandler.decode_argument(self, value: bytes, name: Optional[str] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `value` | `bytes` | `—` | pos/kw |
| `name` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `delete`

```python
notebook.app.NotebookHandler.delete(self, *args: str, **kwargs: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `args` | `str` | `—` | *args |
| `kwargs` | `str` | `—` | **kwargs |

### `detach`

Take control of the underlying stream.

Returns the underlying `.IOStream` object and stops all
further HTTP processing. Intended for implementing protocols
like websockets that tunnel over an HTTP h…

```python
notebook.app.NotebookHandler.detach(self) -> tornado.iostream.IOStream
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'tornado.iostream.IOStream'>`

### `finish`

Finishes this response, ending the HTTP request.

Passing a ``chunk`` to ``finish()`` is equivalent to passing that
chunk to ``write()`` and then calling ``finish()`` with no arguments.

Returns a `.…

```python
notebook.app.NotebookHandler.finish(self, chunk: Union[str, bytes, dict, NoneType] = None) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `chunk` | `Union` | `None` | pos/kw |

**Returns:** `Future[None]`

### `flush`

Flushes the current output buffer to the network.

.. versionchanged:: 4.0
   Now returns a `.Future` if no callback is given.

.. versionchanged:: 6.0

   The ``callback`` argument was removed.

```python
notebook.app.NotebookHandler.flush(self, include_footers: bool = False) -> 'Future[None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `include_footers` | `bool` | `False` | pos/kw |

**Returns:** `Future[None]`

### `force_clear_cookie`

Force a cookie clear.

```python
notebook.app.NotebookHandler.force_clear_cookie(self, name: 'str', path: 'str' = '/', domain: 'str | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `path` | `str` | `'/'` | pos/kw |
| `domain` | `str \| None` | `None` | pos/kw |

### `get`

Get the notebook page. Redirect if it's a directory.

```python
notebook.app.NotebookHandler.get(self, path: 'str' = '') -> 't.Any'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `str` | `''` | pos/kw |

**Returns:** `t.Any`

### `get_argument`

Returns the value of the argument with the given name.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is missing.

If the argument…

```python
notebook.app.NotebookHandler.get_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_arguments`

Returns a list of the arguments with the given name.

If the argument is not present, returns an empty list.

This method searches both the query and body arguments.

```python
notebook.app.NotebookHandler.get_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_body_argument`

Returns the value of the argument with the given name
from the request body.

If default is not provided, the argument is considered to be
required, and we raise a `MissingArgumentError` if it is mis…

```python
notebook.app.NotebookHandler.get_body_argument(self, name: str, default: Union[NoneType, str, tornado.web._ArgDefaultMarker] = <tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>, strip: bool = True) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Union` | `<tornado.web._ArgDefaultMarker object at 0x7aa0e0b541a0>` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_body_arguments`

Returns a list of the body arguments with the given name.

If the argument is not present, returns an empty list.

.. versionadded:: 3.2

```python
notebook.app.NotebookHandler.get_body_arguments(self, name: str, strip: bool = True) -> List[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `strip` | `bool` | `True` | pos/kw |

**Returns:** `typing.List[str]`

### `get_browser_locale`

Determines the user's locale from ``Accept-Language`` header.

See http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.4

```python
notebook.app.NotebookHandler.get_browser_locale(self, default: str = 'en_US') -> tornado.locale.Locale
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `default` | `str` | `'en_US'` | pos/kw |

**Returns:** `<class 'tornado.locale.Locale'>`

### `get_cookie`

Returns the value of the request cookie with the given name.

If the named cookie is not present, returns ``default``.

This method only returns cookies that were present in the request.
It does not…

```python
notebook.app.NotebookHandler.get_cookie(self, name: str, default: Optional[str] = None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `default` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_current_user`

Get the current user.

```python
notebook.app.NotebookHandler.get_current_user(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `get_json_body`

Return the body of the request as JSON data.

```python
notebook.app.NotebookHandler.get_json_body(self) -> 'dict[str, Any] | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `dict[str, Any] | None`

### `notebook.app.TerminalHandler` methods

### `add_header`

Adds the given response header and value.

Unlike `set_header`, `add_header` may be called multiple times
to return multiple values for the same header.

```python
notebook.app.TerminalHandler.add_header(self, name: str, value: Union[bytes, str, int, numbers.Integral, datetime.datetime]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `value` | `Union` | `—` | pos/kw |

### `check_etag_header`

Checks the ``Etag`` header against requests's ``If-None-Match``.

Returns ``True`` if the request's Etag matches and a 304 should be
returned. For example::

    self.set_etag_header()
    if self.ch…

```python
notebook.app.TerminalHandler.check_etag_header(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `check_host`

Check the host header if remote access disallowed.

Returns True if the request should continue, False otherwise.

```python
notebook.app.TerminalHandler.check_host(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_origin`

Check Origin for cross-site API requests, including websockets

Copied from WebSocket with changes:

- allow unspecified host/origin (e.g. scripts)
- allow token-authenticated requests

```python
notebook.app.TerminalHandler.check_origin(self, origin_to_satisfy_tornado: 'str' = '') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `origin_to_satisfy_tornado` | `str` | `''` | pos/kw |

**Returns:** `bool`

### `check_referer`

Check Referer for cross-site requests.
Disables requests to certain endpoints with
external or missing Referer.
If set, allow_origin settings are applied to the Referer
to whitelist specific cross-or…

```python
notebook.app.TerminalHandler.check_referer(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `check_xsrf_cookie`

Bypass xsrf cookie checks when token-authenticated

```python
notebook.app.TerminalHandler.check_xsrf_cookie(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear`

Resets all headers and content for this response.

```python
notebook.app.TerminalHandler.clear(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `clear_all_cookies`

Attempt to delete all the cookies the user sent with this request.

See `clear_cookie` for more information on keyword arguments. Due to
limitations of the cookie protocol, it is impossible to determ…

```python
notebook.app.TerminalHandler.clear_all_cookies(self, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_cookie`

Deletes the cookie with the given name.

This method accepts the same arguments as `set_cookie`, except for
``expires`` and ``max_age``. Clearing a cookie requires the same
``domain`` and ``path`` ar…

```python
notebook.app.TerminalHandler.clear_cookie(self, name: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `clear_header`

Clears an outgoing header, undoing a previous `set_header` call.

Note that this method does not apply to multi-valued headers
set by `add_header`.

```python
notebook.app.TerminalHandler.clear_header(self, name: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `str` | `—` | pos/kw |


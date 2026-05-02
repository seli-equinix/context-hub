---
name: package
description: "Twine package guide for building, checking, and uploading Python distributions to PyPI and TestPyPI"
metadata:
  languages: "python"
  versions: "6.2.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "twine,python,pypi,packaging,publishing,repository,release,ini,Version-Sensitive,CredentialInput,Private,choose,get_password_from_keyring,get_username_from_keyring,is_pypi,make_trusted_publishing_token,password_from_keyring_or_trusted_publishing_or_prompt,prompt,username_from_keyring_or_prompt,Resolver,TrustedPublishingAuthenticator,TrustedPublishingToken,TrustedPublishingTokenRetrievalError,configure_output,dep_versions,dispatch,list_dependencies_and_versions,Inputs,check,main,register,skip_upload,upload,Distribution,read,InvalidConfiguration,InvalidDistribution,InvalidPyPIUploadURL,InvalidSigningConfiguration,InvalidSigningExecutable,NonInteractive,PackageNotFound,RedirectDetected,from_args,TrustedPublishingFailure,TwineException,UnreachableRepositoryURLDetected,UnsupportedConfiguration,UploadToDeprecatedPyPIDetected,HashManager,hash,hexdigest,Hexdigest,PackageFile,add_attestations,add_gpg_signature,from_filename,metadata_dictionary,run_gpg,sign,PackageMetadata,Repository,close,package_is_uploaded,release_urls,set_certificate_authority,set_client_certificate,verify_package_integrity,make_requests_session,SDist,TarGzSDist,ZipSDist,Settings,check_repository_url,create_repository,from_argparse,register_argparse_arguments,verify_feature_capability,EnvironmentDefault,format_usage,EnvironmentFlag,bool_from_env,check_status_code,get_config,get_file_size,get_repository_from_config,get_userpass_value,normalize_repository_url,sanitize_url,Wheel,find_candidate_metadata_files"
---

# twine — package

Top-level module for Twine.

The contents of this package are not a public API. For more details, see
https://github.com/pypa/twine/issues/194 and https://github.com/pypa/twine/issues/665.

## Install

```bash
pip install twine
```

## Imports

```python
import twine
```

## Symbols (101)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `CredentialInput` | Class |  |
| `Private` | Class |  |
| `choose` | Method |  |
| `get_password_from_keyring` | Method |  |
| `get_username_from_keyring` | Method |  |
| `is_pypi` | Method | As of 2024-01-01, PyPI requires API tokens for uploads. |
| `make_trusted_publishing_token` | Method |  |
| `password_from_keyring_or_trusted_publishing_or_prompt` | Method |  |
| `prompt` | Method |  |
| `username_from_keyring_or_prompt` | Method |  |
| `Resolver` | Class |  |
| `choose` | Method |  |
| `get_password_from_keyring` | Method |  |
| `get_username_from_keyring` | Method |  |
| `is_pypi` | Method | As of 2024-01-01, PyPI requires API tokens for uploads. |
| `make_trusted_publishing_token` | Method |  |
| `password_from_keyring_or_trusted_publishing_or_prompt` | Method |  |
| `prompt` | Method |  |
| `username_from_keyring_or_prompt` | Method |  |
| `TrustedPublishingAuthenticator` | Class | Base class that all auth implementations derive from |
| `TrustedPublishingToken` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `TrustedPublishingTokenRetrievalError` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `configure_output` | Function |  |
| `dep_versions` | Function |  |
| `dispatch` | Function |  |
| `list_dependencies_and_versions` | Function |  |
| `Inputs` | Class | Represents structured user inputs. |
| `check` | Function | Check that a distribution will render correctly on PyPI and display the results… |
| `main` | Function | Execute the ``check`` command.  :param args:     The command-line arguments.  :… |
| `main` | Function | Execute the ``register`` command.  :param args:     The command-line arguments. |
| `register` | Function | Pre-register a package name with a repository before uploading a distribution.… |
| `main` | Function | Execute the ``upload`` command.  :param args:     The command-line arguments. |
| `skip_upload` | Function | Determine if a failed upload is an error or can be safely ignored.  :param resp… |
| `upload` | Function | Upload one or more distributions to a repository, and display the progress.  If… |
| `Distribution` | Class |  |
| `read` | Method |  |
| `InvalidConfiguration` | Class | Raised when configuration is invalid. |
| `InvalidDistribution` | Class | Raised when a distribution is invalid. |
| `InvalidPyPIUploadURL` | Class | Repository configuration tries to use PyPI with an incorrect URL.  For example,… |
| `InvalidSigningConfiguration` | Class | Both the sign and identity parameters must be present. |
| `InvalidSigningExecutable` | Class | Signing executable must be installed on system. |
| `NonInteractive` | Class | Raised in non-interactive mode when credentials could not be found. |
| `PackageNotFound` | Class | A package file was provided that could not be found on the file system.  This i… |
| `RedirectDetected` | Class | A redirect was detected that the user needs to resolve.  In some cases, request… |
| `from_args` | Method |  |
| `TrustedPublishingFailure` | Class | Raised if we expected to use trusted publishing but couldn't. |
| `TwineException` | Class | Base class for all exceptions raised by twine. |
| `UnreachableRepositoryURLDetected` | Class | An upload attempt was detected to a URL without a protocol prefix.  All reposit… |
| `UnsupportedConfiguration` | Class | An upload attempt was detected using features not supported by a repository.  T… |
| `UploadToDeprecatedPyPIDetected` | Class | An upload attempt was detected to deprecated PyPI domains.  The sites pypi.pyth… |
| `from_args` | Method | Return an UploadToDeprecatedPyPIDetected instance. |
| `HashManager` | Class | Manage our hashing objects for simplicity.  This will also allow us to better t… |
| `hash` | Method | Hash the file contents. |
| `hexdigest` | Method | Return the hexdigest for the file. |
| `Hexdigest` | Class | Hexdigest(sha2, blake2) |
| `PackageFile` | Class |  |
| `add_attestations` | Method |  |
| `add_gpg_signature` | Method |  |
| `from_filename` | Method |  |
| `metadata_dictionary` | Method | Merge multiple sources of metadata into a single dictionary.  Includes values f… |
| `run_gpg` | Method |  |
| `sign` | Method |  |
| `PackageMetadata` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `Repository` | Class |  |
| `close` | Method |  |
| `package_is_uploaded` | Method | Determine if a package has been uploaded to PyPI already.  .. warning:: This do… |
| `register` | Method |  |
| `release_urls` | Method |  |
| `set_certificate_authority` | Method |  |
| `set_client_certificate` | Method |  |
| `upload` | Method |  |
| `verify_package_integrity` | Method |  |
| `make_requests_session` | Function | Prepare a requests Session with retries & twine's user-agent string. |
| `SDist` | Class |  |
| `read` | Method |  |
| `TarGzSDist` | Class |  |
| `read` | Method |  |
| `ZipSDist` | Class |  |
| `read` | Method |  |
| `Settings` | Class | Object that manages the configuration for Twine.  This object can only be insta… |
| `check_repository_url` | Method | Verify we are not using legacy PyPI.  :raises twine.exceptions.UploadToDeprecat… |
| `create_repository` | Method | Create a new repository for uploading. |
| `from_argparse` | Method | Generate the Settings from parsed arguments. |
| `register_argparse_arguments` | Method | Register the arguments for argparse. |
| `verify_feature_capability` | Method | Verify configured settings are supported for the configured repository.  This p… |
| `EnvironmentDefault` | Class | Get values from environment variable. |
| `format_usage` | Method |  |
| `EnvironmentFlag` | Class | Set boolean flag from environment variable. |
| `bool_from_env` | Method | Allow '0' and 'false' and 'no' to be False. |
| `format_usage` | Method |  |
| `check_status_code` | Function | Generate a helpful message based on the response from the repository.  Raise a… |
| `get_config` | Function | Read repository configuration from a file (i.e. ~/.pypirc).  Format: https://pa… |
| `get_file_size` | Function | Return the size of a file in KB, or MB if >= 1024 KB. |
| `get_repository_from_config` | Function | Get repository config command-line values or the .pypirc file. |
| `get_userpass_value` | Function | Get a credential (e.g. a username or password) from the configuration.  Uses th… |
| `make_requests_session` | Function | Prepare a requests Session with retries & twine's user-agent string. |
| `normalize_repository_url` | Function |  |
| `sanitize_url` | Function | Sanitize a URL.  Sanitize URLs, removing any user:password combinations and rep… |
| `Wheel` | Class |  |
| `find_candidate_metadata_files` | Method | Filter files that may be METADATA files. |
| `read` | Method |  |

## Classes

### `CredentialInput`

```python
twine.auth.CredentialInput(self, username: Optional[str] = None, password: Optional[str] = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `username` | `Optional` | `None` | pos/kw |
| `password` | `Optional` | `None` | pos/kw |

### `Private`

```python
twine.auth.Private(self, config: Dict[str, Optional[str]], input: twine.auth.CredentialInput) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `Dict` | `—` | pos/kw |
| `input` | `CredentialInput` | `—` | pos/kw |

### `Resolver`

```python
twine.auth.Resolver(self, config: Dict[str, Optional[str]], input: twine.auth.CredentialInput) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `Dict` | `—` | pos/kw |
| `input` | `CredentialInput` | `—` | pos/kw |

### `TrustedPublishingAuthenticator`

Base class that all auth implementations derive from

```python
twine.auth.TrustedPublishingAuthenticator(self, resolver: 'Resolver') -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `resolver` | `Resolver` | `—` | pos/kw |

### `TrustedPublishingToken`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
twine.auth.TrustedPublishingToken(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TrustedPublishingTokenRetrievalError`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
twine.auth.TrustedPublishingTokenRetrievalError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Inputs`

Represents structured user inputs.

```python
twine.commands.Inputs(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Distribution`

```python
twine.distribution.Distribution(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidConfiguration`

Raised when configuration is invalid.

```python
twine.exceptions.InvalidConfiguration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidDistribution`

Raised when a distribution is invalid.

```python
twine.exceptions.InvalidDistribution(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidPyPIUploadURL`

Repository configuration tries to use PyPI with an incorrect URL.

For example, https://pypi.org instead of https://upload.pypi.org/legacy.

```python
twine.exceptions.InvalidPyPIUploadURL(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidSigningConfiguration`

Both the sign and identity parameters must be present.

```python
twine.exceptions.InvalidSigningConfiguration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `InvalidSigningExecutable`

Signing executable must be installed on system.

```python
twine.exceptions.InvalidSigningExecutable(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NonInteractive`

Raised in non-interactive mode when credentials could not be found.

```python
twine.exceptions.NonInteractive(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PackageNotFound`

A package file was provided that could not be found on the file system.

This is only used when attempting to register a package_file.

```python
twine.exceptions.PackageNotFound(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `RedirectDetected`

A redirect was detected that the user needs to resolve.

In some cases, requests refuses to issue a new POST request after a
redirect. In order to prevent a confusing user experience, we raise this
e…

```python
twine.exceptions.RedirectDetected(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TrustedPublishingFailure`

Raised if we expected to use trusted publishing but couldn't.

```python
twine.exceptions.TrustedPublishingFailure(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TwineException`

Base class for all exceptions raised by twine.

```python
twine.exceptions.TwineException(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnreachableRepositoryURLDetected`

An upload attempt was detected to a URL without a protocol prefix.

All repository URLs must have a protocol (e.g., ``https://``).

```python
twine.exceptions.UnreachableRepositoryURLDetected(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnsupportedConfiguration`

An upload attempt was detected using features not supported by a repository.

The features specified either in configuration or on the command-line.

```python
twine.exceptions.UnsupportedConfiguration(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UploadToDeprecatedPyPIDetected`

An upload attempt was detected to deprecated PyPI domains.

The sites pypi.python.org and testpypi.python.org are deprecated.

```python
twine.exceptions.UploadToDeprecatedPyPIDetected(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `HashManager`

Manage our hashing objects for simplicity.

This will also allow us to better test this logic.

```python
twine.package.HashManager(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `Hexdigest`

Hexdigest(sha2, blake2)

```python
twine.package.Hexdigest(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PackageFile`

```python
twine.package.PackageFile(self, filename: str, comment: Optional[str], metadata: packaging.metadata.RawMetadata, python_version: str, filetype: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |
| `comment` | `Optional` | `—` | pos/kw |
| `metadata` | `RawMetadata` | `—` | pos/kw |
| `python_version` | `str` | `—` | pos/kw |
| `filetype` | `str` | `—` | pos/kw |

### `PackageMetadata`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
twine.package.PackageMetadata(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Repository`

```python
twine.repository.Repository(self, repository_url: str, username: Optional[str], password: Optional[str], disable_progress_bar: bool = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repository_url` | `str` | `—` | pos/kw |
| `username` | `Optional` | `—` | pos/kw |
| `password` | `Optional` | `—` | pos/kw |
| `disable_progress_bar` | `bool` | `False` | pos/kw |

### `SDist`

```python
twine.sdist.SDist(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `TarGzSDist`

```python
twine.sdist.TarGzSDist(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `ZipSDist`

```python
twine.sdist.ZipSDist(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

### `Settings`

Object that manages the configuration for Twine.

This object can only be instantiated with keyword arguments.

For example,

.. code-block:: python

    Settings(True, username='fakeusername')

Will…

```python
twine.settings.Settings(self, *, attestations: bool = False, sign: bool = False, sign_with: str = 'gpg', identity: Optional[str] = None, username: Optional[str] = None, password: Optional[str] = None, non_interactive: bool = False, comment: Optional[str] = None, config_file: str = '~/.pypirc', skip_existing: bool = False, cacert: Optional[str] = None, client_cert: Optional[str] = None, repository_name: str = 'pypi', repository_url: Optional[str] = None, verbose: bool = False, disable_progress_bar: bool = False, **ignored_kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `attestations` | `bool` | `False` | kw |
| `sign` | `bool` | `False` | kw |
| `sign_with` | `str` | `'gpg'` | kw |
| `identity` | `Optional` | `None` | kw |
| `username` | `Optional` | `None` | kw |
| `password` | `Optional` | `None` | kw |
| `non_interactive` | `bool` | `False` | kw |
| `comment` | `Optional` | `None` | kw |
| `config_file` | `str` | `'~/.pypirc'` | kw |
| `skip_existing` | `bool` | `False` | kw |
| `cacert` | `Optional` | `None` | kw |
| `client_cert` | `Optional` | `None` | kw |
| `repository_name` | `str` | `'pypi'` | kw |
| `repository_url` | `Optional` | `None` | kw |
| `verbose` | `bool` | `False` | kw |
| `disable_progress_bar` | `bool` | `False` | kw |
| `ignored_kwargs` | `Any` | `—` | **kwargs |

### `EnvironmentDefault`

Get values from environment variable.

```python
twine.utils.EnvironmentDefault(self, env: str, required: bool = True, default: Optional[str] = None, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `str` | `—` | pos/kw |
| `required` | `bool` | `True` | pos/kw |
| `default` | `Optional` | `None` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `EnvironmentFlag`

Set boolean flag from environment variable.

```python
twine.utils.EnvironmentFlag(self, env: str, **kwargs: Any) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `env` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

### `Wheel`

```python
twine.wheel.Wheel(self, filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

## Functions

### `configure_output`

```python
twine.cli.configure_output() -> None
```

### `dep_versions`

```python
twine.cli.dep_versions() -> str
```

**Returns:** `<class 'str'>`

### `dispatch`

```python
twine.cli.dispatch(argv: List[str]) -> Any
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `argv` | `List` | `—` | pos/kw |

**Returns:** `typing.Any`

### `list_dependencies_and_versions`

```python
twine.cli.list_dependencies_and_versions() -> List[Tuple[str, str]]
```

**Returns:** `typing.List[typing.Tuple[str, str]]`

### `check`

Check that a distribution will render correctly on PyPI and display the results.

This is currently only validates ``long_description``, but more checks could be
added.

:param dists:
    The distrib…

```python
twine.commands.check.check(dists: List[str], strict: bool = False) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `dists` | `List` | `—` | pos/kw |
| `strict` | `bool` | `False` | pos/kw |

**Returns:** `<class 'bool'>`

### `main`

Execute the ``check`` command.

:param args:
    The command-line arguments.

:return:
    The exit status of the ``check`` command.

```python
twine.commands.check.main(args: List[str]) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `List` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `main`

Execute the ``register`` command.

:param args:
    The command-line arguments.

```python
twine.commands.register.main(args: List[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `List` | `—` | pos/kw |

### `register`

Pre-register a package name with a repository before uploading a distribution.

Pre-registration is not supported on PyPI, so the ``register`` command is only
necessary if you are using a different r…

```python
twine.commands.register.register(register_settings: twine.settings.Settings, package: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `register_settings` | `Settings` | `—` | pos/kw |
| `package` | `str` | `—` | pos/kw |

### `main`

Execute the ``upload`` command.

:param args:
    The command-line arguments.

```python
twine.commands.upload.main(args: List[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `List` | `—` | pos/kw |

### `skip_upload`

Determine if a failed upload is an error or can be safely ignored.

:param response:
    The response from attempting to upload ``package`` to a repository.
:param skip_existing:
    If ``True``, use…

```python
twine.commands.upload.skip_upload(response: requests.models.Response, skip_existing: bool, package: twine.package.PackageFile) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `response` | `Response` | `—` | pos/kw |
| `skip_existing` | `bool` | `—` | pos/kw |
| `package` | `PackageFile` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `upload`

Upload one or more distributions to a repository, and display the progress.

If a package already exists on the repository, most repositories will return an
error response. However, if ``upload_setti…

```python
twine.commands.upload.upload(upload_settings: twine.settings.Settings, dists: List[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `upload_settings` | `Settings` | `—` | pos/kw |
| `dists` | `List` | `—` | pos/kw |

### `make_requests_session`

Prepare a requests Session with retries & twine's user-agent string.

```python
twine.repository.make_requests_session() -> requests.sessions.Session
```

**Returns:** `<class 'requests.sessions.Session'>`

### `check_status_code`

Generate a helpful message based on the response from the repository.

Raise a custom exception for recognized errors. Otherwise, print the
response content (based on the verbose option) before re-ra…

```python
twine.utils.check_status_code(response: requests.models.Response, verbose: bool) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `response` | `Response` | `—` | pos/kw |
| `verbose` | `bool` | `—` | pos/kw |

### `get_config`

Read repository configuration from a file (i.e. ~/.pypirc).

Format: https://packaging.python.org/specifications/pypirc/

If the default config file doesn't exist, return a default configuration for…

```python
twine.utils.get_config(path: str) -> Dict[str, Dict[str, Optional[str]]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `str` | `—` | pos/kw |

**Returns:** `typing.Dict[str, typing.Dict[str, typing.Optional[str]]]`

### `get_file_size`

Return the size of a file in KB, or MB if >= 1024 KB.

```python
twine.utils.get_file_size(filename: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `get_repository_from_config`

Get repository config command-line values or the .pypirc file.

```python
twine.utils.get_repository_from_config(config_file: str, repository: str, repository_url: Optional[str] = None) -> Dict[str, Optional[str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config_file` | `str` | `—` | pos/kw |
| `repository` | `str` | `—` | pos/kw |
| `repository_url` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Dict[str, typing.Optional[str]]`

### `get_userpass_value`

Get a credential (e.g. a username or password) from the configuration.

Uses the following rules:

1. If ``cli_value`` is specified, use that.
2. If ``config[key]`` is specified, use that.
3. If ``pr…

```python
twine.utils.get_userpass_value(cli_value: Optional[str], config: Dict[str, Optional[str]], key: str, prompt_strategy: Optional[Callable[[], str]] = None) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cli_value` | `Optional` | `—` | pos/kw |
| `config` | `Dict` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `prompt_strategy` | `Optional` | `None` | pos/kw |

**Returns:** `typing.Optional[str]`

### `make_requests_session`

Prepare a requests Session with retries & twine's user-agent string.

```python
twine.utils.make_requests_session() -> requests.sessions.Session
```

**Returns:** `<class 'requests.sessions.Session'>`

### `normalize_repository_url`

```python
twine.utils.normalize_repository_url(url: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `sanitize_url`

Sanitize a URL.

Sanitize URLs, removing any user:password combinations and replacing them with
asterisks.  Returns the original URL if the string is a non-matching pattern.

:param url:
    str cont…

```python
twine.utils.sanitize_url(url: str) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `url` | `str` | `—` | pos/kw |

**Returns:** `<class 'str'>`

## Methods

### `twine.auth.Private` methods

### `choose`

```python
twine.auth.Private.choose(interactive: bool) -> Type[ForwardRef('Resolver')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interactive` | `bool` | `—` | pos/kw |

**Returns:** `typing.Type[ForwardRef('Resolver')]`

### `get_password_from_keyring`

```python
twine.auth.Private.get_password_from_keyring(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_username_from_keyring`

```python
twine.auth.Private.get_username_from_keyring(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `is_pypi`

As of 2024-01-01, PyPI requires API tokens for uploads.

```python
twine.auth.Private.is_pypi(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `make_trusted_publishing_token`

```python
twine.auth.Private.make_trusted_publishing_token(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `password_from_keyring_or_trusted_publishing_or_prompt`

```python
twine.auth.Private.password_from_keyring_or_trusted_publishing_or_prompt(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `prompt`

```python
twine.auth.Private.prompt(self, what: str, how: Optional[Callable[..., str]] = None) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `what` | `str` | `—` | pos/kw |
| `how` | `Optional` | `None` | pos/kw |

**Returns:** `<class 'str'>`

### `username_from_keyring_or_prompt`

```python
twine.auth.Private.username_from_keyring_or_prompt(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `twine.auth.Resolver` methods

### `choose`

```python
twine.auth.Resolver.choose(interactive: bool) -> Type[ForwardRef('Resolver')]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `interactive` | `bool` | `—` | pos/kw |

**Returns:** `typing.Type[ForwardRef('Resolver')]`

### `get_password_from_keyring`

```python
twine.auth.Resolver.get_password_from_keyring(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `get_username_from_keyring`

```python
twine.auth.Resolver.get_username_from_keyring(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `is_pypi`

As of 2024-01-01, PyPI requires API tokens for uploads.

```python
twine.auth.Resolver.is_pypi(self) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `make_trusted_publishing_token`

```python
twine.auth.Resolver.make_trusted_publishing_token(self) -> Optional[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `typing.Optional[str]`

### `password_from_keyring_or_trusted_publishing_or_prompt`

```python
twine.auth.Resolver.password_from_keyring_or_trusted_publishing_or_prompt(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `prompt`

```python
twine.auth.Resolver.prompt(self, what: str, how: Callable[..., str]) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `what` | `str` | `—` | pos/kw |
| `how` | `Callable` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `username_from_keyring_or_prompt`

```python
twine.auth.Resolver.username_from_keyring_or_prompt(self) -> str
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'str'>`

### `twine.distribution.Distribution` methods

### `read`

```python
twine.distribution.Distribution.read(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `twine.exceptions.RedirectDetected` methods

### `from_args`

```python
twine.exceptions.RedirectDetected.from_args(repository_url: str, redirect_url: str) -> 'RedirectDetected'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `repository_url` | `str` | `—` | pos/kw |
| `redirect_url` | `str` | `—` | pos/kw |

**Returns:** `RedirectDetected`

### `twine.exceptions.UploadToDeprecatedPyPIDetected` methods

### `from_args`

Return an UploadToDeprecatedPyPIDetected instance.

```python
twine.exceptions.UploadToDeprecatedPyPIDetected.from_args(target_url: str, default_url: str, test_url: str) -> 'UploadToDeprecatedPyPIDetected'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `target_url` | `str` | `—` | pos/kw |
| `default_url` | `str` | `—` | pos/kw |
| `test_url` | `str` | `—` | pos/kw |

**Returns:** `UploadToDeprecatedPyPIDetected`

### `twine.package.HashManager` methods

### `hash`

Hash the file contents.

```python
twine.package.HashManager.hash(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `hexdigest`

Return the hexdigest for the file.

```python
twine.package.HashManager.hexdigest(self) -> twine.package.Hexdigest
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'twine.package.Hexdigest'>`

### `twine.package.PackageFile` methods

### `add_attestations`

```python
twine.package.PackageFile.add_attestations(self, attestations: List[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `attestations` | `List` | `—` | pos/kw |

### `add_gpg_signature`

```python
twine.package.PackageFile.add_gpg_signature(self, signature_filepath: str, signature_filename: str) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `signature_filepath` | `str` | `—` | pos/kw |
| `signature_filename` | `str` | `—` | pos/kw |

### `from_filename`

```python
twine.package.PackageFile.from_filename(filename: str, comment: Optional[str]) -> 'PackageFile'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `str` | `—` | pos/kw |
| `comment` | `Optional` | `—` | pos/kw |

**Returns:** `PackageFile`

### `metadata_dictionary`

Merge multiple sources of metadata into a single dictionary.

Includes values from filename, PKG-INFO, hashers, and signature.

```python
twine.package.PackageFile.metadata_dictionary(self) -> twine.package.PackageMetadata
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'twine.package.PackageMetadata'>`

### `run_gpg`

```python
twine.package.PackageFile.run_gpg(gpg_args: Tuple[str, ...]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `gpg_args` | `Tuple` | `—` | pos/kw |

### `sign`

```python
twine.package.PackageFile.sign(self, sign_with: str, identity: Optional[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `sign_with` | `str` | `—` | pos/kw |
| `identity` | `Optional` | `—` | pos/kw |

### `twine.repository.Repository` methods

### `close`

```python
twine.repository.Repository.close(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `package_is_uploaded`

Determine if a package has been uploaded to PyPI already.

.. warning:: This does not support indexes other than PyPI or TestPyPI

:param package:
    The package file that will otherwise be uploaded…

```python
twine.repository.Repository.package_is_uploaded(self, package: twine.package.PackageFile, bypass_cache: bool = False) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `PackageFile` | `—` | pos/kw |
| `bypass_cache` | `bool` | `False` | pos/kw |

**Returns:** `<class 'bool'>`

### `register`

```python
twine.repository.Repository.register(self, package: twine.package.PackageFile) -> requests.models.Response
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `PackageFile` | `—` | pos/kw |

**Returns:** `<class 'requests.models.Response'>`

### `release_urls`

```python
twine.repository.Repository.release_urls(self, packages: List[twine.package.PackageFile]) -> Set[str]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `packages` | `List` | `—` | pos/kw |

**Returns:** `typing.Set[str]`

### `set_certificate_authority`

```python
twine.repository.Repository.set_certificate_authority(self, cacert: Optional[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `cacert` | `Optional` | `—` | pos/kw |

### `set_client_certificate`

```python
twine.repository.Repository.set_client_certificate(self, clientcert: Optional[str]) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `clientcert` | `Optional` | `—` | pos/kw |

### `upload`

```python
twine.repository.Repository.upload(self, package: twine.package.PackageFile, max_redirects: int = 5) -> requests.models.Response
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `PackageFile` | `—` | pos/kw |
| `max_redirects` | `int` | `5` | pos/kw |

**Returns:** `<class 'requests.models.Response'>`

### `verify_package_integrity`

```python
twine.repository.Repository.verify_package_integrity(self, package: twine.package.PackageFile) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `package` | `PackageFile` | `—` | pos/kw |

### `twine.sdist.SDist` methods

### `read`

```python
twine.sdist.SDist.read(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `twine.sdist.TarGzSDist` methods

### `read`

```python
twine.sdist.TarGzSDist.read(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `twine.sdist.ZipSDist` methods

### `read`

```python
twine.sdist.ZipSDist.read(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

### `twine.settings.Settings` methods

### `check_repository_url`

Verify we are not using legacy PyPI.

:raises twine.exceptions.UploadToDeprecatedPyPIDetected:
    The configured repository URL is for legacy PyPI.

```python
twine.settings.Settings.check_repository_url(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `create_repository`

Create a new repository for uploading.

```python
twine.settings.Settings.create_repository(self) -> twine.repository.Repository
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'twine.repository.Repository'>`

### `from_argparse`

Generate the Settings from parsed arguments.

```python
twine.settings.Settings.from_argparse(args: argparse.Namespace) -> 'Settings'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `Namespace` | `—` | pos/kw |

**Returns:** `Settings`

### `register_argparse_arguments`

Register the arguments for argparse.

```python
twine.settings.Settings.register_argparse_arguments(parser: argparse.ArgumentParser) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `parser` | `ArgumentParser` | `—` | pos/kw |

### `verify_feature_capability`

Verify configured settings are supported for the configured repository.

This presently checks:
- ``--skip-existing`` was only provided for PyPI and TestPyPI

:raises twine.exceptions.UnsupportedConf…

```python
twine.settings.Settings.verify_feature_capability(self) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `twine.utils.EnvironmentDefault` methods

### `format_usage`

```python
twine.utils.EnvironmentDefault.format_usage(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `twine.utils.EnvironmentFlag` methods

### `bool_from_env`

Allow '0' and 'false' and 'no' to be False.

```python
twine.utils.EnvironmentFlag.bool_from_env(val: Optional[str]) -> bool
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `val` | `Optional` | `—` | pos/kw |

**Returns:** `<class 'bool'>`

### `format_usage`

```python
twine.utils.EnvironmentFlag.format_usage(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `twine.wheel.Wheel` methods

### `find_candidate_metadata_files`

Filter files that may be METADATA files.

```python
twine.wheel.Wheel.find_candidate_metadata_files(names: List[str]) -> List[List[str]]
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `names` | `List` | `—` | pos/kw |

**Returns:** `typing.List[typing.List[str]]`

### `read`

```python
twine.wheel.Wheel.read(self) -> bytes
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `<class 'bytes'>`

